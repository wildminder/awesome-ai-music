---
release_date: "March 23, 2026"
model_name: "MuQ-Eval (A3a LoRA)"
category: "audio_understanding"
summary: "Open-source per-sample quality metric for AI-generated music: lightweight prediction heads on MuQ-310M representations score individual 10-second clips against human mean opinion ratings."
slug: "muq-eval"
---

# MuQ-Eval (A3a LoRA)

MuQ-Eval is an open-source, per-sample quality metric for AI-generated music. Distributional measures such as Fréchet Audio Distance can only compare sets of clips and correlate poorly with human judgments; MuQ-Eval scores a single clip directly, predicting Musical Impression (MI) and Technical Artifacts (TA) on a 1–5 scale. It attaches lightweight prediction heads to MuQ-310M representations (`OpenMuQ/MuQ-large-msd-iter`) with attention-weighted mean pooling and trains them on MusicEval — 2,748 generated clips from 31 text-to-music systems with 13,740 expert ratings. The checkpoint published here is the **A3a** ablation variant: LoRA r=16 adapts the encoder and an ordinal cross-entropy loss with 5 bins replaces plain MSE; the project's recommended checkpoint remains the simpler frozen-encoder A1 model at `zhudi2825/MuQ-Eval-A1`. Under 5-fold cross-validation stratified by TTM system, A3a reaches system-level SRCC 0.960 and utterance-level SRCC 0.835 — statistically indistinguishable from A1's 0.957 / 0.838, which the paper reads as evidence that frozen MuQ features already carry quality-relevant information and that encoder choice dominates over head design or adaptation. The authors also report LoRA-adapted models trained on as few as 150 clips remain usable, enabling personalized quality evaluators from individual listener annotations, and a controlled degradation analysis showing sensitivity to signal-level artifacts but not musical-structural distortions. The A1 baseline scores a 10-second clip in ~35 ms on a single consumer GPU; A3a needs ~4 GB VRAM. MIT-licensed, with code, weights and evaluation scripts public.

## Links

- HuggingFace: https://huggingface.co/zhudi2825/MuQ-Eval
- GitHub: https://github.com/dgtql/MuQ-Eval
- arXiv: https://arxiv.org/abs/2603.22677

## Features

- use_case: per-sample music quality assessment, MOS prediction
- input: mono audio waveform at 24 kHz
- audio_length: 10 s max, 240,000 samples
- base_model: OpenMuQ/MuQ-large-msd-iter, MuQ-310M
- parameters: ~2M trainable on a 310M encoder
- architecture: MuQ-310M encoder + attention-weighted mean pooling + two MLP heads
- loss: ordinal cross-entropy, 5 bins
- output: MI and TA quality scores
- training_data: MusicEval, 2,748 clips, 31 TTM systems, 13,740 expert ratings
- evaluation: 5-fold CV, system SRCC 0.960, utterance SRCC 0.835
- music_gen: no
- music_understanding: yes
- vram: ~4 GB
- speed: real time on a single consumer GPU
- publication: arXiv 2603.22677, 2026
- license: MIT

## Comparison

- use_case: quality scoring
- input: audio waveform
- audio_length: 10 s
- base_model: MuQ-310M
- license: MIT

## Innovation

Replaces distributional FAD-style evaluation with an open, per-sample learned metric: frozen MuQ-310M music representations plus ~1–2M-parameter heads predict human MOS for individual clips at SRCC 0.957 system-level / 0.838 utterance-level, while an ablation sweep shows no architectural or objective addition meaningfully beats the frozen baseline — making encoder selection, not model engineering, the decisive design factor. Runs in real time on one consumer GPU and is fully open, unlike the previous high-correlation closed-source metric.
