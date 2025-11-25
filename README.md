# 🌈 Interpretable and Fair Spectral–Spatial Disentangled Representation Learning with Learnable Hierarchical Superpixel Guidance for Hyperspectral Analysis
# The code will be open-sourced after the article is accepted.
## 🌐 Overview
This repository presents **LHSFormer**, a Learnable Hierarchical Superpixel-guided Dual-Attention Transformer that achieves end-to-end spectral–spatial disentanglement.
Specifically, a 3D convolutional stem first extracts joint spectral–spatial embeddings, while a learnable hierarchical superpixel (LHS) module adaptively clusters pixels into multi-scale, differentiable superpixels.
These superpixels guide a dual-branch Transformer encoder, which decouples spectral and spatial dependencies via two complementary attention mechanisms.
A gate-controlled fusion unit is then introduced to adaptively balance spectral and spatial cues, enabling fine-grained boundary preservation and context enhancement.

By integrating a **learnable hierarchical superpixel module** and a **dual-attention disentanglement Transformer**, LHSFormer achieves transparent and robust feature extraction—bridging **fairness, explainability, and high-dimensional spectral understanding**.

---

## 🚀 Key Features

- **🧩 Dual-Stream Disentangled Transformer**  
  Visible and non-visible (spectral/NIR/HSI) modalities are processed by two separate Transformer encoders, ensuring that modality-specific information is disentangled while enabling adaptive cross-modal fusion.

- **🌈 Learnable Superpixel Guidance**  
  Introduces a trainable, hierarchical superpixel generation module that adaptively segments spatial regions and guides the Transformer to learn structure-aware and interpretable spatial features.

- **⚖️ Fair and Group-Invariant Representation**  
  Employs fairness-aware regularization in the latent space to minimize subgroup bias and promote balanced decision-making across heterogeneous categories.

- **🔍 Transparent Spectral–Spatial Attribution**  
  Provides interpretable attention visualization and feature attribution maps, revealing how visible and spectral cues contribute to model predictions.

- **📈 Superior Generalization**  
  Demonstrates strong performance on multiple real-world hyperspectral datasets with improved robustness and interpretability.

---

## 🧠 Model Architecture
```text
Input Data 
 ├── Visible Stream (RGB Transformer Encoder)
 ├── Spectral Stream (HSI/NIR Transformer Encoder)
 └── Learnable Superpixel Module (Hierarchical, Multi-Scale)
        ↓
    Dual-Attention Fusion & Fairness Regularization
        ↓
    Classification / Reconstruction Head
Visible Stream: Transformer encoder for RGB or visible-spectrum imagery.

Spectral Stream: 1D/3D Transformer encoder for NIR or HSI data.

Superpixel Module: Learnable multi-scale segmentation that adaptively groups pixels by spectral–spatial similarity.

Fusion Layer: Dual-attention fusion mechanism to combine disentangled features.

Fairness Head: Regularizes latent representations to ensure group invariance and interpretability.
