---
title: Towards 3D Objectness Learning in an Open World
title_zh: 走向开放世界中的三维物体性学习
authors: "Taichi Liu, Zhenyu Wang, Ruofeng Liu, Guang Wang, Desheng Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=wEOmS8Aw1W"
tags: ["query:stage-d-det"]
score: 6.0
evidence: 无需文本提示、与类别无关的开放世界三维物体检测，直接从点云学习
tldr: 提出OP3Det，一种与类别无关的开放世界三维检测器，无需文本提示即可在三维场景中发现所有物体。该方法旨在解决现有检测器无法泛化到新类别的问题。虽非针对LiDAR或两阶段设计，但为三维开放世界检测提供了可行思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-weoms8aw1w/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1420, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-weoms8aw1w/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1420, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-weoms8aw1w/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1431, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-weoms8aw1w/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-weoms8aw1w/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1437, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-weoms8aw1w/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1391, \"height\": 1255, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-weoms8aw1w/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 545, \"height\": 496, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-weoms8aw1w/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1304, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-weoms8aw1w/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1157, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-weoms8aw1w/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1084, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-weoms8aw1w/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1159, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-weoms8aw1w/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-weoms8aw1w/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 868, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-weoms8aw1w/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1430, \"height\": 868, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-weoms8aw1w/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 800, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-weoms8aw1w/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1081, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-weoms8aw1w/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 720, \"height\": 442, \"label\": \"Table\"}]"
motivation: 现有三维检测器难以泛化到开放世界，未见类别检测能力不足。
method: 提出与类别无关的开放世界提示无关三维检测器，通过强基线实现通用物体发现。
result: 能够检测任意物体，包括训练时未见过的类别。
conclusion: 为开放世界三维检测设立了新范式，推动三维感知向更通用性发展。
---

## Abstract
Recent advancements in 3D object detection and novel category detection have made significant progress, yet research on learning generalized 3D objectness remains insufficient. In this paper, we delve into learning open-world 3D objectness, which focuses on detecting all objects in a 3D scene, including novel objects unseen during training. Traditional closed-set 3D detectors struggle to generalize to open-world scenarios, while directly incorporating 3D open-vocabulary models for open-world ability struggles with vocabulary expansion and semantic overlap. To achieve generalized 3D object discovery, We propose OP3Det, a class-agnostic Open-World Prompt-free 3D Detector to detect any objects within 3D scenes without relying on hand-crafted text prompts. We introduce the strong generalization and zero-shot capabilities of 2D foundation models, utilizing both 2D semantic priors and 3D geometric priors for class-agnostic proposals to broaden 3D object discovery. Then, by integrating complementary information from point cloud and RGB image in the cross-modal mixture of experts, OP3Det dynamically routes uni-modal and multi-modal features to learn generalized 3D objectness. Extensive experiments demonstrate the extraordinary performance of OP3Det, which significantly surpasses existing open-world 3D detectors by up to 16.0% in AR and achieves a 13.5% improvement compared to closed-world 3D detectors.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：现有的 3D 目标检测方法大多基于封闭世界假设，只能识别预定义类别，难以泛化到开放世界中从未训练过的新类别。部分开放词汇 3D 检测器虽然能识别新类别，但仍然依赖手工设计的文本提示，存在词汇扩展困难和语义重叠等问题，无法真正学习“物体性”（objectness）。
- **核心目标**：本文旨在从类别无关（class‑agnostic）的角度学习**开放世界 3D 物体性**，即让模型能够直接根据点云和图像的几何与视觉线索，发现并定位 3D 场景中的所有物体实例，而不依赖任何语义类别标签或文本提示。
- **整体含义**：这项工作首次明确定义并解决类别无关的开放世界 3D 目标检测问题，期望为开放环境下的机器人、自动驾驶等场景中的通用 3D 感知提供新的范式。

### 2. 方法论

#### 2.1 整体框架：OP3Det

OP3Det 是一个**类别无关、开放世界、无提示（Prompt‑free）** 的多模态 3D 检测器。其训练与推理流程分为两个关键阶段：

- **3D 物体发现（3D Object Discovery）**：在训练前，利用 2D 基础模型和大规模 2D 知识发现更多潜在 3D 物体，扩充训练监督信号。
- **跨模态混合专家（Cross‑Modal MoE）**：在训练阶段，通过动态路由机制融合点云的几何特征与图像的语义特征，学习泛化性更强的 3D 物体性。

#### 2.2 3D 物体发现：多尺度点采样策略

- **基础操作**：给定 RGB 图像 \(X_I\)，使用 Segment Anything Model（SAM）进行类别无关分割，获得大量掩码。但 SAM 会产生碎片化和不完整的物体掩码，引入噪声。
- **多尺度点采样**：
  1. 利用自监督模型（如 DINO）的注意力图和 SAM 的 IoU 分数，为每个采样点分配“物体先验分数”。
  2. 在 3D 空间中，以当前最高先验分数的点作为源点，计算其余 3D 点与源点的空间距离，保留距离小于阈值 \(\delta\) 的点，并抑制距离过近的低先验点。
  3. 使用多个不同的 \(\delta\) 值（例如 0.2, 0.5, 1, 2）进行多尺度采样，最后通过 NMS 合并结果，以平衡碎片过滤与物体保留。
- **后处理**：将多尺度采样得到的掩码输入预训练的类别无关 2D 检测器（LDET），进一步滤除不完整的掩码，并根据 2D 边框回归调整物体边界。
- **投影到 3D**：通过相机内外参 \(K, Rt\)，将 2D 边框内的点聚类并反投影到 3D 空间，得到发现的 3D 边界框 \(\{\hat{bb}^{3D}_i\}\)。

#### 2.3 跨模态混合专家（Cross‑Modal MoE）

在训练阶段，模型同时接收点云 \(X_P\) 和 RGB 图像 \(X_I\)，提取体素化 3D 特征 \(F_P\) 和 2D 图像特征 \(F_I\)（通过投影转为体素空间 \(F'_I\)），并拼接得到多模态特征 \(F_M = [F_P, F'_I]\)。

- **模态内增强**：对 \(F_P\)、\(F'_I\)、\(F_M\) 分别应用自注意力（Self‑Attention），学习各自空间上的重要区域。
- **动态路由**：使用一个多模态路由器 \(R\)（含 3D 卷积、全局池化、全连接层和 Softmax），以 \(F_M\) 为输入，输出路由概率 \(p_P, p_I, p_M\)。
- **专家加权融合**：定义三个专家 \(E_P\)（几何专家）、\(E_I\)（语义专家）、\(E_M\)（融合专家），每个专家由三层 3D 卷积构成。最终融合特征为：
  \[
  F = \sum_{i \in \{P, I, M\}} p_i \cdot E_i(F_i)
  \]
- **检测头**：将 \(F\) 送入基于 Transformer 的 3D 检测头，进行类别无关的二分类（前景/背景）和边界框回归。分类损失被设定为类别无关的二分类损失。

#### 2.4 训练与推理流程

- **训练**：利用 3D 物体发现得到的大量类别无关 3D 框和原始标注框共同监督模型。使用 RGB‑点云对进行多模态训练。
- **推理**：直接输入点云‑图像对，由跨模态 MoE 完成特征融合与类别无关检测，全程无需任何额外的文本提示或后处理模块。

### 3. 实验设计

#### 3.1 数据集与场景划分

- **室内场景**：
  - **SUN RGB‑D**（46 类）：取样本数最多的 10 类为基类，其余 36 类为新类。
  - **ScanNet V2**（200 类）：同样取样本数最多的 10 类为基类（实际报告中为 50 类新类，即总 60 类参与评估）。
- **室外场景**：
  - **KITTI**：将汽车（car）作为基类，行人与骑行者作为新类。
- **评估指标**：主要采用 **Average Recall (AR)** 在 IoU 阈值 0.25 下衡量召回能力；同时报告 Average Precision (AP) 作为辅助指标。对于室外 KITTI，采用官方 AP₇₀（40 个召回位置）。

#### 3.2 对比方法

- **封闭世界 3D 检测器**（转为类别无关二分类）：
  - VoteNet、GroupFree3D、FCAF3D、Uni3DETR、Tr3D（室内）
  - SECOND、PointPillar、Part‑A²、3DSSD、PV‑RCNN、Uni3DETR（室外）
- **开放词汇 3D 检测器**（类别提示统一改为 "object"）：
  - Det‑PointCLIPv2、3D‑CLIP、CoDA、OV‑Uni3DETR、ImOV3D
  - 此外，在类别特定检测扩展实验中还比较了 INHA、CoDAv2、GLRD 等。

#### 3.3 实验类型

- **跨类别泛化**：在 SUN RGB‑D 和 ScanNet 上分别训练，评估基类、新类及所有类的 AR/AP。
- **跨数据集泛化**：ScanNet → SUN RGB‑D 和 SUN RGB‑D → ScanNet，仅评估所有类的 AR/AP（因类别定义冲突）。
- **室外场景泛化**：在 KITTI 上评估 AP₃D 和 AP_BEV。
- **类别特定检测泛化**：将 OP3Det 扩展到类别特定设置，与 CoDA 等开放词汇方法对比 AP。
- **消融实验**：验证 SAM、多尺度点采样、跨模态 MoE 等各组件的贡献。
- **与 2D 开放世界方法对比**：在 COCO→VOC 设定下，用 OP3Det 的 2D 部分进行实例分割对比。
- **可视化分析**：展示检测结果与失败案例。

### 4. 资源与算力

- **硬件**：使用 **NVIDIA A100** GPU。
- **软件与框架**：基于 MMDetection3D 实现，采用 AdamW 优化器。
- **训练细节**：论文给出了批次大小、训练轮次等超参数，并声明将在补充材料中提供估计的训练时间和计算消耗。但**未明确说明具体单次实验的 GPU 数量或训练小时数**。

### 5. 实验数量与充分性

- **实验规模**：
  - 在两个室内数据集、一个室外数据集上进行了多组对比。
  - 覆盖了约 **15 个以上的基线模型**，包括封闭世界和开放词汇两大类。
  - 设计了至少 **3 组主要消融实验**（SAM、多尺度点采样、CM‑MoE），并进一步消融了不同融合方式（加法、拼接、CM‑MoE）和多尺度采样参数 \(\delta\) 的影响。
  - 额外测试了跨数据集泛化、类别特定任务扩展、与 2D 方法的对比、与 SAM3D 的定性对比等。
- **充分性与公平性**：
  - 实验设置详尽，类别划分遵循已有工作（如 CoDA），封闭世界检测器均被转换为类别无关的二分类模式，开放词汇方法的提示统一为 "object"，确保了比较的**公平性**。
  - 通过多个数据集、多个模态、室内外场景的验证，展示了方法的**客观性与泛化性**。消融实验完整揭示了各模块的贡献，证据较为充分。

### 6. 主要结论与发现

- OP3Det 在**新类别发现**上显著超越所有基线：在 SUN RGB‑D 上 AR_novel 提升 16.0%（相对于 OV‑Uni3DETR），在 ScanNet 上提升 12.3%。
- 模型不仅对新类有效，**基类性能也保持优势**，全局 AR 和 AP 均有提升。
- **跨数据集泛化能力强**：例如 ScanNet → SUN RGB‑D 的 AR₂₅ 达到 73.1%，远超其他方法，且接近同数据集表现。
- 在室外 KITTI 数据集上同样取得最优 AP₃D，证明方法对稀疏 LiDAR 点云也有良好适应性。
- 即使从类别无关扩展到类别特定检测，OP3Det 仍优于现有开放词汇检测器，表明其学习到的物体性可作为高质量基础迁移至具体类别任务。
- 跨模态 MoE 的动态路由机制比传统的特征相加或拼接融合方式更有效，能够根据场景自适应地利用几何或语义信息。

### 7. 优点

- **问题定义新颖**：首次正式提出类别无关的开放世界 3D 目标检测，直面真实开放世界的需求。
- **完全无提示（Prompt‑free）**：推理时不依赖任何人工设计的文本提示，直接从几何与视觉信号中学习物体性，避免了词汇表限制。
- **有效的 2D 知识迁移**：通过多尺度点采样巧妙利用 SAM 与类别无关 2D 检测器，缓解了 SAM 碎片化问题，高质量地将 2D 语义知识注入 3D 域。
- **动态多模态融合**：跨模态 MoE 模块能够自适应地选择单模态或多模态特征，在开放世界中平衡了语义与几何信息的贡献，优于 naive 融合方案。
- **实验全面扎实**：涵盖室内外场景、跨类别/跨数据集/类别特定扩展、多类基线以及丰富的消融分析，验证充分。
- **通用性**：方法可灵活扩展至室外、类别特定检测，甚至 2D 开放世界任务。

### 8. 不足与局限

- **对低纹理、非刚性物体存在失败案例**：如白色窗帘、同色背景下的物体可能无法检测，因为这类物体缺乏明显的几何或颜色特征，且边界模糊。
- **依赖准确的 2D‑3D 投影**：3D 物体发现阶段需要相机内外参将 2D 边框投影到 3D 空间，在传感器校准不准或遮挡严重的场景下，可能会引入误差。
- **未充分探讨计算开销**：虽然提到在 A100 上训练，但未给出具体的训练时长、推理延迟等计算效率分析，在实际部署时可能受限。
- **数据集规模与多样性**：目前仅在 SUN RGB‑D、ScanNet、KITTI 上验证，尚未在更大规模的室外数据集（如 nuScenes、Waymo）上报告结果，实际泛化上限有待进一步检验。
- **对完全未见的环境极端变化的鲁棒性未测试**：跨数据集实验已展示一定泛化能力，但若传感器类型、点云密度差异极大，性能可能会有所衰减。

（完）
