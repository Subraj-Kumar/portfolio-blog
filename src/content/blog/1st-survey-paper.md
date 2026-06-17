---
title: "How Deep Learning Changed Medical Image Analysis"
description: "Reviewing Geert Litjens' influential survey paper and exploring the paradigm shift from handcrafted features to Explainable AI in healthcare."
pubDate: 2026-06-27
readingTime: "4 min read"
tags:
  [
    "Explainable AI",
    "Computer Vision",
    "Medical Imaging",
    "Deep Learning",
    "Paper Review",
  ]
draft: false
---

While diving into the research phase for our B.Tech Minor Project on Medical Image Analysis with Explainable AI, I spent some time reading one of the most influential survey papers in the field: _A Survey on Deep Learning in Medical Image Analysis_ by Geert Litjens et al.

What fascinated me most wasn't a specific model or a benchmark result. It was seeing how an entire field transformed within just a few years.

### The Paradigm Shift: From Handcrafted to Learned Features

Before deep learning, medical image analysis followed a fairly predictable pipeline. Researchers manually designed image features, selected what they believed were important patterns, and then trained traditional machine learning algorithms on those handcrafted representations. Success depended heavily on deep domain expertise and meticulous feature engineering.

Deep learning changed that core assumption.

Instead of asking researchers to define useful features, neural networks began learning those representations directly from the data. **Convolutional Neural Networks (CNNs)** became particularly effective because they could automatically discover low-level patterns—such as edges and textures—before gradually building higher-level, complex medical concepts.

The survey highlights how quickly CNNs spread across medical imaging tasks. Applications ranged from disease classification in MRI and CT scans to lesion detection, organ segmentation, image registration, and even image reconstruction. What stood out to me was that deep learning was not just solving a single problem; it was becoming a universal framework for solving entirely different categories of problems.

### The Legacy of U-Net

One architecture mentioned throughout the survey deserves special attention: **U-Net**.

U-Net introduced an elegant encoder-decoder design that allowed models to understand both global context and fine-grained, localized details. Even years after its introduction, U-Net remains one of the most widely used architectures in medical image segmentation. Many of the modern segmentation models we study today can trace their foundational design principles right back to it.

### Lingering Challenges in the Domain

Despite the massive leaps forward, the paper also outlines several structural challenges that still exist today:

- **Data Scarcity:** Medical datasets are often small because annotations require the time and expertise of specialized radiologists or clinicians.
- **Class Imbalance:** Many imaging problems suffer from severe class imbalance, where the abnormal or pathological regions occupy only a tiny fraction of the overall image.
- **Computational Cost:** Medical scans are frequently three-dimensional (volumetric), making computation significantly more expensive than standard 2D computer vision tasks.

### The Evolution Towards Explainability

Reading this 2017 survey made me realize just how much the conversation has evolved since its publication. At that time, much of the focus was purely on improving absolute accuracy and surpassing traditional baselines. Today, researchers are increasingly asking fundamentally different questions:

> - Can we actually trust the model's prediction?
> - Can we explain _why_ a specific diagnosis was made?
> - Will the model generalize safely across different hospitals and imaging devices?
> - How can clinicians interact with AI systems confidently?

These questions directly connect with my team's current work in **Explainable AI (XAI)**. A model that achieves high accuracy is incredibly valuable, but in high-stakes healthcare environments, understanding _why_ a prediction was made is often just as important as the prediction itself.

The biggest takeaway from this paper is that deep learning fundamentally changed medical image analysis by eliminating the dependency on handcrafted feature engineering. However, the next monumental stage of progress will likely come from making these systems more transparent, reliable, and clinically interpretable.

That shift—from building merely _accurate_ models to building _trustworthy_ models—is what I find most exciting about the future of medical AI.
