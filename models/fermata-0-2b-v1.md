---
release_date: "September 17, 2026"
model_name: "Fermata 0.2B v1"
category: "music"
summary: "From-scratch 201M decoder-only transformer for symbolic multi-track music generation — a compact symbolic conditioning header becomes a bar-major REMI+ token stream that decodes to MusicXML/MIDI for rendering by a General MIDI SoundFont."
slug: "fermata-0-2b-v1"
---

# Fermata 0.2B v1

Fermata 0.2B v1 is a 201M-parameter decoder-only transformer for **symbolic** multi-track music generation, trained from scratch — the `LlamaForCausalLM` layout is used for tooling compatibility only, and no Llama weights are involved. It does not produce audio: it emits bar-major symbolic tokens through a custom REMI+ tokenizer (`tokenizer_v2`, 9,507-token vocabulary, 24 TPQN), and the project pipeline decodes them to MusicXML/MIDI, which a General MIDI-compatible renderer or SoundFont then turns into sound. Conditioning is a compact header — genre, ensemble type, tempo (5–999 BPM), key (−7…+7), mode, meter, and an instrument plan of General MIDI programs plus an optional `<DRUM_TRACK>` — laid out as `BOS [GENRE] [ENSEMBLE] TEMPO KEY METER <PLAN> {TRACK|DRUM}* <PLAN_END> (BAR ...)* EOS`. Tracks are interleaved bar by bar so every instrument advances together and parts tend to terminate together. Three instruction-tuned tasks are supported: GENERATE from the header, CONTINUE from an existing prefix, and INFILL of masked bars; both conditional tasks scored 12/12 on held-out prompts, with an in-key ratio of 0.81 and dissonance of 0.29 against roughly 0.96 / 0.15 for real human scores. The backbone is 17 layers at d_model 1024 with 16 query / 4 KV heads (GQA), a 2,816-wide SwiGLU FFN, RoPE and RMSNorm. Context is 4,096 tokens (about 35 bars) even though training used 2,048-token windows, so longer pieces are stitched from CONTINUE passes. Pretraining ran 3 epochs / 13,821 steps at global batch 256 over roughly 1.18M bar-major windows with ×12 transposition, in fp8 (torchao, tensorwise) with `torch.compile` on a single 96 GB RTX PRO 6000 Blackwell; the shipped BF16 weights are ~403 MB, and the released checkpoint is the step-299 instruction-tuned snapshot (760 steps, 2 epochs, best validation loss 0.3088) built from PDMX, KernScores/Humdrum, OpenScore Lieder and The Session. Two post-release defects are documented and deliberately left unpatched for reproducibility: a builder bug meant the BPE merges were never applied, so the model effectively trained on an atomic token stream, and MusicXML's 1-based `midi-unpitched` values left drum pitches shifted by +1 GM key (subtract one at render time, or run the optional `sanitize_drums` pass). Recommended sampling is temperature 0.7, top_k 24, repetition penalty ≈1.12; `frequency_penalty` is explicitly to be avoided because it destabilises structural tokens such as `BAR`, `TRK` and `PLAN`. Apache-2.0. Published as `haster/Clef-0.2B` and renamed on October 2, 2026, and explicitly unrelated to Cloudflare's Clef decision models; a successor with a new tokenizer and a GDN-hybrid architecture is planned.

## Links

- HuggingFace: https://huggingface.co/haster/Fermata-0.2B-v1

## Features

- music_gen: yes
- musical_notation: yes
- instrument_control: yes
- streaming: no
- input_modalities: symbolic conditioning header (genre, ensemble, tempo, key, mode, meter, instrument plan), existing prefix, or masked bars
- output: MusicXML / MIDI (symbolic only, no audio — render with a General MIDI SoundFont or MuseScore)
- license: Apache-2.0
- parameters: 201,398,272 (~0.2B), decoder-only
- architecture: 17 layers, d_model 1024, 16 query / 4 KV heads (GQA), FFN 2816, RoPE, RMSNorm, SwiGLU
- serialization: LlamaForCausalLM layout, trained from scratch (no Llama weights)
- tokenizer: custom bar-major REMI+ (`tokenizer_v2`, 9,507 vocab, 24 TPQN) — not an AutoTokenizer
- context: 4,096 tokens (~35 bars); trained on 2,048-token windows
- tasks: GENERATE, CONTINUE, INFILL
- precision: BF16 release (~403 MB); fp8 tensorwise via torchao for training
- pretraining: 3 epochs, 13,821 steps, global batch 256, ~1.18M bar-major windows, x12 transposition
- instruction_tuning: 760 steps, 2 epochs, best validation loss 0.3088 at step 299 (adopted)
- training_data: PDMX, KernScores/Humdrum, OpenScore Lieder, The Session
- training_hardware: 1x NVIDIA RTX PRO 6000 Blackwell (96 GB), ~80k tokens/s
- sampling: temperature 0.7, top_k 24, repetition_penalty ~1.12 (avoid frequency_penalty)
- evaluation: in-key 0.81, dissonance 0.29, co-termination spread 0.14, early part death 0.10; CONTINUE 12/12, INFILL 12/12
- known_issues: BPE merges never applied (atomic token stream); drum pitches shifted by +1 GM key
- former_name: Clef-0.2B (renamed October 2, 2026)

## Comparison

- music_gen: ✅
- input_modalities: symbolic MIDI/MusicXML
- streaming: ❌
- languages: -
- license: Apache-2.0

## Innovation

Bar-major interleaving as a structural prior: instead of encoding one instrument's tokens through to the end before moving to the next, tracks are laid out bar by bar so all parts advance in lockstep and terminate together — directly attacking the "parts die at different times" failure that makes naive multi-track symbolic generation sound wrong, with co-termination spread measured as an explicit metric. The conditioning header is deliberately coarse (nine genres, six ensemble types) so a 0.2B model trained from scratch on ~1.18M windows still produces coherent, key-consistent multi-instrument scores, and a single instruction-tuned checkpoint serves all three of generation, continuation and masked-bar infilling.