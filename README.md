<div align="center">

# DF-DETR: Degradation-Aware Frequency-Enhanced DETR for End-to-End Underwater Object Detection

[![License](https://img.shields.io/badge/License-MIT-green.svg)]()
[![Last Commit](https://img.shields.io/github/last-commit/EUOD/DF-DETR?color=yellowgreen)](https://github.com/EUOD/DF-DETR/commits)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-orange.svg)](https://github.com/EUOD/DF-DETR/pulls)


</div>

# Introduction

This repository presents DF-DETR, a degradation-aware frequency-enhanced end-to-end underwater object detection framework built upon RT-DETR. Underwater object detection is severely affected by wavelength-dependent light attenuation, scattering noise, color distortion, nonuniform illumination, blurred boundaries, and small or low-contrast targets. DF-DETR addresses these challenges through a Degradation-Aware Frequency-Enhanced Hybrid Encoder (DFHE), which integrates two complementary modules: the Channel-Adaptive Spectral Module (CASM) and the Wavelet-Guided Degradation Purification module (WGDP). CASM performs adaptive Fourier-domain interaction across multiple backbone feature levels, enabling efficient global context modeling without introducing dense self-attention on high-resolution features. WGDP decomposes fused features into low- and high-frequency components, using stable low-frequency semantics to guide high-frequency purification.

![Alt Text](picture.png)
---

# Quick Start

## 1. Dataset Preparation

### Download Dataset
#### (1) DUO dataset (https://github.com/chongweiliu/DUO)
#### (2) UTDAC dataset (https://github.com/Ixiaohuihuihui/UTDAC)
#### (3) RUOD dataset (https://github.com/dlut-dimt/RUOD))

### Dataset Structure

Please download and organize the datasets with the following structure:

```text
datasets/
├── DUO/
│   ├── images/
│   │   ├── train/
│   │   └── val/
│   ├── labels/
│   │   ├── train/
│   │   └── val/
│   └── DUO.yaml
│
├── UTDAC/
│   ├── images/
│   │   ├── train/
│   │   └── val/
│   ├── labels/
│   │   ├── train/
│   │   └── val/
│   └── UTDAC.yaml
│
└── RUOD/
    ├── images/
    │   ├── train/
    │   └── val/
    ├── labels/
    │   ├── train/
    │   └── val/
    └── RUOD.yaml
```

### Configuration File

Use `datasets/data_RUOD.yaml` to configure the dataset path. An example is shown below:

```yaml
path: ./datasets/RUOD   # dataset root directory
train: images/train
val: images/val
nc: 10                                   # number of classes
names: ['holothurian', 'boat', 'echinus', 'starfish', 'fish', 'corals', 'diver', 'cuttlefish', 'turtle', 'jellyfish']
```

## 2. Model Training

```bash
# Basic training command (using default configuration)
python ./train.py
```
## 3. Model Validation

```bash
# Basic training command (using default configuration)
python ./val.py
```
## 4. Model Detection

```bash
# Basic training command (using default configuration)
python ./detect.py
```
