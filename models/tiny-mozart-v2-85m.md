---
release_date: "May 3, 2026"
model_name: "TinyMozart v2 85M"
category: "music"
summary: "Tiny 85M-parameter unconditional MIDI piano generator trained on Google MAESTRO V3 — CPU-runnable, open-source, audio-output."
slug: "tiny-mozart-v2-85m"
---

# TinyMozart v2 85M

Unconditional MIDI classic piano music generator trained on the Google MAESTRO V3 MIDI dataset. Tiny (85M) and CPU-friendly, designed to make local unconditional piano generation accessible.

## Links

- HuggingFace: https://huggingface.co/LH-Tech-AI/TinyMozart_v2_85M

## Features

- parameters: 85M
- music_gen: yes (unconditional MIDI piano)
- input_modalities: unconditional (no prompt)
- streaming: no
- license: Unknown (HuggingFace card does not specify — left as Unknown canonical)
- text_to_music: no (unconditional generation; MIDI output, not audio directly)
- midi_output: yes
- architecture: not specified (small autoregressive model)
- training_data: Google MAESTRO V3 MIDI dataset
- vram: CPU-runnable (designed for low-resource local use)

## Comparison

- music_gen: ✅
- input_modalities: unconditional
- streaming: ❌
- languages: -
- license: Unknown

## Innovation

85M-parameter conditional-free MIDI piano generator trained on MAESTRO V3 — designed to be the smallest viable entry point for unconditional symbolic music generation on commodity hardware, paired with a `use.py` inference script that runs on CPU.
