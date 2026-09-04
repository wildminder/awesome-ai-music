---
release_date: "August 31, 2026"
model_name: "VIBE"
category: "music"
summary: "Video instruction-aligned background music generation: an EMNLP 2026 Findings model that scores continuous-latent music with GRPO RL against a multimodal LLM judge and rule-based verifiable rewards."
slug: "vibe"
---

# VIBE (Video Instruction-aligned Background Music gEneration)

VIBE generates background music for a video that follows an explicit text instruction — not just "music that fits this video," but music that fits *and* does what the user asked (tempo, key, mood, instrumentation). Rather than converting audio to discrete tokens, it models music in a continuous latent space: a MiniCPM4-0.5B-based multimodal semantic LM produces planning latents, a RITE (Residual Integration Transformer Encoder) stack refines them, and a local diffusion transformer (LocDiT) denoises under conditional flow matching before a music VAE decodes to 48 kHz stereo. Video conditioning enters through a frozen CLIP ViT-B/32 encoder and semantic routing merges the video and instruction signals into a single conditioning stream. The released checkpoint is the Stage-5 RL policy (GRPO against a Qwen2.5-Omni-7B judge plus deterministic tempo/key rewards), with the LoRA already folded into the base weights. Built on VoxCPM, adapted from speech to music; accepts both video-to-music (first 10 s of the clip) and instruction-only text-to-music, and outputs short-form instrumental music.

## Links

- HuggingFace: https://huggingface.co/aryanvibhosale/vibe
- GitHub: https://github.com/aryanvibhosale/vibe
- arXiv: https://arxiv.org/abs/2608.30125
- Demo: https://vibe-text-video-to-music-generation.github.io/vibe/

## Features

- music_gen: yes
- video_to_music: yes
- text_to_music: yes
- streaming: no
- input_modalities: video (first 10s, 8 CLIP frames), text instruction
- output: 48 kHz stereo, short-form instrumental
- license: Apache-2.0
- parameters: 953.5M
- architecture: MiniCPM4-0.5B semantic LM + RITE + LocDiT flow matching + music VAE
- base_model: MiniCPM4-0.5B (Apache-2.0)
- rl_method: GRPO vs Qwen2.5-Omni-7B judge + verifiable tempo/key rewards
- continuous_latents: yes (no audio tokenizer)

## Comparison

- music_gen: ✅
- input_modalities: video, text
- streaming: ❌
- languages: -
- license: Apache-2.0

## Innovation

Instruction alignment through reinforcement learning: GRPO against a multimodal LLM judge (Qwen2.5-Omni-7B watches the video and listens to the generated music, scoring musicality, text-music alignment, and video-music alignment via constrained digit-logit decoding) combined with hard verifiable rewards — rule-based tempo/BPM and musical-key agreement measured on the generated audio, deterministic and immune to reward hacking — on top of a tokenizer-free continuous-latent stack that avoids the quality ceiling and codebook artifacts of discrete tokenization.
