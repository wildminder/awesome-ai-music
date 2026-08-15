---
release_date: "July 10, 2025"
model_name: "Audio Flamingo 3"
category: "audio_understanding"
summary: "NVIDIA's fully open Audio Flamingo 3 — multi-turn chat, transcription, and chain-of-thought audio reasoning over long audio with a PEFT 'AF-Think' adapter."
slug: "audio-flamingo-3"
---

# Audio Flamingo 3

NVIDIA's Audio Flamingo 3 — a fully open audio-language model that extends Audio Flamingo 2 with multi-turn chat, transcription shortcuts, and a chain-of-thought PEFT adapter (`AF-Think`) for audio reasoning. Integrated into HuggingFace Transformers.

## Links

- HuggingFace: https://huggingface.co/nvidia/audio-flamingo-3
- HuggingFace: https://huggingface.co/nvidia/audio-flamingo-3-hf
- GitHub: https://github.com/NVIDIA/audio-flamingo
- arXiv: https://arxiv.org/abs/2507.08128
- Demo: https://research.nvidia.com/labs/adlr/AF3/

## Features

- parameters: not specified (8B-class)
- use_case: multi-turn chat, transcription, audio reasoning (chain-of-thought)
- input: audio + text (text-only and audio-only modes also supported)
- audio_length: long (multi-turn, long-audio reasoning)
- base_model: Audio Flamingo 2 continuation (audio encoder + LLM backbone)
- music_gen: no
- audio_generation: no
- reasoning: yes (AF-Think PEFT adapter)
- chat: yes (multi-turn chat templating)
- transcription: yes (with strip_prefix option)
- architecture: Audio-language model with PEFT-based AF-Think reasoning adapter
- training_data: nvidia/AudioSkills, nvidia/AF-Chat, nvidia/AF-Think, nvidia/LongAudio
- license: NVIDIA OneWay Noncommercial License (checkpoints)

## Comparison

- use_case: chat + reasoning
- input: audio + text
- audio_length: long
- base_model: Audio Flamingo 2
- license: NVIDIA OneWay Noncommercial License

## Innovation

Fully open continuation of Audio Flamingo 2 — adds a unified `apply_chat_template` API for multi-turn chat, a one-call `apply_transcription_request` shortcut with strip-prefix cleanup, and a PEFT-based **AF-Think** chain-of-thought reasoning adapter over the same checkpoints.
