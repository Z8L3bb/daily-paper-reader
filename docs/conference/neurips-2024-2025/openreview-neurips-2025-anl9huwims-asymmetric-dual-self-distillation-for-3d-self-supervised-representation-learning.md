---
title: Asymmetric Dual Self-Distillation for 3D Self-Supervised Representation Learning
title_zh: 面向3D自监督表征学习的非对称双自蒸馏
authors: "Remco F. Leijenaar, Hamidreza Kasaei"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ANl9HuwIMs"
tags: ["query:lidar-d-det"]
score: 4.0
evidence: 使用注意力机制进行点云特征学习
tldr: 针对无监督3D点云表征学习，提出非对称双自蒸馏框架，结合掩码建模与不变性学习，通过潜空间预测和注意力机制防止形状泄露，统一了掩码建模与对比学习，提升了语义表征质量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1088, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1288, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 557, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 492, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 654, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 705, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1134, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1454, \"height\": 795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 697, \"height\": 716, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1415, \"height\": 837, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1095, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1467, \"height\": 899, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-anl9huwims/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1447, \"height\": 554, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1397, \"height\": 1073, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 816, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1348, \"height\": 529, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 518, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 564, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 799, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 822, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1068, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 702, \"height\": 829, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 677, \"height\": 1022, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 828, \"height\": 480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 775, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 543, \"height\": 741, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 817, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1285, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 927, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-anl9huwims/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1296, \"height\": 298, \"label\": \"Table\"}]"
motivation: 现有掩码点建模依赖重建目标，限制高层语义捕获。
method: 提出非对称双自蒸馏框架，在潜空间统一掩码建模与不变性学习，禁用掩码查询间注意力以防止形状泄露。
result: 在点云理解任务中取得优越的语义表征性能。
conclusion: 该方法有效结合自蒸馏与掩码建模，为3D预训练提供新范式。
---

## Abstract
Learning semantically meaningful representations from unstructured 3D point clouds remains a central challenge in computer vision, especially in the absence of large-scale labeled datasets. While masked point modeling (MPM) is widely used in self-supervised 3D learning, its reconstruction-based objective can limit its ability to capture high-level semantics. We propose AsymDSD, an Asymmetric Dual Self-Distillation framework that unifies masked modeling and invariance learning through prediction in the latent space rather than the input space. AsymDSD builds on a joint embedding architecture and introduces several key design choices: an efficient asymmetric setup, disabling attention between masked queries to prevent shape leakage, multi-mask sampling, and a point cloud adaptation of multi-crop. AsymDSD achieves state-of-the-art results on ScanObjectNN (90.53\%) and further improves to 93.72\% when pretrained on 930k shapes, surpassing prior methods.

---

## 论文详细总结（自动生成）

# 论文总结：Asymmetric Dual Self-Distillation for 3D Self-Supervised Representation Learning

## 1. 核心问题与整体含义

- **问题背景**：从无结构的三维点云中学习具有语义意义的表征是计算机视觉的核心挑战，尤其在缺少大规模标注数据的情况下。
- **现有方法的局限**：当前主流自监督方法——掩码点建模（Masked Point Modeling, MPM）侧重于重建点坐标，倾向于捕捉短程依赖和高频细节，难以学习高层语义抽象，在少样本和线性探测任务上表现不佳。
- **整体含义**：本文旨在通过一种新的自监督学习框架，统一掩码建模与不变性学习，在潜空间中预测表征而非输入空间，从而提升点云表征的语义质量和下游任务性能，并解决形状泄漏、表征坍缩等问题。

## 2. 方法论

### 2.1 核心思想：非对称双自蒸馏 (AsymDSD)
- 将掩码点建模重构为**在潜空间中预测被掩蔽块的教师网络表征**，而非直接重建原始点云。
- 联合优化两个自蒸馏目标：
  1. **全局不变性学习（跨视图自蒸馏）**：通过多裁剪增强，学习全局语义不变的表征。
  2. **块级掩码潜变量预测（同视图自蒸馏）**：预测被掩蔽块对应的动量教师表征。
- 使用离散潜变量（通过 softmax 投影到有限类别）并通过 **centering** 和 **sharpening** 防止表征坍缩。

### 2.2 关键技术细节
- **非对称架构**：
  - 教师网络：完整编码器，处理全量块，输出目标表征。
  - 学生网络：编码器-预测器结构，编码器仅处理可见块，轻量预测器根据掩码查询生成被掩块表征。
  - 预测器中使用**交叉注意力（仅关注可见上下文）并禁用掩码查询之间的自注意力**，防止全局形状通过位置查询泄漏。
- **掩码策略**：采用**逆块状掩码（inverse block-wise masking）**，保留多个固定大小的连续可见区域，迫使模型从局部细节推断全局形状。
- **多掩码 (Multi-Mask)**：每个点云采样多个独立掩码，复用教师目标和学生非上下文化嵌入，在极小计算开销下增大有效批量大小。
- **点云多裁剪 (Multi-Crop)**：采样不同比例（如 5% 到 100%）的裁剪视图，强制学习从局部到全局的映射能力。
- **优化与正则**：AdamW 优化器，余弦学习率与 EMA 衰减，KoLeo 损失增强多样性，标签平滑等。

### 2.3 目标函数
- 全局目标：最小化教师与学生跨视图后验的 KL 散度。
- 块级目标：最大化给定可见上下文时，对被掩块的真实潜变量的对数后验期望（通过交叉熵实现）。
- 最终损失 = 全局损失（跨所有裁剪对）+ 块级损失（对掩码块求和）+ KoLeo 正则项。

## 3. 实验设计

### 3.1 数据集与基准
- **预训练**：
  - ShapeNet-Core（41,952 个合成 CAD 模型，55 类）
  - 大规模混合数据集（**Mixture**，930k+ 实例，含 Objaverse、3D-FUTURE、ScanObjectNN 等）
- **下游评估**：
  - **对象分类**：ModelNet40（合成）、ScanObjectNN（真实扫描，含 OBJ\_BG, OBJ\_ONLY, PB\_T50\_RS 三个子集）
  - **少样本分类**：ModelNet40 的 5-way/10-way × 10-shot/20-shot 协议
  - **部件分割**：ShapeNet-Part
  - **大规模泛化**：Objaverse-LVIS 子集上的少样本线性探测与 kNN

### 3.2 对比方法
- **监督基线**：PointNet, PointMLP, PointNeXt, Adapted ViT-S
- **自监督 MPM 系列**：Point-BERT, Point-MAE, Point-M2AE, PointGPT, Point-FEMAE, MaskPoint 等
- **融合方法**：ReCon（单模态/多模态）, ACT
- **大型预训练对比**：PointGPT-L, ReCon++-B 等

## 4. 资源与算力

- **ShapeNet 预训练**：单张 RTX 4090，约 18 小时（ViT-S 模型）。
- **Mixture 大规模预训练**：
  - AsymDSD-S\*（ViT-S）：单张 A100，100 epoch，约 100 小时。
  - AsymDSD-B\*（ViT-B）：单张 A100，50 epoch，约 175 小时。
- 使用混合精度（FP16）训练，报告了内存与吞吐数据。

## 5. 实验数量与充分性

### 5.1 主要实验
- 在 **ModelNet40** 和 **ScanObjectNN** 上进行了全微调、线性探测和从零训练三个协议，对比十余种 SOTA 方法，并提供标准差。
- **少样本分类**：4 种设定，10 次独立运行，报告平均准确率与标准差。
- **部件分割**：ShapeNet-Part，报告实例和类别平均 IoU。
- **大规模预训练**：比较 ViT-S/ViT-B 在不同规模数据上的全微调和线性性能，包括与后预训练、跨模态模型对比。
- **Objaverse-LVIS** 上的 10-shot 线性与 kNN 评估。

### 5.2 消融与分析
- **裁剪与多裁剪**的作用（有无裁剪、是否多裁剪）。
- **掩码策略**：对比均匀掩码与逆块状掩码，不同掩码比率的影响。
- **预测器设计**：有无预测器、自注意力 vs 交叉注意力、多块预测等，分析形状泄漏与效率。
- **多掩码**：比较有无多掩码的内存、吞吐和下游性能。
- **潜变量 vs 原始点重建**：单独训练以及联合全局目标时的对比。
- **自蒸馏动态**：展示 marginal/posterior 熵、KL 散度、教师与学生性能变化。
- **可视化**：注意力距离、t-SNE 嵌入着色。

**总体评价**：实验覆盖多个主流基准、多种评估协议与大量消融，对比方法全面且客观，实验设计充分。

## 6. 主要结论与发现

- AsymDSD 在 **ScanObjectNN-PB\_T50\_RS** 上以 **90.53%** 达到单模态标准 Transformer 的 SOTA，线性探测性能超越所有自监督方法。
- 联合优化全局不变性和局部掩码预测产生**显著的协同效应**，优于单独使用任一目标。
- 转换到潜空间预测目标比重建原始点云更能提升语义抽象，尤其与全局目标结合时。
- 逆块状掩码、非对称预测器设计、多掩码和多裁剪是性能提升的关键，并能大幅提高训练效率（内存与吞吐改善约 70%）。
- 方法展现出良好的可扩展性，预训练数据扩大至 93 万样本时，ScanObjectNN 精度进一步提升至 **93.72%**。

## 7. 优点

- **创新性强**：首次在 3D 点云自监督中同时纳入了潜空间掩码预测、非对称架构、形状泄漏防护、多掩码和多裁剪等多项设计。
- **效率高**：编码器只处理少量可见块，预测器轻量，多掩码策略极大降低计算开销，训练速度快。
- **防止坍缩和泄漏**：通过 centering/sharpening、预测器交叉注意力和联合优化有效避免常见问题。
- **实验扎实**：在多个数据集、协议、规模下系统验证，消融实验全面，提供了深入的动态分析。
- **易复现**：公开代码、详细配置，采用标准 ViT 架构，方便后续研究。

## 8. 不足与局限

- **数据集偏向**：预训练和评估主要集中于**物体为中心的数据集**，未在大型场景点云（如室内/室外场景理解）上验证。
- **架构限制**：当前采用平坦层次结构的 ViT，难以扩展到大规模场景点云，需要层级化或多分辨率改进。
- **缺乏多模态对比**：未明确结合图像、文本等跨模态信息，在大规模多模态模型涌现的背景下，纯单模态方法的竞争力有待观察。
- **统计显著性检验缺失**：作者申明未进行统计显著性测试（仅报告标准差）。
- **部件分割性能中等**：在 ShapeNet-Part 上未超越使用 U-Net 式架构的专门方法，表明对密集预测任务的适应性有待提升。

（完）
