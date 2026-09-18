---
release_date: "September 14, 2026"
model_name: "MuLaCover"
category: "music"
summary: "Controllable cover-song and remix model from the HeartMuLa team — reference audio or melody/chord MIDI, plus new lyrics and a structured style prompt, become a fully re-sung and re-arranged track."
slug: "mulacover"
---

# MuLaCover

MuLaCover is a controllable cover-song and music-remix model from the HeartMuLa team (MuLa Labs / Vera Praxis Lab). Rather than copying reference audio frame by frame, it transcribes a reference track into symbolic conditions — melody, harmony, and optional drum parts — and injects that symbolic lead sheet into a pretrained text-to-song backbone through gated adaptive cross-attention, so the source's melodic and harmonic identity is preserved while vocals, lyrics, arrangement, and style are regenerated. A second control path skips audio entirely: supply `--melody_midi` and `--chord_midi` (with optional `--drum_midi`) and MuLaCover composes the cover from a symbolic score. Lyrics are UTF-8 text with section markers (`[Intro]`, `[Verse]`, `[Chorus]`, `[Interlude]`, `[Bridge]`, `[Outro]`) and can be kept or rewritten; style is a single line of named fields such as `topic:[Longing]; genre:[country]; instrument:[Strings,acoustic guitar]; mood:[hopeful]`. The pipeline pairs the backbone with HeartCodec (audio codec), Qwen3-Embedding-0.6B (style encoder), and a SymbolicTranscriptor built on YourMT3 plus a chord recognizer, with lazy loading so only the active stage occupies GPU memory. Training uses cross-cover training with partial conditioning; full-song cover generation was evaluated objectively across six systems and in a 22-participant human study across four systems. Source code is Apache-2.0, but the official weights and their generated outputs are CC BY-NC 4.0 with additional `MODEL_LICENSE` terms — commercial use requires written authorization from MuLa Labs. Built on the HeartMuLa backbone (paper: arXiv 2601.10547).

## Links

- HuggingFace: https://huggingface.co/HeartMuLa/MuLaCover
- GitHub: https://github.com/HeartMuLa/MuLaCover

## Features

- parameters: not stated (five safetensors shards)
- music_gen: yes
- cover_songs: yes
- input_modalities: reference audio, melody/chord MIDI, lyrics + style tags
- streaming: no
- languages: zh/en/ja/ko/es (inherited from the multilingual HeartMuLa backbone)
- license: CC BY-NC 4.0 (weights and outputs); Apache-2.0 (source code)
- architecture: symbolic lead sheet injected into a text-to-song backbone via gated adaptive cross-attention
- style_prompt: named fields — topic, genre, instrument, mood
- reference_audio: yes
- melody_control: yes (melody + chord MIDI required, drums optional)
- symbolic_control: reference audio is converted to melody, harmony and optional drum conditions
- companion_models: HeartCodec, Qwen3-Embedding-0.6B, SymbolicTranscriptor (YourMT3 + chord recognition)
- lyrics_support: yes (section markers, keep or rewrite)
- training: cross-cover training with partial conditioning
- vram: lazy loading keeps only the active stage resident; tested with PyTorch 2.10 / CUDA 13 on an NVIDIA B300
- evaluation: six-system objective study plus a 22-participant human study

## Comparison

- music_gen: ✅
- input_modalities: audio, MIDI, text
- streaming: ❌
- languages: zh/en/ja/ko/es
- license: CC BY-NC 4.0

## Innovation

Symbolic rather than acoustic reference conditioning: the reference song is reduced to a lead sheet (melody, chords, optional drums) and injected through gated adaptive cross-attention, which separates "what the song is" from "how it is performed" — enabling remixes that keep identity while changing genre, instrumentation, topic, mood, and lyrics, and enabling pure MIDI-to-cover generation with no audio reference at all.
