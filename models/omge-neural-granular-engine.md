---
release_date: "August 21, 2026"
model_name: "0MGE (Neural Granular Engine)"
category: "music"
summary: "Pre-trained neural granular engine that learns from a music library and generates new drone landscapes, textures, and atmospheres from a learned grain field — fully local, no cloud or API."
slug: "omge-neural-granular-engine"
---

# 0MGE (Neural Granular Engine)

0MGE is a pre-trained neural granular engine for AI music generation from your own music — scan, train, and generate entirely locally. It scans audio files into millions of micro-grains and trains a navigator to reassemble those grains into new drone landscapes, textures, and atmospheres; the shipped checkpoint was trained on 2,389 tracks (~48 hours) with a 566K-grain pool across three hierarchy tiers (micro/meso/macro). The architecture is a MultiNavigator Transformer (4 heads, 3 layers, 192 hidden) whose six independent stream heads select grains over band-split roles (sub, drums, harmonic, texture, presence, air), steered by a z0-inspired attractor field for long-range coherence. Output is stereo WAV at 22,050 Hz. It is explicitly not text-to-music: generation is conditioned on the learned grain field rather than prompts.

## Links

- HuggingFace: https://huggingface.co/0penAGI/0MGE
- GitHub: https://github.com/0penAGI/0MGE
- Demo: https://0penagi.github.io/0MGE/

## Features

- music_gen: yes
- text_to_music: no
- input_modalities: audio (reference music library)
- streaming: no
- license: MIT
- architecture: MultiNavigator Transformer (4 heads / 3 layers / 192 hidden) + attractor field
- grain_pool: 566K grains (micro ~55ms / meso ~300ms / macro ~3s)
- sample_rate: 22.05 kHz stereo WAV
- quantization: INT8 navigator available (weights-only)
- local_inference: yes

## Comparison

- music_gen: ✅
- input_modalities: audio
- streaming: ❌
- languages: -
- license: MIT

## Innovation

Grain-field navigation instead of token prediction: six band-specialized transformer stream heads pick from a 566K-grain hierarchical pool via softmax over pool similarities, while a learned per-stream attractor field pulls generation toward musically meaningful directions instead of a random walk — enabling long-range coherent drones/textures generated entirely offline.
