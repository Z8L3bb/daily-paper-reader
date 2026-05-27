---
title: "LiT: Unifying LiDAR \"Languages\" with LiDAR Translator"
title_zh: LiT：通过LiDAR翻译器统一LiDAR语言
authors: "Yixing Lao, Tao Tang, Xiaoyang Wu, Peng Chen, Kaicheng Yu, Hengshuang Zhao"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=wcX04Wn34u"
tags: ["query:lidar-d-det"]
score: 6.0
evidence: LiDAR数据跨域迁移翻译
tldr: 针对LiDAR数据在不同传感器、车辆和场景下的域差异问题，提出LiDAR翻译器LiT。LiT通过场景建模模块、统计射线建模及硬件加速射线投射，实现跨域点云直接转换，从而支持零样本和统一域检测。实验表明，LiT在多个检测数据集上取得了领先的跨域和联合学习性能，为LiDAR感知模型的可扩展性提供了新思路。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-wcx04wn34u/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 939, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wcx04wn34u/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wcx04wn34u/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wcx04wn34u/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wcx04wn34u/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wcx04wn34u/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 736, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wcx04wn34u/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1455, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wcx04wn34u/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1396, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wcx04wn34u/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1367, \"height\": 986, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wcx04wn34u/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1428, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wcx04wn34u/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1453, \"height\": 378, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-wcx04wn34u/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wcx04wn34u/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wcx04wn34u/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 823, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wcx04wn34u/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wcx04wn34u/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 677, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wcx04wn34u/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 716, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wcx04wn34u/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 792, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wcx04wn34u/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 633, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wcx04wn34u/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1440, \"height\": 461, \"label\": \"Table\"}]"
motivation: 不同LiDAR收集的点云存在显著域差异，限制模型泛化。
method: 设计LiT框架，包含场景建模、统计射线建模和射线投射引擎。
result: 实现零样本和统一域的最先进检测性能。
conclusion: LiT有效弥合LiDAR域鸿沟，提升感知模型的可扩展性。
---

## Abstract
LiDAR data exhibits significant domain gaps due to variations in sensors, vehicles, and driving environments, creating “language barriers” that limit the effective use of data across domains and the scalability of LiDAR perception models. To address these challenges, we introduce the LiDAR Translator (LiT), a framework that directly translates LiDAR data across domains, enabling both cross-domain adaptation and multi-domain joint learning. LiT integrates three key components: a scene modeling module for precise foreground and background reconstruction, a LiDAR modeling module that models LiDAR rays statistically and simulates ray-drop, and a fast, hardware-accelerated ray casting engine. LiT enables state-of-the-art zero-shot and unified domain detection across diverse LiDAR datasets, marking a step toward data-driven domain unification for autonomous driving systems. Source code and demos are available at: https://yxlao.github.io/lit.

---

## 论文详细总结（自动生成）

好的，这是对论文《LiT: Unifying LiDAR “Languages” with LiDAR Translator》的结构化深入总结。

### 1. 论文的核心问题与整体含义
*   **核心问题**：不同厂商、不同配置（如线束数量、视场角）的 LiDAR 传感器采集的点云数据之间存在显著的域差异，这被论文比喻为“语言障碍”。这些差异导致在一个 LiDAR 数据集上训练的感知模型，直接应用到另一个数据集时性能会大幅下降，严重阻碍了模型的跨域泛化能力和多数据集联合训练。
*   **整体含义**：论文提出了一种名为 LiDAR Translator (LiT) 的**数据驱动**框架。与以往在模型层面做适配的方法不同，LiT 的目标是像语言翻译器一样，直接将源域的 LiDAR 数据“翻译”成目标域的“语言”（即数据风格），从而从根本上消除域差异。这使得模型可以在统一风格的数据上进行训练和推理，实现零样本跨域检测和多源数据联合学习，有望突破 LiDAR 感知模型训练规模化的瓶颈。

### 2. 论文提出的方法论
LiT 框架包含三个核心组件，协同完成数据翻译：

*   **场景建模**
    *   **前景建模**：针对动态物体（本文主要指车辆），利用多帧 LiDAR 点云进行融合。通过从 ShapeNet 数据集预训练的 SDF（有符号距离函数）神经隐式表示模型，为每个被追踪的车辆优化出一个潜在编码，从而重建出高保真的、多样化的车辆 3D 网格模型。
    *   **背景建模**：移除前景物体后的静态环境点云，通过一个可泛化的层次化神经核场进行高效重建，无需像传统方法那样为每个新场景重新训练，显著提升了效率。
*   **LiDAR 建模**
    *   **射线角度统计建模**：不采用均匀分布假设，而是从少量目标域数据中统计分析 LiDAR 垂直角的分布模式，找出主要的峰值角度，并据此生成模拟射线，使模拟数据更贴近真实传感器的扫描模式。
    *   **射线丢弃建模**：训练一个 MLP 网络来预测射线被丢弃的概率。该网络以射线方向、距离和入射角为输入，学习模拟因物体反射率、吸收等因素造成的真实 LiDAR 扫描中常见的“丢点”现象。
*   **硬件加速的射线投射引擎**
    *   将场景建模得到的网格和 LiDAR 建模产生的射线作为输入，通过自研的、在 CPU（Intel Embree）和 GPU（Nvidia OptiX）上加速的射线投射引擎，高效计算射线与网格的交点，最终生成带有目标域特性的模拟点云。

### 3. 实验设计
*   **数据集与场景**：实验覆盖了自动驾驶领域三个主流且差异巨大的 LiDAR 数据集：
    *   **Waymo Open Dataset**: 64 线 LiDAR
    *   **nuScenes**: 32 线 LiDAR
    *   **KITTI**: 64 线 LiDAR（但扫描模式与 Waymo 不同）
    *   具体的跨域迁移场景包括：`Waymo → KITTI`、`Waymo → nuScenes`、以及 `nuScenes → KITTI`。
*   **下游任务与基准**：以**3D 目标检测**（针对车辆类别）为核心评测任务，使用 KITTI 标准的 AP_BEV 和 AP_3D（IoU=0.7）作为评估指标。
*   **检测模型**：在 `SECOND-IoU` 和 `PV-RCNN` 两种检测器上验证。
*   **对比方法**：
    *   **Source Only**: 源域训练，目标域直接测试的下限。
    *   **Oracle**: 目标域数据训练，目标域测试的上限。
    *   **模型驱动的域适应方法**：`SN`（统计归一化）、`ST3D`（自训练）。
    *   **数据驱动的域适应方法**：`ReSimAD`（重建+模拟）。

### 4. 资源与算力
*   **硬件配置**：论文明确指出，LiT 的**场景重建和射线投射过程**在所有实验中均在一块 **NVIDIA RTX 4090 GPU** 上进行。
*   **运行时长**：LiT 非常高效。报告显示，完成一个约 200 帧的 LiDAR 序列的完整翻译，总耗时不到 1 分钟。其中，射线投射阶段更是达到了实时性能（22-31 Hz）。这相对于需要数小时的 NeuS 重建方法（如 ReSimAD 所用），效率优势明显。

### 5. 实验数量与充分性
论文实验设计较为全面和充分，客观性与公平性较强：
*   **多场景定量评估**：涵盖了三种数据集组合下的跨域翻译任务，并设置了完备的单源域零样本检测、多源域统一学习等不同实验设置。实验对比了多种模型驱动和数据驱动基线，并使用两个标准检测器，确保了结论的普适性和公平性。
*   **翻译质量评估**：除下游任务外，还从分布对齐角度出发，使用 MMD 和 JSD 统计指标度量翻译后数据与真实目标域数据的相似性，提供了直接的评价维度。
*   **消融实验**：设计了丰富的消融实验来分析关键组件的贡献，包括：
    *   前景物体的多样性。
    *   前景、背景及联合场景重建的精度（添加不同强度高斯噪声）。
*   这些实验充分验证了方法设计的有效性以及各组件的容错能力。

### 6. 论文的主要结论与发现
*   LiT 作为一种数据驱动的域统一方法，能有效弥合不同 LiDAR 数据间的“语言障碍”。
*   在零样本 3D 目标检测任务中，LiT 显著优于现有 SOTA 方法（如 ST3D、ReSimAD），大幅收窄了与 Oracle 上限之间的性能差距。
*   通过 LiT 将多源数据（如Waymo+nuScenes）翻译至统一目标域（KITTI）后，进行联合训练，其性能可超越单一源域训练，甚至在部分指标上超越了使用全量目标域数据训练的 Oracle 模型，证明了数据规模化带来的巨大潜力。

### 7. 优点
*   **范式创新**：从主流的“模型适配”转向“数据翻译”的新范式，为解决 LiDAR 域泛化问题开辟了新思路。
*   **系统完备与精细**：LiT 是一个从场景建模到传感器物理特性模拟的完备系统，对 LiDAR 的垂直角分布和丢点现象进行了精细建模，是其效果超越简单模拟方法的关键。
*   **高效与可扩展**：自研的加速引擎和可泛化的背景建模使得整个翻译流程极其高效，为处理大规模数据集和实际部署提供了可能。
*   **灵活可组合**：LiDAR 模型与场景模型解耦，可以灵活地将某个数据集的 LiDAR 特性“部署”到任意其他重建场景（如Mai City）中，应用潜力大。

### 8. 不足与局限
*   **依赖源域标注**：前景物体的重建依赖于 3D 目标跟踪信息，而这些信息通常需要大量标注，这在一定程度上限制了其在完全无监督场景下的应用。
*   **仅针对车辆类别**：当前的工作仅重建和评估了“车辆”这一种前景对象，尚未扩展到行人、骑行者等其他关键交通参与者。
*   **模态与组件限制**：方法仅利用 LiDAR 数据，未融合相机等其他传感器信息。同时，其 LiDAR 模拟未考虑运动模糊等更复杂的物理效应。
*   **统计建模的依赖性**：LiDAR 射线统计建模依赖于一小部分无标注的目标域数据，虽然不需要人工标注，但并非完全零样本。

（完）
