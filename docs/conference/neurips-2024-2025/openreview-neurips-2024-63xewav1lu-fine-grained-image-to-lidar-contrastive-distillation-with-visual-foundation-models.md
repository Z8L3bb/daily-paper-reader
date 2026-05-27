---
title: Fine-grained Image-to-LiDAR Contrastive Distillation with Visual Foundation Models
title_zh: 利用视觉基础模型的细粒度图像到LiDAR对比蒸馏
authors: "Yifan Zhang, Junhui Hou"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=63xeWav1lU"
tags: ["query:lidar-d-det"]
score: 8.0
evidence: 图像到LiDAR对比知识迁移用于3D表征学习
tldr: 针对图像到LiDAR对比学习中特征分离的问题，利用视觉基础模型生成语义标签进行弱监督像素到点对比蒸馏，并通过冯·米塞斯分布结构化特征空间，增强了多模态3D表征的语义一致性。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 711, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1411, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 770, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1288, \"height\": 765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1284, \"height\": 775, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1431, \"height\": 1875, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1381, \"height\": 1945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1422, \"height\": 2088, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1427, \"height\": 1469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1419, \"height\": 1758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1327, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-63xewav1lu/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1434, \"height\": 769, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1391, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1358, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1421, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1123, \"height\": 384, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 565, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 575, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 554, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 578, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 567, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1429, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 903, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 995, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1429, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-63xewav1lu/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1430, \"height\": 319, \"label\": \"Table\"}]"
motivation: 现有对比损失会意外地分离语义相同的非匹配像素与点，损害表征完整性。
method: 利用现成视觉基础模型生成语义标签，进行弱监督像素到点对比蒸馏，并采用分布建模特征空间。
result: 学习到的3D表征在下游任务中展现更强的语义区分能力。
conclusion: 该方法有效融合多模态信息，提升3D表征的泛化性与语义完整性。
---

## Abstract
Contrastive image-to-LiDAR knowledge transfer, commonly used for learning 3D representations with synchronized images and point clouds, often faces a self-conflict dilemma. This issue arises as contrastive losses unintentionally dissociate features of unmatched points and pixels that share semantic labels, compromising the integrity of learned representations. To overcome this, we harness Visual Foundation Models (VFMs), which have revolutionized the acquisition of pixel-level semantics, to enhance 3D representation learning. Specifically, we utilize off-the-shelf VFMs to generate semantic labels for weakly-supervised pixel-to-point contrastive distillation. Additionally, we employ von Mises-Fisher distributions to structure the feature space, ensuring semantic embeddings within the same class remain consistent across varying inputs. Furthermore, we adapt sampling probabilities of points to address imbalances in spatial distribution and category frequency, promoting comprehensive and balanced learning. Extensive experiments demonstrate that our approach mitigates the challenges posed by traditional methods and consistently surpasses existing image-to-LiDAR contrastive distillation methods in downstream tasks. We have included the code in supplementary materials.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义
*   **研究背景**：在自动驾驶等3D场景理解任务中，通过同步的相机图像和LiDAR点云进行“图像到LiDAR”的对比知识迁移，是学习有效3D表征的主流预训练方法之一。
*   **核心问题（自冲突困境）**：传统对比学习方法（如PPKT, SLidR）会导致“自冲突”。具体而言，**对比损失会错误地将那些与锚点（anchor）语义类别相同、但像素-点不直接匹配的样本，当作负样本推开**，从而破坏了该类别的语义完整性，损害了学习到的3D表征质量。
*   **整体含义**：本论文旨在解决上述“自冲突”问题，通过引入视觉基础模型（VFMs）提供的语义信息，实现更细粒度的、语义一致的多模态对比蒸馏，从而提升3D预训练模型在多种下游任务上的性能。

### 论文方法论
本论文提出的方法名为OLIVINE，其核心思想是利用VFMs生成的弱语义标签，将无监督的像素-点对比学习升级为**弱监督对比蒸馏**，并通过概率分布约束特征空间，结合针对性的采样策略来优化学习过程。

*   **核心组件与技术细节**：
    1.  **弱监督对比蒸馏 (Weakly-supervised Contrastive Distillation)**：
        *   **解决“自冲突”**：利用**视觉基础模型（VFMs，如SAM、SEEM）** 为每个像素生成粗糙的语义标签 `Y`。
        *   **正负样本重定义**：在对比学习中，将具有**相同语义标签**的点-像素对定义为正样本对，反之为负样本对。这从根本上避免了因空间不匹配而错误地推开同类特征。
        *   **公式**：损失函数 `L_sup` 在一个批次内，对于一个锚点特征 `G_{3D,i}`，其正样本集合 `A(i)` 由标签相同的像素特征 `G_{2D,a}` 构成，目标是拉近锚点与所有正样本的距离，同时推远它与负样本的距离。
    2.  **语义引导一致性正则化 (Semantic-guided Consistency Regularization)**：
        *   **构建结构化特征空间**：为使同类点特征在特征空间中更凝聚，论文假设每个类别 `k` 的点特征 `z` 服从**冯·米塞斯-费舍尔 (von Mises-Fisher, vMF) 分布** `vMF(z; μ_k, κ_k)`，其中 `μ_k` 是平均方向，`κ_k` 是集中度参数。
        *   **分布参数更新**：通过指数移动平均（EMA）动态估计每个类别的 `μ_k` 和 `κ_k`。
        *   **损失函数**：使用**KL散度损失 `L_kl`** 将每个点的特征拉向其所属类别的vMF分布中心，从而增强语义一致性。
    3.  **密度与类别感知采样 (Density and Category-aware Sampling)**：
        *   **解决问题**：点云存在空间分布不均（近密远疏）和类别频率严重不平衡（如“路面”远多于“自行车”）的问题。
        *   **采样策略**：为每个点 `p_i` 计算采样概率 `ρ(p_i)`，该概率与**核密度估计（KDE）得出的点密度**成反比，与**该点所属类别的出现频率**也成反比。这使得稀疏区域和少数类的点有更高概率被采样，促进平衡学习。
*   **整体流程**：特征由可训练的3D编码器（如SparseResUNet或VoxelNet）和固定的2D编码器（如ResNet-50）提取后，分别送入**两套并行投影头**：一套用于标准自监督点-像素对比损失 `L_PPNCE`，另一套用于上述弱监督对比损失 `L_sup` 和一致性正则化 `L_kl`。总损失为三者的加权和 `L = λ1*L_PPNCE + λ2*L_sup + λ3*L_kl`。

### 实验设计
*   **预训练数据集**：nuScenes（包含同步的多相机图像和32线LiDAR点云）。
*   **下游任务与基准 (Benchmarks)**：
    1.  **3D语义分割**：在 **nuScenes-lidarseg** 和 **SemanticKITTI** 数据集上，使用不同比例（1%, 5%, 10%, 25%, 100%）的标注数据微调，评价指标为mIoU。同时还测试了**线性探测（Linear Probing, LP）** 设置下的性能。
    2.  **3D目标检测**：在 **KITTI** 数据集上微调，使用SECOND和PV-RCNN两种检测头，评价指标为mAP。
    3.  **跨数据集泛化能力**：在 **ScribbleKITTI, RELLIS-3D, SemanticPOSS, SemanticSTF, SynLiDAR, DAPS-3D** 等6个数据集上评估预训练模型的迁移能力。
    4.  **鲁棒性评估**：在 **Robo3D (nuScenes-C)** 基准上测试模型面对雾、雪、运动模糊等8种OOD（分布外）干扰的鲁棒性。
*   **对比方法**：与**Random initialization**和多个先进的3D自监督/跨模态预训练方法进行了全面比较，包括**PointContrast, DepthContrast, PPKT, SLidR, ST-SLidR, Seal** 和 **HVDistill**。

### 资源与算力
*   **硬件**：使用 **4块NVIDIA-3090 GPU** 进行预训练。
*   **预训练配置**：优化器为动量SGD，初始学习率根据主干网络不同（SparseResUNet为0.5，VoxelNet为0.01），采用余弦退火调度，共训练**50个epoch**，总批量大小为16。论文附录提到，对于SparseResUNet，其预训练显存占用约为8.1GB，训练耗时约36.5小时。

### 实验数量与充分性
*   **实验数量丰富**：论文进行了大量的实验，涵盖了2个主要下游数据集（语义分割和目标检测）的多种数据比例设置，以及6个额外的跨数据集泛化实验和1个鲁棒性评估实验。
*   **消融研究充分**：通过详细的消融实验（Table 5, 6），明确验证了（1）弱监督对比蒸馏，（2）语义一致性正则化，（3）密度与类别感知采样，（4）解耦投影头，（5）vMF分布等各个核心组件的有效性及增益。
*   **对比客观公平**：严格遵循先前工作（如SLidR, Seal）的评估协议，对比了同一时期的最先进方法，并公开了代码以确保可复现性。实验比较全面，结论较为可靠。

### 主要结论与发现
*   OLIVINE通过利用VFMs生成的弱语义标签进行监督对比学习，有效解决了传统图像到LiDAR对比学习中的“自冲突”问题。
*   引入vMF分布进行语义一致性正则化，能有效塑造结构化的特征空间，使得相同类别的特征更加紧凑。
*   提出的密度和类别感知采样策略能有效缓解点云数据中的空间分布不均和类别不平衡问题，提升了对少数类和远距离物体的学习效果。
*   综合上述技术，OLIVINE在语义分割、目标检测、跨数据集泛华及鲁棒性等多个下游任务上，**一致地超越了所有现有方法，取得了最优性能**。

### 优点
*   **创新性强**：首次将视觉基础模型（VFMs）的语义先验引入图像到LiDAR的对比蒸馏流程，将无监督学习升级为弱监督学习，从根本上解决了自冲突问题。
*   **方法设计合理**：提出解耦投影头设计，分别学习实例级（点-像素对应）和语义级（类别一致）特征，并结合vMF分布进行概率建模，思想新颖且有效。
*   **实验系统全面**：不仅在标准任务和数据比例下评估，还涵盖了跨数据集、鲁棒性等复杂场景，消融实验设计细致，充分证明了各模块的有效性。
*   **实用性强**：该方法仅在预训练阶段使用VFMs生成额外标签，不增加下游推理时的计算成本，且能显著提升少样本下的微调性能，具有很好的应用价值。

### 不足与局限
*   **依赖VFMs的准确性**：方法性能依赖于VFMs（如SAM, SEEM）生成的伪标签质量。若VFM在某些特定场景下产生错误标签，可能会误导预训练，尽管论文指出更强的VFM能带来更好的效果。
*   **训练场景多样性**：目前预训练主要基于nuScenes这一单一数据集，可能限制了模型在差异较大的其他环境中的泛化潜力，尽管跨数据集实验已初步验证了其有效性。
*   **目标检测增益相对有限**：论文指出，由于目标检测模型架构更为复杂（包含BEV投影、RPN等大量未预训练组件），其性能提升幅度不如语义分割任务那样显著。
*   **自监督分支未完全移除**：尽管引入了弱监督分支，但方法仍保留了传统的自监督像素-点对比损失 `L_PPNCE`，这部分的消融实验分析相对较少。

（完）
