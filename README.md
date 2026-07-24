# DINO-Minimal-From-Scratch

A minimal implementation of **DINO (Self-Distillation with No Labels)** from scratch using **PyTorch**.

This project was built to understand the fundamental ideas behind DINO by implementing its core architecture from scratch instead of relying on existing libraries. The goal is educational: to understand how a Vision Transformer, a student-teacher framework, exponential moving average (EMA) updates, and the DINO loss work together to learn visual representations without labels.

> **Note:** This repository is **not** a complete reproduction of the original DINO paper. It is a minimal implementation designed to build intuition before implementing the complete research paper.

---

# Project Motivation

Reproducing research papers requires understanding both the high-level ideas and the implementation details. Instead of directly reproducing the original DINO paper, this project focuses on implementing the essential building blocks from scratch.

The objective is to understand:

- Vision Transformer (ViT)
- Patch Embedding
- Positional Embeddings
- CLS Token
- Transformer Encoder
- DINO Projection Head
- Student–Teacher Architecture
- Exponential Moving Average (EMA) Teacher Update
- DINO Self-Supervised Loss

This implementation serves as the foundation for a future full reproduction of the DINO paper.

---

# Implemented Components

✔ Patch Embedding

✔ Vision Transformer Backbone

✔ Learnable CLS Token

✔ Learnable Positional Embeddings

✔ Multi-Head Self Attention

✔ Transformer Encoder Blocks

✔ DINO Projection Head

✔ Student Network

✔ Teacher Network

✔ EMA Teacher Update

✔ DINO Loss

✔ CIFAR-10 Training Pipeline

✔ Model Checkpoint Saving

✔ Training Loss Visualization

---

# Project Structure

```
DINO-Minimal-From-Scratch/

├── dino_minimal.ipynb
├── README.md
├── requirements.txt
├── LICENSE
├── training_loss.png
├── training_loss.csv
├── student_dino_minimal.pth
└── teacher_dino_minimal.pth
```

---

# Model Pipeline

```
Input Image
      │
      ▼
Patch Embedding
      │
      ▼
CLS Token + Positional Embeddings
      │
      ▼
Vision Transformer
      │
      ▼
CLS Representation
      │
      ▼
DINO Projection Head
      │
      ├──────────────┐
      ▼              ▼
Student         Teacher
      │              │
      └──────┬───────┘
             ▼
        DINO Loss
             │
             ▼
Student Update

Teacher ← EMA(Student)
```

---

# Training Configuration

Dataset

- CIFAR-10

Image Size

- 224 × 224

Optimizer

- Adam

Loss Function

- DINO Loss

Framework

- PyTorch

---

# Results

The training loss consistently decreases during training, indicating that the student network successfully learns to match the teacher representations under the simplified DINO objective.

Training artifacts included in this repository:

- training_loss.png
- training_loss.csv
- student_dino_minimal.pth
- teacher_dino_minimal.pth

---

# What is Missing?

The original DINO paper contains several additional components that are **not implemented** in this repository.

These include:

- Multi-Crop Augmentation
- Teacher Centering
- Teacher Temperature Scheduling
- AdamW Optimizer
- Cosine Learning Rate Scheduler
- Weight Decay Scheduling
- Mixed Precision Training
- Linear Evaluation Protocol
- k-NN Evaluation
- Full ImageNet Training Pipeline

Therefore, this repository should be viewed as a **minimal educational implementation**, not a faithful reproduction of the research paper.

---

# Future Work

The next stage of this project is to build a **complete reproduction of the DINO paper** by progressively adding the missing research components, including:

- Multi-Crop Strategy
- Centering Mechanism
- Temperature Scheduling
- AdamW Optimization
- Cosine Learning Rate Scheduling
- Linear Evaluation
- ImageNet Pretraining
- Paper-level Training Configuration

---

# Learning Outcomes

Through this implementation, the following concepts were explored:

- Vision Transformers from scratch
- Self-Supervised Learning
- Representation Learning
- Knowledge Distillation
- Student–Teacher Training
- Exponential Moving Average Updates
- Contrastive-style Self-Distillation Objectives
- End-to-End Training in PyTorch

---

# Reference

**DINO: Emerging Properties in Self-Supervised Vision Transformers**

Mathilde Caron, Hugo Touvron, Ishan Misra, Hervé Jégou, Julien Mairal, Piotr Bojanowski, Armand Joulin

https://arxiv.org/abs/2104.14294

---

# License

This project is released under the MIT License.