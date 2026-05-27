---
title: "TREND: Unsupervised 3D Representation Learning via Temporal Forecasting for LiDAR Perception"
title_zh: TREND：通过时间预测进行LiDAR感知的无监督3D表征学习
authors: "Runjian Chen, Hyoungseob Park, Bo Zhang, Wenqi Shao, Ping Luo, Alex Wong"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=AHccBzULR7"
tags: ["query:lidar-d-det"]
score: 8.0
evidence: 通过时间预测进行LiDAR感知的无监督3D表征学习
tldr: 针对LiDAR点云标注成本高的问题，TREND利用时间序列预测未来观测，通过循环嵌入和时间LiDAR神经场实现无监督3D表征学习。该方法在不用标注的情况下预训练模型，有效提升下游感知任务性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ahccbzulr7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1408, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ahccbzulr7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1404, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ahccbzulr7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1137, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ahccbzulr7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1053, \"height\": 433, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ahccbzulr7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1436, \"height\": 1029, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ahccbzulr7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 705, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ahccbzulr7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ahccbzulr7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 669, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ahccbzulr7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 601, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ahccbzulr7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 758, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ahccbzulr7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1055, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ahccbzulr7/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1402, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ahccbzulr7/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 594, \"height\": 225, \"label\": \"Table\"}]"
motivation: LiDAR点云标注耗时耗力，现有无监督方法多忽略时间序列信息。
method: 提出TREND框架，结合循环嵌入和时间神经场，通过预测未来观测进行无监督预训练。
result: 在LiDAR感知任务上学习到有效表征，减少标注依赖。
conclusion: TREND为LiDAR点云的无监督预训练提供了一种利用时序信息的新方法。
---

## Abstract
Labeling LiDAR point clouds is notoriously time-and-energy-consuming, which spurs recent unsupervised 3D representation learning methods to alleviate the labeling burden in LiDAR perception via pretrained weights. Existing work focus on either masked auto encoding or contrastive learning on LiDAR point clouds, which neglects the temporal LiDAR sequence that naturally accounts for object motion (and their semantics). Instead, we propose TREND, short for Temporal REndering with Neural fielD, to learn 3D representation via forecasting the future observation in an unsupervised manner. TREND integrates forecasting for 3D pre-training through a Recurrent Embedding scheme to generate 3D embeddings across time and a Temporal LiDAR Neural Field specifically designed for LiDAR modality to represent the 3D scene, with which we compute the loss using differentiable rendering. We evaluate TREND on 3D object detection and LiDAR semantic segmentation tasks on popular datasets, including Once, Waymo, NuScenes, and SemanticKITTI. TREND generally improves from-scratch models across datasets and tasks and brings gains of 1.77\% mAP on Once and 2.11\% mAP on NuScenes, which are up to 400\% more improvement compared to previous SOTA unsupervised 3D pre-training methods. Codes and models will be available.

---

## 论文详细总结（自动生成）

# TREND: Unsupervised 3D Representation Learning via Temporal Forecasting for LiDAR Perception  
## 论文详细总结

### 1. 核心问题与研究动机
- **标注成本极高**：LiDAR点云的人工标注极为耗时耗力，有研究指出标注一帧粗粒度点云至少需10分钟，导致大规模全监督训练难以普及。
- **现有无监督预训练方法的局限**：
  - 主流方法（如掩码自编码 `(a)`、对比学习 `(b)`）仅在单帧点云或相邻两帧上操作。
  - 它们忽略了**完整的时序序列蕴含的目标运动信息与语义**，未能充分利用未来观测所携带的“干扰变量”自然分布。
- **整体含义**：论文希望利用未标注的连续LiDAR序列，通过**预测未来点云**这一自监督任务，让3D骨干网络学到更具最小充分性、更鲁棒的场景表征，从而在下游检测/分割任务中用少量标签即可取得显著提升。

### 2. 方法论
#### 核心思想
让模型在当前点云和自车动作的条件下，预测未来若干时刻的LiDAR观测，驱动3D encoder学习包含物体运动规律和场景几何的通用表示。

#### 关键技术细节与流程
- **问题定义**  
  给定当前时刻 \(t_0\) 的点云 \(\mathbf{P}_{t_0}\) 与未来各步的自车动作 \(A_{t_n\rightarrow t_{n+1}}\)，预训练目标是使渲染出的未来点云 \(\tilde{\mathbf{P}}_{t_n}\) 与真实未来点云 \(\mathbf{P}_{t_n}\) 一致（所有点云已变换至 \(t_0\) 坐标系）。

- **1) 循环嵌入（Recurrent Embedding）**  
  - 先用3D编码器\(f_{enc}\)提取当前帧3D体素特征 \(\hat{\mathbf{P}}_{t_0}\)。
  - 对自车动作 \(A_{t_n\rightarrow t_{n+1}} = [\Delta x, \Delta y, \Delta \theta]\) 进行正弦编码，并经 MLP 生成动作嵌入。
  - 将动作嵌入广播并与上一时刻的特征 \(\hat{\mathbf{P}}_{t_n}\) 拼接，通过**浅层3D稠密卷积** \(f_{3D}\) 生成下一时刻的3D嵌入 \(\hat{\mathbf{P}}_{t_{n+1}}\)，从而迭代地获得各时间步的三维特征。

- **2) 时序激光雷达神经场（Temporal LiDAR Neural Field）**  
  - 对于每个时刻 \(t\)，给定空间点 \(\mathbf{p}\)，通过三线性插值从 \(\hat{\mathbf{P}}_t\) 中查询局部特征 \(\mathbf{f}_p\)。
  - 将点坐标 \(\mathbf{p}\)、时刻的正弦编码、以及 \(\mathbf{f}_p\) 拼接后，经过 \(f_{geo}\) 得到几何特征 \(\mathbf{f}_{geo}\)，再经 \(f_{SDF}\) 预测该点的**有符号距离值** \(s\)。
  - 该神经场不仅建模了LiDAR的表面几何，还专门设计了**强度预测分支**：结合射线方向编码、几何特征和查询特征，预测该射线扫描点的强度值 \(\tilde{I}\)。

- **3) 可微渲染与损失**  
  - 过滤地面点后均匀采样射线，沿每条射线采样 \(N_{ray}\) 个点。
  - 利用预测的符号距离 \(s_n\) 计算点上的占用概率 \(\alpha_n\)，再计算累计透射率和无偏权重，**积分得到预测深度** \(\tilde{r}\)。
  - 损失函数 \(\mathcal{L}_{t_n}\) 包含三项L1损失：真实深度 vs 预测深度、真实强度 vs 预测强度、以及真实表面点的期望符号距离（应为0）。
  - 总损失 \(\mathcal{L} = \mathcal{L}_{t_0} + \mathcal{L}_{t_m}\)，其中未来时刻 \(m\) 按衰减概率采样，实现**课程学习**：逐步增加预测帧数，初期先学重建当下帧，再逐渐添入远处的未来帧。

#### 理论视角
将时间预测任务与**信息瓶颈（Information Bottleneck）** 理论关联，指出通过观测并预测场景动态，可以让表征 **Z** 自然压缩掉干扰因素 **N**，使其对下游任务 **Y** 更"最小充分"，从而提升泛化能力。

### 3. 实验设计
#### 数据集与任务
- **Once**（40线）：3D目标检测，使用5%/20%/100%标签微调。
- **NuScenes**（32线）：3D目标检测，少样本（175帧）及2.5%/5%标签微调。
- **Waymo**（64线）：作为迁移测试，用Once预训练的骨干在该数据集1%标签上微调检测。
- **SemanticKITTI**（64线）：LiDAR语义分割，测跨任务泛化能力。

#### 下游模型与指标
- 检测：CenterPoint（Once/Waymo），Transfusion-L（NuScenes），指标含 mAP、AP、mAPH、NDS 等。
- 分割：Cylinder3D，指标 mIoU、Accuracy。

#### 对比方法
- **ALSO**：占位预测法。
- **Occupancy-MAE**：掩码自编码方法。
- **4DOCC**：LiDAR点云预测方法。
- **T-MAE**：使用前一相邻帧的掩码自编码。
- **UniPAD**：基于神经渲染的自编码预训练。
- 所有baseline均用官方代码复现，并在相同下游训练配置（收敛迭代次数）下比较。

### 4. 资源与算力
- **预训练**：8张A100 GPU，每GPU batch size = 3。
- **下游微调/训练**：4张A100 GPU，按OpenPCDet默认配置。
- **计算开销对比**：每一轮训练，TREND比前方法约多8%的时间（65分钟 vs 60分钟），但下游阶段不引入额外开销，结构完全相同。
- 文中未提供总训练时长（如总epoch数对应的小时数），仅给出了单epoch耗时比较。

### 5. 实验数量与充分性
- **主要结果**：
  - Once不同数据比例3组（5%、20%、100%）×多个baseline。
  - NuScenes少样本（175帧）及附加的2.5%和5%实验。
  - Waymo迁移实验1组。
  - SemanticKITTI分割实验1组。
- **消融实验**：对循环嵌入、神经场、时序神经场进行组件消融（NuScenes）。
- **额外分析**：
  - T-SNE可视化（动静物体特征分离）。
  - 重复性实验（Once 20%标签5次重复，报告均值和方差）。
  - 课程学习、预测长度、掩码率、采样策略等超参数敏感性实验。
  - 对解码器选择（3DGS、占位、Copilot4D等）的对比讨论。
- 实验覆盖了主流数据集、不同任务和多种数据量设定，对比方法包含较新的state-of-the-art，公平性较有保障（统一架构、相同的收敛标准），整体实验设计**较为充分、客观**。

### 6. 主要结论与发现
- TREND在所有设定下均**优于训练自草稿（from-scratch）**，并大幅领先先前SOTA无监督预训练方法。
- 在Once上，仅用5%标签时即可提升mAP达 **1.77%**，20%时提升 **1.25%**，100%时提升 **1.06%**，相对先前方法提升幅度最高达400%。
- 在NuScenes少样本175帧上提升 **2.11% mAP** 和 **1.46% NDS**，相比UniPAD提升多出约90%。
- 在语义分割上同样提升 **2.89% mIoU**，证明跨任务泛化能力。
- 迁移至Waymo时亦有平均 **0.77%** 的提升。
- 通过T-SNE观察到预训练特征能较好地分离动、静态物体，表明时序预测任务确实学到了物体运动先验。

### 7. 优点
- **新颖的预训练范式**：将LiDAR点云预测作为自监督信号，天然利用时序信息。
- **显式建模自车动作**：循环嵌入机制将ego-motion作为条件输入，使未来帧的预测更合理。
- **专门设计的时序神经场**：融合时间戳、几何与强度信息，匹配LiDAR传感器特性，较直接使用相机类神经渲染更有效。
- **课程学习策略**：分阶段增加预测帧数，平滑了训练难度。
- **计算开销可控**：预训练虽略增计算，但下游结构完全不变，部署方便。
- **理论联系**：从信息瓶颈角度解释方法的合理性。

### 8. 不足与局限
- **类别不平衡表现**：
  - 在低数据量（5%、20%）下对**行人**检测提升有限，甚至轻微退化，原因可能是行人在LiDAR中呈现为难以区分的柱状几何，预测此类“模糊”物体可能导致表征对行人类判别力下降。
  - 类似现象在UniPAD等渲染类方法中也存在。
- **显式语义缺失**：方法目前主要依赖几何变化，未显式结合语义先验（如来自相机），可能限制了更高层语义的提取。
- **计算开销略高**：预训练阶段单epoch耗时约比一些baseline多8%。
- **未来预测长度的限制**：当预测帧数过多（如5帧以上）时，表征质量反而下降，表明模型对长期预测的泛化能力有限。
- **泛化实验偏少**：仅在Waymo上做了跨数据集迁移，更多第三方数据上的证据尚未提供。
- **内存消耗限制**：虽然通过地面点过滤和均匀采样控制显存，但在极高分辨率LiDAR或更大场景下可能仍有瓶颈。

（完）
