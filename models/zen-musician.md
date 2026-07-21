---
release_date: "November 13, 2025"
model_name: "Zen Musician"
category: "music"
summary: "Stage-1 lyrics-to-music model repackaged from M-A-P's YuE-s1-7B-anneal-en-cot — LLaMA-based 7B transformer conditioned on lyrics and prompts via the standard transformers library."
slug: "zen-musician"
---

# Zen Musician

A 7B-param LLaMA-based lyrics-to-song model repackaged by Zen (Hanzo AI / Zoo Labs Foundation) from M-A-P's YuE stage-1 model. It generates the lyric+prompt-conditioned token stream that the YuE pipeline feeds into a stage-2 audio decoder. Designed for in-process use via HuggingFace Transformers (`transformers.AutoModelForCausalLM`) rather than a diffusion/Gradio UI, so it drops cleanly into scripts and notebooks. Full song generation also requires the YuE stage-2 model ([m-a-p/YuE-s2-1B-general](https://huggingface.co/m-a-p/YuE-s2-1B-general)).

## Links

- HuggingFace: https://huggingface.co/zenlm/zen-musician
- HuggingFace: https://huggingface.co/m-a-p/YuE-s1-7B-anneal-en-cot
- HuggingFace: https://huggingface.co/m-a-p/YuE-s2-1B-general
- GitHub: https://github.com/multimodal-art-projection/YuE
- Website: https://hanzo.ai

## Features

- parameters: 6.2B BF16 (7B-class LLaMA)
- music_gen: yes
- input_modalities: text (lyrics + style prompt)
- streaming: no
- languages: English
- license: apache-2.0
- architecture: LlamaForCausalLM
- base_model: m-a-p/YuE-s1-7B-anneal-en-cot
- library: transformers (AutoModelForCausalLM + AutoTokenizer)
- pipeline_tag: text-to-audio
- stage: 1 of 2 (lyrics → latent tokens; full song requires YuE stage-2 decoder)
- text_to_music: yes
- lyrics_support: yes

## Comparison

- music_gen: ✅
- input_modalities: text
- streaming: ❌
- languages: English
- license: apache-2.0

## Innovation

A consumer-friendly, Transformers-native repackage of the open YuE lyrics-to-song pipeline: the stage-1 model that translates lyrics and a style prompt into the token stream consumed by YuE's stage-2 audio decoder. Released under Apache 2.0 with full attribution to the original M-A-P YuE authors, designed to drop into any `transformers.AutoModelForCausalLM` workflow.
