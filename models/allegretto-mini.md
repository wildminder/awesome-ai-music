---
release_date: "July 27, 2026"
model_name: "Allegretto Mini"
category: "music"
summary: "Lightweight local-first text-to-music model (~640 MB int4 ONNX) — T5Gemma encoder + 20-layer DiT + SAME-S decoder, runs on CPU without PyTorch."
slug: "allegretto-mini"
---

# Allegretto Mini

A lightweight, local-first AI music generation model by OSAMA INC (India). Synthesizes stereo audio at 44.1 kHz directly from text prompts using ONNX Runtime — no cloud API, no server-side GPU, no PyTorch dependency required. Built on a three-stage pipeline (T5Gemma text encoder → 20-layer DiT with 8-step rectified-flow sampling → SAME-S decoder) derived from the Stable Audio 3 Small architecture, independently int4-quantized and packaged for efficient local deployment. Total download size ~640 MB.

## Links

- HuggingFace: https://huggingface.co/Dev4285/Allegretto-Mini
- GitHub: https://github.com/aryanisproinroblox-source/Allegretto-Mini
- Demo: https://huggingface.co/spaces/Dev4285/Allegretto-Mini-Demo

## Features

- parameters: ~640 MB (int4 quantized ONNX)
- music_gen: yes
- input_modalities: text
- streaming: no
- languages: English
- license: Stability AI Community License
- duration: up to 10s (default), 8 diffusion steps
- sample_rate: 44.1 kHz stereo
- platforms: CPU (ONNX Runtime), GPU (ONNX Runtime EP)
- library: onnxruntime (no PyTorch needed)
- architecture: T5Gemma encoder (768-dim, 256 tokens) + 20-layer DiT + SAME-S decoder
- quantization: int4 MatMulNBits (block_size=16), GatherBlockQuantized for embeddings
- text_to_music: yes
- local_first: yes

## Comparison

- music_gen: ✅
- input_modalities: text
- streaming: ❌
- languages: English
- license: Stability AI Community License

## Innovation

A production-grade text-to-music model compressed to ~640 MB of int4 ONNX weights that runs entirely on-device via ONNX Runtime — no Python or PyTorch required. The three-stage pipeline (T5Gemma → DiT → SAME-S) is derived from the Stable Audio 3 Small architecture but independently quantized and repackaged for CPU-first local inference, making it one of the smallest and most portable open-weight music generation models available.
