<div align="center">

# 🚶 Awesome VLN

**A Curated Collection of Vision-and-Language Navigation Research**

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
[![Papers](https://img.shields.io/badge/Papers-48-0984e3?style=for-the-badge&logo=google-scholar&logoColor=white)](#topological-planning)
[![Last Commit](https://img.shields.io/github/last-commit/Stagnation47/Awsome-VLN?style=for-the-badge&color=00b894)](https://github.com/Stagnation47/Awsome-VLN/commits/main)
[![Stars](https://img.shields.io/github/stars/Stagnation47/Awsome-VLN?style=for-the-badge&color=fdcb6e&logo=github)](https://github.com/Stagnation47/Awsome-VLN/stargazers)
[![Forks](https://img.shields.io/github/forks/Stagnation47/Awsome-VLN?style=for-the-badge&color=e17055&logo=github)](https://github.com/Stagnation47/Awsome-VLN/forks)

*Papers, models, and benchmarks for vision-and-language navigation, organized by research direction.*

</div>

## Table of Contents

- [Surveys](#surveys)
- [Topological Mapping and Path Planning](#topological-planning)
- [Scene Graphs and Instruction Constraints](#scene-graphs)
- [Semantic Maps and 3D Feature Fields](#spatial-maps)
- [Implicit Memory, Streaming Context, and Efficient Inference](#memory-streaming)
- [Reasoning, Training, and Test-Time Adaptation](#reasoning-adaptation)
- [Visual Imagination and Data Augmentation](#imagination-data)
- [Generalist Navigation and Real-World Instruction Following](#generalist-real-world)
- [Aerial Vision-and-Language Navigation](#aerial-vln)
- [Benchmarks and Datasets](#benchmarks)

<a id="surveys"></a>

## Surveys

- [2024] Vision-language navigation: a survey and taxonomy [[paper](https://arxiv.org/pdf/2108.11544)]

<a id="topological-planning"></a>

## Topological Mapping and Path Planning

Spatial memory organized around waypoints and connectivity for long-range planning, backtracking, and graph policy learning.

- [2026] [**arXiv**] **DGNav**: Dynamic Topology Awareness: Breaking the Granularity Rigidity in Vision-Language Navigation [[paper](https://arxiv.org/abs/2601.21751)] — Adapts graph granularity to scene complexity and combines visual, linguistic, and geometric cues into dynamic edge weights for VLN-CE.
- [2025] [**arXiv**] **ETP-R1**: Evolving Topological Planning with Reinforcement Fine-tuning for Vision-Language Navigation in Continuous Environments [[paper](https://arxiv.org/abs/2512.20940)] [[code](https://github.com/Cepillar/ETP-R1)] — Scales instruction–trajectory pretraining, jointly uses R2R/RxR data, and fine-tunes graph policies with closed-loop GRPO.
- [2025] SmartWay: Enhanced Waypoint Prediction and Backtracking for Zero-Shot Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2503.10069)]
- [2024] Mobility VLA: Multimodal Instruction Navigation with Long-Context VLMs and Topological Graphs [[paper](https://arxiv.org/pdf/2407.07775)]
- [2023] [**arXiv debut**] **ETPNav**: Evolving Topological Planning for Vision-Language Navigation in Continuous Environments [[paper](https://arxiv.org/abs/2304.03047)] [[code](https://github.com/MarSaKi/ETPNav)] — Online topological mapping, cross-modal planning, and low-level obstacle avoidance for VLN-CE; first released in 2023.
- [2023] [**CVPR 23**] Adaptive Zone-Aware Hierarchical Planner for Vision-Language Navigation [[paper](https://openaccess.thecvf.com/content/CVPR2023/papers/Gao_Adaptive_Zone-Aware_Hierarchical_Planner_for_Vision-Language_Navigation_CVPR_2023_paper.pdf)]

<a id="scene-graphs"></a>

## Scene Graphs and Instruction Constraints

Objects, regions, and spatial relations connect language instructions to navigation goals. Scene graph relations must also connect to executable paths.

- [2026] [**arXiv**] **SpatialNav**: Leveraging Spatial Scene Graphs for Zero-Shot Vision-and-Language Navigation [[paper](https://arxiv.org/abs/2601.06806)] — Uses scene graphs for global spatial information. Allows exploration before task execution; continuous-environment experiments use sampled R2R-CE/RxR-CE subsets.
- [2025] [**NeurIPS 25**] **HSAN**: Hierarchical Semantic-Augmented Navigation: Optimal Transport and Graph-Driven Reasoning for Vision-Language Navigation [[paper](https://papers.neurips.cc/paper_files/paper/2025/hash/592da1445a51e54a3987958b5831948f-Abstract-Conference.html)] — Combines hierarchical semantic scene graphs, optimal transport for topological planning, and graph-aware low-level reinforcement learning for VLN-CE.
- [2025] [**arXiv**] **FSR-VLN**: Fast and Slow Reasoning for Vision-Language Navigation with Hierarchical Multi-modal Scene Graph [[paper](https://arxiv.org/abs/2509.13733)] — Combines fast retrieval over hierarchical multimodal graphs with VLM refinement on demand. Assumes static environments; graph construction is unsuitable for real-time mapping.
- [2025] [**arXiv**] **VLN-Zero**: Rapid Exploration and Cache-Enabled Neurosymbolic Vision-Language Planning for Zero-Shot Transfer in Robot Navigation [[paper](https://arxiv.org/abs/2509.18592)] — Builds symbolic scene graphs during exploration, then uses neurosymbolic planning and cached paths during deployment.
- [2025] [**CoRL 25**] GC-VLN: Instruction as Graph Constraints for Training-free Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2509.10454)] [[project](https://bagh2178.github.io/GC-VLN/)] [[code](https://github.com/bagh2178/GC-VLN)] — Converts instructions into constraints on objects, waypoints, and spatial relations, then navigates through constraint solving and a navigation tree.
- [2025] DyNaVLM: Zero-Shot Vision-Language Navigation System with Dynamic Viewpoints and Self-Refining Graph Memory [[paper](https://arxiv.org/pdf/2506.15096)]

<a id="spatial-maps"></a>

## Semantic Maps and 3D Feature Fields

Vision-language features aligned with geometric locations for language grounding, waypoint prediction, and lookahead planning.

- [2025] [**RA-L 25**] **OVL-MAP**: An Online Visual Language Map Approach for Vision-and-Language Navigation in Continuous Environments [[paper](https://labsun.org/pub/RAL2025_ovlmap.pdf)] — Fuses spatial and vision-language features online with waypoint prediction and action selection; evaluated on Robo-VLN and R2R-CE.
- [2025] [**CVPR 25**] **g3D-LF**: Generalizable 3D-Language Feature Fields for Embodied Tasks [[paper](https://arxiv.org/abs/2411.17030)] — Updatable 3D-language feature fields support novel views, BEV representations, and language queries at multiple granularities; evaluated on panoramic and monocular VLN.
- [2025] MapNav: A Novel Memory Representation via Annotated Semantic Maps for VLM-based Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2502.13451)]
- [2025] [**IJRR 25**] Multimodal Spatial Language Maps for Robot Navigation and Manipulation [[paper](https://arxiv.org/pdf/2506.06862)] [[project](https://mslmaps.github.io/)]
- [2024] [**CVPR 24**] **HNR**: Lookahead Exploration with Neural Radiance Representation for Continuous Vision-Language Navigation [[paper](https://arxiv.org/abs/2404.01943)] — Predicts future semantic features at candidate locations and evaluates future path trees for VLN-CE.

<a id="memory-streaming"></a>

## Implicit Memory, Streaming Context, and Efficient Inference

Historical observations compressed or organized to combine recent perception with long-term spatial memory.

- [2026] [**Sensors 26**] **SR-VLN**: Implicit Spatial Reasoning Vision-and-Language Navigation [[paper](https://www.mdpi.com/1424-8220/26/12/3809)] — Combines perceptual compression, hierarchical history, and implicit spatial tokens; evaluated on discrete navigation tasks including R2R, REVERIE, and SOON.
- [2025] JanusVLN: Decoupling Semantics and Spatiality with Dual Implicit Memory for Vision-Language Navigation [[paper](https://arxiv.org/pdf/2509.22548)] [[project](https://miv-xjtu.github.io/JanusVLN.github.io/)] [[code](https://github.com/MIV-XJTU/JanusVLN)] — Decouples semantic and spatial information through dual implicit memory for VLN.
- [2025] [**arXiv**] **StreamVLN**: Streaming Vision-and-Language Navigation via SlowFast Context Modeling [[paper](https://arxiv.org/abs/2507.05240)] — Combines fast sliding-window context with slowly updated memory and compresses history through 3D-aware token pruning.
- [2025] Ground Slow, Move Fast: A Dual-System Foundation Model for Generalizable Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2512.08186)] [[project](https://internrobotics.github.io/internvla-n1-dualvln.github.io/)] [[code](https://github.com/InternRobotics/InternNav)]
- [2025] COSMO: Combination of Selective Memorization for Low-cost Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2503.24065)]
- [2025] Dynam3D: Dynamic Layered 3D Tokens Empower VLM for Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2505.11383)] [[project](https://github.com/MrZihan/Dynam3D)]
- [2024] [**RSS 24**] Navid: Video-based vlm plans the next step for vision-and-language navigation [[paper](https://arxiv.org/pdf/2402.15852)]

<a id="reasoning-adaptation"></a>

## Reasoning, Training, and Test-Time Adaptation

Methods for instruction reasoning, cross-task adaptation, self-correction, and policy updates at test time.

- [2025] Active Test-time Vision-Language Navigation [[paper](https://arxiv.org/pdf/2506.06630)] — **ATENA, NeurIPS 2025**: Adapts at test time using task outcome feedback and self-evaluation. Comparisons should account for feedback access and parameter updates.
- [2025] CorrectNav: Self-Correction Flywheel Empowers Vision-Language-Action Navigation Model [[paper](https://arxiv.org/pdf/2508.10416)] [[project](https://correctnav.github.io/)]
- [2025] Aux-Think: Exploring Reasoning Strategies for Data-Efficient Vision-Language Navigation [[paper](https://arxiv.org/pdf/2505.11886)]
- [2025] FlexVLN: Flexible Adaptation for Diverse Vision-and-Language Navigation Tasks [[paper](https://arxiv.org/pdf/2503.13966)]
- [2025] TRAVEL: Training-Free Retrieval and Alignment for Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2502.07306)]

<a id="imagination-data"></a>

## Visual Imagination and Data Augmentation

VLN methods using visual prediction, environment generation, or instruction–observation rewriting.

- [2025] VISTA: Generative Visual Imagination for Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2505.07868)]
- [2025] Do Visual Imaginations Improve Vision-and-Language Navigation Agents? [[paper](https://arxiv.org/pdf/2503.16394)] [[project](https://www.akhilperincherry.com/VLN-Imagine-website/)]
- [2025] PanoGen++: Domain-Adapted Text-Guided Panoramic Environment Generation for Vision-and-Language Navigation [[paper](https://arxiv.org/pdf/2503.09938)]
- [2025] Unseen from Seen: Rewriting Observation-Instruction Using Foundation Models for Augmenting Vision-Language Navigation [[paper](https://arxiv.org/pdf/2503.18065)] [[project](https://github.com/SaDil13/VLN-RAM)]

<a id="generalist-real-world"></a>

## Generalist Navigation and Real-World Instruction Following

Generalist models and real-world systems that explicitly support navigation from language instructions.

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

## Aerial Vision-and-Language Navigation

Language understanding, spatial planning, and continuous control for UAV navigation.

- [2025] CityNavAgent: Aerial Vision-and-Language Navigation with Hierarchical Semantic Planning and Global Memory [[paper](https://arxiv.org/pdf/2505.05622)] [[project](https://github.com/VinceOuti/CityNavAgent)]
- [2025] Grounded Vision-Language Navigation for UAVs with Open-Vocabulary Goal Understanding [[paper](https://arxiv.org/pdf/2506.10756)] [[project](https://zzzzzyh111.github.io/VLFly/)]

<a id="benchmarks"></a>

## Benchmarks and Datasets

Evaluation of instruction following, dynamic interactions, and conditional branching.

- [2026] [**arXiv**] **CondVLN**: If, Then, Otherwise: Diagnosing Conditional Branching in Vision-Language Navigation [[paper](https://arxiv.org/abs/2608.17318)] — Uses scene graphs to construct conditional instructions and diagnose condition evaluation and branch execution.
- [2025] HA-VLN: A Benchmark for Human-Aware Navigation in Discrete-Continuous Environments with Dynamic Multi-Human Interactions, Real-World Validation, and an Open Leaderboard [[paper](https://arxiv.org/pdf/2503.14229)] [[project](https://ha-vln-project.vercel.app/)]
- [2025] OpenFly: A Versatile Toolchain and Large-scale Benchmark for Aerial Vision-Language Navigation [[paper](https://arxiv.org/pdf/2502.18041)]

## Contributing

Contributions of VLN papers, datasets, and tools are welcome through an [Issue](https://github.com/Stagnation47/Awsome-VLN/issues) or [Pull Request](https://github.com/Stagnation47/Awsome-VLN/pulls). Please include the title, year, paper and code links, research category, and a brief description of the task setting.

## Acknowledgements

This collection is adapted from [awesome-embodied-vla-va-vln](https://github.com/jonyzhang2023/awesome-embodied-vla-va-vln). Thanks to the original maintainers and contributors.
