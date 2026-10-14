---
release_date: "September 29, 2026"
model_name: "WorldSonus"
category: "music"
summary: "Interactive video-to-audio framework from NoizAI that brings synchronized, controllable stereo sound to world models with a streaming causal autoregressive diffusion model generating 100 ms audio chunks at RTF 0.41."
slug: "worldsonus"
---

# WorldSonus (Video-to-Audio)

WorldSonus gives visual worlds a soundtrack. Built for world models — where interactivity, real-time pacing, and camera geometry all matter at once — it takes a video plus a text instruction and emits stereo audio in 100 ms chunks, generating each chunk as soon as its three video frames are available. The core is a streaming causal autoregressive diffusion model at RTF 0.41; visual temporal differences, an autoregressive Ring-KV history, and causal decoder convolution states persist across chunks, so output is one continuous signal rather than independently decoded clips stitched together. It is also steerable mid-stream: an audio-centric captioning pipeline with chunk-indexed prompt scheduling lets sound instructions change while a sequence is being generated. For spatial alignment it leans on stereo supervision curated from diverse stereo and ambisonic data, and it generalizes beyond its world-model target to open-domain video-to-audio benchmarks, matching or outperforming bidirectional state of the art on acoustic quality and spatial alignment. Video conditioning comes from DINOv3, text from T5Gemma 2, and a causal decoder (64 latent channels at 30 Hz) renders 48 kHz float stereo WAV.

## Links

- GitHub: https://github.com/NoizAI/WorldSonus
- HuggingFace: https://huggingface.co/FF2416/WorldSonus
- arXiv: https://arxiv.org/abs/2610.08760
- Demo: https://noizai.github.io/WorldSonus/

## Features

- audio_generation: yes
- video_to_audio: yes
- text_to_audio: yes
- streaming: yes
- input_modalities: video, text instruction
- output: 48 kHz stereo, float WAV
- architecture: streaming causal autoregressive diffusion
- video_encoder: DINOv3
- text_encoder: T5Gemma 2
- decoder: causal stereo 48 kHz, 64 latent channels at 30 Hz
- chunk_size: 100 ms, 3 video frames per chunk
- context: 5-second autoregressive Ring-KV history
- spatial: yes, stereo supervision from stereo and ambisonic data
- interactive_control: yes, chunk-indexed prompt scheduling
- real_time_factor: 0.41
- weights: worldsonus_150k_padtrim.pt, 638 inference tensors, 4.12 GB
- checkpoint: C3 no-H0, 150k EMA, HQ fine-tuned
- requirements: Python 3.10+, CUDA GPU, FFmpeg and ffprobe
- license: CC BY-NC 4.0

## Comparison

- music_gen: ❌
- input_modalities: video, text
- streaming: ✅
- languages: -
- license: CC BY-NC 4.0

## Innovation

Three problems solved together, where most video-to-audio systems only address one. Real time is achieved with a streaming causal architecture that emits 100 ms chunks at RTF 0.41 and keeps Ring-KV history and decoder convolution state alive across chunks instead of re-encoding or stitching per clip. Interactivity comes from an audio-centric captioning pipeline with chunk-indexed prompt scheduling, so a sound instruction delivered mid-generation takes effect from that chunk onward. Spatial alignment is trained directly from curated stereo and ambisonic supervision rather than inferred from mono data, which is what makes camera motion and scene geometry audible in the stereo field.
