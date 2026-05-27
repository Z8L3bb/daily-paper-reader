---
title: "DH-Fusion: Depth-Aware Hybrid Feature Fusion for Multimodal 3D Object Detection"
title_zh: DH-Fusion：用于多模态三维物体检测的深度感知混合特征融合
authors: "Mingqian Ji, Jian Yang, Shanshan Zhang"
date: 2024-05-10
pdf: "https://openreview.net/pdf?id=gBOQ0ACqoO"
tags: ["query:lidar-d-det"]
score: 9.0
evidence: DH-Fusion引入深度感知混合特征融合用于LiDAR-相机三维物体检测，有效结合模态
tldr: 针对现有LiDAR-相机3D检测器在融合时忽视深度因素的问题，DH-Fusion首次揭示不同模态在不同深度下的作用差异，并提出深度感知混合特征融合策略，通过全局和局部深度编码动态调节多模态特征的权重，显著提升了鲁棒性和检测精度，在多个基准上达到最优。
source: NeurIPS-2024-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-gboq0acqoo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1283, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gboq0acqoo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gboq0acqoo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 474, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gboq0acqoo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gboq0acqoo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 584, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gboq0acqoo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 683, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gboq0acqoo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1297, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gboq0acqoo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1295, \"height\": 2234, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-gboq0acqoo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1149, \"height\": 706, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gboq0acqoo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gboq0acqoo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 449, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gboq0acqoo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 408, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gboq0acqoo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 327, \"height\": 135, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gboq0acqoo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 668, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gboq0acqoo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 554, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gboq0acqoo/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1004, \"height\": 915, \"label\": \"Table\"}]"
motivation: 现有LiDAR-相机融合方法在设计融合策略时忽略了深度因素的影响。
method: 提出深度感知混合特征融合策略，在全局和局部层面通过深度编码自适应调节点云和图像特征的融合权重。
result: 在多个多模态3D检测基准上取得了领先性能，验证了深度感知融合的有效性。
conclusion: 深度感知融合显著提升了多模态检测器的鲁棒性和精度，为传感器融合提供了新思路。
---

## Abstract
State-of-the-art LiDAR-camera 3D object detectors usually focus on feature fusion. However, they neglect the factor of depth while designing the fusion strategy. In this work, we for the first time point out that different modalities play different roles as depth varies via statistical analysis and visualization. Based on this finding, we propose a Depth-Aware Hybrid Feature Fusion (DH-Fusion) strategy that guides the weights of point cloud and RGB image modalities by introducing depth encoding at both global and local levels. Specifically, the Depth-Aware Global Feature Fusion (DGF) module adaptively adjusts the weights of image Bird's-Eye-View (BEV) features in multi-modal global features via depth encoding. Furthermore, to compensate for the information lost when transferring raw features to the BEV space, we propose a Depth-Aware Local Feature Fusion (DLF) module, which adaptively adjusts the weights of original voxel features and multi-view image features in multi-modal local features via depth encoding. Extensive experiments on the nuScenes dataset demonstrate that our DH-Fusion method surpasses previous state-of-the-art methods w.r.t. NDS. Moreover, our DH-Fusion is more robust to various kinds of corruptions, outperforming previous methods on nuScenes-C w.r.t. both NDS and mAP.

---

## 论文详细总结（自动生成）

好的，以下是基于您提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与研究动机

*   **核心问题**：当前最先进的激光雷达-相机（LiDAR-camera）多模态3D物体检测器在设计融合策略时，普遍忽略了一个关键因素——**深度（物体与传感器的距离）**。
*   **研究动机与背景**：
    *   单模态检测器（纯激光雷达或纯视觉）存在性能瓶颈：激光雷达点云稀疏，缺乏纹理语义信息；相机图像虽富含纹理，但缺乏精确的3D空间信息。
    *   作者首次通过统计和可视化分析揭示：**不同模态在不同深度区间扮演的角色存在显著差异**。
        *   **近距离（<10m）**：目标点云数量充足（平均每目标163.7个点），可准确表征物体形状，此时图像信息可能带来背景噪声干扰。
        *   **远距离（>40m）**：目标点云极度稀疏甚至缺失（平均不足0.4个点），此时完整的图像信息对于检测变得至关重要。
    *   基于此发现，论文旨在设计一种能根据深度动态调整两种模态融合权重的新策略。

### 2. 方法论核心：深度感知混合特征融合 (DH-Fusion)

*   **整体思想**：通过在**全局**和**局部**两个层面引入深度编码，来动态、自适应地调整激光雷达点云特征和RGB图像特征在融合时的权重。
*   **核心组件一：深度感知全局特征融合模块 (DGF)**
    *   **输入**：编码后的点云BEV特征和图像BEV特征。
    *   **深度编码**：首先构建一个深度矩阵 `M`，存储BEV空间每个位置的深度值（该位置到自车坐标系的欧氏距离）。然后将正弦和余弦位置编码应用于深度矩阵，生成深度编码 `De`。
    *   **动态加权融合**：使用一个全局融合Transformer。将深度编码与点云BEV特征相乘(作为调制)，生成注意力机制中的查询（Query, Q）；图像BEV特征作为键（Key, K）和值（Value, V）。通过交叉注意力机制，深度编码引导模型根据深度值自适应地调整图像特征的注意力权重。
*   **核心组件二：深度感知局部特征融合模块 (DLF)**
    *   **动机**：补偿原始特征转换到BEV空间时的信息损失。
    *   **流程**：
        1.  **局部特征筛选**：通过区域提议网络（RPN）从融合的BEV特征中生成3D候选框。将这些框分别投影到**原始体素特征**和**多视图图像特征**上，裁剪出包含更丰富细节的局部实例特征。
        2.  **动态加权融合**：使用一个局部融合Transformer。将深度编码与局部融合BEV特征相乘形成查询(Q)，分别查询局部体素特征(K, V)和局部图像特征(K, V)。通过两个交叉注意力模块，实现基于深度的多模态局部特征交互与增强。
        3.  **特征更新**：将增强后的局部实例特征更新回全局特征图的对应位置，从而得到最终的增强多模态全局特征，用于后续的解码和检测头预测。

### 3. 实验设计与评估方法

*   **数据集与场景**：
    *   **nuScenes**：主评估基准，包含1000个驾驶场景，提供32线激光雷达和6个环绕相机数据，共10个目标类别。用于和当前最优方法进行性能比较。
    *   **nuScenes-C**：鲁棒性基准，对nuScenes验证集施加27种、5个严重等级的损坏（如天气、传感器、运动、物体、对齐等层面），用于评估模型在各种数据损坏下的鲁棒性。
*   **评估指标**：
    *   **NDS (nuScenes detection score)**：nuScenes的综合评估指标，结合了目标平移、尺寸、方向、速度和属性等多维度误差。
    *   **mAP (mean Average Precision)**：平均精度均值。
*   **对比方法**：与多类别的SOTA多模态3D检测器进行了广泛比较，包括TransFusion、BEVFusion、ObjectFusion、SparseFusion、IS-Fusion、CMT、FUTR3D等。同时提供了轻量版(DH-Fusion-light)、基础版(DH-Fusion-base)和大型版(DH-Fusion-large)与使用不同图像骨干网络（如ResNet50, SwinTiny）的方法进行公平对比。

### 4. 资源与算力

*   **训练配置**：
    *   **硬件**：4块 NVIDIA 3090 RTX GPU。
    *   **批量大小**：8。
    *   **训练周期**：20个epochs。
    *   **框架**：基于PyTorch和MMDetection3D实现。
*   **测试配置**：在单块3090 RTX GPU上进行模型评估。

### 5. 实验数量与充分性分析

*   **主要实验对比（约20种方法，表1）**：在nuScenes验证集和测试集上，将3个版本的DH-Fusion与使用了不同骨干网络的SOTA方法进行了全面对比，比较主流，对比充分、公平。
*   **鲁棒性实验对比（表2）**：在nuScenes-C数据集上，与FUTR3D、TransFusion、BEVFusion等方法对比鲁棒性，分析了6种主要损坏类型下的性能，实验具有现实意义。
*   **消融实验**：
    *   **核心模块有效性（表3）**：通过逐步添加DGF和DLF模块到基线模型（BEVFusion）上，证明了每个模块的独立贡献。
    *   **深度编码有效性（表4）**：分别移除DGF和DLF中的深度编码，观察性能下降，验证了深度编码是关键设计。
    *   **融合操作影响（表5）**：比较了深度编码与特征进行“乘”、“加”、“拼接”三种操作的效果，证明了“乘”法操作最优。
*   **深入分析实验**：
    *   **不同深度区间性能（表7）**：将目标按深度分为近、中、远三组，分别评估性能，直接证明了方法在远距离检测上的显著优势。
    *   **多目标跟踪（表6）**：验证了高质量的检测框对下游跟踪任务的益处。
    *   **可视化分析**：提供了注意力权重随深度变化的曲线图和检测结果、BEV特征的可视化对比图，定性支撑了核心论点。
*   **总结**：实验设计**系统、全面且逻辑清晰**。从主基准对标，到鲁棒性考验，再到严谨的消融和深入分析，多维度、定量与定性相结合地验证了方法的有效性。

### 6. 主要结论与发现

*   **核心结论**：论文验证了“深度是影响多模态3D检测融合效果的关键因素”这一观点。
*   **最终效果**：提出的DH-Fusion方法通过在全局和局部特征融合阶段引入深度编码，能够动态调整模态重要性，最终在nuScenes数据集上取得了超越先前SOTA方法的NDS分数，并且在nuScenes-C数据损坏场景下展现出更强的鲁棒性。

### 7. 优点

*   **创新性视角**：首次系统性地分析并揭示了深度对多模态3D检测融合策略的影响，为后续研究提供了新洞见。
*   **精巧的方法设计**：深度感知的全局和局部“混合”融合策略，既能宏观建模场景，又能微观补偿细节，设计合理。
*   **可解释性强**：通过注意力权重与深度的关系曲线，直观展现了模型如何实现深度感知，增加了方法的可信度。
*   **实验严谨扎实**：实验覆盖了SOTA对比、鲁棒性测试、详尽消融和深度分析，证据链条完整。轻量版模型实现了较好的速度-精度平衡。

### 8. 不足与局限

*   **对模态缺失的敏感性**：论文在结论部分明确指出，其基于注意力机制的模态交互方式使得检测结果对某一模态的完全丢失较为敏感，这是未来需要探索改进的方向。
*   **代码未开源**：论文提交时尚未公开代码，尽管提供了详细实现细节，但代码的缺失可能影响其他研究者复现和在该基础上的改进。论文承诺接收后开源。
*   **数据场景单一**：评估主要在nuScenes数据集上进行，该数据集以城市驾驶为主。方法在高速公路、乡村或其他极端环境下的泛化能力未得到验证。
*   **应用限制性讨论不充分**：论文虽提示需在实际应用中准备应急预案以确保安全，但对模型在误检、漏检情况下的具体失效模式、公平性等议题未做深入探讨。

（完）
