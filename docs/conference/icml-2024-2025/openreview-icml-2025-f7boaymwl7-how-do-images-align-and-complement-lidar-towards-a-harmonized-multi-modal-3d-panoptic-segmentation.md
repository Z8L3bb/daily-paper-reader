---
title: How Do Images Align and Complement LiDAR? Towards a Harmonized Multi-modal 3D Panoptic Segmentation
title_zh: 图像如何对齐并补充LiDAR？迈向协调的多模态3D全景分割
authors: "Yining Pan, Qiongjie Cui, Xulei Yang, Na Zhao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=F7BOaYmWl7"
tags: ["query:lidar-d-det"]
score: 9.0
evidence: 提出融合LiDAR与图像的多模态3D全景分割框架
tldr: 针对LiDAR数据稀疏导致远距离小目标识别困难的问题，提出图像辅助LiDAR的多模态3D全景分割框架IAL，通过模态同步数据增强和特征对齐增强感知，有效提升分割精度。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1741, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1755, \"height\": 1078, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 1031, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1759, \"height\": 1721, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1779, \"height\": 579, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1779, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 869, \"height\": 473, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 869, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 869, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 870, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1246, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 609, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 980, \"height\": 295, \"label\": \"Table\"}]"
motivation: LiDAR点云稀疏性限制了对远距离和小物体的准确识别，需要融合相机图像以提供稠密纹理信息。
method: 提出IAL框架，引入模态同步数据增强和特征对齐模块，实现图像与LiDAR的协调融合用于3D全景分割。
result: 在多模态3D全景分割任务上取得领先性能，显著改善了对稀疏和远距离目标的识别效果。
conclusion: 图像辅助LiDAR的多模态融合有效克服点云稀疏性，IAL框架为鲁棒3D感知提供了新思路。
---

## Abstract
LiDAR-based 3D panoptic segmentation often struggles with the inherent sparsity of data from LiDAR sensors, which makes it challenging to accurately recognize distant or small objects. Recently, a few studies have sought to overcome this challenge by integrating LiDAR inputs with camera images, leveraging the rich and dense texture information provided by the latter. While these approaches have shown promising results, they still face challenges, such as misalignment during data augmentation and the reliance on post-processing steps. To address these issues, we propose **I**mage-**A**ssists-**L**iDAR (**IAL**), a novel multi-modal 3D panoptic segmentation framework.
In IAL, we first introduce a modality-synchronized data augmentation strategy, PieAug, to ensure alignment between LiDAR and image inputs from the start. Next, we adopt a transformer decoder to directly predict panoptic segmentation results. To effectively fuse LiDAR and image features into tokens for the decoder, we design a Geometric-guided Token Fusion (GTF) module. Additionally, we leverage the complementary strengths of each modality as priors for query initialization through a Prior-based Query Generation (PQG) module, enhancing the decoder’s ability to generate accurate instance masks. Our IAL framework achieves state-of-the-art performance compared to previous multi-modal 3D panoptic segmentation methods on two widely used benchmarks. Code and models are publicly available at https://github.com/IMPL-Lab/IAL.git.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **核心问题**：LiDAR点云因激光束的径向发射模式导致数据稀疏，尤其对小物体或远距离目标的捕获点极少，严重制约了3D全景分割的精度。现有LiDAR‑相机融合方法虽能引入密集纹理信息，但存在两个关键缺陷：
  - **数据增强时的模态失配**：仅对LiDAR做增强，导致LiDAR与图像在空间上不再对齐，削弱融合效果。
  - **依赖后处理**：通过语义分割后聚类生成实例，不仅效率低，且将分割性能绑定在前置步骤的结果上，不能端到端优化全局上下文。
- **整体含义**：本文提出图像辅助LiDAR（Image‑Assists‑LiDAR, IAL）框架，旨在从根本上解决多模态3D全景分割中的输入对齐、特征融合和查询初始化问题，实现真正协调、无需后处理的端到端感知。

### 2. 方法论

IAL 基于 Transformer 解码器直接输出全景结果，由三大模块协同实现多模态协调融合：

- **PieAug——模态同步数据增强**
  - 核心思想：在圆柱体素划分的LiDAR点云上，按**高度、角度或半径**切取“扇形”体素区域，同时找到对应的图像块，将二者同步交换或粘贴。
  - 统一形式：通过一个二值掩码 `S` 控制哪些体素被来自新场景的体素替换，图像块同步替换。这样，实例粘贴（instance pasting）和场景交换（scene swapping）均可统一实现。
  - 广义性：PieAug 能泛化 PolarMix、LaserMix 等现有LiDAR增强方法，且保证**LiDAR‑图像始终对齐**。

- **GTF——几何引导的Token融合**
  - **投影与聚合**：不依赖虚拟的体素中心，而是将体素内所有物理点投影到图像平面，取对应图像特征的均值作为该体素对齐的图像特征，避免大尺寸体素投影偏差。
  - **尺度感知位置编码（SPE）**：为每个圆柱体素引入由8个角点构成的极值点集合，对中心位置进行混合参数化编码（笛卡尔+极坐标），并用MLP编码体素尺度（极值点到中心的L2距离）。将同一尺度感知位置编码分别加到LiDAR特征和图像特征上，形成统一感知域的融合 Token。
  - 最终融合 Token：`Ffuse_i = Concat[ (F3D_i + si), (F2D_i + si) ]`。

- **PQG——基于先验的查询生成**
  - 将实例查询分为三类：
    - **几何‑先验查询**：基于LiDAR预测BEV中心热度图，经NMS采样后提升到3D，适合具有丰富几何信息的大/近物体。
    - **纹理‑先验查询**：利用预训练大模型（Grounding‑DINO + SAM）提取2D掩膜，反投影到3D视锥内，通过DBSCAN聚类获取候选中心，擅长发现远/小物体。
    - **无先验查询**：一组纯可学习参数，捕获其余难以被先验覆盖的实例。
  - 将三类实例查询与语义查询一起输入 Transformer 解码器，经多层迭代直接预测掩膜和类别。

### 3. 实验设计

- **数据集与基准**：
  - **nuScenes**：32线LiDAR + 6 RGB相机，标注16个类别（10 “things” + 6 “stuffs”），训练/验证/测试帧数 34,149 / 6,019 / 6,008。
  - **SemanticKITTI**：64线LiDAR + 2前视相机，19个类别（8 “things” + 11 “stuffs”），训练/验证/测试 19,130 / 4,071 / 20,351帧。
- **评价指标**：以**Panoptic Quality (PQ)** 为主，同时汇报 PQ†（stuffs用mIoU）、**RQ**、**SQ**、**mIoU**，并按things和stuffs分解。
- **对比方法**：
  - LiDAR‑only：DS‑Net、EfficientLPS、Panoptic‑PolarNet、Panoptic‑PHNet、CFNet、CenterLPS、P3Former 等。
  - 多模态：LCPS、Panoptic‑FusionNet（及它们对应的LiDAR分支），测试集上还比较了4DFormer。

### 4. 资源与算力

- **硬件**：4 × NVIDIA A40 GPU，每卡batch size 2（总batch size 8? 原文写batch size 2，推测为总batch size 2，用4卡实现分布式训练）。
- **训练配置**：优化器 AdamW，权重衰减0.01，初始学习率 0.0008，nuScenes训练 80 epochs（在60、75 epoch衰减），SemanticKITTI训练 36 epochs（在30、32 epoch衰减）。
- **未使用测试时增强（TTA）**，推理速度：轻量版（去除2D掩膜预处理的*IAL）4.0 FPS，完整版 0.9 FPS；参数量：轻量版 81.8M，完整版 859.9M（包含预训练大模型）。

### 5. 实验数量与充分性

实验设计较为详尽，主要包括：
- **两个多模态自动驾驶基准**（nuScenes、SemanticKITTI）的全面对比，覆盖验证集和测试集。
- **整体模块消融**：依次添加 PieAug、GTF、PQG，验证三者对PQ的提升（75.7→78.4→81.1→82.3）。
- **PQG内部消融**：单独/组合使用 Geo.、Tex.、NP 查询，证实三组联合效果最优。
- **GTF内部消融**：对 token选择（虚拟中心 vs 物理点集）和位置嵌入（无/中心/极值/尺度）进行细致对比。
- **增强策略对比**：PolarMix、LaserMix 与 PieAug（含/不含图像同步）对比，证明同步增强的有效性。
- **鲁棒性实验**：在 nuScenes 的夜间/雨天子集评估，IAL 仍大幅优于 LiDAR‑only 分支和 LCPS。
- **效率/模型规模分析**：与 LCPS 在 FPS、参数量上对比，展现性能与效率的 trade‑off。
整体而言，实验从主流基准、内部机制到鲁棒性、效率均有覆盖，对比公平客观，且代码已开源。

### 6. 主要结论与发现

- IAL 在 nuScenes 验证集上达到 **82.3% PQ**，测试集 **82.0% PQ**，在 SemanticKITTI 上达到 **63.1% PQ**，均显著超越现有最先进的多模态方法（LCPS、Panoptic‑FusionNet）。
- PieAug 提供的同步增强有效缓解了模态失配，其灵活切片机制可涵盖现有多种LiDAR增强策略。
- GTF 中**物理点投影+尺度感知位置编码**对提高融合质量和识别精度贡献显著（+2.7% PQ）。
- PQG 通过几何/纹理先验与无先验查询的协同，大幅提升实例分割质量（尤其在 things 类上 +7.5% 相对于LiDAR分支）。
- 即使在夜间和雨天等成像质量严重下降的条件下，融合图像仍能为LiDAR带来稳定的性能增益（+7.3%～+8.1% PQ）。

### 7. 优点

- **首次将 Transformer 解码器直接应用于多模态3D全景分割**，摆脱后处理，实现真正的端到端预测。
- **PieAug 是通用型多模态增强框架**，统一并泛化了主流点云增强操作，同时保证模态间严格对齐。
- **GTF 的尺度感知位置编码**巧妙解决了圆柱体素尺寸不一致所导致的投影误差和感知域不匹配问题。
- **PQG 模块利用两种模态的互补先验**，结合可学习的“无先验”查询，有效提升对远距、小目标及重叠物体的检测能力。
- 实验全面：覆盖了模块消融、增强策略对比、恶劣环境测试及效率分析，提供完整解读。
- 代码开源，易于复现和后续研究。

### 8. 不足与局限

- **纹理先验依赖外部大模型**：PQG 中的纹理‑先验查询需借助 Grounding‑DINO 和 SAM，这些模型并非为本任务专门训练，可能引入域偏差和额外计算开销（导致完整模型慢且大）。
- **2D掩膜生成简单**：基于通用检测和分割模型，未对自动驾驶场景做特定优化，未来可探索任务专用的小型先验提取模块。
- **数据集覆盖有限**：仅在 nuScenes 和 SemanticKITTI 上进行验证，尚未在更多样化传感器配置（如固态雷达、不同相机布局）或合成数据集上评估泛化性。
- **SemanticKITTI 仅有两颗前视相机**，图像信息覆盖不完整，限制了多模态增益的进一步发挥。
- **先验采样策略相对朴实**：FPS 采样和 NMS 方式较为基础，可能产生次优的查询候选分布，可通过学习式采样改进。
- **无 test‑time augmentation**，虽体现方法原始性能，但或许未能完全反映最佳可达上限。

（完）
