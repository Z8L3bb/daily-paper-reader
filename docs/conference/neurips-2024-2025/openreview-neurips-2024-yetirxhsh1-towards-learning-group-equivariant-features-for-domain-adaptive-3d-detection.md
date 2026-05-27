---
title: Towards Learning Group-Equivariant Features for Domain Adaptive 3D Detection
title_zh: 面向域自适应3D检测的学习群等变特征方法
authors: "Sangyun Shin, Yuhang He, Madhu Vankadari, Ta-Ying Cheng, Qian Xie, Andrew Markham, Niki Trigoni"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=YEtirXhsh1"
tags: ["query:stage-d-det"]
score: 8.0
evidence: 在大型室外点云中进行三维目标检测并适应域间差异
tldr: 针对室外点云3D目标检测中的域间差异问题，提出学习群等变特征以联合处理多种域偏移因素，通过组等变特征学习提升跨域检测性能。实验表明，方法能有效减小域间隙，增强模型在未知环境中的泛化能力。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-yetirxhsh1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yetirxhsh1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yetirxhsh1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1428, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yetirxhsh1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yetirxhsh1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 728, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yetirxhsh1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yetirxhsh1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 457, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-yetirxhsh1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1481, \"height\": 1048, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yetirxhsh1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 719, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yetirxhsh1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 592, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yetirxhsh1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 916, \"height\": 348, \"label\": \"Table\"}]"
motivation: 3D目标检测在未知环境中性能因域间隙严重下降。
method: 提出群等变特征学习，联合处理物体尺寸、形状和密度变化等多因素。
result: 在跨域设置中有效减小域间隙，提升检测准确率。
conclusion: 群等变特征学习为域自适应3D检测提供了有效解决方案。
---

## Abstract
The performance of 3D object detection in large outdoor point clouds deteriorates significantly in an unseen environment due to the inter-domain gap. To address these challenges, most existing methods for domain adaptation harness self-training schemes and attempt to bridge the gap by focusing on a single factor that causes the inter-domain gap, such as objects' sizes, shapes, and foreground density variation. However, the resulting adaptations suggest that there is still a substantial inter-domain gap left to be minimized. We argue that this is due to two limitations: 1) Biased pseudo-label collection from self-training. 2) Multiple factors jointly contributing to how the object is perceived in the unseen target domain. In this work, we propose a grouping-exploration strategy framework,  Group Explorer Domain Adaptation ($\textbf{GroupEXP-DA}$), to addresses those two issues. Specifically, our grouping divides the available label sets into multiple clusters and ensures all of them have equal learning attention with the group-equivariant spatial feature, avoiding dominant types of objects causing imbalance problems. Moreover, grouping learns to divide objects by considering inherent factors in a data-driven manner, without considering each factor separately as existing works. On top of the group-equivariant spatial feature that selectively detects objects similar to the input group, we additionally introduce an explorative group update strategy that reduces the false negative detection in the target domain, further reducing the inter-domain gap. During inference, only the learned group features are necessary for making the group-equivariant spatial feature, placing our method as a simple add-on that can be applicable to most existing detectors. We show how each module contributes to substantially bridging the inter-domain gaps compared to existing works across large urban outdoor datasets such as NuScenes, Waymo, and KITTI.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **研究背景**：3D 目标检测在室外大场景点云中面临严重的跨域性能下降问题（如 Waymo → NuScenes 等），主要源于传感器差异导致的域间差距。
- **现存问题**：
  - 主流的自训练（self-training）范式倾向于收集高置信度伪标签，但这些伪标签大多来自源域中占主导的物体类型，导致模型偏向常见物体，忽视稀疏或罕见外观的物体。
  - 现有方法往往仅针对单一因素（如物体尺寸、密度、几何形状）来减小域差异，而物体的外观是由多种因素联合决定的，单一因素无法全面解释域间差距。
- **本文目标**：提出一种分组‑探索策略框架 **GroupExp-DA**，通过数据驱动的方式发现物体的内在群组，实现群等变特征学习，使得所有群组获得均等的学习关注，从而同时应对多因素造成的域间差距。

## 2. 论文提出的方法论
### 2.1 核心思想
- 不再将伪标签视为同等重要，而是对可用标签进行聚类，形成若干群组，并确保每个群组在检测器学习中获得均衡注意力。
- 通过学习群等变空间特征，使网络能够根据输入群组查询，选择性地检测与该群组相似的物体，从而缓解主导群组的偏差。
- 引入探索式群组更新策略，利用目标域伪标签不断更新群组参数，使群组分布更好地反映目标域特性，减少漏检。

### 2.2 关键技术细节
- **对象描述符提取**：从已知边界框提取前景点，通过 MLP + 全局最大池化得到每框的对象描述符 \(F_{obj} \in \mathbb{R}^{n_b \times d_{obj}}\)。
- **渐进式分组**：
  - 使用 K‑Means 初始化 \(n_g\) 个群组，然后用最大似然估计得到高斯混合模型（GMM）参数 \(\mu, \sigma, \phi\)。
  - 对每批数据，按高斯概率分布确定样本归属群组（公式 1、2）。
  - 在训练过程中，利用该批数据统计各群组的样本均值、协方差和权重（公式 3），并与历史参数进行加权滑动更新（公式 5），参数 \(\alpha\) 控制更新保守程度。
  - 引入群间排斥损失 \(L_{rep}\)（公式 6）和群内吸引损失 \(L_{att}\)（公式 7），推动群组可分且紧致。
- **群‑区域相关（Group‑Region Correlation）**：
  - 将群组均值 \(\mu_i\) 作为查询，与骨干网络产生的 BEV 特征 \(F_{bev}\) 进行交叉注意力，生成群等变空间特征 \(F^i_{cbev}\)（公式 8）。
  - 每个群组对应的 \(F^i_{cbev}\) 送入共享的 RPN 进行目标检测，只预测属于该群组的物体，从而选择性检测。
- **探索式群组更新**：利用目标域的伪标签重新估计群组参数，赋予伪标签更高权重，使得群组特征向目标域偏移，减少假阴性。
- **整体训练**：总损失为 \(L = \lambda_1 L_{rep} + \lambda_2 L_{att} + \lambda_3 L_{det}\)，其中 \(L_{det}\) 为各群组检测损失的平均（公式 10）。训练遵循自训练循环，伪标签逐步扩增。推理时仅使用群组均值生成群等变特征，基线 RPN 也参与最终测试，保证推理速度不变。

## 3. 实验设计
### 3.1 数据集与适配场景
- **数据集**：KITTI（64 线）、NuScenes（32 线）、Waymo（1×64 线 + 4×200 线）。
- **三个跨域适配任务**（仅限“car”类）：
  - Waymo → NuScenes、NuScenes → KITTI、Waymo → KITTI。
- **基础检测器**：SECOND‑IoU 和 PointPillars。

### 3.2 对比方法
- 与近年域自适应检测方法对比：SN、3D‑CoCo、ST3D、ST3D++、GPA‑3D、DTS。
- 同时报告源域仅训练（Source Only）和全监督（Oracle）作为下界与上界。

### 3.3 评估指标
- 采用 \(AP_{BEV}\)（鸟瞰图 IoU=0.7）和 \(AP_{3D}\)（3D 框 IoU=0.7），40 个召回点。

## 4. 资源与算力
- 训练使用 **1 块 NVIDIA A10 GPU**。
- 预训练阶段 50 epochs，batch size 8；自训练阶段额外 30 epochs 调优。
- 学习率 \(1\times 10^{-4}\)，Adam 优化器，余弦退火调度。

## 5. 实验数量与充分性
- **定量实验**：3 个适配任务 × 2 种检测器，共 6 组主要对比（见表 1），结果全面超越现有 SOTA。
- **消融实验**：
  - 各组件逐步添加（分组、\(L_{att}\)、\(L_{rep}\)、探索更新）对性能的影响（表 2）。
  - 群组数量 \(n_g\) 的敏感性分析，在 3 种适配任务上测试（图 5）。
  - 对比 GMM 分组与基于距离的分组，及不同更新系数 \(\alpha\) 的影响（表 3）。
- **定性实验**：展示了基线、DTS 和本方法在特定场景下的检测框可视化，验证了对假阳性/假阴性的改善。
- **多类别适配**：在 NuScenes → KITTI 上进行 car/pedestrian/cyclist 三分类实验，证明可与现有方法 ReDB 结合并提升性能（附录表 II）。
- **实验充分性**：实验覆盖主流场景、检测器，对比方法完备，消融分析细致，并且涉及定性比较和多类别拓展，整体设计合理、公平。

## 6. 论文的主要结论与发现
- **主要结论**：所提出的 GroupExp‑DA 通过数据驱动分组和群等变特征学习，能有效联合处理多因素域差异，显著桥接跨域性能差距。
- **定量结果**：在几乎所有场景下均优于现有方法，例如 Waymo→KITTI 任务上 SECOND‑IoU 检测器 \(AP_{BEV}/AP_{3D}\) 达到 86.94/73.70，提升明显。
- **消融发现**：探索更新和组间排斥损失贡献最大，GMM 分组稳定性优于纯距离分组，适当增大组数可提升性能但超过 6 组时性能下降。
- **泛化能力**：方法可作为即插即用模块模块嵌入现有检测器，多类别适配也显示协同增益。

## 7. 优点
- **问题建模新颖**：首次从多因素联合角度看待域适应，用数据驱动分组替代人为解耦单一因素。
- **群等变机制**：通过群组查询与空间特征的交叉注意力，自然地使不同群组关注不同物体，缓解类别/样本不平衡。
- **探索式更新**：合理重用目标域伪标签来更新群组参数，提高了对目标域未知物体的召回能力。
- **轻量且通用**：仅需群组均值即可驱动，推理速度与基线一致，易于集成到大多数体素基检测器。

## 8. 不足与局限
- **极度稀疏点云物体**：当物体点云过于稀疏时（如远距离小目标），仍难以形成有区分性的群组特征，检测困难（文中明确承认）。
- **群组数量敏感**：最佳群组数 \(n_g\) 需要在不同任务上调参，过大时容易因每组样本过少而欠拟合或过拟合。
- **初始伪标签依赖**：方法基于自训练框架，若初始伪标签质量极差，群组更新可能引入噪声，尽管探索更新策略有一定缓解，但未完全消除该风险。
- **仅验证于车类为主**：主要实验集中在“car”类，多类别适配只在一组实验下测试，且提升幅度不如单类显著，对其他类别（如行人）的普适性需更多验证。
- **计算复杂度微增**：虽推理速度不变，但训练时因为每个群组都要生成一次群等变特征并送入 RPN，会增加一定显存和计算负担（文中未明确量化）。

（完）
