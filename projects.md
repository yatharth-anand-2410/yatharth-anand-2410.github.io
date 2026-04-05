---
layout: page
title: "Research Projects"
permalink: /projects/
---

A collection of my experiments in Mechanistic Interpretability, LLM optimization, and decoding strategies. 

---

## 🔬 Llama 3 MLX Research Lab
Deconstructing Llama 3 on Apple Silicon. This lab focuses on how weights respond to corruption and how the model's internal layers are structured.
- **Key Discovery**: Identified the "Tipping Point" (~1M shift) in 4-bit quantized weights where bit-level borrow propagation causes catastrophic failure.
- **Tools**: MLX, Llama 3, Python.
- **[View on GitHub](https://github.com/yatharth-anand-2410/llama3-mlx-research-lab)**

## 🧠 LLM Decoding Strategies
If a model's weights are "wobbly" or corrupted, can smart decoding rescue it? I tested Greedy vs. Top-P vs. Contrastive Search.
- **Key Discovery**: Contrastive Search is superior for creative coherence because it penalizes semantic redundancy in the hidden state.
- **Tools**: MLX, NumPy.
- **[View on GitHub](https://github.com/yatharth-anand-2410/llm-decoding-strategies)**

## 🔦 Mechanistic Interpretability Lab
Finding functional redundancy in Llama 3. We discovered that for shallow tasks (facts), **60% of the model is mathematically optional.**
- **Key Discovery**: The "Middle Void" Theory—removing Layers 3 through 21 and maintaining factual recall.
- **Tools**: Logit Lens, Cosine Similarity, MLX.
- **[View on GitHub](https://github.com/yatharth-anand-2410/llm-mechanistic-interpretability)**

---

## 🛠️ Upcoming Research
- **KV Cache Manipulation**: Pruning and prompt caching for infinite generation.
- **DPO Optimization**: Direct Preference Optimization for alignment on Apple Silicon.
- **RoPE Visualization**: Mapping how positional embeddings rotate across layers.
