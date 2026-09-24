<div align="center">

# 🚶 Awesome VLN

**A Curated Collection of Vision-and-Language Navigation Research**

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
[![Papers](https://img.shields.io/badge/Papers-48-0984e3?style=for-the-badge&logo=google-scholar&logoColor=white)](#topological-planning)
[![Last Commit](https://img.shields.io/github/last-commit/Stagnation47/Awsome-VLN?style=for-the-badge&color=00b894)](https://github.com/Stagnation47/Awsome-VLN/commits/main)
[![Stars](https://img.shields.io/github/stars/Stagnation47/Awsome-VLN?style=for-the-badge&color=fdcb6e&logo=github)](https://github.com/Stagnation47/Awsome-VLN/stargazers)
[![Forks](https://img.shields.io/github/forks/Stagnation47/Awsome-VLN?style=for-the-badge&color=e17055&logo=github)](https://github.com/Stagnation47/Awsome-VLN/forks)

*视觉语言导航（VLN）论文、模型与基准，按研究方向分类整理。*

</div>

## 目录

- [综述](#surveys)
- [拓扑地图与路径规划](#topological-planning)
- [场景图与指令约束](#scene-graphs)
- [语义地图与三维特征场](#spatial-maps)
- [隐式记忆、流式上下文与高效推理](#memory-streaming)
- [推理、训练与测试时适应](#reasoning-adaptation)
- [视觉想象与数据增强](#imagination-data)
- [通用导航模型与实机指令跟随](#generalist-real-world)
- [空中视觉语言导航](#aerial-vln)
- [基准与数据集](#benchmarks)

## 收录范围

聚焦基于视觉观察与自然语言指令的导航，包括离散 VLN、连续环境 VLN-CE、空中 VLN 和实机语言导航；保留直接支持这些任务的空间表示与导航 VLA 模型。

每篇论文按主要研究方向收录一次；分类用于检索，不代表方法之间互斥。年份沿用发表年份或原清单记录；新增预印本标为 arXiv，ETPNav 单独注明 2023 年首次公开。离散导航、在线未知环境、预探索建图和测试时适应的实验条件需分别比较。

<a id="surveys"></a>

## 综述

- [2024] Vision-language navigation: a survey and taxonomy [[paper](https://arxiv.org/pdf/2108.11544)]

<a id="topological-planning"></a>

## 拓扑地图与路径规划

以路点和连通关系组织空间记忆，支持长程规划、回溯和图策略学习。

- [2026] [**arXiv**] **DGNav**: Dynamic Topology Awareness: Breaking the Granularity Rigidity in Vision-Language Navigation [[paper](https://arxiv.org/abs/2601.21751)] — 按场景复杂度调整图粒度，并融合视觉、语言和几何信息形成动态边权；VLN-CE。
- [2025] [**arXiv**] **ETP-R1**: Evolving Topological Planning with Reinforcement Fine-tuning for Vision-Language Navigation in Continuous Environments [[paper](https://arxiv.org/abs/2512.20940)] [[code](https://github.com/Cepillar/ETP-R1)] — 扩大指令—轨迹预训练数据，联合 R2R/RxR，并用闭环 GRPO 强化微调图策略。
- [2025] SmartWay: Enhanced Waypoint Prediction and Backtracking for Zero-Shot Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2503.10069)]
- [2024] Mobility VLA: Multimodal Instruction Navigation with Long-Context VLMs and Topological Graphs [[paper](https://arxiv.org/pdf/2407.07775)]
- [2023] [**arXiv 首发**] **ETPNav**: Evolving Topological Planning for Vision-Language Navigation in Continuous Environments [[paper](https://arxiv.org/abs/2304.03047)] [[code](https://github.com/MarSaKi/ETPNav)] — 在线拓扑建图、跨模态规划与低层避障；VLN-CE。
- [2023] [**CVPR 23**] Adaptive Zone-Aware Hierarchical Planner for Vision-Language Navigation [[paper](https://openaccess.thecvf.com/content/CVPR2023/papers/Gao_Adaptive_Zone-Aware_Hierarchical_Planner_for_Vision-Language_Navigation_CVPR_2023_paper.pdf)]

<a id="scene-graphs"></a>

## 场景图与指令约束

用物体、区域及空间关系关联语言指令与导航目标；场景图关系仍需连接到可执行路径。

- [2026] [**arXiv**] **SpatialNav**: Leveraging Spatial Scene Graphs for Zero-Shot Vision-and-Language Navigation [[paper](https://arxiv.org/abs/2601.06806)] — 场景图提供全局空间信息；允许任务前预探索，连续环境实验使用 R2R-CE/RxR-CE 抽样子集。
- [2025] [**NeurIPS 25**] **HSAN**: Hierarchical Semantic-Augmented Navigation: Optimal Transport and Graph-Driven Reasoning for Vision-Language Navigation [[paper](https://papers.neurips.cc/paper_files/paper/2025/hash/592da1445a51e54a3987958b5831948f-Abstract-Conference.html)] — 分层语义场景图、最优传输拓扑规划与图感知低层强化学习；VLN-CE。
- [2025] [**arXiv**] **FSR-VLN**: Fast and Slow Reasoning for Vision-Language Navigation with Hierarchical Multi-modal Scene Graph [[paper](https://arxiv.org/abs/2509.13733)] — 分层多模态图上的快速检索与按需 VLM 精细推理；假设静态环境，建图不适合实时执行。
- [2025] [**arXiv**] **VLN-Zero**: Rapid Exploration and Cache-Enabled Neurosymbolic Vision-Language Planning for Zero-Shot Transfer in Robot Navigation [[paper](https://arxiv.org/abs/2509.18592)] — 探索阶段构建符号场景图，部署阶段进行神经符号规划并复用缓存路径。
- [2025] [**CoRL 25**] GC-VLN: Instruction as Graph Constraints for Training-free Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2509.10454)] [[project](https://bagh2178.github.io/GC-VLN/)] [[code](https://github.com/bagh2178/GC-VLN)] — 将指令转为物体、路点和空间关系约束，结合约束求解及导航树完成导航。
- [2025] DyNaVLM: Zero-Shot Vision-Language Navigation System with Dynamic Viewpoints and Self-Refining Graph Memory [[paper](https://arxiv.org/pdf/2506.15096)]

<a id="spatial-maps"></a>

## 语义地图与三维特征场

将视觉语言特征与几何位置对齐，用于语言定位、路点预测或前瞻规划。

- [2025] [**RA-L 25**] **OVL-MAP**: An Online Visual Language Map Approach for Vision-and-Language Navigation in Continuous Environments [[paper](https://labsun.org/pub/RAL2025_ovlmap.pdf)] — 在线融合空间与视觉语言特征，结合路点预测和动作决策；评测包含 Robo-VLN 与 R2R-CE。
- [2025] [**CVPR 25**] **g3D-LF**: Generalizable 3D-Language Feature Fields for Embodied Tasks [[paper](https://arxiv.org/abs/2411.17030)] — 可更新的三维语言特征场，支持新视角、BEV 和多粒度语言查询；含全景及单目 VLN 评测。
- [2025] MapNav: A Novel Memory Representation via Annotated Semantic Maps for VLM-based Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2502.13451)]
- [2025] [**IJRR 25**] Multimodal Spatial Language Maps for Robot Navigation and Manipulation [[paper](https://arxiv.org/pdf/2506.06862)] [[project](https://mslmaps.github.io/)]
- [2024] [**CVPR 24**] **HNR**: Lookahead Exploration with Neural Radiance Representation for Continuous Vision-Language Navigation [[paper](https://arxiv.org/abs/2404.01943)] — 预测候选位置的未来语义特征，并评估未来路径树；VLN-CE。

<a id="memory-streaming"></a>

## 隐式记忆、流式上下文与高效推理

压缩或组织历史观察，协调近期感知与长期空间记忆。

- [2026] [**Sensors 26**] **SR-VLN**: Implicit Spatial Reasoning Vision-and-Language Navigation [[paper](https://www.mdpi.com/1424-8220/26/12/3809)] — 感知压缩、分层历史与隐式空间 token；评测为 R2R、REVERIE、SOON 等离散导航任务。
- [2025] JanusVLN: Decoupling Semantics and Spatiality with Dual Implicit Memory for Vision-Language Navigation [[paper](https://arxiv.org/pdf/2509.22548)] [[project](https://miv-xjtu.github.io/JanusVLN.github.io/)] [[code](https://github.com/MIV-XJTU/JanusVLN)] — 分离语义与空间信息，通过双隐式记忆支持 VLN。
- [2025] [**arXiv**] **StreamVLN**: Streaming Vision-and-Language Navigation via SlowFast Context Modeling [[paper](https://arxiv.org/abs/2507.05240)] — 快速滑窗上下文结合慢速更新记忆，并用三维感知 token 剪枝压缩历史。
- [2025] Ground Slow, Move Fast: A Dual-System Foundation Model for Generalizable Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2512.08186)] [[project](https://internrobotics.github.io/internvla-n1-dualvln.github.io/)] [[code](https://github.com/InternRobotics/InternNav)]
- [2025] COSMO: Combination of Selective Memorization for Low-cost Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2503.24065)]
- [2025] Dynam3D: Dynamic Layered 3D Tokens Empower VLM for Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2505.11383)] [[project](https://github.com/MrZihan/Dynam3D)]
- [2024] [**RSS 24**] Navid: Video-based vlm plans the next step for vision-and-language navigation [[paper](https://arxiv.org/pdf/2402.15852)]

<a id="reasoning-adaptation"></a>

## 推理、训练与测试时适应

关注指令推理、跨任务适应、自纠错以及测试阶段策略更新。

- [2025] Active Test-time Vision-Language Navigation [[paper](https://arxiv.org/pdf/2506.06630)] — **ATENA，NeurIPS 2025**：利用任务结果反馈与自评估进行测试时适应；比较时需对齐反馈及参数更新条件。
- [2025] CorrectNav: Self-Correction Flywheel Empowers Vision-Language-Action Navigation Model [[paper](https://arxiv.org/pdf/2508.10416)] [[project](https://correctnav.github.io/)]
- [2025] Aux-Think: Exploring Reasoning Strategies for Data-Efficient Vision-Language Navigation [[paper](https://arxiv.org/pdf/2505.11886)]
- [2025] FlexVLN: Flexible Adaptation for Diverse Vision-and-Language Navigation Tasks [[paper](https://arxiv.org/pdf/2503.13966)]
- [2025] TRAVEL: Training-Free Retrieval and Alignment for Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2502.07306)]

<a id="imagination-data"></a>

## 视觉想象与数据增强

通过未来视觉预测、环境生成或指令—观察改写改进 VLN。

- [2025] VISTA: Generative Visual Imagination for Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2505.07868)]
- [2025] Do Visual Imaginations Improve Vision-and-Language Navigation Agents? [[paper](https://arxiv.org/pdf/2503.16394)] [[project](https://www.akhilperincherry.com/VLN-Imagine-website/)]
- [2025] PanoGen++: Domain-Adapted Text-Guided Panoramic Environment Generation for Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2503.09938)]
- [2025] Unseen from Seen: Rewriting Observation-Instruction Using Foundation Models for Augmenting Vision-Language Navigation [[paper](https://arxiv.org/pdf/2503.18065)] [[project](https://github.com/SaDil13/VLN-RAM)]

<a id="generalist-real-world"></a>

## 通用导航模型与实机指令跟随

收录明确支持语言指令导航的通用模型和实机系统。

- [2025] Embodied Navigation Foundation Model [[paper](https://arxiv.org/pdf/2509.12129)] [[project](https://pku-epic.github.io/NavFoM-Web/)]
- [2025] OctoNav: Towards Generalist Embodied Navigation [[paper](https://arxiv.org/pdf/2506.09839)] [[project](https://buaa-colalab.github.io/OctoNav/)]
- [2025] [**RSS 25**] NaVILA: Legged Robot Vision-Language-Action Model for Navigation [[paper](https://arxiv.org/pdf/2412.04453)] [[project](https://navila-bot.github.io/)]
- [2025] OmniVLA: An Omni-Modal Vision-Language-Action Model for Robot Navigation [[paper](https://arxiv.org/pdf/2509.19480)] [[project](https://omnivla-nav.github.io/)] [[code](https://github.com/NHirose/OmniVLA)]
- [2025] LOVON: Legged Open-Vocabulary Object Navigator [[paper](https://arxiv.org/pdf/2507.06747)] [[project](https://daojiepeng.github.io/LOVON/)]
- [2025] VL-Nav: Real-time Vision-Language Navigation with Spatial Reasoning [[paper](https://arxiv.org/pdf/2502.00931)]
- [2025] OpenNav: Open-World Navigation with Multimodal Large Language Models [[paper](https://arxiv.org/pdf/2507.18033)] [[project](https://trailab.github.io/OpenNav-website/)]
- [2025] Ground-level Viewpoint Vision-and-Language Navigation in Continuous Environments [[paper](https://arxiv.org/pdf/2502.19024)]
- [2024] CANVAS: Commonsense-Aware Navigation System for Intuitive Human-Robot Interaction [[paper](https://arxiv.org/abs/2410.01273)] [[project](https://worv-ai.github.io/canvas/)] [[code](https://github.com/worv-ai/canvas)]

<a id="aerial-vln"></a>

## 空中视觉语言导航

面向无人机的语言理解、空间规划与连续控制。

- [2025] CityNavAgent: Aerial Vision-and-Language Navigation with Hierarchical Semantic Planning and Global Memory [[paper](https://arxiv.org/pdf/2505.05622)] [[project](https://github.com/VinceOuti/CityNavAgent)]
- [2025] Grounded Vision-Language Navigation for UAVs with Open-Vocabulary Goal Understanding [[paper](https://arxiv.org/pdf/2506.10756)] [[project](https://zzzzzyh111.github.io/VLFly/)]

<a id="benchmarks"></a>

## 基准与数据集

用于评估指令跟随、动态交互及条件分支能力。

- [2026] [**arXiv**] **CondVLN**: If, Then, Otherwise: Diagnosing Conditional Branching in Vision-Language Navigation [[paper](https://arxiv.org/abs/2608.17318)] — 以场景图为依据构造条件分支指令，诊断条件判断与分支执行能力。
- [2025] HA-VLN: A Benchmark for Human-Aware Navigation in Discrete-Continuous Environments with Dynamic Multi-Human Interactions, Real-World Validation, and an Open Leaderboard [[paper](https://arxiv.org/pdf/2503.14229)] [[project](https://ha-vln-project.vercel.app/)]
- [2025] OpenFly: A Versatile Toolchain and Large-scale Benchmark for Aerial Vision-Language Navigation [[paper](https://arxiv.org/pdf/2502.18041)]

## 贡献

欢迎通过 [Issue](https://github.com/Stagnation47/Awsome-VLN/issues) 或 [Pull Request](https://github.com/Stagnation47/Awsome-VLN/pulls) 补充 VLN 论文、数据集和工具。请提供题名、年份、论文及代码链接、所属方向，并简要说明任务设置。

## 致谢

本清单基于 [awesome-embodied-vla-va-vln](https://github.com/jonyzhang2023/awesome-embodied-vla-va-vln) 整理，感谢原维护者与贡献者。

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=Stagnation47/Awsome-VLN&type=Date)](https://star-history.com/#Stagnation47/Awsome-VLN&Date)
