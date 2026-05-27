---
title: Spherical Frustum Sparse Convolution Network for LiDAR Point Cloud Semantic Segmentation
title_zh: 面向LiDAR点云语义分割的球面视锥稀疏卷积网络
authors: "Yu Zheng, Guangming Wang, Jiuming Liu, Marc Pollefeys, Hesheng Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=LqdcdqIeVD"
tags: ["query:stage-d-det"]
score: 8.0
evidence: 提出球面视锥稀疏卷积保留所有点，实现LiDAR点云的高效操作
tldr: 针对LiDAR点云语义分割中2D投影方法导致的量化信息损失问题，提出球面视锥稀疏卷积网络。该方法利用球面视锥结构保留全部点，并结合稀疏卷积进行高效处理，在语义分割任务中显著提升小物体分割性能。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-lqdcdqievd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1374, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lqdcdqievd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lqdcdqievd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lqdcdqievd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 1094, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lqdcdqievd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 996, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lqdcdqievd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1450, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lqdcdqievd/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1396, \"height\": 1553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lqdcdqievd/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1362, \"height\": 1531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lqdcdqievd/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1362, \"height\": 1543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lqdcdqievd/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1368, \"height\": 1702, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 886, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 727, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 726, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 547, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 661, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1014, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 793, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 937, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 760, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 937, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1392, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lqdcdqievd/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 950, \"height\": 272, \"label\": \"Table\"}]"
motivation: 解决现有2D投影式LiDAR点云分割方法因投影量化导致信息丢失、小物体几何结构不完整的难题。
method: 提出球面视锥结构保存所有点，设计对应的稀疏卷积网络直接处理3D点云以进行语义分割。
result: 在LiDAR点云语义分割任务上，方法有效保留小物体信息，提高分割精度。
conclusion: 球面视锥稀疏卷积网络避免量化损失，为LiDAR点云语义分割提供了一种更完整且高效的框架。
---

## Abstract
LiDAR point cloud semantic segmentation enables the robots to obtain fine-grained semantic information of the surrounding environment. Recently, many works project the point cloud onto the 2D image and adopt the 2D Convolutional Neural Networks (CNNs) or vision transformer for LiDAR point cloud semantic segmentation. However, since more than one point can be projected onto the same 2D position but only one point can be preserved, the previous 2D projection-based segmentation methods suffer from inevitable quantized information loss, which results in incomplete geometric structure, especially for small objects. To avoid quantized information loss, in this paper, we propose a novel spherical frustum structure, which preserves all points projected onto the same 2D position. Additionally, a hash-based representation is proposed for memory-efficient spherical frustum storage. Based on the spherical frustum structure, the Spherical Frustum sparse Convolution (SFC) and Frustum Farthest Point Sampling (F2PS) are proposed to convolve and sample the points stored in spherical frustums respectively. Finally, we present the Spherical Frustum sparse Convolution Network (SFCNet) to adopt 2D CNNs for LiDAR point cloud semantic segmentation without quantized information loss. Extensive experiments on the SemanticKITTI and nuScenes datasets demonstrate that our SFCNet outperforms previous 2D projection-based semantic segmentation methods based on conventional spherical projection and shows better performance on small object segmentation by preserving complete geometric structure. Codes will be available at https://github.com/IRMVLab/SFCNet.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究背景**：LiDAR 点云语义分割是自动驾驶与机器人环境感知的关键任务。近年来，基于 2D 投影（尤其是球面投影）的方法因其高效性而备受关注，它们将点云投影为 2D 图像，再利用成熟的 2D CNN 或 Transformer 进行处理。
- **核心问题**：传统的球面投影存在不可避免的**量化信息损失**。当多个点被投影到同一个 2D 网格时，仅保留离原点最近的点，其余点被丢弃，导致几何结构不完整，特别是对小物体（如行人、自行车、杆状物）的分割性能造成严重损害。现有的补偿方案（如 KNN 后处理或点网络细化）仅在预测阶段进行修补，而未解决特征聚合过程中的信息丢失。
- **整体含义**：本文旨在从根本上解决量化信息损失问题，提出一种名为**球面视锥**的新数据结构，能够保留所有投影到同一网格的点，并配套设计相应的稀疏卷积网络，使得 2D CNN 可以直接处理完整的点云，从而提升小物体的分割精度。

### 2. 论文提出的方法论
论文的核心思想是构建一个**球面视锥（Spherical Frustum）**结构，并基于此设计神经网络的关键操作。具体技术细节如下：

- **球面视锥结构**：
    - 不同于传统投影只保留一个点，球面视锥将投影到同一 2D 坐标 `(u, v)` 的所有点组织成一个点集，并为每个点分配一个在视锥内的唯一索引 `m`。这样，所有点的 3D 坐标和特征得以完整保留，消除了量化损失。
    - **哈希表示**：为避免稠密存储带来的内存浪费，采用哈希表将三元组 `(u, v, m)` 映射到原始点云索引 `k`，实现内存高效且支持快速查询的非规则存储。

- **球面视锥稀疏卷积（SFC）**：
    - 用于在球面视锥结构上执行 2D 卷积特征聚合。
    - 流程：对于中心点，依卷积核内的偏移量确定待卷积的球面视锥，通过哈希表查询这些视锥中的点。然后，根据 3D 距离（实际采用 range 距离 `|r_j - r|` 以简化计算）选择每个视锥中**距离中心点最近的点**的特征。最后，将这些被选点的特征进行加权求和，完成稀疏卷积。`f' = sum(W_i f_i)`。该操作实现了对非结构点云的规则化与局部特征聚合。

- **视锥最远点采样（F2PS）**：
    - 一种高效且均匀的 3D 点云降采样方法，结合了步长采样和点集内采样。
    - 流程：首先按步长 `(S_h, S_w)` 对球面视锥进行合并降采样；然后，对合并后每个视锥内的点集，利用**最远点采样（FPS）** 在 3D 坐标下均匀采样。由于每个视锥内点数量有限，FPS 的计算复杂度为常数级，因此 F2PS 总体复杂度为 O(N)，非常高效。

- **网络架构（SFCNet）**：
    - 基于上述操作构建的编码器-解码器架构。编码器使用残差 SFC 块和 F2PS 进行多层特征提取，解码器通过带有特定上采样率的 SFC 层恢复分辨率并拼接特征，最终通过头部层输出语义预测。

### 3. 实验设计
- **数据集**：在 **SemanticKITTI**（64 线激光雷达，19 类，点云较稠密）和 **nuScenes**（32 线激光雷达，16 类，点云较稀疏）两个权威大规模自动驾驶数据集上进行验证。使用官方划分的训练/验证/测试集。
- **基准指标**：采用语义分割任务通用的**平均交并比（mIoU）** 评估。
- **对比方法**：与三大类主流方法进行了全面比较：
    - **点基方法**：PointNet++, RandLA, KPConv。
    - **3D 体素方法**：Cylinder3D, (AF)2-S3Net, SphereFormer。
    - **2D 投影方法**：RangeNet++, PolarNet, SqueezeSegV3, SalsaNext, KPRNet, Lite-HDSeg, RangeViT, CENet。

### 4. 资源与算力
- **硬件**：模型训练在**单张 NVIDIA Quadro RTX 8000 GPU** 上进行。
- **软件**：基于 PyTorch 框架实现。
- **训练细节**：训练批次大小设为 4。优化器为 Adam，初始学习率 0.001，每 epoch 衰减 5%。使用了包括随机旋转、翻转、平移、缩放在内的数据增强，并采用多层加权交叉熵损失和 Lovász-Softmax 损失进行优化。
- **推理效率**：在 RTX 4090Ti 上进行效率测试，SFCNet 处理一帧 SemanticKITTI 点云约需 59.7ms，归一化时间（每千点）为 0.49ms，优于对比的主流方法，达到实时性。

### 5. 实验数量与充分性
实验设计**非常充分且客观**，主要包含以下几组：
- **主要定量结果**：在两个数据集上与多达 10 余种代表性方法进行对比，并提供了详细的每类 IoU 分析。
- **定性结果**：展示了与 CENet、RangeViT 等方法在多个场景下的错误图对比，并通过 RGB 图像上的投影结果进行可视化，直观展示了小物体分割效果的提升。
- **消融实验**：在 SemanticKITTI 验证集上，以常规球面投影和步长采样为基线，逐步加入 SFC 和 F2PS，验证了每个模块的有效性（mIoU 从 56.2% 提升到 62.9%）。
- **对比分析**：
    - 与基于修复的方法（KNN后处理、KPConv细化）对比，证明 SFCNet 从根本上解决问题的优势。
    - 分析了增加基线模型分辨率的效果，证明简单提升分辨率无法解决信息损失，反而降低性能。
    - 对 F2PS 的步长、视锥内最大点数、哈希表函数数量等关键参数进行敏感性分析，证明方法鲁棒。
    - 定性和定量的比较了 F2PS 与传统步长采样的效果，以及 F2PS 与 FPS 的速度对比。
    - 对小物体类别进行专项的 IoU 对比，突出方法优势。

### 6. 论文的主要结论与发现
- SFCNet 在两个主流数据集上超越了所有先前的**2D 投影式分割方法**，缩小了与 3D 体素方法的性能差距。
- 通过保留完整的几何结构，SFCNet 在**小物体**（如摩托车、行人、骑行者、树干、杆状物）上的分割精度得到了显著且一致的提升。
- 提出的 F2PS 采样方法能均匀高效地采样 3D 点云，保留关键信息，且计算效率高（线性复杂度）。
- 系统性地证明了从数据结构层面解决量化损失比后期补偿更为有效。

### 7. 优点
- **创新性强**：提出的球面视锥结构及其配套的 SFC 和 F2PS 操作，是一种根本性的解决方案，巧妙融合了 2D 投影的高效性和 3D 点云处理的完整性。
- **问题导向明确**：准确识别并有效解决了 2D 投影方法对小物体分割不利这一关键痛点。
- **内存与计算高效**：哈希表示避免了稠密张量的内存浪费；F2PS 将 FPS 的计算限定在局部视锥内，实现了 O(N) 的高效采样；整体推理速度满足实时要求。
- **无需额外后处理**：SFCNet 端到端地输出完整的点云预测，无需依赖 KNN 投票或额外的点网络细化模块。
- **实验扎实全面**：在两个大型数据集上进行了详尽的定量、定性、消融和对比分析，论证充分。

### 8. 不足与局限
- **感受野限制**：SFC 仅选取每个邻近视锥中的最近点进行卷积，这可能会限制网络的纹理感受野，导致在道路、停车场等**宽范围、大尺度类别**上的性能略低于部分方法。
- **结构依赖性强**：方法性能依赖于球面视锥结构，其有效性主要针对旋转式机械激光雷达产生的有序点云，对于其他类型（如固态激光雷达）点云的泛化能力有待验证。
- **未来工作**：论文指出，将球面视锥结构与具有更大感受野的架构（如 vision transformer 或 vision mamba）结合，是解决当前局限并进一步提升性能的潜在方向。同时可探索在弱监督、多模态及点云配准等任务上的应用。

（完）
