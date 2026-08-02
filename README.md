<div align="center">

# DF-DETR: Degradation-Aware Frequency-Enhanced DETR for End-to-End Underwater Object Detection

[![License](https://img.shields.io/badge/License-MIT-green.svg)]()
[![Last Commit](https://img.shields.io/badge/last%20commit-March%202026-yellowgreen)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-orange)]()


</div>

# Introduction

This repository presents **WM-DETR**, a robust underwater object detection framework that integrates **wavelet-based frequency decomposition**, state-space modeling (Mamba), and sparse adaptive interaction.Underwater detection is severely affected by light attenuation, scattering noise, color distortion, low contrast, and small objects. WM-DETR addresses these challenges by decomposing visual features into frequency sub-bands and modeling them using dual-branch state-space representations.Our framework improves detection robustness by suppressing background noise while preserving fine structural details, achieving strong performance on challenging underwater benchmarks.

![Alt Text](illustrates.png)
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
