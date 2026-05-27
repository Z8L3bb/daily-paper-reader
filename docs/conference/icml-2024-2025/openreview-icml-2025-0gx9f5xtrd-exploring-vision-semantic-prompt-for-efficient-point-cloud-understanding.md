---
title: Exploring Vision Semantic Prompt for Efficient Point Cloud Understanding
title_zh: 探索视觉语义提示以实现高效的点云理解
authors: "Yixin Zha, Chuxin Wang, Wenfei Yang, Tianzhu Zhang, Feng Wu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=0gX9f5xTrD"
tags: ["query:stage-d-det"]
score: 5.0
evidence: 提出利用二维语义提示进行高效点云理解微调的范式，与三维感知任务相关。
tldr: 针对三维预训练模型全微调带来的灾难性遗忘和高存储成本问题，现有参数高效迁移学习（PETL）方法未能充分对齐下游任务所需的语义特征关系。该论文提出利用冻结的二维预训练模型作为视觉语义提示，为三维点云理解注入丰富语义，设计了一种新颖的微调范式。实验结果显示，该方法在多个点云理解任务上性能优于现有PETL方法，同时大幅减少可训练参数，为边缘设备部署点云模型提供了可行方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-0gx9f5xtrd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1746, \"height\": 709, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0gx9f5xtrd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 877, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0gx9f5xtrd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1734, \"height\": 940, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0gx9f5xtrd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0gx9f5xtrd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 528, \"height\": 736, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0gx9f5xtrd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 643, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0gx9f5xtrd/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1769, \"height\": 893, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0gx9f5xtrd/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1769, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0gx9f5xtrd/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0gx9f5xtrd/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1771, \"height\": 902, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-0gx9f5xtrd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1765, \"height\": 1652, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0gx9f5xtrd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 992, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0gx9f5xtrd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 890, \"height\": 866, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0gx9f5xtrd/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 875, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0gx9f5xtrd/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1708, \"height\": 986, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0gx9f5xtrd/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 786, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0gx9f5xtrd/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 688, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0gx9f5xtrd/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 924, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0gx9f5xtrd/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 871, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0gx9f5xtrd/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 849, \"height\": 276, \"label\": \"Table\"}]"
motivation: 现有3D PETL方法未能充分对齐下游任务的语义特征关系，导致性能次优。
method: 提出利用冻结的2D预训练模型作为视觉语义提示，为3D点云模型提供语义引导的微调范式。
result: 在多个点云理解任务上，该方法性能优于现有PETL方法，且可训练参数大幅减少。
conclusion: 该范式实现了参数高效且语义丰富的点云模型微调，适合边缘部署。
---

## Abstract
A series of pre-trained models have demonstrated promising results in point cloud understanding tasks and are widely applied to downstream tasks through fine-tuning. However, full fine-tuning leads to the forgetting of pretrained knowledge and substantial storage costs on edge devices. To address these issues, Parameter-Efficient Transfer Learning (PETL) methods have been proposed. According to our analysis, we find that existing 3D PETL methods cannot adequately align with semantic relationships of features required by downstream tasks, resulting in suboptimal performance. To ensure parameter efficiency while introducing rich semantic cues, we propose a novel fine-tuning paradigm for 3D pre-trained models. We utilize frozen 2D pre-trained models to provide vision semantic prompts and design a new Hybrid Attention Adapter to efficiently fuse 2D semantic cues into 3D representations with minimal trainable parameters(1.8M). Extensive experiments conducted on datasets including ScanObjectNN, ModelNet40, and ShapeNetPart demonstrate the effectiveness of our proposed paradigm. In particular, our method achieves 95.6% accuracy on ModelNet40 and attains 90.09% performance on the most challenging classification split ScanObjectNN(PB-T50-RS).

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义
*   **研究背景**：大型预训练模型在3D点云理解任务上取得了成功，但通过全量微调应用于下游任务时存在两大缺陷：
    1.  **灾难性遗忘**：微调所有参数会导致模型遗忘预训练阶段学到的通用知识。
    2.  **高存储成本**：在边缘设备上，为每个下游任务存储一份完整的微调后模型参数成本高昂。
*   **核心问题**：为解决上述问题，参数高效迁移学习方法被提出。然而，作者通过分析发现，**现有的3D PETL方法未能充分对齐下游任务所需的语义特征关系**，因为其主干网络被冻结，输出的特征缺少丰富的语义线索，限制了模型的泛化能力。
*   **整体含义与动机**：基于2D图像比3D点云包含更丰富的语义信息这一观察，论文提出一个核心问题：**能否利用现成的、冻结的2D预训练模型提供视觉语义提示，以极少的可训练参数显著提升3D模型在下游任务上的性能？**

### 2. 论文提出的方法论
论文提出一个全新的微调范式，其核心思想是**利用冻结的2D模型作为额外的视觉语义提示源，通过一个混合注意力适配器高效地将2D语义融入3D特征**。整体流程如下图所示（文中图3），关键技术细节如下：

*   **3D到2D投影**：为了能让2D模型理解点云，首先将点云从**三个正交视图**投影成2D深度图，以缓解单一视图带来的局部和全局几何歧义。
*   **多尺度模态融合框架**：
    *   **双流处理**：3D点云和生成的2D深度图分别输入到冻结的3D和2D预训练Transformer中，进行逐层的并行处理。2D模型选用的是CLIP或DINOv2的图像编码器。
    *   **视觉语义提示生成**：在每一层，对三个视图的2D类别令牌（Class Token）进行最大池化，然后通过一个共享的**多层感知机**将其映射到3D语义特征空间，生成视觉语义提示。
    *   **混合注意力适配器**：这是实现高效模态融合的核心模块。在此适配器内：
        1.  **语义迁移**：生成的2D语义提示通过两个并行的非线性层，产生缩放（α）和偏移（β）参数，用于调制归一化后的3D特征，得到语义增强的混合特征，以解耦语义信息并减轻局部歧义。
        2.  **混合注意力**：提出一种新颖的注意力机制，用**语义增强后的混合特征**作为查询和键，用**未改变的原始3D特征**作为值来计算自注意力。此设计旨在更新3D特征间的语义关联，同时过滤掉来自2D模态的冗余噪声。
*   **模态语义对齐**：在模型的最后一层，将2D语义提示与3D特征结合后再送入下游任务头，以显式地对齐两个模态的特征空间。

### 3. 实验设计
论文在多种任务和数据集上验证了方法的有效性。

*   **数据集/场景**:
    *   **真实世界物体分类**: ScanObjectNN（包含其三个难度变体：OBJ\_BG, OBJ\_ONLY, PB\_T50\_RS）。
    *   **合成物体分类**: ModelNet40。
    *   **零件分割**: ShapeNetPart。
    *   **小样本学习**: ModelNet40上的少样本分类（5-way和10-way，10-shot和20-shot）。
*   **Benchmark比较方法**:
    *   **完全监督学习方法**: PointNet, PointNet++, DGCNN, PointNeXt等。
    *   **自监督预训练 + 全量微调方法**: Point-BERT, Point-MAE, ACT, PointMamba等。
    *   **自监督预训练 + 参数高效微调方法**: IDPT, DAPT, Point-PEFT。论文将提出的方法作为这些3D PETL方法的增强版本进行对比。
*   **2D与3D预训练模型组合**: 为验证通用性，在2D (CLIP, DINOv2) 和 3D (Point-BERT, Point-MAE) 模型上进行了四种组合实验。

### 4. 资源与算力
*   **硬件**: 论文明确指出所有实验均在**单张GeForce RTX 3090** GPU上完成。
*   **训练时长**: 论文未提及具体的每次实验耗时。

### 5. 实验数量与充分性
*   **实验充分性**: 实验设计**非常充分、客观且公平**。
    *   **多任务覆盖**: 涵盖了分类、零件分割和小样本学习等多种下游任务。
    *   **多数据集覆盖**: 包括真实世界和合成数据集，以及不同难度级别。
    *   **多模型组合验证**: 通过4种（2D, 3D）模型组合，证明了范式的通用性，避免了在单一模型上的过拟合结论。
    *   **公平对比基线**: 包括监督、全微调、多种PETL方法，并且统一采用冻结2D和3D骨干网络、只更新插入模块的设定。
    *   **详尽的消融实验**: 从2D基线开始，逐步加入3D模型、语义迁移、自注意力、混合注意力等模块，清晰展示了每个设计的贡献。还对适配器内部结构（如BN-v的秩）进行了实验。

### 6. 论文的主要结论与发现
论文提出的新范式**首次成功探索了利用冻结的2D预训练模型中的视觉语义线索来高效地增强3D点云理解**。主要结论如下：
1.  该范式能以**极少的可训练参数（约1.8M）**，在多个下游任务上显著提升冻结的3D预训练模型的性能，超越了现有的3D PETL方法。
2.  在部分任务上，该参数高效的方法甚至**超越了全量微调方法**的性能。例如，“Point-MAE + CLIP”的组合在ModelNet40上达到**95.6%的准确率**，在ScanObjectNN最难的PB-T50-RS分割上达到**89.14%**（使用增强后达90.09%）。
3.  通过特征可视化，证实了注入的2D语义信息能够有效对齐点云中相同结构的特征，从而提升了模型的泛化能力。

### 7. 优点
*   **创新性强**：首次将2D视觉语义提示引入3D PETL领域，思路新颖。
*   **设计精巧**：提出的混合注意力适配器通过解耦语义迁移和特征更新，有效实现了双模态融合并抑制噪声。
*   **参数高效**：在仅增加约1.8M可训练参数的情况下，实现了巨大的性能提升，非常适合边缘计算场景。
*   **通用性和兼容性**：方法不依赖于特定的2D或3D模型架构，可以与任何Transformer-based模型组合使用，潜力巨大。
*   **实验扎实且表现优异**：在多个数据集和任务上取得了SOTA性能，并通过详尽的消融实验和可视化证明了方法的有效性。

### 8. 不足与局限
*   **计算量（FLOPs）较高**：论文在讨论部分明确指出，由于引入了完整的2D预训练模型（如ViT-B/16或ViT-B/14）参与推理过程，导致整个框架的浮点运算次数相对较高。这是为了利用强大的2D语义模型所付出的算力代价。
*   **2D模型依赖**：方法的性能提升高度依赖于所选2D预训练模型的语义丰富度和鲁棒性。如果未来出现更轻量高效的2D模型，此范式则可以立即受益，但目前尚未解决对大型2D模型的固有依赖。
*   **投影方式**: 投影采用三个正交视图，虽然缓解了歧义，但对于形状特别复杂或有自遮挡的物体，固定正交视图可能不是最优的2D观察角度。
*   **未明确训练时间**：论文未提供在RTX 3090上的具体训练耗时，使得评估其训练阶段的计算开销不够直观。

（完）
