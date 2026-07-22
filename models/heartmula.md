---
release_date: "February 13, 2026"
model_name: "HeartMuLa"
category: "music"
summary: "Family of open-source music foundation models — 3B-param lyrics+tags conditioned music LM (multilingual: zh/en/ja/ko/es) with a companion 12.5 Hz music codec (HeartCodec)."
slug: "heartmula"
---

# HeartMuLa

A family of open-source music foundation models from HeartMuLa, comprising HeartMuLa (a 3B-param lyrics+tags music language model with multilingual support covering Chinese, English, Japanese, Korean, and Spanish), HeartCodec (a 12.5 Hz music codec for high-fidelity reconstruction), HeartTranscriptor (a Whisper-tuned ASR model for lyrics transcription), and HeartCLAP (audio-text alignment for music description and cross-modal retrieval). The current recommended pre-trained checkpoint is `HeartMuLa-oss-3B-happy-new-year` (Feb 13, 2026), tuned for lyrics controllability; an RL-refined variant `HeartMuLa-RL-oss-3B-20260123` is also published for tighter style/tag control. Reference-audio conditioning, fine-grained control, and a 7B variant are listed as TODO.

## Links

- GitHub: https://github.com/HeartMuLa/heartlib
- HuggingFace: https://huggingface.co/HeartMuLa
- HuggingFace: https://huggingface.co/HeartMuLa/HeartMuLa-oss-3B-happy-new-year
- HuggingFace: https://huggingface.co/HeartMuLa/HeartMuLa-oss-3B
- HuggingFace: https://huggingface.co/HeartMuLa/HeartMuLa-RL-oss-3B-20260123
- HuggingFace: https://huggingface.co/HeartMuLa/HeartCodec-oss-20260123
- HuggingFace: https://huggingface.co/HeartMuLa/HeartTranscriptor-oss
- Demo: https://huggingface.co/spaces/HeartMuLa/heartmula
- Website: https://heartmula.github.io/
- arXiv: https://arxiv.org/abs/2601.10547

## Features

- parameters: 3B (HeartMuLa LM) + HeartCodec decoder
- music_gen: yes
- input_modalities: text (lyrics + comma-separated style tags)
- streaming: no
- languages: Chinese, English, Japanese, Korean, Spanish
- license: apache-2.0
- duration: up to 4 min (default `max_audio_length_ms=240000`)
- architectures: language model (LM) + codec decoder
- text_to_music: yes
- lyrics_support: yes (structured prompts with `[Intro]`, `[Verse]`, `[Chorus]`, etc.)
- family_components: HeartMuLa (LM), HeartCodec (12.5 Hz), HeartTranscriptor (ASR), HeartCLAP (audio-text)
- recommended_checkpoint: HeartMuLa-oss-3B-happy-new-year
- rl_variant: HeartMuLa-RL-oss-3B-20260123 (tighter style/tag control)

## Comparison

- music_gen: ✅
- input_modalities: text
- streaming: ❌
- languages: zh/en/ja/ko/es
- license: apache-2.0

## Innovation

A single open-source stack for end-to-end music generation: a 3B multilingual lyrics+tags LM that autoregressively emits HeartCodec's 12.5 Hz tokens, paired with a high-fidelity codec decoder — released alongside the rest of the pipeline (HeartTranscriptor for lyrics ASR, HeartCLAP for audio-text alignment) and a benchmark (HeartBeats). Apache 2.0 across repo and all model weights.
