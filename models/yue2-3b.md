---
release_date: "September 9, 2026"
model_name: "YuE2"
category: "music"
summary: "Frontier open-weights song generation from m-a-p: lyrics and a style prompt become complete 48 kHz stereo songs through an editable ABC-notation score, with cover-song and agent-driven editing workflows."
slug: "yue2-3b"
---

# YuE2 (3B)

YuE2 is the second-generation open music generation model from the m-a-p (Multimodal Art Projection) team, producing complete 48 kHz stereo songs — vocals plus accompaniment — from a style prompt and lyrics, with benchmark scores rivaling Suno v5 on WildSongBench (6.73 SongBench average, 6.96 best-of-8, vs Suno v5's 6.87). Its distinguishing feature is an editable symbolic score: an AR–NAR Mixture-of-Transformers backbone first writes an ABC-notation plan (melody-only or melody plus chords), then generates semantic tokens and acoustic latents through flow matching, which a VAE decodes to stereo audio. Users can edit the score by hand, supply their own ABC, or let an LLM agent iteratively reharmonize, restyle, and rewrite lyrics across multiple revision rounds; a zero-shot cover workflow conditions generation on a transcribed melody (via the companion SheetSage2 model) while preserving song identity. Runs locally on a single 24GB GPU — a 3.6-minute song in ~71 seconds on an RTX 4090 — and ships with companion models (YuE2-Vae, MERT-v2 encoders, SheetSage2 transcription) plus the WildSongBench benchmark. Model weights are non-commercial (CC BY-NC 4.0); the YuE2 technical report is forthcoming and the original YuE paper is cited in the meantime.

## Links

- HuggingFace: https://huggingface.co/m-a-p/YuE2-3B
- GitHub: https://github.com/multimodal-art-projection/YuE
- arXiv: https://arxiv.org/abs/2503.08638
- Demo: https://map-yue2.github.io/
- HFSpaces: https://huggingface.co/spaces/mrfakename/yue2-3b

## Tools

- piscesbody/ComfyUI-YuE2 | ComfyUI Nodes | https://github.com/piscesbody/ComfyUI-YuE2
- T8mars/Comfyui-YuE2-T8 | ComfyUI Nodes + WebUI | https://github.com/T8mars/Comfyui-YuE2-T8
- filliptm/ComfyUI-FL-YuE2 | ComfyUI Nodes + Piano Roll | https://github.com/filliptm/ComfyUI-FL-YuE2
- Starnodes2024/ComfyUI-YuE2-Trainer | ComfyUI LoRA Trainer | https://github.com/Starnodes2024/ComfyUI-YuE2-Trainer
- Comfy-Org/YuE2 | ComfyUI Weights Pack | https://huggingface.co/Comfy-Org/YuE2
- audio-cpp/Yue2-3B-GGUF | GGUF (audio.cpp) | https://huggingface.co/audio-cpp/Yue2-3B-GGUF
- drbaph/yue2-mothersuperior-realaudio-tokenizer-comfyui | Tokenizer + NAR LoRA Assets | https://huggingface.co/drbaph/yue2-mothersuperior-realaudio-tokenizer-comfyui
- dynamohum/yue2gen | Web UI + Stems (Docker) | https://github.com/dynamohum/yue2gen
- monsterovich/yue2-industrial-rock-lora | AR+NAR LoRA Pair | https://huggingface.co/monsterovich/yue2-industrial-rock-lora
- guey-khala-mari/yue2_lora_sandbox | LoRA Sandbox | https://huggingface.co/guey-khala-mari/yue2_lora_sandbox
- ntc-ai/yue2-concept-sliders | Concept Sliders | https://huggingface.co/ntc-ai/yue2-concept-sliders
- Mothersuperior/YuE2-hum-to-song | Hum-to-Song Adapter | https://huggingface.co/Mothersuperior/YuE2-hum-to-song
- Mothersuperior/YuE2-instrumental-cot-full-loras | AR Planner LoRA (instrumental) | https://huggingface.co/Mothersuperior/YuE2-instrumental-cot-full-loras
- TheMindExpansionNetwork/earthdrone_yue2_v1 | LoKr LoRA (earthdrone) | https://huggingface.co/TheMindExpansionNetwork/earthdrone_yue2_v1
- Mothersuperior/YuE2-Vae-merge-0.666 | Merged VAE Decoder | https://huggingface.co/Mothersuperior/YuE2-Vae-merge-0.666
- m-a-p/YuE2-Vae-legacy | Official Legacy VAE | https://huggingface.co/m-a-p/YuE2-Vae-legacy
- m-a-p/YuE2-Vae | Official VAE | https://huggingface.co/m-a-p/YuE2-Vae

## Features

- music_gen: yes
- singing_generation: yes
- lyrics_support: yes
- long_form: yes
- streaming: no
- input_modalities: lyrics, style prompt, ABC score (optional)
- license: CC BY-NC 4.0
- parameters: 3.6B
- architecture: AR–NAR Mixture-of-Transformers + flow matching + VAE
- sample_rate: 48 kHz stereo
- vram: 24GB GPU (~11 GiB peak, BF16)
- speed: 3.6-min song in ~71s on RTX 4090
- editable_score: yes (ABC notation, cot=full/melody/off)
- agentic_editing: yes
- cover_songs: yes (via SheetSage2 transcription)
- languages: English, Mandarin

## Comparison

- music_gen: ✅
- input_modalities: lyrics, style prompt
- streaming: ❌
- languages: 2
- license: CC BY-NC 4.0

## Innovation

Symbolic planning as a first-class interface: the model writes an editable ABC-notation score (melody plus optional chords) before synthesis, so melody and harmony can be shaped directly, an LLM agent can translate musical feedback into iterative score/lyric revisions, and transcribed melodies (SheetSage2) drive zero-shot covers — cutting lyric phoneme error from YuE 1's 36% to 8.4% while running on a single 24GB GPU.
