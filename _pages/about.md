---
layout: about
title: about
permalink: /
subtitle:

profile:
  align: right
  image: prof_pic.jpeg
  image_circular: false # crops the image to make it circular
  more_info: Bengaluru, Karnataka, India 560078.

selected_papers: false # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: true
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

My work is driven by a core philosophy: true progress in AI requires moving beyond "black box" models and building systems from **first principles**. I focus on meticulous engineering and the scientific principle of reproducibility to gain a deep, functional understanding of the mechanics that govern machine learning.

My projects are demonstrations of this philosophy in action:

*   **Reproducibility and Analysis:** I performed a complete, clean-room replication of the **Sharpness-Aware Minimization (SAM)** optimizer (ICLR 2021). By building the algorithm solely from the paper's description, I successfully reproduced its CIFAR-10 results, validating its performance and the importance of scientific rigor.
    *   **[View the Project Analysis & Code →](httpd://github.com/S-Sairam/sam-optimizer)**

*   **First-Principles Engineering:** To master the mechanics of deep learning, I engineered a complete, **reverse-mode automatic differentiation engine** in Python from the ground up. I then built and trained a neural network using only this custom framework, demonstrating a ground-up understanding of gradient-based learning.
    *   **[Explore the Autodiff Engine →](https://github.com/S-Sairam/micrograd)**

### **Current Research & Future Direction**

Leveraging this foundational experience, I am now focused on the theory and practice of advanced optimization. My current project is the development of **Artemis**, a novel optimizer designed to unify the geometric insights of methods like SAM with the principled uncertainty of Bayesian inference.
