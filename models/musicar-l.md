---
release_date: "October 25, 2026"
model_name: "musicar-L"
category: "music"
summary: "464M-parameter decoder-only transformer that writes multi-instrument MIDI one note at a time, pretrained from scratch on 8.3B notes of public MIDI data."
slug: "musicar-l"
---

# musicar-L

musicar-L is a 464.24M-parameter decoder-only transformer for **symbolic** multi-instrument music generation: it emits MIDI notes, not audio, and renders through a General MIDI SoundFont. One sequence position is one whole note on a 20 ms grid, and five cascade output heads choose its delta-time, instrument, pitch, duration and velocity one after another, each head reading a running state updated by the previous head's sampled choice — a factorised compound token that avoids a flat joint vocabulary. The trunk is 28 pre-norm blocks at width 1152 with RMSNorm, causal full attention (18 heads), RoPE, QK-norm and SwiGLU feed-forward layers. Context is 2,048 notes (roughly 1–4 minutes), covering 129 instruments (128 General MIDI programs plus drums); there are no bar, beat or tempo tokens. This is the uncaptioned pretrained base: besides a MIDI prompt its only controls are two optional window conditions (the set of instruments and the notes per second), so text-conditioned generation lives in the separate `musicar-L-caption`, and `musicar-S` / `musicar-S-piano` are smaller siblings. Training ran from scratch for 126,582 steps over 8.3B notes (GigaMIDI 0.4, Aria-MIDI 0.3, Discover MIDI 0.3) with Muon + AdamW and fp8 torchao matmuls on a single rented RTX 5090 in about 41 hours; teacher-forced validation cross-entropy reached 1.679 nats per note on clean GigaMIDI. BF16 weights are released under CC BY-NC-SA 4.0, with `model.safetensors` and a `generate.py` CLI in the companion code repository.

## Links

- HuggingFace: https://huggingface.co/Dimitri-206265/musicar-L
- GitHub: https://github.com/DmytroHilei/Music_generative_model

## Features

- music_gen: yes
- musical_notation: yes
- instrument_control: yes
- text_to_music: no
- streaming: no
- input_modalities: MIDI prompt, optional instrument-set and notes-per-second window conditions
- output: MIDI (symbolic only, no audio; rendered with a General MIDI SoundFont)
- license: CC BY-NC-SA 4.0
- parameters: 464.24M (trunk 445.98M, cascade heads 16.28M, embeddings 1.99M)
- architecture: 28 pre-norm decoder blocks, d_model 1152, 18 attention heads, RMSNorm, RoPE, QK-norm, SwiGLU
- tokenization: one compound token per note on a 20 ms grid (delta-time 512, instrument 129, pitch 130, duration 512, velocity 32), no bar/beat/tempo tokens
- cascade_heads: five sequential heads (delta-time → instrument → pitch → duration → velocity), each reading a running state h_t + sum of embeddings of prior choices
- context: 2,048 notes (~1–4 min), sliding KV-cache rebuild every 512 notes
- instruments: 129 (128 General MIDI programs + drums)
- conditions: window instrument set and notes per second, both optional with an explicit "none" value
- sampling: temperature, top-k, top-p, separate instrument temperature, min-notes, MIDI-prompt continuation
- precision: BF16 release weights; bf16 autocast with fp8 (torchao float8) training matmuls
- training_data: GigaMIDI 0.4, Aria-MIDI 0.3, Discover MIDI 0.3 — 8.3B notes, ~1.8 epochs, random ±5 semitone transposition
- training: 126,582 steps, 65,536 notes/step, Muon (block matrices) + AdamW, WSD schedule, 1× RTX 5090 ~41 h
- evaluation: 1.679 nats/note on clean GigaMIDI validation (instrument head 0.117)
- variants: musicar-L-caption (text-conditioned), musicar-S, musicar-S-piano

## Comparison

- music_gen: ✅
- input_modalities: MIDI prompt
- streaming: ❌
- languages: -
- license: CC BY-NC-SA 4.0

## Innovation

Factorising a compound note token into five cascade heads: instead of a single joint vocabulary over delta-time, instrument, pitch, duration and velocity, each head sees a running state that accumulates an embedding of every attribute already chosen, so the attributes are modelled jointly at a fraction of the vocabulary cost. Combined with a pure 20 ms-grid note stream that carries no bar, beat or tempo tokens, the model learns timing and multi-instrument texture directly from data, and the two optional window conditions (instrument set, notes per second) give coarse global control without any text encoder — the base checkpoint stays deliberately caption-free while `musicar-L-caption` adds text conditioning on top.
