---
release_date: "July 9, 2026"
model_name: "MuScriptor"
category: "audio_understanding"
summary: "Open multi-instrument MIDI transcription model from Mirelo AI + Kyutai + IRCAM"
slug: "muscriptor"
---

# MuScriptor

MuScriptor is the first open-source multi-instrument music transcription model trained at scale — co-developed by Mirelo AI, Kyutai, and IRCAM. Trained on 170k songs spanning classical to heavy metal.

## Links

- Blog: https://www.mirelo.ai/blog/turning-audio-to-midi
- HuggingFace: https://huggingface.co/MuScriptor
- HuggingFace model: https://huggingface.co/MuScriptor/muscriptor-medium
- GitHub: https://github.com/muscriptor/muscriptor
- Online demo: https://muscriptor.kyutai.org
- Paper: https://arxiv.org/abs/2607.08168

## Features

- parameters: small / medium / large (multi-size release)
- use_case: multi-instrument music transcription to MIDI
- input: full-mix audio (wav + mp3 streamed via CLI / web UI)
- output_format: multi-track MIDI
- audio_length: long (full songs, classical to heavy metal)
- training_scale: 170k songs
- upstream_application: Mirelo Studio Audio-to-MIDI tool (chord / key / tempo detection on top)
- library: torch + transformers (served via uvx)
- model_size_variants: muscriptor-small, muscriptor-medium, muscriptor-large
- weights_license: cc-by-nc-4.0 (gated, requires HF ack)
- code_license: MIT (GitHub repo)
- audio_language_task: yes
- music_understanding: yes
- music_generation: no
- continuous_monitoring: no
- streaming_input: yes (uvx transcribe)
- benchmark: Mirelo internal + Mirelo Studio tool

## Comparison

- use_case: multi-instrument music transcription
- input: full-mix audio
- audio_length: long
- base_model: custom Mirelo + Kyutai + IRCAM
- license: CC-BY-NC-4.0

## Innovation

First open-source music transcription model trained at scale — 170k songs including classical to heavy metal. Co-built by Mirelo AI, Kyutai, and IRCAM. The Mirelo Studio Audio-to-MIDI tool layers chord / key / tempo detection on top, giving users the full harmonic picture from raw audio input.