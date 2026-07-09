# Awesome Music Generation Models

A curated list of open-source music generation models for audio and song synthesis. Models are sorted by release date (newest first).

---

## Table of Contents

- [Music Generation Models](#music-generation-models)
- [Additional Resources](#additional-resources)

---

## Music Generation Models

### Quick Comparison

| Model | Music Gen | Input Modalities | Streaming | Languages | License |
| :--- | :---: | :---: | :---: | :--- | :--- |
| [Magenta RealTime 2](#magenta-realtime-2) | ✅ | text | ✅ | English | ![Apache 2.0][license-apache-2.0]<br>![CC BY 4.0][license-cc-by-4.0] |
| [Live Music Diffusion Models (LMDM)](#lmdm) | ✅ | text | ✅ | - | ![MIT][license-mit] |
| [TinyMozart v2 85M](#tiny-mozart-v2-85m) | ✅ | unconditional | ❌ | - | ![Unknown][license-unknown] |
| [ACE-Step 1.5](#ace-step-15) | ✅ | text | ❌ | 50+ | ![MIT][license-mit] |
| [Uni-MoE (Audio)](#uni-moe-audio) | ✅ | text | ❌ | - | ![Apache 2.0][license-apache-2.0] |
| [Magenta Realtime](#magenta-realtime) | ✅ | text | ✅ | - | ![Apache 2.0][license-apache-2.0]<br>![CC BY 4.0][license-cc-by-4.0] |
| [Foundation-1](#foundation-1) | ✅ | text | ❌ | - | ![Stability AI][license-stability-ai] |
| [LeVo 2 (SongGeneration 2)](#levo-2) | ✅ | text | ❌ | Zh/En | ![Apache 2.0][license-apache-2.0] |
| [Music Flamingo](#music-flamingo) | ❌ | audio | ❌ | - | ![Apache 2.0][license-apache-2.0] |
| [SoulX-Singer](#soulx-singer-music) | ✅ | text | ❌ | Zh/En/Yue | ![Apache 2.0][license-apache-2.0] |

<!-- MODEL:magenta-realtime-2.md -->
<details id="magenta-realtime-2">
<summary>Magenta RealTime 2</summary>

### Magenta RealTime 2

**Description:** Open music generation model from Google DeepMind built for on-device streaming generation with low-latency control. Follow-up to Magenta RealTime, offering richer control and lower latency across text prompts, audio examples, and MIDI.

**Release Date:** May 28, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 2.4B (base), 230M (small) |
| **Music Gen** | ✅ |
| **Input Modalities** | text, audio, MIDI |
| **Streaming** | ✅ |
| **Languages** | English (text prompts) |
| **License** | ![Apache 2.0][license-apache-2.0]<br>![CC BY 4.0][license-cc-by-4.0] |
| **Real Time** | ✅ |
| **Text To Music** | ✅ |
| **Audio To Music** | ✅ |
| **Midi Conditioning** | yes |
| **Continuous Generation** | ✅ |
| **Codec** | SpectroStream (stereo 48 kHz discrete tokens) |
| **Embedding** | MusicCoCa (contrastive audio-text) |
| **Architecture** | Decoder-only Transformer LLM with frame-wise autoregression (vs. chunk-wise in RealTime v1) |
| **Vram** | on-device (small config) |

**Features:** Decoder-only Transformer LLM that does frame-wise (not chunk-wise) autoregression over SpectroStream audio tokens, conditioned on MusicCoCa embeddings + MIDI tokens — bringing Gram-style frame-level latency to live music generation with both a `base` (2.4B) and `small` (230M) configuration sized for on-device deployment.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/google/magenta-realtime-2)
[![GitHub][link-github]](https://github.com/magenta/magenta-realtime)
[![Blog][link-blog]](https://magenta.withgoogle.com/magenta-realtime-2)
[![Demo][link-demo]](https://magenta.withgoogle.com/mrt2)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2508.04651)

</details>
<!-- /MODEL:magenta-realtime-2.md -->
<!-- MODEL:lmdm.md -->
<details id="lmdm">
<summary>Live Music Diffusion Models (LMDM)</summary>

### Live Music Diffusion Models (LMDM)

**Description:** A framework for efficient fine-tuning and post-training of interactive diffusion music generators. LMDM enables text-to-music generation, live generative-delay interaction (a guitarist/saxophonist/cellist can play into the model and trigger accompaniment in real time), time-varying prompt transitions, and stem-conditioned accompaniment generation across lookahead windows (+2 s / 0 s / −2 s).

**Release Date:** May 21, 2026

| Feature | Value |
|---------|-------|
| **Music Gen** | ✅ |
| **Input Modalities** | text, audio prompt, audio stem, MIDI / sketch conditions |
| **Streaming** | ✅ |
| **License** | ![Unknown][license-unknown] |
| **Text To Music** | ✅ |
| **Audio To Music** | ✅ |
| **Real Time** | ✅ |
| **Time Varying Prompts** | yes |
| **Accompaniment Lookahead** | +2 s / 0 s / −2 s |
| **Architecture** | Diffusion-based generator + efficient fine-tuning / post-training |
| **Authors** | Novack, Brade, Kim, Flores García, Shikarpur, Talegaonkar, Kim, Chen, McAuley, Berg-Kirkpatrick, Huang |
| **Training Data** | Jamendo + humpback-whale-call (per the supplementary demos) |

**Features:** A training and post-training recipe that turns a base music-diffusion model into an interactive live instrument: efficient fine-tuning plus a generative-delay deployment with controllable accommodation across positive, zero, and negative stem lookahead — shown in production-quality demos with instrumentalists performing alongside the model in real time.

**Links:**
[![Website][link-website]](https://stephenbrade.github.io/lmdm-public/)
[![GitHub][link-github]](https://github.com/ZacharyNovack/live-music-diffusion-models)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2605.22717)

</details>
<!-- /MODEL:lmdm.md -->
<!-- MODEL:tiny-mozart-v2-85m.md -->
<details id="tiny-mozart-v2-85m">
<summary>TinyMozart v2 85M</summary>

### TinyMozart v2 85M

**Description:** Unconditional MIDI classic piano music generator trained on the Google MAESTRO V3 MIDI dataset. Tiny (85M) and CPU-friendly, designed to make local unconditional piano generation accessible.

**Release Date:** May 3, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 85M |
| **Music Gen** | ✅ |
| **Input Modalities** | unconditional (no prompt) |
| **Streaming** | ❌ |
| **License** | ![Unknown][license-unknown] |
| **Text To Music** | ❌ |
| **Midi Output** | yes |
| **Architecture** | not specified (small autoregressive model) |
| **Training Data** | Google MAESTRO V3 MIDI dataset |
| **Vram** | CPU-runnable (designed for low-resource local use) |

**Features:** 85M-parameter conditional-free MIDI piano generator trained on MAESTRO V3 — designed to be the smallest viable entry point for unconditional symbolic music generation on commodity hardware, paired with a `use.py` inference script that runs on CPU.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/LH-Tech-AI/TinyMozart_v2_85M)

</details>
<!-- /MODEL:tiny-mozart-v2-85m.md -->
<!-- MODEL:ace-step-15.md -->
<details id="ace-step-15">
<summary>ACE-Step 1.5</summary>

### ACE-Step 1.5

**Description:** The most powerful local music generation model outperforming most commercial alternatives. Supports Mac, AMD, Intel, and CUDA devices.

**Release Date:** February 20, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 0.6B-4B (LM), DiT variants |
| **Music Gen** | ✅ |
| **Input Modalities** | text (lyrics 50+ langs), reference audio |
| **Streaming** | ❌ |
| **Languages** | 50+ |
| **License** | ![MIT][license-mit] |
| **Duration** | 10s - 10min |
| **Vram** | <4GB |
| **Platforms** | CUDA, MPS, ROCm, XPU, CPU |
| **Voice2Bgm** | ✅ |
| **Track Separation** | ✅ |
| **Lyrics Support** | ✅ |
| **Text To Music** | ✅ |
| **Reference Audio** | ✅ |

**Features:** Local-first music generation with broad hardware support (CUDA, MPS, ROCm, XPU, CPU) and a flexible DiT-based LM variant that adapts scale to available compute.

**Links:**
[![GitHub][link-github]](https://github.com/ace-step/ACE-Step-1.5)
[![HuggingFace][link-huggingface]](https://huggingface.co/ACE-Step/Ace-Step1.5)
[![Website][link-website]](https://ace-step.github.io/ace-step-v1.5.github.io/)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2602.00744)

</details>
<!-- /MODEL:ace-step-15.md -->
<!-- MODEL:uni-moe-audio.md -->
<details id="uni-moe-audio">
<summary>Uni-MoE (Audio)</summary>

### Uni-MoE (Audio)

**Description:** MoE-based omnimodal model with voice cloning, TTS, T2M (text-to-music), and V2M (video-to-music).

**Release Date:** October 16, 2025

| Feature | Value |
|---------|-------|
| **Music Gen** | ✅ |
| **Voice Cloning** | ✅ |
| **Input Modalities** | text, video |
| **Streaming** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Tts** | ✅ |
| **Text To Music** | ✅ |
| **Video To Music** | ✅ |
| **Dynamic Routing** | ✅ |

**Features:** Mixture-of-experts omnimodal architecture with dynamic routing across voice cloning, TTS, text-to-music, and video-to-music — a single model that dispatches on input modality.

**Links:**
[![GitHub][link-github]](https://github.com/HITsz-TMG/Uni-MoE)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2510.13344)

</details>
<!-- /MODEL:uni-moe-audio.md -->
<!-- MODEL:magenta-realtime.md -->
<details id="magenta-realtime">
<summary>Magenta Realtime</summary>

### Magenta Realtime

**Description:** Open music generation model from Google DeepMind enabling continuous generation of musical audio steered by text prompts or audio examples.

**Release Date:** August 2025

| Feature | Value |
|---------|-------|
| **Music Gen** | ✅ |
| **Input Modalities** | text, reference audio |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Text To Music** | ✅ |
| **Audio To Music** | ✅ |
| **Reference Audio** | ✅ |
| **Continuous Generation** | ✅ |
| **Real Time** | ✅ |
| **Context** | 10 seconds |
| **Training Data** | ~190k hours |

**Features:** Continuous streaming music generation with style-prompt latency around 2 seconds — built on the Magenta line from Google DeepMind and trained on roughly 190k hours of audio.

**Links:**
[![GitHub][link-github]](https://github.com/magenta/magenta-realtime)
[![HuggingFace][link-huggingface]](https://huggingface.co/google/magenta-realtime)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2508.04651)

</details>
<!-- /MODEL:magenta-realtime.md -->
<!-- MODEL:foundation-1.md -->
<details id="foundation-1">
<summary>Foundation-1</summary>

### Foundation-1

**Description:** Structured text-to-sample generation model for music production workflows. Generates tempo-synced, key-aware, bar-aware sample generation with support for instrument identity, timbre control, and FX processing.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Type** | Text-to-Sample (Music) |
| **Base Model** | stabilityai/stable-audio-open-1.0 |
| **Music Gen** | ✅ |
| **Input Modalities** | text |
| **Streaming** | ❌ |
| **License** | ![Stability AI][license-stability-ai] |
| **Instrument Control** | ✅ |
| **Timbre Descriptors** | ✅ |
| **Fx Tags** | ✅ |
| **Musical Notation** | ✅ |
| **Text To Music** | ✅ |
| **Vram** | ~8GB |

**Features:** Production-grade structured sample generation with tempo/key/bar awareness plus fine-grained instrument-identity, timbre, and FX descriptors — built on top of Stable Audio Open.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/RoyalCities/Foundation-1)

</details>
<!-- /MODEL:foundation-1.md -->
<!-- MODEL:levo-2.md -->
<details id="levo-2">
<summary>LeVo 2 (SongGeneration 2)</summary>

### LeVo 2 (SongGeneration 2)

**Description:** Open-source foundation model for commercial-grade music generation by Tencent AI Lab. It outperforms open-source baselines and rivals commercial systems in Overall Quality, Melody, Arrangement, Sound Quality, and Structure.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Architecture** | Hybrid LLM-Diffusion |
| **Music Gen** | ✅ |
| **Input Modalities** | text (lyrics, multilingual), audio prompt |
| **Streaming** | ❌ |
| **Languages** | Zh, En |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Lyrics Support** | ✅ |
| **Multilingual** | ✅ |
| **Text Audio Prompts** | ✅ |
| **Text To Music** | ✅ |
| **Vram** | 12GB-22GB |

**Features:** Hybrid LLM-Diffusion approach that combines autoregressive language modeling with diffusion-based audio synthesis, enabling commercial-grade full-song generation with both Chinese and English lyrics.

**Links:**
[![GitHub][link-github]](https://github.com/tencent-ailab/songgeneration)
[![HuggingFace][link-huggingface]](https://huggingface.co/tencent/SongGeneration)
[![Demo][link-demo]](https://huggingface.co/spaces/tencent/SongGeneration)

</details>
<!-- /MODEL:levo-2.md -->
<!-- MODEL:music-flamingo.md -->
<details id="music-flamingo">
<summary>Music Flamingo</summary>

### Music Flamingo

**Description:** Large audio-language model designed to advance music (including song) understanding. Achieves SOTA on 10+ music benchmarks.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Music Gen** | ❌ |
| **Music Understanding** | ✅ |
| **Input Modalities** | audio |
| **Streaming** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Rich Captions** | ✅ |
| **Music Qa** | ✅ |
| **Reasoning** | ✅ |
| **Long Form** | ✅ |

**Features:** Flamingo-style few-shot audio-language architecture adapted for music — chain-of-thought reasoning over rich captions, long-form audio QA, and SOTA on 10+ music-understanding benchmarks.

**Links:**
[![Website][link-website]](https://musicflamingo.github.io/)
[![HuggingFace][link-huggingface]](https://huggingface.co/google/music-flamingo)

</details>
<!-- /MODEL:music-flamingo.md -->
<!-- MODEL:soulx-singer-music.md -->
<details id="soulx-singer-music">
<summary>SoulX-Singer</summary>

### SoulX-Singer

**Description:** Mandarin / English / Cantonese singing voice synthesis model with explicit melody control via F0 and MIDI conditioning.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Music Gen** | ✅ |
| **Singing Generation** | ✅ |
| **Input Modalities** | text (lyrics), melody (F0/MIDI) |
| **Streaming** | ❌ |
| **Languages** | Mandarin, English, Cantonese |
| **Voice Cloning** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Melody Control** | ✅ |

**Features:** Multilingual singing voice synthesis (Mandarin / English / Cantonese) with explicit F0 and MIDI melody conditioning, paired with zero-shot voice cloning for singer identity.


</details>
<!-- /MODEL:soulx-singer-music.md -->

---

## Additional Resources

Community-maintained leaderboards for tracking and comparing music generation models.

- [Artificial Analysis — Music Leaderboard](https://artificialanalysis.ai/music/leaderboard) — Elo-based arena for music generation systems, ranking models on prompt fidelity, audio quality, and genre coverage.

---

## Contributing

This list is continuously evolving. If you have any models to add or updates to suggest, please feel free to contribute! See [CONTRIBUTING.md](./CONTRIBUTING.md) for the template-driven workflow.

*Last Updated: July 2026*

<!-- MARKDOWN LINKS & IMAGES -->
[license-apache-2.0]: https://img.shields.io/badge/Apache_2.0-green?style=flat-square&logo=apache "Apache 2.0"
[license-cc-by-4.0]: https://img.shields.io/badge/CC_BY_4.0-green?style=flat-square&logo=creativecommons "CC BY 4.0"
[license-unknown]: https://img.shields.io/badge/Unknown-lightgrey?style=flat-square "Unknown"
[license-mit]: https://img.shields.io/badge/MIT-green?style=flat-square&logo=openldap "MIT"
[license-stability-ai]: https://img.shields.io/badge/Stability_AI-informational?style=flat-square&logo=stability "Stability AI"

[link-blog]: https://img.shields.io/badge/Blog-post-blue?style=flat-square "Blog post"
[link-demo]: https://img.shields.io/badge/Demo-live-blue?style=flat-square "Demo live"
[link-github]: https://img.shields.io/badge/GitHub-code-black?style=flat-square&logo=github "GitHub code"
[link-huggingface]: https://img.shields.io/badge/HuggingFace-models-yellow?style=flat-square&logo=huggingface "HuggingFace models"
[link-website]: https://img.shields.io/badge/Website-site-blue?style=flat-square "Website site"
[link-arxiv]: https://img.shields.io/badge/arXiv-paper-red?style=flat-square "arXiv paper"
