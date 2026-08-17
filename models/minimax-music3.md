---
release_date: "August 13, 2026"
model_name: "MiniMax Music 3"
category: "music"
summary: "High-performance music generation model that creates complete songs up to five minutes long, conditioned on lyrics and a detailed music description, with expressive vocals and stable long-form coherence."
slug: "minimax-music3"
---

# MiniMax Music 3

MiniMax Music 3 is a high-performance music generation model for creating complete songs up to five minutes long. Conditioned on lyrics and a detailed music description, it generates structurally coherent songs with expressive vocals, evolving arrangements, and stable long-form audio quality. It combines an 8B Global LLM for long-range musical structure, a 0.6B Local LLM for frame-level acoustic detail, and a continuous hidden-state synthesis system based on Flow Matching and Flow-VAE, producing 32 kHz, 16-bit stereo WAV audio.

## Links

- HuggingFace: https://huggingface.co/MiniMaxAI/MiniMax-Music3
- GitHub: https://github.com/MiniMax-AI/MiniMax-Music3
- Demo: https://minimax-ai.github.io/music3-demo/
- Website: https://www.minimax.io

## Tools

- SimpleTuner/minimaxmusic-reggae-test-lora-comfyui-v1-4k | ComfyUI LoRA | https://huggingface.co/SimpleTuner/minimaxmusic-reggae-test-lora-comfyui-v1-4k
- ntc-ai/minimax-music3-concept-sliders | Concept Sliders | https://huggingface.co/ntc-ai/minimax-music3-concept-sliders
- bghira/minimaxh3-suno-reggae-rank128 | LoRA | https://huggingface.co/bghira/minimaxh3-suno-reggae-rank128
- coolpoodle/music3lab | Lab | https://huggingface.co/coolpoodle/music3lab
- dummy9996/MiniMax-Music3-w4a8-bf16-comfyui | ComfyUI Quant | https://huggingface.co/dummy9996/MiniMax-Music3-w4a8-bf16-comfyui/tree/main
- molbal/Minimax-Music3-GGUF | GGUF | https://huggingface.co/molbal/Minimax-Music3-GGUF
- realrebelai/MiniMax-Music-3_GGUFs | GGUF | https://huggingface.co/realrebelai/MiniMax-Music-3_GGUFs/tree/main

## Features

- music_gen: yes
- singing_generation: yes
- long_form: yes
- streaming: no
- input_modalities: lyrics, music description
- license: MiniMax-Music3 Community License
- base_model: Qwen3-8B
- architecture: 8B Global LLM + 0.6B Local LLM + Flow Matching/VAE
- sample_rate: 32 kHz stereo WAV
- max_duration: 5 minutes

## Comparison

- music_gen: ✅
- input_modalities: lyrics, music description
- streaming: ❌
- languages: -
- license: MiniMax-Music3 Community License

## Innovation

Hierarchical autoregressive Hybrid-LM: an 8B Global LLM (initialized from Qwen3-8B) models long-range song structure frame by frame while a 0.6B Local LLM restores fine-grained acoustic codebooks, and the two LLMs' final hidden states are fused and passed through Flow Matching (2.4B) + a Flow-VAE decoder to synthesize continuous 32 kHz stereo audio — enabling native five-minute, end-to-end coherent song generation.
