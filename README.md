# FAT-Diff: Decoupling Structural Topology and Generative Realism for Extreme Face Super-Resolution

Official PyTorch implementation of **FAT-Diff**, a two-stage framework for extreme face super-resolution that decouples structural topology recovery and generative detail enhancement.

> **Status:** Under Review
> **Code Release:** Available
> **Pretrained Models:** To be released upon acceptance

---

## Overview

Extreme face super-resolution aims to reconstruct high-quality facial images from extremely low-resolution inputs. Existing methods often struggle to simultaneously preserve facial topology and generate realistic textures under severe degradation.

To address this challenge, we propose **FAT-Diff**, a two-stage framework that explicitly decouples structural topology recovery and generative realism enhancement.

The proposed framework consists of:

* **FAT-Net**: A Facial Topology-Aware Transformer for structural recovery.
* **FTGM**: A Facial Topology Guidance Matrix that models intrinsic relationships among facial regions.
* **Diffusion Refinement Module**: A DDIM-based generative refinement stage for realistic texture synthesis.
* **Perception-Distortion Controllable Inference**: An α-blending strategy that enables flexible trade-offs between distortion fidelity and perceptual quality.

---

## Framework

### Stage I: Facial Topology-Aware Structure Recovery

FAT-Net leverages graph-based attention mechanisms guided by the proposed Facial Topology Guidance Matrix (FTGM) to recover global facial structures from severely degraded inputs.

### Stage II: Diffusion-based Texture Refinement

A diffusion refinement network further restores high-frequency facial details and improves perceptual realism while maintaining identity consistency.

<p align="center">
  <img src="figs/framework.png" width="90%">
</p>

---

## Highlights

* Facial Topology Guidance Matrix (FTGM)
* Graph Vision Transformer based structure recovery
* Diffusion-based detail refinement
* Identity-preserving face reconstruction
* Controllable perception-distortion trade-off
* Strong performance under extreme 8× face super-resolution

---

## Project Structure

```text
FAT-Diff
├── basicsr
├── experiments
├── inference
├── options
├── scripts
├── tests
├── figs
├── results
└── README.md
```

---

## Installation

```bash
git clone https://github.com/your_username/FAT-Diff.git

cd FAT-Diff

conda create -n fatdiff python=3.10

conda activate fatdiff

pip install -r requirements.txt
```

---

## Dataset Preparation

Prepare the datasets following the structure below:

```text
datasets/
├── CelebA-HQ
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

## Training

### Stage I: FAT-Net

```bash
python basicsr/train.py \
-opt options/train/GVTNet/my_x8_train.yml
```

### Resume Training

```bash
python basicsr/train.py \
-opt options/train/GVTNet/my_x8_train.yml \
--auto_resume
```

### Stage II: Diffusion Refinement

```bash
python basicsr/train.py \
-opt options/train/GVTNet/diffusion_train.yml
```

### Multi-GPU Training

```bash
python -m torch.distributed.launch \
--nproc_per_node=4 \
basicsr/train.py \
-opt options/train/GVTNet/my_x8_train.yml \
--launcher pytorch
```

---

## Testing

```bash
python basicsr/test.py \
-opt options/test/GVTNet/your_test_config.yml
```

---

## Experimental Results

FAT-Diff achieves competitive performance on multiple face super-resolution benchmarks and demonstrates strong reconstruction capability under extreme low-resolution settings.

Representative visual results are provided below.

<p align="center">
  <img src="figs/visual_results.png" width="90%">
</p>

---

## Pretrained Models

Pretrained checkpoints will be released upon acceptance.

| Model    | Status      |
| -------- | ----------- |
| FAT-Net  | Coming Soon |
| FAT-Diff | Coming Soon |

---

## Citation

If you find this work useful, please consider citing:

```bibtex
@article{jin2026fatdiff,
  title={FAT-Diff: Decoupling Structural Topology and Generative Realism for Extreme Face Super-Resolution},
  author={Jin, XXX and others},
  journal={Under Review},
  year={2026}
}
```

---

## Acknowledgement

This project is built upon several excellent open-source projects, including:

* BasicSR
* SwinIR
* GVTNet
* DDIM

We sincerely thank the authors for making their code publicly available.

---

## License

Copyright (c) 2026

This repository is released for academic research purposes only.

The code and associated materials may be used, reproduced, and modified for non-commercial research and educational purposes.

Commercial use of any part of this repository is strictly prohibited without prior written permission from the authors.

The authors provide this software "as is" without warranty of any kind.

For commercial licensing inquiries, please contact the corresponding author.
