---
release_date: "March 4, 2025"
model_name: "Audio Flamingo 2"
category: "audio_understanding"
summary: "NVIDIA's 3B audio-language model that beats larger proprietary systems on 20+ audio-understanding and reasoning benchmarks, with up to 5 minutes of long-audio understanding."
slug: "audio-flamingo-2"
---

# Audio Flamingo 2

NVIDIA's PyTorch implementation of Audio Flamingo 2 (paper: arXiv 2503.03983). A 3B parameter cross-attention audio-language model built on a Qwen-2.5 backbone. Adds two new datasets (AudioSkills for expert reasoning and LongAudio for long-audio understanding) and reports SOTA across 20+ audio-understanding and reasoning benchmarks while being smaller and trained on public data.

## Links

- HuggingFace: https://huggingface.co/nvidia/audio-flamingo-2
- GitHub: https://github.com/NVIDIA/audio-flamingo
- arXiv: https://arxiv.org/abs/2503.03983
- Demo: https://research.nvidia.com/labs/adlr/AF2/

## Features

- parameters: 3B
- use_case: audio understanding, reasoning, captioning, transcription, multi-turn chat
- input: audio + text
- audio_length: up to 5 minutes
- base_model: Qwen-2.5 (audio encoder + cross-attention)
- music_gen: no
- audio_generation: no
- reasoning: yes
- long_audio: yes (5 minutes)
- architecture: cross-attention audio-language model
- training_data: nvidia/AudioSkills + nvidia/LongAudio
- license: NVIDIA OneWay Noncommercial License (checkpoints); MIT (code)

## Comparison

- use_case: reasoning
- input: audio + text
- audio_length: 5 min
- base_model: Qwen-2.5
- license: NVIDIA OneWay Noncommercial License

## Innovation

Cross-attention audio-language model that builds Flamingo-style few-shot learning on top of Qwen-2.5, taught on AudioSkills and LongAudio — SOTA-class audio reasoning despite being only 3B parameters and trained exclusively on public data.
