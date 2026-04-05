---
layout: home
title: "Yatharth Anand | AI Researcher"
---

# Hello, I'm Yatharth. 🚀

I am an **AI Engineer & Machine Learning Researcher** specializing in Large Language Model (LLM) internals, mechanistic interpretability, and low-level optimization. My work focuses on deconstructing the "black box" of neural networks to understand how they reason and where they break.

Currently, I'm deep-diving into **Llama 3** on **Apple Silicon** using the **MLX** framework.

---

## 🔬 Featured Projects

### [Llama 3 MLX Research Lab](https://github.com/yatharth-anand-2410/llama3-mlx-research-lab)
A dedicated lab for deconstructing Llama 3. Key discoveries include the "Tipping Point" of quantized weights and manual "brain surgery" on token embeddings.
* **Tech**: MLX, Python, Llama 3, Metal.

### [LLM Decoding Strategies](https://github.com/yatharth-anand-2410/llm-decoding-strategies)
Exploring how different sampling methods (Contrastive Search, Top-P, Min-P) can "rescue" models with physical weight corruption.
* **Tech**: MLX, NumPy, Logit Manipulation.

[View all projects &rarr;]({{ site.baseurl }}/projects)

---

## ✍️ Latest Blog Posts

<div class="posts-list">
  {% for post in site.posts limit:3 %}
    <div class="post-item" style="margin-bottom: 25px; border-left: 3px solid #007bff; padding-left: 15px;">
      <span class="post-date" style="color: #666; font-size: 0.9em;">{{ post.date | date: "%B %-d, %Y" }}</span>
      <h3 style="margin: 5px 0;"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p style="font-size: 0.95em; line-height: 1.5;">{{ post.excerpt | strip_html | truncatewords: 35 }}</p>
    </div>
  {% endfor %}
</div>

[Read the Blog &rarr;]({{ site.baseurl }}/blog)

---

## 🛠️ Toolkit
**Frameworks**: MLX, PyTorch, Transformers, JAX  
**Hardware**: Apple M-Series (Metal Performance Shaders)  
**Interests**: Mechanistic Interpretability, Quantization, KV-Cache Optimization, DPO.

---

<p align="center">
  <a href="https://github.com/yatharth-anand-2410">GitHub</a> • 
  <a href="https://twitter.com/yatharth_anand">Twitter</a> • 
  <a href="https://www.linkedin.com/in/yatharth-anand">LinkedIn</a>
</p>
