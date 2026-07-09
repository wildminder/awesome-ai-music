---
release_date: "August 2025"
model_name: "Magenta Realtime"
category: "music"
summary: "Google DeepMind's open music generation model for continuous, streaming audio steered by text prompts or audio examples with sub-second style latency."
slug: "magenta-realtime"
---

# Magenta Realtime

Open music generation model from Google DeepMind enabling continuous generation of musical audio steered by text prompts or audio examples.

## Links

- GitHub: https://github.com/magenta/magenta-realtime
- HuggingFace: https://huggingface.co/google/magenta-realtime
- arXiv: https://arxiv.org/abs/2508.04651

## Features

- music_gen: yes (Real-time)
- input_modalities: text, reference audio
- streaming: yes (~2s latency)
- license: Apache-2.0 (code), CC-BY-4.0 (model) — both: Apache-2.0 for code, CC-BY-4.0 for model weights
- text_to_music: yes
- audio_to_music: yes
- reference_audio: yes
- continuous_generation: yes
- real_time: yes
- context: 10 seconds
- training_data: ~190k hours

## Comparison

- music_gen: ✅
- input_modalities: text
- streaming: ✅
- languages: -
- license: Apache-2.0 / CC-BY-4.0

## Innovation

Continuous streaming music generation with style-prompt latency around 2 seconds — built on the Magenta line from Google DeepMind and trained on roughly 190k hours of audio.
