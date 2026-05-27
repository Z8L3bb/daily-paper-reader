---
title: "LION: Linear Group RNN for 3D Object Detection in Point Clouds"
title_zh: LION：面向点云3D目标检测的线性分组RNN
authors: "Zhe Liu, Jinghua Hou, Xinyu Wang, Xiaoqing Ye, Jingdong Wang, Hengshuang Zhao, Xiang Bai"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=5tGkAcY7uV"
tags: ["query:stage-d-det"]
score: 8.0
evidence: 用于点云3D目标检测的线性分组RNN
tldr: 针对Transformer在稀疏点云中建模长程关系计算开销大，提出基于窗口的线性分组RNN检测器LION。通过大分组内特征交互，实现高效准确的三维目标检测。实验证明LION在精度和效率上均优于主流方法。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-5tgkacy7uv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1428, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5tgkacy7uv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5tgkacy7uv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1355, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5tgkacy7uv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5tgkacy7uv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 436, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5tgkacy7uv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 873, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5tgkacy7uv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1437, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5tgkacy7uv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 431, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 608, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1448, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1438, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1435, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1438, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1440, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1445, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5tgkacy7uv/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1442, \"height\": 718, \"label\": \"Table\"}]"
motivation: Transformer在稀疏点云检测中面临平方复杂度，限制了实用。
method: 提出LION，采用线性分组RNN在窗口内实现大范围特征交互，提升效率。
result: 在多个点云检测基准上取得领先的精度与速度权衡。
conclusion: 线性RNN为稀疏三维检测提供了有效的长程建模替代方案。
---

## Abstract
The benefit of transformers in large-scale 3D point cloud perception tasks, such as 3D object detection, is limited by their quadratic computation cost when modeling long-range relationships. In contrast, linear RNNs have low computational complexity and are suitable for long-range modeling. Toward this goal, we propose a simple and effective window-based framework built on Linear group RNN (i.e., perform linear RNN for grouped features) for accurate 3D object detection, called LION. The key property is to allow sufficient feature interaction in a much larger group than transformer-based methods. However, effectively applying linear group RNN to 3D object detection in highly sparse point clouds is not trivial due to its limitation in handling spatial modeling. To tackle this problem, we simply introduce a 3D spatial feature descriptor and integrate it into the linear group RNN operators to enhance their spatial features rather than blindly increasing the number of scanning orders for voxel features. To further address the challenge in highly sparse point clouds, we propose a 3D voxel generation strategy to densify foreground features thanks to linear group RNN as a natural property of auto-regressive models. 
Extensive experiments verify the effectiveness of the proposed components and the generalization of our LION on different linear group RNN operators including Mamba, RWKV, and RetNet. Furthermore, it is worth mentioning that our LION-Mamba achieves state-of-the-art on Waymo, nuScenes, Argoverse V2, and ONCE datasets. Last but not least, our method supports kinds of advanced linear RNN operators (e.g., RetNet, RWKV, Mamba, xLSTM and TTT) on small but popular KITTI dataset for a quick experience with our linear RNN-based framework.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：在大型3D点云的目标检测任务中，基于Transformer的方法在建模长距离关系时计算复杂度呈平方级增长，导致计算成本高昂，限制了其在大规模场景中的应用，使其通常只能在小范围的分组内进行特征交互。
*   **整体含义**：为了克服Transformer的局限性，本文提出将线性复杂度的循环神经网络（RNN）引入3D目标检测，旨在以更低的计算成本实现更广泛、更有效的长距离特征交互，从而提升检测性能。

### 2. 论文提出的方法论

论文的核心方法是构建了一个名为 **LION**（**LI**near gr**O**up R**N**N）的3D检测框架，其主要技术细节如下：

*   **核心思想：基于线性分组RNN的窗口框架**
    *   将点云划分为不重叠的3D窗口，并在每个窗口内将体素特征排序并分割为**大尺寸的等大小组**。
    *   利用线性RNN算子（如Mamba）在大型组内执行特征交互，以线性复杂度实现长距离关系建模，突破了Transformer因平方复杂度而受限的分组大小。

*   **关键技术细节**
    *   **LION层**：一个LION层包含两个线性分组RNN算子，分别沿X轴和Y轴两种窗口划分方式执行长距离特征交互，以获得更充分的信息交流。
    *   **3D空间特征描述符**：为解决将体素展平为1D序列时造成的3D空间信息丢失问题，引入了一个由“3D子流形卷积 + LayerNorm + GELU激活函数”组成的描述符。该描述符被集成到线性分组RNN中，为其提供丰富的局部3D空间位置信息，而非简单地增加扫描次序。
    *   **体素生成策略**：为了解决稀疏点云中前景特征不足的问题，利用线性RNN的自回归特性进行体素生成。
        1.  **无监督前景区分**：计算特征图沿通道维度的高响应值，并选取`Top-m`个体素作为前景区域，无需额外监督分支。
        2.  **自回归体素生成**：对选定的前景体素坐标施加四个方向的偏移（`[-1,-1,0], [1,1,0], [1,-1,0], [-1,1,0]`）来扩散体素，新体素特征初始化为零。然后，将这些初始化特征与原始特征拼接，送入后续的LION块中，利用其自回归能力生成具有判别力的扩散特征。
            *   生成过程可形式化为：
                `Fp = Fi ⊕ 所有偏移方向的初始化特征`
                接下来的LION块处理：`F'p = Block(Fp)`

### 3. 实验设计

*   **数据集与场景**：在四个大规模自动驾驶数据集上进行了评估，覆盖了不同的感知范围和场景。
    *   **Waymo Open Dataset (WOD)**：大型户外场景，感知范围为`150m × 150m`。
    *   **nuScenes**：流行户外场景，感知范围达50米。
    *   **Argoverse V2**：长距离户外场景，感知范围达200米。
    *   **ONCE**：代表性自动驾驶场景。
    *   **KITTI**：小规模但经典的自动驾驶数据集，用于快速验证多种RNN算子的泛化性。
*   **评估指标**：
    *   **WOD**: 3D均值平均精度（mAP）和按航向角加权的mAP（mAPH），均按L1和L2难度级别评估。
    *   **nuScenes, Argoverse V2**: mAP和nuScenes检测分数（NDS）。
    *   **ONCE, KITTI**: mAP。
*   **对比方法**：与多类代表性方法进行了广泛对比，包括：
    *   传统基于体素/点的方法：SECOND， PointPillars， CenterPoint， PV-RCNN， HEDNet等。
    *   基于Transformer的方法：DSVT-Voxel， DSVT-Pillar， SWFormer， SST等。
    *   其他先进方法：FSD， SAFDNet， VoxelNext等。

### 4. 资源与算力

*   论文明确提到在**Waymo开放数据集**上训练模型的资源使用情况：
    *   **GPU型号与数量**：8块 NVIDIA Tesla V100 GPU。
    *   **训练时长**：训练了24个周期（epochs）。
    *   **批量大小**：16。

### 5. 实验数量与充分性

*   **实验数量**：论文进行了大量的实验，主要包括：
    *   **4个大型数据集的主要结果对比**：在Waymo, nuScenes, Argoverse V2, ONCE上与SOTA方法进行全面比较。
    *   **2个数据集的泛化性验证**：在KITTI和ONCE上验证了对多种线性RNN算子(Mamba, RWKV, RetNet, xLSTM, TTT)的支持。
    *   **消融实验**：针对LION的三大核心组件（大分组、3D空间特征描述符、体素生成）分别进行了有效性验证。
    *   **子组件细节实验**：对空间特征描述符的放置位置、体素生成的前景比例`r`、窗口与分组大小等进行了详细的对比分析。
    *   **效率与成本分析**：对比了LION与Transformer方法(DSVT)的计算量(FLOPs)、参数量(Params)和延迟(Latency)。
*   **充分性与公平性**：实验设计非常充分且公平。
    *   **数据集多样**：覆盖了多个主流且具有挑战性的自动驾驶基准。
    *   **对比对象广泛**：包含了各时期的SOTA方法，并遵循公平对比原则（如相同的检测头、数据增强）。
    *   **消融充分**：系统性拆解了各个模块的贡献。
    *   **多维验证**：不仅评估精度，还提供了效率分析和架构泛化性验证。

### 6. 论文的主要结论与发现

*   **LION框架的有效性**：基于线性分组RNN的LION框架能够有效地在3D点云中进行长距离特征交互，在多个数据集上超越基于Transformer和卷积的SOTA方法，尤其在LION-Mamba模型上取得了最佳性能。
*   **各组件的贡献**：
    *   **大分组设计**是性能提升的关键，使得长距离关系建模成为可能。
    *   **3D空间特征描述符**有效补偿了线性RNN在处理局部空间信息方面的不足，对小物体（如行人）的提升尤为明显。
    *   **体素生成策略**通过自回归方式增强了稀疏点云中的前景特征表示，显著提升了检测精度。
*   **优秀的泛化能力**：LION框架是一个通用的架构，能够无缝集成多种先进的线性RNN算子（Mamba、RWKV、RetNet等），并均能取得有竞争力的结果。

### 7. 优点

*   **方法新颖**：成功将线性复杂度的RNN引入3D点云检测，解决了Transformer计算成本高的固有问题。
*   **设计优雅**：通过3D空间描述符和自回归体素生成，巧妙地解决了线性RNN在稀疏3D数据上的适应性难题，结构简洁高效。
*   **性能优越**：在多个权威数据集上取得SOTA，并且比同等性能的Transformer方法计算成本和参数量更低。
*   **实验扎实**：实验设计全面、系统，不仅有SOTA对比，还有详尽的消融实验、效率分析和泛化性验证，说服力强。

### 8. 不足与局限

*   **推理延迟**：尽管计算量和参数量有优势，但LION在推理阶段的延迟（146.2ms）略高于其对比的Transformer方法DSVT-Voxel（136.7ms），说明其在实际应用中仍有优化空间。
*   **远距离点云稀疏**：即便性能优越，论文可视化结果也表明，LION在距离较远且点云极度稀疏的区域仍存在漏检情况。
*   **算力要求**：论文指出其运行速度对硬件有较高要求，这可能在资源受限的平台（如某些边缘计算设备）上构成应用限制。

（完）
