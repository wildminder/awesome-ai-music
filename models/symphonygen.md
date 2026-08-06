---
release_date: "August 3, 2026"
model_name: "SymphonyGen"
category: "music"
summary: "3D hierarchical orchestral music generation framework — cascading bar/track/event decoders with harmony-skeleton conditioning, GRPO reinforcement learning, and dissonance-averse sampling. Accepted at ISMIR 2026."
slug: "symphonygen"
---

# SymphonyGen

A 3D hierarchical framework for contemporary cinematic orchestration, accepted at ISMIR 2026. Decomposes symphonic scores along the Bar, Track, and Event axes with a cascading decoder architecture that keeps decoding memory far below flat token streams. Conditions generation on a beat-quantized multi-voice harmony skeleton ("short-score" conditioning) that may be user-written, analyzed, or model-generated — enabling outline control while producing full orchestral textures. Refined with GRPO (Group Relative Policy Optimization) using a cross-modal acoustic reward from CLaMP 3 audio embeddings, and suppresses tonal clashes at inference time with dissonance-averse sampling.

## Links

- HuggingFace: https://huggingface.co/SymphonyGen/SymphonyGen
- GitHub: https://github.com/symphonygen/symphonygen
- Website: https://symphonygen.github.io/
- arXiv: https://arxiv.org/abs/2604.25498

## Features

- music_gen: yes
- input_modalities: text (harmony skeleton / short-score conditioning)
- streaming: no
- languages: -
- license: mit
- architecture: 3D hierarchical cascading decoder (Bar × Track × Event)
- conditioning: beat-quantized multi-voice harmony skeleton
- reinforcement_learning: GRPO with CLaMP 3 audio reward
- dissonance_averse_sampling: yes
- output_format: symbolic (MIDI / orchestral scores)
- accepted: ISMIR 2026
- pipeline_tag: reinforcement-learning
- library: pytorch

## Comparison

- music_gen: ✅
- input_modalities: text
- streaming: ❌
- languages: -
- license: mit

## Innovation

A 3D hierarchical cascading decoder that decomposes orchestral scores along the Bar, Track, and Event axes — keeping decoding memory far below flat token streams while enabling conditioning at every structural level. A beat-quantized harmony skeleton provides "short-score" conditioning (user-written, analyzed, or model-generated), and the model is refined with GRPO against a cross-modal acoustic reward from CLaMP 3 audio embeddings, plus a dissonance-averse sampling algorithm that suppresses unintended tonal clashes during inference.
