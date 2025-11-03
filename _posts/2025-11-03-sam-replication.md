---
layout: post
title: "Science, Not Sorcery: A First-Principles Replication of Sharpness-Aware Minimization"
date: 2025-11-03
description: An independent study in scientific reproducibility, rebuilding the ICLR 2021 SAM optimizer from scratch to validate its claims and understand its mechanics.
tags:
- Reproducibility
- Deep Learning
- Optimization
- Scientific Rigor
- Undergraduate Research
---

### What separates a good model from a *robust* one?

In deep learning, it's easy to achieve high accuracy on a training set. It's far harder to build a model that generalizes reliably to the unseen chaos of the real world. Many state-of-the-art models are brittle, their success tied to a "sharp" minimum in the loss landscape—a narrow ravine that is easy to fall out of.

The ICLR 2021 paper on **Sharpness-Aware Minimization (SAM)** proposed an elegant solution: force the optimizer to find not just a low point, but a wide, flat valley, making the model inherently more robust.

This claim was powerful, and it led me to a critical question: could I, as an independent researcher with nothing but the paper itself, rebuild this complex system from scratch and verify its results? This project wasn't about inventing a new method, but about engaging in a core, often-neglected, scientific practice: **rigorous replication.**

The goal was to perform a complete, clean-room implementation. Using only the paper's algorithmic description, I engineered a PyTorch optimizer from first principles. It follows the paper's two-step process: first, an adversarial ascent to find a point of higher loss, followed by a descent using the gradient from that perturbed position.

The experiment was a success, reproducing the paper's benchmark on CIFAR-10 with a Wide-ResNet-28-10.

| Experiment | Reported Test Accuracy (%) |
| :--- | :---: |
| **SAM (Foret et al., ICLR 2021)** | **~97.3** |
| **This First-Principles Replication** | **~96.74** |

![W&B Logs](/assets/img/train_loss.png) 
*The full training run, publicly logged on Weights & Biases, shows stable convergence to the final high-accuracy state.*

The final accuracy of **96.74%** is within **0.56%** of the original paper—a strong validation of the algorithm's claims and the correctness of my implementation.

### The Real Lesson: Research is More Than the Algorithm

The most valuable outcome of this project was not the final accuracy number, but the insight gained from the tiny gap between my result and the paper's. A clean, two-page algorithm in a paper belies the complex reality of its implementation. That 0.56% difference is a lesson in the hidden variables of deep learning research: minuscule differences in data augmentation pipelines, random seeds, software versions, or even GPU hardware can create subtle but measurable shifts in outcomes.

This study taught me that true understanding of a research paper comes not from reading it, but from building it. It is in the building that you discover the unwritten details and develop an intuition for the system's sensitivities.

This commitment to deep, validated understanding is now the foundation of my current work. It directly motivates the development of **[Artemis, my novel optimizer]**, which combines the geometric insights I validated in SAM with principles of Bayesian uncertainty. This replication wasn't just an exercise; it was the necessary groundwork for building the next generation of robust and reliable optimizers.

[View the Code on GitHub](https://github.com/S-Sairam/sam-optimizer)

[See the Full, Transparent Training Logs on W&B](https://wandb.ai/pesu-ai-ml/sam-replication-cifar10/runs/mjyz5xy4)
