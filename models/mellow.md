---
release_date: "March 10, 2025"
model_name: "Mellow"
category: "audio_understanding"
summary: "167M audio-language model that uses 50× fewer parameters than SOTA yet still reaches competitive AQA performance, training on two-audio + text prompts (AudioCaps + Clotho)."
slug: "mellow"
---

# Mellow

A 167M-parameter audio-language model that takes **two audios plus a text prompt** and produces free-form text outputs. Trained on ~155 hours of audio (AudioCaps + Clotho), claims SoTA-class performance on audio-QA tasks with 50× fewer parameters than peer ALMs.

## Links

- HuggingFace: https://huggingface.co/soham97/mellow
- GitHub: https://github.com/soham97/Mellow
- arXiv: https://arxiv.org/abs/2503.08540
- Demo: https://tinyurl.com/mellowredirect
- Paper: https://zenodo.org/records/15036628

## Features

- parameters: 167M
- use_case: audio question answering, audio captioning, audio reasoning, zero-shot
- input: two audios + text
- audio_length: short clips (~10 s)
- base_model: from-scratch 167M audio-language model
- music_generation: no
- audio_generation: no
- reasoning: yes
- zero_shot: yes
- architecture: small audio-language model
- training_data: AudioCaps, Clotho (~155 hours)
- license: MIT

## Comparison

- use_case: AQA + captioning
- input: audio + text
- audio_length: short
- base_model: from-scratch 167M
- license: MIT

## Innovation

A two-audio plus text-conditioned small audio-language model (167M) that shows you can get SOTA-class AQA behaviour with **50× fewer parameters** than competitive models — and trains on a lean ~155-hour corpus of AudioCaps + Clotho.
