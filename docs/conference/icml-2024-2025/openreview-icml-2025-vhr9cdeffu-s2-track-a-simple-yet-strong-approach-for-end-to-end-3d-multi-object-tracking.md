---
title: "S2-Track: A Simple yet Strong Approach for End-to-End 3D Multi-Object Tracking"
title_zh: S2-Track：一种简单而强大的端到端三维多目标跟踪方法
authors: "Tao Tang, Lijun Zhou, Pengkun Hao, Zihang He, Kalok Ho, Shuo Gu, Zhihui Hao, Haiyang Sun, Kun Zhan, Peng Jia, XianPeng Lang, Xiaodan Liang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vHr9cdeFfu"
tags: ["query:lidar-d-det"]
score: 8.0
evidence: 三维多目标跟踪在三维空间中同时检测和跟踪物体
tldr: 本文提出S2-Track，一种简单而强大的端到端三维多目标跟踪方法。将现有框架分解为查询初始化、传播和匹配三个模块，并针对每个模块进行改进。在自动驾驶场景的多项测试中，该方法显著提升了跟踪准确率，尤其在遮挡和小目标情况下表现优异，推动了端到端三维感知的实用化。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vhr9cdeffu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhr9cdeffu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1678, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhr9cdeffu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhr9cdeffu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhr9cdeffu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 562, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhr9cdeffu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1774, \"height\": 1145, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhr9cdeffu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1767, \"height\": 982, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vhr9cdeffu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1778, \"height\": 967, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhr9cdeffu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1776, \"height\": 790, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhr9cdeffu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1779, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhr9cdeffu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 520, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhr9cdeffu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 867, \"height\": 695, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhr9cdeffu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhr9cdeffu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 863, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhr9cdeffu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 815, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhr9cdeffu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1780, \"height\": 903, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhr9cdeffu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1779, \"height\": 821, \"label\": \"Table\"}]"
motivation: 现有端到端三维多目标跟踪方法缺乏系统改进，在遮挡和小目标场景下容易失败。
method: 将端到端三维多目标跟踪分解为查询初始化、查询传播和查询匹配三部分，并分别提出改进方案。
result: 在多个自动驾驶数据集上实现领先的跟踪精度，尤其改善了遮挡和小目标跟踪。
conclusion: S2-Track以简单设计实现了强大的三维跟踪性能，为端到端三维感知提供新基准。
---

## Abstract
3D multiple object tracking (MOT) plays a crucial role in autonomous driving perception. Recent end-to-end query-based trackers simultaneously detect and track objects, which have shown promising potential for the 3D MOT task. However, existing methods are still in the early stages of development and lack systematic improvements, failing to track objects in certain complex scenarios, like occlusions and the small size of target object’s situations. In this paper, we first summarize the current end-to-end 3D MOT framework by decomposing it into three constituent parts: query initialization, query propagation, and query matching. Then we propose corresponding improvements, which lead to a strong yet simple tracker: S2-Track. Specifically, for query initialization, we present 2D-Prompted Query Initialization, which leverages predicted 2D object and depth information to prompt an initial estimate of the object’s 3D location. For query propagation, we introduce an Uncertainty-aware Probabilistic Decoder to capture the uncertainty of complex environment in object prediction with probabilistic attention. For query matching, we propose a Hierarchical Query Denoising strategy to enhance training robustness and convergence. As a result, our S2-Track achieves state-of-the-art performance on nuScenes benchmark, i.e., 66.3% AMOTA on test split, surpassing the previous best end-to-end solution by a significant margin of 8.9% AMOTA. We achieve 1st place on the nuScenes tracking task leaderboard.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **研究背景**
    *   3D多目标跟踪是自动驾驶感知系统的核心组件，对安全导航和决策至关重要。
    *   传统方法依赖“检测-后处理”的流水线，流程复杂且依赖人工设计规则。
    *   基于查询的端到端跟踪器虽然能同时进行检测与跟踪，展现出巨大潜力，但仍处于发展早期。
*   **核心问题**
    *   现有的端到端查询式跟踪器缺乏系统性的改进，难以应对复杂的驾驶场景。
    *   在目标遮挡和目标尺寸过小等情况下，模型容易出现漏跟或跟丢的问题。
*   **研究动机与目标**
    *   本文旨在系统性地增强现有的端到端3D MOT框架，使其在复杂驾驶环境中实现鲁棒、准确的跟踪。
    *   通过分解现有框架并提出针对性的简单而强大的改进，打造一个强大且高效的跟踪器S2-Track。

### 2. 论文提出的方法论

S2-Track的核心思想是将现有端到端3D MOT框架分解为三个组成部分，并分别提出改进模块。

*   **框架分解**
    *   **查询初始化**：生成初始对象查询以寻找新目标或定位已有目标。
    *   **查询传播**：将前一帧的查询与初始查询结合，并通过解码器与图像特征交互来更新查询。
    *   **查询匹配**：利用更新后的查询预测3D边界框，并与真实框进行匹配以实现监督训练。
*   **关键技术模块**
    *   **2D提示查询初始化**：
        *   **动机**：解决随机初始化查询不可靠，导致在遮挡、小目标场景下跟踪丢失的问题。
        *   **方法**：利用辅助任务（2D检测和深度预测）来估计目标的初步3D位置，并以此初始化查询，同时保留部分随机查询以发现新目标。
    *   **不确定性感知概率解码器**：
        *   **动机**：应对复杂环境中目标运动模式、尺寸多样带来的预测不确定性。
        *   **方法**：将传统Transformer解码器中的确定性注意力机制，升级为概率注意力。具体而言，将注意力分数建模为高斯分布，并通过重参数化技巧进行采样，从而量化预测不确定性。
        *   **损失函数**：引入负对数似然损失来约束概率注意力的学习。
    *   **分层查询降噪**：
        *   **动机**：加速模型收敛，增强训练鲁棒性，尤其是在遮挡等困难场景下。
        *   **方法**：训练时向真实边界框添加噪声，生成“噪声查询”。根据噪声查询与真实框的3D IoU值，将其划分为正样本（低难度）、负样本（高难度）和忽略样本，并进行差异化降噪学习。模型需将噪声查询重建回原始边界框，从而增强对复杂情况的处理能力。

### 3. 实验设计

*   **数据集**
    *   **nuScenes**：大型自动驾驶数据集，包含700段训练、150段验证和150段测试场景。每帧包含6个环视相机图像和1个激光雷达点云，提供7个类别的3D跟踪边界框。
*   **评估指标**
    *   **跟踪任务**：采用nuScenes官方指标，主要指标包括AMOTA、AMOTP、RECALL、MOTA、MOTP和IDS。
    *   **检测任务**：同时报告NDS、mAP以及mATE、mASE等细粒度误差指标。
*   **对比方法**
    *   与大量现有方法进行了对比，涵盖了：
        *   **传统检测式跟踪**：如DEFT, QD-3DT, CC-3DT, Cyclic, QTrack等。
        *   **基于查询的端到端跟踪**：如MUTR3D, STAR-TRACK, DQTrack, PF-Track（先前最优端到端方法）, Sparse4D-v3, HSTrack, ADA-Track等。
    *   在验证集和测试集上均进行了对比。

### 4. 资源与算力

*   **硬件**：所有实验均在**8块 NVIDIA A100-80GB GPU**上进行。
*   **训练时长与配置**：
    *   **预训练**：首先在单帧检测任务上进行预训练，小分辨率（800x320）训练12个周期，全分辨率（1600x640）训练24个周期。
    *   **跟踪训练**：在连续3帧的序列数据上进行跟踪器训练，小分辨率额外训练12个周期，全分辨率额外训练24个周期。
*   **其他细节**：采用AdamW优化器，初始学习率0.01，余弦权重衰减设为0.001。推断速度FPS在单块A100上约为7.5。

### 5. 实验数量与充分性

*   **实验充分性评估**：实验设计较为充分和客观。
    *   **主实验**：包含验证集和测试集上的全面SOTA对比，结果详实。
    *   **消融实验**：详细验证了三个核心模块的有效性，并对其关键超参数（如HQD中的IoU阈值、PQI中的特征步长）进行了深入分析。
    *   **鲁棒性分析**：专门分析了模型在不同遮挡程度、目标大小和距离等复杂场景下的性能，证明了方法的针对性改进。
    *   **通用性验证**：在不同骨干网络（V2-99, ViT-L）和不同解码器（DETR3D, PETR）上均验证了模型的增益，证明了方法的通用性。
    *   **额外实验**：包括不确定量化分析、检测联合性能评估、推理延迟对比等，从多角度支撑了方法的优越性。

### 6. 论文的主要结论与发现

*   S2-Track通过系统性地改进查询式跟踪框架的三个核心阶段，构建了一个简单而强大的3D MOT跟踪器。
*   所提出的三个模块（2D提示初始化、不确定性感知解码、分层查询降噪）均能有效提升跟踪性能，尤其在困难场景下增益显著。
*   在nuScenes测试集上，S2-Track以**66.3% AMOTA**的分数实现了目前最优性能，**显著超出先前最佳端到端方法8.9% AMOTA**，并取得了榜单第一名。

### 7. 优点

*   **框架清晰，系统性强**：将复杂的端到端跟踪问题分解为清晰的三个阶段，并分别提出针对性改进，思路明确。
*   **方法新颖且有效**：
    *   混合使用2D先验进行3D查询初始化，巧妙结合了2D检测的成熟度与3D跟踪的需求。
    *   首次在3D MOT中引入并建模预测的不确定性，提升了模型在复杂环境下的鲁棒性。
    *   分层降噪策略通过难度分级处理噪声样本，相比于普通降噪策略更为精细高效。
*   **性能表现突出**：在权威基准上取得了巨大的性能提升，具有很强的实践价值。
*   **实验详实充分**：全面的消融、对比与分析实验，验证了方法的有效性、通用性和鲁棒性，结论可靠。

### 8. 不足与局限

*   **计算效率**：虽然性能强大，但相较于前代方法（如PF-Track），S2-Track引入了额外的计算开销，推断速度略有下降（从9.2 FPS降至7.5 FPS），实时性有进一步提升的空间。
*   **模态局限性**：论文中明确提到，目前主要关注图像模态的场景感知，框架虽可扩展到多传感器融合（如激光雷达+相机），但本身并未在多模态融合上进行验证。
*   **复杂性引入**：引入多个辅助任务和模块（2D检测、深度估计、概率注意力、分层降噪），增加了训练和实现的复杂性。
*   **隐私风险**：论文自身声明，研究集中于通用目标跟踪，不涉及特定人类识别，因此目前未见隐私问题，但未来扩展到特定人类识别时需要关注此风险。

（完）
