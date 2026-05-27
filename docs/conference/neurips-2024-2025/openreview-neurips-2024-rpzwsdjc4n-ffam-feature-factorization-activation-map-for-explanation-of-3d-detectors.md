---
title: "FFAM: Feature Factorization Activation Map for Explanation of 3D Detectors"
title_zh: FFAM：用于三维检测器解释的特征分解激活图
authors: "Shuai Liu, Boyang Li, Zhiyu Fang, Mingyue Cui, Kai Huang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=rpZWSDjc4N"
tags: ["query:lidar-d-det"]
score: 6.0
evidence: 基于LiDAR的三维检测器可解释性
tldr: 现有LiDAR三维物体检测器多为黑箱，缺乏可解释性。FFAM利用非负矩阵分解生成概念激活图，并通过目标特征梯度优化视觉解释，同时引入体素上采样策略。实验表明，FFAM能产生高质量的视觉解释，有助于理解三维检测器的决策行为，促进检测模型的可信部署。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-rpzwsdjc4n/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rpzwsdjc4n/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1304, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rpzwsdjc4n/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 1281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rpzwsdjc4n/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rpzwsdjc4n/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 716, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rpzwsdjc4n/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1172, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rpzwsdjc4n/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1460, \"height\": 904, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-rpzwsdjc4n/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1307, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rpzwsdjc4n/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 655, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rpzwsdjc4n/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1327, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rpzwsdjc4n/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 832, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rpzwsdjc4n/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 896, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rpzwsdjc4n/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 798, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rpzwsdjc4n/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1386, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rpzwsdjc4n/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1302, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rpzwsdjc4n/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 762, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rpzwsdjc4n/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 977, \"height\": 180, \"label\": \"Table\"}]"
motivation: LiDAR三维检测器黑箱特性限制其应用中的信任。
method: FFAM使用非负矩阵分解生成激活图，并用目标梯度精炼。
result: 提供高质量对象级视觉解释，揭示检测器关注区域。
conclusion: FFAM为三维检测器提供了有效的解释手段，提升模型透明度。
---

## Abstract
LiDAR-based 3D object detection has made impressive progress recently, yet most existing models are black-box, lacking interpretability. Previous explanation approaches primarily focus on analyzing image-based models and are not readily applicable to LiDAR-based 3D detectors. In this paper, we propose a feature factorization activation map (FFAM) to generate high-quality visual explanations for 3D detectors. FFAM employs non-negative matrix factorization to generate concept activation maps and subsequently aggregates these maps to obtain a global visual explanation. To achieve object-specific visual explanations, we refine the global visual explanation using the feature gradient of a target object. Additionally, we introduce a voxel upsampling strategy to align the scale between the activation map and input point cloud. We qualitatively and quantitatively analyze FFAM with multiple detectors on several datasets. Experimental results validate the high-quality visual explanations produced by FFAM. The code is available at \url{https://anonymous.4open.science/r/FFAM-B9AF}.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **核心问题**：当前基于LiDAR的3D目标检测模型（如SECOND、CenterPoint）大多为“黑箱”系统，缺乏可解释性，用户难以理解模型为何做出某个检测决策，这在自动驾驶等高风险领域尤为关键。
- **现有方法的不足**：已有的视觉解释方法（如Grad-CAM、D-RISE）主要面向2D图像模型，直接应用于点云时会遇到三个挑战：
  - 点云本质是3D的，需生成三维显著性图；
  - 需提供针对**单个检测目标**的对象级解释，而非类别级；
  - 点云稀疏、分布不均，传统线性插值上采样失效。
- **整体含义**：提出FFAM（特征分解激活图）方法，为LiDAR 3D检测器生成高质量、对象级的视觉解释，从而揭示模型决策依据，增强模型可信度。

## 2. 论文提出的方法论

FFAM的整体流程分为三个阶段，融合了非负矩阵分解（NMF）、梯度加权和定制化体素上采样。

- **特征分解激活图（Sec 3.1）**
  - 从3D骨干网络提取体素特征图 \(F \in \mathbb{R}^{M \times d}\)，利用NMF将其分解为概念向量矩阵和权重矩阵：\(F_i \approx \sum_{j=1}^r H_{ij} W_j\)，其中 \(r\) 为预设概念数量（设为64）。
  - 聚合概念权重得到全局概念激活图 \(V = \sum_{j=1}^r H_{\cdot j}\)，该图突出包含丰富语义信息（如车轮、车顶）的体素。

- **对象特异性梯度加权（Sec 3.2）**
  - 为获得针对某一检测框 \(d\) 的解释，定义一个基准检测 \(d^b\)（置零），计算损失 \(\ell = \|d - d^b\|_1\)，并求特征图梯度 \(G = \partial \ell / \partial F\)。
  - 利用梯度绝对值之和得到通道权重 \(\omega = \sum_{k=1}^d |G_{\cdot k}|\)，归一化后与全局概念激活图逐元素相乘，得到对象特异性激活图 \(M = \Phi(\omega) \odot \Phi(V)\)。
  - 通过修改损失中的特定属性（如长宽高），可以分析模型预测该属性时关注的区域。

- **体素上采样策略（Sec 3.3）**
  - 为解决3D稀疏体素上采样问题，对于输入点云中的每个点，计算其所属体素坐标，并在激活图 \(M\) 上以曼哈顿距离查找最多 \(k\) 个近邻体素（距离阈值设为2，\(k=16\)）。
  - 使用高斯核对邻居值加权平均，得到该点的显著性分数，从而将粗粒度激活图映射回原始点云尺度。

## 3. 实验设计

- **数据集与检测器**：
  - **KITTI** 数据集：使用 **SECOND** 作为基线检测器（训练后用于解释）。
  - **Waymo Open** 数据集：使用 **CenterPoint** 作为检测器。
- **对比方法**：
  - 图像领域方法：**Grad-CAM**、**ODAM**。
  - 点云领域方法：**OccAM**（当前SOTA，基于扰动）。
- **评价指标**：
  - **Deletion & Insertion**：通过逐步移除/插入高显著性点，观察预测与真值的IoU变化曲线下面积（AUC）。
  - **Visual Explanation Accuracy (VEA)**：计算不同阈值下显著性图与真值mask的点级IoU。
  - **Pointing Game (PG) 与 energy-based PG (enPG)**：评估最高显著性点是否落入真值框内及框内能量占比。
  - 实验对象限定在“良好检测”（IoU大于相应类别阈值的预测框）。

## 4. 资源与算力

- 文中明确提到实验基于 **PyTorch** 框架，使用 **单张RTX 3090 GPU** 运行。未提及训练时长、显存占用量及GPU数量等详细算力开销。

## 5. 实验数量与充分性

实验设计较为全面，覆盖了定性与定量、多数据集、多指标、消融与超参数分析等多个维度：

- **定性比较**：在KITTI和Waymo上可视化了FFAM与OccAM的显著性图，并生成了不同类别的平均显著性图以探究检测模式。
- **定量比较**：在KITTI上使用SECOND，报告了所有对比方法在三个类别上的Deletion & Insertion AUC、VEA、PG、enPG共四个指标（总计4张主表格）。在Waymo上使用CenterPoint进行了相同的定量评估（附录表7-9）。
- **消融实验**：逐一移除特征分解、体素上采样、对象梯度三个组件，验证各模块的贡献（附录表10）。
- **超参数分析**：探究了特征图层位置（4个block）、体素上采样搜索范围与邻居数（4组）、概念数目 \(r\)（5个值）对性能的影响（附录表4-6）。
- **额外分析**：分析了真实正例与假正例的平均显著性图差异，揭示了噪声和点密度可能是导致假正例的因素。
- **评估公平性**：所有对比方法均基于官方实现或原文设定，评价指标与处理流程（如仅在目标周围局部区域操作）遵循了先前工作的标准，确保了比较的公平性。

## 6. 论文的主要结论与发现

- FFAM能够**高效地生成高质量、对象特定的3D显著性图**，在定性和定量上均显著优于OccAM、Grad-CAM、ODAM。
- 通过平均显著性图发现，检测器常基于固有几何先验进行预测，例如：
  - 汽车主要依靠四个角点（受LiDAR扫描特性影响），高度则依赖车顶点。
  - 行人依靠头肩区域，骑行者依靠头和背部。
- FFAM可辅助分析**假正例模式**：假正例的平均显著性图与真正例相似，但其周围噪声点更多、点密度更低，暗示了假正例的成因。
- 该方法适用于一阶段与二阶段检测器，通用性强。

## 7. 优点

- **方法创新**：首次将NMF引入点云检测器解释，巧妙地通过概念聚合生成全局解释，并结合梯度实现对象级聚焦，完全适配3D稀疏结构。
- **解决痛点**：专门设计的体素上采样策略有效解决了点云稀疏性带来的尺度对齐问题。
- **解释粒度精细**：不仅能解释整个检测框，还能针对位置、尺寸、朝向等单一属性进行解释，为模型诊断提供了有力工具。
- **评估全面**：结合了多种主流评价指标，并在两个大规模自动驾驶数据集、两种主流检测器上进行了验证，说服力强。
- **代码开源**：提供了可复现的代码，增强了研究的透明度和实用性。

## 8. 不足与局限

- **白盒依赖**：方法需要访问3D检测器内部的特征图和梯度，无法直接应用于纯黑盒模型。
- **超参数敏感性**：NMF的概念数量 \(r\)、体素上采样近邻参数等需手动调整，尽管文中进行了分析，但在新模型或新数据上可能需要重新调优。
- **评估偏差风险**：定量实验仅针对“良好检测”的目标，未涵盖模型漏检或低质量预测的解释评估，可能高估方法的实际表现。
- **数据集与模型覆盖**：主要在KITTI和Waymo两个数据集上测试，检测器限于SECOND和CenterPoint，对于最新的Transformer架构或全稀疏检测器的泛化性尚未验证。
- **计算效率未详述**：虽然指出比基于扰动的OccAM高效，但未提供生成单个显著性图的具体耗时对比数据。

（完）
