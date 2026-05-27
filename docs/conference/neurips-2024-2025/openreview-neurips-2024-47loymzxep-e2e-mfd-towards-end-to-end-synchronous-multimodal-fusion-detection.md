---
title: "E2E-MFD: Towards End-to-End Synchronous Multimodal Fusion Detection"
title_zh: E2E-MFD：面向端到端同步多模态融合检测
authors: "Jiaqing Zhang, Mingxiang Cao, Weiying Xie, Jie Lei, DaixunLi, Wenbo Huang, Yunsong Li, Xue Yang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=47loYmzxep"
tags: ["query:lidar-d-det"]
score: 4.0
evidence: 端到端同步多模态融合检测
tldr: 针对多模态图像融合与目标检测任务训练流程复杂、易陷入次优解的问题，提出端到端同步多模态融合检测算法E2E-MFD。该方法采用同步联合优化策略，共享参数梯度矩阵综合优化，实现融合与检测在单一训练阶段内端到端协同收敛。在多个多模态数据集上的实验表明，E2E-MFD相比分阶段训练方法显著提升了检测精度与效率，为自动驾驶感知系统提供了简洁高效的融合检测方案。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1389, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1167, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1311, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1415, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1312, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1313, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1299, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1090, \"height\": 1202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1022, \"height\": 1098, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1022, \"height\": 1075, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-47loymzxep/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1171, \"height\": 1098, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-47loymzxep/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-47loymzxep/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1299, \"height\": 582, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-47loymzxep/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-47loymzxep/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 800, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-47loymzxep/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 801, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-47loymzxep/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 660, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-47loymzxep/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 664, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-47loymzxep/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1209, \"height\": 213, \"label\": \"Table\"}]"
motivation: 现有多模态融合检测方法训练流程复杂，限制应用。
method: 提出端到端同步联合优化算法，在单一训练阶段内实现融合与检测协同。
result: 在多个数据集上实现高精度检测，训练流程简化。
conclusion: E2E-MFD为多模态融合检测提供了高效端到端解决方案。
---

## Abstract
Multimodal image fusion and object detection are crucial for autonomous driving. While current methods have advanced the fusion of texture details and semantic information, their complex training processes hinder broader applications. Addressing this challenge, we introduce E2E-MFD, a novel end-to-end algorithm for multimodal fusion detection. E2E-MFD streamlines the process, achieving high performance with a single training phase. It employs synchronous joint optimization across components to avoid suboptimal solutions associated to individual tasks. Furthermore, it implements a comprehensive optimization strategy in the gradient matrix for shared parameters, ensuring convergence to an optimal fusion detection configuration. Our extensive testing on multiple public datasets reveals E2E-MFD's superior capabilities, showcasing not only visually appealing image fusion but also impressive detection outcomes, such as a 3.9\% and  2.0\% $\text{mAP}_{50}$ increase on horizontal object detection dataset M3FD and oriented object detection dataset DroneVehicle, respectively, compared to state-of-the-art approaches.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：可见光-红外多模态图像融合与目标检测是自动驾驶和遥感监测的关键技术。现有方法通常采用多阶段级联训练（先训练融合网络，再训练检测网络），或逐步联合优化，导致训练流程复杂、效率低下，且容易陷入单个任务的局部最优，难以获得对融合和检测都友好的统一特征表示。
- **整体含义**：提出一种端到端的**同步联合优化**框架 E2E‑MFD，将图像融合和目标检测整合到一个单一训练阶段中，通过共享参数和梯度对齐，实现两个任务的高效协同，输出视觉友好且有利于检测的融合图像及准确的检测结果。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **总体架构**：E2E‑MFD 由共享骨干网络、融合子网络和检测子网络三部分构成，采用**同步联合优化**，目标函数为融合损失和检测损失的加权组合，并引入对共享参数的约束项。
- **对象‑区域‑像素进化树（Object‑Region‑Pixel Phylogenetic Tree, ORPPT）**：
  - 受人类视觉由粗到细的感知过程启发，构建多分支结构（1个像素特征挖掘模块 PFMM + L个区域特征细化模块 RFRM）。
  - PFMM 直接对输入图像对进行像素级融合；RFRM 在共享骨干提取的多模态特征上，利用可学习的区域提示生成区域掩码，对特征进行空间注意力加权，形成区域级表示，再上采样并与像素级特征融合，最终通过卷积重建融合图像。
- **粗到细扩散过程（Coarse‑to‑Fine Diffusion Process, CFDP）**：
  - 将扩散模型用作检测头，对目标边界框进行前向噪声添加和反向去噪预测，训练时最小化去噪后的框与真实框的 ℓ₂ 损失。
  - 推理时从标准高斯噪声逐步去噪恢复边界框，条件为可见光‑红外图像对。
- **梯度矩阵任务对齐（Gradient Matrix Task‑Alignment, GMTA）**：
  - 将共享参数的梯度矩阵 G = {g_u, g_d} 视为一个线性系统，通过约束其条件数 κ(G)=1（即梯度正交且等幅）来消除任务冲突和支配。
  - 通过 SVD 分解 G，并将其奇异值缩放至最小奇异值，获得对齐后的梯度矩阵 $\hat{G}$，保证优化稳定性，确保收敛到对两任务均优的权重配置。
- **损失函数**：融合损失 L_u 包含结构相似性损失 L_SSIM、对象感知像素损失 L_pixel（对象区域取最大像素、背景区域取平均像素）和多尺度梯度损失 L_grad；检测损失 L_d 使用扩散过程中的 ℓ₂ 损失。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：
  - **M3FD**：水平框多模态目标检测（含 2,940 训练对、1,260 测试对），同时用于融合和检测评估。
  - **DroneVehicle**：旋转框多模态目标检测（28,439 对，含训练/验证/测试），用于融合和定向检测评估。
  - **TNO**（42 对）和 **RoadScene**（37 对）：仅用于融合质量测试。
- **对比方法**：
  - 纯融合方法：DIDFuse、U2Fusion、PIAFusion、SwinFusion、CDDFuse 等。
  - 融合‑检测联合方法：Tardal、MetaFusion、ICAFusion、CFT 等。
  - 单模态检测基线：YOLOv5s、LSKNet‑OBB、Faster R‑CNN‑OBB、Gliding Vertex 等。
- **评估指标**：融合质量用 EN、MI、VIF；检测用 mAP₅₀ 和 mAP₅₀:₉₅。

### 4. 资源与算力
- **硬件**：所有实验使用 1 块 NVIDIA GeForce RTX 3090 GPU。
- **训练时长**：M3FD 上 E2E‑MFD 训练仅需约 2 小时 50 分钟（15,000 次迭代），显著低于大多数对比方法（如 CDDFuse 约 6 小时，MetaFusion 约 6 小时 47 分钟）；DroneVehicle 上微调 12 个 epoch（batch size=4）。测试时单张融合图像推理时间约 0.014 秒，排名第三。

### 5. 实验数量与充分性
- **主要实验**：
  - 4 个数据集上的融合质量对比（表 1，图 3）。
  - M3FD 和 DroneVehicle 上的检测性能对比（表 2/3，图 4/8）。
  - 多个检测器下的鲁棒性验证（YOLOv5s、DiffusionDet、LSKNet‑OBB 等）。
- **消融实验**：
  - GMTA 有效性：对比独立训练、无 GMTA 联合训练、有 GMTA 联合训练（表 4）。
  - 不同多任务学习方法对比：PCGrad、CAGrad、Nash‑MTL（表 5）。
  - GMTA 操作频率（迭代间隔 n）的影响（表 6）。
  - ORPPT 分支数量（0～4 个区域分支）（表 7），并结合特征图可视化（图 6）。
  - CFDP 有无及提议框数量（表 8）。
- **充分性与公平性**：实验涵盖多种数据集、多种 SOTA 方法，并在相同硬件及软件环境下公平对比；消融实验设计全面，覆盖各关键模块，结论可靠。

### 6. 论文的主要结论与发现
- E2E‑MFD 实现了真正的端到端单阶段同步联合训练，在提升融合视觉效果的同时显著提高了目标检测精度（M3FD 上 mAP₅₀ 达 91.8%，DroneVehicle 上达 77.4%）。
- ORPPT 结构有效地在不同粒度上捕捉对象信息，增强了融合图像的对比度和细节保留。
- GMTA 通过缓解梯度冲突和任务支配，使共享参数能收敛至对两任务均有利的平衡点，是性能提升的关键。
- CFDP 扩散检测头能更好地利用融合特征，相比传统 RPN 方案带来进一步增益。

### 7. 优点：方法或实验设计上的亮点
- **端到端同步范式**：打破了多阶段级联训练的传统，极大地简化了训练流程，同时提升了最终性能。
- **GMTA 梯度对齐**：将多任务学习中的梯度冲突问题形式化为条件数约束，并给出解析投影解法，理论清晰，效果显著。
- **ORPPT 多粒度融合**：模拟人类视觉由粗到细的过程，显式引入区域级语义信息，平衡了像素细节和高层语义。
- **全面的实验验证**：覆盖水平框和旋转框检测、不同检测器骨架、多个公开数据集，并与大量竞争方法进行公平对比，消融实验拆分细致。

### 8. 不足与局限
- **模态单一**：仅验证了可见光‑红外两种模态的组合，尚未拓展至其他模态（如近红外、短波红外、深度图等），受限于相关多模态数据集。
- **数据集规模局限**：TNO、RoadScene 等融合测试集规模极小，虽然用于评估融合质量，但统计意义有限。
- **潜在泛化风险**：虽然在不同数据集上表现良好，但未讨论在极端天气、严重遮挡或低分辨率等实际挑战下的鲁棒性。
- **可解释性**：ORPPT 的区域提示和分支行为分析尚停留在定性的特征图可视化，缺乏更深入的定量或理论支撑。

（完）
