---
title: "OpenBox: Annotate Any Bounding Boxes in 3D"
title_zh: OpenBox：标注任意三维边界框
authors: "In-Jae Lee, Mungyeom Kim, Kwonyoung Ryu, Pierre Musacchio, Jaesik Park"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=7ieZWCc7rB"
tags: ["query:stage-d-det"]
score: 7.0
evidence: OpenBox利用两阶段管线结合2D基础模型与3D点云进行三维边界框标注，整合多模态线索
tldr: 针对现有无监督标注方法忽略物体物理状态、需多次迭代的问题，OpenBox设计了一个两阶段自动标注流程，利用2D基础模型提取实例级线索并与3D点云关联，通过上下文感知精化生成高质量3D边界框，在开放词汇设定下显著提升了标注效率和检测器训练性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-7iezwcc7rb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 801, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7iezwcc7rb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7iezwcc7rb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1430, \"height\": 646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7iezwcc7rb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1417, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7iezwcc7rb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1429, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7iezwcc7rb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 575, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7iezwcc7rb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7iezwcc7rb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7iezwcc7rb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1158, \"height\": 651, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-7iezwcc7rb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1327, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7iezwcc7rb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1389, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7iezwcc7rb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 832, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7iezwcc7rb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 955, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7iezwcc7rb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 592, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7iezwcc7rb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 567, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7iezwcc7rb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1236, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7iezwcc7rb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1323, \"height\": 498, \"label\": \"Table\"}]"
motivation: 现有无监督3D检测标注方法忽视物体物理状态且需多次迭代，质量欠佳且计算开销大。
method: 提出两阶段自动标注管线，利用2D基础模型提取实例线索，通过上下文精化与三维点云关联生成3D边界框。
result: 实验表明OpenBox在多个数据集上提高了标注质量和效率。
conclusion: OpenBox通过有效地结合2D和3D信息，为开放词汇3D检测提供了高质量的自动标注方法。
---

## Abstract
Unsupervised and open-vocabulary 3D object detection has recently gained attention, particularly in autonomous driving, where reducing annotation costs and recognizing unseen objects are critical for both safety and scalability. However, most existing approaches uniformly annotate 3D bounding boxes, ignore objects’ physical states, and require multiple self-training iterations for annotation refinement, resulting in suboptimal quality and substantial computational overhead. To address these challenges, we propose OpenBox, a two-stage automatic annotation pipeline that leverages a 2D vision foundation model. In the first stage, OpenBox associates instance-level cues from 2D images processed by a vision foundation model with the corresponding 3D point clouds via context-aware refinement. In the
second stage, it categorizes instances by rigidity and motion state, then generates adaptive bounding boxes with class-specific size statistics. As a result, OpenBox produces high-quality 3D bounding box annotations without requiring self-training.
Experiments on the Waymo Open Dataset (WOD), the Lyft Level 5 Perception dataset, and the nuScenes dataset demonstrate improved accuracy and efficiency over baselines.

---

## 论文详细总结（自动生成）

# OpenBox 论文结构化总结

## 1. 论文核心问题与研究动机
- 三维目标检测是自动驾驶、机器人等领域的关键技术，但现有方法依赖大量人工标注，且多局限于闭集类别。
- 无监督与开放词汇三维检测旨在降低标注成本，并拓展至未见过的物体类别，但已有自动标注流水线存在以下痛点：
  - **忽略物体物理状态**：统一生成三维边界框，未区分刚性、动态、可变形物体，导致框的尺寸和朝向不准确。
  - **依赖多次迭代自训练**：通过反复训练检测器来精修标注，计算开销巨大，且质量仍不理想。
- 本文提出 **OpenBox**，目标是利用二维视觉基础模型（如 Grounding DINO、SAM2）作为监督信号，在**无自训练**的条件下自动生成高质量、开放词汇的三维边界框标注。

## 2. 方法论：两阶段自动标注流水线
OpenBox 由两个核心阶段构成，输入仅为同步的相机图像与 LiDAR 点云。

### 2.1 跨模态实例对齐（Cross-modal Instance Alignment）
- **二维实例级信息提取**：用 Grounding DINO 检测二维框和语义类别，再用 SAM2 根据文本提示和二维框生成实例掩膜与跟踪 ID。将 LiDAR 点云投影到图像平面，与掩膜对应，得到初始的 `实例级点云`。
- **自适应腐蚀**：对掩膜边界做自适应侵蚀，消除投影误差带来的边界噪声。
- **上下文感知精炼**（Context-aware Refinement）：
  - 在 LiDAR 点云上去除地面后，用 HDBSCAN 聚类得到空间簇 \(R_k\)。
  - 对每个实例级点云 \(F_i\) 与每个簇 \(R_k\) 计算双向邻近包含比：当 \(R_k\) 中足够多点在 \(F_i\) 的邻域内，且同时 \(F_i\) 中足够多点在 \(R_k\) 邻域内时，将 \(R_k\) 分配给实例 \(i\)，从而滤除背景噪声、补回被遮挡的实例点。
- 通过该阶段得到经过精炼的实例级点云 \(F_{ref}\)。

### 2.2 自适应三维边界框生成（Adaptive 3D Bbox Generation）
- **运动分解**：利用 PP Score 估计各点的动态性，将实例分为三类：
  - 刚性静态（如停放车辆）
  - 刚性动态（如行驶车辆）
  - 可变形（如行人、骑行者）
- **初始边界框**：对所有实例均先用 closeness-to-edge 算法生成紧贴点云的边界框。若框的任一维度小于 ChatGPT 查询的该类典型尺寸的 80%，则触发后续调整。

#### 处理刚性静态实例
- **表面感知去噪**：通过 SDF（符号距离函数）重建网格表面 \(S\)，对每个顶点统计近邻的前景点与背景点数量，保留前景点占优的顶点，形成精炼表面 \(S_{ref}\) 与精炼点云 \(F_{ref}^{S,(2)}\)。
- **边界框精调与选择**：
  - 从 \(S_{ref}\) 提取实例表面 \(S_{ins}\)，计算其法向量与四个正交方向的点积，判断物体哪些侧面被观测到。
  - 若某些侧面不可见，根据类统计先验生成两个候选框（考虑长度方向不确定性）。
  - 将候选框投影至多视角图像，与 Grounding DINO 的二维框计算 IoU，选择 IoU 更高的候选框。

#### 处理刚性动态实例
- **朝向估计**：利用二维跟踪 ID 关联相邻帧，以物体轨迹方向修正初始框的朝向。
- **可见性驱动扩展**：对 X、Y 轴方向的每个面，计算面中心处的 LiDAR 射线方向与面外向法线的点积，仅在点积为负时（表明该面朝向光线，点云可见）按类统计尺寸扩展边界框。

#### 处理可变形实例
- 为避免多帧聚合时的几何失真，直接对单一帧的可见区域使用 closeness-to-edge 算法生成紧致边界框，不采取复杂的几何精修。

整个流程不包含自训练循环，可一次性完成三类实例的自动标注。

## 3. 实验设计
### 3.1 数据集与评估指标
- **Waymo Open Dataset (WOD)**：主要评估车辆、行人、骑行者类别，使用 LEVEL_1 和 LEVEL_2 的 AP\(_{3D}\)（IoU=0.5/0.7 和 IoU=0.3/0.5）。
- **Lyft Level 5 Perception**：类不可知（class-agnostic）评估，AP\(_{BEV}\) 和 AP\(_{3D}\)（IoU=0.25），按距离范围 0–30m, 30–50m, 50–80m 展示。
- **nuScenes**：汽车、行人、骑行者三类，AP\(_{3D}\)（IoU 阈值未明确，沿用 UNION 设置）。

### 3.2 训练与检测器
- 在自动标注的结果上训练检测器：
  - WOD 使用 Voxel R-CNN
  - Lyft 使用 PointRCNN
  - nuScenes 使用 CenterPoint
- 检测器评估均在人工标注验证集上进行（场景一）；Lyft 额外做直接对比自动标注与人工标注的 AP（场景二）。

### 3.3 对比方法
- **WOD**：CPD、MODEST、OYSTER、DBSCAN 等；特别设计了相机视锥区域标注和 360° 覆盖（通过与 CPD 的 CST/CBR 联合训练）两种设置。
- **Lyft**：MODEST-PP、LiSe 等。
- **nuScenes**：UNION。

## 4. 资源与算力
- 训练使用 **8 块 NVIDIA A6000 GPU（48 GB 显存）**，CPU 为 2× AMD EPYC 7763。
- 训练配置详见表 6：Voxel R-CNN（batch size=16，20  epoch）、PointRCNN（batch size=2，60 epoch）、CenterPoint（batch size=32，20 epoch）。
- 论文未报告整个自动标注管线的执行时间或推理开销。

## 5. 实验数量、充分性与公平性
- **主要实验组**：三大数据集共约 **5 组基准对比**（WOD 相机区域、WOD 360° 两种、Lyft、Lyft 直接比较、nuScenes），每组均包含多个距离或类别。
- **消融实验**：在 WOD 车辆类上对点级精炼（Context-aware、Surface-aware）和框级精炼（Visibility-based、3D-2D IoU）分别做了 **两套消融**。
- **定性分析**：多场景可视化，展示与人工标注和 CPD、OYSTER 的对比，以及开放词汇标注能力。
- 实验覆盖全面，对比方法包括纯 LiDAR 和多模态无监督方法，均使用同一检测框架、相同数据和评估协议，公平性较好。但未提供误差棒或多次运行的统计显著性。

## 6. 主要结论与发现
- OpenBox 在不依赖自训练的情况下，生成的自动标注质量显著提升：
  - WOD 车辆 AP\(_{3D}\)@0.5 达 70.49%，远超 CPD 的 30.30%；行人亦有大幅提升。
  - Lyft 上 0–80m AP\(_{3D}\) 达到 43.3%，比 LiSe 的 27.5% 提高 15.8%，远距离（50–80m）优势尤为突出。
  - nuScenes 上三类全面超越 UNION。
- 通过消融实验验证，上下文感知精炼和表面感知去噪对点云质量提升明显；3D-2D IoU 对齐和可见性驱动扩展对框质量有互补贡献。
- 方法可灵活扩展至任意文本描述的新类别（如婴儿车、消防栓），展现开放词汇能力。

## 7. 优点
- **免自训练**：一次性生成高质量标注，大幅降低计算成本。
- **物理状态感知**：首次显式区分刚性与动态、可变形实例，并针对性设计框生成策略，减少框的欠/过拟合。
- **多模态融合深入**：不仅简单拼接二维和三维，而是通过上下文精炼和 SDF 表面过滤深度融合两模态。
- **实验扎实**：覆盖多个主流数据集、多种距离和类别，消融实验支撑各模块有效性，与 SOTA 方法公平比较。
- **开放词汇能力**：仅需文本提示即可扩展至新物体类别，实用性强。

## 8. 不足与局限
- **受二维模型影响**：恶劣天气或低对比度导致二维检测/分割失败，会直接传导至三维标注。
- **可变形物体处理有限**：行人和骑行者因姿势变化难以推断完整尺寸，常回退为固定类统计框，容易过大或过小。
- **远距离性能瓶颈**：点云过于稀疏时，几何约束不足，框拟合病态，定位精度下降。
- **未讨论标注效率**：未给出推理时间或硬件占用，难以评估大规模部署的实时性。
- **缺少误差分析**：实验未提供多次运行的均值和方差，结果的稳健性有待进一步验证。

（完）
