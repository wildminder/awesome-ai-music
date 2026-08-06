<h1 align="center">
『 Awesome Music Generation Models 』
</h1>
<div align="center">
<p> A curated list of open-source music generation models for audio and song synthesis. Models are sorted by release date (newest first).</p>

<img alt="image" src="https://github.com/user-attachments/assets/5bf3f3d4-f3a7-4826-8a0b-632cb6c696de" />
</div>

## ░ Table of Contents

- [Music Generation Models](#music-generation-models)
- [Audio-Language Models (Audio Understanding)](#audio-language-models-audio-understanding)
- [Additional Resources](#additional-resources)

<p align="center">≋≋≋≋≋≋≋≋≋≋≋≋≋≋</p>

## ░ Music Generation Models

### Quick Comparison

| Model | Music Gen | Input Modalities | Streaming | Languages | License |
| :--- | :---: | :---: | :---: | :--- | :--- |
| [SymphonyGen](#symphonygen) | ✅ | text | ❌ | - | ![MIT][license-mit] |
| [VocalRender](#vocalrender) | ✅ | text | ❌ | Chinese | ![Apache 2.0][license-apache-2.0] |
| [Allegretto Mini](#allegretto-mini) | ✅ | text | ❌ | English | ![Stability AI][license-stability-ai] |
| [UniMuMo](#unimumo) | ✅ | text, audio, motion | ❌ | English | ![Unknown][license-unknown] |
| [Magenta RealTime 2](#magenta-realtime-2) | ✅ | text | ✅ | English | ![Apache 2.0][license-apache-2.0]<br>![CC BY 4.0][license-cc-by-4.0] |
| [Live Music Diffusion Models (LMDM)](#lmdm) | ✅ | text | ✅ | - | ![MIT][license-mit] |
| [Stable Audio 3](#stable-audio-3) | ✅ | text, audio | ❌ | English | ![Stability AI][license-stability-ai] |
| [TinyMozart v2 85M](#tiny-mozart-v2-85m) | ✅ | unconditional | ❌ | - | ![Unknown][license-unknown] |
| [ACE-Step 1.5](#ace-step-15) | ✅ | text | ❌ | 50+ | ![MIT][license-mit] |
| [HeartMuLa](#heartmula) | ✅ | text | ❌ | zh/en/ja/ko/es | ![Apache 2.0][license-apache-2.0] |
| [Zen Musician](#zen-musician) | ✅ | text | ❌ | English | ![Apache 2.0][license-apache-2.0] |
| [Uni-MoE (Audio)](#uni-moe-audio) | ✅ | text | ❌ | - | ![Apache 2.0][license-apache-2.0] |
| [Magenta Realtime](#magenta-realtime) | ✅ | text | ✅ | - | ![Apache 2.0][license-apache-2.0]<br>![CC BY 4.0][license-cc-by-4.0] |
| [Foundation-1](#foundation-1) | ✅ | text | ❌ | - | ![Stability AI][license-stability-ai] |
| [LeVo 2 (SongGeneration 2)](#levo-2) | ✅ | text | ❌ | Zh/En | ![Apache 2.0][license-apache-2.0] |
| [Music Flamingo](#music-flamingo) | ❌ | audio | ❌ | - | ![Apache 2.0][license-apache-2.0] |
| [SoulX-Singer](#soulx-singer-music) | ✅ | text | ❌ | Zh/En/Yue | ![Apache 2.0][license-apache-2.0] |

<!-- MODEL:symphonygen.md -->
<details id="symphonygen">
<summary>SymphonyGen</summary>

### SymphonyGen

**Description:** A 3D hierarchical framework for contemporary cinematic orchestration, accepted at ISMIR 2026. Decomposes symphonic scores along the Bar, Track, and Event axes with a cascading decoder architecture that keeps decoding memory far below flat token streams. Conditions generation on a beat-quantized multi-voice harmony skeleton ("short-score" conditioning) that may be user-written, analyzed, or model-generated — enabling outline control while producing full orchestral textures. Refined with GRPO (Group Relative Policy Optimization) using a cross-modal acoustic reward from CLaMP 3 audio embeddings, and suppresses tonal clashes at inference time with dissonance-averse sampling.

**Release Date:** August 3, 2026

| Feature | Value |
|---------|-------|
| **Music Gen** | ✅ |
| **Input Modalities** | text (harmony skeleton / short-score conditioning) |
| **Streaming** | ❌ |
| **Languages** | - |
| **License** | ![MIT][license-mit] |
| **Architecture** | 3D hierarchical cascading decoder (Bar × Track × Event) |
| **Conditioning** | beat-quantized multi-voice harmony skeleton |
| **Reinforcement Learning** | GRPO with CLaMP 3 audio reward |
| **Dissonance Averse Sampling** | yes |
| **Output Format** | symbolic (MIDI / orchestral scores) |
| **Accepted** | ISMIR 2026 |
| **Pipeline Tag** | reinforcement-learning |
| **Library** | pytorch |

**Features:** A 3D hierarchical cascading decoder that decomposes orchestral scores along the Bar, Track, and Event axes — keeping decoding memory far below flat token streams while enabling conditioning at every structural level. A beat-quantized harmony skeleton provides "short-score" conditioning (user-written, analyzed, or model-generated), and the model is refined with GRPO against a cross-modal acoustic reward from CLaMP 3 audio embeddings, plus a dissonance-averse sampling algorithm that suppresses unintended tonal clashes during inference.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/SymphonyGen/SymphonyGen)
[![GitHub][link-github]](https://github.com/symphonygen/symphonygen)
[![Website][link-website]](https://symphonygen.github.io/)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2604.25498)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:symphonygen.md -->
<!-- MODEL:vocalrender.md -->
<details id="vocalrender">
<summary>VocalRender</summary>

### VocalRender

**Description:** A score-native singing voice synthesis model that directly transforms composer-oriented symbolic scores — lyrics, MIDI pitches, note values, and tempo — into expressive 48 kHz singing audio. Combines an interleaved lyric–note representation (preserving note-to-word alignment and melisma), continuous acoustic latents via AudioVAE, and autoregressive diffusion for global prosody modeling. Does not require phoneme-level durations, an explicit duration predictor, or a time-aligned acoustic reference. Fine-tuned from VoxCPM2 on the open-source CrawlSinger-OS dataset.

**Release Date:** July 30, 2026

| Feature | Value |
|---------|-------|
| **Music Gen** | ✅ |
| **Input Modalities** | text (lyrics + MIDI pitches + note values + tempo) |
| **Streaming** | ❌ |
| **Languages** | Chinese |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Duration** | score-dependent (variable length) |
| **Sample Rate** | 48 kHz |
| **Base Model** | openbmb/VoxCPM2 |
| **Architecture** | interleaved lyric–note representation + AudioVAE + autoregressive diffusion |
| **Pipeline Tag** | text-to-speech |
| **Singing Voice Synthesis** | yes |
| **Score Native** | yes (no phoneme-level durations needed) |
| **Melisma Support** | yes |
| **Training Dataset** | pymaster/CrawlSinger-OS (open-source) |
| **Variants** | VocalRender (base), VocalRender-Pro |

**Features:** Score-native singing voice synthesis: an interleaved representation serializes BPM followed by each lyric syllable and its associated (pitch, note-value) pairs, retaining lyric-to-note alignment and supporting melisma — eliminating the need for phoneme-level durations or time-aligned acoustic references. AudioVAE compresses singing into continuous acoustic latents that preserve fine pitch, timbre, and articulation, while an autoregressive diffusion model handles global prosody modeling and local reconstruction.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/pymaster/VocalRender)
[![GitHub][link-github]](https://github.com/pymaster17/VocalRender)
[![Website][link-website]](https://pymaster17.github.io/VocalRender/)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2607.27768)
[![HuggingFace][link-huggingface]](https://huggingface.co/datasets/pymaster/CrawlSinger-OS)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:vocalrender.md -->
<!-- MODEL:allegretto-mini.md -->
<details id="allegretto-mini">
<summary>Allegretto Mini</summary>

### Allegretto Mini

**Description:** A lightweight, local-first AI music generation model by OSAMA INC (India). Synthesizes stereo audio at 44.1 kHz directly from text prompts using ONNX Runtime — no cloud API, no server-side GPU, no PyTorch dependency required. Built on a three-stage pipeline (T5Gemma text encoder → 20-layer DiT with 8-step rectified-flow sampling → SAME-S decoder) derived from the Stable Audio 3 Small architecture, independently int4-quantized and packaged for efficient local deployment. Total download size ~640 MB.

**Release Date:** July 27, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | ~640 MB (int4 quantized ONNX) |
| **Music Gen** | ✅ |
| **Input Modalities** | text |
| **Streaming** | ❌ |
| **Languages** | English |
| **License** | ![Stability AI][license-stability-ai] |
| **Duration** | up to 10s (default), 8 diffusion steps |
| **Sample Rate** | 44.1 kHz stereo |
| **Platforms** | CPU (ONNX Runtime), GPU (ONNX Runtime EP) |
| **Library** | onnxruntime (no PyTorch needed) |
| **Architecture** | T5Gemma encoder (768-dim, 256 tokens) + 20-layer DiT + SAME-S decoder |
| **Quantization** | int4 MatMulNBits (block_size=16), GatherBlockQuantized for embeddings |
| **Text To Music** | ✅ |
| **Local First** | yes |

**Features:** A production-grade text-to-music model compressed to ~640 MB of int4 ONNX weights that runs entirely on-device via ONNX Runtime — no Python or PyTorch required. The three-stage pipeline (T5Gemma → DiT → SAME-S) is derived from the Stable Audio 3 Small architecture but independently quantized and repackaged for CPU-first local inference, making it one of the smallest and most portable open-weight music generation models available.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/Dev4285/Allegretto-Mini)
[![GitHub][link-github]](https://github.com/aryanisproinroblox-source/Allegretto-Mini)
[![Demo][link-demo]](https://huggingface.co/spaces/Dev4285/Allegretto-Mini-Demo)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:allegretto-mini.md -->
<!-- MODEL:unimumo.md -->
<details id="unimumo">
<summary>UniMuMo</summary>

### UniMuMo

**Description:** A self-contained safe-artifact release of UniMuMo by Motius, repackaging the authors' published weights into a single verifiable checkpoint loaded via `motius.pipelines.unimumo.UniMuMoPipeline`. The model is a 24-layer, 1,024-dimensional dual-stream autoregressive Transformer operating over parallel music and motion token streams at a shared 50 Hz rate (Encodec 32 kHz audio with four 2,048-entry RVQ codebooks; HumanML3D-263 motion at 60 fps; T5-base text encoder and captioner). Supported routes include text-to-motion, text-to-music, joint text-to-music-motion, music-to-dance (AIST++), dance-to-music (D2M-GAN 86-clip protocol), plus captioning on both music and motion inputs. Maximum generation length per call is 10 seconds. The upstream paper is *UniMuMo: Unified Text, Music and Motion Generation* (Yang et al., arXiv 2410.04534).

**Release Date:** July 22, 2026

| Feature | Value |
|---------|-------|
| **Music Gen** | ✅ |
| **Input Modalities** | text, audio, motion |
| **Streaming** | ❌ |
| **Languages** | English |
| **License** | ![Unknown][license-unknown] |
| **Release Type** | derivative repackage (Motius re-release) |
| **Upstreams Repo** | hanyangclarence/UniMuMo@a75ddac7 |
| **Pipeline** | motius.pipelines.unimumo.UniMuMoPipeline |
| **Duration** | up to 10 s per call |
| **Sample Rate** | 32 kHz (Encodec audio) |
| **Motion Representation** | HumanML3D-263 at 60 fps |
| **Music Representation** | Encodec 32 kHz, four 2,048-entry RVQ codebooks |
| **Shared Code Rate** | 50 Hz |
| **Architecture** | 24-layer, 1,024-D dual-stream autoregressive Transformer |
| **Text Encoder** | T5-base (encoder + captioner) |
| **Text To Music** | ✅ |
| **Text To Motion** | yes |
| **Joint Text Music Motion** | yes |
| **Music To Dance** | yes |
| **Dance To Music** | yes |
| **Music Captioning** | yes |
| **Motion Captioning** | yes |
| **Benchmarks** | HumanML3D (T2M, M2T), AIST++ (M2D, D2M-GAN 86-clip) |
| **Self Contained** | yes (no upstream import needed) |

**Features:** UniMuMo's novelty is a **single dual-stream autoregressive Transformer** that jointly generates synchronized music and motion tokens from text, plus the reverse routes — all from one set of weights, no external captioners or codecs required at runtime. Motius' release packages every component (Encodec, T5 encoder + captioner, SentencePiece tokenizer, HumanML3D normalization stats, configuration, provenance) into one safe artifact with explicit tensor-layout mapping and a pass-or-fail loader, so `UniMuMoPipeline.from_pretrained` exposes text-to-music-motion, music-to-dance, dance-to-music, and bidirectional captioning behind one entry point. Reproduction audit reports exact code/waveform parity with the upstream runtime (`RMSE=0`, `max abs err=0`) on all anchor routes.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/ZeyuLing/Motius-UniMuMo)
[![HuggingFace][link-huggingface]](https://huggingface.co/ClarenceY/unimumo)
[![GitHub][link-github]](https://github.com/hanyangclarence/UniMuMo)
[![Website][link-website]](https://hanyangclarence.github.io/unimumo_demo/)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2410.04534)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:unimumo.md -->
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


<p align="center">· · · · · · · · · · · · · ·</p>
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


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:lmdm.md -->
<!-- MODEL:stable-audio-3.md -->
<details id="stable-audio-3">
<summary>Stable Audio 3</summary>

### Stable Audio 3

**Description:** A state-of-the-art open platform for fast, high-quality audio and music generation built around a diffusion transformer and the SAME (Semantic-Acoustic Music Encoder) autoencoder. Ships in four variants — Small-Music, Small-SFX, Medium, and Large (API only) — covering lightweight CPU inference up to the highest-quality 2.7B parameter model. Supports variable-length generation up to 380 seconds and built-in LoRA fine-tuning.

**Release Date:** May 20, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 433M (Small) / 1.4B (Medium) / 2.7B (Large, API only) |
| **Music Gen** | ✅ |
| **Input Modalities** | text, audio (audio-to-audio editing + inpainting/continuation) |
| **Streaming** | ❌ |
| **Languages** | English |
| **License** | ![Stability AI][license-stability-ai] |
| **Duration** | up to 380s (Medium / Large), 120s (Small) |
| **Sample Rate** | 44.1 kHz stereo, 256-dim latents |
| **Platforms** | CPU (Small), CUDA / TensorRT (Medium), CoreML / MLX (Apple Silicon) |
| **Text To Audio** | yes |
| **Audio To Audio** | yes (editing + inpainting/continuation) |
| **Lora Training** | yes (built-in `uv sync --extra lora`; MLX LoRA training on Apple Silicon) |
| **Api Only Variant** | large (2.7B) |

**Features:** Open-weight diffusion transformer paired with the SAME (Semantic-Acoustic Music Encoder) autoencoder — a stereo 44.1 kHz model with 256-dimensional latents optimized for both generative tractability and high-quality reconstruction. Variable-length generation avoids wasting inference time on unused latents, and built-in stackable LoRA personalization runs at small, medium, and large scales (plus a pure-MLX LoRA path on Apple Silicon).

**Links:**
[![GitHub][link-github]](https://github.com/Stability-AI/stable-audio-3)
[![HuggingFace][link-huggingface]](https://huggingface.co/collections/stabilityai/stable-audio-3)
[![HuggingFace][link-huggingface]](https://huggingface.co/collections/stabilityai/stable-audio-3-extra)
[![Demo][link-demo]](https://huggingface.co/spaces/stabilityai/stable-audio-3)
[![Blog][link-blog]](https://stability.ai/news-updates/meet-stable-audio-3-the-model-family-built-for-artistic-experimentation-with-open-weight-models)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2605.17991)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:stable-audio-3.md -->
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


<p align="center">· · · · · · · · · · · · · ·</p>
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


<p align="center">· · · · · · · · · · · · · ·</p>

---

<details>
<summary><b>Table of Contents</b></summary>

* [Models](#models)
* [Language & Auxiliary Models](#auxiliary)
* [GGUF / Quants & Merges](#finetunes)
* [Tools & Apps](#tools)
* [Finetunes & LoRA](#lora-section)
  * [Merges](#merges)
  * [LoRA (Community)](#lora)

</details>

<a id="models"></a>

## ⣿ Models

| Ver | Regime | Variant | DiT | Download |
| :--- | :--- | :--- | :---: | :--- |
| **v1** | ![Base][badge-base] | — | ![3.5B][badge-3.5B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/ACE-Step-v1-3.5B) |
| | | | | |
| **1.5** | ![Base][badge-base] | — | ![3.5B][badge-3.5B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-v15-base) ┊ [![][gh-Comfy-Org]](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files/resolve/main/split_files/diffusion_models/acestep_v1.5_base.safetensors) |
| **1.5** | ![SFT][badge-sft] | — | ![3.5B][badge-3.5B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-v15-sft) |
| **1.5** | ![Canonical][badge-canonical] | — | ![3.5B][badge-3.5B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/Ace-Step1.5) |
| **1.5** | ![Turbo][badge-turbo] | ![Continuous][badge-turbo-continuous] | ![3.5B][badge-3.5B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-v15-turbo-continuous) ┊ [![][gh-Comfy-Org]](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files/resolve/main/split_files/diffusion_models/acestep_v1.5_turbo.safetensors) |
| **1.5** | ![Turbo][badge-turbo] | ![Shift-1][badge-turbo-shift1] | ![3.5B][badge-3.5B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-v15-turbo-shift1) |
| **1.5** | ![Turbo][badge-turbo] | ![Shift-3][badge-turbo-shift3] | ![3.5B][badge-3.5B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-v15-turbo-shift3) |
| **1.5** | ![Merged][badge-merged] | turbo AIO | ![3.5B][badge-3.5B] | [![][gh-Comfy-Org]](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files/resolve/main/checkpoints/ace_step_1.5_turbo_aio.safetensors) |
| | | | | |
| **1.5 XL** | ![Base][badge-base] | — | ![4B][badge-4B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-v15-xl-base) ┊ [![][gh-Comfy-Org]](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files/resolve/main/split_files/diffusion_models/acestep_v1.5_xl_base_bf16.safetensors) |
| **1.5 XL** | ![SFT][badge-sft] | — | ![4B][badge-4B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-v15-xl-sft) ┊ [![][gh-Comfy-Org]](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files/resolve/main/split_files/diffusion_models/acestep_v1.5_xl_sft_bf16.safetensors) |
| **1.5 XL** | ![Turbo][badge-turbo] | ![Shift-1][badge-turbo-shift1] | ![4B][badge-4B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-v15-xl-turbo) ┊ [![][gh-Comfy-Org]](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files/resolve/main/split_files/diffusion_models/acestep_v1.5_xl_turbo_bf16.safetensors) |


<p align="center">╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍</p>

<a id="auxiliary"></a>

## ⣿ Language & Auxiliary Models

| Ver | Model | Purpose | DiT | Download |
| :--- | :--- | :--- | :---: | :--- |
| **1.5** | `acestep-5Hz-lm-0.6B` | Language model (5 Hz) | ![0.6B][badge-0.6B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-5Hz-lm-0.6B) ┊ [![][gh-Comfy-Org]](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files/resolve/main/split_files/text_encoders/qwen_0.6b_ace15.safetensors) |
| **1.5** | `acestep-5Hz-lm-1.7B` | Language model (5 Hz) | — | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-5Hz-lm-1.7B) ┊ [![][gh-Comfy-Org]](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files/resolve/main/split_files/text_encoders/qwen_1.7b_ace15.safetensors) |
| **1.5** | `acestep-5Hz-lm-4B` | Language model (5 Hz) | ![4B][badge-4B] | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-5Hz-lm-4B) ┊ [![][gh-Comfy-Org]](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files/resolve/main/split_files/text_encoders/qwen_4b_ace15.safetensors) |
| **1.5** | `acestep-captioner` | Music captioner (training data labeling) | — | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/acestep-captioner) |
| **1.5** | `ace-step-v1.5-1d-vae-stable-audio-format` | 1D VAE (latent ↔ StableAudio tokens) | — | [![][gh-ACE-Step]](https://huggingface.co/ACE-Step/ace-step-v1.5-1d-vae-stable-audio-format) ┊ [![][gh-Comfy-Org]](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files/resolve/main/split_files/vae/ace_1.5_vae.safetensors) |
| **1.5** | `Ace-Step-1.5-ScragVAE` | Custom VAE (audio-to-audio, alt decoder) | — | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-ScragVAE) |
| **1.5** | `ACEStep-XL-Regrind-V1` | XL Turbo regrind: VAE decoder + DiT LoRA for Oobleck artifact suppression (CC BY-NC-SA 4.0) | ![4B][badge-4B] | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1) |
| **1.5** | `ace-step-v1.5-1d-vae-stable-audio-format` (rAVEUK) | 1D VAE (community mirror) | — | [![][gh-rAVEUK]](https://huggingface.co/rAVEUK/ace-step-v1.5-1d-vae-stable-audio-format) |

<details>
<summary>mdmachine — ACEStep XL Regrind V1 (VAE + DiT + LoRA)</summary>

#### [mdmachine ACEStep-XL-Regrind-V1](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1)

Fine-tuned VAE decoder and DiT LoRA targeting the Oobleck hum artifact series at the weight level. Base: ACE-Step XL Turbo. License: CC BY-NC-SA 4.0.

**VAE** (`vae/`)

| File | Quant | Size | Download |
| :--- | :---: | :---: | :---: |
| `acestep_1.5_vae_Regrind_V10b` | ![BF16][badge-BF16] | 337 MB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/vae/acestep_1.5_vae_Regrind_V10b.safetensors) |
| `acestep_1.5_vae_Regrind_V10b` (GGUF) | ![BF16][badge-BF16] | 337 MB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/vae/acestep_1.5_vae_Regrind_V10b-BF16.gguf) |
| `acestep_1.5_vae_Regrind_V10b_blend50` | ![BF16][badge-BF16] | 337 MB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/vae/acestep_1.5_vae_Regrind_V10b_blend50.safetensors) |
| `acestep_1.5_vae_Regrind_V10b_blend50` (GGUF) | ![BF16][badge-BF16] | 337 MB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/vae/acestep_1.5_vae_Regrind_V10b_blend50-BF16.gguf) |
| `acestep_1.5_vae_Regrind_V9b` (GGUF) | ![BF16][badge-BF16] | 337 MB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/vae/acestep_1.5_vae_Regrind_V9b-BF16.gguf) |
| `acestep_1.5_vae_Regrind_V9b_blend50` (GGUF) | ![BF16][badge-BF16] | 337 MB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/vae/acestep_1.5_vae_Regrind_V9b_blend50-BF16.gguf) |
| `acestep_1.5_vae_Regrind_V9b_blend50` | ![BF16][badge-BF16] | 337 MB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/vae/acestep_1.5_vae_Regrind_V9b_blend50.safetensors) |
| `acestep_1.5_vae_Regrind_V7` | ![BF16][badge-BF16] | 337 MB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/vae/acestep_1.5_vae_Regrind_V7.safetensors) |

**DiT base model** (`dit/`)

| File | Quant | Size | Download |
| :--- | :---: | :---: | :---: |
| `acestep_xl_turbo_Regrind_V1` | ![BF16][badge-BF16] | 9.97 GB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/dit/acestep_xl_turbo_Regrind_V1.safetensors) |
| `acestep_1.5_xl_turbo_regrind_v1` | ![Q4_K_M][badge-Q4_K_M] | 2.99 GB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/dit/acestep_1.5_xl_turbo_regrind_v1-Q4_K_M.gguf) |
| `acestep_1.5_xl_turbo_regrind_v1` | ![Q6_K][badge-Q6_K] | 4.10 GB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/dit/acestep_1.5_xl_turbo_regrind_v1-Q6_K.gguf) |
| `acestep_1.5_xl_turbo_regrind_v1` | ![Q8_0][badge-Q8_0] | 5.18 GB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/dit/acestep_1.5_xl_turbo_regrind_v1-Q8_0.gguf) |

**LoRA** (`lora/`)

| File | Size | Download |
| :--- | :---: | :---: |
| `acestep_xl_turbo_lora_LayerRegrind_V7` (strength 0.25–0.50) | 393 MB | [![][gh-mdmachine]](https://huggingface.co/mdmachine/ACEStep-XL-Regrind-V1/resolve/main/lora/acestep_xl_turbo_lora_LayerRegrind_V7.safetensors) |

</details>

<p align="center">╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍</p>

<a id="finetunes"></a>

## ⣿ GGUF / Quants & Merges

### ▣ GGUF Quantized Models

Optimized for lower memory; load as transformer-only in ComfyUI.

<details>
  <summary>Serveurperso — ACE-Step 1.5 GGUF (full set)</summary>

#### ❖ [Serveurperso ACE-Step-1.5-GGUF](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF) — v1.5 (3.5B DiT)

| Model | Quant | Size | Download |
| :--- | :---: | :---: | :---: |
| acestep-v15-base | ![BF16][badge-BF16] | 4.79 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-base-BF16.gguf) |
| acestep-v15-base | ![Q4_K_M][badge-Q4_K_M] | 1.45 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-base-Q4_K_M.gguf) |
| acestep-v15-base | ![Q5_K_M][badge-Q5_K_M] | 1.70 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-base-Q5_K_M.gguf) |
| acestep-v15-base | ![Q6_K][badge-Q6_K] | 1.97 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-base-Q6_K.gguf) |
| acestep-v15-base | ![Q8_0][badge-Q8_0] | 2.55 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-base-Q8_0.gguf) |
| acestep-v15-sft | ![BF16][badge-BF16] | 4.79 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-sft-BF16.gguf) |
| acestep-v15-sft | ![Q4_K_M][badge-Q4_K_M] | 1.45 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-sft-Q4_K_M.gguf) |
| acestep-v15-sft | ![Q5_K_M][badge-Q5_K_M] | 1.70 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-sft-Q5_K_M.gguf) |
| acestep-v15-sft | ![Q6_K][badge-Q6_K] | 1.97 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-sft-Q6_K.gguf) |
| acestep-v15-sft | ![Q8_0][badge-Q8_0] | 2.55 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-sft-Q8_0.gguf) |
| acestep-v15-turbo | ![BF16][badge-BF16] | 4.79 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-BF16.gguf) |
| acestep-v15-turbo | ![Q4_K_M][badge-Q4_K_M] | 1.45 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-Q4_K_M.gguf) |
| acestep-v15-turbo | ![Q5_K_M][badge-Q5_K_M] | 1.70 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-Q5_K_M.gguf) |
| acestep-v15-turbo | ![Q6_K][badge-Q6_K] | 1.97 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-Q6_K.gguf) |
| acestep-v15-turbo | ![Q8_0][badge-Q8_0] | 2.55 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-Q8_0.gguf) |
| acestep-v15-turbo-continuous | ![BF16][badge-BF16] | 4.79 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-continuous-BF16.gguf) |
| acestep-v15-turbo-continuous | ![Q4_K_M][badge-Q4_K_M] | 1.45 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-continuous-Q4_K_M.gguf) |
| acestep-v15-turbo-continuous | ![Q5_K_M][badge-Q5_K_M] | 1.70 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-continuous-Q5_K_M.gguf) |
| acestep-v15-turbo-continuous | ![Q6_K][badge-Q6_K] | 1.97 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-continuous-Q6_K.gguf) |
| acestep-v15-turbo-continuous | ![Q8_0][badge-Q8_0] | 2.55 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-continuous-Q8_0.gguf) |
| acestep-v15-turbo-shift1 | ![BF16][badge-BF16] | 4.79 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-shift1-BF16.gguf) |
| acestep-v15-turbo-shift1 | ![Q4_K_M][badge-Q4_K_M] | 1.45 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-shift1-Q4_K_M.gguf) |
| acestep-v15-turbo-shift1 | ![Q5_K_M][badge-Q5_K_M] | 1.70 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-shift1-Q5_K_M.gguf) |
| acestep-v15-turbo-shift1 | ![Q6_K][badge-Q6_K] | 1.97 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-shift1-Q6_K.gguf) |
| acestep-v15-turbo-shift1 | ![Q8_0][badge-Q8_0] | 2.55 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-shift1-Q8_0.gguf) |
| acestep-v15-turbo-shift3 | ![BF16][badge-BF16] | 4.79 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-shift3-BF16.gguf) |
| acestep-v15-turbo-shift3 | ![Q4_K_M][badge-Q4_K_M] | 1.45 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-shift3-Q4_K_M.gguf) |
| acestep-v15-turbo-shift3 | ![Q5_K_M][badge-Q5_K_M] | 1.70 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-shift3-Q5_K_M.gguf) |
| acestep-v15-turbo-shift3 | ![Q6_K][badge-Q6_K] | 1.97 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-shift3-Q6_K.gguf) |
| acestep-v15-turbo-shift3 | ![Q8_0][badge-Q8_0] | 2.55 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-turbo-shift3-Q8_0.gguf) |
| acestep-v15-sftturbo50 | ![BF16][badge-BF16] | 4.79 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-sftturbo50-BF16.gguf) |
| acestep-v15-sftturbo50 | ![Q8_0][badge-Q8_0] | 2.55 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-sftturbo50-Q8_0.gguf) |

#### ❖ [Serveurperso ACE-Step-1.5-GGUF](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF) — v1.5 XL (4B DiT)

| Model | Quant | Size | Download |
| :--- | :---: | :---: | :---: |
| acestep-v15-xl-base | ![BF16][badge-BF16] | 9.98 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-base-BF16.gguf) |
| acestep-v15-xl-base | ![Q4_K_M][badge-Q4_K_M] | 2.99 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-base-Q4_K_M.gguf) |
| acestep-v15-xl-base | ![Q5_K_M][badge-Q5_K_M] | 3.53 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-base-Q5_K_M.gguf) |
| acestep-v15-xl-base | ![Q6_K][badge-Q6_K] | 4.10 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-base-Q6_K.gguf) |
| acestep-v15-xl-base | ![Q8_0][badge-Q8_0] | 5.31 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-base-Q8_0.gguf) |
| acestep-v15-xl-sft | ![BF16][badge-BF16] | 9.98 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-sft-BF16.gguf) |
| acestep-v15-xl-sft | ![Q4_K_M][badge-Q4_K_M] | 2.99 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-sft-Q4_K_M.gguf) |
| acestep-v15-xl-sft | ![Q5_K_M][badge-Q5_K_M] | 3.53 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-sft-Q5_K_M.gguf) |
| acestep-v15-xl-sft | ![Q6_K][badge-Q6_K] | 4.10 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-sft-Q6_K.gguf) |
| acestep-v15-xl-sft | ![Q8_0][badge-Q8_0] | 5.31 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-sft-Q8_0.gguf) |
| acestep-v15-xl-turbo | ![BF16][badge-BF16] | 9.98 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-turbo-BF16.gguf) |
| acestep-v15-xl-turbo | ![Q4_K_M][badge-Q4_K_M] | 2.99 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-turbo-Q4_K_M.gguf) |
| acestep-v15-xl-turbo | ![Q5_K_M][badge-Q5_K_M] | 3.53 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-turbo-Q5_K_M.gguf) |
| acestep-v15-xl-turbo | ![Q6_K][badge-Q6_K] | 4.10 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-turbo-Q6_K.gguf) |
| acestep-v15-xl-turbo | ![Q8_0][badge-Q8_0] | 5.31 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-turbo-Q8_0.gguf) |
| acestep-v15-xl-sftturbo50 | ![BF16][badge-BF16] | 9.98 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-sftturbo50-BF16.gguf) |
| acestep-v15-xl-sftturbo50 | ![Q4_K_M][badge-Q4_K_M] | 2.99 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-sftturbo50-Q4_K_M.gguf) |
| acestep-v15-xl-sftturbo50 | ![Q5_K_M][badge-Q5_K_M] | 3.53 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-sftturbo50-Q5_K_M.gguf) |
| acestep-v15-xl-sftturbo50 | ![Q6_K][badge-Q6_K] | 4.10 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-sftturbo50-Q6_K.gguf) |
| acestep-v15-xl-sftturbo50 | ![Q8_0][badge-Q8_0] | 5.31 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-v15-xl-sftturbo50-Q8_0.gguf) |

#### ❖ [Serveurperso ACE-Step-1.5-GGUF](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF) — Language models / VAE

| Component | Quant | Size | Download |
| :--- | :---: | :---: | :---: |
| Qwen3-Embedding-0.6B | ![BF16][badge-BF16] | 1.20 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/Qwen3-Embedding-0.6B-BF16.gguf) |
| Qwen3-Embedding-0.6B | ![Q8_0][badge-Q8_0] | 0.78 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/Qwen3-Embedding-0.6B-Q8_0.gguf) |
| acestep-5Hz-lm-0.6B | ![BF16][badge-BF16] | 1.33 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-5Hz-lm-0.6B-BF16.gguf) |
| acestep-5Hz-lm-0.6B | ![Q8_0][badge-Q8_0] | 0.71 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-5Hz-lm-0.6B-Q8_0.gguf) |
| acestep-5Hz-lm-1.7B | ![BF16][badge-BF16] | 3.71 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-5Hz-lm-1.7B-BF16.gguf) |
| acestep-5Hz-lm-1.7B | ![Q8_0][badge-Q8_0] | 1.98 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-5Hz-lm-1.7B-Q8_0.gguf) |
| acestep-5Hz-lm-4B | ![BF16][badge-BF16] | 8.38 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-5Hz-lm-4B-BF16.gguf) |
| acestep-5Hz-lm-4B | ![Q5_K_M][badge-Q5_K_M] | 3.03 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-5Hz-lm-4B-Q5_K_M.gguf) |
| acestep-5Hz-lm-4B | ![Q6_K][badge-Q6_K] | 3.44 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-5Hz-lm-4B-Q6_K.gguf) |
| acestep-5Hz-lm-4B | ![Q8_0][badge-Q8_0] | 4.46 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/acestep-5Hz-lm-4B-Q8_0.gguf) |
| vae | ![BF16][badge-BF16] | 0.34 GB | [![][gh-Serveurperso]](https://huggingface.co/Serveurperso/ACE-Step-1.5-GGUF/resolve/main/vae-BF16.gguf) |

</details>

<details>
  <summary>scragnog — ACE-Step 1.5 MXFP4 Quants</summary>

#### ❖ [scragnog Ace-Step-1.5-MXFP4-Quants](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants)

| Model | Quant | Size | Download |
| :--- | :---: | :---: | :---: |
| acestep-v15-base | ![MXFP4][badge-nvfp4] | 1.28 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-base-MXFP4.gguf) |
| acestep-v15-sft | ![MXFP4][badge-nvfp4] | 1.28 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-sft-MXFP4.gguf) |
| acestep-v15-sftturbo50 | ![MXFP4][badge-nvfp4] | 1.28 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-sftturbo50-MXFP4.gguf) |
| acestep-v15-turbo | ![MXFP4][badge-nvfp4] | 1.28 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-turbo-MXFP4.gguf) |
| acestep-v15-turbo-continuous | ![MXFP4][badge-nvfp4] | 1.28 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-turbo-continuous-MXFP4.gguf) |
| acestep-v15-turbo-shift1 | ![MXFP4][badge-nvfp4] | 1.28 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-turbo-shift1-MXFP4.gguf) |
| acestep-v15-turbo-shift3 | ![MXFP4][badge-nvfp4] | 1.28 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-turbo-shift3-MXFP4.gguf) |
| acestep-v15-xl-base | ![MXFP4][badge-nvfp4] | 2.66 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-xl-base-MXFP4.gguf) |
| acestep-v15-xl-sft | ![MXFP4][badge-nvfp4] | 2.66 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-xl-sft-MXFP4.gguf) |
| acestep-v15-xl-sftturbo50 | ![MXFP4][badge-nvfp4] | 2.66 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-xl-sftturbo50-MXFP4.gguf) |
| acestep-v15-xl-turbo | ![MXFP4][badge-nvfp4] | 2.66 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-xl-turbo-MXFP4.gguf) |
| acestep-v15-merge-base-turbo-xl-ta-0.5 | ![MXFP4][badge-nvfp4] | 2.66 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-merge-base-turbo-xl-ta-0.5-MXFP4.gguf) |
| acestep-v15-merge-sft-turbo-xl-ta-0.3 | ![MXFP4][badge-nvfp4] | 2.66 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.3-MXFP4.gguf) |
| acestep-v15-merge-sft-turbo-xl-ta-0.7 | ![MXFP4][badge-nvfp4] | 2.66 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/Ace-Step-1.5-MXFP4-Quants/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.7-MXFP4.gguf) |

</details>

<details>
  <summary>hrktxz — ACE-Step 1.5 int8 convrot (ComfyUI)</summary>

#### ❖ [hrktxz ACE_Step_1.5_ComfyUI_int8_convrot](https://huggingface.co/hrktxz/ACE_Step_1.5_ComfyUI_int8_convrot)

| Model | Quant | Size | Download |
| :--- | :---: | :---: | :---: |
| acestep_v1.5_base | ![int8][badge-int8mixedtensorwise] | 2.40 GB | [![][gh-hrktxz]](https://huggingface.co/hrktxz/ACE_Step_1.5_ComfyUI_int8_convrot/resolve/main/acestep_v1.5_base_int8_convrot.safetensors) |
| acestep_v1.5_turbo | ![int8][badge-int8mixedtensorwise] | 2.40 GB | [![][gh-hrktxz]](https://huggingface.co/hrktxz/ACE_Step_1.5_ComfyUI_int8_convrot/resolve/main/acestep_v1.5_turbo_int8_convrot.safetensors) |
| acestep_v1.5_xl_base | ![int8][badge-int8mixedtensorwise] | 4.99 GB | [![][gh-hrktxz]](https://huggingface.co/hrktxz/ACE_Step_1.5_ComfyUI_int8_convrot/resolve/main/acestep_v1.5_xl_base_int8_convrot.safetensors) |
| acestep_v1.5_xl_sft | ![int8][badge-int8mixedtensorwise] | 4.99 GB | [![][gh-hrktxz]](https://huggingface.co/hrktxz/ACE_Step_1.5_ComfyUI_int8_convrot/resolve/main/acestep_v1.5_xl_sft_int8_convrot.safetensors) |
| acestep_v1.5_xl_sft_turbo | ![int8][badge-int8mixedtensorwise] | 4.99 GB | [![][gh-hrktxz]](https://huggingface.co/hrktxz/ACE_Step_1.5_ComfyUI_int8_convrot/resolve/main/acestep_v1.5_xl_sft_turbo_int8_convrot.safetensors) |
| acestep_v1.5_xl_turbo | ![int8][badge-int8mixedtensorwise] | 4.99 GB | [![][gh-hrktxz]](https://huggingface.co/hrktxz/ACE_Step_1.5_ComfyUI_int8_convrot/resolve/main/acestep_v1.5_xl_turbo_int8_convrot.safetensors) |

</details>

<details>
  <summary>mingyi456 — ACE-Step 1.5 XL DF11 (ComfyUI)</summary>

#### ❖ [mingyi456 Ace-Step1.5-XL-DF11-ComfyUI](https://huggingface.co/mingyi456/Ace-Step1.5-XL-DF11-ComfyUI)

| Model | Quant | Size | Download |
| :--- | :---: | :---: | :---: |
| acestep_v1.5_xl_base | ![BF16][badge-BF16] | 6.80 GB | [![][gh-mingyi456]](https://huggingface.co/mingyi456/Ace-Step1.5-XL-DF11-ComfyUI/resolve/main/acestep_v1.5_xl_base_bf16-DF11.safetensors) |
| acestep_v1.5_xl_sft | ![BF16][badge-BF16] | 6.80 GB | [![][gh-mingyi456]](https://huggingface.co/mingyi456/Ace-Step1.5-XL-DF11-ComfyUI/resolve/main/acestep_v1.5_xl_sft_bf16-DF11.safetensors) |
| acestep_v1.5_xl_turbo | ![BF16][badge-BF16] | 6.80 GB | [![][gh-mingyi456]](https://huggingface.co/mingyi456/Ace-Step1.5-XL-DF11-ComfyUI/resolve/main/acestep_v1.5_xl_turbo_bf16-DF11.safetensors) |

</details>

<p align="center">╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍</p>

<a id="tools"></a>

## ⣿ Tools & Apps

* [acestep.vst3](https://github.com/ace-step/acestep.vst3) — ACE-Step VST3 plugin for DAWs.
* [acestep.cpp](https://github.com/ServeurpersoCom/acestep.cpp) — C++ inference engine for ACE-Step.
* [ACE-Step Transcriber](https://huggingface.co/ACE-Step/acestep-transcriber) — audio transcription model (audio-text-to-text).

<p align="center">╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍</p>

<a id="lora-section"></a>

## ⣿ Finetunes & LoRA

<a id="merges"></a>

### ▣ Merges

#### ❖ [jeankassio acestep_v1.5_merge_sft_turbo_xl](https://huggingface.co/jeankassio/acestep_v1.5_merge_sft_turbo_xl)

| Model | Quant | Size | Download |
| :--- | :---: | :---: | :---: |
| merge sft+turbo+xl ta-0.5 | ![BF16][badge-BF16] | 19.95 GB | [![][gh-jeankassio]](https://huggingface.co/jeankassio/acestep_v1.5_merge_sft_turbo_xl/resolve/main/acestep_v1.5_merge_sft_turbo_xl_ta_0.5.safetensors) |

#### ❖ [scragnog ace-step-1.5-gguf-merge-models](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models)

| Merge | Variant | Quant | Size | Download |
| :--- | :--- | :---: | :---: | :---: |
| Base SFT | XL ta 0.5 | ![BF16][badge-BF16] | 9.98 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-base-sft-xl-ta-0.5-BF16.gguf) |
| Base SFT | XL ta 0.5 | ![Q4_K_M][badge-Q4_K_M] | 2.99 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-base-sft-xl-ta-0.5-Q4_K_M.gguf) |
| Base SFT | XL ta 0.5 | ![Q5_K_M][badge-Q5_K_M] | 3.53 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-base-sft-xl-ta-0.5-Q5_K_M.gguf) |
| Base SFT | XL ta 0.5 | ![Q6_K][badge-Q6_K] | 4.10 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-base-sft-xl-ta-0.5-Q6_K.gguf) |
| Base SFT | XL ta 0.5 | ![Q8_0][badge-Q8_0] | 5.31 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-base-sft-xl-ta-0.5-Q8_0.gguf) |
| Base Turbo | XL ta 0.5 | ![BF16][badge-BF16] | 9.98 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-base-turbo-xl-ta-0.5-BF16.gguf) |
| Base Turbo | XL ta 0.5 | ![Q4_K_M][badge-Q4_K_M] | 2.99 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-base-turbo-xl-ta-0.5-Q4_K_M.gguf) |
| Base Turbo | XL ta 0.5 | ![Q5_K_M][badge-Q5_K_M] | 3.53 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-base-turbo-xl-ta-0.5-Q5_K_M.gguf) |
| Base Turbo | XL ta 0.5 | ![Q6_K][badge-Q6_K] | 4.10 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-base-turbo-xl-ta-0.5-Q6_K.gguf) |
| Base Turbo | XL ta 0.5 | ![Q8_0][badge-Q8_0] | 5.31 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-base-turbo-xl-ta-0.5-Q8_0.gguf) |
| SFT Turbo | XL ta 0.3 | ![BF16][badge-BF16] | 9.98 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.3-BF16.gguf) |
| SFT Turbo | XL ta 0.3 | ![Q4_K_M][badge-Q4_K_M] | 2.99 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.3-Q4_K_M.gguf) |
| SFT Turbo | XL ta 0.3 | ![Q5_K_M][badge-Q5_K_M] | 3.53 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.3-Q5_K_M.gguf) |
| SFT Turbo | XL ta 0.3 | ![Q6_K][badge-Q6_K] | 4.10 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.3-Q6_K.gguf) |
| SFT Turbo | XL ta 0.3 | ![Q8_0][badge-Q8_0] | 5.31 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.3-Q8_0.gguf) |
| SFT Turbo | XL ta 0.7 | ![BF16][badge-BF16] | 9.98 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.7-BF16.gguf) |
| SFT Turbo | XL ta 0.7 | ![Q4_K_M][badge-Q4_K_M] | 2.99 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.7-Q4_K_M.gguf) |
| SFT Turbo | XL ta 0.7 | ![Q5_K_M][badge-Q5_K_M] | 3.53 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.7-Q5_K_M.gguf) |
| SFT Turbo | XL ta 0.7 | ![Q6_K][badge-Q6_K] | 4.10 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.7-Q6_K.gguf) |
| SFT Turbo | XL ta 0.7 | ![Q8_0][badge-Q8_0] | 5.31 GB | [![][gh-scragnog]](https://huggingface.co/scragnog/ace-step-1.5-gguf-merge-models/resolve/main/acestep-v15-merge-sft-turbo-xl-ta-0.7-Q8_0.gguf) |

<p align="center">╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍</p>

<a id="lora"></a>

### ▣ LoRA (Community)

#### ❖ HuggingFace

| Name | Desc | Link |
| :--- | :--- | :--- |
| `aworldofhate_adarkerworld` | Darker / aggressive aesthetic style (ACE-Step 1.5) | [![][gh-DeadSoulInside]](https://huggingface.co/DeadSoulInside/aworldofhate_adarkerworld) |
| `ACE-Step-v1-chinese-rap-LoRA` | Chinese rap style (ACE-Step v1) | [![][gh-Tuananh20015]](https://huggingface.co/Tuananh20015/ACE-Step-v1-chinese-rap-LoRA) |
| `ACE-Step Audio Steering Suite` | Audio steering / control suite (collection) | [![][gh-lukasz]](https://huggingface.co/collections/lukasz-staniszewski/ace-step-audio-steering-suite) |
| `Ace-Step-1.5-XL-Concept-Sliders` | Concept sliders for XL (style/strength control) | [![][gh-Xanthius]](https://huggingface.co/Xanthius/Ace-Step-1.5-XL-Concept-Sliders) |
| `ACE-Step-xl-base-pop-electro-lora` | Pop / electro (XL Base) | [![][gh-Nekochu]](https://huggingface.co/Nekochu/ACE-Step-xl-base-pop-electro-lora) |
| `russian-pop-lora` | Russian pop | [![][gh-kemendev]](https://huggingface.co/kemendev/russian-pop-lora) |
| `ACE-Step-v1.5-Kawaii_Future_Bass-LoRA` | Kawaii future bass | [![][gh-NoyzeAI]](https://huggingface.co/NoyzeAI/ACE-Step-v1.5-Kawaii_Future_Bass-LoRA) |
| `ACE-Step-v1.5-raspy-vocal-and-instrumental-5-LoRAs` | Raspy vocal + instrumental set (5 LoRAs) | [![][gh-DisturbingTheField]](https://huggingface.co/DisturbingTheField/ACE-Step-v1.5-raspy-vocal-and-instrumental-5-LoRAs) |
| `ACE-Step-v1.5-ambient_dream1-LoRA` | Ambient dream | [![][gh-DisturbingTheField]](https://huggingface.co/DisturbingTheField/ACE-Step-v1.5-ambient_dream1-LoRA) |
| `davesnow1/Loras` | Mixed LoRA collection (folder) | [![][gh-davesnow1]](https://huggingface.co/davesnow1/Loras/tree/main) |
| `ACE-Step-1.5-Naija-Legacy-Rhythms-LoRA-v1` | Nigerian legacy rhythms | [![][gh-David-A-Amoo]](https://huggingface.co/David-A-Amoo/ACE-Step-1.5-Naija-Legacy-Rhythms-LoRA-v1) |
| `ACE-Step-v1.5-acoustic-guitar-and-a-merge-LoRA` | Acoustic guitar + merge | [![][gh-DisturbingTheField]](https://huggingface.co/DisturbingTheField/ACE-Step-v1.5-acoustic-guitar-and-a-merge-LoRA) |
| `Acestep1.5-qinglong-lokr` | Qinglong LoKR (Chinese dragon style) | [![][gh-bdsqlsz]](https://huggingface.co/bdsqlsz/Acestep1.5-qinglong-lokr) |
| `ACE-STEP-1.5v-rain-techno-lora` | Rain techno | [![][gh-tarn59]](https://huggingface.co/tarn59/ACE-STEP-1.5v-rain-techno-lora) |
| `Afrobeat_Urban_v1_ACESTEP_V1.5SFT` | Afrobeat / urban (v1.5 SFT) | [![][gh-walkis]](https://huggingface.co/walkis/Afrobeat_Urban_v1_ACESTEP_V1.5SFT) |
| `acestep-lora-cryda` | Cryda style | [![][gh-duckdbot]](https://huggingface.co/duckdbot/acestep-lora-cryda) |
| `RagaLoRA-indian-music-ace-step` | Indian raga music | [![][gh-veeceey]](https://huggingface.co/veeceey/RagaLoRA-indian-music-ace-step) |
| `russianrap-v3-lora` | Russian rap (v3) | [![][gh-ruslanmusinrusmus]](https://huggingface.co/ruslanmusinrusmus/russianrap-v3-lora) |
| `ACE-Step1.5-Zulu-Finteuned` | Zulu music finetune | [![][gh-Gyimah3]](https://huggingface.co/Gyimah3/ACE-Step1.5-Zulu-Finteuned) |
| `AceStep_Refine_Redmond` | Refine / polish | [![][gh-artificialguybr]](https://huggingface.co/artificialguybr/AceStep_Refine_Redmond) |
| `macan-lora-v6-acestep-v15` | Macan style (v6) | [![][gh-ruslanmusinrusmus]](https://huggingface.co/ruslanmusinrusmus/macan-lora-v6-acestep-v15) |
| `acestep-cinematic-soundtrack` | Cinematic soundtrack | [![][gh-Notid]](https://huggingface.co/Notid/acestep-cinematic-soundtrack) |
| `acestep-lofi-lora` | Lo-fi | [![][gh-pedroapfilho]](https://huggingface.co/pedroapfilho/acestep-lofi-lora) |
| `smoki-lofi-acestep1.5` | Lo-fi | [![][gh-smoki9999]](https://huggingface.co/smoki9999/smoki-lofi-acestep1.5) |
| `super_eurobeats_ACE_STEP-1.5-lora` | Eurobeat (Initial D style) | [![][gh-tarn59]](https://huggingface.co/tarn59/super_eurobeats_ACE_STEP-1.5-lora) |
| `Totally-Generic-LoFi-Hip-Hop-LoKr` | Lo-fi hip-hop; analog sound, trigger: Portishead | [![][gh-Urabewe]](https://huggingface.co/Urabewe/Totally-Generic-LoFi-Hip-Hop-LoKr) |
| `daft-punk-adapter` | Daft Punk style (multi-epoch checkpoints available) | [![][gh-Wildminder]](https://huggingface.co/Wildminder/ace-step-loras/resolve/main/daft-punk/daft-punk-adapter.safetensors) |
| `french-rap-iam` | French rap (IAM group) | [![][gh-Wildminder]](https://huggingface.co/Wildminder/ace-step-loras/resolve/main/french-rap-iam/french-rap-iam.safetensors) |
| `hip-hop-anti-bleed-turbo` | Hip-hop anti-bleed (Turbo) | [![][gh-Wildminder]](https://huggingface.co/Wildminder/ace-step-loras/resolve/main/hip-hop-anti-bleed-turbo/hip-hop-anti-bleed-turbo.safetensors) |
| `m3l0dysh33p-epoch500` | MelodySheep style (WIP, epoch 500) | [![][gh-Wildminder]](https://huggingface.co/Wildminder/ace-step-loras/resolve/main/m3l0dysh33p/m3l0dysh33p-epoch500.safetensors) |
| `monstercat-edm-adapter` | Monstercat-style EDM; trigger: `mstrct` | [![][gh-Wildminder]](https://huggingface.co/Wildminder/ace-step-loras/resolve/main/monstercat-edm/monstercat-edm-adapter.safetensors) |
| `nevermind` | Nirvana Nevermind album; trigger: `nevermind` | [![][gh-Wildminder]](https://huggingface.co/Wildminder/ace-step-loras/resolve/main/nevermind/nevermind.safetensors) |
| `prodigy` | The Prodigy style | [![][gh-Wildminder]](https://huggingface.co/Wildminder/ace-step-loras/resolve/main/prodigy/prodigy.safetensors) |
| `progressive-techno-ag-xl-turbo-best` | Progressive techno; trigger: `JVS` | [![][gh-Wildminder]](https://huggingface.co/Wildminder/ace-step-loras/resolve/main/progressive-techno/progressive-techno-ag-xl-turbo-best.safetensors) |
| `riddim-dnb-underground` | Riddim / DnB / Underground | [![][gh-Wildminder]](https://huggingface.co/Wildminder/ace-step-loras/resolve/main/riddim-dnb-underground/riddim-dnb-underground.safetensors) |
| `snail-house` | Snail's House style (chiptune / 8-bit / electronic) | [![][gh-Wildminder]](https://huggingface.co/Wildminder/ace-step-loras/resolve/main/snail-house/snail-house.safetensors) |
| `synth-funk-new-jack-swing` | Synth-funk pop / New Jack Swing (Turbo) | [![][gh-Wildminder]](https://huggingface.co/Wildminder/ace-step-loras/resolve/main/synth-funk-new-jack-swing/synth-funk-new-jack-swing.pt) |

<p align="center">╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍ ╍</p>

#### ❖ Civitai

Part of [ACEStep LoRAs](https://civitai.com/models/2416425/acestep-loras) — genre DoRA set for ACE-Step 1.5 Base (prompt-driven, no trigger token).

| Name | Desc | Link |
| :--- | :--- | :--- |
| `DEATHSTEP` | Experimental deathstep (ComfyUI-FL-AceStep training) | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=2716799) |
| `FUNK_A2B` | Funk | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=2981735) |
| `AMBIENT_A` | Ambient | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=2981749) |
| `DEEPHOUSE_A` | Deep house | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=2981752) |
| `PHONK_A` | Phonk | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=2982033) |
| `DEATHCORE_C` | Deathcore | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=2998842) |
| `ALTPOP_A` | Alt-pop | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=2999417) |
| `BLUES_A` | Blues | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=2999441) |
| `ALTERNATIVEMETAL_A` | Alternative metal | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002467) |
| `ALTERNATIVEROCK_B` | Alternative rock | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002472) |
| `AMBIENT_B` | Ambient | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002473) |
| `AMERICANA_A` | Americana | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002475) |
| `ARTPOP_A` | Art pop | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002476) |
| `BREAKBEAT_A` | Breakbeat | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002479) |
| `BREAKCORE_A` | Breakcore | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002480) |
| `CHILLWAVE_A` | Chillwave | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002482) |
| `CHILL_A` | Chill | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002484) |
| `CHIPTUNE_A` | Chiptune | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002485) |
| `CINEMATICPOP_A` | Cinematic pop | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002487) |
| `CLASSICAL_A` | Classical | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002490) |
| `COMEDY_A` | Comedy | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002491) |
| `COUNTRY_A` | Country | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3002493) |
| `FUNK_A` | Funk | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3004478) |
| `ACOUSTIC_A` | Acoustic | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3024410) |
| `ALTERNATIVEROCK_A` | Alternative rock | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3024450) |
| `ALTERNATIVE_A` | Alternative | [![][civitai]](https://civitai.com/models/2416425/acestep-loras?modelVersionId=3024451) |
| `Deep House Vocal` | Deep house vocal (ACE-Step 1.5 XL Base V2) | [![][civitai]](https://civitai.com/models/2648802/deep-house-vocal-acestep-v15-xl-base-v2?modelVersionId=2974219) |
| `Minimal Techno Overdrive` | Minimal techno (ACE-Step 1.5 XL Base) | [![][civitai]](https://civitai.com/models/2642635/minimal-techno-overdrive-lora-ace-step-v15-xl-base?modelVersionId=2967308) |
| `AceStep TranceDance` | Trance dance | [![][civitai]](https://civitai.com/models/2637950/acesteptrancedancev1?modelVersionId=2961844) |
| `Dark Techno Sub-Bass Rumble` | Dark techno sub-bass (ACE-Step 1.5 XL) | [![][civitai]](https://civitai.com/models/2631092/dark-techno-sub-bass-rumble-ace-step-15-xl?modelVersionId=2954080) |
| `ACE-Step 1.5 Psytrance` | Psytrance (v2.0) | [![][civitai]](https://civitai.com/models/2624128/ace-step-15-psytrance-lora-ver-20?modelVersionId=2946188) |
| `AceStep 8-bit` | 8-bit chiptune | [![][civitai]](https://civitai.com/models/2611058/acestep8bitv1?modelVersionId=2931802) |
| `1951-1964` | Vintage 1951-1964 (ACE-Step 1.5 Base) | [![][civitai]](https://civitai.com/models/2585761/1951-1964-ace-step-15-base-lora?modelVersionId=2931399) |
| `ACE-STEP 80's Citypop` | 80s citypop | [![][civitai]](https://civitai.com/models/1646967/ace-step-80s-citypop-lora?modelVersionId=1864132) |
| `Super Eurobeats (ACEStep 1.5 XL)` | 90s Eurobeat, Initial D style (XL Base) | [![][civitai]](https://civitai.com/models/2702491/super-eurobeats-acestep-15-xl?modelVersionId=3034855) |

<!-- MARKDOWN LINKS & IMAGES -->
[gh-ACE-Step]: https://img.shields.io/badge/ACE--Step-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-scragnog]: https://img.shields.io/badge/scragnog-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-mdmachine]: https://img.shields.io/badge/mdmachine-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-rAVEUK]: https://img.shields.io/badge/rAVEUK-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-hrktxz]: https://img.shields.io/badge/hrktxz-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-Serveurperso]: https://img.shields.io/badge/Serveurperso-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-mingyi456]: https://img.shields.io/badge/mingyi456-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-jeankassio]: https://img.shields.io/badge/jeankassio-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-Comfy-Org]: https://img.shields.io/badge/Comfy--Org-lightgrey?style=flat-square&logo=huggingface&logoColor=white

[badge-0.6B]: https://img.shields.io/badge/0.6B-0077cc?style=flat-square
[badge-3.5B]: https://img.shields.io/badge/3.5B-0077cc?style=flat-square
[badge-4B]: https://img.shields.io/badge/4B-e05d44?style=flat-square

[badge-base]: https://img.shields.io/badge/Base-0077cc?style=flat-square
[badge-sft]: https://img.shields.io/badge/SFT-28a745?style=flat-square
[badge-canonical]: https://img.shields.io/badge/Canonical-dfb317?style=flat-square
[badge-turbo]: https://img.shields.io/badge/Turbo-e05d44?style=flat-square
[badge-turbo-continuous]: https://img.shields.io/badge/Continuous-e05d44?style=flat-square
[badge-turbo-shift1]: https://img.shields.io/badge/Shift--1-17a2b8?style=flat-square
[badge-turbo-shift3]: https://img.shields.io/badge/Shift--3-97c00f?style=flat-square
[badge-merged]: https://img.shields.io/badge/Merged-6f42c1?style=flat-square

[badge-BF16]: https://img.shields.io/badge/BF16-0077cc?style=flat-square
[badge-Q4_K_M]: https://img.shields.io/badge/Q4__K__M-dfb317?style=flat-square
[badge-Q5_K_M]: https://img.shields.io/badge/Q5__K__M-97c00f?style=flat-square
[badge-Q6_K]: https://img.shields.io/badge/Q6__K-0077cc?style=flat-square
[badge-Q8_0]: https://img.shields.io/badge/Q8__0-28a745?style=flat-square
[badge-nvfp4]: https://img.shields.io/badge/MXFP4-6f42c1?style=flat-square
[badge-int8mixedtensorwise]: https://img.shields.io/badge/int8-17a2b8?style=flat-square

[gh-DeadSoulInside]: https://img.shields.io/badge/DeadSoulInside-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-Tuananh20015]: https://img.shields.io/badge/Tuananh20015-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-lukasz]: https://img.shields.io/badge/lukasz--staniszewski-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-Xanthius]: https://img.shields.io/badge/Xanthius-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-Nekochu]: https://img.shields.io/badge/Nekochu-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-kemendev]: https://img.shields.io/badge/kemendev-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-NoyzeAI]: https://img.shields.io/badge/NoyzeAI-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-DisturbingTheField]: https://img.shields.io/badge/DisturbingTheField-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-davesnow1]: https://img.shields.io/badge/davesnow1-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-David-A-Amoo]: https://img.shields.io/badge/David--A--Amoo-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-bdsqlsz]: https://img.shields.io/badge/bdsqlsz-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-tarn59]: https://img.shields.io/badge/tarn59-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-walkis]: https://img.shields.io/badge/walkis-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-duckdbot]: https://img.shields.io/badge/duckdbot-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-veeceey]: https://img.shields.io/badge/veeceey-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-ruslanmusinrusmus]: https://img.shields.io/badge/ruslanmusinrusmus-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-Gyimah3]: https://img.shields.io/badge/Gyimah3-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-artificialguybr]: https://img.shields.io/badge/artificialguybr-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-Notid]: https://img.shields.io/badge/Notid-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-pedroapfilho]: https://img.shields.io/badge/pedroapfilho-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-smoki9999]: https://img.shields.io/badge/smoki9999-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-Urabewe]: https://img.shields.io/badge/Urabewe-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[gh-Wildminder]: https://img.shields.io/badge/Wildminder-lightgrey?style=flat-square&logo=huggingface&logoColor=white
[civitai]: https://img.shields.io/badge/Civitai-ea2d6f?style=flat-square
</details>
<!-- /MODEL:ace-step-15.md -->
<!-- MODEL:heartmula.md -->
<details id="heartmula">
<summary>HeartMuLa</summary>

### HeartMuLa

**Description:** A family of open-source music foundation models from HeartMuLa, comprising HeartMuLa (a 3B-param lyrics+tags music language model with multilingual support covering Chinese, English, Japanese, Korean, and Spanish), HeartCodec (a 12.5 Hz music codec for high-fidelity reconstruction), HeartTranscriptor (a Whisper-tuned ASR model for lyrics transcription), and HeartCLAP (audio-text alignment for music description and cross-modal retrieval). The current recommended pre-trained checkpoint is `HeartMuLa-oss-3B-happy-new-year` (Feb 13, 2026), tuned for lyrics controllability; an RL-refined variant `HeartMuLa-RL-oss-3B-20260123` is also published for tighter style/tag control. Reference-audio conditioning, fine-grained control, and a 7B variant are listed as TODO.

**Release Date:** February 13, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 3B (HeartMuLa LM) + HeartCodec decoder |
| **Music Gen** | ✅ |
| **Input Modalities** | text (lyrics + comma-separated style tags) |
| **Streaming** | ❌ |
| **Languages** | Chinese, English, Japanese, Korean, Spanish |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Duration** | up to 4 min (default `max_audio_length_ms=240000`) |
| **Architectures** | language model (LM) + codec decoder |
| **Text To Music** | ✅ |
| **Lyrics Support** | ✅ |
| **Family Components** | HeartMuLa (LM), HeartCodec (12.5 Hz), HeartTranscriptor (ASR), HeartCLAP (audio-text) |
| **Recommended Checkpoint** | HeartMuLa-oss-3B-happy-new-year |
| **Rl Variant** | HeartMuLa-RL-oss-3B-20260123 (tighter style/tag control) |

**Features:** A single open-source stack for end-to-end music generation: a 3B multilingual lyrics+tags LM that autoregressively emits HeartCodec's 12.5 Hz tokens, paired with a high-fidelity codec decoder — released alongside the rest of the pipeline (HeartTranscriptor for lyrics ASR, HeartCLAP for audio-text alignment) and a benchmark (HeartBeats). Apache 2.0 across repo and all model weights.

**Links:**
[![GitHub][link-github]](https://github.com/HeartMuLa/heartlib)
[![HuggingFace][link-huggingface]](https://huggingface.co/HeartMuLa)
[![HuggingFace][link-huggingface]](https://huggingface.co/HeartMuLa/HeartMuLa-oss-3B-happy-new-year)
[![HuggingFace][link-huggingface]](https://huggingface.co/HeartMuLa/HeartMuLa-oss-3B)
[![HuggingFace][link-huggingface]](https://huggingface.co/HeartMuLa/HeartMuLa-RL-oss-3B-20260123)
[![HuggingFace][link-huggingface]](https://huggingface.co/HeartMuLa/HeartCodec-oss-20260123)
[![HuggingFace][link-huggingface]](https://huggingface.co/HeartMuLa/HeartTranscriptor-oss)
[![Demo][link-demo]](https://huggingface.co/spaces/HeartMuLa/heartmula)
[![Website][link-website]](https://heartmula.github.io/)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2601.10547)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:heartmula.md -->
<!-- MODEL:zen-musician.md -->
<details id="zen-musician">
<summary>Zen Musician</summary>

### Zen Musician

**Description:** A 7B-param LLaMA-based lyrics-to-song model repackaged by Zen (Hanzo AI / Zoo Labs Foundation) from M-A-P's YuE stage-1 model. It generates the lyric+prompt-conditioned token stream that the YuE pipeline feeds into a stage-2 audio decoder. Designed for in-process use via HuggingFace Transformers (`transformers.AutoModelForCausalLM`) rather than a diffusion/Gradio UI, so it drops cleanly into scripts and notebooks. Full song generation also requires the YuE stage-2 model ([m-a-p/YuE-s2-1B-general](https://huggingface.co/m-a-p/YuE-s2-1B-general)).

**Release Date:** November 13, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 6.2B BF16 (7B-class LLaMA) |
| **Music Gen** | ✅ |
| **Input Modalities** | text (lyrics + style prompt) |
| **Streaming** | ❌ |
| **Languages** | English |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Architecture** | LlamaForCausalLM |
| **Base Model** | m-a-p/YuE-s1-7B-anneal-en-cot |
| **Library** | transformers (AutoModelForCausalLM + AutoTokenizer) |
| **Pipeline Tag** | text-to-audio |
| **Stage** | 1 of 2 (lyrics → latent tokens; full song requires YuE stage-2 decoder) |
| **Text To Music** | ✅ |
| **Lyrics Support** | ✅ |

**Features:** A consumer-friendly, Transformers-native repackage of the open YuE lyrics-to-song pipeline: the stage-1 model that translates lyrics and a style prompt into the token stream consumed by YuE's stage-2 audio decoder. Released under Apache 2.0 with full attribution to the original M-A-P YuE authors, designed to drop into any `transformers.AutoModelForCausalLM` workflow.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/zenlm/zen-musician)
[![HuggingFace][link-huggingface]](https://huggingface.co/m-a-p/YuE-s1-7B-anneal-en-cot)
[![HuggingFace][link-huggingface]](https://huggingface.co/m-a-p/YuE-s2-1B-general)
[![GitHub][link-github]](https://github.com/multimodal-art-projection/YuE)
[![Website][link-website]](https://hanzo.ai)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:zen-musician.md -->
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


<p align="center">· · · · · · · · · · · · · ·</p>
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


<p align="center">· · · · · · · · · · · · · ·</p>
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


<p align="center">· · · · · · · · · · · · · ·</p>
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


<p align="center">· · · · · · · · · · · · · ·</p>
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


<p align="center">· · · · · · · · · · · · · ·</p>
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



<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:soulx-singer-music.md -->

<p align="center">≋≋≋≋≋≋≋≋≋≋≋≋≋≋</p>

## ░ Audio-Language Models (Audio Understanding)

Audio-language models (ALMs) — large audio-language and audio-reasoning specialists that do not generate audio. They caption audio, answer audio questions, transcribe speech, and reason over short or long audio inputs. Examples include NVIDIA's Audio Flamingo series, Qwen2-Audio, Xiaomi's MiDashengLM, Mellow, and music-specialised ALMs like TinyMU.

### Quick Comparison

| Model | Use Case | Input | Audio Length | Base Model | License |
| :--- | :--- | :--- | :--- | :--- | :--- |
| [MuScriptor](#muscriptor) | multi-instrument music transcription | full-mix audio | long | custom Mirelo + Kyutai + IRCAM | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [TinyMU](#tinymu) | music caption + QA | audio + text | short | from-scratch 229M | ![Unknown][license-unknown] |
| [Audio Flamingo 3](#audio-flamingo-3) | chat + reasoning | audio + text | long | Audio Flamingo 2 | ![NVIDIA NC][license-nvidia-noncommercial] |
| [MiDashengLM-7B-0804](#midashenglm) | caption + AQA | audio + text | short-medium | Qwen2.5-Omni-7B | ![Apache 2.0][license-apache-2.0] |
| [Mellow](#mellow) | AQA + captioning | audio + text | short | from-scratch 167M | ![MIT][license-mit] |
| [Audio Flamingo 2](#audio-flamingo-2) | reasoning | audio + text | 5 min | Qwen-2.5 | ![NVIDIA NC][license-nvidia-noncommercial] |
| [Qwen2-Audio-7B-Instruct](#qwen2-audio) | voice chat + analysis | audio + text | short-medium | Qwen2-Audio | ![Apache 2.0][license-apache-2.0] |
| [MusiLingo](#musilingo) | captioning + AQA | audio + text | short to long | Vicuna 7B + MERT | ![Unknown][license-unknown] |
| [MU-LLaMA](#mu-llama) | music QA + captioning | audio + text | short | LLaMA-2 + MERT | ![MIT][license-mit] |

<!-- MODEL:muscriptor.md -->
<details id="muscriptor">
<summary>MuScriptor</summary>

### MuScriptor

**Description:** MuScriptor is the first open-source multi-instrument music transcription model trained at scale — co-developed by Mirelo AI, Kyutai, and IRCAM. Trained on 170k songs spanning classical to heavy metal.

**Release Date:** July 9, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | small / medium / large (multi-size release) |
| **Use Case** | multi-instrument music transcription to MIDI |
| **Input** | full-mix audio (wav + mp3 streamed via CLI / web UI) |
| **Output Format** | multi-track MIDI |
| **Audio Length** | long (full songs, classical to heavy metal) |
| **Training Scale** | 170k songs |
| **Upstream Application** | Mirelo Studio Audio-to-MIDI tool (chord / key / tempo detection on top) |
| **Library** | torch + transformers (served via uvx) |
| **Model Size Variants** | muscriptor-small, muscriptor-medium, muscriptor-large |
| **Weights License** | cc-by-nc-4.0 (gated, requires HF ack) |
| **Code License** | MIT (GitHub repo) |
| **Audio Language Task** | yes |
| **Music Understanding** | ✅ |
| **Music Generation** | no |
| **Continuous Monitoring** | no |
| **Streaming Input** | yes (uvx transcribe) |
| **Benchmark** | Mirelo internal + Mirelo Studio tool |

**Features:** First open-source music transcription model trained at scale — 170k songs including classical to heavy metal. Co-built by Mirelo AI, Kyutai, and IRCAM. The Mirelo Studio Audio-to-MIDI tool layers chord / key / tempo detection on top, giving users the full harmonic picture from raw audio input.

**Links:**
[![Blog][link-blog]](https://www.mirelo.ai/blog/turning-audio-to-midi)
[![HuggingFace][link-huggingface]](https://huggingface.co/MuScriptor)
[![HFModelPage][link-hfmodelpage]](https://huggingface.co/MuScriptor/muscriptor-medium)
[![GitHub][link-github]](https://github.com/muscriptor/muscriptor)
[![Demo][link-demo]](https://muscriptor.kyutai.org)
[![Paper][link-paper]](https://arxiv.org/abs/2607.08168)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:muscriptor.md -->
<!-- MODEL:tinymu.md -->
<details id="tinymu">
<summary>TinyMU</summary>

### TinyMU

**Description:** TinyMU: A Compact Audio-Language Model for Music Understanding (paper: arXiv 2604.15849). A 229M-parameter music-specialised audio-language model that reaches 82% of SOTA LALM performance on the MuChoMusic benchmark while being 35× smaller than the SOTA system. Trained on the released MusicSkills-3.5M music-understanding dataset (captioning, QA, reasoning tasks across MusicCaps and other sources).

**Release Date:** April 17, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 229M |
| **Use Case** | music captioning, music QA, music reasoning |
| **Input** | audio + text |
| **Audio Length** | short music clips (~10 s) |
| **Base Model** | from-scratch 229M music-language model |
| **Music Generation** | no |
| **Audio Generation** | no |
| **Music Understanding** | ✅ |
| **Reasoning** | ✅ |
| **Architecture** | compact music-language model |
| **Training Data** | MusicSkills-3.5M (captioning, QA, reasoning tasks over MusicCaps etc.) |
| **Benchmark** | MuChoMusic |
| **License** | ![Unknown][license-unknown] |

**Features:** Compact music-specialised audio-language model trained on the released **MusicSkills-3.5M** dataset — listed as hitting 82% of SOTA LALM performance on MuChoMusic at 35× smaller scale, balancing captioning, QA, and reasoning skills specifically for music.

**Links:**
[![GitHub][link-github]](https://github.com/xiquan-li/TinyMU)
[![HuggingFace][link-huggingface]](https://huggingface.co/AndreasXi/TinyMU)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2604.15849)
[![HuggingFace][link-huggingface]](https://huggingface.co/datasets/AndreasXi/MusicSkills-3.5M)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:tinymu.md -->
<!-- MODEL:audio-flamingo-3.md -->
<details id="audio-flamingo-3">
<summary>Audio Flamingo 3</summary>

### Audio Flamingo 3

**Description:** NVIDIA's Audio Flamingo 3 — a fully open audio-language model that extends Audio Flamingo 2 with multi-turn chat, transcription shortcuts, and a chain-of-thought PEFT adapter (`AF-Think`) for audio reasoning. Integrated into HuggingFace Transformers.

**Release Date:** July 10, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | not specified (8B-class) |
| **Use Case** | multi-turn chat, transcription, audio reasoning (chain-of-thought) |
| **Input** | audio + text (text-only and audio-only modes also supported) |
| **Audio Length** | long (multi-turn, long-audio reasoning) |
| **Base Model** | Audio Flamingo 2 continuation (audio encoder + LLM backbone) |
| **Music Generation** | no |
| **Audio Generation** | no |
| **Reasoning** | ✅ |
| **Chat** | yes (multi-turn chat templating) |
| **Transcription** | yes (with strip_prefix option) |
| **Architecture** | Audio-language model with PEFT-based AF-Think reasoning adapter |
| **Training Data** | nvidia/AudioSkills, nvidia/AF-Chat, nvidia/AF-Think, nvidia/LongAudio |
| **License** | ![NVIDIA NC][license-nvidia-noncommercial] |

**Features:** Fully open continuation of Audio Flamingo 2 — adds a unified `apply_chat_template` API for multi-turn chat, a one-call `apply_transcription_request` shortcut with strip-prefix cleanup, and a PEFT-based **AF-Think** chain-of-thought reasoning adapter over the same checkpoints.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/nvidia/audio-flamingo-3)
[![HuggingFace][link-huggingface]](https://huggingface.co/nvidia/audio-flamingo-3-hf)
[![GitHub][link-github]](https://github.com/NVIDIA/audio-flamingo)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2507.08128)
[![Demo][link-demo]](https://research.nvidia.com/labs/adlr/AF3/)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:audio-flamingo-3.md -->
<!-- MODEL:midashenglm.md -->
<details id="midashenglm">
<summary>MiDashengLM-7B-0804</summary>

### MiDashengLM-7B-0804

**Description:** Xiaomi Research's MiDashengLM-7B-0804 — a 7B audio-language generalist captioner that pairs the Dasheng-0.6B audio encoder with Qwen2.5-Omni-7B as the language backbone, training on caption-based alignment. Reports 3.2x throughput speedup over comparable ALMs at the same accuracy and supports batch sizes up to 512.

**Release Date:** June 26, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 7B (audio encoder 0.6B + LLM 7B) |
| **Use Case** | holistic audio captioning, audio question answering |
| **Input** | audio + text |
| **Audio Length** | short-to-medium (caption-based; full-clip captions) |
| **Base Model** | dasheng-0.6B + Qwen2.5-Omni-7B (finetune) |
| **Music Generation** | no |
| **Audio Generation** | no |
| **Reasoning** | ✅ |
| **Batching** | up to 512 |
| **Inference Speedup** | 3.2x over peer ALMs |
| **Architecture** | caption-aligned audio-language model |
| **Languages** | en, zh, th, id, vi |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Features:** Caption-based audio-language alignment that combines Dasheng audio encoder with Qwen2.5-Omni-7B at 7B scale — SOTA-level holistic audio understanding with up to 512 batch size and 3.2× throughput vs. comparable ALMs, making captioning pipelines much cheaper to deploy at scale.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/mispeech/midashenglm-7b-0804-fp32)
[![GitHub][link-github]](https://github.com/xiaomi-research/dasheng-lm)
[![HuggingFace][link-huggingface]](https://huggingface.co/mispeech/midashenglm-7b-0804-bf16)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:midashenglm.md -->
<!-- MODEL:mellow.md -->
<details id="mellow">
<summary>Mellow</summary>

### Mellow

**Description:** A 167M-parameter audio-language model that takes **two audios plus a text prompt** and produces free-form text outputs. Trained on ~155 hours of audio (AudioCaps + Clotho), claims SoTA-class performance on audio-QA tasks with 50× fewer parameters than peer ALMs.

**Release Date:** March 10, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 167M |
| **Use Case** | audio question answering, audio captioning, audio reasoning, zero-shot |
| **Input** | two audios + text |
| **Audio Length** | short clips (~10 s) |
| **Base Model** | from-scratch 167M audio-language model |
| **Music Generation** | no |
| **Audio Generation** | no |
| **Reasoning** | ✅ |
| **Zero Shot** | yes |
| **Architecture** | small audio-language model |
| **Training Data** | AudioCaps, Clotho (~155 hours) |
| **License** | ![MIT][license-mit] |

**Features:** A two-audio plus text-conditioned small audio-language model (167M) that shows you can get SOTA-class AQA behaviour with **50× fewer parameters** than competitive models — and trains on a lean ~155-hour corpus of AudioCaps + Clotho.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/soham97/mellow)
[![GitHub][link-github]](https://github.com/soham97/Mellow)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2503.08540)
[![Demo][link-demo]](https://tinyurl.com/mellowredirect)
[![Paper][link-paper]](https://zenodo.org/records/15036628)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:mellow.md -->
<!-- MODEL:audio-flamingo-2.md -->
<details id="audio-flamingo-2">
<summary>Audio Flamingo 2</summary>

### Audio Flamingo 2

**Description:** NVIDIA's PyTorch implementation of Audio Flamingo 2 (paper: arXiv 2503.03983). A 3B parameter cross-attention audio-language model built on a Qwen-2.5 backbone. Adds two new datasets (AudioSkills for expert reasoning and LongAudio for long-audio understanding) and reports SOTA across 20+ audio-understanding and reasoning benchmarks while being smaller and trained on public data.

**Release Date:** March 4, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 3B |
| **Use Case** | audio understanding, reasoning, captioning, transcription, multi-turn chat |
| **Input** | audio + text |
| **Audio Length** | up to 5 minutes |
| **Base Model** | Qwen-2.5 (audio encoder + cross-attention) |
| **Music Generation** | no |
| **Audio Generation** | no |
| **Reasoning** | ✅ |
| **Long Audio** | yes (5 minutes) |
| **Architecture** | cross-attention audio-language model |
| **Training Data** | nvidia/AudioSkills + nvidia/LongAudio |
| **License** | ![Unknown][license-unknown] |

**Features:** Cross-attention audio-language model that builds Flamingo-style few-shot learning on top of Qwen-2.5, taught on AudioSkills and LongAudio — SOTA-class audio reasoning despite being only 3B parameters and trained exclusively on public data.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/nvidia/audio-flamingo-2)
[![GitHub][link-github]](https://github.com/NVIDIA/audio-flamingo)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2503.03983)
[![Demo][link-demo]](https://research.nvidia.com/labs/adlr/AF2/)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:audio-flamingo-2.md -->
<!-- MODEL:qwen2-audio.md -->
<details id="qwen2-audio">
<summary>Qwen2-Audio-7B-Instruct</summary>

### Qwen2-Audio-7B-Instruct

**Description:** Alibaba's Qwen2-Audio-7B-Instruct — a large audio-language model that supports two interaction modes: voice chat (audio-in, audio+text-out without user-typed text) and audio analysis (audio+text-in, text-out). Released alongside the Qwen2-Audio-7B pretrained variant.

**Release Date:** August 9, 2024

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Use Case** | voice chat, audio analysis (ASR + audio captioning + audio QA) |
| **Input** | audio (+ optional text) |
| **Audio Length** | short to medium (one-shot speech / audio analysis) |
| **Base Model** | Qwen2-Audio-7B (pretrained) |
| **Music Generation** | no |
| **Audio Generation** | no |
| **Reasoning** | limited (instruct-tuned) |
| **Voice Chat** | yes (no text input required) |
| **Audio Analysis** | yes |
| **Asr** | yes |
| **Architecture** | Qwen2 audio-language model |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Features:** Qwen-style audio-language architecture that supports **two distinct interaction modes** in one model — pure voice chat (audio in, free-form text out without user-typed prompts) and structured audio analysis (audio + text instruction in, text-only analysis out) — both served by the same instruct-tuned checkpoint.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/Qwen/Qwen2-Audio-7B-Instruct)
[![GitHub][link-github]](https://github.com/QwenLM/Qwen2-Audio)
[![Blog][link-blog]](https://qwenlm.github.io/blog/qwen2-audio/)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2407.10759)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:qwen2-audio.md -->
<!-- MODEL:musilingo.md -->
<details id="musilingo">
<summary>MusiLingo</summary>

### MusiLingo

**Description:** MusiLingo (NAACL 2024): "Bridging Music and Text with Pre-trained Language Models for Music Captioning and Query Response". Two-stage model — pretrained on a long-form music captioning dataset (LP-MusicCaps-MSD) and instruction-tuned on MusicInstruct for short/long music QA and on MusicQA. Built on MERT-v1-330M (music encoder) + Vicuna 7B v0 (text backbone).

**Release Date:** September 15, 2023

| Feature | Value |
|---------|-------|
| **Parameters** | 7B (Vicuna 7B v0) + 330M MERT-v1 (music encoder) |
| **Use Case** | music captioning, music QA (short + long + MusicQA) |
| **Input** | audio + text |
| **Audio Length** | short to long (variable; model trained to handle both) |
| **Base Model** | MERT-v1-330M + Vicuna 7B v0 |
| **Music Generation** | no |
| **Audio Generation** | no |
| **Music Understanding** | ✅ |
| **Captioning** | yes |
| **Question Answering** | yes (short + long) |
| **Architecture** | encoder (MERT) + instruction-tuned LLM (Vicuna) |
| **Training Data** | LP-MusicCaps-MSD (pretrain), MusicCaps, MusicInstruct, MusicQA (instruction-finetune) |
| **Publication** | NAACL 2024 |
| **License** | ![Unknown][license-unknown] |

**Features:** Two-stage music-language training recipe that pairs MERT-v1 with Vicuna 7B — first pretrains on a long-caption corpus (LP-MusicCaps-MSD), then instruction-tunes on MusicInstruct for short/long music QA, releasing the data and weights as a standard MERT-based music-understanding baseline at NAACL 2024.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/collections/m-a-p/musilingo)
[![GitHub][link-github]](https://github.com/zihaod/MusiLingo)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2309.08730)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:musilingo.md -->
<!-- MODEL:mu-llama.md -->
<details id="mu-llama">
<summary>MU-LLaMA</summary>

### MU-LLaMA

**Description:** MU-LLaMA (Music Understanding Large Language Model) — an audio-language model that answers questions about music and captions music files. Built on a MERT music encoder + LLaMA-2 (7B) text backbone with an adapter that incorporates music context. Used in the paper to generate MusicQA from MusicCaps and MagnaTagATune, providing training data for downstream text-to-music generation models.

**Release Date:** August 22, 2023

| Feature | Value |
|---------|-------|
| **Parameters** | 7B (LLaMA-2 base) + ~95M MERT (music encoder) |
| **Use Case** | music QA, music captioning, music understanding |
| **Input** | audio + text |
| **Audio Length** | short clips (MusicCaps-style) |
| **Base Model** | MERT (music encoder) + LLaMA-2 7B (text backbone) via adapter |
| **Music Generation** | no |
| **Audio Generation** | no |
| **Music Understanding** | ✅ |
| **Captioning** | yes |
| **Question Answering** | yes |
| **Architecture** | cross-modal audio-language model (encoder + LLM + adapter) |
| **Training Data** | MusicCaps, MagnaTagATune (used to build MusicQA) |
| **Evaluation** | MTG-Jamendo |
| **License** | ![MIT][license-mit] |

**Features:** One of the earliest MERT + LLaMA-2 music-language models for music QA/captioning — its **MusicQA** dataset (built from MusicCaps and MagnaTagATune) became a standard component of music-AQA pipelines, and the MERT backbone became the de-facto music encoder for downstream music-language work that followed (e.g. MusiLingo, LP-MusicCaps-MSD).

**Links:**
[![GitHub][link-github]](https://github.com/shansongliu/MU-LLaMA)
[![HuggingFace][link-huggingface]](https://huggingface.co/mu-llama/MU-LLaMA)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2308.11276)
[![Demo][link-demo]](https://crypto-code.github.io/MU-LLaMA-Demo/)


<p align="center">· · · · · · · · · · · · · ·</p>
</details>
<!-- /MODEL:mu-llama.md -->

<p align="center">≋≋≋≋≋≋≋≋≋≋≋≋≋≋</p>

## ░ Additional Resources

Community-maintained leaderboards for tracking and comparing music generation models.

- [Artificial Analysis — Music Leaderboard](https://artificialanalysis.ai/music/leaderboard) — Elo-based arena for music generation systems, ranking models on prompt fidelity, audio quality, and genre coverage.

<p align="center">≋≋≋≋≋≋≋≋≋≋≋≋≋≋</p>

## ░ Contributing

This list is continuously evolving. If you have any models to add or updates to suggest, please feel free to contribute! See [CONTRIBUTING.md](./CONTRIBUTING.md) for the template-driven workflow.

*Last Updated: August 2026*

<!-- MARKDOWN LINKS & IMAGES -->
[license-mit]: https://img.shields.io/badge/MIT-green?style=flat-square&logo=openldap "MIT"
[license-apache-2.0]: https://img.shields.io/badge/Apache_2.0-green?style=flat-square&logo=apache "Apache 2.0"
[license-stability-ai]: https://img.shields.io/badge/Stability_AI-informational?style=flat-square&logo=stability "Stability AI"
[license-unknown]: https://img.shields.io/badge/Unknown-lightgrey?style=flat-square "Unknown"
[license-cc-by-4.0]: https://img.shields.io/badge/CC_BY_4.0-green?style=flat-square&logo=creativecommons "CC BY 4.0"
[license-nvidia-noncommercial]: https://img.shields.io/badge/NVIDIA_NC-yellow?style=flat-square&logo=nvidia "NVIDIA NC"

[link-blog]: https://img.shields.io/badge/Blog-post-blue?style=flat-square "Blog post"
[link-demo]: https://img.shields.io/badge/Demo-live-blue?style=flat-square "Demo live"
[link-github]: https://img.shields.io/badge/GitHub-code-black?style=flat-square&logo=github "GitHub code"
[link-hfmodelpage]: https://img.shields.io/badge/HFModelPage-models-yellow?style=flat-square&logo=huggingface "HFModelPage models"
[link-huggingface]: https://img.shields.io/badge/HuggingFace-models-yellow?style=flat-square&logo=huggingface "HuggingFace models"
[link-paper]: https://img.shields.io/badge/Paper-paper-red?style=flat-square "Paper paper"
[link-website]: https://img.shields.io/badge/Website-site-blue?style=flat-square "Website site"
[link-arxiv]: https://img.shields.io/badge/arXiv-paper-red?style=flat-square "arXiv paper"
