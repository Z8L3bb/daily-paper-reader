---
title: "One for All: Multi-Domain Joint Training for Point Cloud Based 3D Object Detection"
title_zh: 一以贯之：面向点云三维物体检测的多域联合训练
authors: "Zhenyu Wang, Ya-Li Li, Hengshuang Zhao, Shengjin Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=ndoeHX1Acq"
tags: ["query:stage-d-det"]
score: 8.0
evidence: 跨域点云三维物体检测
tldr: 点云三维物体检测面临多域数据联合训练时严重的域干扰问题。OneDet3D提出域感知划分技术，在散射和聚集操作中嵌入域特异性处理，使得单一参数模型能同时应对室内外多种场景的点云检测。实验证明，该模型在多个基准数据集上取得与专用模型相当甚至更优的性能，为通用三维检测迈出重要一步。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-ndoehx1acq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ndoehx1acq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 821, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ndoehx1acq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ndoehx1acq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ndoehx1acq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1430, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ndoehx1acq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1426, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ndoehx1acq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ndoehx1acq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1462, \"height\": 470, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-ndoehx1acq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ndoehx1acq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1330, \"height\": 710, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ndoehx1acq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1337, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ndoehx1acq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 730, \"height\": 442, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ndoehx1acq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 691, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ndoehx1acq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1298, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ndoehx1acq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 725, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ndoehx1acq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1345, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ndoehx1acq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ndoehx1acq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1200, \"height\": 248, \"label\": \"Table\"}]"
motivation: 点云三维检测的多域联合训练因域差异大而相互干扰。
method: 设计OneDet3D，通过域感知划分在散射和聚集阶段实现域特定处理。
result: 在室内外多个数据集上，统一模型达到与专用模型相近的性能。
conclusion: OneDet3D验证了单模型多域点云检测的可行性，提升模型泛化性。
---

## Abstract
The current trend in computer vision is to utilize one universal model to address all various tasks. Achieving such a universal model inevitably requires incorporating multi-domain data for joint training to learn across multiple problem scenarios. In point cloud based 3D object detection, however, such multi-domain joint training is highly challenging, because large domain gaps among point clouds from different datasets lead to the severe domain-interference problem. In this paper, we propose OneDet3D, a universal one-for-all model that addresses 3D detection across different domains, including diverse indoor and outdoor scenes, within the same framework and only one set of parameters. We propose the domain-aware partitioning in scatter and context, guided by a routing mechanism, to address the data interference issue, and further incorporate the text modality for a language-guided classification to unify the multi-dataset label spaces and mitigate the category interference issue. The fully sparse structure and anchor-free head further accommodate point clouds with significant scale disparities. Extensive experiments demonstrate the strong universal ability of OneDet3D to utilize only one trained model for addressing almost all 3D object detection tasks (Fig. 1). We will open-source the code for future research and applications.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义

- **研究动机**：当前 3D 点云目标检测普遍采用“单数据集训练-测试”范式，模型无法泛化到不同域（室内/室外）的数据，严重限制了通用 3D 检测的发展。二维视觉中已有成熟的联合多数据集训练方案，但三维检测面临巨大的域差异（点云范围、稀疏度、物体尺度等）导致严重的域干扰问题。
- **核心问题**：如何在单一模型和单一参数集下，实现多域（室内与室外、不同传感器）点云数据的联合训练，使一个模型同时适配多个 3D 检测任务。
- **整体含义**：提出“一以贯之”的通用 3D 检测器 OneDet3D，首次实现用一个模型处理几乎所有室内外点云的 3D 目标检测，为 3D 基础模型提供可行路径。

## 方法论

- **全稀疏骨干与无锚检测头**：
  - 采用 3D 稀疏卷积提取体素特征，避免点云采样和分组对域差异的敏感性，无需固定尺寸的稠密特征图。
  - 使用无锚检测头（基于中心点表示），直接利用稀疏卷积后的点进行预测，适应不同尺度的点云，并保留所有点直到最后阶段，避免因点云变化需要不同剪枝策略的问题。

- **域感知划分（Domain-aware Partitioning）**，用于缓解数据级干扰：
  - **域路由器（Domain Router）**：一个小型 3D 稀疏卷积分类器，以场景全局平均池化特征预测输入点云的域标签概率 `p(n)_d`，为不可见域提供路由依据。
  - **散射划分（Scatter Partitioning）**：在归一化层中为每个域学习独立的缩放 `γ(n)` 和偏移 `β(n)`，并根据域路由器输出的概率对它们加权，输出为 `x = Σ p(n)_d * [(x - E)/√(Var + ε) * γ(n) + β(n)]`。仅引入极少的域特定参数，绝大部分卷积层共享。
  - **上下文划分（Context Partitioning）**：针对室内域单独学习全局上下文信息。对每个块的输出特征 `f` 进行全局平均池化，再用域特定的稀疏卷积处理，仅对室内域加权：`f̂ = f + Σ(i∈indoor) p(i)_d * conv(i)(GAP(f))`。室外点云不引入上下文学习，避免背景干扰。

- **语言引导分类（Language-guided Classification）**，用于缓解类别级干扰：
  - 利用 CLIP 的文本嵌入作为分类层的权重（冻结），统一不同数据集的标签空间，缓解标签冲突。
  - 由于冻结的全连接层会阻碍梯度回传，额外引入类别无关的二分类分支（物体/背景），由 3D 稀疏卷积实现，在所有数据集上共享。最终的分类概率为两个分支的乘积。该共享分支也促进学习通用的类别知识。
  - 可轻松扩展至开放词汇设定，结合预训练的 2D 开放词汇检测器生成伪标签进行多域联合训练，提升对新类别的泛化能力。

- **损失函数设计**：
  - 分类损失使用软目标 focal loss，以 BEV-IoU（俯视图下 2D IoU）作为软目标，忽略高度方向的位置信息以降低优化难度：`Lcls = -α̂_t * |c·IoU_BEV - p̂|^ξ * log(|1 - c - p̂|)`。
  - 回归损失使用 3D IoU 损失。
  - 中心度和 IoU 预测分支均使用二元交叉熵损失，其中 IoU 预测分支以常规 3D IoU 作为监督。
  - 采用数据集感知采样策略（先采样数据集再随机采样样本）平衡不同尺度数据集的影响。

## 实验设计

- **使用数据集**：SUN RGB-D、ScanNet（室内）；KITTI、nuScenes（室外）；S3DIS、Waymo 作为跨域评估的未见过数据集。
- **Benchmark 设置**：
  - 闭词设定（多数据集联合训练并测试同一模型）：对 SUN RGB-D 10 类、ScanNet 18 类、KITTI “car”、nuScenes “car” 进行检测，以对应的 AP 指标评估。
  - 开放词汇设定：重新划分 SUN RGB-D 和 ScanNet 的基类/新类，基类为各数据集前十类取并集，其余为新类；训练时只提供基类标注。
  - 跨域评价：在未见过的 S3DIS（室内）和 Waymo（室外）上测试，观察泛化能力。
- **对比方法**：
  - 室内检测器：VoteNet, H3DNet, GroupFree, FCAF3D, CenterPoint (仅限单数据集对比) 等。
  - 室外检测器：SECOND, PointPillar, PointRCNN, Part-A2, PV-RCNN, VoxelNeXt, UVTR 等。
  - 部分近期多数据集方法：Uni3D, VoxelNeXt, FSD v2, SAFDNet (大多只能处理单一类型场景)。
  - 开放词汇对比：Det-PointCLIP, Det-PointCLIPv2, 3D-CLIP, CoDA。

## 资源与算力

- 文中未明确提及 GPU 型号、数量或具体训练时间。仅说明实现基于 MMDetection3D，使用 AdamW 优化器训练 20 个 epoch，初始学习率 0.0001 采用循环调整。

## 实验数量与充分性

- **主要实验**：
  - 闭词四数据集联合训练与测试，与十余个现有方法对比（表 2、表 3）。
  - 开放词汇联合训练，与四个现有开放词汇 3D 检测方法对比（表 4）。
  - 跨域评价（S3DIS 和 Waymo），对比多种室内/室外检测器及不同训练数据组合的表现（表 5、表 6）。
  - 消融实验：逐步添加散射划分、上下文划分、语言引导分类，验证各模块作用（表 7）。
  - 更多消融：上下文划分仅作用于室内/室外的影响（表 8）；分类方式对比（纯稀疏卷积、纯冻结 CLIP、可训练 CLIP、混合方法）（表 9）；分类损失函数选择（表 10）。
  - 可视化结果展示在多个数据集上的检测效果。
- **实验充分性与公平性**：所有对比方法均在同一硬件环境下复现（除原文仅献单数据集结果的方法外），使用统一的数据预处理和评估协议。消融实验设计具有递进性，验证了各模块的必要性和协同作用。开放词汇设定也完全遵循 CoDA 的划分，保证了公平比较。

## 主要结论与发现

- OneDet3D 是首个在单一参数集和同一架构下，同时处理室内和室外多域点云 3D 检测的通用模型。
- 在全稀疏结构和无锚头的基础上，域感知划分有效缓解了数据级干扰；语言引导分类解决了类别级冲突，且通过共享类别无关分支降低了优化难度。
- 闭词设定下，联合训练后的 OneDet3D 在 SUN RGB-D 上 AP₂₅ 达 65.0% (超 FCAF3D 1.2%)，在 KITTI 上 AP_m 达 84.2% (优于 PV-RCNN)，在 nuScenes 上 AP 达 81.0%。联合训练带来的性能普遍超过单数据集训练基线。
- 开放词汇设定下，相比 CoDA，在 SUN RGB-D 上新类 AP 提升超过 5%，在 ScanNet 上提升超过 9%。
- 跨域实验中，多数据集联合训练能大幅提升对未见域（S3DIS、Waymo）的泛化能力，说明模型学习了域无关的通用三维知识。

## 优点

- **首创性**：首次实现单一模型同时适用于室内外多域点云的 3D 检测，突破传统单域限制。
- **结构简单有效**：全稀疏骨干+无锚头避免了对固定尺寸特征图的依赖，天然适合多域训练。
- **域感知划分设计精巧**：仅引入极少域特定参数（归一化层的缩放/偏移和室内上下文模块），通过域路由器动态加权，开销小但缓解数据干扰效果显著。
- **语言引导分类**：巧妙结合 CLIP 文本嵌入与类别无关卷积分支，既解决了标签冲突，又克服了冻结全连接层阻断梯度的问题，且自然支持开放词汇。
- **实验全面扎实**：涵盖闭词、开放词汇、跨域等多个设定，与广泛基线对比，并对各组件进行了详细消融。

## 不足与局限

- **依赖全监督标注**：当前模型要求每个训练数据集都具有完整的 3D 框和类别标注，未探索弱监督或无标注数据的使用。
- **算力细节缺失**：未提供训练消耗的 GPU 数量及具体时长，难以直接评估训练成本。
- **数据集采样策略仍显简单**：尽管采用了先采样数据集再采样本的策略，但不同数据集间样本不平衡的影响未深入分析。
- **未来扩展**：作者仅提及可能整合弱标注数据，但未给出具体方案；开放词汇扩展依赖 2D 预训练模型生成伪标签，可能引入 2D-3D 不对齐误差。
- **潜在社会风险**：多源点云数据的收集与使用可能涉及隐私问题，论文仅作简要声明。

（完）
