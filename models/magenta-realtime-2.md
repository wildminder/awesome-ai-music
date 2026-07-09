---
release_date: "May 28, 2026"
model_name: "Magenta RealTime 2"
category: "music"
summary: "Google DeepMind's on-device streaming music generation model — frame-wise autoregressive Transformer LLM over SpectroStream tokens with text, audio, and MIDI conditioning; available in `base` (2.4B) and `small` (230M) configurations."
slug: "magenta-realtime-2"
---

# Magenta RealTime 2

Open music generation model from Google DeepMind built for on-device streaming generation with low-latency control. Follow-up to Magenta RealTime, offering richer control and lower latency across text prompts, audio examples, and MIDI.

## Links

- HuggingFace: https://huggingface.co/google/magenta-realtime-2
- GitHub: https://github.com/magenta/magenta-realtime
- Blog: https://magenta.withgoogle.com/magenta-realtime-2
- Demo: https://magenta.withgoogle.com/mrt2
- arXiv: https://arxiv.org/abs/2508.04651

## Features

- parameters: 2.4B (base), 230M (small)
- music_gen: yes (live music generation)
- input_modalities: text, audio, MIDI
- streaming: yes (frame-level streaming)
- languages: English (text prompts)
- license: Apache-2.0 (code), CC-BY-4.0 (model weights)
- real_time: yes
- text_to_music: yes
- audio_to_music: yes
- midi_conditioning: yes
- continuous_generation: yes
- codec: SpectroStream (stereo 48 kHz discrete tokens)
- embedding: MusicCoCa (contrastive audio-text)
- architecture: Decoder-only Transformer LLM with frame-wise autoregression (vs. chunk-wise in RealTime v1)
- vram: on-device (small config)

## Comparison

- music_gen: ✅
- input_modalities: text
- streaming: ✅
- languages: English
- license: Apache-2.0 / CC-BY-4.0

## Innovation

Decoder-only Transformer LLM that does frame-wise (not chunk-wise) autoregression over SpectroStream audio tokens, conditioned on MusicCoCa embeddings + MIDI tokens — bringing Gram-style frame-level latency to live music generation with both a `base` (2.4B) and `small` (230M) configuration sized for on-device deployment.
