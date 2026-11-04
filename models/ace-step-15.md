---
release_date: "February 20, 2026"
model_name: "ACE-Step 1.5"
category: "music"
summary: "Open-source local music generation model from ACE-Step — outperforms most commercial alternatives on Mac, AMD, Intel, and CUDA devices."
slug: "ace-step-15"
---

# ACE-Step 1.5

The most powerful local music generation model outperforming most commercial alternatives. Supports Mac, AMD, Intel, and CUDA devices.

## Links

- GitHub: https://github.com/ace-step/ACE-Step-1.5
- HuggingFace: https://huggingface.co/ACE-Step/Ace-Step1.5
- Website: https://ace-step.github.io/ace-step-v1.5.github.io/
- arXiv: https://arxiv.org/abs/2602.00744

## Tools

- Nepali Folk | LoRA | https://huggingface.co/pradipbasnet68/nepali-folk-acestep-1.5-lora
- South India Parai | LoRA | https://huggingface.co/boobalanit/ACE-Step-1.5-SouthIndiaParaiLoRA
- WebGPU Weights | Weights | https://huggingface.co/FluidInference/ace-step-webgpu-models
- Fizgig Model EQ | LoRA | https://huggingface.co/ShootTheSound/Fizgig-ACE-Step-1.5-XL-Model-EQ
- Kannaka | LoRA | https://huggingface.co/flaukowski/kannaka-ace-step-lora
- GTSinger Alto2 Clean Pop (Base) | LoRA | https://huggingface.co/DanielMarius/dms-gtsinger-en-alto2-clean-pop-ace15-base-200e-20260806
- GTSinger Alto2 Natural 100e (Turbo) | LoRA | https://huggingface.co/DanielMarius/dms-gtsinger-en-alto2-natural-ace15-100e-20260805
- VocalSet F3 Clean Single (Base) | LoRA | https://huggingface.co/DanielMarius/dms-vocalset-f3-clean-single-singer-ace15-base-200e-20260806
- VocalSet Lyrical Female (Turbo) | LoRA | https://huggingface.co/DanielMarius/dms-vocalset-clean-lyrical-female-ace15-100e-adafactor-20260806
- VocalSet F3 Clear (Turbo) | LoRA | https://huggingface.co/DanielMarius/dms-vocalset-f3-clear-ace15-50e-20260805-r4
- GTSinger Alto2 Natural 800e (Turbo) | LoRA | https://huggingface.co/DanielMarius/dms-gtsinger-en-alto2-natural-ace15-800e-20260805

## Features

- parameters: 0.6B-4B (LM), DiT variants
- music_gen: yes
- input_modalities: text (lyrics 50+ langs), reference audio
- streaming: no
- languages: 50+
- license: MIT
- duration: 10s - 10min
- vram: <4GB
- platforms: CUDA, MPS, ROCm, XPU, CPU
- voice2bgm: yes
- track_separation: yes
- lyrics_support: yes
- text_to_music: yes
- reference_audio: yes

## Comparison

- music_gen: ✅
- input_modalities: text
- streaming: ❌
- languages: 50+
- license: MIT

## Innovation

Local-first music generation with broad hardware support (CUDA, MPS, ROCm, XPU, CPU) and a flexible DiT-based LM variant that adapts scale to available compute.
