---
title: Steerable Transformers for Volumetric Data
title_zh: 用于体积数据的可操控变压器
authors: "Soumyabrata Kundu, Risi Kondor"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Ax550Vokon"
tags: ["query:lidar-d-det"]
score: 7.0
evidence: 用于体积数据的等变注意力机制，可用于点云特征聚合
tldr: 提出可操控变压器，通过将SE(d)等变注意力机制引入视觉变压器，适用于三维体积数据。该等变注意力在傅里叶空间中对可操控卷积特征进行操作，提升了二维和三维任务性能。该模块可作为3D点云特征聚合的通用注意力方法，为点云处理带来新的设计范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ax550vokon/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1306, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ax550vokon/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1006, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ax550vokon/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1130, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ax550vokon/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1078, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ax550vokon/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 481, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ax550vokon/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1022, \"height\": 811, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ax550vokon/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1464, \"height\": 924, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ax550vokon/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1277, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ax550vokon/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1026, \"height\": 546, \"label\": \"Table\"}]"
motivation: 现有视觉变压器缺乏对三维数据旋转等变的处理能力，限制了其在体积数据上的应用。
method: 提出可操控变压器，通过等变注意力机制在傅里叶空间处理可操控卷积特征，实现SE(d)等变性。
result: 在二维和三维实验上验证，叠加可操控变压器层能提升可操控卷积网络的性能。
conclusion: 该方法为三维点云和体积数据提供了等变注意力模块，增强了模型对几何变换的鲁棒性。
---

## Abstract
We introduce Steerable Transformers, an extension of the Vision Transformer mechanism that maintains equivariance to the special Euclidean group $\mathrm{SE}(d)$. We propose an equivariant attention mechanism that operates on features extracted by steerable convolutions. Operating in Fourier space, our network utilizes Fourier space non-linearities. Our experiments in both two and three dimensions show that adding steerable transformer layers to steerable convolutional networks enhances performance.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究动机**：视觉 Transformer 在图像任务中表现出色，但标准自注意力机制会破坏对旋转、平移等几何变换的等变性。可操控卷积（steerable convolutions）擅长在傅里叶空间中提取局部等变特征，却难以捕捉全局依赖关系。
- **核心问题**：如何将 Transformer 的自注意力机制融入等变神经网络，使模型在保持对 Special Euclidean 群 $\mathrm{SE}(d)$ 等变的同时，兼具全局上下文建模能力，并可用于二维与三维体积数据。
- **整体含义**：提出“可操控 Transformer”（Steerable Transformers），作为可操控卷积网络的增强模块，在傅里叶空间中实现等变注意力，提升下游任务性能。

### 2. 方法论
- **整体架构**：采用混合设计，以可操控卷积编码器提取局部等变特征图，随后接入可操控 Transformer 层，最后通过全局池化与全连接层输出。该结构可灵活替换为 U‑Net 等分割网络中的瓶颈模块。
- **可操控自注意力机制**：
  - 输入来自可操控卷积的输出，按不可约表示（irrep）分组，形如 $f_{\text{in}}(\mathbf{x},\rho)\in\mathbb{C}^{d_\rho\times d_{\text{model}}}$。
  - 查询、键、值由可学习的权重矩阵生成，并加入**可操控位置编码** $\mathbf{P}^{(\rho)}(\mathbf{x}, \mathbf{y})$。
  - 注意力分数为各表示下的缩放点积之和，取模后经 softmax 得到注意力权重，输出为值向量的加权和。
  - 定理 1 证明：当且仅当 $\mathbf{P}^{(\rho)}(\mathbf{Rx}+\mathbf{t}, \mathbf{Ry}+\mathbf{t}) = \rho(\mathbf{R}) \mathbf{P}^{(\rho)}(\mathbf{x}, \mathbf{y})$ 时，整个注意力模块保持 $\mathrm{SE}(d)$ 等变性。
- **可操控位置编码**：
  - 满足等变条件的自然选择是球谐函数：2D 为 $P^{(k)}(\mathbf{x}) = \phi(r,k)e^{ik\theta}$，3D 为 $\mathbf{P}^{(\ell)}(\mathbf{x}) = \phi(r,\ell)\mathbf{Y}^{(\ell)}(\theta,\phi)$。
  - 径向调制函数采用 $\phi(r,\rho) = w_\rho r^{-2}\mathbf{1}_{r>0}$，其中 $w_\rho$ 为可学习标量，使得邻近点获得更高权重。
- **等变 MLP 与归一化**：
  - MLP 线性层仅混合各不可约表示的通道，不破坏等变性。
  - 非线性激活采用基于范数的傅里叶空间非线性（对特征向量范数施加 ReLU）。
  - 层归一化利用傅里叶变换保持 $L_2$ 范数的性质，在空间位置上对各表示的总范数进行归一化。
- **计算复杂度**：可操控自注意力的复杂度与可操控卷积在同一量级，均为 $O(N d_\rho^2 C^2)$（忽略核尺寸），额外开销可控。

### 3. 实验设计
- **数据集**：
  - 二维分类：Rotated MNIST（12k 训练 / 50k 测试，28×28 灰度随机旋转图像）。
  - 三维分类：ModelNet10（10 类 CAD 模型，3991 训练 / 908 测试；点云体素化后施加随机旋转，生成 z‑旋转与 $\mathrm{SO}(3)$ 旋转两个变体）。
  - 二维分割：PH2（200 张皮肤镜图像，100/50/50 训练/验证/测试，二值掩膜分割）。
  - 三维分割：BraTS（脑肿瘤 MRI，4 模态，240×240×155，训练/验证/测试 243/96/145，分割增强肿瘤、肿瘤核心、全肿瘤三个区域）。
- **基准与对比方法**：
  - 主要基线：相同架构下仅使用可操控卷积（无 Transformer 层）的模型。
  - 外部对比（分类）：Harmonic Net、P4CNN、E(2)‑CNN、α‑R4 CNN、GSA‑Nets、GE‑ViT 等；在 ModelNet10 上还与 3D ShapeNets、VoxNet、CubeNet 等对比。
  - 在 Rotated MNIST 和 ModelNet10 上还报告了注意力方法的比较。

### 4. 资源与算力
- **GPU 型号**：文中仅提及使用单块 **16 GB 显存的 GPU**，未注明具体型号（推测为 NVIDIA V100 或同级别）。
- **训练时长**：
  - Rotated MNIST（最大模型 k=8）：约 **4 小时**。
  - ModelNet10（可操控 Transformer）：约 **12 小时**。
  - PH2 分割：约 **2 小时**。
  - BraTS 分割（最大模型）：约 **40 小时**。
- **其他资源限制**：因显存不足，无法使用更大的批次大小（BraTS 和 PH2 使用 batch size = 1）或更高的傅里叶截断频率，导致模型容量受限。

### 5. 实验数量与充分性
- **实验组数**：
  - 在 4 个数据集上进行了评估，每个数据集包含 2～4 种频率截断设置（如 2D 的 $k=4,8$；3D 的 $\ell=2,3$），每组均与纯卷积基线对比（见表 1）。
  - 在 Rotated MNIST 和 ModelNet10 上提供了与其他文献方法的数值对比（见表 2、表 3）。
  - 定性结果展示了注意力图以及分割样本的可视化。
- **充分性与公平性**：
  - 对比内部基线时保持架构一致，仅在瓶颈模块中插入 Transformer，公平性较好。
  - 与外部方法对比时，不同工作的训练策略（如数据增强）存在差异，论文中对此进行了说明（例如 ModelNet10 上其他方法使用了训练时增强，而本工作仅在测试时增强），对比相对客观。
  - 缺乏对 Transformer 深度、头数、位置编码形式的消融实验，深度和表征能力的相关性未充分探究。但考虑到显存瓶颈，现有实验组合仍具有一定说服力。

### 6. 主要结论与发现
- 在可操控卷积网络中加入可操控 Transformer 层，能够在所有测试的二维与三维分类、分割任务中一致地提升性能（例如 Rotated MNIST 错误率降至 1.18%，ModelNet10 准确率最高 90.40%，BraTS 全肿瘤 Dice 从 74.43% 提升至 76.37%）。
- 该方法优于纯注意力架构（如 GSA‑Nets、GE‑ViT），表明“卷积 + Transformer”的混合设计更有效。
- 可操控位置编码与等变自注意力机制成功保持了 $\mathrm{SE}(d)$ 等变性，验证了定理 1 的理论条件。

### 7. 优点
- **新颖的等变注意力**：首次在傅里叶空间中为体积数据设计 $\mathrm{SE}(d)$ 等变的自注意力模块，理论证明完备。
- **通用性强**：可即插即用地附加到已有的可操控卷积网络中，用于分类、分割等多种任务，2D 和 3D 均适用。
- **性能提升明确**：在多种模态和分辨率下均有稳定提升，参数增加不多（甚至在某些设置下参数更少）。
- **开源可复现**：提供代码仓库，实验细节（优化器、学习率衰减等）描述清晰。

### 8. 不足与局限
- **计算开销与显存瓶颈**：自注意力在高分辨率输入上导致显存占用极大，迫使 batch size = 1 和较低的频率截断，限制了模型规模与性能上界。
- **频率截断受限**：因资源限制仅使用 $k=8$（2D）或 $\ell=3$（3D），相比其他 steerable 工作（如使用 $k=16$）存在差距，未能充分发挥等变表示能力。
- **消融分析不足**：未探讨 Transformer 层数、注意力头数、位置编码中的径向函数选择、归一化位置等对性能的影响。
- **依赖卷积先验**：提出的 Transformer 并非“纯注意力”等变架构，仍需依赖可操控卷积编码器，初始化与前端设计敏感性未评估。
- **数据规模偏小**：测试数据集规模有限，未在大规模 3D 场景（如 ShapeNet 全量、医学影像多中心数据）上验证。

（完）
