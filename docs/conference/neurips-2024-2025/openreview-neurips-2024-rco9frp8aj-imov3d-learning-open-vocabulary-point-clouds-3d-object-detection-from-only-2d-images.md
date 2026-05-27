---
title: "ImOV3D: Learning Open Vocabulary Point  Clouds 3D Object Detection from Only 2D Images"
title_zh: ImOV3D：仅从2D图像学习开放词汇点云3D目标检测
authors: "Timing Yang, Yuanliang Ju, Li Yi"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=RCO9fRP8AJ"
tags: ["query:stage-d-det"]
score: 6.0
evidence: 从2D图像学习的开放词汇点云3D检测
tldr: 为解决3D检测标注稀缺问题，提出ImOV3D仅用2D图像训练开放词汇点云3D检测器。通过跨模态知识迁移，在测试时直接处理点云，实现新类别的泛化。实验表明该方法能有效利用丰富的2D标注，降低3D检测的标注成本。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-rco9frp8aj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rco9frp8aj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rco9frp8aj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rco9frp8aj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rco9frp8aj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rco9frp8aj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1432, \"height\": 698, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rco9frp8aj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1163, \"height\": 915, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rco9frp8aj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1440, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rco9frp8aj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1422, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rco9frp8aj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1436, \"height\": 870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-rco9frp8aj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1428, \"height\": 816, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1165, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 740, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1254, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1237, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1088, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 882, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-rco9frp8aj/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1242, \"height\": 374, \"label\": \"Table\"}]"
motivation: 3D目标检测标注昂贵，2D图像标注丰富但模态不同。
method: 提出ImOV3D框架，利用2D图像中的开放词汇知识训练点云检测器。
result: 在开放词汇设置下取得有竞争力的性能，减少了对3D标注的依赖。
conclusion: 为低成本、可扩展的3D检测系统提供了新路径。
---

## Abstract
Open-vocabulary 3D object detection (OV-3Det) aims to generalize beyond the limited number of base categories labeled during the training phase. The biggest bottleneck is the scarcity of annotated 3D data, whereas 2D image datasets are abundant and richly annotated. Consequently, it is intuitive to leverage the wealth of annotations in 2D images to alleviate the inherent data scarcity in OV-3Det. In this paper, we push the task setup to its limits by exploring the potential of using solely 2D images to learn OV-3Det. The major challenges for this setup is the modality gap between training images and testing point clouds, which prevents effective integration of 2D knowledge into OV-3Det. To address this challenge, we propose a novel framework ImOV3D to leverage pseudo multimodal representation containing both images and point clouds (PC) to close the modality gap. The key of ImOV3D lies in flexible modality conversion where 2D images can be lifted into 3D using monocular depth estimation and can also be derived from 3D scenes through rendering. This allows unifying both training images and testing point clouds into a common image-PC representation, encompassing a wealth of 2D semantic information and also incorporating the depth and structural characteristics of 3D spatial data. We carefully conduct such conversion to minimize the domain gap between training and test cases. Extensive experiments on two benchmark datasets, SUNRGBD and ScanNet, show that ImOV3D significantly outperforms existing methods, even in the absence of ground truth 3D training data. With the inclusion of a minimal amount of real 3D data for fine-tuning, the performance also significantly surpasses previous state-of-the-art. Codes and pre-trained models are released on the  https://github.com/yangtiming/ImOV3D.

---

## 论文详细总结（自动生成）

好的，以下是针对论文《ImOV3D: Learning Open-Vocabulary Point Clouds 3D Object Detection from Only 2D Images》的结构化深度总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：论文旨在解决**开放词汇3D目标检测（OV-3Det）** 任务中**3D标注数据极度稀缺**的瓶颈。该任务要求模型能检测出训练时未见过的新类别物体，但现有方法严重依赖稀缺且获取成本高的3D标注框。
*   **整体含义与设定**：本文提出了一个极为激进的设定：**完全摒弃真实3D标注，甚至完全摒弃真实3D点云数据，仅使用大规模的2D图像及其标注来训练一个OV-3Det模型。** 训练好的模型在推理时，可直接处理3D点云输入，并泛化到新类别。其核心挑战在于如何弥合2D图像（训练）与3D点云（测试）之间的**模态鸿沟**，实现有效的知识迁移。

### 2. 论文提出的方法论

核心思想是构建一个**伪多模态表示框架（ImOV3D）**，通过灵活的模态转换，将2D训练图像和3D测试点云统一到一个共同的图像-点云表征空间中。

关键技术细节和流程如下：

*   **图像 → 伪点云（Point Cloud Lifting Module）**
    *   **处理流程**：利用单目深度估计模型从2D图像生成度量深度图，结合一个基于固定视场角的近似相机内参，将深度图反投影为伪3D点云。
    *   **旋转校正（Rotation Correction Module）**：由于缺乏真实相机外参，生成的点云朝向是任意的。该模块利用法线估计模型预测地面法向量，通过罗德里格斯旋转公式计算旋转矩阵，将地面法向量对齐到Z轴，确保点云水平。
    *   **公式说明**：旋转矩阵 \(R\) 通过公式 \(R = I + K + \frac{1 - \mathbf{N}_{pred} \cdot \mathbf{Z}_{axis}}{\|\mathbf{v}\|^2} K^2\) 计算，其中 \(I\) 是单位矩阵，\(\mathbf{v}\) 是预测法向量与Z轴叉积，\(K\) 是 \(\mathbf{v}\) 的斜对称矩阵。

*   **2D标注 → 伪3D标注（Pseudo 3D Annotation Generator）**
    *   **标签提升**：将2D边界框通过相机参数投影到3D空间，提取视锥体内的点云，并使用聚类算法清除背景和离群点，生成初始的伪3D边界框。
    *   **尺寸过滤（3D Box Filtering Module）**：为滤除因深度估计噪声产生的异常框，利用GPT-4查询各类别的“平均长宽高”作为先验知识，移除尺寸比例严重偏离先验的伪3D框，提升标注质量。

*   **伪点云 → 伪图像（Point Cloud Renderer）**
    *   **目的**：为了让点云也能利用强大的2D开放词汇检测器（如Detic），需要一个从点云到图像的转换器。
    *   **处理流程**：
        1.  **点云渲染（Partial-View Removal）**：从多个虚拟视角观察点云，移除视角间的重叠区域，渲染出带有空洞的部分视角深度图。
        2.  **上色（Color Rendering Module）**：使用这些部分视角深度图作为条件，微调一个ControlNet模型，将深度图转化为具有逼真纹理和色彩的“伪图像”。
        3.  **2D检测器微调**：在生成的伪图像上微调一个开放词汇2D检测器（Detic），使其能更好地适应此类图像。

*   **伪多模态3D检测器（Pseudo Multimodal 3D Object Detector）**
    *   **两阶段训练策略**：
        1.  **预训练阶段**：结合伪点云、伪3D标注和伪图像，训练一个基于ImVoteNet架构的多模态检测器。点云通过3D主干网络提取特征，同时将种子点投影到2D伪图像上，利用微调后的Detic提取2D语义特征，最后将两种特征融合进行最终预测。
        2.  **适配阶段**：在少量真实3D点云（无3D标注）上，用同样方法生成伪标签和伪图像，对模型进行微调，以缩小仿真数据与真实数据的域差距。
    *   **损失函数**：总损失 \(L_{total} = L_{loc} + \sum_i W_i \times \text{CrossEntropy}(\text{Cls-header}(F_i) \cdot \mathbf{F}_{text})\)。它结合了定位损失 \(L_{loc}\) 和分类损失，其中 \(F_i\) 可以是点云特征、图像特征或融合特征，分别与CLIP文本编码器提取的文本特征 \(\mathbf{F}_{text}\) 计算交叉熵损失。

### 3. 实验设计

*   **数据集与场景**：
    *   **训练（2D图像源）**：使用**LVIS**数据集，包含42,000张图像，覆盖1203个类别。
    *   **测试与适配（3D点云）**：在**SUNRGBD**和**ScanNet**两个室内数据集上进行评估和适配。测试时使用它们共有的10个常见类别（文中补充材料扩展为20类）。
*   **Benchmark与对比方法**：
    *   **预训练阶段（无任何3D数据）**：比较了将CLIP适配到传统3D检测器的方法，包括 **OV-VoteNet** 和 **OV-3DETR**，以及先前需要RGB-D数据训练的方法 **OV-3DET**。
    *   **适配阶段（使用少量3D点云）**：对比了当前最优的OV-3Det方法，如 **OV-3DET** 和 **CoDA**。
*   **评估指标**：采用IoU阈值为0.25的平均精度均值（**mAP@0.25**）。

### 4. 资源与算力

*   论文正文及附录中**均未明确提及**训练所使用的GPU型号、数量、显存大小或具体的训练时长。仅提供了批次大小和学习率等超参数信息，这部分信息缺失。

### 5. 实验数量与充分性

*   **实验组数**：论文进行了较为全面的实验，大约包含以下多组：
    *   **主要结果**：在2个数据集上，分别进行了预训练（3D数据自由）和适配（3D数据引导）两个阶段的对比实验。
    *   **消融实验**：对方法论中的关键组件进行了消融研究，包括：
        1.  **3D数据修正模块**：验证旋转校正和尺寸过滤两个子模块的贡献。
        2.  **伪图像渲染质量**：对比使用深度图与使用ControlNet上色后伪图像的性能差异。
        3.  **数据量影响**：探究在适配阶段，使用不同比例（如10%）真实点云数据对性能的影响。
        4.  **迁移性分析**：进行跨数据集的迁移实验（在A数据集适配，在B数据集测试）。
        5.  **2D检测器微调效果**：对比使用现成的Detic和伪图像微调后的Detic对最终结果的影响。
        6.  **补充材料**：提供了每个类别的详细AP分析、GPT-4尺寸先验的有效性可视化等。
*   **充分性与公平性**：实验设计**总体上充分、客观且公平**。从模块有效性、数据利用效率到跨场景泛化能力进行了多维度验证。对比基线清晰，特别是在预训练阶段，将CLIP合理应用于传统检测器，为本文的极端设定提供了公平的对比基准。

### 6. 论文的主要结论与发现

*   **仅用2D图像训练完全可行**：ImOV3D在完全未使用任何真实3D数据的情况下，在SUNRGBD和ScanNet上的OV-3Det性能（mAP@0.25）远超将所有现有方法强行拉到此设定下的baseline，提升幅度超过6.78%。
*   **伪多模态表示是弥合模态鸿沟的关键**：通过将图像提升为点云，再将点云渲染为图像，形成了一个“图像-点云-图像”的闭环，使得2D语义知识和3D几何结构能在同一框架内有效融合。
*   **数据质量提升模块至关重要**：旋转校正和基于GPT-4尺寸先验的过滤模块能显著提升伪数据质量，进而大幅提升模型性能。
*   **预训练对下游任务增益巨大**：当有少量真实3D点云用于适配时，经过伪数据预训练的模型性能显著优于从零开始训练的方法，证明了该预训练策略的有效性，并超越了之前的SOTA方法。

### 7. 优点

*   **设定极具突破性**：首次验证了完全脱离3D数据和标注，仅凭2D图像学习3D开放词汇检测的可能性，极大地拓展了该任务的数据来源和研究边界。
*   **方法论创新且自洽**：提出了一套完整的“2D→3D→2D”伪多模态生成与融合框架，巧妙地解决了模态鸿沟问题。特别是点云渲染器和GPT-4辅助的数据清洗模块，设计精巧。
*   **实验扎实全面**：在多个数据集和多种设定下进行了详尽的对比和消融实验，充分证明了方法各模块的有效性和框架的整体优越性。

### 8. 不足与局限

*   **对密集点云依赖性强**：论文明确指出，为渲染出有助于提升性能的伪图像，需要**密集的点云**。这意味着该方法在稀疏点云数据（如室外激光雷达点云）上的适用性可能受限。
*   **渲染视角策略限制**：在推理时，为获得最佳渲染效果，需要搜索最优的相机视角。这个过程可能增加额外的计算开销，且其鲁棒性有待进一步考证。
*   **2D检测器依赖**：整个3D检测流程的性能上限，部分受限于其所使用的2D开放词汇检测器（Detic）和上色模型（ControlNet）的性能，是一个“站在巨人肩膀上”但也被其制约的框架。
*   **算力开销不明**：未披露训练所需的计算资源，使得其他研究者难以评估其复现成本和对硬件资源的门槛要求。
*   **类别覆盖与偏差**：利用GPT-4的尺寸先验可能在极稀有或尺寸异常的物体上失效。同时，模型性能可能继承2D预训练模型中的类别偏见。

（完）
