---
release_date: "September 2, 2026"
model_name: "MIDI Gen AI"
category: "music"
summary: "Real-time MIDI continuation: a from-scratch GPT-style transformer (113M v3) that answers a played phrase with a coherent symbolic continuation, built for live jamming inside Ableton Live."
slug: "midigenai"
---

# MIDI Gen AI (midigenai)

midigenai is a GPT-style decoder-only transformer trained from scratch on ~408k symbolic MIDI files (Lakh, LAMD, MAESTRO, POP909, GiantMIDI) for real-time music continuation — play a phrase and the model answers with a coherent continuation, streaming note by note. The default v3 checkpoint (113M parameters) uses a 641-token MidiTok event vocabulary and a 2048-token context, and an MLX backend runs it at ~800 tokens/s on Apple silicon — fast enough for call-and-response jamming inside Ableton Live (~0.5 s latency via the ableton-mcp-pro control surface). The model is symbolic-only: it reads and writes MIDI, with no audio synthesis.

## Links

- HuggingFace: https://huggingface.co/nicholasbien/midigenai
- GitHub: https://github.com/nicholasbien/midigenai
- Demo: https://nicholasbien.com/midi

## Features

- music_gen: yes
- streaming: yes
- real_time: yes
- input_modalities: MIDI
- output: MIDI (symbolic only, no audio)
- license: MIT
- parameters: 113M (v3 default); 25M pilot
- architecture: GPT-style decoder-only transformer (RoPE, SwiGLU, RMSNorm, FlashAttention-2)
- vocabulary: 641 event tokens (MidiTok MIDILike)
- context: 2048 tokens
- training_data: ~408k MIDI files (Lakh, LAMD, MAESTRO, POP909, GiantMIDI)
- checkpoints: v2-pilot, v2-production, v2-100m, v3 (default)
- ableton_integration: yes (via ableton-mcp-pro)
- mlx_backend: yes (~800 tok/s on Apple silicon)
- tempo_invariant: yes

## Comparison

- music_gen: ✅
- input_modalities: MIDI
- streaming: ✅
- languages: -
- license: MIT

## Innovation

Small-scale from-scratch design: a custom 641-token event vocabulary (MidiTok MIDILike) with RoPE/SwiGLU/RMSNorm beats GPT-2 fine-tunes on every axis (~2.5x fewer tokens per note, 60% less repetition, an order of magnitude faster inference); tempo is stripped at training and re-applied at decode for tempo-invariant learning, and a preallocated-KV-cache MLX backend with one-step-ahead pipelined decoding makes real-time DAW integration practical.
