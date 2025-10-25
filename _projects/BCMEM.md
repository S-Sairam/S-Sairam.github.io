---
layout: page
title: BCMEM
description: Architectural Regularization via Number-Theoretic Priors
img: /assets/img/bcmem_banner.png # Suggestion: Create a visually appealing banner image from your 3D plot
importance: 1
category: Research
related_publications: sairam2025bhargava 
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bhargava_cube_3d_visualization.png" title="Emergent Structure in Latent Space" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1:</b> The 3D latent space learned by BCMEM on the MNIST test set. The model, guided only by our novel algebraic regularizer, autonomously learns to organize its internal "mind" into a highly structured manifold where each digit class occupies a distinct, well-separated cluster.
</div>

### **Core Research Question**

Can we move beyond standard statistical regularization and build AI systems that are robust *by design*? This project was a first-principles investigation into whether deep, abstract mathematical structures could be forged into a new class of **architectural regularizers** to force neural networks to learn more stable and interpretable representations of the world.

---

### **Methodology: An Inductive Bias from Abstract Algebra**

Instead of relying on common techniques, we designed a novel, end-to-end differentiable framework that uses principles from algebraic number theory—specifically, the **Gauss composition laws as generalized by Bhargava cubes**—as its primary inductive bias.

The core of the `BCMEM` model is an auxiliary loss function that penalizes the system for producing mathematically inconsistent or chaotic internal representations. This is not just a constraint; it is a fundamental piece of the architecture, designed to guide the optimizer towards finding solutions in a more **principled and structured region of the loss landscape.** This approach is a direct exploration into achieving stability not by changing the training algorithm, but by **fundamentally constraining the hypothesis space of the model itself.**

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/loss.png" title="Training and Validation Loss" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2:</b> The training and validation loss curves demonstrate stable convergence and excellent generalization, validating the compatibility of our algebraic loss with standard gradient-based optimization.
</div>

### **Conclusion & Strategic Relevance**

The experiment was a definitive success. The model achieved **99.46% accuracy** on MNIST, but the true victory was the emergence of a beautifully ordered latent space, proving that architectural regularization via first principles is a powerful and viable path toward building more reliable AI.

This work, which has been **accepted for publication at the International Conference on Applied Algorithms (ICAA 2026)** and will be published by **Springer in their Lecture Notes in Computer Science,** served as a crucial proof of concept. It has provided the foundational insights and the intellectual momentum for our current, more ambitious research campaigns in Causal-NeuroSymbolic AI.

---
