---
title: "Towards Flexible 3D Perception: Object-Centric Occupancy Completion Augments 3D Object Detection"
title_zh: 面向灵活3D感知：以对象为中心的占用补全增强3D目标检测
authors: "Chaoda Zheng, Feng Wang, Naiyan Wang, Shuguang Cui, Zhen Li"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=yktQNqtepd"
tags: ["query:stage-d-det"]
score: 9.0
evidence: 以对象为中心的占用补全增强3D目标检测
tldr: 针对3D边界框无法表达物体精确几何的问题，提出以对象为中心的占用栅格表示，作为边界框的补充，在高分辨率下捕获物体细节，从而增强3D检测性能，并在实际应用中可行。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 714, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 653, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 684, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1304, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 663, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1374, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1440, \"height\": 816, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1437, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1432, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1412, \"height\": 750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1300, \"height\": 1014, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yktqnqtepd/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1293, \"height\": 443, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-yktqnqtepd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 733, \"height\": 483, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yktqnqtepd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 738, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yktqnqtepd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1170, \"height\": 1060, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yktqnqtepd/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 737, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yktqnqtepd/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 739, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yktqnqtepd/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 738, \"height\": 168, \"label\": \"Table\"}]"
motivation: 3D边界框缺乏对物体内在几何的精确描述，占用栅格计算量大。
method: 引入以对象为中心的占用表示，与边界框互补，允许更高体素分辨率。
result: 在3D目标检测任务中，检测精度得到显著提升。
conclusion: 该表示方式灵活且有效，为3D感知提供了更丰富的几何信息。
---

## Abstract
While 3D object bounding box (bbox) representation has been widely used in autonomous driving perception, it lacks the ability to capture the precise details of an object's intrinsic geometry. Recently, occupancy has emerged as a promising alternative for 3D scene perception. However, constructing a high-resolution occupancy map remains infeasible for large scenes due to computational constraints. Recognizing that foreground objects only occupy a small portion of the scene, we introduce object-centric occupancy as a supplement to object bboxes. This representation not only provides intricate details for detected objects but also enables higher voxel resolution in practical applications. We advance the development of object-centric occupancy perception from both data and algorithm perspectives. On the data side, we construct the first object-centric occupancy dataset from scratch using an automated pipeline. From the algorithmic standpoint, we introduce a novel object-centric occupancy completion network equipped with an implicit shape decoder that manages dynamic-size occupancy generation. This network accurately predicts the complete object-centric occupancy volume for inaccurate object proposals by leveraging temporal information from long sequences. Our method demonstrates robust performance in completing object shapes under noisy detection and tracking conditions. Additionally, we show that our occupancy features significantly enhance the detection results of state-of-the-art 3D object detectors, especially for incomplete or distant objects in the Waymo Open Dataset.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **核心问题**：在自动驾驶感知中，传统的3D目标边界框（Bounding Box）虽然被广泛使用，但其本质是一个长方体，无法精确描述不规则物体的几何形状。这会导致将边界框内未被占用的空间也错误地标记为“占用”，从而影响下游规划与控制任务的精度。
*   **研究动机**：虽然3D占用网格（Occupancy）能更精细地表示场景，但构建整个大场景的高分辨率占用图因计算成本过高而难以实际应用。鉴于前景目标仅占场景的一小部分，本文提出**以对象为中心的占用表示**，作为边界框的补充，旨在用更高的体素分辨率捕获单个目标的精细几何结构。
*   **整体含义**：这项工作旨在推动感知表示从粗略的边界框向更精细的占用描述演进，通过同时提供目标边界框和内部精细占用信息，实现更灵活、更准确的3D感知，从而提升自动驾驶系统的安全性与鲁棒性。

### 2. 论文提出的方法论

*   **核心思想**：将占用预测的重点从整个场景转移到单个前景对象上。通过一个序列级占用补全网络，利用长时序的激光雷达点云和带噪声的检测跟踪结果，为每个目标生成完整的、高分辨率的对象中心占用体，并同时优化其边界框。
*   **关键技术细节与算法流程**：
    *   **输入**：一个由离线3D检测器和跟踪器生成的对象轨迹序列，包含各时刻的点云和带噪声的边界框。
    *   **双分支感兴趣区域编码**：
        *   **局部分支**：将点云转换至以各自边界框为中心的规范坐标系下，用类似PointNet的网络提取局部几何特征。
        *   **全局分支**：直接在全局坐标系下编码，以保留目标的运动动态信息，有助于处理检测漂移。
    *   **时序信息聚合**：使用一个**因果Transformer（Causal Transformer）**对全局分支的特征进行时序建模，确保在线应用时不泄露未来信息。然后将增强后的全局特征与局部几何特征融合，形成最终的形状隐编码。
    *   **动态尺寸占用生成（隐式形状解码器）**：为处理不同尺寸的目标，采用**隐式神经表示（Implicit Neural Representation）**。一个MLP解码器接收`（形状隐编码, 查询点坐标）`作为输入，输出该点的占用概率，从而避免了传统3D卷积对固定尺寸特征图的需求。
        *   `p = D(z, q)`，其中 `z` 是形状隐编码，`q` 是查询点。
    *   **输出**：
        *   **占用补全**：通过在不同位置查询隐式解码器，生成完整的对象中心占用体。
        *   **检测优化**：将融合后的形状隐编码与全局特征再次整合，送入检测头，优化原有的边界框和置信度。

### 3. 实验设计

*   **数据集与场景**：实验主要在**Waymo Open Dataset (WOD)** 上进行，专注于**车辆**这一类刚体对象。
*   **对象中心占用数据集构建**：提出了一套自动化的标注流程，基于WOD的激光雷达点云和3D边界框标注，聚合多帧点云并进行遮挡推理，自动为每个目标实例生成对象中心占用网格的真值。
*   **评估基准**：
    *   **占用补全**：使用**交并比（IoU）** 作为主要指标，评估预测占用体与真值占用体的一致性。
    *   **3D检测**：采用WOD官方的**平均精度（AP）** 和**加权平均精度（APH）** 指标，并按照距离和点云稀疏度（LEVEL 1/2）进行了细分评估。
*   **对比方法**：
    *   **占用补全对比**：与直接聚合历史点云并体素化的基线方法对比，并分别使用了GT轨迹、CenterPoint轨迹、FSD轨迹等多种质量的输入。
    *   **3D检测对比**：将本方法应用于CenterPoint、FSD等主流检测器，并与它们的基线版本以及使用了长时序信息的先进方法（如MoDAR、MPPNet、3D-MAN）进行对比。

### 4. 资源与算力

*   **训练资源**：模型使用**PyTorch**实现，在**8块NVIDIA 3090 GPU**上进行训练。
*   **训练配置**：使用Adam优化器，初始学习率为1e-4，批次大小为8。采用余弦退火学习率策略，总共训练24个轮次。
*   **模型效率分析**：论文提到了理论推理成本。对于一个标准化的32帧输入、查询4096个点，形状解码器额外增加的推理时间约**0.15毫秒**，显存开销约**66MB**，表明其计算效率很高。

### 5. 实验数量与充分性

*   **实验数量**：论文设计了较为丰富的实验，包括：
    *   **主要任务实验**：占用补全（表1）和3D目标检测（表2）的结果对比。
    *   **鲁棒性分析**：对GT轨迹添加噪声（表1）和不同距离下的检测性能分析（表3）。
    *   **模型分析**：单分支vs双分支、显式vs隐式占用、有无占用解码器的消融实验（表4）。
    *   **时序长度分析**：不同训练和测试序列长度对性能的影响（表5）。
    *   **泛化性验证**：直接将在FSD轨迹上训练的模型应用到FSDv2轨迹上的效果（表1）。
*   **充分性评估**：实验设计**较为充分且客观**。它不仅对比了最终性能，还深入分析了模型各个组件的贡献、对输入噪声的鲁棒性、对不同距离目标的增益以及模型对未见检测器的泛化能力。对比方法涵盖了当时最先进的在线和离线检测器，实验结论有强有力的数据支撑。

### 6. 论文的主要结论与发现

*   **对象中心占用表示是有效的**：相较于直接聚合点云，本方法能有效处理检测噪声和轨迹不准确问题，鲁棒地补全目标形状。
*   **占用信息能提升3D检测精度**：学习到的细粒度形状信息可以反哺检测任务，显著提升SOTA检测器的性能，尤其是在处理远距离和不完整目标时增益更大。
*   **双重坐标系编码的必要性**：融合局部几何和全局运动信息的双分支设计，对于同时完成形状补全和检测优化至关重要。
*   **隐式解码的优势**：隐式形状解码器不仅实现了动态尺寸的占用生成，还具备外推能力（预测边界框外的占用），并允许占用补全和检测任务进行端到端联合训练。

### 7. 优点

*   **新颖的感知表示**：创造性地提出了“对象中心占用”这一概念，巧妙地平衡了几何精度和计算成本，是对现有纯边界框或全场景占用方案的有益补充。
*   **方法设计精巧**：双分支编码、因果Transformer与隐式解码器的组合，有效地解决了长序列建模、动态尺寸输出和多任务联合学习等技术挑战。
*   **端到端多任务框架**：将占用补全和检测优化统一在一个框架下，两个任务相互促进，展现了优雅的设计思路。
*   **强鲁棒性和泛化能力**：方法对输入噪声、不同质量的轨迹提案以及新的检测器都表现出很好的鲁棒性和泛化性，具备较高的实用价值。
*   **高质量的数据贡献**：提供了首个自动化构建的对象中心占用数据集及其生成流程，为未来研究奠定了基础。

### 8. 不足与局限

*   **刚体假设**：数据集的自动标注流程基于刚体假设（目标形状不随时间改变），这使其难以精确评估行人和骑行者等可形变对象，当前的实验也因此局限于车辆类别。
*   **依赖上游模块**：方法的性能严重依赖于上游的检测器和跟踪器，虽然表现出鲁棒性，但上游模块的严重失效仍会影响最终效果。
*   **占用分辨率与渲染质量的权衡**：采用的0.2m体素分辨率对自动驾驶下游任务足够，但不足以支撑高精度的三维表面渲染，可能限制了其在需要精细网格的应用中的推广。
*   **实验对象单一**：所有实验都在车辆这一类别上进行，缺少对其他交通参与者（如行人、骑行者）的定量评估，无法完全揭示方法对非刚体目标的处理能力。

（完）
