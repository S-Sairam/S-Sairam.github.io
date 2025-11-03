---
layout: post
title: "Why Reproducibility is the Ultimate Teacher: A Clean-Room SAM Replication"
date: 2025-11-03
description: A deep dive into scientific validation, deconstructing the ICLR 2021 SAM optimizer from first principles by analyzing the raw training process.
tags:
- Reproducibility
- Optimization
- Scientific Rigor
- Deep Learning
- Undergraduate Research
---

### The promise of deep learning is often ahead of our understanding. To bridge that gap, I believe in deconstruction.

A state-of-the-art paper presents an algorithm as a clean, two-page mathematical object. But its true character is only revealed in the chaotic, 200-epoch firefight of training. I chose the ICLR 2021 SAM paper not just to implement it, but to inhabit that space—to understand the core principles of sharpness and generalization from the ground up by watching them unfold.

My goal was a **clean-room replication**: to build the optimizer based solely on the paper's algorithmic description and force it to prove itself, with every step logged and publicly scrutinized. This transforms the exercise from mere implementation to genuine scientific validation.

### The Process and The Struggle: A Tale of Two Ascents

The logs tell a story of two distinct phases of learning. The initial ascent was a brute-force climb. The first epoch ended with a validation accuracy of just 53.17%, but the learning was explosive. In just 37 epochs, it had shattered the 90% accuracy barrier, a furious sprint through the easiest parts of the problem space.

But the real struggle, the part that defines research, was the second ascent: the long, grueling climb from 90% to the frontier of the problem. This wasn't a sprint; it was a siege. It took another **104 epochs** to crawl from 90.39% (Epoch 37) to break the 95% barrier (Epoch 141). This was a phase of meticulous, incremental refinement.

### The "Aha!" Moment: The Story in the Logs

The final `train_loss` was a near-perfect `0.0018`, but the true story was in the gap between training and validation. It became clear that SAM's job isn't to force `train_loss` to absolute zero, but to manage that gap. It's a **physical regularizer on the geometry of the solution space**, sacrificing training perfection for a robust, "flat" basin.

<d-figure style="width: 100% !important; max-width: 680px !important; margin: 2rem auto !important; display: block !important;">
  <img src="/assets/img/sam_wandb_graph.png"
       alt="W&B Plot showing the long, steady climb of validation accuracy for the SAM optimizer"
       style="width: 100% !important; height: auto !important; border-radius: 8px;">
  <figcaption>
    The story of the run, logged on Weights & Biases: validation accuracy's long, slow climb to its peak, mirroring the optimizer's search for a robust solution.
  </figcaption>
</d-figure>

The final result, a test accuracy of **96.74%**, successfully validated the paper's claims. But the real outcome was the hard-won intuition behind the numbers.

### The Forward Look: From Deconstruction to Architecture

This exercise in reproducibility wasn't an end in itself. It was training. The patience learned during that 104-epoch climb is the same patience required to develop a new idea. This deep dive is the direct foundation for my current work on **[Artemis, a novel optimizer]**, which seeks to unify these geometric insights with the principled uncertainty of Bayesian inference. Because to build the future, you must first be able to perfectly, and patiently, rebuild the present.

[View the Code on GitHub](https://github.com/S-Sairam/sam-optimizer)

[See the Full, Unabridged Training Logs on W&B](https://wandb.ai/pesu-ai-ml/sam-replication-cifar10/runs/mjyz5xy4)
