# Web World Models

[![arXiv](https://img.shields.io/badge/arXiv-2512.23676-b31b1b.svg)](https://arxiv.org/abs/2512.23676) 
[![Website](https://img.shields.io/badge/Project-Website-blue)](https://princeton-ai2-lab.github.io/Web-World-Models) 
[![License: CC-BY](https://img.shields.io/badge/License-CC_BY_4.0-yellow.svg)](https://creativecommons.org/licenses/by/4.0) 

We introduce the **Web World Model (WWM)**, a middle ground where world state and physics are implemented in web code to ensure logical consistency, while large language models generate context, narratives, and high-level decisions on top of this structured latent state.

**Authors**: Jichen Feng*, Yifan Zhang*, Chenggong Zhang, Yifu Lu, Shilong Liu, Mengdi Wang 

[[Webpage](https://princeton-ai2-lab.github.io/Web-World-Models)] [[Huggingface](https://huggingface.co/papers/2512.23676)] 

## Abstract

Language agents increasingly require persistent worlds in which they can act, remember, and learn. Existing approaches sit at two extremes: conventional web frameworks provide reliable but fixed contexts backed by databases, while fully generative world models aim for unlimited environments, but the world is constructed primarily through generation, making it harder to maintain a fixed, deterministic global framework, reducing controllability.
In this work, we introduce the **Web World Model (WWM)**, a middle ground where world state and physics are implemented in web code to ensure logical consistency, while large language models generate context, narratives, and high-level decisions on top of this structured latent state. We build a suite of WWMs on a realistic web stack, including an infinite travel atlas grounded in real geography, fictional galaxy explorers, web-scale encyclopedic and narrative worlds, and simulation- and game-like environments. Across these systems, we identify practical design principles for WWMs: separating code-defined rules from model-driven imagination, representing latent state as typed web interfaces, and utilizing deterministic generation to achieve unlimited but structured exploration. Our results suggest that web stacks themselves can serve as a scalable substrate for world models, enabling controllable yet open-ended environments.

## Citation

```bibtex
@article{feng2025web,
   title   = {Web World Models},
   author    = {Feng, Jichen and Zhang, Chenggong and Zhang, Yifan and Lu, Yifu and Liu, Shilong and Wang, Mengdi},
   journal = {arXiv preprint arXiv:2512.23676},
   year    = {2025}
}
```
