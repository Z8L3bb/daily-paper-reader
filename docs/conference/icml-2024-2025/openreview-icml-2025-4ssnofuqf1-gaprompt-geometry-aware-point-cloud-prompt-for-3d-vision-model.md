---
title: "GAPrompt: Geometry-Aware Point Cloud Prompt for 3D Vision Model"
title_zh: GAPrompt：面向三维视觉模型的几何感知点云提示
authors: "Zixiang Ai, Zichen Liu, Yuanhang Lei, Zhenyu Cui, Xu Zou, Jiahuan Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=4SsNofUQf1"
tags: ["query:stage-d-det"]
score: 4.0
evidence: 利用几何先验对三维点云视觉模型进行参数高效微调
tldr: 针对预训练三维视觉模型全微调计算开销大、现有参数高效方法难以捕获点云几何信息的问题，本文提出几何感知点云提示（GAPrompt），通过引入点提示等几何引导模块，仅训练少量参数即可有效适配下游任务，在点云分类、分割等任务上显著优于先前PEFT方法，为三维视觉模型的轻量级迁移提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-4ssnofuqf1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 703, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ssnofuqf1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1613, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ssnofuqf1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1605, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ssnofuqf1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 766, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ssnofuqf1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ssnofuqf1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 844, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ssnofuqf1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 722, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ssnofuqf1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 730, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ssnofuqf1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1759, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ssnofuqf1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1783, \"height\": 316, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-4ssnofuqf1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1722, \"height\": 1528, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ssnofuqf1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 590, \"height\": 583, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ssnofuqf1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 866, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ssnofuqf1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 867, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ssnofuqf1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1606, \"height\": 815, \"label\": \"Table\"}]"
motivation: 现有参数高效微调方法难以捕获点云内在的几何信息，限制了预训练三维视觉模型的下游任务适应性。
method: 提出几何感知点云提示（GAPrompt），包括点提示作为辅助输入，显式引导模型利用几何线索。
result: 实验表明，GAPrompt在多个三维视觉任务上以少量可调参数超越了现有PEFT方法。
conclusion: 显式融入几何先验的提示调优能显著提升点云预训练模型在下游任务中的性能。
---

## Abstract
Pre-trained 3D vision models have gained significant attention for their promising performance on point cloud data. However, fully fine-tuning these models for downstream tasks is computationally expensive and storage-intensive. Existing parameter-efficient fine-tuning (PEFT) approaches, which focus primarily on input token prompting, struggle to achieve competitive performance due to their limited ability to capture the geometric information inherent in point clouds. To address this challenge, we propose a novel Geometry-Aware Point Cloud Prompt (GAPrompt) that leverages geometric cues to enhance the adaptability of 3D vision models. First, we introduce a Point Prompt that serves as an auxiliary input alongside the original point cloud, explicitly guiding the model to capture fine-grained geometric details. Additionally, we present a Point Shift Prompter designed to extract global shape information from the point cloud, enabling instance-specific geometric adjustments at the input level. Moreover, our proposed Prompt Propagation mechanism incorporates the shape information into the model's feature extraction process, further strengthening its ability to capture essential geometric characteristics. Extensive experiments demonstrate that GAPrompt significantly outperforms state-of-the-art PEFT methods and achieves competitive results compared to full fine-tuning on various benchmarks, while utilizing only 2.19\% of trainable parameters.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容撰写的详细中文总结。

### **1. 论文的核心问题与整体含义**

*   **核心问题**：将预训练的三维视觉模型适配到下游任务时，全量微调计算开销和存储成本巨大。现有的参数高效微调方法多源自二维视觉或自然语言处理领域，主要通过在输入标记（Token）层面添加可学习提示，但忽略了三维点云数据的本质特性。
*   **核心挑战**：点云数据具有稀疏、不规则且包含丰富几何结构的特性。纯标记级别的提示方法难以有效捕获和利用点云内在的局部与全局几何信息，导致其性能难以媲美全量微调。
*   **整体含义**：本文提出了一种专为三维点云模型设计的、具备几何感知能力的参数高效微调新范式，即**几何感知点云提示（GAPrompt）**。该方法通过显式地在输入层面（点坐标）和特征层面（形状特征）引入几何引导，使得预训练模型仅需调整极少参数（约2.19%），即可在多个下游任务中取得匹敌甚至超越全量微调的性能。

### **2. 论文提出的方法论**

GAPrompt的核心思想是**显式地、多层次地利用点云的几何信息来增强提示效果**。其整体流程如图3所示，包含三大核心组件：

*   **可学习点提示**
    *   **核心思想**：直接在点云的三维几何空间中引入一组可学习的点坐标作为提示，而非在抽象的标记空间。这使提示本身与点云数据具有天然的强相关性，能更有效地引导模型捕捉细微的几何形状。
    *   **技术细节**：定义一组可学习的点坐标`P`，将其与原始输入点云`x`拼接，形成混合点云`[x; P]`，作为模型的增强输入。

*   **几何感知点偏移提示器**
    *   **核心思想**：设计一个轻量级模块，从原始点云中提取实例特定的全局形状特征`f`，并利用该特征从两方面增强几何感知能力：1）对输入点云进行坐标偏移，增强输入级几何特征；2）增强后续的令牌提示和适配器模块。
    *   **技术细节**：
        1.  **形状特征提取**：采用类似PointNet++的多分辨率分组策略，通过最远点采样（FPS）和K近邻（KNN）分层下采样，再用轻量级PointNet编码中心点坐标。最终将最高层次的特征重塑为一维向量`f`，作为该点云的全局形状表征。
        2.  **生成偏移输入**：将形状特征通过上采样（特征传播）传回原始点，再输入一个浅层MLP（偏移头），预测每个点的坐标偏移量，生成偏移后的点云`~x`。
        3.  **增强提示与适配器**：将形状特征`f`乘以一个缩放因子后，分别叠加到原始的提示令牌和适配器模块的输出上，以注入几何信息（公式12，5）。

*   **提示传播机制**
    *   **核心思想**：将经过全局形状增强的提示令牌，进一步注入到模型的特征提取过程中，以更细粒度地利用几何信息。
    *   **技术细节**：
        1.  对输入令牌`hi`再次应用FPS和KNN，找到其在几何空间中的中心令牌`hci`和邻居令牌`hni`。
        2.  采用一种类似Dropout思想的**提示注入**策略，随机地（通过替换或排列）将增强后的提示令牌`pi`混合到`hci`和`hni`中。
        3.  通过特征插值算法（公式23），将组合后的中心令牌特征传播回所有输入令牌`~hi`，从而使全局形状感知融入局部特征交互过程中。

### **3. 实验设计**

论文通过点云分类任务进行了全面评估，多个维度验证了方法的有效性。

*   **数据集与基准**：
    *   **ScanObjectNN**：一个极具挑战性的真实世界扫描物体数据集，包含嘈杂背景和遮挡。实验覆盖了它的三个变体：`OBJ_BG`、`OBJ_ONLY`和最难变体`PB_T50_RS`。
    *   **ModelNet40**：一个经典的合成三维CAD模型数据集，点云完整且无噪声，任务相对简单。

*   **基线预训练模型**：
    *   选取了多种主流的三维点云预训练模型作为微调骨架，包括Point-MAE、ReCon、Point-GPT-L和Point-FEMAE。

*   **对比方法**：
    *   **全量微调**：作为性能上限。
    *   **三维专有PEFT方法**：IDPT, DAPT, Point-PEFT。
    *   **通用的二维/NLP领域PEFT方法**：线性探测、前缀微调、VPT、Adapter、LoRA、SSF、AdapterFormer。

### **4. 资源与算力**

*   **硬件配置**：论文在附录A中明确指出，所有实验均在单个GeForce RTX 4090 GPU上完成。
*   **软件环境**：使用PyTorch 1.13.1。
*   **训练时长**：论文未明确提及具体训练时长（如小时数）。尽管提供了训练轮次、批次大小等超参数，但缺少这一直接衡量算力消耗的指标。

### **5. 实验数量与充分性**

*   **实验数量**：实验设计较为全面。
    *   **主要对比实验**：在4个不同预训练模型和4个不同数据集配置上，与4种全量微调和6种以上的PEFT方法进行了系统对比，构成了数十组定量结果。
    *   **消融实验**：系统解耦了GAPrompt的三大组件，并对组件内部（如偏移提示器各模块）、超参数（提示点数量、增强因子、初始化方式等）和策略选择（提示注入时机和方式）进行了详尽消融。
    *   **可视化分析**：提供了注意力位置热力图、特征t-SNE降维图、偏移前后点云对比图等定性分析。

*   **公平性与客观性**：
    *   使用了统一的基准数据集、数据增强策略和评价指标，对比方包括最新的SOTA方法。
    *   消融实验设置合理，遵循增量叠加原则，能清晰量化每个设计的贡献。
    *   结论多角度交叉印证，例如参数数量、浮点运算数（FLOPs）与精度一同比较，避免了以算力换精度的片面性。

### **6. 论文的主要结论与发现**

*   **性能卓越**：GAPrompt在所有实验设置下均显著优于现有的参数高效微调方法，并在多数情况下超越了全量微调的性能上限。例如，在基于Point-FEMAE的ScanObjectNN最难变体上，以**2.19%** 的可训练参数取得了比全量微调高**0.45%** 的准确率。
*   **效率极高**：GAPrompt仅增加极少的参数和计算量，证明了在3D视觉任务中，轻量级的几何感知设计比复杂的标记交互网络更有效。
*   **几何信息的核心价值**：消融实验充分证明，显式捕捉并利用实例特定的几何信息（形状特征）是提升点云PEFT方法性能的关键，其贡献远大于单纯的标记级提示。

### **7. 优点**

*   **创新性强且动机明确**：精准抓住了将PEFT方法从2D迁移到3D所面临的“几何信息缺失”这一核心痛点，提出的解决方案具有领域特异性。
*   **方法设计精巧**：三大组件（点提示、偏移提示器、提示传播）形成一套完整的几何信息闭环，从输入空间、全局特征到局部交互，层层递进地注入几何先验。
*   **性能与效率的出色平衡**：在显著超越全量微调性能的同时，保持了极低的参数量（<3%）和计算量，实践价值高。
*   **实验全面且扎实**：覆盖了多种预训练模型、数据集和对比方法，消融实验细致，可视化分析有力支撑了理论假设。

### **8. 不足与局限**

*   **下游任务覆盖有限**：实验主要聚焦于**点云分类**任务，未在如点云分割、目标检测等其他重要下游任务上进行验证，方法的泛化能力有待考证。
*   **算力成本细节缺失**：论文报告了单个RTX 4090 GPU，但未给出具体训练耗时，使得其他研究者难以精确评估其计算资源准入门槛。
*   **预训练模型依赖**：方法的表现依赖于作为基座的预训练模型，而实验中对部分基线模型（如ReCon、Point-FEMAE）仅加载其与Point-MAE兼容的部分权重，这种处理方式可能不是原模型的最佳迁移状态，略微影响了对比的绝对公平性。
*   **超参数敏感性**：论文通过消融实验展示了不同超参数（如增强因子、提示点数）对性能的影响，表明模型对部分参数较为敏感，可能需要针对新任务进行调整。

（完）
