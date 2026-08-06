---
release_date: "July 30, 2026"
model_name: "VocalRender"
category: "music"
summary: "Score-native singing voice synthesis (SVS) model — transforms composer-oriented symbolic scores (lyrics, MIDI pitches, note values, tempo) into 48 kHz singing audio without phoneme-level durations or time-aligned acoustic guidance."
slug: "vocalrender"
---

# VocalRender

A score-native singing voice synthesis model that directly transforms composer-oriented symbolic scores — lyrics, MIDI pitches, note values, and tempo — into expressive 48 kHz singing audio. Combines an interleaved lyric–note representation (preserving note-to-word alignment and melisma), continuous acoustic latents via AudioVAE, and autoregressive diffusion for global prosody modeling. Does not require phoneme-level durations, an explicit duration predictor, or a time-aligned acoustic reference. Fine-tuned from VoxCPM2 on the open-source CrawlSinger-OS dataset.

## Links

- HuggingFace: https://huggingface.co/pymaster/VocalRender
- GitHub: https://github.com/pymaster17/VocalRender
- Website: https://pymaster17.github.io/VocalRender/
- arXiv: https://arxiv.org/abs/2607.27768
- HuggingFace: https://huggingface.co/datasets/pymaster/CrawlSinger-OS

## Features

- music_gen: yes
- input_modalities: text (lyrics + MIDI pitches + note values + tempo)
- streaming: no
- languages: Chinese
- license: apache-2.0
- duration: score-dependent (variable length)
- sample_rate: 48 kHz
- base_model: openbmb/VoxCPM2
- architecture: interleaved lyric–note representation + AudioVAE + autoregressive diffusion
- pipeline_tag: text-to-speech
- singing_voice_synthesis: yes
- score_native: yes (no phoneme-level durations needed)
- melisma_support: yes
- training_dataset: pymaster/CrawlSinger-OS (open-source)
- variants: VocalRender (base), VocalRender-Pro

## Comparison

- music_gen: ✅
- input_modalities: text
- streaming: ❌
- languages: Chinese
- license: apache-2.0

## Innovation

Score-native singing voice synthesis: an interleaved representation serializes BPM followed by each lyric syllable and its associated (pitch, note-value) pairs, retaining lyric-to-note alignment and supporting melisma — eliminating the need for phoneme-level durations or time-aligned acoustic references. AudioVAE compresses singing into continuous acoustic latents that preserve fine pitch, timbre, and articulation, while an autoregressive diffusion model handles global prosody modeling and local reconstruction.
