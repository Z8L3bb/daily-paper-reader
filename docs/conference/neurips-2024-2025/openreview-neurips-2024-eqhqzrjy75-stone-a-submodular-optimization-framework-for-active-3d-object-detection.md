---
title: "STONE: A Submodular Optimization Framework for Active 3D Object Detection"
title_zh: STONE：面向主动3D目标检测的子模优化框架
authors: "RUIYU MAO, Sarthak Kumar Maharana, Rishabh K Iyer, Yunhui Guo"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=EQHQzRJy75"
tags: ["query:stage-d-det"]
score: 9.0
evidence: 利用LiDAR点云的主动3D目标检测框架
tldr: 针对3D目标检测标注成本高的问题，提出基于子模优化的主动学习框架，专门用于LiDAR点云的3D目标检测，通过有效样本选择大幅降低训练检测器所需的标注量，在保证检测精度同时显著减少标注开销。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-eqhqzrjy75/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-eqhqzrjy75/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 517, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-eqhqzrjy75/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1414, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-eqhqzrjy75/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 948, \"height\": 317, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-eqhqzrjy75/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eqhqzrjy75/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 673, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eqhqzrjy75/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 705, \"height\": 390, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eqhqzrjy75/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 736, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eqhqzrjy75/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 813, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eqhqzrjy75/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 743, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eqhqzrjy75/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 742, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eqhqzrjy75/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 553, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eqhqzrjy75/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 599, \"height\": 143, \"label\": \"Table\"}]"
motivation: 训练高精度3D检测器需大量LiDAR点云标注，标注成本极高。
method: 提出基于子模优化的统一主动3D检测框架，解决点云选择中的两个基本挑战。
result: 在降低标注成本的同时保持检测性能，优于现有主动学习方法。
conclusion: 为3D检测提供经济高效的数据标注策略，推动大规模应用。
---

## Abstract
3D object detection is fundamentally important for various emerging applications, including autonomous driving and robotics. A key requirement for training an accurate 3D object detector is the availability of a large amount of LiDAR-based point cloud data. Unfortunately, labeling point cloud data is extremely challenging, as accurate 3D bounding boxes and semantic labels are required for each potential object. This paper proposes a unified active 3D object detection framework, for greatly reducing the labeling cost of training 3D object detectors. Our framework is based on a novel formulation of submodular optimization, specifically tailored to the problem of active 3D object detection. In particular, we address two fundamental challenges associated with active 3D object detection: data imbalance and the need to cover the distribution of the data, including LiDAR-based point cloud data of varying difficulty levels. Extensive experiments demonstrate that our method achieves state-of-the-art performance with high computational efficiency compared to existing active learning methods. The code is available at [https://github.com/RuiyuM/STONE](https://github.com/RuiyuM/STONE)

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：训练高精度的3D目标检测器需要海量带有精准三维边界框和语义标签的LiDAR点云数据，但点云标注成本极高，成为制约该领域发展的瓶颈。
- **整体含义**：提出一种名为STONE的统一主动3D目标检测框架，基于子模优化策略，通过智能化地选择最有信息量的未标注点云进行人工标注，从而在保证检测性能的同时大幅降低标注开销，并特别针对3D检测中**数据极度不平衡**和**场景难度多样性**两个根本性挑战给出了解决方案。

### 2. 论文提出的方法论
- **核心思想**：将主动3D目标检测建模为一个双目标子模优化问题——同时最大化所选未标注子集对整体未标注池的**代表性**以及**标注集标签分布的均衡性**。
- **关键技术细节与流程**：
  - **问题形式化** (\(\text{Eq. 3}\))：寻找子集 \(D_S\) 同时优化 \(\max [f_1(D_S) - f_1(D_U)] + [f_2(D_L) - f_2(D_L \cup D_S)]\)，其中 \(f_1\) 衡量代表性，\(f_2\) 衡量标签分布质量。
  - **两阶段算法框架**：
    1. **梯度基子模子集选择 (GBSSS)**：
        - 使用MC-Dropout生成伪标签，并计算重加权损失：回归损失按类别频率的倒数加权；分类损失通过标签分布感知的边界向量 \(m_{i,c}=1/\sqrt{n_c}\) 调整logits (\(\text{Eq. 4}\))，以缓解类别不平衡对梯度计算的影响。
        - 利用重加权损失 \(\hat{L}\) 对各点云计算梯度 \(\nabla_{\theta}\hat{L}_i\)，再以该梯度的信息熵作为得分，通过具有递减收益特性的凹函数 \(g(x)=\log(1+x)\) 建子模函数 (\(\text{Eq. 5}\))，并用贪心算法选出 \(\Gamma_1\) 个具有代表性且多样化的样本。
    2. **子模多样性最大化类别平衡 (SDMCB)**：
        - **步骤1**：利用伪标签计算每个点云的标签分布熵 \(H(P_i)\) (\(\text{Eq. 6}\))，选出个人点云标签最平衡的 \(K_1\) 个样本。
        - **步骤2**：计算将某个点云加入标注集后的累计标签分布熵 \(H(\tilde{P}_i)\) (\(\text{Eq. 7}\))，用贪心搜索迭代挑选能最大化累计熵的 \(\Gamma_2\) 个样本，从而保证全局标注集标签均衡。

### 3. 实验设计
- **数据集与场景**：
  - **KITTI**：包含3,712训练/3,769验证样本，涵盖汽车、行人、骑行者，并按遮挡程度分为EASY, MODERATE, HARD三个难度级别。
  - **Waymo Open**：大规模自动驾驶数据集，158,361训练/40,077测试样本，设LEVEL 1和LEVEL 2两个难度。
  - **PASCAL VOC**：用于验证方法在2D检测任务上的泛化能力。
- **对比方法 (Benchmark)**：
  - 通用主动学习基线：Random, ENTROPY, LLAL, CoreSet, BADGE。
  - 3D/2D检测专用或可适配方法：MC-MI, MC-REG, LT/C, CONSENSUS, CRB, KECOR, AL-MDN。
- **评估指标**：
  - KITTI：各难度级别下的3D AP和BEV AP（汽车IoU 0.7，行人/骑行者IoU 0.5）。
  - Waymo Open：各难度级别下的APH（带航向角加权的AP）。
  - PASCAL VOC：mAP@IoU 0.5。

### 4. 资源与算力
- **GPU**：使用4块NVIDIA RTX A5000 GPU。
- **显存与效率**：文中明确指出，在KITTI数据集上以批次大小6进行公平对比时，**STONE的GPU显存消耗仅为10 GB**，而KECOR为24 GB，显存占用显著降低（KECOR高出140%）。运行时间与KECOR大致相当。
- **训练设置**：KITTI和Waymo Open的批次大小分别设为6和4，评估批次大小均为16；使用Adam优化器，固定学习率0.01；均进行5次MC-Dropout随机前向传播。

### 5. 实验数量与充分性
- **实验组数**：实验设计非常全面且系统，覆盖了**3个不同尺寸和类型的公开数据集**、**2种主流3D检测骨干网络**（PV-RCNN和SECOND）、**超过10种主动学习基线方法**、以及**多种难度级别**的独立评测。
- **消融与敏感性分析**：包含关于**重加权损失函数、两阶段不同组合策略、不同子模函数选型、关键阈值 \(\Gamma_1, \Gamma_2\)** 的消融实验，还对比了不同标注预算（1%、2%、3%）下的性能走势。实验对比公平，结果充分支撑了方法的有效性。

### 6. 论文的主要结论与发现
- STONE在所有评估设置下均取得**最先进的主动3D目标检测性能**，能在相同甚至更低的标注预算下获得更高精度。
- 方法有效解决了数据不平衡问题，在主动学习过程中能保持更优的标签分布熵（Fig. 2）。
- 通过两阶段设计，既保证了所选样本的代表性，又维持了标注集的类别均衡，两者互为补充。
- 该方法不仅在3D检测上性能优越，也能**泛化至2D目标检测任务**，表现出良好的通用性。

### 7. 优点
- **问题创新**：首次将子模优化框架系统性地引入主动3D目标检测，并同时显式建模代表性和类别平衡两大难题。
- **技术设计精巧**：提出的类别平衡重加权损失函数巧妙地缓解了梯度计算阶段的类别偏差；两阶段渐进式选择流程（先个人点云平衡，再全局标注集平衡）逻辑清晰且有效。
- **计算资源友好**：相比同领域的最强基线KECOR，在保持同等运行时间下，显著降低了GPU显存占用。
- **实验扎实广泛**：在多个主流数据集、多种检测骨干和检测任务（2D/3D）上进行了全面验证，消融研究详尽，结论可信度高。

### 8. 不足与局限
- **运行效率未根本提升**：论文明确指出现有方法的运行时间瓶颈在于未标注点云数量庞大，STONE并未从实质上减少单轮选择的计算时间。
- **高预算场景下的性能优势缩小**：在超过1%标注框的高预算实验中，STONE会因倾向于选择含物体较多的场景而过早耗尽框预算，在训练轮次上少于某些基线，导致其在2%和3%标注框时的性能被KECOR轻微反超。
- **超参数敏感性**：方法依赖 \(\Gamma_1, \Gamma_2\) 等阈值，文中虽有灵敏度分析，但最优参数可能需要根据具体数据集调整。
- **域偏移未深入探讨**：实验集中于KITTI和Waymo等典型数据集，对于更多样化的传感器或极端场景下的鲁棒性，文中未做延伸讨论。

（完）
