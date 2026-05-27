---
title: "VoxDet: Rethinking 3D Semantic Scene Completion as Dense Object Detection"
title_zh: "VoxDet: 将3D语义场景补全重新思考为稠密目标检测"
authors: "Wuyang Li, Zhu Yu, Alexandre Alahi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=lMhNrt0Bnm"
tags: ["query:lidar-d-det"]
score: 6.0
evidence: 将3D语义场景补全重新定义为稠密目标检测
tldr: 现有语义场景补全方法视为稠密分割任务，忽略实例级区分性，导致实例不完整。本文提出VoxDet，将场景补全重新定义为稠密目标检测，并利用训练免费的体素到实例转换技巧，从类别标签中获取实例信息。方法提升了场景补全中的实例完整性和边界清晰度，在多个基准上取得最佳性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 876, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1401, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 937, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1373, \"height\": 294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1408, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 638, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1437, \"height\": 1058, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 452, \"height\": 247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1292, \"height\": 716, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 422, \"height\": 242, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 422, \"height\": 243, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1306, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1171, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1454, \"height\": 2253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lmhnrt0bnm/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1460, \"height\": 2252, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 635, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 620, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 590, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 674, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 677, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 809, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 473, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 713, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1432, \"height\": 1143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 732, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1441, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 296, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 295, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 296, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lmhnrt0bnm/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1441, \"height\": 200, \"label\": \"Table\"}]"
motivation: 传统场景补全方法缺乏实例级区分，造成实例不完整和边界歧义。
method: 将场景补全转为稠密目标检测，并设计体素到实例转换技巧。
result: 在场景补全数据集上实现实例完整性和语义准确性的双重提升。
conclusion: 将检测视角引入场景补全有效利用了标签中的实例信息，开辟了新方向。
---

## Abstract
Semantic Scene Completion (SSC) aims to reconstruct the 3D geometry and semantics of the surrounding environment. With dense voxel labels, prior works typically formulate SSC as a *dense segmentation task*, independently classifying each voxel. However, this paradigm neglects critical instance-centric discriminability, leading to instance-level incompleteness and adjacent ambiguities. To address this, we highlight a "free lunch" of SSC labels: the voxel-level class label has implicitly told the instance-level insight, which is ever-overlooked by the community. Motivated by this observation, we first introduce a training-free **Voxel-to-Instance (VoxNT) trick**: a simple yet effective method that freely converts voxel-level class labels into instance-level offset labels. Building on this, we further propose **VoxDet**, an instance-centric framework that reformulates the voxel-level SSC as *dense object detection* by decoupling it into two sub-tasks: offset regression and semantic prediction. Specifically, based on the lifted 3D volume, VoxDet first uses (a) Spatially-decoupled Voxel Encoder to generate disentangled feature volumes for the two sub-tasks, which learn task-specific spatial deformation in the densely projected tri-perceptive space. Then, we deploy (b) Task-decoupled Dense Predictor to address SSC via dense detection. Here, we first regress a 4D offset field to estimate distances (6 directions) between voxels and the corresponding object boundaries in the voxel space. The regressed offsets are then used to guide the instance-level aggregation in the classification branch, achieving instance-aware scene completion. VoxDet can be deployed on both camera and LiDAR input and jointly achieves state-of-the-art results on both benchmarks, which gives 63.0 IoU on the SemanticKITTI test set, **ranking 1$^{st}$** on the online leaderboard.

---

## 论文详细总结（自动生成）

好的，以下是基于所提供论文内容生成的结构化中文总结。

---

### 1. 论文的核心问题与整体含义

*   **研究背景**：3D语义场景补全（SSC）旨在从传感器数据（如相机、激光雷达）重建完整的环境几何结构和语义信息，是自动驾驶与机器人导航中的关键任务。现有方法通常将SSC视为密集的体素分割任务，独立地对每个体素进行分类。
*   **核心问题**：这种“体素中心”的分割范式忽略了关键的**实例级区分性**，导致补全结果存在实例不完整（如汽车被截断）、相邻实例边界模糊等问题。这是因为分割方法在空间中不考虑哪些体素共同构成一个独立物体，如同“只见树木，不见森林”。
*   **整体含义**：作者发现了一个被忽视的“免费午餐”——**仅使用体素级别的语义标签，隐含地包含了实例级别的信息**。受此启发，本文提出了一种范式转变，将语义场景补全从“密集分割”重新定义为“**密集目标检测**”，从而利用实例级洞察来提升补全的完整性和精确性。

### 2. 论文提出的方法论

*   **核心思想**：将SSC解耦为两个子任务——**实例偏移回归**和**语义预测**，以此实现实例感知的场景补全。
*   **关键技术细节**：
    *   **体素到实例 (VoxNT) 技巧**：一个无需训练的方法，直接从体素级语义标签中生成实例级偏移标签。其核心是对每个体素，在六个方向（±X， ±Y， ±Z）上扫描，直到语义标签发生变化，以此计算出该体素到其所属实例边界的距离。这些距离构成了一个4D偏移场作为回归的真值。
    *   **VoxDet 整体框架**：
        1.  **2D到3D的提升 (Lifting)**：基于输入图像和估计的深度图，使用LSS等方法生成初始的3D特征体积 $V$。
        2.  **空间解耦体素编码器 (SVE)**：在密集投影的三视角空间 (Tri-Perceptive View) 中，将共享的3D体素特征 $V$ 解耦为两个任务特定的特征体积 $V_{\text{cls}}$ (用于分类) 和 $V_{\text{reg}}$ (用于回归)，通过可变形卷积学习任务特定的空间变形，以解决特征错位问题。
        3.  **任务解耦密集预测器 (TDP)**：
            *   **回归分支**：输入 $V_{\text{reg}}$，预测一个4D偏移场 $\Delta$，其每个元素是一个6维向量，表示该体素到实例边界在6个方向上的距离。
            *   **分类分支**：输入 $V_{\text{cls}}$，利用回归分支预测的偏移 $\Delta$，以注意力机制自适应地聚合属于同一实例边界附近的体素特征，从而增强实例级语义，最终进行语义分类。
*   **核心公式与优化**：
    *   **回归损失**：使用L1损失函数来监督预测偏移 $\Delta$ 和 VoxNT 技巧生成的真值偏移 $\hat{\Delta}$ 之间的差异：$L_{\text{reg}} = \sum |\Delta - \hat{\Delta}|$。
    *   **整体优化目标**：$L_{\text{VoxDet}} = L_{\text{cls}} + L_{\text{reg}} + \lambda L_{\text{aux occ}}$，其中 $L_{\text{cls}}$ 是分类损失，$L_{\text{aux occ}}$ 是辅助的体素分割损失。

### 3. 实验设计

*   **数据集与基准**：
    *   **SemanticKITTI**：基于KITTI里程计数据集的SSC基准，评估几何 (IoU) 和语义 (mIoU) 补全性能。
    *   **SSCBench-KITTI-360**：基于KITTI-360数据集的SSC基准，提供更多样的场景。
    *   **模态**：同时评估了**纯相机**和**纯激光雷达**输入两种设定下的性能。
*   **对比方法**：
    *   **相机方法**：对比了大量最新成果，包括 MonoScene, VoxFormer, SurroundOcc, OccFormer, Symphonize, HASSC, StereoScene, H2GFormer, MonoOcc, CGFormer, HTCL, ScanSSC 等。
    *   **激光雷达方法**：对比了 SSCNet, LMSCNet, Local-DIFs, JS3C-Net, SSA-SC, VPNet, L2COcc-L 等。

### 4. 资源与算力

*   **硬件配置**：所有实验在 **2块 NVIDIA A100 GPU (40G显存)** 上进行。
*   **训练批次与时长**：批大小设置为4（每GPU 2个样本）。在 SemanticKITTI 数据集上，训练一个单帧模型大约需要 **9小时**；在 SSCBench-KITTI-360 数据集上则需要约 **18小时**。文中特别指出，此训练成本对拥有商业级GPU的研究团队非常友好。

### 5. 实验数量与充分性

实验设计**非常充分且客观**，具体体现在：
*   **多基准全面验证**：在两个主流SSC基准（SemanticKITTI和SSCBench-KITTI-360）的在线隐藏测试集上均进行了评估，确保了结果的权威性。
*   **跨模态扩展**：不仅限于主流相机方案，还将方法直接扩展到纯激光雷达输入，并在SemanticKITTI激光雷达排行榜上同样取得第一，证明了方法的普适性。
*   **详尽的消融研究**：
    *   对提出的TDP（回归/分类分支）和SVE（空间解耦）各个模块逐一进行消融，分析贡献。
    *   对比了不同的SSC范式（分割、朴素FCOS检测、VoxDet），证明其独特优势。
    *   分析了不同的设计变体，如聚合方式、投影方式、解耦方式等。
*   **鲁棒性与效率分析**：
    *   提供了**多次实验（5次）的稳定性分析**，展示了结果的鲁棒性。
    *   与SOTA方法进行了模型**参数量和推理速度**的对比，显示其高效性。
    *   比较了使用单目深度估计器的性能，展示了其对深度精度的鲁棒性。
*   **深度见解分析**：通过调制偏移缩放因子 $\alpha$ 的实验，深入探索并论证了实例级聚合究竟在何处起作用的物理含义（靠近边界）。

### 6. 论文的主要结论与发现

*   3D体素空间的无遮挡特性，使得从语义标签中推断实例级的几何信息成为可能，这是一直被社区忽略的“免费午餐”。
*   将SSC重新定义为密集目标检测任务，并辅以VoxNT技巧，可以在**无需任何额外实例标注**的情况下，实现真正的实例级感知。
*   所提出的VoxDet模型，通过空间解耦和任务解耦设计，在相机和激光雷达两大SSC基准上均取得了最优性能，同时在模型参数量和推理效率上保持显著优势。
*   该方法能有效改善对动态物体标签噪声的鲁棒性，并能更合理地预测被错误标注的物体边界。

### 7. 优点

*   **创新性强**：提出了一个全新的视角（“密集检测”）来解决SSC问题，这是范式级的创新。
*   **巧妙利用数据**：VoxNT技巧极具洞察力，从免费标签中挖掘出高价值的监督信号，无需增加标注成本。
*   **性能顶尖**：在多个权威基准测试集上达到State-of-the-art，且同时在相机和激光雷达榜单上排名第一。
*   **效率与精度兼得**：模型设计轻量化，推理速度快，但性能远超参数更多的复杂模型。
*   **实验扎实**：不仅提供了充分的性能对比，还通过大量消融和可视化，深入剖析了每个设计的原理和效果（如实例聚合的有效性分析），为后续工作提供了宝贵洞察。
*   **应用灵活**：方法不局限于具体模态，可灵活部署于纯视觉或激光雷达系统。

### 8. 不足与局限

*   **无法直接输出稀疏实例**：目前的VoxDet仅利用实例边界信息增强密集预测，无法直接输出如3D边界框等稀疏实例表达，尚不能完全替代独立的检测任务。
*   **依赖深度估计精度**：视觉方案的效果在一定程度上受制于上游深度估计模型的准确性，尤其是在远距离或密集重叠场景下。
*   **密集场景假设失效**：在实例在标注中就已天然融合的场景（如重叠的树冠）下，其“实例可分离”的假设可能不成立，方法会退化为传统分割，无法进一步区分实例。
*   **对错误标签的处理能力有限**：虽然能识别出动态物体的错误标签（如拖尾），并提供更合理的预测，但这种“合理”反而可能因与错误真值不符而在IoU等指标上受到惩罚。

（完）
