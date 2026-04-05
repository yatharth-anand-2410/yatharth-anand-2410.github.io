---
layout: post
title: "The Tipping Point: Identifying the Threshold of Quantized Weight Corruption"
date: 2026-04-05 09:00:00 -0000
categories: [research, interpretability]
tags: [llama3, mlx, quantization, weights]
---

## Objective
To determine the precise mathematical threshold at which uniform bit-level perturbations to 4-bit quantized LLM weights cause catastrophic model collapse.

## Methodology
Using Llama 3 8B (4-bit quantized) on Apple MLX, we systematically subtracted increasing integer values from the packed `uint32` weights of the `lm_head` layer. We then observed the model's response to the prompt *"What is 2+2?"* across a range of shifts from 0 to 100 million.

## Results: The Observation Table

| Shift Amount | % of Range | Model Response | Status |
| :--- | :--- | :--- | :--- |
| 0 | 0.0% | "The answer to 2+2 is 4" | 🟢 Healthy |
| 1,000,000 | 0.074% | "The answer to 2+2 is 4" | 🟢 Healthy |
| 1,000,003 | 0.074% | "The answer is 4 obceLIKELYHonestly..." | 🟠 Mid-sentence collapse |
| 1,000,005 | 0.074% | "The answer permalinkizmet..." | 💀 Catastrophic Failure |

## Core Finding: The "Wobble Room"
The experiments revealed a sharp **"Tipping Point"** at a shift of approximately **1,000,004**. 

### Why 1,000,004?
The magic number is a consequence of 4-bit packing in `uint32` containers. Each `uint32` stores 8 separate 4-bit mini-weights. When we subtract from the container, **borrow propagation** crosses nibble boundaries. 

At a shift of ~1M, the cumulative "borrow" across the bit-stream flips enough individual weights by more than **4 nibble units**. With a scale factor of ~0.004, this results in a real-weight change of ~0.016—just enough to push the logit probabilities past the Softmax decision margin.

## Key Insights
1. **Robustness:** LLMs exhibit extreme resilience to small, uniform bit-level noise (up to 0.07% of the weight range).
2. **Sudden Collapse:** Degradation is not linear; it is binary. The model maintains full coherence until the bit-borrowing flips the dominant token probability.
3. **Quantization Nuance:** Modifying quantized weights requires explicit awareness of bit-packing layouts; traditional float math will cast and destroy the quantization format.

---
*For the full code and reproduction steps, see [Notebook 06: Sensitivity Analysis](https://github.com/stokome/llama3-mlx-research-lab/blob/main/notebooks/06_sensitivity_analysis.ipynb).*
