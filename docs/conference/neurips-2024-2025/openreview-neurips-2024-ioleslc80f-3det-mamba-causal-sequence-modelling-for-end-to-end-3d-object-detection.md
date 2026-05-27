---
title: "3DET-Mamba: Causal Sequence Modelling for End-to-End 3D Object Detection"
title_zh: "3DET-Mamba: 因果序列建模用于端到端3D目标检测"
authors: "Mingsheng Li, Jiakang Yuan, Sijin Chen, Lin Zhang, Anyu Zhu, Xin Chen, Tao Chen"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=iOleSlC80F"
tags: ["query:stage-d-det"]
score: 9.0
evidence: 基于状态空间模型的点云3D目标检测，具有高效序列建模
tldr: Transformer在3D点云目标检测中表现出色，但其二次复杂度难以处理高分辨率点云。本文首次将状态空间模型Mamba用于3D场景级感知，提出3DET-Mamba。方法将点云分块，使用内部Mamba捕获局部几何，再通过外部Mamba建模场景上下文。在室内检测基准上，该方法以线性复杂度取得与Transformer相当或更优的性能。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-ioleslc80f/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ioleslc80f/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ioleslc80f/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 613, \"height\": 702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ioleslc80f/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 672, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-ioleslc80f/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1377, \"height\": 593, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ioleslc80f/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 905, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ioleslc80f/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 585, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ioleslc80f/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 669, \"height\": 193, \"label\": \"Table\"}]"
motivation: 注意力机制二次复杂度限制了点云高分辨率特征编码。
method: 提出基于Mamba的3D检测器，通过内外部Mamba分别建模局部和全局特征。
result: 在室内3D检测数据集上达到与SOTA相当的性能，且计算复杂度更低。
conclusion: 状态空间模型为高效3D目标检测提供了新方向，尤其适合长序列点云。
---

## Abstract
Transformer-based architectures have been proven successful in detecting 3D objects from point clouds. However, the quadratic complexity of the attention mechanism struggles to encode rich information as point cloud resolution increases. Recently, state space models (SSM) such as Mamba have gained great attention due to their linear complexity and long sequence modeling ability for language understanding. To exploit the potential of Mamba on 3D scene-level perception, for the first time, we propose 3DET-Mamba, which is a novel SSM-based model designed for indoor 3d object detection. Specifically, we divide the point cloud into different patches and use a lightweight yet effective Inner Mamba to capture local geometric information. To observe the scene from a global perspective, we introduce a novel Dual Mamba module that models the point cloud in terms of spatial distribution and continuity. Additionally, we design a Query-aware Mamba module that decodes context features into object sets under the guidance of learnable queries. Extensive experiments demonstrate that 3DET-Mamba surpasses previous 3DETR on indoor 3D detection benchmarks such as ScanNet, improving AP25/AP50 from 65.0\%/47.0\% to 70.4\%/54.4\%, respectively.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义 (研究动机和背景)
- **核心问题**：现有的基于 Transformer 的 3D 点云目标检测器（如 3DETR）虽然性能优异，但其注意力机制具有**二次计算复杂度**。随着点云分辨率提高（序列变长），该类模型在有限计算资源下难以编码丰富的场景信息。
- **研究动机**：状态空间模型（SSM）特别是 Mamba 具备**线性复杂度**和**强大的长序列建模能力**，已在自然语言处理中取得成功。然而，Mamba 是为因果 1-D 序列设计的，直接应用于无序、非因果的 3-D 点云存在困难。
- **整体含义**：本文首次将 Mamba 引入到 3D 场景级感知任务中，提出了一个端到端的 3D 目标检测器 **3DET-Mamba**，旨在利用 Mamba 的高效性来捕捉 3D 场景中的长距离依赖，解决 Transformer 的计算瓶颈。

### 2. 论文提出的方法论：核心思想、关键技术细节
核心思想是设计一个基于 Mamba 的编码器-解码器架构，通过**局部到全局的扫描机制**和**查询感知解码**来适配 3D 点云。

- **场景特征聚合器 (Scene Feature Aggregator)**
    - **内部 Mamba (Inner Mamba) 块**：用于局部特征提取。
        - 首先通过最远点采样（FPS）和 K 近邻（KNN）将点云划分为多个局部块（patch）。
        - 对每个块内的点，根据其到中心点的距离进行**排序**，使其成为有序的因果序列。
        - 将该序列送入一个轻量级 Mamba 块中进行局部几何特征聚合，最后使用最大池化得到该块的嵌入特征。
    - **双 Mamba (Dual Mamba) 块**：用于全局场景上下文建模。
        - 将每个块视为一个 token，并采用 **两种不同的空间排序策略** 来生成序列：**最远点采样（FPS）顺序**（最大化相邻 token 距离，增加分布感知）和**最近点采样（NPS）顺序**（保持空间邻近性，保留局部一致性）。
        - 两条分支分别处理 FPS 和 NPS 序列，各自通过独立的 SSM、1D 卷积和 SiLU 激活函数进行前向传播。
        - 最终将两个分支输出的特征相加并经过线性层，得到全局表征。

- **解码器 (Decoder)**
    - **查询感知 Mamba (Query-aware Mamba) 块**：用于将场景特征解码为目标集合。
        - 通过 FPS 从关键点中选取固定数量的查询点，并将其坐标通过傅里叶变换和 MLP 转换为可学习的查询嵌入。
        - 每个解码块内部，**场景特征**和**查询序列**分别经过独立的 Mamba 块（含归一化、卷积、SSM）进行建模。
        - 最后将处理后的场景特征与查询嵌入进行**逐元素相乘**，实现场景上下文信息与查询的融合，并经过多层 MLP 输出最终预测。

- **训练目标**
    - 采用与 3DETR 相同的集合预测损失。使用二分图匹配预测框与真值框，计算交并比损失 \(L_{giou}\)，以及中心点、尺寸的 \(\ell_1\) 损失和角度残差的 Huber 损失等几何损失 \(L_{geo}\)，并加上角度与语义分类的交叉熵损失 \(L_{sem}\)。

### 3. 实验设计：数据集 / 场景、基准、对比方法
- **数据集与场景**
    - **ScanNet V2**: 室内场景，包含 1201 个训练样本和 312 个验证样本，18 个物体类别。
    - **SUN RGB-D**: 室内场景，包含 5285 个训练样本和 5050 个验证样本，10 个最常见物体类别。RGB-D 图像通过相机参数转换为点云。
- **评估指标**
    - 采用平均精度均值 (mAP) 在 3D IoU 阈值为 0.25 和 0.5 下的指标 (mAP@0.25 和 mAP@0.5)。
- **对比方法**
    - 主要与 **3DETR** (Transformer 基线) 进行对比，同时也报告了 VoteNet, GroupFree3D, H3DNet, BRNet 等基于 PointNet++ 或 Transformer 的方法的性能作为参考。
    - 报告了使用与 3DETR 相同点数和查询数的 **3DET-Mamba**，以及加倍点数和查询数以测试长序列能力的 **3DET-Mamba†**。

### 4. 资源与算力
- **GPU**: 论文明确说明使用了 **8 块 NVIDIA 3090 GPU (24GB)** 进行训练。
- **总批次大小**: 64。
- **训练时长**: **未提及**。
- **优化器与超参数**: 使用 AdamW 优化器，基础学习率 \(7 \times 10^{-4}\)，余弦衰减至 \(10^{-6}\)，权重衰减 0.1。梯度范数裁剪为 0.1。

### 5. 实验数量与充分性
- **实验数量**：大约进行了 4 组主要实验。
    - **主要结果对比**：在 ScanNet 和 SUN RGB-D 两个数据集上与多个现有方法进行性能比较。
    - **消融实验**：
        - **编码器组件分析**：比较 PointNet++、Transformer、Inner Mamba、Dual Mamba 的不同组合对性能的影响。
        - **双 Mamba 块效果分析**：将 Dual Mamba 替换为原始 Mamba 块和双向 Mamba 块进行对比。
        - **查询感知 Mamba 块效果分析**：将解码器替换为 Transformer 解码器和直接拼接的 Mamba 解码器。
- **充分性与公平性**：
    - 实验设计较为充分，通过消融实验清晰地验证了所提核心模块（Inner Mamba, Dual Mamba, Query-aware Mamba）的有效性。
    - 对比基线（3DETR）遵循相同的设置（点云数量、查询数量），确保了公平性。通过增加序列长度（3DET-Mamba†）进一步验证了模型处理长序列的优势，符合 Mamba 的设计初衷。
    - 实验覆盖了主流的室内 3D 检测基准，但未涉及室外场景。

### 6. 论文的主要结论与发现
- **性能超越基线**：3DET-Mamba 在 ScanNet 和 SUN RGB-D 数据集上均**超越了基于 Transformer 的 3DETR**。例如，在 ScanNet 上，mAP@0.25/mAP@0.50 从 65.0%/47.0% 提升至 66.9%/48.7%。
- **长序列建模优势**：通过增加输入点云数量和查询数量（3DET-Mamba†），性能可以得到进一步的显著提升（ScanNet mAP@0.5 提升至 54.4%），证明了 Mamba 在处理长序列时的固有优势。
- **架构有效性**：所提出的局部-全局扫描机制、双 Mamba 和查询感知 Mamba，都是有效的设计，能够很好地适配 3D 目标检测任务。

### 7. 优点：方法或实验设计上的亮点
- **开创性探索**：首次将状态空间模型 Mamba 应用于 3D 场景级别的感知任务，填补了该领域的空白。
- **精巧的适配设计**：针对点云无序、非因果的特性，设计了**多分支空间排序策略**（FPS 和 NPS）和**局部到全局扫描机制**，巧妙地将 1D 因果 Mamba 模型适配到 3D 数据。
- **全面的编解码架构**：不仅设计了高效的 Mamba 编码器，还针对 DETR 范式设计了**查询感知 Mamba 解码器**，通过乘法交互有效融合查询场景特征，优于简单的序列拼接。
- **可扩展性验证**：通过增加点云和查询序列长度的实验，直观地展示了模型性能随序列增长而提升的潜力，凸显了线性复杂度的价值。

### 8. 不足与局限：实验覆盖、偏差风险、应用限制等
- **数据类型局限**：论文明确指出，目前仅探索了点云数据，尚未验证模型在处理其他 3D 数据类型（如网格）上的潜力，通用性有待考察。
- **计算资源信息不全**：虽然公布了 GPU 型号和数量，但**未提供训练时长**等具体资源消耗数据，不利于精确评估计算效益。
- **实验场景偏差**：仅在室内场景数据集（ScanNet, SUN RGB-D）上进行了验证，缺乏在**室外大规模自动驾驶场景**（如 KITTI, Waymo）上的实验结论，限制了结论的广泛性。
- **技术应用风险**：作为 3D 感知模型，虽然文中未强调负面社会影响，但应用于监控、自动驾驶等领域时，存在潜在的隐私和公平性风险。
- **缺少统计显著性检验**：实验未提供误差棒或多次运行的方差结果，无法评估结果的统计稳定性。

（完）
