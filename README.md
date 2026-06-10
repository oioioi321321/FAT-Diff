# 🚀 FAT-Diff: Decoupling Structural Topology and Generative Realism for Extreme Face Super-Resolution

Official PyTorch implementation of **FAT-Diff**, a two-stage framework for extreme face super-resolution that decouples structural topology recovery and generative detail enhancement.

> **Status:** Under Review
> **Code Release:** To be released upon acceptance
> **Pretrained Models:** To be released upon acceptance

---

## 🏗️ Framework

### Stage I: Facial Topology-Aware Structure Construction

FAT-Net leverages graph-based attention mechanisms guided by the proposed Facial Topology Guidance Matrix (FTGM) to recover global facial structures from severely degraded inputs.

### Stage II: Diffusion-based Texture Refinement

A diffusion refinement network further restores high-frequency facial details and improves perceptual realism while maintaining identity consistency.

<p align="center">
  <img src="figs/framework.png" width="90%">
</p>

---

## 📦 Installation

```bash
git clone https://github.com/your_username/FAT-Diff.git

cd FAT-Diff

conda create -n fatdiff python=3.10

conda activate fatdiff

pip install -r requirements.txt
```

---

## 📦 Dataset Preparation

Prepare the datasets following the structure below:

```text
datasets/
├── CelebA
├── Helen
└── ...
```

For extreme face super-resolution, HR images are resized to 128×128 and degraded to 16×16 using bicubic downsampling.

```text
128×128
   ↓
Bicubic Downsampling
   ↓
16×16
```

---

## 📊Experimental Results

FAT-Diff achieves competitive performance on multiple face super-resolution benchmarks and demonstrates strong reconstruction capability under extreme low-resolution settings.

Representative visual results are provided below.

<p align="center">
  <img src="figs/visual_results.png" width="90%">
</p>

---

## 📈 Pretrained Models

Pretrained checkpoints will be released upon acceptance.

| Model    | Status      |
| -------- | ----------- |
| FAT-Net  | Coming Soon |
| FAT-Diff | Coming Soon |

---

---

## 🙏 Acknowledgement

This project is built upon several excellent open-source projects, including:

* BasicSR
* SwinIR
* GVTNet
* DDIM

We sincerely thank the authors for making their code publicly available.

---

## 📜 License

Copyright (c) 2026

This repository is released for academic research purposes only.

The code and associated materials may be used, reproduced, and modified for non-commercial research and educational purposes.

Commercial use of any part of this repository is strictly prohibited without prior written permission from the authors.

The authors provide this software "as is" without warranty of any kind.

For commercial licensing inquiries, please contact the corresponding author.
