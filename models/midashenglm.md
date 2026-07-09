---
release_date: "June 26, 2025"
model_name: "MiDashengLM-7B-0804"
category: "audio_understanding"
summary: "Xiaomi's 7B audio-language captioner that combines Dasheng audio encoder with Qwen2.5-Omni-7B and reaches SOTA-level holistic audio understanding with up to 512 batch size."
slug: "midashenglm"
---

# MiDashengLM-7B-0804

Xiaomi Research's MiDashengLM-7B-0804 — a 7B audio-language generalist captioner that pairs the Dasheng-0.6B audio encoder with Qwen2.5-Omni-7B as the language backbone, training on caption-based alignment. Reports 3.2x throughput speedup over comparable ALMs at the same accuracy and supports batch sizes up to 512.

## Links

- HuggingFace: https://huggingface.co/mispeech/midashenglm-7b-0804-fp32
- GitHub: https://github.com/xiaomi-research/dasheng-lm
- HuggingFace: https://huggingface.co/mispeech/midashenglm-7b-0804-bf16

## Features

- parameters: 7B (audio encoder 0.6B + LLM 7B)
- use_case: holistic audio captioning, audio question answering
- input: audio + text
- audio_length: short-to-medium (caption-based; full-clip captions)
- base_model: dasheng-0.6B + Qwen2.5-Omni-7B (finetune)
- music_generation: no
- audio_generation: no
- reasoning: yes (caption-based alignment)
- batching: up to 512
- inference_speedup: 3.2x over peer ALMs
- architecture: caption-aligned audio-language model
- languages: en, zh, th, id, vi
- license: Apache-2.0

## Comparison

- use_case: caption + AQA
- input: audio + text
- audio_length: short-medium
- base_model: Qwen2.5-Omni-7B
- license: Apache-2.0

## Innovation

Caption-based audio-language alignment that combines Dasheng audio encoder with Qwen2.5-Omni-7B at 7B scale — SOTA-level holistic audio understanding with up to 512 batch size and 3.2× throughput vs. comparable ALMs, making captioning pipelines much cheaper to deploy at scale.
