---
release_date: "May 20, 2026"
model_name: "Stable Audio 3"
category: "music"
summary: "Stability AI's open-weight diffusion-transformer audio generation family — text-to-audio, audio-to-audio editing, and inpainting/continuation across music and sound-effects variants."
slug: "stable-audio-3"
---

# Stable Audio 3

A state-of-the-art open platform for fast, high-quality audio and music generation built around a diffusion transformer and the SAME (Semantic-Acoustic Music Encoder) autoencoder. Ships in four variants — Small-Music, Small-SFX, Medium, and Large (API only) — covering lightweight CPU inference up to the highest-quality 2.7B parameter model. Supports variable-length generation up to 380 seconds and built-in LoRA fine-tuning.

## Links

- GitHub: https://github.com/Stability-AI/stable-audio-3
- HuggingFace: https://huggingface.co/collections/stabilityai/stable-audio-3
- HuggingFace: https://huggingface.co/collections/stabilityai/stable-audio-3-extra
- Demo: https://huggingface.co/spaces/stabilityai/stable-audio-3
- Blog: https://stability.ai/news-updates/meet-stable-audio-3-the-model-family-built-for-artistic-experimentation-with-open-weight-models
- arXiv: https://arxiv.org/abs/2605.17991
- LoRA Training: https://github.com/dada-bots/underfit

## Features

- parameters: 433M (Small) / 1.4B (Medium) / 2.7B (Large, API only)
- music_gen: yes
- input_modalities: text, audio (audio-to-audio editing + inpainting/continuation)
- streaming: no
- languages: English
- license: Stability AI Community License
- duration: up to 380s (Medium / Large), 120s (Small)
- sample_rate: 44.1 kHz stereo, 256-dim latents
- platforms: CPU (Small), CUDA / TensorRT (Medium), CoreML / MLX (Apple Silicon)
- text_to_audio: yes
- audio_to_audio: yes (editing + inpainting/continuation)
- lora_training: yes (built-in `uv sync --extra lora`; MLX LoRA training on Apple Silicon)
- api_only_variant: large (2.7B)

## Comparison

- music_gen: ✅
- input_modalities: text, audio
- streaming: ❌
- languages: English
- license: Stability AI Community License

## Innovation

Open-weight diffusion transformer paired with the SAME (Semantic-Acoustic Music Encoder) autoencoder — a stereo 44.1 kHz model with 256-dimensional latents optimized for both generative tractability and high-quality reconstruction. Variable-length generation avoids wasting inference time on unused latents, and built-in stackable LoRA personalization runs at small, medium, and large scales (plus a pure-MLX LoRA path on Apple Silicon).
