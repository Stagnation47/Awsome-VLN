<div align="center">

# 🚶 Awesome VLN

**A Curated Collection of Vision-and-Language Navigation Research**

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
[![Papers](https://img.shields.io/badge/Papers-60-0984e3?style=for-the-badge&logo=google-scholar&logoColor=white)](#papers)
[![Last Commit](https://img.shields.io/github/last-commit/Stagnation47/Awsome-VLN?style=for-the-badge&color=00b894)](https://github.com/Stagnation47/Awsome-VLN/commits/main)
[![Stars](https://img.shields.io/github/stars/Stagnation47/Awsome-VLN?style=for-the-badge&color=fdcb6e&logo=github)](https://github.com/Stagnation47/Awsome-VLN/stargazers)
[![Forks](https://img.shields.io/github/forks/Stagnation47/Awsome-VLN?style=for-the-badge&color=e17055&logo=github)](https://github.com/Stagnation47/Awsome-VLN/forks)

*Papers, models, and benchmarks for vision-and-language navigation.*

</div>

## Contents

- [Surveys](#surveys)
- [Task Foundations and Benchmarks](#task-foundations)
- [Topological Mapping and Planning](#topological-planning)
- [Scene Graphs and Instruction Constraints](#scene-graphs)
- [Semantic Maps and 3D Representations](#spatial-maps)
- [History, Memory, and Streaming](#memory-streaming)
- [Pretraining, Learning, and Adaptation](#reasoning-adaptation)
- [LLM/VLM Planning and Reasoning](#foundation-planners)
- [VLM/VLA Navigation Policies](#vlm-policies)
- [Data Augmentation and Visual Imagination](#imagination-data)
- [Real-World and Generalist Navigation](#generalist-real-world)
- [Aerial Vision-and-Language Navigation](#aerial-vln)


## Surveys

- <a id="paper-vln-taxonomy-survey"></a>★ [**VLN Taxonomy Survey**: Vision-language navigation: a survey and taxonomy](https://arxiv.org/pdf/2108.11544) · 2024, arXiv
- <a id="paper-foundation-model-survey"></a>[**Foundation-Model VLN Survey**: Vision-and-Language Navigation Today and Tomorrow: A Survey in the Era of Foundation Models](https://arxiv.org/abs/2407.07035) · 2024, arXiv

<a id="task-foundations"></a>

## Task Foundations and Benchmarks

- <a id="paper-r2r"></a>★ [**R2R**: Vision-and-Language Navigation: Interpreting visually-grounded navigation instructions in real environments](https://arxiv.org/abs/1711.07280) · 2018, CVPR · `DE` — Foundational viewpoint-graph benchmark; first released in 2017.
- <a id="paper-vln-ce"></a>[**VLN-CE**: Beyond the Nav-Graph: Vision-and-Language Navigation in Continuous Environments](https://arxiv.org/abs/2004.02857) · 2020, ECCV · `CE` — Introduces continuous-environment execution; low-level actions may still be discrete.
- <a id="paper-ha-vln"></a>[**HA-VLN**: HA-VLN 2.0: An Open Benchmark and Leaderboard for Human-Aware Navigation in Discrete and Continuous Environments with Dynamic Multi-Human Interactions](https://arxiv.org/pdf/2503.14229) · 2025, arXiv · `DE / CE` · [project](https://ha-vln-project.vercel.app/)
- <a id="paper-condvln"></a>[**CondVLN**: If, Then, Otherwise: Diagnosing Conditional Branching in Vision-Language Navigation](https://arxiv.org/abs/2608.17318) · 2026, arXiv · `Conditional instructions`

<a id="topological-planning"></a>

## Topological Mapping and Planning

- <a id="paper-duet"></a>★ [**DUET**: Think Global, Act Local: Dual-scale Graph Transformer for Vision-and-Language Navigation](https://arxiv.org/abs/2202.11742) · 2022, CVPR · `DE` — Classic global/local topological reasoning.
- <a id="paper-etpnav"></a>[**ETPNav**: Evolving Topological Planning for Vision-Language Navigation in Continuous Environments](https://arxiv.org/abs/2304.03047) · 2023, arXiv · `CE` · [code](https://github.com/MarSaKi/ETPNav) — First publicly released in 2023.
- <a id="paper-azhp"></a>[**AZHP**: Adaptive Zone-Aware Hierarchical Planner for Vision-Language Navigation](https://openaccess.thecvf.com/content/CVPR2023/papers/Gao_Adaptive_Zone-Aware_Hierarchical_Planner_for_Vision-Language_Navigation_CVPR_2023_paper.pdf) · 2023, CVPR · `DE`
- <a id="paper-etp-r1"></a>[**ETP-R1**: Evolving Topological Planning with Reinforcement Fine-tuning for Vision-Language Navigation in Continuous Environments](https://arxiv.org/abs/2512.20940) · 2025, arXiv · `CE` · [code](https://github.com/Cepillar/ETP-R1)
- <a id="paper-dgnav"></a>[**DGNav**: Dynamic Topology Awareness: Breaking the Granularity Rigidity in Vision-Language Navigation](https://arxiv.org/abs/2601.21751) · 2026, arXiv · `CE`

<a id="scene-graphs"></a>

## Scene Graphs and Instruction Constraints

- <a id="paper-entity-graph"></a>★ [**Entity-Graph VLN**: Language and Visual Entity Relationship Graph for Agent Navigation](https://arxiv.org/abs/2010.09304) · 2020, NeurIPS · `DE` — Early entity-relation model; not a persistent 3D scene map.
- <a id="paper-hsan"></a>[**HSAN**: Hierarchical Semantic-Augmented Navigation: Optimal Transport and Graph-Driven Reasoning for Vision-Language Navigation](https://papers.neurips.cc/paper_files/paper/2025/hash/592da1445a51e54a3987958b5831948f-Abstract-Conference.html) · 2025, NeurIPS · `CE`
- <a id="paper-fsr-vln"></a>[**FSR-VLN**: Fast and Slow Reasoning for Vision-Language Navigation with Hierarchical Multi-modal Scene Graph](https://arxiv.org/abs/2509.13733) · 2025, arXiv · `Real robot` — Requires a prebuilt static graph.
- <a id="paper-gc-vln"></a>[**GC-VLN**: Instruction as Graph Constraints for Training-free Vision-and-Language Navigation](https://arxiv.org/pdf/2509.10454) · 2025, CoRL · `CE / Real robot` · [project](https://bagh2178.github.io/GC-VLN/) · [code](https://github.com/bagh2178/GC-VLN) — Graph encodes instruction constraints.
- <a id="paper-vln-zero"></a>[**VLN-Zero**: Rapid Exploration and Cache-Enabled Neurosymbolic Vision-Language Planning for Zero-Shot Transfer in Robot Navigation](https://arxiv.org/abs/2509.18592) · 2025, arXiv · `Exploration → deployment` — Exploration precedes deployment.
- <a id="paper-spatialnav"></a>[**SpatialNav**: Leveraging Spatial Scene Graphs for Zero-Shot Vision-and-Language Navigation](https://arxiv.org/abs/2601.06806) · 2026, arXiv · `DE / CE` — Allows pre-exploration; CE results use sampled subsets.
- <a id="paper-dynavlm"></a>[**DyNaVLM**: Zero-Shot Vision-Language Navigation System with Dynamic Viewpoints and Self-Refining Graph Memory](https://arxiv.org/pdf/2506.15096) · 2025, arXiv · `GoalNav` — GOAT/ObjectNav evaluations, rather than route-following VLN.

<a id="spatial-maps"></a>

## Semantic Maps and 3D Representations

- <a id="paper-vlmaps"></a>★ [**VLMaps**: Visual Language Maps for Robot Navigation](https://arxiv.org/abs/2210.05714) · 2023, ICRA · `Spatial goals` — Spatial-language goals with a map built before queries.
- <a id="paper-hnr"></a>[**HNR**: Lookahead Exploration with Neural Radiance Representation for Continuous Vision-Language Navigation](https://arxiv.org/abs/2404.01943) · 2024, CVPR · `CE`
- <a id="paper-ovl-map"></a>[**OVL-MAP**: An Online Visual Language Map Approach for Vision-and-Language Navigation in Continuous Environments](https://labsun.org/pub/RAL2025_ovlmap.pdf) · 2025, RA-L · `CE`
- <a id="paper-g3d-lf"></a>[**g3D-LF**: Generalizable 3D-Language Feature Fields for Embodied Tasks](https://arxiv.org/abs/2411.17030) · 2025, CVPR · `CE / Multitask`
- <a id="paper-mapnav"></a>[**MapNav**: A Novel Memory Representation via Annotated Semantic Maps for Vision-and-Language Navigation](https://arxiv.org/pdf/2502.13451) · 2025, arXiv · `CE`
- <a id="paper-multimodal-spatial-language-maps"></a>[**Multimodal Spatial Language Maps**: Multimodal Spatial Language Maps for Robot Navigation and Manipulation](https://arxiv.org/pdf/2506.06862) · 2025, IJRR · `Spatial goals` · [project](https://mslmaps.github.io/)
- <a id="paper-dynam3d"></a>[**Dynam3D**: Dynamic Layered 3D Tokens Empower VLM for Vision-and-Language Navigation](https://arxiv.org/pdf/2505.11383) · 2025, arXiv · `CE` · [project](https://github.com/MrZihan/Dynam3D) — Posed RGB-D; includes pre-exploration variants.

<a id="memory-streaming"></a>

## History, Memory, and Streaming

- <a id="paper-hamt"></a>★ [**HAMT**: History Aware Multimodal Transformer for Vision-and-Language Navigation](https://arxiv.org/abs/2110.13309) · 2021, NeurIPS · `DE` — Classic long-history modeling.
- <a id="paper-recurrent-vln-bert"></a>[**Recurrent VLN-BERT**: A Recurrent Vision-and-Language BERT for Navigation](https://arxiv.org/abs/2011.13922) · 2021, CVPR · `DE`
- <a id="paper-cosmo"></a>[**COSMO**: Combination of Selective Memorization for Low-cost Vision-and-Language Navigation](https://arxiv.org/pdf/2503.24065) · 2025, arXiv · `DE / CE`
- <a id="paper-janusvln"></a>[**JanusVLN**: Decoupling Semantics and Spatiality with Dual Implicit Memory for Vision-Language Navigation](https://arxiv.org/pdf/2509.22548) · 2025, arXiv · `CE` · [project](https://miv-xjtu.github.io/JanusVLN.github.io/) · [code](https://github.com/MIV-XJTU/JanusVLN)
- <a id="paper-streamvln"></a>[**StreamVLN**: Streaming Vision-and-Language Navigation via SlowFast Context Modeling](https://arxiv.org/abs/2507.05240) · 2025, arXiv · `CE`
- <a id="paper-sr-vln"></a>[**SR-VLN**: Implicit Spatial Reasoning Vision-and-Language Navigation](https://www.mdpi.com/1424-8220/26/12/3809) · 2026, Sensors · `DE`

<a id="reasoning-adaptation"></a>

## Pretraining, Learning, and Adaptation

- <a id="paper-prevalent"></a>★ [**PREVALENT**: Towards Learning a Generic Agent for Vision-and-Language Navigation via Pre-training](https://arxiv.org/abs/2002.10638) · 2020, CVPR · `DE` — Foundational VLN pretraining.
- <a id="paper-atena"></a>[**ATENA**: Active Test-time Vision-Language Navigation](https://arxiv.org/pdf/2506.06630) · 2025, NeurIPS · `DE / CE` — Test-time parameter updates and outcome feedback.
- <a id="paper-flexvln"></a>[**FlexVLN**: Flexible Adaptation for Diverse Vision-and-Language Navigation Tasks](https://arxiv.org/pdf/2503.13966) · 2025, arXiv · `DE`
- <a id="paper-aux-think"></a>[**Aux-Think**: Exploring Reasoning Strategies for Data-Efficient Vision-Language Navigation](https://arxiv.org/pdf/2505.11886) · 2025, arXiv · `CE`

<a id="foundation-planners"></a>

## LLM/VLM Planning and Reasoning

- <a id="paper-navgpt"></a>★ [**NavGPT**: Explicit Reasoning in Vision-and-Language Navigation with Large Language Models](https://arxiv.org/abs/2305.16986) · 2024, AAAI · `DE` — Early LLM planning over textualized visual observations.
- <a id="paper-travel"></a>[**TRAVEL**: Training-Free Retrieval and Alignment for Vision-and-Language Navigation](https://arxiv.org/pdf/2502.07306) · 2025, arXiv · `Mapped environment` — Assumes a known environment map.
- <a id="paper-smartway"></a>[**SmartWay**: Enhanced Waypoint Prediction and Backtracking for Zero-Shot Vision-and-Language Navigation](https://arxiv.org/pdf/2503.10069) · 2025, arXiv · `CE` — Zero-shot navigator with a trained waypoint predictor.
- <a id="paper-vl-nav"></a>[**VL-Nav**: Neuro-Symbolic Reasoning-based Vision-Language Navigation](https://arxiv.org/pdf/2502.00931) · 2025, arXiv · `Real robot`

<a id="vlm-policies"></a>

## VLM/VLA Navigation Policies

- <a id="paper-navid"></a>★ [**NaVid**: Video-based VLM Plans the Next Step for Vision-and-Language Navigation](https://arxiv.org/pdf/2402.15852) · 2024, RSS · `CE` — Early video-to-action VLM; RGB-only inference.
- <a id="paper-correctnav"></a>[**CorrectNav**: Self-Correction Flywheel Empowers Vision-Language-Action Navigation Model](https://arxiv.org/pdf/2508.10416) · 2025, arXiv · `CE` · [project](https://correctnav.github.io/)
- <a id="paper-dualvln"></a>[**DualVLN**: Ground Slow, Move Fast: A Dual-System Foundation Model for Generalizable Vision-and-Language Navigation](https://arxiv.org/pdf/2512.08186) · 2025, arXiv · `CE / Real robot` · [project](https://internrobotics.github.io/internvla-n1-dualvln.github.io/) · [code](https://github.com/InternRobotics/InternNav)

<a id="imagination-data"></a>

## Data Augmentation and Visual Imagination

- <a id="paper-speaker-follower"></a>★ [**Speaker-Follower**: Speaker-Follower Models for Vision-and-Language Navigation](https://arxiv.org/abs/1806.02724) · 2018, NeurIPS · `DE` — Classic synthetic-instruction augmentation.
- <a id="paper-panogen-"></a>[**PanoGen++**: Domain-Adapted Text-Guided Panoramic Environment Generation for Vision-and-Language Navigation](https://arxiv.org/pdf/2503.09938) · 2025, arXiv · `DE`
- <a id="paper-ram"></a>[**RAM**: Unseen from Seen: Rewriting Observation-Instruction Using Foundation Models for Augmenting Vision-Language Navigation](https://arxiv.org/pdf/2503.18065) · 2025, arXiv · `DE / CE` · [project](https://github.com/SaDil13/VLN-RAM)
- <a id="paper-vln-imagine"></a>[**VLN-Imagine**: Do Visual Imaginations Improve Vision-and-Language Navigation Agents?](https://arxiv.org/pdf/2503.16394) · 2025, arXiv · `DE` · [project](https://www.akhilperincherry.com/VLN-Imagine-website/)
- <a id="paper-vista"></a>[**VISTA**: Generative Visual Imagination for Vision-and-Language Navigation](https://arxiv.org/pdf/2505.07868) · 2025, arXiv · `DE / GoalNav`

<a id="generalist-real-world"></a>

## Real-World and Generalist Navigation

- <a id="paper-mobility-vla"></a>★ [**Mobility VLA**: Multimodal Instruction Navigation with Long-Context VLMs and Topological Graphs](https://arxiv.org/pdf/2407.07775) · 2024, arXiv · `Real robot` — Representative system; requires a tour video and offline topology.
- <a id="paper-navila"></a>[**NaVILA**: Legged Robot Vision-Language-Action Model for Navigation](https://arxiv.org/pdf/2412.04453) · 2025, RSS · `Legged robot` · [project](https://navila-bot.github.io/)
- <a id="paper-canvas"></a>[**CANVAS**: Commonsense-Aware Navigation System for Intuitive Human-Robot Interaction](https://arxiv.org/abs/2410.01273) · 2024, arXiv · `Human–robot interaction` · [project](https://worv-ai.github.io/canvas/) · [code](https://github.com/worv-ai/canvas)
- <a id="paper-opennav"></a>[**OpenNav**: Open-World Navigation with Multimodal Large Language Models](https://arxiv.org/pdf/2507.18033) · 2025, arXiv · `Outdoor / Real robot` · [project](https://trailab.github.io/OpenNav-website/)
- <a id="paper-lovon"></a>[**LOVON**: Legged Open-Vocabulary Object Navigator](https://arxiv.org/pdf/2507.06747) · 2025, arXiv · `Legged robot` · [project](https://daojiepeng.github.io/LOVON/) — Open-vocabulary object missions.
- <a id="paper-omnivla"></a>[**OmniVLA**: An Omni-Modal Vision-Language-Action Model for Robot Navigation](https://arxiv.org/pdf/2509.19480) · 2025, arXiv · `Multimodal goals` · [project](https://omnivla-nav.github.io/) · [code](https://github.com/NHirose/OmniVLA)
- <a id="paper-gvnav"></a>[**GVNav**: Ground-level Viewpoint Vision-and-Language Navigation in Continuous Environments](https://arxiv.org/pdf/2502.19024) · 2025, arXiv · `CE / Legged robot`
- <a id="paper-octonav"></a>[**OctoNav**: Towards Generalist Embodied Navigation](https://arxiv.org/pdf/2506.09839) · 2025, arXiv · `CE / Multitask` · [project](https://buaa-colalab.github.io/OctoNav/)
- <a id="paper-navfom"></a>[**NavFoM**: Embodied Navigation Foundation Model](https://arxiv.org/pdf/2509.12129) · 2025, arXiv · `CE / Multitask` · [project](https://pku-epic.github.io/NavFoM-Web/)

<a id="aerial-vln"></a>

## Aerial Vision-and-Language Navigation

- <a id="paper-aerialvln"></a>★ [**AerialVLN**: Vision-and-Language Navigation for UAVs](https://arxiv.org/abs/2308.06735) · 2023, ICCV · `Aerial / CE` — Foundational aerial benchmark.
- <a id="paper-citynavagent"></a>[**CityNavAgent**: Aerial Vision-and-Language Navigation with Hierarchical Semantic Planning and Global Memory](https://arxiv.org/pdf/2505.05622) · 2025, arXiv · `Aerial` · [project](https://github.com/VinceOuti/CityNavAgent)
- <a id="paper-vlfly"></a>[**VLFly**: Grounded Vision-Language Navigation for UAVs with Open-Vocabulary Goal Understanding](https://arxiv.org/pdf/2506.10756) · 2025, arXiv · `Aerial` · [project](https://zzzzzyh111.github.io/VLFly/)
- <a id="paper-openfly"></a>[**OpenFly**: A comprehensive platform for aerial vision-language navigation](https://arxiv.org/pdf/2502.18041) · 2025, arXiv · `Aerial / CE`

## Contributing

Suggest papers through an [Issue](https://github.com/Stagnation47/Awsome-VLN/issues) or [Pull Request](https://github.com/Stagnation47/Awsome-VLN/pulls). Include the title, year, venue or arXiv, paper/code links, primary category, and any important evaluation assumptions.

## Acknowledgements

Adapted from [awesome-embodied-vla-va-vln](https://github.com/jonyzhang2023/awesome-embodied-vla-va-vln). Thanks to the original maintainers and contributors.
