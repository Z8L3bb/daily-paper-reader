---
title: "What We Miss Matters: Learning from the Overlooked in Point Cloud Transformers"
title_zh: 我们忽略的很重要：从点云Transformer中学习被忽视的信息
authors: "Yi Wang, Jiaze Wang, Ziyu Guo, Renrui Zhang, Donghao Zhou, Guangyong Chen, Anfeng Liu, Pheng-Ann Heng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=bh56ijtRb9"
tags: ["query:lidar-d-det"]
score: 9.0
evidence: BlindFormer通过对比注意力挖掘被忽略的区域，提升点云Transformer的特征多样性
tldr: 针对点云Transformer自注意力机制偏向显著区域而忽视其他信息区域的缺陷，BlindFormer提出注意力盲点挖掘方法，通过训练时抑制高注意力区域迫使模型探索被忽略的部分，从而扩展感知场并捕获更丰富的几何特征。该框架在点云分类与分割任务上显著提升了特征多样性和鲁棒性，为点云Transformer的注意力学习提供了新的有效范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-bh56ijtrb9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1433, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bh56ijtrb9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 915, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bh56ijtrb9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1428, \"height\": 737, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bh56ijtrb9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1419, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bh56ijtrb9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1429, \"height\": 634, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-bh56ijtrb9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 742, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bh56ijtrb9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1305, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bh56ijtrb9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 1235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bh56ijtrb9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 718, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bh56ijtrb9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 580, \"height\": 646, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bh56ijtrb9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1421, \"height\": 701, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bh56ijtrb9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1101, \"height\": 690, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bh56ijtrb9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 803, \"height\": 346, \"label\": \"Table\"}]"
motivation: 点云Transformer的自注意力机制过度关注显著区域，忽视其他信息区域，限制特征多样性和鲁棒性。
method: 提出BlindFormer，通过注意力盲点挖掘（ABM）抑制训练时的高关注区域，引导模型探索被忽略的区域以丰富几何特征。
result: 在3D点云分类和分割任务上，BlindFormer一致提升了性能并增强了鲁棒性。
conclusion: 通过对比注意力学习挖掘被忽略的点云区域，BlindFormer显著改进了点云Transformer的特征表示能力。
---

## Abstract
Point Cloud Transformers have become a cornerstone in 3D representation for their ability to model long-range dependencies via self-attention. However, these models tend to overemphasize salient regions while neglecting other informative regions, which limits feature diversity and compromises robustness.
To address this challenge, we introduce BlindFormer, a novel contrastive attention learning framework that redefines saliency by explicitly incorporating features typically neglected by the model. The proposed Attentional Blindspot Mining (ABM) suppresses highly attended regions during training, thereby guiding the model to explore its own blind spots. This redirection of attention expands the model’s perceptual field and uncovers richer geometric cues.
To consolidate these overlooked features, BlindFormer employs Blindspot-Aware Joint Optimization (BJO), a joint learning objective that integrates blindspot feature alignment with the original pretext task. BJO enhances feature discrimination while preserving performance on the primary task, leading to more robust and generalizable representations.
We validate BlindFormer on several challenging benchmarks and demonstrate consistent performance gains across multiple Transformer backbones. Notably, it improves Point-MAE by +13.4\% and PointGPT-S by +6.3\% on OBJ-BG under Gaussian noise. These results highlight the importance of mitigating attentional biases in 3D representation learning, revealing BlindFormer’s superior ability to handle perturbations and improve feature discrimination.

---

## 论文详细总结（自动生成）

好的，以下是根据论文内容生成的结构化深度总结。

### 1. 论文的核心问题与整体含义

*   **研究动机**：点云Transformer已成为3D视觉的基石，但其自注意力机制存在天然的注意力偏差，即过度关注少数显著区域（如物体的突出部分），而忽略了其他同样包含信息但不太显眼的区域。
*   **核心问题**：这种“注意力盲点”导致两个关键问题：
    1.  **鲁棒性降低**：对显著区域的过度依赖使模型对噪声、遮挡等扰动极其敏感，因为这些区域的破坏会不成比例地影响模型判断。
    2.  **特征判别力不足**：忽略来自非显著区域的信息限制了模型对具有相似局部结构但全局形态不同的物体的区分能力，削弱了泛化性。
*   **整体含义**：论文旨在纠正点云Transformer的注意力偏差，通过强制模型挖掘并学习被自身“忽略”的信息，从而学习到更全面、更具判别力和鲁棒性的3D表征。这是一种**对比注意力学习**范式，核心思想是“我们忽略的很重要”。

### 2. 论文提出的方法论

论文提出了一个名为 **BlindFormer** 的即插即用框架，由两大核心组件构成：**注意力盲点挖掘** 和 **盲点感知联合优化**。

*   **整体流程**：框架包含一个共享权重的双分支结构。标准分支处理原始点云，盲点分支处理被动态掩码的点云。通过联合优化原始任务损失和盲点特征对齐损失来训练模型。
*   **核心思想**：在训练过程中识别并动态抑制模型最关注的区域，迫使模型从之前被忽视的区域（即“盲点”）中学习几何线索，从而扩展其感知场并丰富特征。
*   **关键技术细节**：
    1.  **注意力盲点挖掘（ABM）**：
        *   **计算显著性分数**：利用Transformer自注意力矩阵和Value向量的范数，计算每个局部点块对全局特征的贡献度`S`。
        *   **生成动态掩码概率**：设计了一个动态掩码策略。将显著性分数`S`通过Softmax函数转化为基础概率，并引入Gumbel噪声作为扰动，得到最终动态掩码概率`pdy`。公式为 `pdy = log(Softmax(S/τ_pro)) - log(-log ε)`，其中`τ_pro`控制概率分布的锐度，`ε`来自均匀分布。
        *   **生成盲点输入**：根据`pdy`，动态地屏蔽掉Top-K个贡献度最高的点块，将剩余的、先前被忽视的点块作为盲点分支的输入。
    2.  **盲点感知联合优化（BJO）**：
        *   **盲点特征对齐**：提出一个双向对比损失`L_contra`，用于拉近标准分支和盲点分支产生的全局特征`H_s`和`H_b`。这促使模型学习到对局部显著区域缺失具有不变性的全局表征。公式为 `L_contra = -1/(2a) ∑_i (log(exp(H_bi · H_si / τ_sim) / Σ_j exp(H_bi · H_sj / τ_sim)) + ... )`。
        *   **联合学习目标**：总损失为 `L_total = L_origin + λL_contra`。其中，`L_origin`是原始预训练任务损失（如重建或生成损失），`λ`是平衡两个损失的权重。训练采用分阶段策略，初期仅优化`L_origin`，后期引入`L_contra`，以避免多任务冲突。

### 3. 实验设计

*   **数据集与场景**：
    *   **标准任务**：在真实扫描数据集 **ScanObjectNN** 和合成数据集 **ModelNet40** 上进行物体分类；在 **ShapeNetPart** 上进行部件分割。
    *   **鲁棒性测试**：在ScanObjectNN和ShapeNetPart上，模拟了四种噪声/扰动环境进行测试：**高斯噪声、随机旋转、随机缩放、点丢失（DropPoint）**。
    *   **少样本学习**：在ModelNet40上进行了5-way和10-way的少样本分类实验。
*   **基准与对比方法**：
    *   **主干网络**：将BlindFormer应用于两种主流的自监督点云Transformer架构：**Point-MAE**（掩码自编码器）和 **PointGPT-S**（自回归生成预训练）。
    *   **对比方法**：与多种监督学习方法（如PointNet++、DGCNN）和自监督学习方法（如Point-BERT、Point-M2AE、MaskPoint）进行了全面比较。

### 4. 资源与算力

*   **硬件配置**：所有实验均使用 **4块NVIDIA V100 GPU** 完成。
*   **训练时长**：BlindFormer的总预训练周期为**600个epochs**。其中，前300个epochs仅进行原始任务训练，后300个epochs引入联合优化。下游任务微调阶段也进行了相应设置和成本分析，证明性能提升并非单纯来自更长训练时间。

### 5. 实验数量与充分性

论文进行了大量且全面的实验来验证方法的有效性，覆盖超过7组主要实验和数十个子任务，具体如下：
*   **主体实验**：在不同数据集（ScanObjectNN的3个子集、ModelNet40）和不同主干网络（Point-MAE、PointGPT-S）下进行了标准分类、少样本分类和部件分割实验。
*   **鲁棒性实验**：针对高斯噪声（不同方差）、旋转（不同轴）、缩放、点丢失、局部点簇增/删等多种扰动，在分类和分割任务上均进行了系统性验证。
*   **消融实验**：在ScanObjectNN上对框架的关键组件（掩码策略、损失函数）和超参数（掩码率`R`、概率温度`τ_pro`、对比损失权重`λ`）进行了详尽的消融研究。
*   **成本与公平性分析**：针对双分支设计可能带来的训练时间增加问题，设计了对比基线（基线模型训练相同/加倍的时间/批次大小）来论证性能增益的来源，确保了公平性。
*   **定性分析**：提供了特征分布（t-SNE）可视化、注意力热力图可视化，直观地展示了方法的有效性。
这些实验设计充分、客观且公平，不仅验证了性能提升，也深入分析了背后机理。

### 6. 论文的主要结论与发现

*   BlindFormer能够有效地挖掘和利用点云Transformer中常被忽视的区域信息。
*   通过注意力盲点挖掘和联合优化，模型学习到的表征更具多样性、判别力和鲁棒性。
*   该框架在各种扰动环境下均能显著提升基线模型的性能，尤其在极端噪声下优势更为明显（例如，在OBJ-ONLY上，高斯噪声下Point-MAE准确率提升**+17.2%**）。
*   BlindFormer是一个通用的、即插即用的框架，可以无缝集成到不同的点云Transformer架构中，并带来一致性的性能增益。

### 7. 优点

*   **问题发现明确**：准确指出了点云Transformer的注意力偏差问题，并提出了有效的解决方案。
*   **方法新颖且有效**：提出“注意力盲点挖掘”的对比学习范式，通过动态抑制高注意力区域来迫使模型学习更全面的特征，构思巧妙。
*   **实验极其扎实**：实验设计严谨，覆盖了多个数据集、多种噪声、多个主干网络和全面的消融研究，并深入讨论了训练成本公平性问题，论证极具说服力。
*   **显著的鲁棒性提升**：在各种扰动下性能提升巨大，这在真实世界的3D应用中（如自动驾驶）具有极高价值。
*   **良好的通用性**：作为一种即插即用的学习策略，不绑定特定模型架构，具有很高的推广应用潜力。

### 8. 不足与局限

*   **训练开销增加**：双分支结构和分阶段训练策略总预训练周期（600 epochs）较长，相比于基线方法增加了训练时间和计算成本。
*   **数据集验证范围**：验证主要集中在物体级的分类和分割任务上，尚未在室/室外大场景点云分割、3D目标检测等更复杂的任务上进行验证。
*   **掩码粒度固定**：方法基于固定的点块（patch）粒度进行掩码，对于需要细粒度局部信息或尺度变化剧烈的场景，其适应性可能需要进一步探索。

（完）
