---
release_date: "August 9, 2024"
model_name: "Qwen2-Audio-7B-Instruct"
category: "audio_understanding"
summary: "Alibaba's 7B audio-language model that supports both voice chat (no text input) and audio analysis with structured text responses."
slug: "qwen2-audio"
---

# Qwen2-Audio-7B-Instruct

Alibaba's Qwen2-Audio-7B-Instruct — a large audio-language model that supports two interaction modes: voice chat (audio-in, audio+text-out without user-typed text) and audio analysis (audio+text-in, text-out). Released alongside the Qwen2-Audio-7B pretrained variant.

## Links

- HuggingFace: https://huggingface.co/Qwen/Qwen2-Audio-7B-Instruct
- GitHub: https://github.com/QwenLM/Qwen2-Audio
- Blog: https://qwenlm.github.io/blog/qwen2-audio/
- arXiv: https://arxiv.org/abs/2407.10759

## Features

- parameters: 7B
- use_case: voice chat, audio analysis (ASR + audio captioning + audio QA)
- input: audio (+ optional text)
- audio_length: short to medium (one-shot speech / audio analysis)
- base_model: Qwen2-Audio-7B (pretrained)
- music_generation: no
- audio_generation: no
- reasoning: limited (instruct-tuned)
- voice_chat: yes (no text input required)
- audio_analysis: yes
- asr: yes
- architecture: Qwen2 audio-language model
- license: Apache-2.0

## Comparison

- use_case: voice chat + analysis
- input: audio + text
- audio_length: short-medium
- base_model: Qwen2-Audio
- license: Apache-2.0

## Innovation

Qwen-style audio-language architecture that supports **two distinct interaction modes** in one model — pure voice chat (audio in, free-form text out without user-typed prompts) and structured audio analysis (audio + text instruction in, text-only analysis out) — both served by the same instruct-tuned checkpoint.
