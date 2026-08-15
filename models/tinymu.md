---
release_date: "April 17, 2026"
model_name: "TinyMU"
category: "audio_understanding"
summary: "229M music-language model from UC San Diego that hits 82% of SOTA LALM performance on MuChoMusic at 35× smaller scale, on the MusicSkills-3.5M dataset."
slug: "tinymu"
---

# TinyMU

TinyMU: A Compact Audio-Language Model for Music Understanding (paper: arXiv 2604.15849). A 229M-parameter music-specialised audio-language model that reaches 82% of SOTA LALM performance on the MuChoMusic benchmark while being 35× smaller than the SOTA system. Trained on the released MusicSkills-3.5M music-understanding dataset (captioning, QA, reasoning tasks across MusicCaps and other sources).

## Links

- GitHub: https://github.com/xiquan-li/TinyMU
- HuggingFace: https://huggingface.co/AndreasXi/TinyMU
- arXiv: https://arxiv.org/abs/2604.15849
- HuggingFace: https://huggingface.co/datasets/AndreasXi/MusicSkills-3.5M

## Features

- parameters: 229M
- use_case: music captioning, music QA, music reasoning
- input: audio + text
- audio_length: short music clips (~10 s)
- base_model: from-scratch 229M music-language model
- music_gen: no
- audio_generation: no
- music_understanding: yes
- reasoning: yes
- architecture: compact music-language model
- training_data: MusicSkills-3.5M (captioning, QA, reasoning tasks over MusicCaps etc.)
- benchmark: MuChoMusic
- license: Unknown (HF dataset card not present / repo license unspecified)

## Comparison

- use_case: music caption + QA
- input: audio + text
- audio_length: short
- base_model: from-scratch 229M
- license: Unknown

## Innovation

Compact music-specialised audio-language model trained on the released **MusicSkills-3.5M** dataset — listed as hitting 82% of SOTA LALM performance on MuChoMusic at 35× smaller scale, balancing captioning, QA, and reasoning skills specifically for music.
