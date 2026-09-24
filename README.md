<div align="center">

# 🚶 Awesome VLN

**A Curated Collection of Vision-and-Language Navigation Research**

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
[![Papers](https://img.shields.io/badge/Papers-60-0984e3?style=for-the-badge&logo=google-scholar&logoColor=white)](#paper-catalog)
[![Last Commit](https://img.shields.io/github/last-commit/Stagnation47/Awsome-VLN?style=for-the-badge&color=00b894)](https://github.com/Stagnation47/Awsome-VLN/commits/main)
[![Stars](https://img.shields.io/github/stars/Stagnation47/Awsome-VLN?style=for-the-badge&color=fdcb6e&logo=github)](https://github.com/Stagnation47/Awsome-VLN/stargazers)
[![Forks](https://img.shields.io/github/forks/Stagnation47/Awsome-VLN?style=for-the-badge&color=e17055&logo=github)](https://github.com/Stagnation47/Awsome-VLN/forks)

*Papers, models, and benchmarks for vision-and-language navigation, organized by task setting, model role, representation, and learning strategy.*

</div>

## Table of Contents

- [Development Milestones](#development-milestones)
- [Classification Axes](#classification-axes)
- [Reading Guides: Foundational Work First](#reading-guides)
- [Paper Catalog](#paper-catalog)
- [Contributing](#contributing)
- [Acknowledgements](#acknowledgements)

<a id="development-milestones"></a>

## Development Milestones

These are overlapping developments, not successive replacements. Discrete VLN remains an active setting; continuous navigation can still use a graph internally.

| Development | Starting references | What changed |
|:---|:---|:---|
| Viewpoint-graph instruction following | [R2R (2018)](#paper-r2r); [Speaker-Follower (2018)](#paper-speaker-follower) | Navigation on predefined viewpoint connectivity; instruction learning and synthetic supervision. |
| Continuous-environment execution | [VLN-CE (2020)](#paper-vln-ce) | Agents execute low-level movement and handle collisions instead of relying on graph-edge traversal. Continuous environments do not require continuous-valued actions. |
| Pretraining, long history, and explicit planning | [PREVALENT (2020)](#paper-prevalent); [HAMT (2021)](#paper-hamt); [DUET (2022)](#paper-duet) | Stronger cross-modal representations, history encoding, and online topological reasoning; applicable across different task settings. |
| Language-grounded spatial representations and foundation-model planners | [VLMaps (2023)](#paper-vlmaps); [NavGPT (2024)](#paper-navgpt); [ETPNav (2023)](#paper-etpnav) | Language queries, pretrained reasoning, and explicit maps become complementary system components. ETPNav illustrates graph planning in continuous environments. |
| Video policies, streaming, and physical deployment | [NaVid (2024)](#paper-navid); [Mobility VLA (2024)](#paper-mobility-vla); [StreamVLN (2025)](#paper-streamvln); [JanusVLN (2025)](#paper-janusvln) | Direct action generation, persistent memory, and hierarchical robot execution develop along multiple parallel directions. |

Years follow publication years or the original list's recorded years. Newly added preprints are labeled **arXiv**; an arXiv label identifies the linked version and does not establish that no later publication exists. ETPNav is separately marked as first publicly released in 2023. Where relevant, catalog notes distinguish an earlier preprint from the publication year.

<a id="classification-axes"></a>

## Classification Axes

This is a repository-specific, multi-axis index informed by the [task-taxonomy survey](#paper-vln-taxonomy-survey) and the [foundation-model survey](#paper-foundation-model-survey). It is not a universal or mutually exclusive taxonomy. A paper can use a VLM, a scene graph, and a topological planner simultaneously.

| Axis | What is recorded |
|:---|:---|
| Task setting | **DE**: discrete viewpoint-graph navigation; **CE**: continuous-environment navigation; physical/custom settings are named explicitly. **GoalNav** marks goal-navigation evaluations that should not be equated with route-following VLN. |
| Instruction and embodiment | Route instructions, referring/spatial goals, dialogue, or conditional instructions; aerial and physical-robot settings are additional properties. |
| Model / policy role | A learned navigation policy, a foundation model used for features or grounding, an LLM/VLM planner, a VLM/VLA action policy, or a hybrid of these. |
| Spatial / history representation | Recurrent or implicit state, historical observations, topological maps, semantic maps, 3D fields/tokens, scene graphs, or instruction constraint graphs. Multiple representations can coexist. |
| Learning | Pretraining, supervised/imitative learning, reinforcement learning, task-specific fine-tuning, zero-shot inference, or test-time adaptation. |
| Evaluation conditions | Benchmark, observation modality, prior map or exploration access, feedback, and embodiment where these affect interpretation. |

**Three different graph roles:** a navigation topology represents locations and traversability; a scene graph represents environmental entities and their relations; an instruction graph represents requested constraints or dependencies. The same system may connect all three.

The catalog records reported method characteristics, not reproduced results or performance rankings. A zero-shot navigation component may still rely on trained perception, waypoint prediction, or control. Pre-exploration, maps, feedback, and additional training data must be aligned before comparing results. Aerial navigation is an embodiment tag, not an alternative to DE/CE or VLM-based modeling.

<a id="reading-guides"></a>

## Reading Guides: Foundational Work First

Each guide starts with a foundational or established reference selected for its contribution to that direction, followed by later work. For newer directions, the first entry is explicitly labeled a representative starting point. These are editorial reading recommendations, not citation-count rankings. Guides overlap; each paper has one full record in the catalog.

<a id="surveys"></a>

### Surveys

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Foundational task taxonomy** | **[VLN Taxonomy Survey (2024)](#paper-vln-taxonomy-survey)** | Starts from instruction structure and interaction. Read the foundation-model survey next for a complementary model-centered view. |
| 2. Continue with | [Foundation-Model VLN Survey (2024)](#paper-foundation-model-survey) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="task-foundations"></a>

### Task Foundations: Discrete and Continuous Navigation

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Foundational benchmark** | **[R2R (2018)](#paper-r2r)** | Introduced R2R and the viewpoint-graph task. VLN-CE then makes navigation execution part of the problem. |
| 2. Continue with | [VLN-CE (2020)](#paper-vln-ce); [AerialVLN (2023)](#paper-aerialvln); [HA-VLN (2025)](#paper-ha-vln); [CondVLN (2026)](#paper-condvln) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="topological-planning"></a>

### Topological Mapping and Planning

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Established reference** | **[DUET (2022)](#paper-duet)** | A clear reference for online topology and global/local graph reasoning in discrete VLN. ETPNav is the next starting point for continuous environments. |
| 2. Continue with | [ETPNav (2023)](#paper-etpnav); [AZHP (2023)](#paper-azhp); [ETP-R1 (2025)](#paper-etp-r1); [DGNav (2026)](#paper-dgnav); [SmartWay (2025)](#paper-smartway); [Mobility VLA (2024)](#paper-mobility-vla); [TRAVEL (2025)](#paper-travel) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="scene-graphs"></a>

### Entity Relations and Scene Graphs

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Early direct VLN reference** | **[Entity-Graph VLN (2020)](#paper-entity-graph)** | Introduces language/visual entity relations for navigation. Its relation graph is not a persistent 3D scene graph; HSAN and FSR-VLN cover later scene-graph systems. |
| 2. Continue with | [HSAN (2025)](#paper-hsan); [FSR-VLN (2025)](#paper-fsr-vln); [VLN-Zero (2025)](#paper-vln-zero); [SpatialNav (2026)](#paper-spatialnav); [VL-Nav (2025)](#paper-vl-nav); [DyNaVLM (2025)](#paper-dynavlm) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="instruction-constraints"></a>

### Instruction Graphs and Constraint Planning

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Representative starting point** | **[GC-VLN (2025)](#paper-gc-vln)** | A direct entry into explicit instruction constraints and solving for waypoints. This narrower direction is recent; no longstanding classic is asserted. |
| 2. Continue with | [VLN-Zero (2025)](#paper-vln-zero); [SpatialNav (2026)](#paper-spatialnav); [CondVLN (2026)](#paper-condvln) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="spatial-maps"></a>

### Semantic Maps and 3D Feature Fields

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Foundational representation** | **[VLMaps (2023)](#paper-vlmaps)** | Grounds spatial language in a geometric map with visual-language features. It provides background for language-guided navigation, rather than the standard route-following protocol alone. |
| 2. Continue with | [Multimodal Spatial Language Maps (2025)](#paper-multimodal-spatial-language-maps); [OVL-MAP (2025)](#paper-ovl-map); [MapNav (2025)](#paper-mapnav); [HNR (2024)](#paper-hnr); [g3D-LF (2025)](#paper-g3d-lf); [Dynam3D (2025)](#paper-dynam3d); [GVNav (2025)](#paper-gvnav) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="memory-streaming"></a>

### History, Memory, and Streaming

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Established history-modeling reference** | **[HAMT (2021)](#paper-hamt)** | Makes long visual history explicit. Recurrent VLN-BERT, JanusVLN, and StreamVLN illustrate different state, implicit-memory, and streaming choices. |
| 2. Continue with | [Recurrent VLN-BERT (2021)](#paper-recurrent-vln-bert); [COSMO (2025)](#paper-cosmo); [NaVid (2024)](#paper-navid); [JanusVLN (2025)](#paper-janusvln); [StreamVLN (2025)](#paper-streamvln); [SR-VLN (2026)](#paper-sr-vln) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="reasoning-adaptation"></a>

### Pretraining, Learning, and Adaptation

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Foundational pretraining reference** | **[PREVALENT (2020)](#paper-prevalent)** | Establishes a useful starting point for pretraining and task adaptation. Test-time adaptation is a separate learning condition, illustrated by ATENA. |
| 2. Continue with | [Recurrent VLN-BERT (2021)](#paper-recurrent-vln-bert); [HAMT (2021)](#paper-hamt); [ATENA (2025)](#paper-atena); [FlexVLN (2025)](#paper-flexvln); [Aux-Think (2025)](#paper-aux-think); [CorrectNav (2025)](#paper-correctnav); [ETP-R1 (2025)](#paper-etp-r1) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="foundation-planners"></a>

### LLM/VLM Planning and Reasoning

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Early LLM-navigation reference** | **[NavGPT (2024)](#paper-navgpt)** | Shows explicit LLM reasoning over visual descriptions. A planner using textualized observations is distinguished from a VLM that consumes images and predicts actions. |
| 2. Continue with | [TRAVEL (2025)](#paper-travel); [SmartWay (2025)](#paper-smartway); [GC-VLN (2025)](#paper-gc-vln); [FSR-VLN (2025)](#paper-fsr-vln); [VL-Nav (2025)](#paper-vl-nav); [OpenNav (2025)](#paper-opennav) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="vlm-policies"></a>

### VLM/VLA Navigation Policies

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Representative early video-VLM reference** | **[NaVid (2024)](#paper-navid)** | A direct starting point for monocular video-to-action VLN. Subsequent policies add memory, correction, geometry, or hierarchical execution. |
| 2. Continue with | [NaVILA (2025)](#paper-navila); [JanusVLN (2025)](#paper-janusvln); [StreamVLN (2025)](#paper-streamvln); [CorrectNav (2025)](#paper-correctnav); [DualVLN (2025)](#paper-dualvln); [OctoNav (2025)](#paper-octonav); [NavFoM (2025)](#paper-navfom); [OmniVLA (2025)](#paper-omnivla) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="imagination-data"></a>

### Data Augmentation and Visual Imagination

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Foundational augmentation reference** | **[Speaker-Follower (2018)](#paper-speaker-follower)** | Uses a speaker to synthesize instructions and score candidate paths. Visual imagination is a later, distinct augmentation/decision mechanism. |
| 2. Continue with | [PanoGen++ (2025)](#paper-panogen-); [RAM (2025)](#paper-ram); [VLN-Imagine (2025)](#paper-vln-imagine); [VISTA (2025)](#paper-vista); [HNR (2024)](#paper-hnr) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="generalist-real-world"></a>

### Real-World and Generalist Navigation

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Representative system starting point** | **[Mobility VLA (2024)](#paper-mobility-vla)** | Connects a VLM goal selector to a topological controller on a physical robot. Its tour-video/map requirement makes it a useful comparison case, not a universal classic for all robot embodiments. |
| 2. Continue with | [NaVILA (2025)](#paper-navila); [CANVAS (2024)](#paper-canvas); [OpenNav (2025)](#paper-opennav); [LOVON (2025)](#paper-lovon); [OmniVLA (2025)](#paper-omnivla); [GVNav (2025)](#paper-gvnav); [OctoNav (2025)](#paper-octonav); [NavFoM (2025)](#paper-navfom) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="aerial-vln"></a>

### Aerial Vision-and-Language Navigation

| Reading order | Paper(s) | Why read it |
|:---|:---|:---|
| **1. Foundational aerial benchmark** | **[AerialVLN (2023)](#paper-aerialvln)** | Defines a language-guided outdoor UAV task with a simulator, dataset, and baseline. It separates aerial embodiment from the choice of model or memory. |
| 2. Continue with | [CityNavAgent (2025)](#paper-citynavagent); [VLFly (2025)](#paper-vlfly); [OpenFly (2025)](#paper-openfly) | Compare the model, representation, and evaluation conditions in the catalog. |

<a id="paper-catalog"></a>

## Paper Catalog

All **60 unique papers** are recorded below: **52 method/representation papers**, **6 benchmark papers**, and **2 surveys**. Each paper is listed once by its primary resource type; papers introducing both an agent and a benchmark are labeled accordingly. Method rows are ordered by recorded year, then name. Use the reading guides above for foundational-first ordering within a direction.

### Methods and Representations

| Paper · year / venue | Task setting / instruction | Model / policy | Spatial / history representation | Learning | Evaluation conditions |
|:---|:---|:---|:---|:---|:---|
| <a id="paper-speaker-follower"></a>**Speaker-Follower · 2018** · NeurIPS 2018<br>[Speaker-Follower Models for Vision-and-Language Navigation](https://arxiv.org/abs/1806.02724) | DE · route | Speaker + follower + pragmatic search | Recurrent sequence state | Synthetic instructions + follower training | R2R; panoramic candidate actions. |
| <a id="paper-entity-graph"></a>**Entity-Graph VLN · 2020** · NeurIPS 2020<br>[Language and Visual Entity Relationship Graph for Agent Navigation](https://arxiv.org/abs/2010.09304) | DE · route | Graph message passing + action policy | Language/visual entity relation graph | Navigation model training | R2R; R4R; relational grounding, not a persistent 3D scene map. |
| <a id="paper-prevalent"></a>**PREVALENT · 2020** · CVPR 2020<br>[Towards Learning a Generic Agent for Vision-and-Language Navigation via Pre-training](https://arxiv.org/abs/2002.10638) | DE · route / dialogue | Pretrained VL encoder + navigation policy | Cross-modal representations | Self-supervised pretraining + fine-tuning | Image-text-action triplets; transfer across VLN tasks. |
| <a id="paper-hamt"></a>**HAMT · 2021** · NeurIPS 2021<br>[History Aware Multimodal Transformer for Vision-and-Language Navigation](https://arxiv.org/abs/2110.13309) | DE · route / goal / dialogue | Multimodal Transformer policy | Explicit hierarchical panoramic history | Proxy-task pretraining + RL | Long-horizon history; R2R/RxR/R4R, REVERIE, and dialogue tasks. |
| <a id="paper-recurrent-vln-bert"></a>**Recurrent VLN-BERT · 2021** · CVPR 2021<br>[A Recurrent Vision-and-Language BERT for Navigation](https://arxiv.org/abs/2011.13922) | DE · route / referring goal | Recurrent VL-BERT policy | Recurrent cross-modal state | Pretraining + navigation learning | R2R; REVERIE; CVPR 2021, first public release 2020. |
| <a id="paper-duet"></a>**DUET · 2022** · CVPR 2022<br>[Think Global, Act Local: Dual-scale Graph Transformer for Vision-and-Language Navigation](https://arxiv.org/abs/2202.11742) | DE · route / referring goal | Dual-scale graph Transformer | Online topological map + local observations | Pretraining + navigation learning | R2R; REVERIE; SOON; global/local fusion. |
| <a id="paper-azhp"></a>**AZHP · 2023** · CVPR 23<br>[Adaptive Zone-Aware Hierarchical Planner for Vision-Language Navigation](https://openaccess.thecvf.com/content/CVPR2023/papers/Gao_Adaptive_Zone-Aware_Hierarchical_Planner_for_Vision-Language_Navigation_CVPR_2023_paper.pdf) | DE · route / referring goal | Hierarchical learned planner | Adaptive zones | Hierarchical RL + auxiliary losses | R2R; REVERIE; SOON. |
| <a id="paper-etpnav"></a>**ETPNav · 2023** · arXiv debut<br>[ETPNav: Evolving Topological Planning for Vision-Language Navigation in Continuous Environments](https://arxiv.org/abs/2304.03047)<br>[code](https://github.com/MarSaKi/ETPNav) | CE · route | Cross-modal graph planner + controller | Online topological graph | Trained policy | R2R-CE; RxR-CE; predicted waypoints and obstacle avoidance; first publicly released in 2023. |
| <a id="paper-vlmaps"></a>**VLMaps · 2023** · ICRA 2023<br>[Visual Language Maps for Robot Navigation](https://arxiv.org/abs/2210.05714) | Physical/simulated · spatial language goal | LLM goal grounding + feature queries | 3D visual-language map | Pretrained models; no added labeled grounding data | Map built before goal queries; ICRA 2023, first public release 2022. |
| <a id="paper-canvas"></a>**CANVAS · 2024** · arXiv<br>[CANVAS: Commonsense-Aware Navigation System for Intuitive Human-Robot Interaction](https://arxiv.org/abs/2410.01273)<br>[project](https://worv-ai.github.io/canvas/) · [code](https://github.com/worv-ai/canvas) | Physical/simulated · language + sketch cues | Learned commonsense navigation policy | Visual context + guidance | Imitation learning | COMMAND dataset; noisy verbal/sketch inputs; sim-to-real evaluation. |
| <a id="paper-hnr"></a>**HNR · 2024** · CVPR 24<br>[HNR: Lookahead Exploration with Neural Radiance Representation for Continuous Vision-Language Navigation](https://arxiv.org/abs/2404.01943) | CE · route | Feature prediction + lookahead planner | Hierarchical radiance representation + path tree | Representation/policy training | Future semantic feature prediction; VLN-CE. |
| <a id="paper-mobility-vla"></a>**Mobility VLA · 2024** · arXiv<br>[Mobility VLA: Multimodal Instruction Navigation with Long-Context VLMs and Topological Graphs](https://arxiv.org/pdf/2407.07775) | Physical · multimodal goal | VLM goal selection + local policy | Tour video + topological graph | Pretrained components | Requires demonstration tour and an offline graph. |
| <a id="paper-navgpt"></a>**NavGPT · 2024** · AAAI 2024<br>[NavGPT: Explicit Reasoning in Vision-and-Language Navigation with Large Language Models](https://arxiv.org/abs/2305.16986) | DE · route | LLM planner over visual descriptions | Textual observations + history | Zero-shot LLM inference | R2R; visual observations are converted to text for the planner. |
| <a id="paper-navid"></a>**NaVid · 2024** · RSS 24<br>[NaVid: Video-based VLM Plans the Next Step for Vision-and-Language Navigation](https://arxiv.org/pdf/2402.15852) | CE · route | Video-VLM action policy | Encoded video history | Navigation + general VL training | Monocular RGB; no map, odometry, or depth input. |
| <a id="paper-atena"></a>**ATENA · 2025** · NeurIPS 2025<br>[Active Test-time Vision-Language Navigation](https://arxiv.org/pdf/2506.06630) | DE + CE · route / referring goal | Adaptation applied to navigation policies | Depends on base policy | Test-time active/self-active learning | R2R; REVERIE; R2R-CE; outcome feedback and parameter updates matter. |
| <a id="paper-aux-think"></a>**Aux-Think · 2025** · arXiv<br>[Aux-Think: Exploring Reasoning Strategies for Data-Efficient Vision-Language Navigation](https://arxiv.org/pdf/2505.11886) | CE · route | VLM action policy | Visual history | CoT supervision; direct-action inference | R2R-CE; reasoning is supervised during training, not emitted at every test step. |
| <a id="paper-citynavagent"></a>**CityNavAgent · 2025** · arXiv<br>[CityNavAgent: Aerial Vision-and-Language Navigation with Hierarchical Semantic Planning and Global Memory](https://arxiv.org/pdf/2505.05622)<br>[project](https://github.com/VinceOuti/CityNavAgent) | CE · aerial route / goal | LLM hierarchical planner | Global topological memory | LLM-guided planning | City-scale aerial environments; hierarchical subgoals. |
| <a id="paper-correctnav"></a>**CorrectNav · 2025** · arXiv<br>[CorrectNav: Self-Correction Flywheel Empowers Vision-Language-Action Navigation Model](https://arxiv.org/pdf/2508.10416)<br>[project](https://correctnav.github.io/) | CE · route | VLA navigation policy | Visual trajectory context | Iterative self-correction post-training | R2R-CE; RxR-CE; monocular RGB; real-robot evaluation. |
| <a id="paper-cosmo"></a>**COSMO · 2025** · arXiv<br>[COSMO: Combination of Selective Memorization for Low-cost Vision-and-Language Navigation](https://arxiv.org/pdf/2503.24065) | DE + CE · route / referring goal | State-space/Transformer navigation policy | Selective state-space memory | Navigation model training | R2R; REVERIE; R2R-CE. Not a generative VLM navigator. |
| <a id="paper-dualvln"></a>**DualVLN · 2025** · arXiv<br>[Ground Slow, Move Fast: A Dual-System Foundation Model for Generalizable Vision-and-Language Navigation](https://arxiv.org/pdf/2512.08186)<br>[project](https://internrobotics.github.io/internvla-n1-dualvln.github.io/) · [code](https://github.com/InternRobotics/InternNav) | CE / physical · route | VLM waypoint planner + diffusion policy | Visual context + latent planner features | Separately trained planning/control | Two-level action execution; continuous local trajectories. |
| <a id="paper-dynam3d"></a>**Dynam3D · 2025** · arXiv<br>[Dynam3D: Dynamic Layered 3D Tokens Empower VLM for Vision-and-Language Navigation](https://arxiv.org/pdf/2505.11383)<br>[project](https://github.com/MrZihan/Dynam3D) | CE · route / referring goal | 3D-VLM action policy | Patch-instance-zone 3D tokens | 3D-language pretraining + adaptation | Posed RGB-D; monocular benchmark view; also pre-exploration/lifelong variants. |
| <a id="paper-dynavlm"></a>**DyNaVLM · 2025** · arXiv<br>[DyNaVLM: Zero-Shot Vision-Language Navigation System with Dynamic Viewpoints and Self-Refining Graph Memory](https://arxiv.org/pdf/2506.15096) | GoalNav · multimodal/object goal | VLM reasoning + retrieval | Object-location/topological graph | No task-specific fine-tuning | GOAT; ObjectNav; real robot. These are not route-following VLN benchmarks. |
| <a id="paper-etp-r1"></a>**ETP-R1 · 2025** · arXiv<br>[ETP-R1: Evolving Topological Planning with Reinforcement Fine-tuning for Vision-Language Navigation in Continuous Environments](https://arxiv.org/abs/2512.20940)<br>[code](https://github.com/Cepillar/ETP-R1) | CE · route | Learned graph planner | Topological graph | Pretraining + GRPO | R2R-CE; RxR-CE; expanded instruction data and joint-task training. |
| <a id="paper-flexvln"></a>**FlexVLN · 2025** · arXiv<br>[FlexVLN: Flexible Adaptation for Diverse Vision-and-Language Navigation Tasks](https://arxiv.org/pdf/2503.13966) | DE · route / referring goal / dialogue | LLM planner + supervised follower | Follower state + sub-instructions | Supervised follower; cross-task transfer | REVERIE; SOON; CVDN-target used for out-of-domain evaluation. |
| <a id="paper-fsr-vln"></a>**FSR-VLN · 2025** · arXiv<br>[FSR-VLN: Fast and Slow Reasoning for Vision-Language Navigation with Hierarchical Multi-modal Scene Graph](https://arxiv.org/abs/2509.13733) | Physical · described goal | VLM refinement + retrieval | Hierarchical multimodal scene graph | Pretrained models + retrieval | Prebuilt static graph; goal retrieval and humanoid deployment. |
| <a id="paper-g3d-lf"></a>**g3D-LF · 2025** · CVPR 25<br>[g3D-LF: Generalizable 3D-Language Feature Fields for Embodied Tasks](https://arxiv.org/abs/2411.17030) | CE + other embodied tasks | Learned representation + downstream policy | 3D-language feature field | Representation pretraining + adaptation | Posed RGB-D; panoramic/monocular VLN; also ObjectNav and QA. |
| <a id="paper-gc-vln"></a>**GC-VLN · 2025** · CoRL 25<br>[GC-VLN: Instruction as Graph Constraints for Training-free Vision-and-Language Navigation](https://arxiv.org/pdf/2509.10454)<br>[project](https://bagh2178.github.io/GC-VLN/) · [code](https://github.com/bagh2178/GC-VLN) | CE · route / spatial constraints | Language grounding + constraint solver | Instruction constraint graph + navigation tree | Training-free framework | R2R-CE and real-world navigation; graph encodes requested constraints. |
| <a id="paper-gvnav"></a>**GVNav · 2025** · arXiv<br>[Ground-level Viewpoint Vision-and-Language Navigation in Continuous Environments](https://arxiv.org/pdf/2502.19024) | CE / physical · route | Learned waypoint/navigation policy | Weighted grid history | Policy/predictor training | Low-height viewpoints; quadruped deployment and extra geometric priors. |
| <a id="paper-hsan"></a>**HSAN · 2025** · NeurIPS 25<br>[HSAN: Hierarchical Semantic-Augmented Navigation: Optimal Transport and Graph-Driven Reasoning for Vision-Language Navigation](https://papers.neurips.cc/paper_files/paper/2025/hash/592da1445a51e54a3987958b5831948f-Abstract-Conference.html) | CE · instruction following | Optimal-transport planner + learned controller | Hierarchical scene graph + topology | Graph-aware RL | Joint semantic planning and low-level obstacle avoidance. |
| <a id="paper-janusvln"></a>**JanusVLN · 2025** · arXiv<br>[JanusVLN: Decoupling Semantics and Spatiality with Dual Implicit Memory for Vision-Language Navigation](https://arxiv.org/pdf/2509.22548)<br>[project](https://miv-xjtu.github.io/JanusVLN.github.io/) · [code](https://github.com/MIV-XJTU/JanusVLN) | CE · route | MLLM action policy + geometry encoder | Dual implicit KV memory | Navigation model training | Monocular RGB at inference; semantic and geometric memory streams. |
| <a id="paper-lovon"></a>**LOVON · 2025** · arXiv<br>[LOVON: Legged Open-Vocabulary Object Navigator](https://arxiv.org/pdf/2507.06747)<br>[project](https://daojiepeng.github.io/LOVON/) | Physical · sequential object goals | LLM task planner + visual detector | Object detections + execution state | Pretrained modules + controller | Legged robots; open-vocabulary multigoal missions, not standard route benchmarks. |
| <a id="paper-mapnav"></a>**MapNav · 2025** · arXiv<br>[MapNav: A Novel Memory Representation via Annotated Semantic Maps for Vision-and-Language Navigation](https://arxiv.org/pdf/2502.13451) | CE · route | VLM action policy | Annotated semantic map | Supervised learning + DAgger | R2R-CE; RxR-CE; online map construction; simulation and real robot. |
| <a id="paper-multimodal-spatial-language-maps"></a>**Multimodal Spatial Language Maps · 2025** · IJRR 25<br>[Multimodal Spatial Language Maps for Robot Navigation and Manipulation](https://arxiv.org/pdf/2506.06862)<br>[project](https://mslmaps.github.io/) | Physical/simulated · spatial goal | LLM goal grounding + map queries | 3D visual/audio-language map | Pretrained feature grounding | Mapped environments; spatial and multimodal goal descriptions. |
| <a id="paper-navfom"></a>**NavFoM · 2025** · arXiv<br>[Embodied Navigation Foundation Model](https://arxiv.org/pdf/2509.12129)<br>[project](https://pku-epic.github.io/NavFoM-Web/) | CE / physical · multiple tasks | Multimodal navigation foundation policy | Multiview observation tokens | Large-scale navigation training | Multiple embodiments and camera layouts; VLN is one supported task. |
| <a id="paper-navila"></a>**NaVILA · 2025** · RSS 25<br>[NaVILA: Legged Robot Vision-Language-Action Model for Navigation](https://arxiv.org/pdf/2412.04453)<br>[project](https://navila-bot.github.io/) | CE / physical · route | VLA mid-level commands + locomotion policy | Visual context | Navigation training + locomotion RL | Legged robots; mid-level language commands precede joint-level control. |
| <a id="paper-octonav"></a>**OctoNav · 2025** · arXiv<br>[OctoNav: Towards Generalist Embodied Navigation](https://arxiv.org/pdf/2506.09839)<br>[project](https://buaa-colalab.github.io/OctoNav/) | CE · composite multimodal instructions | MLLM/VLA action policy | Visual context + reasoning traces | SFT + GRPO + online RL | OctoNav-Bench combines capabilities/modalities; not only R2R-style VLN. |
| <a id="paper-omnivla"></a>**OmniVLA · 2025** · arXiv<br>[OmniVLA: An Omni-Modal Vision-Language-Action Model for Robot Navigation](https://arxiv.org/pdf/2509.19480)<br>[project](https://omnivla-nav.github.io/) · [code](https://github.com/NHirose/OmniVLA) | Physical · language / image / pose goal | VLA navigation policy | Multimodal goal conditioning | Policy training with modality fusion | Goal modalities and their combinations; real-world robot navigation. |
| <a id="paper-opennav"></a>**OpenNav · 2025** · arXiv<br>[OpenNav: Open-World Navigation with Multimodal Large Language Models](https://arxiv.org/pdf/2507.18033)<br>[project](https://trailab.github.io/OpenNav-website/) | Physical/outdoor · free-form instructions | MLLM planning + visual grounding | BEV value maps | Zero-shot framework | Autonomous-vehicle data and Husky experiments; varied free-form instructions. |
| <a id="paper-ovl-map"></a>**OVL-MAP · 2025** · RA-L 25<br>[OVL-MAP: An Online Visual Language Map Approach for Vision-and-Language Navigation in Continuous Environments](https://labsun.org/pub/RAL2025_ovlmap.pdf) | CE · route | Language grounding + waypoint/controller policy | Online visual-language map | Trained navigation policy | Robo-VLN; R2R-CE; includes velocity-control setting. |
| <a id="paper-panogen-"></a>**PanoGen++ · 2025** · arXiv<br>[PanoGen++: Domain-Adapted Text-Guided Panoramic Environment Generation for Vision-and-Language Navigation](https://arxiv.org/pdf/2503.09938) | DE · route / dialogue | Diffusion data generator + base policy | Synthetic panoramas | Diffusion adaptation + navigation training | R2R; R4R; CVDN. Contribution is data augmentation. |
| <a id="paper-ram"></a>**RAM · 2025** · arXiv<br>[Unseen from Seen: Rewriting Observation-Instruction Using Foundation Models for Augmenting Vision-Language Navigation](https://arxiv.org/pdf/2503.18065)<br>[project](https://github.com/SaDil13/VLN-RAM) | DE + CE · route / referring goal | VLM/LLM data rewriting + base policy | Synthetic observation-instruction pairs | Augmentation + policy training | R2R; REVERIE; R4R; R2R-CE. |
| <a id="paper-smartway"></a>**SmartWay · 2025** · arXiv<br>[SmartWay: Enhanced Waypoint Prediction and Backtracking for Zero-Shot Vision-and-Language Navigation](https://arxiv.org/pdf/2503.10069) | CE · route | VLM planner + waypoint predictor | Waypoint/history representation | Zero-shot navigator; trained predictor | R2R-CE; real robot; zero-shot does not apply to every component. |
| <a id="paper-streamvln"></a>**StreamVLN · 2025** · arXiv<br>[StreamVLN: Streaming Vision-and-Language Navigation via SlowFast Context Modeling](https://arxiv.org/abs/2507.05240) | CE · route | Video-VLM action policy | Sliding context + pruned visual memory | Navigation model training | Streaming context; 3D-aware pruning; slow/fast memory updates. |
| <a id="paper-travel"></a>**TRAVEL · 2025** · arXiv<br>[TRAVEL: Training-Free Retrieval and Alignment for Vision-and-Language Navigation](https://arxiv.org/pdf/2502.07306) | Mapped environment · route | LLM landmarks + VLM matching + path search | Known topological map + panoramas | Training-free inference | Known environment model; R2R-Habitat path alignment. |
| <a id="paper-vista"></a>**VISTA · 2025** · arXiv<br>[VISTA: Generative Visual Imagination for Vision-and-Language Navigation](https://arxiv.org/pdf/2505.07868) | DE + GoalNav · route / object goal | Diffusion imagination + action reasoning | Imagined goals + perceptual alignment | Pretrained generative prior | R2R and RoboTHOR are different task settings. |
| <a id="paper-vl-nav"></a>**VL-Nav · 2025** · arXiv<br>[VL-Nav: Neuro-Symbolic Reasoning-based Vision-Language Navigation](https://arxiv.org/pdf/2502.00931) | Physical/simulated · complex instructions | VLM + neurosymbolic planner | Symbolic 3D scene graph + image memory | Modular pretrained reasoning | Current paper version uses neuro-symbolic planning; indoor/outdoor tests. |
| <a id="paper-vlfly"></a>**VLFly · 2025** · arXiv<br>[Grounded Vision-Language Navigation for UAVs with Open-Vocabulary Goal Understanding](https://arxiv.org/pdf/2506.10756)<br>[project](https://zzzzzyh111.github.io/VLFly/) | Physical/simulated · aerial language goal | LLM instruction encoding + VLM retrieval | Goal images + waypoint representation | Pretrained modules; zero-shot transfer | Monocular UAV; continuous velocity output; direct/indirect instructions. |
| <a id="paper-vln-imagine"></a>**VLN-Imagine · 2025** · arXiv<br>[Do Visual Imaginations Improve Vision-and-Language Navigation Agents?](https://arxiv.org/pdf/2503.16394)<br>[project](https://www.akhilperincherry.com/VLN-Imagine-website/) | DE · route / referring goal | Imagination module on HAMT/DUET | Generated landmark images + base memory | Fine-tuning + alignment loss | R2R; REVERIE; added visual modality, not a new environment type. |
| <a id="paper-vln-zero"></a>**VLN-Zero · 2025** · arXiv<br>[VLN-Zero: Rapid Exploration and Cache-Enabled Neurosymbolic Vision-Language Planning for Zero-Shot Transfer in Robot Navigation](https://arxiv.org/abs/2509.18592) | Exploration/deployment · instruction following | VLM + neurosymbolic planner | Symbolic scene graph + path cache | Zero-shot transfer | Separate exploration and deployment phases. |
| <a id="paper-dgnav"></a>**DGNav · 2026** · arXiv<br>[DGNav: Dynamic Topology Awareness: Breaking the Granularity Rigidity in Vision-Language Navigation](https://arxiv.org/abs/2601.21751) | CE · route | Learned graph planner | Topological graph | Trained policy | R2R-CE; RxR-CE; adaptive waypoint merging. |
| <a id="paper-spatialnav"></a>**SpatialNav · 2026** · arXiv<br>[SpatialNav: Leveraging Spatial Scene Graphs for Zero-Shot Vision-and-Language Navigation](https://arxiv.org/abs/2601.06806) | DE + CE · route | Foundation-model reasoning + spatial queries | Hierarchical scene graph + local map | Zero-shot navigation | Pre-exploration allowed; sampled R2R-CE/RxR-CE evaluations. |
| <a id="paper-sr-vln"></a>**SR-VLN · 2026** · Sensors 26<br>[SR-VLN: Implicit Spatial Reasoning Vision-and-Language Navigation](https://www.mdpi.com/1424-8220/26/12/3809) | DE · route / referring goal | MLLM policy + implicit reasoning | Pyramidal history + spatial tokens | Supervision + GRPO | R2R; REVERIE; SOON; not a VLN-CE evaluation. |

<a id="benchmarks"></a>

### Benchmarks and Datasets

R2R is the foundational first entry. Later resources change the environment, embodiment, or instruction requirements.

| Paper · year / venue | Task setting | Resource / baseline | Conditions |
|:---|:---|:---|:---|
| <a id="paper-r2r"></a>**R2R · 2018** · CVPR 2018<br>[Vision-and-Language Navigation: Interpreting visually-grounded navigation instructions in real environments](https://arxiv.org/abs/1711.07280) | DE · route | Sequence-to-sequence baseline | Predefined Matterport3D viewpoint connectivity; CVPR 2018, first public release 2017. |
| <a id="paper-vln-ce"></a>**VLN-CE · 2020** · ECCV 2020<br>[Beyond the Nav-Graph: Vision-and-Language Navigation in Continuous Environments](https://arxiv.org/abs/2004.02857) | CE · route | Learned low-level baselines | Continuous traversable space; discrete low-level actions are still possible. |
| <a id="paper-aerialvln"></a>**AerialVLN · 2023** · ICCV 2023<br>[AerialVLN: Vision-and-Language Navigation for UAVs](https://arxiv.org/abs/2308.06735) | CE · aerial route | Cross-modal-alignment baseline | Outdoor UAV task; city simulator and language-guided flight dataset. |
| <a id="paper-ha-vln"></a>**HA-VLN · 2025** · arXiv<br>[HA-VLN 2.0: An Open Benchmark and Leaderboard for Human-Aware Navigation in Discrete and Continuous Environments with Dynamic Multi-Human Interactions](https://arxiv.org/pdf/2503.14229)<br>[project](https://ha-vln-project.vercel.app/) | DE + CE · dynamic human interaction | Benchmark + baselines | Human-aware protocols; current version is HA-VLN 2.0. |
| <a id="paper-openfly"></a>**OpenFly · 2025** · arXiv<br>[Openfly: A comprehensive platform for aerial vision-language navigation](https://arxiv.org/pdf/2502.18041) | CE · aerial instructions | Benchmark/toolchain + agent | Multiple rendering engines; current paper title is Openfly: A comprehensive platform for aerial vision-language navigation. |
| <a id="paper-condvln"></a>**CondVLN · 2026** · arXiv<br>[CondVLN: If, Then, Otherwise: Diagnosing Conditional Branching in Vision-Language Navigation](https://arxiv.org/abs/2608.17318) | Conditional instruction benchmark | Evaluation resource | Branch selection and conditional execution; first public release 2026. |

### Survey References

| Paper · year / venue | Organizing perspective |
|:---|:---|
| <a id="paper-vln-taxonomy-survey"></a>**VLN Taxonomy Survey · 2024** · arXiv<br>[Vision-language navigation: a survey and taxonomy](https://arxiv.org/pdf/2108.11544) | Single-/multi-turn and route-/goal-oriented task distinctions. |
| <a id="paper-foundation-model-survey"></a>**Foundation-Model VLN Survey · 2024** · arXiv<br>[Vision-and-Language Navigation Today and Tomorrow: A Survey in the Era of Foundation Models](https://arxiv.org/abs/2407.07035) | Organizes foundation-model roles in perception, language grounding, and planning. |

## Contributing

Contribute through an [Issue](https://github.com/Stagnation47/Awsome-VLN/issues) or [Pull Request](https://github.com/Stagnation47/Awsome-VLN/pulls). Include the full title, publication or recorded year, venue (or arXiv), paper and code links, task setting, model role, representation, learning strategy, and relevant evaluation conditions. Add one canonical catalog record and link it from any relevant reading guides. Mark uncertain attributes explicitly rather than inferring them from a paper's title.

## Acknowledgements

This collection is adapted from [awesome-embodied-vla-va-vln](https://github.com/jonyzhang2023/awesome-embodied-vla-va-vln). Thanks to the original maintainers and contributors.
