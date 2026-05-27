---
title: "Point4Bit: Post Training 4-bit Quantization for Point Cloud 3D Detection"
title_zh: "Point4Bit: 面向点云3D检测的后训练4位量化"
authors: "Jianyu Wang, Yu Wang, Shengjie Zhao, Sifan Zhou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=sj5wiTCtu6"
tags: ["query:stage-d-det"]
score: 7.0
evidence: 首个面向体素化3D点云目标检测的4位后训练量化框架
tldr: 体素化3D目标检测器性能出色但计算量大，现有后训练量化方法局限于8位，限制了边缘部署。本文提出Point4Bit，首个通用4位后训练量化框架，通过前景感知分段激活量化和权重补偿等技术克服低位量化挑战。实验表明该方法在显著压缩模型的同时保持检测精度，推动点云3D检测在资源受限设备上的应用。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sj5witctu6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1180, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sj5witctu6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1029, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sj5witctu6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1171, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sj5witctu6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 2077, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sj5witctu6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 1580, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1456, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 734, \"height\": 91, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 742, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 537, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 540, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 534, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 747, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 730, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 748, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sj5witctu6/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 982, \"height\": 325, \"label\": \"Table\"}]"
motivation: 3D检测模型高计算与内存需求阻碍边缘部署，现有量化仅支持8位。
method: 提出4位后训练量化框架Point4Bit，包含前景感知分段激活量化等关键技术。
result: 在多个3D检测模型上实现4位量化，精度损失极小。
conclusion: 4位量化有效平衡了3D检测性能与效率，拓宽了边缘部署场景。
---

## Abstract
Voxel-based 3D object detectors have achieved remarkable performance in point cloud perception, yet their high computational and memory demands pose significant challenges for deployment on resource-constrained edge devices. Post-training quantization (PTQ) provides a practical means to compress models and accelerate inference; however, existing PTQ methods for point cloud detection are typically limited to INT8 and lack support for lower-bit formats such as INT4, which restricts their deployment potential. In this paper, we present Point4bit, the first general 4-bit PTQ framework tailored for voxel-based 3D object detectors. To tackle challenges in low-bit quantization, we propose two key techniques: (1) Foreground-aware Piecewise Activation Quantization (FA-PAQ), which leverages foreground structural cues to improve the quantization of sparse activations; and (2) Gradient-guided Key Weight Quantization (G-KWQ), which preserves task-critical weights through gradient-based analysis to reduce quantization-induced degradation. Extensive experiments demonstrate that Point4bit achieves INT4 quantization with minimal accuracy loss with less than 1.5\% accuracy drop. Moreover, we validate its generalization ability on point cloud classification and segmentation tasks, demonstrating broad applicability. Our method further advances the bit-width limitation of point cloud quantization to 4 bits, demonstrating strong potential for efficient deployment on resource-constrained edge devices.

---

## 论文详细总结（自动生成）

# Point4Bit 论文结构化总结

## 1. 论文的核心问题与整体含义
- **研究背景**：体素化 3D 目标检测器（如 CenterPoint、VoxelNeXt）在点云感知中性能出色，但计算与内存开销极大，难以部署于边缘设备（如自动驾驶车载平台）。
- **现有方法局限**：后训练量化（PTQ）是轻量级压缩加速手段，但已有的点云 PTQ 方法（如 LiDAR-PTQ）仅支持 INT8，在更低比特（INT4）下会导致严重精度崩溃，且优化速度慢、泛化性不足。
- **核心问题**：如何在无需重训练、无标签数据的前提下，将 3D 检测器成功量化至 4 比特（W4A4 或 W4A8），并保持检测性能。
- **整体含义**：提出首个通用 4-bit PTQ 框架 Point4Bit，通过前景感知与梯度引导等策略突破低比特量化瓶颈，提升点云感知模型在资源受限边缘场景的部署潜力。

## 2. 方法论：核心思想与关键技术
### 2.1 总体框架
Point4Bit 包含两个核心组件：**前景感知分段激活量化（FA-PAQ）**和**梯度引导关键权重量化（G-KWQ）**，均属于 PTQ 范畴，仅需少量无标签校准数据。

### 2.2 FA-PAQ：前景感知分段激活量化
- **动机**：点云稀疏激活中前景区域（物体框内）的激活幅值较强，对检测任务至关重要，常规均匀量化容易丢失关键信息。
- **步骤**：
  1. **自适应前景识别**：对每层 BEV 特征图的非空体素，按通道平均激活值排序，选取 Top-K（比例 m₁）作为前景候选。
  2. **基于 CDF 的分段区间划分**：统计前景特征的经验累积分布函数 FX(x)，按等概率（1/m）选取边界，将值域分为 m 个区间，使密集区域获得更细量化粒度。
  3. **分段量化**：对每个区间独立计算量化 scale（sf_gk），按区间进行仿射量化；背景区域沿用常规量化。

### 2.3 G-KWQ：梯度引导关键权重量化
- **动机**：低比特下量化误差主要由舍入误差放大，对几何结构敏感的任务，部分权重对损失影响更大，需要重点保护。
- **步骤**：
  1. **梯度敏感性评分**：在校准集上进行一次前向+反向，计算每个输出通道对任务总损失的平均梯度幅度 αℓⱼ。
  2. **关键通道选择**：按 α 排序，选取前 m₂% 的通道作为任务关键权重。
  3. **差异化量化优化**：在 MSE 校准损失中加入通道加权舍入误差惩罚项 λ·αⱼ·L_RE,ⱼ，通过网格搜索优化量化参数，强制关键权重保持高保真度。

### 2.4 整体算法流程
- 遍历所有层，先基于校准数据计算各通道梯度敏感性，并优化权重量化参数；再逐层提取特征、识别前景/背景，分别优化背景量化参数，并利用 CDF 与等概率划分确定前景分段量化 scale。

## 3. 实验设计
### 3.1 数据集与场景
- **3D 检测**：nuScenes（val set），评估指标 mAP、NDS。
- **3D 分类**：ModelNet40、ScanObjectNN，评估 OA 和 mAcc。
- **3D 语义分割**：SemanticKITTI，评估 mIoU。

### 3.2 基准模型与对比方法
- **检测模型**：CP-Voxel、VoxelNeXt、PillarNeXt（覆盖体素、稀疏体素、柱体架构）。
- **对比方法**：RTN、RTN+GS、PD-Quant、QDrop、LiDAR-PTQ，涵盖多种后训练量化策略。

### 3.3 实验设置
- 校准集极小（nuScenes 取 256 帧，占训练集 0.91%；其他任务类似）。
- 保留首尾层为 FP，其余层应用层粒度量化。
- 位宽配置：W8A8、W4A8、W4A4，并探索 W3A3；超参数 m₁、m₂、m 经消融选定。

## 4. 资源与算力
- 所有实验在**单块 NVIDIA Tesla V100 GPU** 上完成。
- 量化部署时间对比（Tab.6）：Point4Bit 约 39.1 分钟，远快于 PD-Quant（650 min）和 LiDAR-PTQ（224 min），与 RTN+GS（38.4 min）相当，但精度大幅领先。
- 推理速度测试：在 Jetson AGX Orin 上 W8A8 的 CP-Voxel 实现 31.1 FPS（FP 为 12.5 FPS），在 Xavier NX 上达到 5.2 FPS（FP 1.9 FPS）。
- 文中未提供 4-bit 推理的实际硬件加速数据（原因是硬件/框架支持尚不成熟）。

## 5. 实验数量与充分性
### 5.1 实验数量
- **主实验**：3 种检测模型 × 多种位宽配置（共约 9 组表格）；2 个分类模型 × 2 个数据集 × 多位宽；1 个分割模型 × 多位宽。
- **消融实验**：组件耦合、位宽影响（含 W3A3）、校准集大小、Top-K 选择比例 m₁、量化区间数 m、关键权重比例 m₂、区间划分策略（CDF vs. 均匀）。
- **附加分析**：量化部署时间对比、推理速度实测、可视化结果、CDF 划分误差的理论证明。

### 5.2 充分性与公正性
- 覆盖多个模型架构、多位宽、多任务，且对比了多种近期 PTQ 方法，均使用统一校准协议。
- 超参数通过消融探究了合理范围，实验设置透明，可复现性高（论文提供了详细的实现细节）。
- 基线方法均采用原文默认配置，对比较为公平。

## 6. 主要结论与发现
- Point4Bit 在 W4A4 设置下，CP-Voxel 仅损失 1.48% mAP，VoxelNeXt 损失 1.56%，PillarNeXt 损失 1.62%，大幅优于现有 PTQ 方法（多数在 10% 以上崩溃）。
- 在分类、分割任务上也表现出强泛化性，4-bit 精度接近全精度模型。
- FA-PAQ 和 G-KWQ 两个模块相互补充，共同提升低比特鲁棒性（消融表明 FA-PAQ 对性能增益贡献更大）。
- 方法对校准集大小不敏感，仅需极少量样本（0.91% 训练数据）即可稳定工作。
- 量化部署速度快（约 39 分钟），且 W8A8 在边缘硬件上实现约 3× 加速，证实实用潜力。

## 7. 优点
- **首次实现点云 3D 检测的通用 4 比特 PTQ**，突破现有方法只能到 8 比特的限制。
- **技术新颖且针对性强**：利用点云稀疏性和前景先验设计激活量化，利用梯度信息指导权重量化，有效缓解低比特量化误差。
- **部署友好**：无需标注数据、无需重训练、量化时间短，且支持混合精度（W4A8）与 NVIDIA 最新硬件格式对齐。
- **评估全面**：涵盖检测、分类、分割三大任务，模型种类丰富，消融细致，理论证明与可视化支撑完备。
- **推理加速验证**：在真实边缘设备上展示了实速提升，具有工程参考价值。

## 8. 不足与局限
- **更低比特（2-bit、二值）未探索**，模型信息损失和硬件支持仍是挑战。
- **4-bit 真实部署受限**：目前依赖稀疏卷积框架（如 spconv）的 4-bit 推理生态不成熟，论文中未报告 W4A4 在边缘设备上的实际加速效果，仅停留在学术探索层面。
- **校准数据影响**：虽对数量不敏感，但校准数据分布可能对域漂移场景（如不同天气、传感器）有潜在影响，未进行跨域验证。
- **方法超参数需手动调优**：如 m₁、m₂、m 等需根据模型和位宽调整，自动化选择机制缺失。
- **仅限于仿射量化**：未涉及非均匀量化或更复杂的量化方案，理论误差分析也基于均匀量化假设。

（完）
