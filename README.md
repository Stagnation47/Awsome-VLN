<div align="center">

# 🚶 Awesome VLN

**A Curated Collection of Vision-and-Language Navigation Research**

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
[![Papers](https://img.shields.io/badge/Papers-94-0984e3?style=for-the-badge&logo=google-scholar&logoColor=white)](#tasks-and-benchmarks)
[![Last Commit](https://img.shields.io/github/last-commit/Stagnation47/Awsome-VLN?style=for-the-badge&color=00b894)](https://github.com/Stagnation47/Awsome-VLN/commits/main)
[![Stars](https://img.shields.io/github/stars/Stagnation47/Awsome-VLN?style=for-the-badge&color=fdcb6e&logo=github)](https://github.com/Stagnation47/Awsome-VLN/stargazers)
[![Forks](https://img.shields.io/github/forks/Stagnation47/Awsome-VLN?style=for-the-badge&color=e17055&logo=github)](https://github.com/Stagnation47/Awsome-VLN/forks)

*Papers, models, and benchmarks for vision-and-language navigation.*

</div>

## Contents

- [Surveys](#surveys)
- **Tasks and Benchmarks**
  - [Indoor Benchmarks and Instruction Variants](#task-foundations)
  - [Continuous and Dynamic Environments](#continuous-navigation)
  - [Dialog and Interactive Navigation](#dialog-navigation)
- **Methods**
  - [Instruction Grounding and Progress Monitoring](#grounding-progress)
  - [Topological Mapping and Planning](#topological-planning)
  - [Scene Graphs and Instruction Constraints](#scene-graphs)
  - [Semantic Maps and 3D Representations](#spatial-maps)
  - [History, Memory, and Streaming](#memory-streaming)
  - [Pretraining, Learning, and Adaptation](#reasoning-adaptation)
  - [LLM/VLM Planning and Reasoning](#foundation-planners)
  - [VLM/VLA Navigation Policies](#vlm-policies)
  - [Data Augmentation and Instruction Generation](#imagination-data)
  - [World Models and Predictive Planning](#world-models)
- **Embodiments and Deployment**
  - [Outdoor and Street-View Navigation](#outdoor-navigation)
  - [Real-World and Generalist Navigation](#generalist-real-world)
  - [Aerial Vision-and-Language Navigation](#aerial-vln)

<a id="surveys"></a>

## Surveys

- <a id="paper-vln-taxonomy-survey"></a>★ [**VLN Taxonomy Survey**: Vision-language navigation: a survey and taxonomy](https://arxiv.org/pdf/2108.11544) · 2024, arXiv
- <a id="paper-foundation-model-survey"></a>[**Foundation-Model VLN Survey**: Vision-and-Language Navigation Today and Tomorrow: A Survey in the Era of Foundation Models](https://arxiv.org/abs/2407.07035) · 2024, arXiv

## Tasks and Benchmarks

<a id="task-foundations"></a>

### Indoor Benchmarks and Instruction Variants

- <a id="paper-r2r"></a>★ [**R2R**: Vision-and-Language Navigation: Interpreting visually-grounded navigation instructions in real environments](https://arxiv.org/abs/1711.07280) · 2018, CVPR · `DE` · [code](https://github.com/peteanderson80/Matterport3DSimulator) — Foundational viewpoint-graph benchmark; first released in 2017.
- <a id="paper-r4r"></a>[**R4R**: Stay on the Path: Instruction Fidelity in Vision-and-Language Navigation](https://arxiv.org/abs/1905.12255) · 2019, ACL · `DE` · [code](https://github.com/google-research/google-research/tree/master/r4r) — Longer routes and instruction-fidelity evaluation.
- <a id="paper-reverie"></a>[**REVERIE**: Remote Embodied Visual Referring Expression in Real Indoor Environments](https://arxiv.org/abs/1904.10151) · 2020, CVPR · `DE / Referring goal` — Navigate to and identify a remotely described object.
- <a id="paper-rxr"></a>[**RxR**: Room-Across-Room: Multilingual Vision-and-Language Navigation with Dense Spatiotemporal Grounding](https://aclanthology.org/2020.emnlp-main.356/) · 2020, EMNLP · `DE / Multilingual` — English, Hindi, and Telugu with timed visual grounding.
- <a id="paper-cross-lingual-vln"></a>[**Cross-Lingual VLN**: Cross-Lingual Vision-Language Navigation](https://arxiv.org/abs/1910.11301) · 2019, arXiv · `DE / Multilingual` · [code](https://github.com/zzxslp/Crosslingual-VLN)
- <a id="paper-condvln"></a>[**CondVLN**: If, Then, Otherwise: Diagnosing Conditional Branching in Vision-Language Navigation](https://arxiv.org/abs/2608.17318) · 2026, arXiv · `Conditional instructions`
- <a id="paper-lh-vln"></a>[**LH-VLN**: Towards Long-Horizon Vision-Language Navigation: Platform, Benchmark and Method](https://openaccess.thecvf.com/content/CVPR2025/html/Song_Towards_Long-Horizon_Vision-Language_Navigation_Platform_Benchmark_and_Method_CVPR_2025_paper.html) · 2025, CVPR · `CCF-A` · `Long-horizon` — NavGen platform and LHPR-VLN benchmark.

<a id="continuous-navigation"></a>

### Continuous and Dynamic Environments

- <a id="paper-vln-ce"></a>★ [**VLN-CE**: Beyond the Nav-Graph: Vision-and-Language Navigation in Continuous Environments](https://arxiv.org/abs/2004.02857) · 2020, ECCV · `CE` · [code](https://github.com/jacobkrantz/VLN-CE) — Introduces continuous-environment execution; low-level actions may still be discrete.
- <a id="paper-robo-vln"></a>[**Robo-VLN**: Hierarchical Cross-Modal Agent for Robotics Vision-and-Language Navigation](https://arxiv.org/abs/2104.10674) · 2021, ICRA · `CE / Robot control` · [code](https://github.com/GT-RIPL/robo-vln) · [project](https://zubair-irshad.github.io/projects/robo-vln.html) — Continuous-valued control in reconstructed environments.
- <a id="paper-ha-vln"></a>[**HA-VLN**: HA-VLN 2.0: An Open Benchmark and Leaderboard for Human-Aware Navigation in Discrete and Continuous Environments with Dynamic Multi-Human Interactions](https://arxiv.org/pdf/2503.14229) · 2025, arXiv · `DE / CE` · [project](https://ha-vln-project.vercel.app/)

<a id="dialog-navigation"></a>

### Dialog and Interactive Navigation

- <a id="paper-cvdn"></a>★ [**CVDN**: Vision-and-Dialog Navigation](https://arxiv.org/abs/1907.04957) · 2019, CoRL · `DE / Dialog` · [project](https://cvdn.dev/) — Foundational cooperative dialog-navigation benchmark.
- <a id="paper-talk-the-walk"></a>[**Talk the Walk**: Navigating New York City through Grounded Dialogue](https://arxiv.org/abs/1807.03367) · 2019, arXiv · `Outdoor / Dialog` · [code](https://github.com/facebookresearch/talkthewalk)
- <a id="paper-vnla"></a>[**VNLA**: Vision-based Navigation with Language-based Assistance via Imitation Learning with Indirect Intervention](https://arxiv.org/abs/1812.04155) · 2019, CVPR · `DE / Assistance` · [code](https://github.com/debadeepta/vnla)
- <a id="paper-anna"></a>[**HANNA**: Help, Anna! Visual Navigation with Natural Multimodal Assistance via Retrospective Curiosity-Encouraging Imitation Learning](https://arxiv.org/abs/1909.01871) · 2019, EMNLP · `DE / Assistance` · [code](https://github.com/khanhptnk/hanna)
- <a id="paper-just-ask"></a>[**Just Ask**: An Interactive Learning Framework for Vision and Language Navigation](https://arxiv.org/abs/1912.00915) · 2020, AAAI · `DE / Interaction`
- <a id="paper-dialnav"></a>[**DialNav**: Multi-turn Dialog Navigation with a Remote Guide](https://openaccess.thecvf.com/content/ICCV2025/papers/Han_DialNav_Multi-turn_Dialog_Navigation_with_a_Remote_Guide_ICCV_2025_paper.pdf) · 2025, ICCV · `CCF-A` · `Dialog` — Remote guide must infer the navigator's location.

## Methods

<a id="grounding-progress"></a>

### Instruction Grounding and Progress Monitoring

- <a id="paper-self-monitoring"></a>★ [**Self-Monitoring** Navigation Agent via Auxiliary Progress Estimation](https://arxiv.org/abs/1901.03035) · 2019, ICLR · `DE` · [code](https://github.com/chihyaoma/selfmonitoring-agent) · [project](https://chihyaoma.github.io/project/2018/09/27/selfmonitoring.html) — Classic auxiliary progress estimation.
- <a id="paper-rcm"></a>[**RCM**: Reinforced Cross-Modal Matching and Self-Supervised Imitation Learning for Vision-Language Navigation](https://arxiv.org/abs/1811.10092) · 2019, CVPR · `DE` — Includes a separate pre-exploration/self-imitation setting.
- <a id="paper-regretful-agent"></a>[**Regretful Agent**: The Regretful Agent: Heuristic-Aided Navigation through Progress Estimation](https://arxiv.org/abs/1903.01602) · 2019, CVPR · `DE` · [code](https://github.com/chihyaoma/regretful-agent) · [project](https://chihyaoma.github.io/project/2019/02/25/regretful.html)
- <a id="paper-progress-think"></a>[**Progress-Think**: Semantic Progress Reasoning for Vision-Language Navigation](https://openaccess.thecvf.com/content/CVPR2026/html/Wang_Progress-Think_Semantic_Progress_Reasoning_for_Vision-Language_Navigation_CVPR_2026_paper.html) · 2026, CVPR · `CCF-A` · `CE` — Instruction-style progress reasoning guides the policy.
- <a id="paper-awarevln"></a>[**AwareVLN**: Reasoning with Self-awareness for Vision-Language Navigation](https://openaccess.thecvf.com/content/CVPR2026/html/Guo_AwareVLN_Reasoning_with_Self-awareness_for_Vision-Language_Navigation_CVPR_2026_paper.html) · 2026, CVPR · `CCF-A` · `CE` · [project](https://gwxuan.github.io/AwareVLN/) — Structured reasoning about progress, deviation, and stopping.

<a id="topological-planning"></a>

### Topological Mapping and Planning

- <a id="paper-duet"></a>★ [**DUET**: Think Global, Act Local: Dual-scale Graph Transformer for Vision-and-Language Navigation](https://arxiv.org/abs/2202.11742) · 2022, CVPR · `DE` — Classic global/local topological reasoning.
- <a id="paper-etpnav"></a>[**ETPNav**: Evolving Topological Planning for Vision-Language Navigation in Continuous Environments](https://arxiv.org/abs/2304.03047) · 2024, [TPAMI](https://ieeexplore.ieee.org/document/10495141/) · `CCF-A` · `CE` · [code](https://github.com/MarSaKi/ETPNav) — First released in 2023; online journal publication in 2024, issue dated 2025.
- <a id="paper-azhp"></a>[**AZHP**: Adaptive Zone-Aware Hierarchical Planner for Vision-Language Navigation](https://openaccess.thecvf.com/content/CVPR2023/papers/Gao_Adaptive_Zone-Aware_Hierarchical_Planner_for_Vision-Language_Navigation_CVPR_2023_paper.pdf) · 2023, CVPR · `DE`
- <a id="paper-etp-r1"></a>[**ETP-R1**: Evolving Topological Planning with Reinforcement Fine-tuning for Vision-Language Navigation in Continuous Environments](https://arxiv.org/abs/2512.20940) · 2025, arXiv · `CE` · [code](https://github.com/Cepillar/ETP-R1)
- <a id="paper-dgnav"></a>[**DGNav**: Dynamic Topology Awareness: Breaking the Granularity Rigidity in Vision-Language Navigation](https://arxiv.org/abs/2601.21751) · 2026, arXiv · `CE`

<a id="scene-graphs"></a>

### Scene Graphs and Instruction Constraints

- <a id="paper-entity-graph"></a>★ [**Entity-Graph VLN**: Language and Visual Entity Relationship Graph for Agent Navigation](https://arxiv.org/abs/2010.09304) · 2020, NeurIPS · `DE` — Early entity-relation model; not a persistent 3D scene map.
- <a id="paper-hsan"></a>[**HSAN**: Hierarchical Semantic-Augmented Navigation: Optimal Transport and Graph-Driven Reasoning for Vision-Language Navigation](https://papers.neurips.cc/paper_files/paper/2025/hash/592da1445a51e54a3987958b5831948f-Abstract-Conference.html) · 2025, NeurIPS · `CE`
- <a id="paper-fsr-vln"></a>[**FSR-VLN**: Fast and Slow Reasoning for Vision-Language Navigation with Hierarchical Multi-modal Scene Graph](https://arxiv.org/abs/2509.13733) · 2025, arXiv · `Real robot` — Requires a prebuilt static graph.
- <a id="paper-gc-vln"></a>[**GC-VLN**: Instruction as Graph Constraints for Training-free Vision-and-Language Navigation](https://arxiv.org/pdf/2509.10454) · 2025, CoRL · `CE / Real robot` · [project](https://bagh2178.github.io/GC-VLN/) · [code](https://github.com/bagh2178/GC-VLN) — Graph encodes instruction constraints.
- <a id="paper-vln-zero"></a>[**VLN-Zero**: Rapid Exploration and Cache-Enabled Neurosymbolic Vision-Language Planning for Zero-Shot Transfer in Robot Navigation](https://arxiv.org/abs/2509.18592) · 2025, arXiv · `Exploration → deployment` — Exploration precedes deployment.
- <a id="paper-spatialnav"></a>[**SpatialNav**: Leveraging Spatial Scene Graphs for Zero-Shot Vision-and-Language Navigation](https://arxiv.org/abs/2601.06806) · 2026, arXiv · `DE / CE` — Allows pre-exploration; CE results use sampled subsets.
- <a id="paper-dynavlm"></a>[**DyNaVLM**: Zero-Shot Vision-Language Navigation System with Dynamic Viewpoints and Self-Refining Graph Memory](https://arxiv.org/pdf/2506.15096) · 2025, arXiv · `GoalNav` — GOAT/ObjectNav evaluations, rather than route-following VLN.

<a id="spatial-maps"></a>

### Semantic Maps and 3D Representations

- <a id="paper-vlmaps"></a>★ [**VLMaps**: Visual Language Maps for Robot Navigation](https://arxiv.org/abs/2210.05714) · 2023, ICRA · `Spatial goals` — Spatial-language goals with a map built before queries.
- <a id="paper-ovl-map"></a>[**OVL-MAP**: An Online Visual Language Map Approach for Vision-and-Language Navigation in Continuous Environments](https://labsun.org/pub/RAL2025_ovlmap.pdf) · 2025, RA-L · `CE`
- <a id="paper-g3d-lf"></a>[**g3D-LF**: Generalizable 3D-Language Feature Fields for Embodied Tasks](https://arxiv.org/abs/2411.17030) · 2025, CVPR · `CE / Multitask`
- <a id="paper-mapnav"></a>[**MapNav**: A Novel Memory Representation via Annotated Semantic Maps for Vision-and-Language Navigation](https://arxiv.org/pdf/2502.13451) · 2025, arXiv · `CE`
- <a id="paper-multimodal-spatial-language-maps"></a>[**Multimodal Spatial Language Maps**: Multimodal Spatial Language Maps for Robot Navigation and Manipulation](https://arxiv.org/pdf/2506.06862) · 2025, IJRR · `Spatial goals` · [project](https://mslmaps.github.io/)
- <a id="paper-dynam3d"></a>[**Dynam3D**: Dynamic Layered 3D Tokens Empower VLM for Vision-and-Language Navigation](https://arxiv.org/pdf/2505.11383) · 2025, arXiv · `CE` · [project](https://github.com/MrZihan/Dynam3D) — Posed RGB-D; includes pre-exploration variants.
- <a id="paper-monovln"></a>[**monoVLN**: Bridging the Observation Gap between Monocular and Panoramic Vision and Language Navigation](https://openaccess.thecvf.com/content/ICCV2025/papers/Lu_monoVLN_Bridging_the_Observation_Gap_between_Monocular_and_Panoramic_Vision_ICCV_2025_paper.pdf) · 2025, ICCV · `CCF-A` · `CE / RGB-D` — 3D Gaussian completion and uncertainty-aware active perception.
- <a id="paper-gaussian-map"></a>[**3D Gaussian Map** with Open-Set Semantic Grouping for Vision-Language Navigation](https://openaccess.thecvf.com/content/ICCV2025/html/Gao_3D_Gaussian_Map_with_Open-Set_Semantic_Grouping_for_Vision-Language_Navigation_ICCV_2025_paper.html) · 2025, ICCV · `CCF-A` · `DE / RGB-D` — Online geometry and object-level semantic grouping.
- <a id="paper-hsgm"></a>[**HSGM**: Bridging the 2D-3D Gap: A Hierarchical Semantic-Geometric Map for Vision Language Navigation](https://openaccess.thecvf.com/content/CVPR2026/html/Li_Bridging_the_2D-3D_Gap_A_Hierarchical_Semantic-Geometric_Map_for_Vision_CVPR_2026_paper.html) · 2026, CVPR · `CCF-A` · `CE` · [code](https://github.com/Teacher-Tom/HSGM_public) — Hierarchical map connects VLM waypoints to classical control.

<a id="memory-streaming"></a>

### History, Memory, and Streaming

- <a id="paper-hamt"></a>★ [**HAMT**: History Aware Multimodal Transformer for Vision-and-Language Navigation](https://arxiv.org/abs/2110.13309) · 2021, NeurIPS · `DE` — Classic long-history modeling.
- <a id="paper-recurrent-vln-bert"></a>[**Recurrent VLN-BERT**: A Recurrent Vision-and-Language BERT for Navigation](https://arxiv.org/abs/2011.13922) · 2021, CVPR · `DE`
- <a id="paper-chasing-ghosts"></a>[**Chasing Ghosts**: Instruction Following as Bayesian State Tracking](https://arxiv.org/abs/1907.02022) · 2019, NeurIPS · `DE` · [code](https://github.com/batra-mlp-lab/vln-chasing-ghosts)
- <a id="paper-cosmo"></a>[**COSMO**: Combination of Selective Memorization for Low-cost Vision-and-Language Navigation](https://arxiv.org/pdf/2503.24065) · 2025, arXiv · `DE / CE`
- <a id="paper-janusvln"></a>[**JanusVLN**: Decoupling Semantics and Spatiality with Dual Implicit Memory for Vision-Language Navigation](https://arxiv.org/pdf/2509.22548) · 2025, arXiv · `CE` · [project](https://miv-xjtu.github.io/JanusVLN.github.io/) · [code](https://github.com/MIV-XJTU/JanusVLN)
- <a id="paper-streamvln"></a>[**StreamVLN**: Streaming Vision-and-Language Navigation via SlowFast Context Modeling](https://arxiv.org/abs/2507.05240) · 2025, arXiv · `CE`
- <a id="paper-sr-vln"></a>[**SR-VLN**: Implicit Spatial Reasoning Vision-and-Language Navigation](https://www.mdpi.com/1424-8220/26/12/3809) · 2026, Sensors · `DE`
- <a id="paper-esceme"></a>[**ESceme**: Vision-and-Language Navigation with Episodic Scene Memory](https://link.springer.com/article/10.1007/s11263-024-02159-8) · 2025, IJCV · `CCF-A` · `DE` · [code](https://github.com/qizhust/esceme) — Memory persists across episodes; online publication in 2024.

<a id="reasoning-adaptation"></a>

### Pretraining, Learning, and Adaptation

- <a id="paper-prevalent"></a>★ [**PREVALENT**: Towards Learning a Generic Agent for Vision-and-Language Navigation via Pre-training](https://arxiv.org/abs/2002.10638) · 2020, CVPR · `DE` · [code](https://github.com/weituo12321/PREVALENT) — Foundational VLN pretraining.
- <a id="paper-vln-bert"></a>[**VLN-BERT**: Improving Vision-and-Language Navigation with Image-Text Pairs from the Web](https://arxiv.org/abs/2004.14973) · 2020, ECCV · `DE / Path ranking` — Web-pretrained path ranking; distinct from Recurrent VLN-BERT.
- <a id="paper-atena"></a>[**ATENA**: Active Test-time Vision-Language Navigation](https://arxiv.org/pdf/2506.06630) · 2025, NeurIPS · `DE / CE` — Test-time parameter updates and outcome feedback.
- <a id="paper-flexvln"></a>[**FlexVLN**: Flexible Adaptation for Diverse Vision-and-Language Navigation Tasks](https://arxiv.org/pdf/2503.13966) · 2025, arXiv · `DE`
- <a id="paper-aux-think"></a>[**Aux-Think**: Exploring Reasoning Strategies for Data-Efficient Vision-Language Navigation](https://arxiv.org/pdf/2505.11886) · 2025, [NeurIPS](https://papers.nips.cc/paper_files/paper/2025/hash/2c90bf5bffe6497730ecade3a3a37458-Abstract-Conference.html) · `CCF-A` · `CE`

<a id="foundation-planners"></a>

### LLM/VLM Planning and Reasoning

- <a id="paper-navgpt"></a>★ [**NavGPT**: Explicit Reasoning in Vision-and-Language Navigation with Large Language Models](https://arxiv.org/abs/2305.16986) · 2024, AAAI · `DE` — Early LLM planning over textualized visual observations.
- <a id="paper-navcot"></a>[**NavCoT**: Boosting LLM-Based Vision-and-Language Navigation via Learning Disentangled Reasoning](https://ieeexplore.ieee.org/document/10938647/) · 2025, TPAMI · `CCF-A` · `DE` — Disentangled reasoning with in-domain fine-tuning.
- <a id="paper-travel"></a>[**TRAVEL**: Training-Free Retrieval and Alignment for Vision-and-Language Navigation](https://arxiv.org/pdf/2502.07306) · 2025, arXiv · `Mapped environment` — Assumes a known environment map.
- <a id="paper-smartway"></a>[**SmartWay**: Enhanced Waypoint Prediction and Backtracking for Zero-Shot Vision-and-Language Navigation](https://arxiv.org/pdf/2503.10069) · 2025, arXiv · `CE` — Zero-shot navigator with a trained waypoint predictor.
- <a id="paper-vl-nav"></a>[**VL-Nav**: Neuro-Symbolic Reasoning-based Vision-Language Navigation](https://arxiv.org/pdf/2502.00931) · 2025, arXiv · `Real robot`
- <a id="paper-profocus"></a>[**ProFocus**: Proactive Perception and Focused Reasoning in Vision-and-Language Navigation](https://openaccess.thecvf.com/content/CVPR2026/html/Xue_ProFocus_Proactive_Perception_and_Focused_Reasoning_in_Vision-and-Language_Navigation_CVPR_2026_paper.html) · 2026, CVPR · `CCF-A` · `DE` — Training-free perception queries and tree-search reasoning.

<a id="vlm-policies"></a>

### VLM/VLA Navigation Policies

- <a id="paper-navid"></a>★ [**NaVid**: Video-based VLM Plans the Next Step for Vision-and-Language Navigation](https://arxiv.org/pdf/2402.15852) · 2024, RSS · `CE` — Early video-to-action VLM; RGB-only inference.
- <a id="paper-correctnav"></a>[**CorrectNav**: Self-Correction Flywheel Empowers Vision-Language-Action Navigation Model](https://arxiv.org/pdf/2508.10416) · 2026, [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/38942) · `CCF-A` · `CE` · [project](https://correctnav.github.io/)
- <a id="paper-dualvln"></a>[**DualVLN**: Ground Slow, Move Fast: A Dual-System Foundation Model for Generalizable Vision-and-Language Navigation](https://arxiv.org/pdf/2512.08186) · 2025, arXiv · `CE / Real robot` · [project](https://internrobotics.github.io/internvla-n1-dualvln.github.io/) · [code](https://github.com/InternRobotics/InternNav)

<a id="imagination-data"></a>

### Data Augmentation and Instruction Generation

- <a id="paper-speaker-follower"></a>★ [**Speaker-Follower**: Speaker-Follower Models for Vision-and-Language Navigation](https://arxiv.org/abs/1806.02724) · 2018, NeurIPS · `DE` · [code](https://github.com/ronghanghu/speaker_follower) — Classic synthetic-instruction augmentation.
- <a id="paper-envdrop"></a>[**EnvDrop**: Learning to Navigate Unseen Environments: Back Translation with Environmental Dropout](https://arxiv.org/abs/1904.04195) · 2019, NAACL · `DE` · [code](https://github.com/airsplay/R2R-EnvDrop)
- <a id="paper-panogen-"></a>[**PanoGen++**: Domain-Adapted Text-Guided Panoramic Environment Generation for Vision-and-Language Navigation](https://arxiv.org/pdf/2503.09938) · 2025, arXiv · `DE`
- <a id="paper-ram"></a>[**RAM**: Unseen from Seen: Rewriting Observation-Instruction Using Foundation Models for Augmenting Vision-Language Navigation](https://arxiv.org/pdf/2503.18065) · 2025, arXiv · `DE / CE` · [project](https://github.com/SaDil13/VLN-RAM)
- <a id="paper-vln-imagine"></a>[**VLN-Imagine**: Do Visual Imaginations Improve Vision-and-Language Navigation Agents?](https://arxiv.org/pdf/2503.16394) · 2025, [CVPR](https://openaccess.thecvf.com/content/CVPR2025/html/Perincherry_Do_Visual_Imaginations_Improve_Vision-and-Language_Navigation_Agents_CVPR_2025_paper.html) · `CCF-A` · `DE` · [project](https://www.akhilperincherry.com/VLN-Imagine-website/)
- <a id="paper-roomtour3d"></a>[**RoomTour3D**: Geometry-Aware Video-Instruction Tuning for Embodied Navigation](https://openaccess.thecvf.com/content/CVPR2025/html/Han_RoomTour3D_Geometry-Aware_Video-Instruction_Tuning_for_Embodied_Navigation_CVPR_2025_paper.html) · 2025, CVPR · `CCF-A` · `Video data` — Training data from real-world room-tour videos.

<a id="world-models"></a>

### World Models and Predictive Planning

- <a id="paper-look-before-you-leap"></a>★ [**Look Before You Leap**: Bridging Model-Free and Model-Based Reinforcement Learning for Planned-Ahead Vision-and-Language Navigation](https://arxiv.org/abs/1803.07729) · 2018, ECCV · `DE` — Early model-based lookahead for VLN.
- <a id="paper-hnr"></a>[**HNR**: Lookahead Exploration with Neural Radiance Representation for Continuous Vision-Language Navigation](https://arxiv.org/abs/2404.01943) · 2024, CVPR · `CE`
- <a id="paper-vista"></a>[**VISTA**: Generative Visual Imagination for Vision-and-Language Navigation](https://arxiv.org/pdf/2505.07868) · 2025, arXiv · `DE / GoalNav`
- <a id="paper-navmorph"></a>[**NavMorph**: A Self-Evolving World Model for Vision-and-Language Navigation in Continuous Environments](https://openaccess.thecvf.com/content/ICCV2025/papers/Yao_NavMorph_A_Self-Evolving_World_Model_for_Vision-and-Language_Navigation_in_Continuous_ICCV_2025_paper.pdf) · 2025, ICCV · `CCF-A` · `CE` — Latent dynamics and contextual memory update during navigation.

## Embodiments and Deployment

<a id="outdoor-navigation"></a>

### Outdoor and Street-View Navigation

- <a id="paper-touchdown"></a>★ [**Touchdown**: Natural Language Navigation and Spatial Reasoning in Visual Street Environments](https://arxiv.org/abs/1811.12354) · 2019, CVPR · `Outdoor / DE` · [code](https://github.com/lil-lab/touchdown) · [project](https://sites.google.com/view/streetlearn/touchdown) — Foundational street-view instruction-following benchmark.
- <a id="paper-streetlearn"></a>[**StreetLearn**: Learning To Follow Directions in Street View](https://arxiv.org/abs/1903.00401) · 2020, AAAI · `Outdoor / DE` · [project](https://sites.google.com/view/streetlearn/aaai-2020)
- <a id="paper-talk2nav"></a>[**Talk2Nav**: Long-Range Vision-and-Language Navigation with Dual Attention and Spatial Memory](https://arxiv.org/abs/1910.02029) · 2019, arXiv · `Outdoor` · [project](https://people.ee.ethz.ch/~arunv/talk2nav.html)
- <a id="paper-drivevln"></a>[**DriveVLN**: Towards Mapless Vision-and-Language Navigation in Autonomous Driving](https://openaccess.thecvf.com/content/CVPR2026/papers/Guo_DriveVLN_Towards_Mapless_Vision-and-Language_Navigation_in_Autonomous_Driving_CVPR_2026_paper.pdf) · 2026, CVPR · `CCF-A` · `Driving / Language goals` — Mapless vehicle navigation with closed-loop CARLA evaluation.

<a id="generalist-real-world"></a>

### Real-World and Generalist Navigation

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

### Aerial Vision-and-Language Navigation

- <a id="paper-aerialvln"></a>★ [**AerialVLN**: Vision-and-Language Navigation for UAVs](https://arxiv.org/abs/2308.06735) · 2023, ICCV · `Aerial / CE` — Foundational aerial benchmark.
- <a id="paper-citynavagent"></a>[**CityNavAgent**: Aerial Vision-and-Language Navigation with Hierarchical Semantic Planning and Global Memory](https://arxiv.org/pdf/2505.05622) · 2025, arXiv · `Aerial` · [project](https://github.com/VinceOuti/CityNavAgent)
- <a id="paper-vlfly"></a>[**VLFly**: Grounded Vision-Language Navigation for UAVs with Open-Vocabulary Goal Understanding](https://arxiv.org/pdf/2506.10756) · 2025, arXiv · `Aerial` · [project](https://zzzzzyh111.github.io/VLFly/)
- <a id="paper-openfly"></a>[**OpenFly**: A comprehensive platform for aerial vision-language navigation](https://arxiv.org/pdf/2502.18041) · 2025, arXiv · `Aerial / CE`
- <a id="paper-htnav"></a>[**HTNav**: A Hybrid Navigation Framework with Tiered Structure for Urban Aerial Vision-and-Language Navigation](https://openaccess.thecvf.com/content/CVPR2026/html/Fan_HTNav_A_Hybrid_Navigation_Framework_with_Tiered_Structure_for_Urban_CVPR_2026_paper.html) · 2026, CVPR · `CCF-A` · `Aerial` — Hierarchical IL/RL on CityNav.

## Contributing

Suggest papers through an [Issue](https://github.com/Stagnation47/Awsome-VLN/issues) or [Pull Request](https://github.com/Stagnation47/Awsome-VLN/pulls). Add each paper once under its primary contribution, with its year, venue, paper/code links, and important evaluation assumptions. Keep the classic or representative starting point first (★).

`CCF-A` marks recent publications verified in this update against official proceedings or journal pages and the [CCF directory](https://www.ccf.org.cn/Academic_Evaluation/AI/), checked on September 24, 2026. It is a selective marker, not a complete ranking of this list; workshop papers and unaccepted preprints are excluded from this marker.

## Acknowledgements

Adapted from [awesome-embodied-vla-va-vln](https://github.com/jonyzhang2023/awesome-embodied-vla-va-vln). The task/method organization and selected early references also draw on [daqingliu/awesome-vln](https://github.com/daqingliu/awesome-vln). Thanks to the original maintainers and contributors.
