---
release_date: "July 22, 2026"
model_name: "UniMuMo"
category: "music"
summary: "Motius release of the unified text-music-motion model (UniMuMo) — single-checkpoint generation across text-to-music, text-to-motion, music-to-dance, and dance-to-music routes plus T5 captioning."
slug: "unimumo"
---

# UniMuMo

A self-contained safe-artifact release of UniMuMo by Motius, repackaging the authors' published weights into a single verifiable checkpoint loaded via `motius.pipelines.unimumo.UniMuMoPipeline`. The model is a 24-layer, 1,024-dimensional dual-stream autoregressive Transformer operating over parallel music and motion token streams at a shared 50 Hz rate (Encodec 32 kHz audio with four 2,048-entry RVQ codebooks; HumanML3D-263 motion at 60 fps; T5-base text encoder and captioner). Supported routes include text-to-motion, text-to-music, joint text-to-music-motion, music-to-dance (AIST++), dance-to-music (D2M-GAN 86-clip protocol), plus captioning on both music and motion inputs. Maximum generation length per call is 10 seconds. The upstream paper is *UniMuMo: Unified Text, Music and Motion Generation* (Yang et al., arXiv 2410.04534).

## Links

- HuggingFace: https://huggingface.co/ZeyuLing/Motius-UniMuMo
- HuggingFace: https://huggingface.co/ClarenceY/unimumo
- GitHub: https://github.com/hanyangclarence/UniMuMo
- Website: https://hanyangclarence.github.io/unimumo_demo/
- arXiv: https://arxiv.org/abs/2410.04534

## Features

- music_gen: yes
- input_modalities: text, audio, motion
- streaming: no
- languages: English
- license: Unknown
- release_type: derivative repackage (Motius re-release)
- upstreams_repo: hanyangclarence/UniMuMo@a75ddac7
- pipeline: motius.pipelines.unimumo.UniMuMoPipeline
- duration: up to 10 s per call
- sample_rate: 32 kHz (Encodec audio)
- motion_representation: HumanML3D-263 at 60 fps
- music_representation: Encodec 32 kHz, four 2,048-entry RVQ codebooks
- shared_code_rate: 50 Hz
- architecture: 24-layer, 1,024-D dual-stream autoregressive Transformer
- text_encoder: T5-base (encoder + captioner)
- text_to_music: yes
- text_to_motion: yes
- joint_text_music_motion: yes
- music_to_dance: yes
- dance_to_music: yes
- music_captioning: yes
- motion_captioning: yes
- benchmarks: HumanML3D (T2M, M2T), AIST++ (M2D, D2M-GAN 86-clip)
- self_contained: yes (no upstream import needed)

## Comparison

- music_gen: ✅
- input_modalities: text, audio, motion
- streaming: ❌
- languages: English
- license: Unknown

## Innovation

UniMuMo's novelty is a **single dual-stream autoregressive Transformer** that jointly generates synchronized music and motion tokens from text, plus the reverse routes — all from one set of weights, no external captioners or codecs required at runtime. Motius' release packages every component (Encodec, T5 encoder + captioner, SentencePiece tokenizer, HumanML3D normalization stats, configuration, provenance) into one safe artifact with explicit tensor-layout mapping and a pass-or-fail loader, so `UniMuMoPipeline.from_pretrained` exposes text-to-music-motion, music-to-dance, dance-to-music, and bidirectional captioning behind one entry point. Reproduction audit reports exact code/waveform parity with the upstream runtime (`RMSE=0`, `max abs err=0`) on all anchor routes.
