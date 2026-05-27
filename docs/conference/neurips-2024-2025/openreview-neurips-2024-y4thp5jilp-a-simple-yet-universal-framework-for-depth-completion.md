---
title: A Simple yet Universal Framework for Depth Completion
title_zh: 一个简单通用的深度补全框架
authors: "Jin-Hwi Park, Hae-Gon Jeon"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=Y4tHp5Jilp"
tags: ["query:lidar-d-det"]
score: 9.0
evidence: 跨传感器稠密深度估计的深度补全框架
tldr: 针对不同传感器间深度估计的尺度泛化难题，定义通用深度补全问题，提出一种简单有效的基线架构，利用最少标注数据实现跨传感器和场景的稠密深度估计，解决了泛化知识匮乏和传感器特性适应问题，在多个基准上表现优越。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-y4thp5jilp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 640, \"height\": 776, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y4thp5jilp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 898, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y4thp5jilp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y4thp5jilp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 460, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 686, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 106, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 655, \"height\": 101, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 661, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1440, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1087, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 770, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1444, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1024, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1439, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1441, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y4thp5jilp/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1442, \"height\": 930, \"label\": \"Table\"}]"
motivation: 传统深度补全依赖大量像素级标注且难适应不同深度传感器尺度差异。
method: 提出通用深度补全问题定义，设计简单基线架构，利用少量标注数据实现跨传感器深度估计。
result: 在多种传感器和场景下取得一致且高精度的深度完成结果。
conclusion: 该方法为深度补全的通用化部署提供了有效且轻量的解决方案。
---

## Abstract
Consistent depth estimation across diverse scenes and sensors is a crucial challenge in computer vision, especially when deploying machine learning models in the real world. Traditional methods depend heavily on extensive pixel-wise labeled data, which is costly and labor-intensive to acquire, and frequently have difficulty in scale issues on various depth sensors. In response, we define Universal Depth Completion (UniDC) problem. We also present a baseline architecture, a simple yet effective approach tailored to estimate scene depth across a wide range of sensors and environments using minimal labeled data. 
Our approach addresses two primary challenges: generalizable knowledge of unseen scene configurations and strong adaptation to arbitrary depth sensors with various specifications. To enhance versatility in the wild, we utilize a foundation model for monocular depth estimation that provides a comprehensive understanding of 3D structures in scenes. Additionally, for fast adaptation to off-the-shelf sensors, we generate a pixel-wise affinity map based on the knowledge from the foundation model. We then adjust depth information from arbitrary sensors to the monocular depth along with the constructed affinity. Furthermore, to boost up both the adaptability and generality, we embed the learned features into hyperbolic space, which builds implicit hierarchical structures of 3D data from fewer examples. Extensive experiments demonstrate the proposed method's superior generalization capabilities for UniDC problem over state-of-the-art depth completion. Source code is publicly available at https://github.com/JinhwiPark/UniDC.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：传统深度补全方法严重依赖大量昂贵的逐像素标注数据，并且难以泛化到具有不同规格（如扫描范围、稀疏模式）的任意深度传感器和未知场景，存在严重的**尺度偏差**问题。
- **研究动机**：现实中存在海量的深度传感器类型和复杂的应用场景，但主流研究仍局限于KITTI和NYU等少数基准数据集。为了满足产业和研究对通用深度感知的需求，作者定义了**通用深度补全**这一新问题，旨在利用极少量的标注数据，使单一模型能够适应任意传感器和环境的深度估计任务。

### 2. 论文提出的方法论
论文提出了一种简单且通用的深度补全框架，核心思想是利用**单目深度基础模型**的预训练知识，并通过**双曲几何空间**来增强模型的少样本适应能力和泛化性。该架构包含三个关键阶段：

- **基线架构设计**：
  - **利用基础模型**：直接使用在大规模数据上预训练的**单目深度估计基础模型**来提取具有丰富上下文信息的深度感知特征，避免了为不同传感器定制额外的深度编码器，从而消除了传感器偏差。
  - **稀疏到稠密转换**：基于基础模型提取的高分辨率逐像素特征，设计一个类似于**双边滤波**的传播过程，将任意传感器提供的稀疏深度点聚合、插值为初始的稠密深度图。
  - **深度图精修**：构建一个像素级的**亲和力图**，并采用**空间传播网络**对初始深度图进行迭代优化，以生成最终的高质量稠密深度图。

- **基于双曲几何的高级架构**：
  - **双曲特征嵌入**：将基础模型的多尺度特征融合后，映射到**双曲空间**中。双曲空间能够用低维度高效表达数据的隐式层次结构，这对于理解3D场景的几何关系至关重要。
  - **多曲率生成**：设计了一个**曲率生成模块**，它能根据输入的融合特征，为不同的场景和传感器类型动态地、自适应地学习最合适的双曲曲率，而不是使用一个固定的全局曲率。
  - **多曲率双曲精修**：在深度图精修阶段，利用生成的多曲率，在双曲空间中构建**多尺度、多曲率的亲和力图**，从而更精确地捕捉像素间的远近层级关系，有效缓解深度边界处的“出血”伪影。

### 3. 实验设计
- **数据集与场景**：
  - **室内场景**：使用**NYU Depth V2**数据集。
  - **室外场景**：使用**KITTI Depth Completion**数据集。
- **评估设置**：
  - **少样本学习**：在官方训练集中随机采样，设置了**1-shot、10-shot、100-shot**以及**1-Sequence（单序列）**等多种极少数据量的训练配置。
  - **无密集真值学习**：在KITTI上模拟使用64线LiDAR作为监督信号，训练8线和32线LiDAR输入的模型，以验证无密集真值监督的实用性。
  - **零样本适应**：评估模型在完全不使用目标数据集训练时的直接迁移能力。
- **对比方法**：与一系列深度补全的SOTA（state-of-the-art）方法进行了全面比较，包括：
  - 经典空间传播网络：CSPN, NLSPN, DySPN。
  - 传感器无关方法：DepthPrompting。
  - 其他强基线：S2D, BPNet, CostDCNet, CompletionFormer, LRRU, DFU, OGNI-DC等。

### 4. 资源与算力
- 文中明确指出，所有训练均在**单张 NVIDIA RTX 3090Ti GPU** 上完成。
- 使用了**Adam优化器**，初始学习率设为**5 × 10⁻³**，并在总迭代次数的每20%时衰减至0.1倍。根据训练数据集大小（1-shot到100-shot），迭代次数从100到3000次不等。
- 模型的**可学习参数量仅为460万**，其中用于微调基础模型的参数仅占41K，具有很高的参数效率。

### 5. 实验数量与充分性
- **实验组数庞大**：论文涵盖了在不同数据集（NYU, KITTI）、不同少样本配置（1-shot, 10-shot, 100-shot, 1-Sequence）、有无密集真值监督、不同深度传感器密度（100点, 32点, 16线, 8线, 4线）下的实验，总计数十项对比。
- **消融研究详尽**：针对提出的组件，进行了全面的消融实验，具体包括：
  - **双曲几何的有效性**：对比了欧几里得空间与双曲空间在零/少样本下的性能。
  - **多曲率策略的影响**：分析了固定曲率与多曲率自适应策略的性能差异，并可视化不同核大小下的曲率值。
  - **基础模型微调策略**：验证了尺度不变损失和偏置项调优的必要性。
  - **特征融合模块**：验证了多尺度特征融合对性能的提升。
  - **基础模型兼容性**：测试了该方法在MiDaS, DepthAnything, UniDepth等不同基础模型上的表现，证明了框架的通用性。
- **实验客观公平**：为保证可靠性，少样本实验均**随机选取10次不同的数据样本并报告平均结果**，并且使用了统一的随机种子。对比方法均采用了其公开的官方代码和最优配置。

### 6. 论文的主要结论与发现
- 所提出的简单通用框架能够有效地解决**通用深度补全**问题，在仅使用**极少标注数据**（甚至1张图）的条件下，显著优于现有SOTA方法，展现了强大的跨传感器和跨场景泛化能力。
- **利用预训练单目深度基础模型**是避免传感器偏差、实现快速适应的关键。
- **双曲几何空间**的引入，特别是**自适应多曲率生成**策略，对于提升模型对3D数据层次结构的理解、改善深度边界精度以及增强少样本学习能力至关重要。

### 7. 优点
- **问题定义新颖**：首次明确提出“通用深度补全”问题，具有重要的现实意义和前瞻性。
- **方法论简洁高效**：整个框架设计精巧，无需为每种传感器设计复杂模块，可学习参数量极少，训练成本低，易于复现和部署。
- **泛化能力极强**：在多种零/少样本设定下均达到SOTA，证明了方法的高鲁棒性和强适应力，摆脱了对特定数据集的过拟合。
- **理论基础扎实**：巧妙的将双曲几何引入深度补全任务，通过实验和可视化深度分析了其作用机理，增强了论文的可解释性。
- **实验极其详尽**：从多维度、多设定、多对比、多消融、多基础模型适配等方面进行了充分论证，结论非常可靠。

### 8. 不足与局限
- **输入模态限制**：当前方法仅能处理**单帧图像和对应稀疏深度图**的输入，无法处理多帧或多视角输入，限制了其在3D重建等需要多视角一致性任务上的直接应用。
- **传感器噪声鲁棒性**：论文提到，该方法难以直接应用于雷达等高噪声、高稀疏的传感器数据，需要额外设计不确定性估计模块来处理噪声测量值。
- **室外场景训练数据**：虽然在KITTI上进行了无密集真值的实验，但监督信号仍源自64线LiDAR。在完全没有真值深度（如纯自监督）的室外场景设定下的能力未得到充分验证。

（完）
