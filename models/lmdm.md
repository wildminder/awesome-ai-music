---
release_date: "May 21, 2026"
model_name: "Live Music Diffusion Models (LMDM)"
category: "music"
summary: "UC San Diego / MIT / Adobe framework for efficient fine-tuning and post-training of interactive diffusion music generators — covers text-to-music, live generative-delay interaction, time-varying prompts, and stem-conditioned accompaniment."
slug: "lmdm"
---

# Live Music Diffusion Models (LMDM)

A framework for efficient fine-tuning and post-training of interactive diffusion music generators. LMDM enables text-to-music generation, live generative-delay interaction (a guitarist/saxophonist/cellist can play into the model and trigger accompaniment in real time), time-varying prompt transitions, and stem-conditioned accompaniment generation across lookahead windows (+2 s / 0 s / −2 s).

## Links

- Website: https://stephenbrade.github.io/lmdm-public/
- GitHub: https://github.com/ZacharyNovack/live-music-diffusion-models
- arXiv: https://arxiv.org/abs/2605.22717

## Features

- music_gen: yes (interactive text-to-music + live accompaniment)
- input_modalities: text, audio prompt, audio stem, MIDI / sketch conditions
- streaming: yes (live / generative-delay interaction)
- license: MIT (code / repo)
- text_to_music: yes
- audio_to_music: yes (stem-conditioned accompaniment)
- real_time: yes (1-second-delay generative-delay mode)
- time_varying_prompts: yes
- accompaniment_lookahead: +2 s / 0 s / −2 s
- architecture: Diffusion-based generator + efficient fine-tuning / post-training
- authors: Novack, Brade, Kim, Flores García, Shikarpur, Talegaonkar, Kim, Chen, McAuley, Berg-Kirkpatrick, Huang
- training_data: Jamendo + humpback-whale-call (per the supplementary demos)

## Comparison

- music_gen: ✅
- input_modalities: text
- streaming: ✅
- languages: -
- license: MIT

## Innovation

A training and post-training recipe that turns a base music-diffusion model into an interactive live instrument: efficient fine-tuning plus a generative-delay deployment with controllable accommodation across positive, zero, and negative stem lookahead — shown in production-quality demos with instrumentalists performing alongside the model in real time.
