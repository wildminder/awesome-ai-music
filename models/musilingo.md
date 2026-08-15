---
release_date: "September 15, 2023"
model_name: "MusiLingo"
category: "audio_understanding"
summary: "NAACL 2024 MERT + Vicuna music-language model for music captioning and query response — pretrained on LP-MusicCaps-MSD, instruction-tuned on MusicInstruct and MusicQA."
slug: "musilingo"
---

# MusiLingo

MusiLingo (NAACL 2024): "Bridging Music and Text with Pre-trained Language Models for Music Captioning and Query Response". Two-stage model — pretrained on a long-form music captioning dataset (LP-MusicCaps-MSD) and instruction-tuned on MusicInstruct for short/long music QA and on MusicQA. Built on MERT-v1-330M (music encoder) + Vicuna 7B v0 (text backbone).

## Links

- HuggingFace: https://huggingface.co/collections/m-a-p/musilingo
- GitHub: https://github.com/zihaod/MusiLingo
- arXiv: https://arxiv.org/abs/2309.08730

## Features

- parameters: 7B (Vicuna 7B v0) + 330M MERT-v1 (music encoder)
- use_case: music captioning, music QA (short + long + MusicQA)
- input: audio + text
- audio_length: short to long (variable; model trained to handle both)
- base_model: MERT-v1-330M + Vicuna 7B v0
- music_gen: no
- audio_generation: no
- music_understanding: yes
- captioning: yes
- question_answering: yes (short + long)
- architecture: encoder (MERT) + instruction-tuned LLM (Vicuna)
- training_data: LP-MusicCaps-MSD (pretrain), MusicCaps, MusicInstruct, MusicQA (instruction-finetune)
- publication: NAACL 2024
- license: Unknown (HF card collection page does not surface a license; repo has no license file)

## Comparison

- use_case: captioning + AQA
- input: audio + text
- audio_length: short to long
- base_model: Vicuna 7B + MERT
- license: Unknown

## Innovation

Two-stage music-language training recipe that pairs MERT-v1 with Vicuna 7B — first pretrains on a long-caption corpus (LP-MusicCaps-MSD), then instruction-tunes on MusicInstruct for short/long music QA, releasing the data and weights as a standard MERT-based music-understanding baseline at NAACL 2024.
