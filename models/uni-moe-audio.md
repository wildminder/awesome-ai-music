---
release_date: "October 16, 2025"
model_name: "Uni-MoE (Audio)"
category: "music"
summary: "MoE-based omnimodal model covering voice cloning, TTS, text-to-music, and video-to-music with dynamic expert routing."
slug: "uni-moe-audio"
---

# Uni-MoE (Audio)

MoE-based omnimodal model with voice cloning, TTS, T2M (text-to-music), and V2M (video-to-music).

## Links

- GitHub: https://github.com/HITsz-TMG/Uni-MoE
- arXiv: https://arxiv.org/abs/2510.13344

## Features

- music_gen: yes
- voice_cloning: yes
- input_modalities: text, video
- streaming: no
- license: Apache-2.0
- tts: yes
- text_to_music: yes
- video_to_music: yes
- dynamic_routing: yes

## Comparison

- music_gen: ✅
- input_modalities: text
- streaming: ❌
- languages: -
- license: Apache-2.0

## Innovation

Mixture-of-experts omnimodal architecture with dynamic routing across voice cloning, TTS, text-to-music, and video-to-music — a single model that dispatches on input modality.
