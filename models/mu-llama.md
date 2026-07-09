---
release_date: "August 22, 2023"
model_name: "MU-LLaMA"
category: "audio_understanding"
summary: "Music Understanding LLaMA — MERT + LLaMA-2 (7B) music-language model designed for music question answering and music captioning (used to build text-to-music training data)."
slug: "mu-llama"
---

# MU-LLaMA

MU-LLaMA (Music Understanding Large Language Model) — an audio-language model that answers questions about music and captions music files. Built on a MERT music encoder + LLaMA-2 (7B) text backbone with an adapter that incorporates music context. Used in the paper to generate MusicQA from MusicCaps and MagnaTagATune, providing training data for downstream text-to-music generation models.

## Links

- GitHub: https://github.com/shansongliu/MU-LLaMA
- HuggingFace: https://huggingface.co/mu-llama/MU-LLaMA
- arXiv: https://arxiv.org/abs/2308.11276
- Demo: https://crypto-code.github.io/MU-LLaMA-Demo/

## Features

- parameters: 7B (LLaMA-2 base) + ~95M MERT (music encoder)
- use_case: music QA, music captioning, music understanding
- input: audio + text
- audio_length: short clips (MusicCaps-style)
- base_model: MERT (music encoder) + LLaMA-2 7B (text backbone) via adapter
- music_generation: no
- audio_generation: no
- music_understanding: yes
- captioning: yes
- question_answering: yes
- architecture: cross-modal audio-language model (encoder + LLM + adapter)
- training_data: MusicCaps, MagnaTagATune (used to build MusicQA)
- evaluation: MTG-Jamendo
- license: MIT

## Comparison

- use_case: music QA + captioning
- input: audio + text
- audio_length: short
- base_model: LLaMA-2 + MERT
- license: MIT

## Innovation

One of the earliest MERT + LLaMA-2 music-language models for music QA/captioning — its **MusicQA** dataset (built from MusicCaps and MagnaTagATune) became a standard component of music-AQA pipelines, and the MERT backbone became the de-facto music encoder for downstream music-language work that followed (e.g. MusiLingo, LP-MusicCaps-MSD).
