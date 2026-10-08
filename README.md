# 🤗 Awesome LLM Routing

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/your-username/Awesome-LLM-Routing/pulls)

> **Model Routing for Large Language Models: A Unified Taxonomy and Survey**  


A curated list of papers on **model routing for large language models (LLMs)**, organized by our proposed multi-dimensional taxonomy. This repo is the official companion to our survey. We warmly welcome contributions — please raise additions in the Issues section! 👏

---

## 💖 Citation

If you find this repo useful for your research, welcome to ⭐ this repo and cite our paper:

```bibtex
@article{llmrouting2026,
  title={Model Routing for Large Language Models: A Unified Taxonomy and Survey},
  author={Wang Wei, Tiankai Yang, Xiangbo Gao, Chan-Wei Hu, Reuben Luera, Runzhou Liu, Nigel Fernandez, Li Li, Lunyiu Nie, Bo Ni, Junda Wu, Chien Van Nguyen, Deonna Owens, Hongjie Chen, Seunghyun Yoon, Puneet Mathur, Tong Yu, Sungchul Kim, Koustava Goswami, Zichao Wang, Joe Barrow, Samyadeep Basu, Xiang Chen, Namyong Park, Nesreen K. Ahmed, Nedim Lipka, Thien Huu Nguyen, Ting-Hao Kenneth Huang, Franck Dernoncourt, Trung Bui, Ryan A. Rossi, Yue Zhao, Zhengzhong Tu, Hongru Du, Tyler Derr, Yu Wang, Hoda Eldardiry},
  year={2026}
}
```

---

## 📋 Contents

- [🗺️ Taxonomy Overview](#️-taxonomy-overview)
- [🎯 Routing by Objective](#-routing-by-objective)
  - [✅ Quality-driven Routing](#-quality-driven-routing)
  - [💰 Cost-aware Routing](#-cost-aware-routing)
  - [🛡️ Reliability-oriented Routing](#️-reliability-oriented-routing)
  - [⚖️ Multi-objective Routing](#️-multi-objective-routing)
- [📥 Routing by Input](#-routing-by-input)
  - [🔮 Pre-execution Routing](#-pre-execution-routing)
  - [⚙️ Intra-execution Routing](#️-intra-execution-routing)
  - [📤 Post-execution Routing](#-post-execution-routing)
- [🔬 Routing by Granularity](#-routing-by-granularity)
  - [📌 Instance-level Routing](#-instance-level-routing)
  - [🪜 Step-level Routing](#-step-level-routing)
  - [🔡 Token/Feature-level Routing](#-tokenfeature-level-routing)
- [🧠 Routing by Learning Regime](#-routing-by-learning-regime)
  - [📏 Heuristic / Rule-based](#-heuristic--rule-based)
  - [🏫 Supervised Routing](#-supervised-routing)
  - [🔄 Online / Adaptive Routing](#-online--adaptive-routing)
- [📊 Benchmarks & Datasets](#-benchmarks--datasets)
- [📖 Related Surveys](#-related-surveys)

---
## 🚀 Why LLM Routing Matters

Modern applications increasingly rely on *multiple* LLMs with different trade-offs in:
- quality
- cost
- latency
- safety

LLM routing aims to dynamically select the best model (or combination) per query.

However, routing is fundamentally challenging:
- Optimal routing requires oracle knowledge of model performance
- Learned routers often collapse to overusing strong models
- Cost-quality trade-offs are highly task-dependent

This repo organizes the design space of routing methods using the following taxonomy.


## 🗺️ Taxonomy Overview

Our survey organizes routing methods along **four orthogonal dimensions**:

| Dimension | Question Answered | Categories |
|---|---|---|
| **Objectives** | *Why* to route? | Quality, Cost, Reliability, Multi-objective |
| **Input** | *What* information is used? | Pre-execution, Intra-execution, Post-execution |
| **Granularity** | *At what level* does routing occur? | Instance, Step, Token/Feature |
| **Learning Regime** | *How* is the router learned? | Heuristic, Supervised, Online/Adaptive |

---

## 🎯 Routing by Objective

### ✅ Quality-driven Routing

Methods that maximize task performance by selecting the model most likely to produce the best answer.

- **Large Language Model Routing with Benchmark Datasets** (Sep 2023)  
  Tal Shnitzer, Anthony Ou, Mírian Silva, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2309.15789-b31b1b.svg)](https://arxiv.org/abs/2309.15789)

- **Model Spider: Learning to Rank Pre-trained Models Efficiently** (Jun 2023)  
  Yi-Kai Zhang, De-Chuan Zhan, Han-Jia Ye.  
  [![Paper](https://img.shields.io/badge/arXiv-2306.03900-b31b1b.svg)](https://arxiv.org/abs/2306.03900)

- **LLM-Blender: Ensembling Large Language Models with Pairwise Ranking and Generative Fusion** (Jun 2023)  
  Dongfu Jiang, Xiang Ren, Bill Yuchen Lin.  
  [![Paper](https://img.shields.io/badge/arXiv-2306.02561-b31b1b.svg)](https://arxiv.org/abs/2306.02561) [![Code](https://img.shields.io/github/stars/yuchenlin/LLM-Blender.svg?style=social&label=Star)](https://github.com/yuchenlin/LLM-Blender)

- **ZOOTER: Routing to the Expert — Efficient Reward-Guided Ensemble of LLMs** (NAACL 2024)  
  Keming Lu, Hongyi Yuan, Runji Lin, et al.  
  [![Paper](https://img.shields.io/badge/ACL_Anthology-2024.naacl--long.109-blue)](https://aclanthology.org/2024.naacl-long.109)

- **RouterDC: Query-Based Router by Dual Contrastive Learning for Assembling LLMs** (NeurIPS 2024)  
  Shuhao Chen, Weisen Jiang, Baijiong Lin, James T. Kwok, Yu Zhang.  
  [![Paper](https://img.shields.io/badge/arXiv-2409.19886-b31b1b.svg)](https://arxiv.org/abs/2409.19886) [![Code](https://img.shields.io/github/stars/shuhao02/RouterDC.svg?style=social&label=Star)](https://github.com/shuhao02/RouterDC)

- **EmbedLLM: Learning Compact Representations of Large Language Models** (ICLR 2025)  
  Richard Zhuang, Tianhao Wu, Zhaojin Wen, Andrew Li, Jiantao Jiao, Kannan Ramchandran.  
  [![Paper](https://img.shields.io/badge/arXiv-2410.02223-b31b1b.svg)](https://arxiv.org/abs/2410.02223) [![Code](https://img.shields.io/github/stars/richardzhuang0412/EmbedLLM.svg?style=social&label=Star)](https://github.com/richardzhuang0412/EmbedLLM)

- **SelectLLM: Query-Aware Efficient Selection Algorithm for Large Language Models** (ACL 2025 Findings)  
  Kaushal Kumar Maurya, Kv Aditya Srivatsa, Ekaterina Kochmar.  
  [![Paper](https://img.shields.io/badge/ACL_Anthology-2025.findings--acl.1072-blue)](https://aclanthology.org/2025.findings-acl.1072)

- **RAGRouter: Learning to Route Queries to Multiple Retrieval-Augmented Language Models** (May 2025)  
  Jiarui Zhang, Xiangyu Liu, Yong Hu, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2505.23052-b31b1b.svg)](https://arxiv.org/abs/2505.23052)

- **Capability Instruction Tuning** (AAAI 2025)  
  Yi-Kai Zhang, De-Chuan Zhan, Han-Jia Ye.  
  [![Paper](https://img.shields.io/badge/AAAI-2025-blue)](https://ojs.aaai.org/index.php/AAAI/article/view/34790)

- **IRT-Router: Effective and Interpretable Multi-LLM Routing via Item Response Theory** (ACL 2025)  
  Wei Song, Zhenya Huang, Cheng Cheng, et al.  
  [![Paper](https://img.shields.io/badge/ACL_Anthology-2025-blue)](https://aclanthology.org/2025.acl-long.840)

- **Pretrain Once, Route Anywhere: Towards a Foundation Model for LLM Routing** (Sep 2026)<br>
  Guannan Lai, Han-Jia Ye.<br>
  [![Paper](https://img.shields.io/badge/arXiv-2609.37362-b31b1b.svg)](https://arxiv.org/abs/2609.37362) [![Code](https://img.shields.io/github/stars/LAMDA-Model-Reuse/RouteFM.svg?style=social&label=Star)](https://github.com/LAMDA-Model-Reuse/RouteFM)

---

### 💰 Cost-aware Routing

Methods that optimize the trade-off between response quality and resource costs (money, tokens, latency, energy).

- **FrugalGPT: How to Use Large Language Models While Reducing Cost and Improving Performance** (TMLR 2024)  
  Lingjiao Chen, Matei Zaharia, James Zou.  
  [![Paper](https://img.shields.io/badge/arXiv-2305.05176-b31b1b.svg)](https://arxiv.org/abs/2305.05176)

- **Hybrid LLM: Cost-Efficient and Quality-Aware Query Routing** (ICLR 2024)  
  Dujian Ding, Ankur Mallick, Chi Wang, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2404.14618-b31b1b.svg)](https://arxiv.org/abs/2404.14618)

- **AutoMix: Automatically Mixing Language Models** (NeurIPS 2024)  
  Pranjal Aggarwal, Aman Madaan, Ankit Anand, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2310.12963-b31b1b.svg)](https://arxiv.org/abs/2310.12963)

- **RouteLLM: Learning to Route LLMs with Preference Data** (ICLR 2025)  
  Isaac Ong, Amjad Almahairi, Vincent Wu, Wei-Lin Chiang, Tianhao Wu, Joseph E. Gonzalez, M Waleed Kadous, Ion Stoica.  
  [![Paper](https://img.shields.io/badge/arXiv-2406.18665-b31b1b.svg)](https://arxiv.org/abs/2406.18665) [![Code](https://img.shields.io/github/stars/lm-sys/RouteLLM.svg?style=social&label=Star)](https://github.com/lm-sys/RouteLLM)

- **Eagle: Efficient Training-Free Router for Multi-LLM Inference** (Sep 2024)  
  Zesen Zhao, Shuowei Jin, Z. Morley Mao.  
  [![Paper](https://img.shields.io/badge/arXiv-2409.15518-b31b1b.svg)](https://arxiv.org/abs/2409.15518)

- **Leveraging Uncertainty Estimation for Efficient LLM Routing** (Feb 2025)  
  Tuo Zhang, Asal Mehradfar, Dimitrios Dimitriadis, Salman Avestimehr.  
  [![Paper](https://img.shields.io/badge/arXiv-2502.11021-b31b1b.svg)](https://arxiv.org/abs/2502.11021)

- **BEST-Route: Adaptive LLM Routing with Test-Time Optimal Compute** (ICML 2025)  
  Dujian Ding, Ankur Mallick, Shaokun Zhang, et al.  
  [![Paper](https://img.shields.io/badge/ICML-2025-blue)](https://proceedings.mlr.press/v267/ding25d.html)

- **CSCR: Cost-Aware Contrastive Routing for LLMs** (NeurIPS 2025)  
  Reza Shirkavand, Shangqian Gao, Peiran Yu, Heng Huang.  
  [![Paper](https://img.shields.io/badge/NeurIPS-2025-blue)](https://arxiv.org/abs/2502.XXXXX)

- **PROTEUS: SLA-Aware Routing via Lagrangian RL for Multi-LLM Serving Systems** (2026)  
  Amit Singh Bhatti, Vishal Vaddina, Dagnachew Birru.  
  [![Paper](https://img.shields.io/badge/arXiv-2601.19402-b31b1b.svg)](https://arxiv.org/abs/2601.19402)

- **RADAR: Reasoning-Ability and Difficulty-Aware Routing in Language Models** (ICLR 2026)  
  Nigel Fernandez, Branislav Kveton, Ryan A. Rossi, Andrew Lan, Zichao Wang.  
  [![Paper](https://img.shields.io/badge/ICLR-2026-blue)](https://arxiv.org/abs/XXXX.XXXXX)

- **R2-Router: A New Paradigm for LLM Routing with Reasoning** (2026)  
  Jiaqi Xue, Qian Lou, Jiarong Xing, Heng Huang.  
  [![Paper](https://img.shields.io/badge/arXiv-2602.02823-b31b1b.svg)](https://arxiv.org/abs/2602.02823)

- **EquiRouter: When Routing Collapses — On the Degenerate Convergence of LLM Routers** (2026)  
  Guannan Lai, Han-Jia Ye.  
  [![Paper](https://img.shields.io/badge/arXiv-2602.03478-b31b1b.svg)](https://arxiv.org/abs/2602.03478)

- **Routing Should Pay for Itself: Sparse Supervision for Economical LLM Routing** (Sep 2026)<br>
  Guannan Lai, Gelin Bian, Hao-Xuan Ma, et al.<br>
  [![Paper](https://img.shields.io/badge/arXiv-2609.37402-b31b1b.svg)](https://arxiv.org/abs/2609.37402) [![Code](https://img.shields.io/github/stars/LAMDA-Model-Reuse/SaveRouter.svg?style=social&label=Star)](https://github.com/LAMDA-Model-Reuse/SaveRouter)

---

### 🛡️ Reliability-oriented Routing

Methods that prioritize failure avoidance — reducing hallucinations, unsafe outputs, or invalid generations.

- **SafeRoute: Adaptive Model Selection for Efficient and Accurate Safety Guardrails in LLMs** (ACL 2025 Findings)  
  Seanie Lee, Dong Bok Lee, Dominik Wagner, et al.  
  [![Paper](https://img.shields.io/badge/ACL_Anthology-2025.findings--acl.105-blue)](https://aclanthology.org/2025.findings-acl.105)

- **Guarded Query Routing for Large Language Models** (2025)  
  Richard Šléher, William Brach, Tibor Sloboda, Kristián Košt'ál, Lukas Galke.  
  [![Paper](https://img.shields.io/badge/IOS_Press-2025-blue)](http://dx.doi.org/10.3233/FAIA251304)

- **MARVEL: Modular Abstention for Reliable and Versatile Expert LLMs** (ICML Workshop 2025)  
  Bingbing Wen, Faeze Brahman, Zhan Su, et al.  
  [![Paper](https://img.shields.io/badge/OpenReview-2025-blue)](https://openreview.net/forum?id=cVb6jJilvJ)

- **Self-REF / Learning to Route LLMs with Confidence Tokens** (ICML 2025)  
  Yu-Neng Chuang, Prathusha Kameswara Sarma, Parikshit Gopalan, et al.  
  [![Paper](https://img.shields.io/badge/ICML-2025-blue)](https://proceedings.mlr.press/v267/chuang25b.html)

- **RACER: Risk-Aware Calibrated Efficient Routing for Large Language Models** (2026)  
  Sai Hao, Hao Zeng, Hongxin Wei, Bingyi Jing.  
  [![Paper](https://img.shields.io/badge/arXiv-2603.06616-b31b1b.svg)](https://arxiv.org/abs/2603.06616)

- **From Sampled Outcomes to Capability Distributions: Rethinking Supervision for LLM Routing** (EMNLP 2026)<br>
  Guannan Lai, Haoran Hu, Long Chen, Zhenguo Li, Han-Jia Ye.<br>
  [![Paper](https://img.shields.io/badge/arXiv-2606.06924-b31b1b.svg)](https://arxiv.org/abs/2606.06924) [![Code](https://img.shields.io/github/stars/AIGNLAI/DARS.svg?style=social&label=Star)](https://github.com/AIGNLAI/DARS)

- **When LLM Routers Overpay: Strong-Model Over-Selection under Loose Budgets** (NeurIPS 2026)<br>
  Guannan Lai, Long Chen, Han-Jia Ye.<br>
  [![Paper](https://img.shields.io/badge/OpenReview-NeurIPS_2026-blue)](https://openreview.net/forum?id=v2DOrFK8Wp)

---

### ⚖️ Multi-objective Routing

Methods that explicitly model trade-offs among multiple objectives (quality, cost, latency, safety, user preference).

- **GraphRouter: A Graph-based Router for LLM Selections** (ICLR 2025)  
  Tao Feng, Yanzhen Shen, Jiaxuan You.  
  [![Paper](https://img.shields.io/badge/arXiv-2410.03834-b31b1b.svg)](https://arxiv.org/abs/2410.03834) [![Code](https://img.shields.io/github/stars/ulab-uiuc/GraphRouter.svg?style=social&label=Star)](https://github.com/ulab-uiuc/GraphRouter)

- **LLM Bandit: Cost-Efficient LLM Generation via Preference-Conditioned Dynamic Routing** (Feb 2025)  
  Yang Li.  
  [![Paper](https://img.shields.io/badge/arXiv-2502.02743-b31b1b.svg)](https://arxiv.org/abs/2502.02743)

- **BaRP: Learning to Route LLMs from Bandit Feedback — One Policy, Many Trade-offs** (Oct 2025)  
  Wang Wei, Tiankai Yang, Hongjie Chen, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2510.07429-b31b1b.svg)](https://arxiv.org/abs/2510.07429)

- **Router-R1: Teaching LLMs Multi-Round Routing and Aggregation via Reinforcement Learning** (NeurIPS 2025)  
  Haozhen Zhang, Tao Feng, Jiaxuan You.  
  [![Paper](https://img.shields.io/badge/OpenReview-NeurIPS_2025-blue)](https://openreview.net/forum?id=DWf4vroKWJ) [![Code](https://img.shields.io/github/stars/ulab-uiuc/Router-R1.svg?style=social&label=Star)](https://github.com/ulab-uiuc/Router-R1)
  
- **LLM Routing with Dueling Feedback** (Oct 2025)  
  Chao-Kai Chiang, Takashi Ishida, Masashi Sugiyama.  
  [![Paper](https://img.shields.io/badge/arXiv-2510.00841-b31b1b.svg)](https://arxiv.org/abs/2510.00841)

- **Lookahead Routing for Large Language Models** (NeurIPS 2025)  
  Canbin Huang, Tianyuan Shi, Yuhua Zhu, et al.  
  [![Paper](https://img.shields.io/badge/NeurIPS-2025-blue)](https://arxiv.org/abs/XXXX.XXXXX)

- **C2MAB-V: Cost-Effective Online Multi-LLM Selection with Versatile Reward Models** (2024)  
  Xiangxiang Dai, Jin Li, Xutong Liu, Anqi Yu, John C.S. Lui.  
  [![Paper](https://img.shields.io/badge/arXiv-2405.16587-b31b1b.svg)](https://arxiv.org/abs/2405.16587)

- **MixLLM: Dynamic Routing in Mixed Large Language Models** (Feb 2025)  
  Xinyuan Wang, Yanchi Liu, Wei Cheng, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2502.18482-b31b1b.svg)](https://arxiv.org/abs/2502.18482)

- **MetaLLM: A High-Performant and Cost-Efficient Dynamic Framework for Wrapping LLMs** (2025)  
  Quang H. Nguyen, Thinh Dao, Duy C. Hoang, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2407.10834-b31b1b.svg)](https://arxiv.org/abs/2407.10834)

- **PickLLM: Context-Aware RL-Assisted Large Language Model Routing** (2025)  
  Dimitrios Sikeridis, Dennis Ramdass, Pranay Pareek.  
  [![Paper](https://img.shields.io/badge/Springer-2025-blue)](https://doi.org/10.1007/978-981-96-8912-5_11)

- **BEST-Route: Adaptive LLM Routing with Test-Time Optimal Compute** (ICML 2025)  
  Dujian Ding, Ankur Mallick, Shaokun Zhang, et al.  
  [![Paper](https://img.shields.io/badge/ICML-2025-blue)](https://proceedings.mlr.press/v267/ding25d.html)

---

## 📥 Routing by Input

### 🔮 Pre-execution Routing

Routing decisions made using only the raw input or lightweight features, before any model runs.

- **Large Language Model Routing with Benchmark Datasets** (Sep 2023)  
  Tal Shnitzer et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2309.15789-b31b1b.svg)](https://arxiv.org/abs/2309.15789)

- **RouteLLM: Learning to Route LLMs with Preference Data** (ICLR 2025)  
  Isaac Ong et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2406.18665-b31b1b.svg)](https://arxiv.org/abs/2406.18665) [![Code](https://img.shields.io/github/stars/lm-sys/RouteLLM.svg?style=social&label=Star)](https://github.com/lm-sys/RouteLLM)

- **Hybrid LLM: Cost-Efficient and Quality-Aware Query Routing** (ICLR 2024)  
  Dujian Ding et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2404.14618-b31b1b.svg)](https://arxiv.org/abs/2404.14618)

- **RouterDC: Query-Based Router by Dual Contrastive Learning** (NeurIPS 2024)  
  Shuhao Chen et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2409.19886-b31b1b.svg)](https://arxiv.org/abs/2409.19886) [![Code](https://img.shields.io/github/stars/shuhao02/RouterDC.svg?style=social&label=Star)](https://github.com/shuhao02/RouterDC)

- **EmbedLLM: Learning Compact Representations of LLMs** (ICLR 2025 Spotlight)  
  Richard Zhuang et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2410.02223-b31b1b.svg)](https://arxiv.org/abs/2410.02223) [![Code](https://img.shields.io/github/stars/richardzhuang0412/EmbedLLM.svg?style=social&label=Star)](https://github.com/richardzhuang0412/EmbedLLM)

- **SelectLLM: Query-Aware Efficient Selection Algorithm for LLMs** (ACL 2025 Findings)  
  Kaushal Kumar Maurya et al.  
  [![Paper](https://img.shields.io/badge/ACL_Anthology-2025.findings--acl.1072-blue)](https://aclanthology.org/2025.findings-acl.1072)

- **BEST-Route: Adaptive LLM Routing with Test-Time Optimal Compute** (ICML 2025)  
  Dujian Ding et al.  
  [![Paper](https://img.shields.io/badge/ICML-2025-blue)](https://proceedings.mlr.press/v267/ding25d.html)

- **IRT-Router: Effective and Interpretable Multi-LLM Routing via Item Response Theory** (ACL 2025)  
  Wei Song et al.  
  [![Paper](https://img.shields.io/badge/ACL_Anthology-2025-blue)](https://aclanthology.org/2025.acl-long.840)

- **BaRP: Learning to Route from Bandit Feedback — One Policy, Many Trade-offs** (2025)  
  Wang Wei et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2510.07429-b31b1b.svg)](https://arxiv.org/abs/2510.07429)

- **GraphRouter: A Graph-based Router for LLM Selections** (ICLR 2025)  
  Tao Feng, Yanzhen Shen, Jiaxuan You.  
  [![Paper](https://img.shields.io/badge/arXiv-2410.03834-b31b1b.svg)](https://arxiv.org/abs/2410.03834) [![Code](https://img.shields.io/github/stars/ulab-uiuc/GraphRouter.svg?style=social&label=Star)](https://github.com/ulab-uiuc/GraphRouter)

- **SafeRoute: Adaptive Model Selection for Safety Guardrails** (ACL 2025 Findings)  
  Seanie Lee et al.  
  [![Paper](https://img.shields.io/badge/ACL_Anthology-2025.findings--acl.105-blue)](https://aclanthology.org/2025.findings-acl.105)

- **Guarded Query Routing for LLMs** (2025)  
  Richard Šléher et al.  
  [![Paper](https://img.shields.io/badge/IOS_Press-2025-blue)](http://dx.doi.org/10.3233/FAIA251304)

---

### ⚙️ Intra-execution Routing

Routing uses intermediate signals from partial model execution (logits, hidden states, uncertainty).

- **Learning to Route LLMs with Confidence Tokens** (ICML 2025)  
  Yu-Neng Chuang, Prathusha Kameswara Sarma, Parikshit Gopalan, et al.  
  [![Paper](https://img.shields.io/badge/ICML-2025-blue)](https://proceedings.mlr.press/v267/chuang25b.html)

- **Leveraging Uncertainty Estimation for Efficient LLM Routing** (Feb 2025)  
  Tuo Zhang, Asal Mehradfar, Dimitrios Dimitriadis, Salman Avestimehr.  
  [![Paper](https://img.shields.io/badge/arXiv-2502.11021-b31b1b.svg)](https://arxiv.org/abs/2502.11021)

- **Lookahead Routing for Large Language Models** (NeurIPS 2025)  
  Canbin Huang, Tianyuan Shi, Yuhua Zhu, et al.  
  [![Paper](https://img.shields.io/badge/NeurIPS-2025-blue)](https://arxiv.org/abs/XXXX.XXXXX)

---

### 📤 Post-execution Routing

Routing decisions conditioned on full or partial outputs, self-critique, or verification signals.

- **FrugalGPT: How to Use LLMs While Reducing Cost and Improving Performance** (TMLR 2024)  
  Lingjiao Chen, Matei Zaharia, James Zou.  
  [![Paper](https://img.shields.io/badge/arXiv-2305.05176-b31b1b.svg)](https://arxiv.org/abs/2305.05176)

- **AutoMix: Automatically Mixing Language Models** (NeurIPS 2024)  
  Pranjal Aggarwal, Aman Madaan, Ankit Anand, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2310.12963-b31b1b.svg)](https://arxiv.org/abs/2310.12963)

- **A Unified Approach to Routing and Cascading for LLMs** (Oct 2024)  
  Jasper Dekoninck, Maximilian Baader, Martin Vechev.  
  [![Paper](https://img.shields.io/badge/arXiv-2410.10347-b31b1b.svg)](https://arxiv.org/abs/2410.10347)

- **Large Language Model Cascades with Mixture of Thought Representations** (ICLR 2024)  
  Murong Yue, Jie Zhao, Min Zhang, Liang Du, Ziyu Yao.  
  [![Paper](https://img.shields.io/badge/arXiv-2310.03094-b31b1b.svg)](https://arxiv.org/abs/2310.03094)

- **Router-R1: Teaching LLMs Multi-Round Routing and Aggregation via RL** (NeurIPS 2025)  
  Haozhen Zhang, Tao Feng, Jiaxuan You.  
  [![Paper](https://img.shields.io/badge/OpenReview-NeurIPS_2025-blue)](https://openreview.net/forum?id=DWf4vroKWJ) [![Code](https://img.shields.io/github/stars/ulab-uiuc/Router-R1.svg?style=social&label=Star)](https://github.com/ulab-uiuc/Router-R1)

- **LLM-Blender: Ensembling LLMs with Pairwise Ranking and Generative Fusion** (Jun 2023)  
  Dongfu Jiang, Xiang Ren, Bill Yuchen Lin.  
  [![Paper](https://img.shields.io/badge/arXiv-2306.02561-b31b1b.svg)](https://arxiv.org/abs/2306.02561) [![Code](https://img.shields.io/github/stars/yuchenlin/LLM-Blender.svg?style=social&label=Star)](https://github.com/yuchenlin/LLM-Blender)

- **Self-Consistency Improves Chain of Thought Reasoning in Language Models** (ICLR 2023)  
  Xuezhi Wang, Jason Wei, Dale Schuurmans, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2203.11171-b31b1b.svg)](https://arxiv.org/abs/2203.11171)

- **The Avengers: A Simple Recipe for Uniting Smaller Language Models** (May 2025)  
  Yiqun Zhang, Hao Li, Chenxu Wang, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2505.19797-b31b1b.svg)](https://arxiv.org/abs/2505.19797)

---

## 🔬 Routing by Granularity

### 📌 Instance-level Routing

A one-shot decision per input — a single model (or model set) is selected without reassignment during execution.

- **RouteLLM** · **RouterDC** · **EmbedLLM** · **HybridLLM** · **SelectLLM** · **BEST-Route** · **BaRP** · **IRT-Router** · **GraphRouter** · **SafeRoute** · **RADAR** · **EquiRouter** · **PROTEUS** · **R2-Router** · **RACER**  
  *(See respective entries above for full details.)*

---

### 🪜 Step-level Routing

Models are assigned to different subtasks or reasoning steps within a single task.

- **Router-R1: Teaching LLMs Multi-Round Routing and Aggregation via RL** (NeurIPS 2025)  
  Haozhen Zhang, Tao Feng, Jiaxuan You.  
  [![Paper](https://img.shields.io/badge/OpenReview-NeurIPS_2025-blue)](https://openreview.net/forum?id=DWf4vroKWJ) [![Code](https://img.shields.io/github/stars/ulab-uiuc/Router-R1.svg?style=social&label=Star)](https://github.com/ulab-uiuc/Router-R1)

- **TRIM: Hybrid Inference via Targeted Stepwise Routing in Multi-Step Reasoning** (2026)  
  Vansh Kapoor, Aman Gupta, Hao Chen, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2601.10245-b31b1b.svg)](https://arxiv.org/abs/2601.10245)

- **Route-and-Reason: Scaling LLM Reasoning with Reinforced Model Router** (Jun 2025)  
  Chenyang Shao, Xinyang Liu, Yutang Lin, Fengli Xu, Yong Li.  
  [![Paper](https://img.shields.io/badge/arXiv-2506.05901-b31b1b.svg)](https://arxiv.org/abs/2506.05901)

- **AutoMix: Automatically Mixing Language Models** (NeurIPS 2024)  
  Pranjal Aggarwal et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2310.12963-b31b1b.svg)](https://arxiv.org/abs/2310.12963)

- **A Unified Approach to Routing and Cascading for LLMs** (2024)  
  Jasper Dekoninck, Maximilian Baader, Martin Vechev.  
  [![Paper](https://img.shields.io/badge/arXiv-2410.10347-b31b1b.svg)](https://arxiv.org/abs/2410.10347)

---

### 🔡 Token/Feature-level Routing

Fine-grained routing inside a model — across tokens, layers, or expert sub-networks (MoE).

- **Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer** (ICLR 2017)  
  Noam Shazeer, Azalia Mirhoseini, Krzysztof Maziarz, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-1701.06538-b31b1b.svg)](https://arxiv.org/abs/1701.06538)

- **Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity** (JMLR 2022)  
  William Fedus, Barret Zoph, Noam Shazeer.  
  [![Paper](https://img.shields.io/badge/JMLR-2022-blue)](https://arxiv.org/abs/2101.03961)

- **GLaM: Efficient Scaling of Language Models with Mixture-of-Experts** (ICML 2022)  
  Nan Du, Yanping Huang, Andrew M Dai, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2112.06905-b31b1b.svg)](https://arxiv.org/abs/2112.06905)

- **BASE Layers: Simplifying Training of Large, Sparse Models** (ICML 2021)  
  Mike Lewis, Shruti Bhosale, Tim Dettmers, Naman Goyal, Luke Zettlemoyer.  
  [![Paper](https://img.shields.io/badge/ICML-2021-blue)](https://proceedings.mlr.press/v139/lewis21a.html)

- **Mixture-of-Experts with Expert Choice Routing** (NeurIPS 2022)  
  Yanqi Zhou, Tao Lei, Hanxiao Liu, et al.  
  [![Paper](https://img.shields.io/badge/NeurIPS-2022-blue)](https://arxiv.org/abs/2202.09368)

- **Confident Adaptive Language Modeling (CALM)** (NeurIPS 2022)  
  Tal Schuster, Adam Fisch, Jai Gupta, et al.  
  [![Paper](https://img.shields.io/badge/NeurIPS-2022-blue)](https://arxiv.org/abs/2207.07061)

- **SkipDecode: Autoregressive Skip Decoding with Batching and Caching** (Jul 2023)  
  Luciano Del Corro, Allie Del Giorno, Sahaj Agarwal, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2307.02628-b31b1b.svg)](https://arxiv.org/abs/2307.02628)

- **Mixture-of-Depths: Dynamically Allocating Compute in Transformer-based LMs** (Apr 2024)  
  David Raposo, Sam Ritter, Blake Richards, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2404.02258-b31b1b.svg)](https://arxiv.org/abs/2404.02258)

---

## 🧠 Routing by Learning Regime

### 📏 Heuristic / Rule-based

Manually specified rules or thresholds — no learned parameters.

- **FrugalGPT** — threshold-based cascade escalation  
  [![Paper](https://img.shields.io/badge/arXiv-2305.05176-b31b1b.svg)](https://arxiv.org/abs/2305.05176)

- **Leveraging Uncertainty Estimation for Efficient LLM Routing** — uncertainty-threshold deferral  
  [![Paper](https://img.shields.io/badge/arXiv-2502.11021-b31b1b.svg)](https://arxiv.org/abs/2502.11021)

- **The Avengers** — heuristic rule-based routing combining pre- and post-execution signals  
  [![Paper](https://img.shields.io/badge/arXiv-2505.19797-b31b1b.svg)](https://arxiv.org/abs/2505.19797)

- **RADAR: Reasoning-Ability and Difficulty-Aware Routing** (ICLR 2026)  
  Nigel Fernandez et al.  
  [![Paper](https://img.shields.io/badge/ICLR-2026-blue)](https://arxiv.org/abs/XXXX.XXXXX)

---

### 🏫 Supervised Routing

Routing policies learned from labeled data (oracle model choices, performance outcomes, pairwise preferences).

- **Large Language Model Routing with Benchmark Datasets** (Sep 2023)  
  Tal Shnitzer et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2309.15789-b31b1b.svg)](https://arxiv.org/abs/2309.15789)

- **RouteLLM: Learning to Route LLMs with Preference Data** (ICLR 2025)  
  Isaac Ong et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2406.18665-b31b1b.svg)](https://arxiv.org/abs/2406.18665) [![Code](https://img.shields.io/github/stars/lm-sys/RouteLLM.svg?style=social&label=Star)](https://github.com/lm-sys/RouteLLM)

- **RouterDC: Query-Based Router by Dual Contrastive Learning** (NeurIPS 2024)  
  Shuhao Chen et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2409.19886-b31b1b.svg)](https://arxiv.org/abs/2409.19886) [![Code](https://img.shields.io/github/stars/shuhao02/RouterDC.svg?style=social&label=Star)](https://github.com/shuhao02/RouterDC)

- **EmbedLLM: Learning Compact Representations of LLMs** (ICLR 2025)  
  Richard Zhuang et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2410.02223-b31b1b.svg)](https://arxiv.org/abs/2410.02223) [![Code](https://img.shields.io/github/stars/richardzhuang0412/EmbedLLM.svg?style=social&label=Star)](https://github.com/richardzhuang0412/EmbedLLM)

- **GraphRouter: A Graph-based Router for LLM Selections** (2025)  
  Tao Feng, Yanzhen Shen, Jiaxuan You.  
  [![Paper](https://img.shields.io/badge/arXiv-2410.03834-b31b1b.svg)](https://arxiv.org/abs/2410.03834)

- **SafeRoute: Adaptive Model Selection for Safety Guardrails** (ACL 2025 Findings)  
  Seanie Lee et al.  
  [![Paper](https://img.shields.io/badge/ACL_Anthology-2025.findings--acl.105-blue)](https://aclanthology.org/2025.findings-acl.105)

- **LLM-Blender: Ensembling LLMs with Pairwise Ranking and Generative Fusion** (Jun 2023)  
  Dongfu Jiang et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2306.02561-b31b1b.svg)](https://arxiv.org/abs/2306.02561)

- **BASE Layers: Simplifying Training of Large, Sparse Models** (ICML 2021)  
  Mike Lewis et al.  
  [![Paper](https://img.shields.io/badge/ICML-2021-blue)](https://proceedings.mlr.press/v139/lewis21a.html)

- **Self-REF / Learning to Route LLMs with Confidence Tokens** (ICML 2025)  
  Yu-Neng Chuang et al.  
  [![Paper](https://img.shields.io/badge/ICML-2025-blue)](https://proceedings.mlr.press/v267/chuang25b.html)

- **Lookahead Routing for LLMs** (NeurIPS 2025)  
  Canbin Huang et al.  
  [![Paper](https://img.shields.io/badge/NeurIPS-2025-blue)](https://arxiv.org/abs/XXXX.XXXXX)

- **RADAR: Reasoning-Ability and Difficulty-Aware Routing** (ICLR 2026)  
  [![Paper](https://img.shields.io/badge/ICLR-2026-blue)](https://arxiv.org/abs/XXXX.XXXXX)

- **R2-Router: A New Paradigm for LLM Routing with Reasoning** (2026)  
  [![Paper](https://img.shields.io/badge/arXiv-2602.02823-b31b1b.svg)](https://arxiv.org/abs/2602.02823)

- **RACER: Risk-Aware Calibrated Efficient Routing** (2026)  
  [![Paper](https://img.shields.io/badge/arXiv-2603.06616-b31b1b.svg)](https://arxiv.org/abs/2603.06616)

- **EquiRouter: On the Degenerate Convergence of LLM Routers** (2026)  
  [![Paper](https://img.shields.io/badge/arXiv-2602.03478-b31b1b.svg)](https://arxiv.org/abs/2602.03478)

---

### 🔄 Online / Adaptive Routing

Routing policies updated through interaction — contextual bandits, reinforcement learning, or continual adaptation.

- **C2MAB-V: Cost-Effective Online Multi-LLM Selection with Versatile Reward Models** (2024)  
  Xiangxiang Dai, Jin Li, Xutong Liu, Anqi Yu, John C.S. Lui.  
  [![Paper](https://img.shields.io/badge/arXiv-2405.16587-b31b1b.svg)](https://arxiv.org/abs/2405.16587)

- **LLM Bandit: Cost-Efficient LLM Generation via Preference-Conditioned Dynamic Routing** (Feb 2025)  
  Yang Li.  
  [![Paper](https://img.shields.io/badge/arXiv-2502.02743-b31b1b.svg)](https://arxiv.org/abs/2502.02743)

- **BaRP: Learning to Route LLMs from Bandit Feedback** (Oct 2025)  
  Wang Wei, Tiankai Yang, Hongjie Chen, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2510.07429-b31b1b.svg)](https://arxiv.org/abs/2510.07429)

- **Router-R1: Teaching LLMs Multi-Round Routing via Reinforcement Learning** (NeurIPS 2025)  
  Haozhen Zhang, Tao Feng, Jiaxuan You.  
  [![Paper](https://img.shields.io/badge/OpenReview-NeurIPS_2025-blue)](https://openreview.net/forum?id=DWf4vroKWJ) [![Code](https://img.shields.io/github/stars/ulab-uiuc/Router-R1.svg?style=social&label=Star)](https://github.com/ulab-uiuc/Router-R1)

- **PickLLM: Context-Aware RL-Assisted LLM Routing** (2025)  
  Dimitrios Sikeridis, Dennis Ramdass, Pranay Pareek.  
  [![Paper](https://img.shields.io/badge/Springer-2025-blue)](https://doi.org/10.1007/978-981-96-8912-5_11)

- **MetaLLM: A High-Performant and Cost-Efficient Dynamic Framework for Wrapping LLMs** (2025)  
  Quang H. Nguyen et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2407.10834-b31b1b.svg)](https://arxiv.org/abs/2407.10834)

- **MixLLM: Dynamic Routing in Mixed Large Language Models** (Feb 2025)  
  Xinyuan Wang et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2502.18482-b31b1b.svg)](https://arxiv.org/abs/2502.18482)

- **PROTEUS: SLA-Aware Routing via Lagrangian RL for Multi-LLM Serving** (2026)  
  Amit Singh Bhatti et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2601.19402-b31b1b.svg)](https://arxiv.org/abs/2601.19402)

---

## 📊 Benchmarks & Datasets

### Routing-Native Benchmarks

| Dataset | Paper | #Samples | #Models | Key Feature |
|---|---|---|---|---|
| **RouterBench** | [![Paper](https://img.shields.io/badge/arXiv-2403.12031-b31b1b.svg)](https://arxiv.org/abs/2403.12031) | 400k+ | 11 | Standardized multi-task routing eval |
| **LLMRouterBench** | [![Paper](https://img.shields.io/badge/arXiv-2601.07206-b31b1b.svg)](https://arxiv.org/abs/2601.07206) | 400k+ | 33 | Large-scale unified benchmark |
| **RouterEval** | [![Paper](https://img.shields.io/badge/arXiv-2503.10657-b31b1b.svg)](https://arxiv.org/abs/2503.10657) | 200M+ | 8,500+ | Large-scale model-level scaling analysis |
| **RouterArena** | [![Paper](https://img.shields.io/badge/arXiv-2510.00202-b31b1b.svg)](https://arxiv.org/abs/2510.00202) | 8.4k | 42 | Difficulty-aware open platform |
| **RouterDC Dataset** | [![Paper](https://img.shields.io/badge/arXiv-2409.19886-b31b1b.svg)](https://arxiv.org/abs/2409.19886) | 100k+ | 6–10 | Difficulty-aware routing dataset |
| **MixInstruct** | [![Paper](https://img.shields.io/badge/arXiv-2306.02561-b31b1b.svg)](https://arxiv.org/abs/2306.02561) | 110k | 11 | Instruction-following ensembling |
| **EmbedLLM Dataset** | [![Paper](https://img.shields.io/badge/arXiv-2410.02223-b31b1b.svg)](https://arxiv.org/abs/2410.02223) | 36k+ | 112 | Performance-based routing dataset |
| **VL-RouterBench** | [![Paper](https://img.shields.io/badge/arXiv-2503.XXXXX-b31b1b.svg)](https://arxiv.org/abs/XXXX.XXXXX) | 30.5k | 17 | Multimodal (vision-language) routing |
| **MMR-Bench** | [![Paper](https://img.shields.io/badge/arXiv-2601.17814-b31b1b.svg)](https://arxiv.org/abs/2601.17814) | 11k | 10 | Multimodal reasoning routing |
| **Router-R1 Dataset** | [![Paper](https://img.shields.io/badge/OpenReview-NeurIPS_2025-blue)](https://openreview.net/forum?id=DWf4vroKWJ) | 49k | 4–8 | Multi-round reasoning routing |

### Evaluation Platforms & Toolboxes

| Resource | Paper | Type | Key Feature |
|---|---|---|---|
| **RouteJudge** | [![Paper](https://img.shields.io/badge/arXiv-2606.18774-b31b1b.svg)](https://arxiv.org/abs/2606.18774) | [Online platform](https://routejudge.cn/) | Anonymous pairwise, preference-aware router evaluation |
| **ORBIT** | [![Paper](https://img.shields.io/badge/FCS-2026-blue)](https://journal.hep.com.cn/fcs/EN/10.1007/s11704-026-61310-5) | [Toolbox](https://github.com/LAMDA-Model-Reuse/ORBIT) | Standardized routers, benchmarks, and budget-aware evaluation |

### Task Datasets Commonly Used for Routing Evaluation

| Dataset | Description | Routing Use Case |
|---|---|---|
| **MMLU** | Massive Multitask Language Understanding | Input-difficulty routing, capability matching |
| **GSM8K** | Grade School Math | Cascade routing, reasoning escalation |
| **HumanEval** | Code generation | Intra-execution routing signals |
| **HotpotQA** | Multi-hop QA | Step-level routing, sequential reasoning |
| **GLUE / SuperGLUE** | Multi-task NLP benchmarks | Task-type routing, input-only strategies |

---

## 💡 Tips for Using This Repo

- **📖 Search by section**: Use the table of contents to navigate directly to your area of interest.
- **🔍 Search by author**: Use `Ctrl+F` with an author name to quickly find related work.
- **🗂️ Cross-referenced**: Papers appearing in multiple sections are listed in their most relevant section but may apply to others.
- **🔗 All arXiv links verified** as of April 2026. Conference/workshop paper links are to official proceedings when available.

---

## 📖 Related Surveys

- **Harnessing the Power of Multiple Minds: Lessons Learned from LLM Routing** (Insights@NLP 2024)  
  KV Aditya Srivatsa, Kaushal Kumar Maurya, Ekaterina Kochmar.  
  [![Paper](https://img.shields.io/badge/ACL_Anthology-2024.insights--1.15-blue)](https://aclanthology.org/2024.insights-1.15)

- **Personalization of Large Language Models: A Survey** (TMLR 2025)  
  Zhehao Zhang, Ryan A. Rossi, Branislav Kveton, et al.  
  [![Paper](https://img.shields.io/badge/arXiv-2411.00027-b31b1b.svg)](https://arxiv.org/abs/2411.00027)

---

## 🤝 Contributing

We welcome contributions! If you have a paper to add:

1. Open an **Issue** with the paper title, link, and suggested category.
2. Or submit a **Pull Request** following the existing format.

Please check that the paper is directly related to LLM routing (model selection, cascading, MoE gating, or orchestration at inference time).

---

*Last updated: April 2026*
