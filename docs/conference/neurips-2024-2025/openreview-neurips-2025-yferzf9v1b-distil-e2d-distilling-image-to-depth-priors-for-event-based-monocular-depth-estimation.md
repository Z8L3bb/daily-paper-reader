---
title: "Distil-E2D: Distilling Image-to-Depth Priors for Event-Based Monocular Depth Estimation"
title_zh: "Distil-E2D: 为基于事件的单目深度估计蒸馏图像到深度先验"
authors: "Jie Long Lee, Gim Hee Lee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=yFerzf9v1b"
tags: ["query:lidar-d-det"]
score: 4.0
evidence: 通过生成稠密合成伪标签解决稀疏LiDAR深度监督问题
tldr: 事件相机在挑战光照下具有单目深度估计潜力，但LiDAR深度标签稀疏且不完整，制约学习效果。本工作提出Distil-E2D框架，将图像域的深度先验蒸馏至事件域，生成稠密合成伪标签。实验证明该方法能有效提升事件驱动深度估计的精度，为从稀疏LiDAR标签学习高密度深度提供新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yferzf9v1b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yferzf9v1b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yferzf9v1b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 730, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yferzf9v1b/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 556, \"height\": 558, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yferzf9v1b/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 870, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yferzf9v1b/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1450, \"height\": 545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yferzf9v1b/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 872, \"height\": 440, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yferzf9v1b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yferzf9v1b/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yferzf9v1b/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 580, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yferzf9v1b/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1026, \"height\": 187, \"label\": \"Table\"}]"
motivation: 基于事件的深度估计受限于稀疏LiDAR深度标签，导致学习密度深度困难。
method: 通过蒸馏图像域深度先验到事件域，生成稠密合成伪标签。
result: 在事件相机深度估计基准上取得性能提升。
conclusion: 跨模态蒸馏能有效缓解稀疏监督问题，为事件相机深度估计提供实用方案。
---

## Abstract
Event cameras are neuromorphic vision sensors that asynchronously capture pixel-level intensity changes with high temporal resolution and dynamic range. These make them well suited for monocular depth estimation under challenging lighting conditions. However, progress in event-based monocular depth estimation remains constrained by the quality of supervision: LiDAR-based depth labels are inherently sparse, spatially incomplete, and prone to artifacts. Consequently, these signals are suboptimal for learning dense depth from sparse events. To address this problem, we propose Distil-E2D, a framework that distills depth priors from the image domain into the event domain by generating dense synthetic pseudolabels from co-recorded APS or RGB frames using foundational depth models. These pseudolabels complement sparse LiDAR depths with dense semantically rich supervision informed by large-scale image-depth datasets. To reconcile discrepancies between synthetic and real depths, we introduce a Confidence-Guided Calibrated Depth Loss that learns nonlinear depth alignment and adaptively weights supervision by alignment confidence. Additionally, our architecture integrates past predictions via a Context Transformer and employs a Dual-Decoder Training scheme that enhances encoder representations by jointly learning metric and relative depth abstractions. Experiments on benchmark datasets show that Distil-E2D achieves state-of-the-art performance in event-based monocular depth estimation across both event-only and event+APS settings.

---

## 论文详细总结（自动生成）

# Distil-E2D: 为基于事件的单目深度估计蒸馏图像到深度先验

## 1. 论文的核心问题与整体含义（研究动机和背景）
- 事件相机（event cameras）具有高时间分辨率、高动态范围的特点，特别适合在低光照、高速运动等挑战性条件下进行单目深度估计（MDE）。
- 但是，目前事件基单目深度估计（EMDE）的进展受限于监督信号的质量：LiDAR得到的深度标签本身是稀疏的、空间不完整的，且容易产生伪影（如扫描线伪影、时间对齐误差）。
- 因此，从稀疏事件中学习稠密深度时，这些标签并理想。合成数据集虽然能提供稠密标签，但存在领域偏移，导致真实场景泛化性差。
- 图像基的单目深度估计已有强大的基础模型（如 Depth Anything V2），能够提供稠密、语义丰富的深度预测。然而，这些先验尚未被系统地用于事件领域来弥补监督差距。
- 本文提出 Distil-E2D，旨在将图像域的深度先验蒸馏至事件域，通过生成稠密的合成伪标签来补充稀疏的 LiDAR 监督，从而提升事件深度估计的稠密性和准确性。

## 2. 论文提出的方法论
### 核心思想
利用事件相机同步记录的 APS 或 RGB 图像，通过强大的图像基深度基础模型（DepthAnythingV2）生成稠密的合成深度伪标签，再结合稀疏 LiDAR 深度进行联合训练，实现从图像到事件模态的跨模态蒸馏。

### 关键技术细节
#### 事件表示
- 将异步事件流转换为体素网格表示：在固定时间窗口 \( \Delta T \) 内划分为 \( B \) 个时间仓，对每个事件执行时间归一化和线性插值，累积极性值，得到 \( \mathbf{V} \in \mathbb{R}^{H \times W \times B} \)。

#### 稠密深度先验蒸馏
- 使用预训练的 DepthAnythingV2 对每帧图像 \( I_t \) 生成合成深度 \( y_t^{syn} \)，作为稠密辅助监督。

#### 置信度引导的校准深度损失（CCDL）
- **非线性深度校准（NDC）**：用一个小的 MLP \( F_{cal} \) 在对数深度空间学习从相对深度到度量深度的非线性映射，损失为 \( \mathcal{L}_{cal} = \| \log \tilde{y}_t^{syn} - \log y_t^{gt} \|_2^2 \)。校准后的伪标签用于监督网络的度量预测。
- **对齐感知置信度估计（ACE）**：根据校准后深度与稀疏 LiDAR 的对齐程度计算逐像素置信度权重 \( w_t^s = \exp(-|\log \tilde{y}_t^{syn} - \log y_t^{gt}|) \)。利用一个轻量 CNN 从稀疏置信度、合成深度和稀疏掩码生成稠密置信图 \( w_t^d \)，并通过基础钳制（base clamping）和稀疏正则项防止权重退化。最终对齐损失 \( \mathcal{L}_{align} \) 由置信度加权。
- 总损失 \( \mathcal{L}_{ccd} = \mathcal{L}_{cal} + \tilde{w}_t^d \cdot \mathcal{L}_{align}(d_t^m, \tilde{y}_t^{syn}) + \mathcal{L}_{mde}(d_t^m, y_t^{gt}) \)，其中 \( \mathcal{L}_{mde} \) 是度量深度预测与 LiDAR 的监督损失（也使用尺度不变损失 + 梯度匹配损失）。

#### 网络架构
- **模型变体**：Distil-E2D (E)（仅事件）和 Distil-E2D (E+I)（事件+图像）。
- **上下文变换器（CT）**：在事件分支瓶颈处，通过交叉注意力融合来自上下分支（过去预测）的特征，以融入历史信息；在 E+I 设置中，还通过类似方式融合图像分支特征。
- **双解码器训练（DDT）**：同时使用度量深度解码器（用 CCDL 监督）和相对深度解码器（用未校准合成深度监督），分别输出 \( d_t^m \) 和 \( d_t^r \)，促使编码器学习更丰富的空间表征。

## 3. 实验设计
### 数据集与基准
- **MVSEC**：标准事件深度估计基准，包含同步事件、灰度 APS 图像和 LiDAR 深度。使用 `outdoor_day_2` 序列训练，其余四个序列测试。
- **DSEC**：高分辨率事件和 RGB 数据，41 个驾驶序列，28 个训练，13 个测试。

### 对比方法
- 事件仅有方法：ULODE、MDDE+、EMD、ERE、EvT+ (E)。
- 事件+图像方法：RAMNet、EvT+ (E+I)。

### 评估指标
- 10m、20m、30m 截止距离的平均深度误差（越低越好）。

## 4. 资源与算力
- **GPU**：单张 NVIDIA RTX A6000（48 GB 显存）。
- **伪标签生成**：每数据集耗时约 4-6 小时。
- **训练时长**：MVSEC 约 72 小时，DSEC 约 96 小时。
- 未使用分布式训练，整体算力需求对学术机构较友好。

## 5. 实验数量与充分性
### 实验组数概述
- **主实验**：两个数据集、两种输入模态（E 和 E+I），与 6 个基准方法对比。
- **消融实验**：在 MVSEC 上按顺序逐步添加合成深度、NDC、ACE、CT、DDT，共 6 行配置，全面验证每个组件的贡献。
- **额外分析**：在补充材料中对运动程度对上下文分支的影响进行了定量分析，并展示了 DSEC 上仅与 EMD 的比较。
- **实验充分性**：消融设计合理，覆盖所有主要创新点，实验公平（使用统一协议和公开数据集），结果具有说服力。

## 6. 论文的主要结论与发现
- Distil-E2D 在所有基准上均达到最优（SOTA）性能，无论是事件仅在还是事件+图像设置。
- 通过蒸馏图像基础模型的深度先验，可以有效弥补 LiDAR 稀疏监督的不足，生成更稠密、边界更清晰的深度图。
- NDC 能校正合成伪标签的非线性尺度偏差，比尺度不变损失更有效。
- ACE 通过学习置信度图，能自适应地强调可靠区域，进一步提升性能。
- CT 和 DDT 分别通过时序融合和多任务双解码器设计，带来额外改进。

## 7. 优点
- **首次系统地将图像基础深度模型的稠密先验蒸馏到事件领域**，无需合成事件数据，避免了领域偏移。
- **CCDL 设计精巧**：非线性校准解决了相对与度量深度的复杂偏差，置信度估计则灵活应对残留的不对齐。
- **架构创新**：上下文变换器提升时序连贯性，双解码器训练强化编码器表征，且设计合理、效果叠加。
- **实验充分**：在两个真实世界数据集上验证，涵盖消融、运动鲁棒性分析等，结论可信。

## 8. 不足与局限
- **依赖图像基础模型质量**：若伪标签生成模型在低光或弱纹理区域产生不准确预测，可能误导训练。
- **训练数据多样性有限**：仍受限于现有事件相机数据集的规模和场景覆盖，可能限制对复杂驾驶条件的泛化。
- **计算开销相对较大**：单卡训练需 3-4 天，且需额外生成伪标签的预处理时间。
- **运动加速度影响**：虽然上下文分支在多数情况下有益，但大运动时帧间对齐变差，可能导致性能退化（文中已分析）。
- **未对比更多最新事件基方法**：由于领域发展，部分较新的方法可能未被包含，但对比已覆盖代表性工作。

（完）
