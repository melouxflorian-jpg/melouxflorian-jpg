# Florian Meloux

**Founder & CEO of [CLERC](https://clerc.io) - the data infrastructure layer for sign language in multimodal AI.**

Text and images have a data layer. Sign language does not. I build the one that is missing:
native-signer video corpora, annotated to a versioned schema, released open for research and
licensed to foundation model labs.

Native LSF signer. ~10 years in sign language technology. I write the pipeline myself.

---

## 🤗 Open dataset - CLERC Épée v0.3

[![Hugging Face Dataset](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-CLERC--DATA%2Fepee-yellow?style=for-the-badge)](https://huggingface.co/datasets/CLERC-DATA/epee)
[![License](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-blue?style=for-the-badge)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
[![Downloads](https://img.shields.io/badge/Downloads-1k%2B-green?style=for-the-badge)](https://huggingface.co/datasets/CLERC-DATA/epee)
[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.22081248-1682D4?style=for-the-badge)](https://doi.org/10.5281/zenodo.22081248)

**→ [huggingface.co/datasets/CLERC-DATA/epee](https://huggingface.co/datasets/CLERC-DATA/epee)**

An open, AI-grade ASL keypoint corpus. Free to download, free for research.

- **1,200 clips · 6 Deaf signers · 71 minutes of signing** - 200 clips per signer
- **A 201-phrase parallel grid** across five of the six signers: the same sentence, signed by each,
  so signer variation can be isolated from phrase variation. The sixth contributes 200 declarative
  sentences on a separate prompt set, a second register
- **127,545 frames**, 3,788 gloss tokens, 724 unique glosses
- `(n_frames, 128, 3)` keypoint tensors - MediaPipe Hands, Pose, Face and FACE_OVAL silhouette
- **Privacy-preserving by design** - eyes, mouth and head outline only, no internal facial features
- Gold-standard gloss segmentation with temporal boundaries
- Ships with a **cross-signer generalization benchmark**
- CC BY-NC-SA 4.0 · commercial licensing at [florian@clerc.io](mailto:florian@clerc.io)

Sign language AI has been held back by datasets that are small, single-signer, or locked behind
institutional agreements. Épée is the piece I wanted to exist and did not: openly downloadable,
schema-validated, and built with Deaf signers who are paid and credited.

---

## The result the dataset is built to prove

Recognition accuracy on a **held-out, never-seen signer**, as a function of how many signers are in
the training set:

| Training signers | Held-out accuracy | Macro-F1 |
|---|---|---|
| 1 | 29% | 0.17 |
| 4 | 63% | 0.47 |
| **6** | **69%** | **0.57** |

A signer the model *has* seen scores 73%, so the stranger gap closes from 43 points at one training
signer to **3 points at six**, and the curve has not flattened.

Signer diversity, not clip count, is what moves cross-signer generalization. Sign language AI is
**data-bound, not model-bound**. That is the whole thesis behind CLERC, and the benchmark to
reproduce it ships inside the dataset.

---

## What I actually build

**Corpus production** - I design and run the annotation and QA pipeline end to end: gloss segmentation
with temporal boundaries, a versioned schema, validation that refuses non-conformant data at write
time, review queues and quality tiering. Python throughout.

**Pose & keypoints** - MediaPipe Hands/Pose/Face, 128×3 per-frame keypoint tensors, privacy-preserving
face representation, SMPL-X / MANO body and hand modelling, NumPy/SciPy signal processing over pose
streams.

**Models & evaluation** - isolated sign recognition baselines, automatic sign-boundary segmentation,
cross-signer generalization benchmarks, GPU data-augmentation experiments, per-gloss
precision/recall analysis.

**Release engineering** - versioned public dataset releases, reproducible benchmarks, and open
tooling so anyone can load the corpus in five minutes.

👉 **[epee-asl-toolkit](https://github.com/melouxflorian-jpg/epee-asl-toolkit)** - the open Python
toolkit for the dataset: loaders, keypoint visualization, inter-signer variability analysis.

---

## Before CLERC

Built **Keia**, a signing avatar deployed at Airbus, Thales, Macif, TotalEnergies and for the French
government. Co-founded Spokhand (~15M views). HEC Paris and UC Berkeley.

---

## Reach me

[clerc.io](https://clerc.io) · [florian@clerc.io](mailto:florian@clerc.io) · [Hugging Face](https://huggingface.co/CLERC-DATA) · [LinkedIn](https://www.linkedin.com/company/clerc-io/) · [X @FlorianMeloux](https://x.com/FlorianMeloux)

**Training a multimodal model and sign language is a gap? Email me.**

<sub>Keywords: sign language dataset · American Sign Language (ASL) · Langue des Signes Française (LSF) · sign language recognition (SLR) · sign language translation (SLT) · gloss annotation · open dataset · Hugging Face · MediaPipe keypoints · pose estimation · multimodal AI training data · Deaf AI accessibility · AI data infrastructure</sub>
