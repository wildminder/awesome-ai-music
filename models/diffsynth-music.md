---
release_date: "September 14, 2026"
model_name: "DiffSynth-Music"
category: "music"
summary: "Controllable music generation suite from DiffSynth-Studio — three composable audio-conditioning adapters (Control, Prosody, Reference) bolted onto the ACE-Step-1.5 backbone for beats, vocals, accompaniment, prosody, and reference-style control."
slug: "diffsynth-music"
---

# DiffSynth-Music

DiffSynth-Music is a suite of controllable music generation models from the DiffSynth-Studio team, built on the ACE-Step-1.5 backbone and trained with the DiffSynth-Studio framework, with controllable generation driven by Diffusion-Templates. It adds composable audio conditioning to a music synthesis backbone through layer-wise key-value (KV-cache) injection: three template models — Control, Prosody, and Reference — are initialized from the backbone diffusion transformer and trained with conditional flow matching, and because a shared variational autoencoder maps every conditioning waveform into one common latent space, their attention memories can be combined. Five control types are supported: beats (a generated click track at a fixed BPM plus the base model's `bpm` parameter tightly aligns the output's timing), vocals (keeps the input vocal track consistent while the model writes the accompaniment), accompaniment (keeps the instruments while the model writes the vocals), prosody (matches the timing and vocal style of every syllable to an extracted prosody signal), and reference (experimental — generates new music from the style, melody, singing style, and timbre of the loudest segment of an input clip). Fixing the template timestep at the clean-data endpoint means each control cache is computed once and reused throughout sampling. Training pairs are mined from real recordings via beat extraction, source separation (Demucs), vocal resynthesis, and reference-excerpt selection. Single-control evaluation on Mandarin and English songs shows improved adherence across all five control types and better lyric fidelity under vocal conditioning relative to the backbone, with automatic music-quality and instruction-following scores broadly comparable to the base models. Apache-2.0, and the inference stack supports disk/CPU offload for low-VRAM GPUs.

## Links

- HuggingFace: https://huggingface.co/DiffSynth-Studio/DiffSynth-Music
- GitHub: https://github.com/modelscope/DiffSynth-Studio
- arXiv: https://arxiv.org/abs/2609.12774

## Features

- parameters: not stated (ACE-Step-1.5 XL diffusion transformer backbone)
- music_gen: yes
- input_modalities: text (prompt + lyrics), audio (beats, vocals, accompaniment, prosody, reference)
- streaming: no
- languages: zh/en (evaluated); backbone ACE-Step-1.5 supports 50+
- license: Apache-2.0
- control_modes: beats, vocals, accompaniment, prosody, reference (experimental)
- template_models: Control, Prosody, Reference (initialized from the backbone DiT)
- architecture: layer-wise KV-cache audio adapters + conditional flow matching
- shared_vae: conditioning waveforms mapped into one common latent space so attention memories compose
- track_separation: yes (Demucs, for vocals/accompaniment control)
- sample_rate: 48 kHz
- duration: up to 240 s in the released examples
- vram: disk/CPU offload supported for low-VRAM GPUs
- framework: DiffSynth-Studio + Diffusion-Templates
- inference: `pip install -e .[audio]`, `DiffSynthMusicPipeline` + `TemplatePipeline`

## Comparison

- music_gen: ✅
- input_modalities: text, audio
- streaming: ❌
- languages: zh/en
- license: Apache-2.0

## Innovation

Control as a composable KV-cache adapter rather than a retrained model: three small template models are trained on top of an unmodified music synthesis backbone, share one variational autoencoder so their conditioning latents can be mixed, and reuse a single precomputed cache per control during sampling — turning beats, vocals, accompaniment, prosody, and reference audio into stackable knobs on an existing text-to-music model.
