---
title: "Learning the RoPEs: Better 2D and 3D Position Encodings with STRING"
title_zh: 学习RoPE：使用STRING实现更好的2D和3D位置编码
authors: "Connor Schenck, Isaac Reid, Mithun George Jacob, Alex Bewley, Joshua Ainslie, David Rendleman, Deepali Jain, Mohit Sharma, Kumar Avinava Dubey, Ayzaan Wahid, Sumeet Singh, René Wagner, Tianli Ding, Chuyuan Fu, Arunkumar Byravan, Jake Varley, Alexey A. Gritsenko, Matthias Minderer, Dmitry Kalashnikov, Jonathan Tompson, Vikas Sindhwani, Krzysztof Marcin Choromanski"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=XXFBqfwnUp"
tags: ["query:lidar-d-det"]
score: 4.0
evidence: 改进3D位置编码用于视觉Transformer，在RGB-D输入的三维目标检测中应用
tldr: 三维视觉任务中，Transformer的位置编码难以保持精确平移不变性，限制了3D场景理解性能。该文提出STRING位置编码，将旋转位置编码理论推广到任意维度，通过可分离结构实现平移不变性和高效计算。在RGB-D输入的开放词汇目标检测和机器人控制任务中，STRING显著提升模型性能。该方法为3D视觉Transformer提供了新编码范式，可进一步用于LiDAR点云的3D目标检测特征聚合。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1754, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 844, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1680, \"height\": 878, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 709, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 702, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 847, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 862, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1335, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1742, \"height\": 944, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1743, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1743, \"height\": 670, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1732, \"height\": 1411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xxfbqfwnup/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1765, \"height\": 874, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-xxfbqfwnup/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 839, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xxfbqfwnup/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xxfbqfwnup/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 879, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xxfbqfwnup/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xxfbqfwnup/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 846, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xxfbqfwnup/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 640, \"height\": 567, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xxfbqfwnup/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 850, \"height\": 336, \"label\": \"Table\"}]"
motivation: 现有位置编码缺乏精确平移不变性，尤其在高维3D空间中，限制机器人等应用。
method: 提出STRING，将旋转位置编码推广到任意维，通过可分离结构实现高效计算。
result: 在开放词汇目标检测和机器人控制中，STRING编码带来显著性能提升。
conclusion: 为3D Transformer提供了一种高效且理论完备的位置编码方法。
---

## Abstract
We introduce $\textbf{STRING}$: Separable Translationally Invariant Position Encodings. STRING extends Rotary Position Encodings, a recently proposed and widely used algorithm in large language models, via a unifying theoretical framework. Importantly, STRING still provides $\textbf{exact}$ translation invariance, including token coordinates of arbitrary dimensionality, whilst maintaining a low computational footprint. These properties are especially important in robotics, where efficient 3D token representation is key. 
We integrate STRING into Vision Transformers with RGB(-D) inputs (color plus optional depth), showing substantial gains, e.g. in open-vocabulary object detection and for robotics controllers.
We complement our experiments with a rigorous mathematical analysis, proving the universality of our methods. Videos of STRING-based robotics controllers can be found here: https://sites.google.com/view/string-robotics.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将使用中文，以 Markdown 形式，对给定论文进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**:
    *   位置编码是Transformer架构的关键组成部分，用于向模型注入Token的顺序或空间位置信息。
    *   传统的绝对位置编码泛化能力差，而相对位置编码虽好，但计算量大且不兼容线性注意力机制。
    *   旋转位置编码融合了二者的优点，具备**可分离性**和**平移不变性**，在大语言模型中广泛应用。但在二维（图像）和三维（机器人与空间数据）场景中，现有RoPE的扩展方法并非理论上最通用的平移不变形式。
    *   **核心问题**: 能否提出一个理论上更通用、保有平移不变性且计算高效的位置编码框架，以更好地处理多维（2D/3D）Token坐标，从而提升视觉Transformer在诸如图像理解和机器人操控等下游任务上的性能？

*   **整体含义**:
    *   本文的核心贡献是提出了 **STRING** 框架，它从李群理论出发，被证明是满足平移不变性、可分离性及矩阵乘法形式中最通用的位置编码方案。STRING将RoPE纳入其特例，并通过正交变换的视角，提供了更灵活、表达能力更强的编码方式，同时保持了低计算开销，尤其在3D机器人应用中展现出巨大潜力。

### 2. 论文提出的方法论

*   **核心思想**:
    *   STRING旨在通过可学习的矩阵乘法，修改查询和键向量，使得点积的变化仅依赖于Token间的**相对位置差（平移不变性）**，而非绝对位置。它将RoPE从预定义的二维旋转推广到由一组可学习的、反对称且可交换的生成元定义的更一般的正交变换。

*   **关键技术细节与公式**:
    *   **通用定义**:
        *   STRING将位置 $r_i \in \mathbb{R}^{d_c}$ 映射为一个 $d \times d$ 的正交矩阵 $R(r_i)$。
        *   其形式为：$R(r_i) = \exp\left(\sum_{k=1}^{d_c} L_k [r_i]_k\right)$，其中 $L_k$ 是一组可学习的、可交换的反对称生成元矩阵，$\exp(\cdot)$ 是矩阵指数运算。
    *   **理论证明**:
        *   **定理3.2** 证明了在连续可微且不改变零位置Token的弱假设下，STRING是满足 $R(r_i)^\top R(r_j) = R(r_j - r_i)$ 性质的最通用形式。
        *   **定理3.3** 证明了当 $L_k$ 取特定的块对角形式时，STRING即退化为标准的RoPE。
    *   **高效实现**:
        *   **定理3.4** 表明，任何STRING编码等价于在一个新基底下的RoPE：$R(r_i) = P \cdot \text{RoPE}(r_i) \cdot P^\top$，其中 $P$ 是一个可学习的正交矩阵。这意味着无需显式计算矩阵指数，只需学习一个正交矩阵 $P$ 即可。
        *   **Cayley-STRING**：将 $P$ 参数化为Cayley变换形式 $P = (I-S)(I+S)^{-1}$，$S$ 为可学习的反对称矩阵。通过求解线性方程组来高效计算。
        *   **Circulant-STRING**：将生成元 $L_k$ 限制为循环矩阵的反对称部分。利用快速傅里叶变换，可将编码计算复杂度降至 $O(d \log d)$，内存占用 $O(d)$。

### 3. 实验设计

*   **使用的数据集/场景**:
    *   **图像分类**: ImageNet2012, Places365。
    *   **图文检索**: 内部数据集WebLI的3D变体 (WebLI-3D), 包含6000万张带深度信息的图像-文本对。
    *   **2D开放词汇目标检测**: COCO, LVIS 基准数据集。
    *   **3D开放词汇目标检测**: 包含400万张合成室内场景RGB-D图像的自有数据集，带有SE(3)位姿和尺寸真值。
    *   **仿真机器人操控**: ALOHA Unleashed (ALOHA-sim) 环境，包含12项灵巧操作任务。
    *   **真实机器人操控**: 真实世界的ALOHA 2双臂机器人 (10项任务) 和KUKA工业级单臂机器人 (拾取任务及分布外测试)。

*   **对比方法**:
    *   **Baseline**: 使用标准绝对位置编码或无位置编码的Vision Transformer。
    *   **RoPE**: 标准的旋转位置编码。
    *   **RoPE-Mixed (RoPE-M)**: RoPE的一个改进变体。
    *   **STRING变体**: Circulant-STRING, Cayley-STRING。

### 4. 资源与算力

*   论文**未明确提及**训练所使用的具体GPU型号、数量或总训练时长。这在许多侧重于算法创新的研究论文中较为常见。

### 5. 实验数量与充分性

*   **实验数量**: 论文设计并执行了**广泛且大规模**的实验，覆盖了从标准视觉任务（分类、检索、2D检测）到复杂的3D检测和机器人操控（仿真与真实）的多个领域，共计超过5种不同的任务类型。
*   **充分性与公平性**:
    *   **充分性**: 实验设计非常充分。它不仅验证了STRING在常规视觉基准上的有效性，更重要的是在论文所强调的机器人和3D任务上进行了深入验证，包括开箱即用的检测和完整的操控策略训练，并进行了分布外鲁棒性测试。
    *   **公平性**: 对比公平。所有对比方法均基于相同的ViT骨干网络，调整仅限于位置编码模块。对于3D检测任务，甚至报告了3个随机种子的最佳结果以体现性能上限。

### 6. 论文的主要结论与发现

*   **性能卓越**: 在所有测试任务中，STRING（尤其是Cayley-STRING）在性能上都一致优于标准RoPE及其变体，以及不使用此类编码的基线模型。
    *   在ImageNet分类上，STRING模型绝对准确率提升超过1%。
    *   在COCO和LVIS的2D开放词汇检测任务上，Cayley-STRING取得了最高的平均精度。
    *   在3D目标检测上，STRING模型提供了更准确、更鲁棒的3D边界框预测。
    *   在ALOHA仿真机器人任务中，Cayley-STRING实现了最高的平均成功率和最快的收敛速度。
*   **3D应用的关键优势**: 通过直接将深度信息编码为Token的3D坐标，STRING能有效利用深度信号，在真实机器人任务中显著提升了策略的性能和鲁棒性。
*   **良好的泛化性与鲁棒性**: 在KUKA机器人的分布外测试中，3D STRING策略相比2D基线策略在面对光照变化、大型干扰物和桌面高度变化时表现出更强的鲁棒性。
*   **理论完备性**: 论文为STRING提供了严谨的数学证明，展示了其作为平移不变位置编码的一般形式的地位。

### 7. 优点

*   **理论创新**: 首次从李群理论出发，提出了位置编码的统一框架，并证明其最通用性，这是该领域的重要理论贡献。
*   **方法优雅且高效**: 通过定理3.4将复杂的矩阵指数运算简化为学习一个正交矩阵P，并提出了Cayley和Circulant两种高效实现，完美平衡了通用性和计算成本。Circulant-STRING甚至能达到 $O(d \log d)$ 的极低时间复杂度。
*   **实验全面扎实**: 验证范围从标准视觉任务跨越到复杂的真实机器人应用，充分证明了方法的实用价值和广泛适用性。特别是在机器人领域的深入应用，为3D感知与策略学习提供了强有力的新工具。
*   **兼容性强**: 可以与现有的预训练2D模型无缝集成，因为新增的关于深度（第三维）的参数是解耦的，这极大地便利了从2D向3D的迁移学习。

### 8. 不足与局限

*   **计算开销权衡**: 尽管提出了高效版本，但与零开销的RoPE相比，Cayley-STRING在训练时仍需 $O(d^3)$ 时间（可简化为求解线性系统），在资源极度受限的情况下可能仍是一个考量因素。
*   **旋转不变性局限**: 文中提到了将STRING推广到其他变换群（如旋转群）的思路，但并未进行实证验证。当前框架的核心优势仍在于**平移**不变性。
*   **实验细节缺失**: 未能提供关键的算力消耗指标，使得复现成本难以评估。
*   **机器人实验的可复现性风险**: 真实机器人实验通常涉及复杂的硬件和软件栈，论文虽提供了视频，但完全的实验复现依然面临较大挑战，其性能增益可能依赖于特定的系统设置。

（完）
