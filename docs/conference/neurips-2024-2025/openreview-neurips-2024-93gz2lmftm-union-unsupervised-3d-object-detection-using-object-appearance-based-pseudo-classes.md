---
title: "UNION: Unsupervised 3D Object Detection using Object Appearance-based Pseudo-Classes"
title_zh: UNION：基于物体外观伪类的无监督三维物体检测
authors: "Ted Lentsch, Holger Caesar, Dariu Gavrila"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=93gz2lmFtm"
tags: ["query:lidar-d-det"]
score: 8.0
evidence: UNION使用LiDAR点云进行无监督三维物体检测
tldr: 针对现有无监督3D检测方法通过多轮自训练加入静态物体导致计算开销大的问题，UNION提出利用空间聚类和自监督场景流从LiDAR数据中获取动静物体提议，并通过外观编码区分前景与背景静态物体，实现单轮高效训练。实验表明该方法在检测性能与效率上取得改善，为大规模无标签数据下的3D物体检测提供了更实用的方案。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-93gz2lmftm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93gz2lmftm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93gz2lmftm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1404, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93gz2lmftm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 645, \"height\": 525, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-93gz2lmftm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-93gz2lmftm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-93gz2lmftm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1435, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-93gz2lmftm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 718, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-93gz2lmftm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1454, \"height\": 518, \"label\": \"Table\"}]"
motivation: 现有无监督3D检测方法需要多轮自训练，计算开销大。
method: 通过空间聚类和自监督场景流从LiDAR生成动静物体提议，并用外观编码区分静态前景与背景。
result: 实验表明UNION在无监督3D检测任务上高效且性能提升。
conclusion: UNION提出了一种高效的单轮无监督3D检测方法，避免了迭代自训练的计算负担。
---

## Abstract
Unsupervised 3D object detection methods have emerged to leverage vast amounts of data without requiring manual labels for training. Recent approaches rely on dynamic objects for learning to detect mobile objects but penalize the detections of static instances during training. Multiple rounds of (self) training are used to add detected static instances to the set of training targets; this procedure to improve performance is computationally expensive. To address this, we propose the method UNION. We use spatial clustering and self-supervised scene flow to obtain a set of static and dynamic object proposals from LiDAR. Subsequently, object proposals' visual appearances are encoded to distinguish static objects in the foreground and background by selecting static instances that are visually similar to dynamic objects. As a result, static and dynamic mobile objects are obtained together, and existing detectors can be trained with a single training. In addition, we extend 3D object discovery to detection by using object appearance-based cluster labels as pseudo-class labels for training object classification. We conduct extensive experiments on the nuScenes dataset and increase the state-of-the-art performance for unsupervised 3D object discovery, i.e. UNION more than doubles the average precision to 38.4. The code is available at github.com/TedLentsch/UNION.

---

## 论文详细总结（自动生成）

## 1. 研究动机与核心问题

- 现有无监督三维物体检测方法常依赖动态物体作为初始训练目标，将静态前景物体（如停放的车辆）视为负样本，导致训练信号不一致。
- 为解决这一问题，这些方法多采用多轮自训练逐步纳入静态物体，但计算开销大、收敛慢，且可能引入确认偏误。
- 本文提出 **UNION**，目标是利用 LiDAR、相机和时序信息联合生成高质量的伪边界框与伪类别标签，实现**单轮训练**即可同时检测静态与动态的可移动物体，避免昂贵的迭代自训练。

## 2. 方法框架与技术细节

UNION 包含两个阶段，共六个步骤（参考图 1）：

### 阶段一：物体提议生成
1. **地面移除**：使用 RANSAC 拟合地面平面，提取非地面点（高于地面 0.3m 的点）。
2. **空间聚类**：聚合前后 7 个时间步的非地面点云，采用 HDBSCAN 得到物体提议（最小簇尺寸 16 点，参数 ε=0.5m）。
3. **运动估计**：利用改进的 ICP-Flow 估计每个物体提议的 2D 平移和偏航运动，速度超过 0.5 m/s 的提议被标记为动态物体（`O_D`），其余为静态物体（`O_S`）。
4. **视觉外观编码**：使用预训练视觉基础模型 DINOv2 (ViT-L/14) 提取多视图相机图像的特征图；将每个提议的 LiDAR 点投影到图像平面，聚合平均得到外观嵌入 \(a_n \in \mathbb{R}^{C_F}\)。

### 阶段二：可移动物体发现
5. **外观聚类与簇筛选**：对所有物体提议的外观嵌入进行 K-Means 聚类（\(K_1=20\)）；计算每个簇中动态实例占比 \(X\)，若 \(X \ge 5\%\) 则该簇为“可移动簇”，否则丢弃。由此同时获得静态和动态的可移动物体，剔除背景物体（树木、建筑等）。
6. **伪标签生成与检测器训练**：对可移动物体采用 MODEST 的边框拟合算法得到伪边界框；再对其外观嵌入进行二次聚类（\(K_2\) 个伪类别），训练多类别三维检测器。推理时，利用单样本关联将伪类别映射到真实类别（仅需极少监督）。

该方法的核心创新在于：**利用外观相似性筛选静态前景物体**，无需自训练；同时通过外观聚类提供伪类别标签，扩展至多类别检测。

## 3. 实验设计

- **数据集**：nuScenes（700 训练/150 验证/150 测试场景），仅使用 8 个可移动物体类别进行类无关检测，多分类实验则合并为车辆、行人、骑行者三个真实类别。
- **指标**：平均精度 (AP) 和 nuScenes 检测分数 (NDS)，以及 ATE、ASE、AOE、AVE 等真值误差。
- **检测器**：CenterPoint（基于 pillars 0.2m，未使用测试增强，训练 20 epoch，batch size 4）。
- **对比基准**：
  - 类无关检测：HDBSCAN、OYSTER、LISO，以及监督学习下的 1%/10%/100% 数据量。
  - 多分类检测：HDBSCAN + 尺寸先验、UNION + 尺寸先验，以及不同伪类别数量 (5,10,15,20) 的 UNION 多分类版本。

## 4. 资源与算力

- 训练使用 **8 块 NVIDIA V100 32GB GPU**。
- 未提供具体训练时长，但强调单轮训练避免了迭代自训练的大量时间开销。
- 代码已开源。

## 5. 实验数量与充分性

- **主要实验**：类无关检测（表 2）和多类别检测（表 5）各一组，分别报告了与多种基线的对比。
- **消融实验 I**（表 3）：依次验证 HDBSCAN 聚类、运动估计和外观聚类对性能的贡献。
- **消融实验 II**（表 4）：对比不同视觉编码器（DINOv2 vs I-JEPA）的影响。
- **定性分析**：图 3 展示各步骤输出效果；图 4 给出各类簇动态占比分布。
- 实验覆盖了不同配置和竞争方法，对比公平；消融研究清晰证明了外观聚类是主要性能增益来源。但在统计显著性方面缺乏误差条（文中解释为计算资源限制）。

## 6. 主要结论与发现

- UNION 在 nuScenes 类无关检测中将 SOTA AP 从 13.8（HDBSCAN）提升至 **38.4**，超过一倍，且显著优于需要自训练的 OYSTER 和 LISO。
- 在多类别检测中，UNION 结合 5 个伪类别获得 **24.0 mAP**，大幅领先基于尺寸先验的基线；伪类别增加时性能有所下降，但不裁剪 PR 曲线后 20 个伪类别可检测到更多骑行者。
- 单轮训练即可同时检测静态和动态可移动物体，避免了迭代自训练的计算成本与确认偏误风险。

## 7. 亮点与优点

- **多模态联合利用**：首次将 LiDAR、相机、时序信息在同一阶段融合生成伪标签，不再依赖交替或分离的多轮训练。
- **无自训练范式**：通过外观聚类直接区分静态前景与背景，大幅降低训练复杂度与时间。
- **从发现到检测的扩展**：提出利用外观聚类生成伪类别标签，使无监督方法具备多类别检测能力。
- **即插即用**：生成的伪标签可直接用于标准检测器训练，兼容现有框架（MMDetection3D）。
- **开源可复现**：代码、数据和超参数均已公开，便于验证和扩展。

## 8. 不足与局限

- **罕见类别问题**：外观聚类依赖出现频率，若可移动物体类别样本极少，可能被合并到背景簇中而被丢弃。
- **运动估计依赖场景流**：当前使用 ICP-Flow，对快速运动或稀疏点云可能存在误差；论文建议未来可引入雷达等传感器提升鲁棒性。
- **方向估计仍具挑战**：对于各向异性不明显的物体（如行人），无监督方法难以确定正确方向，影响 AP 和 NDS。
- **多类别映射需少量监督**：推理时需要单样本关联伪类别至真实类别，虽仅需极少标注，但并非完全无监督。
- **计算资源要求较高**：使用 8 块 V100 GPU 和多个预训练大模型（DINOv2），对实际部署有一定门槛。
- **未提供多类别检测的误差条**，且对骑行者的检测性能极低（默认 AP 为 0），表明细粒度分类仍有较大提升空间。

（完）
