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

- YuE2 Nodes | ComfyUI node | https://github.com/piscesbody/ComfyUI-YuE2
- YuE2 T8 | ComfyUI node | https://github.com/T8mars/Comfyui-YuE2-T8
- FL YuE2 | ComfyUI node | https://github.com/filliptm/ComfyUI-FL-YuE2
- YuE2 Trainer | Trainer | https://github.com/Starnodes2024/ComfyUI-YuE2-Trainer
- ComfyUI Weights | Weights | https://huggingface.co/Comfy-Org/YuE2
- audio.cpp GGUF | GGUF | https://huggingface.co/audio-cpp/Yue2-3B-GGUF
- Realaudio Tokenizer | Tokenizer | https://huggingface.co/drbaph/yue2-mothersuperior-realaudio-tokenizer-comfyui
- YuE2gen Studio | Web UI | https://github.com/dynamohum/YuE2gen-studio
- Industrial Rock | LoRA | https://huggingface.co/monsterovich/yue2-industrial-rock-lora
- LoRA Sandbox | LoRA | https://huggingface.co/guey-khala-mari/yue2_lora_sandbox
- Hum-to-Song | LoRA | https://huggingface.co/Mothersuperior/YuE2-hum-to-song
- Instrumental CoT | LoRA | https://huggingface.co/Mothersuperior/YuE2-instrumental-cot-full-loras
- Earthdrone | LoRA | https://huggingface.co/TheMindExpansionNetwork/earthdrone_yue2_v1
- Steps From Hell | LoRA | https://huggingface.co/monsterovich/yue2-steps-from-hell
- Death Metal V1 | LoRA | https://huggingface.co/pduncan/YuE2_Deathmetalv1_lora
- J-Pop T4 | LoRA | https://huggingface.co/storagejuju/yue2-jpop-t4-lora
- Billie (Voice) | LoRA | https://huggingface.co/HaileyStorm/sv-billie-yue2-lora
- Lorn | LoRA | https://huggingface.co/polinom100/yue2-lorn-lora
- Phonk | LoRA | https://huggingface.co/supermind/YuE2-phonk-lora
- Ethio-Music | LoRA | https://huggingface.co/Behailut/Ethio-Music-YuE2
- ArabMaqamRock v3 | LoRA | https://huggingface.co/akbargherbal/arabmaqamrock-yue2-lora
- DreamPop v2 | LoRA | https://huggingface.co/atomtanstudio/lora-library/tree/main/yue2/dreampop
- Industrial v1 | LoRA | https://huggingface.co/atomtanstudio/lora-library/tree/main/yue2/industrial
- Old School Hip-Hop | LoRA | https://huggingface.co/atomtanstudio/lora-library/tree/main/yue2/oldschoolhiphop
- Bulgarian Voices | LoRA | https://huggingface.co/becausereasons/yue2-blgr-bulgarian-voices
- Chanson Française | LoRA | https://huggingface.co/becausereasons/yue2-chnsn-chanson-francaise
- Canzone Italiana | LoRA | https://huggingface.co/becausereasons/yue2-cnzn-canzone-italiana
- Qawwali / Sufi / Tabla | LoRA | https://huggingface.co/becausereasons/yue2-qwwl-qawwali-sufi-tabla
- Militant Reggae | LoRA | https://huggingface.co/becausereasons/yue2-mltnt-militant-reggae
- Folk Troubadour | LoRA | https://huggingface.co/becausereasons/yue2-trbdr-folk-troubadour
- Quiet Storm | LoRA | https://huggingface.co/becausereasons/yue2-qtstrm-quiet-storm
- Raspy Rock-Soul | LoRA | https://huggingface.co/becausereasons/yue2-grvl-raspy-rock-soul
- Particle Sliders | Concept slider | https://huggingface.co/ntc-ai/yue2-particle-sliders
- Concept Sliders | ComfyUI node | https://github.com/mikkel/yue2-concept-sliders
- VAE Merge 0.666 | VAE | https://huggingface.co/Mothersuperior/YuE2-Vae-merge-0.666
- Legacy VAE | VAE | https://huggingface.co/m-a-p/YuE2-Vae-legacy
- YuE2 VAE | VAE | https://huggingface.co/m-a-p/YuE2-Vae

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
