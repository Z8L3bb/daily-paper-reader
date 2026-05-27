---
title: "Just Add $100 More: Augmenting Pseudo-LiDAR Point Cloud for Resolving Class-imbalance Problem"
title_zh: 只需增加100美元：用伪LiDAR点云增强解决类别不平衡问题
authors: "Mincheol Chang, Siyeong Lee, Jinkyu Kim, Namil Kim"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=NlpHKNjNNZ"
tags: ["query:lidar-d-det"]
score: 8.0
evidence: 利用二维到三维视图合成生成的伪LiDAR点云增强LiDAR三维物体检测训练
tldr: 提出PGT-Aug方法，通过低成本图像生成伪LiDAR点云，用于增强LiDAR三维物体检测中的少数类训练样本，解决类别不平衡问题。该方法利用二维到三维视图合成模型进行体积三维实例重建，并进行域对齐和点采样，从而生成多样化的伪点云。实验表明，在KITTI等数据集上显著提升了少数类检测精度。该工作为LiDAR数据增强提供了高效的新方案。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 718, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 640, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1170, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1135, \"height\": 572, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1307, \"height\": 1829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1440, \"height\": 1836, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 989, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1421, \"height\": 1471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1424, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nlphknjnnz/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1215, \"height\": 605, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1300, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 580, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 634, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 717, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 652, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1441, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1065, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1450, \"height\": 940, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1096, \"height\": 573, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1309, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1218, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1451, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 751, \"height\": 476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nlphknjnnz/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1384, \"height\": 447, \"label\": \"Table\"}]"
motivation: LiDAR三维检测数据存在类别不平衡，现有增强方法缺乏少数类样本多样性。
method: 利用二维到三维视图合成从低成本视频或模型生成伪LiDAR真值点云并进行对象级域对齐。
result: 在多个LiDAR检测基准上有效提升了少数类别的检测性能。
conclusion: 通过伪点云增强，低成本地缓解了LiDAR三维检测中的类别不平衡问题。
---

## Abstract
Typical LiDAR-based 3D object detection models are trained with real-world data collection, which is often imbalanced over classes.
To deal with it, augmentation techniques are commonly used, such as copying ground truth LiDAR points and pasting them into scenes.
However, existing methods struggle with the lack of sample diversity for minority classes and the limitation of suitable placement.
In this work, we introduce a novel approach that utilizes pseudo LiDAR point clouds generated from low-cost miniatures or real-world videos, which is called Pseudo Ground Truth augmentation (PGT-Aug).
PGT-Aug involves three key steps: (i) volumetric 3D instance reconstruction using a 2D-to-3D view synthesis model, (ii) object-level domain alignment with LiDAR intensity simulation, and (iii) a hybrid context-aware placement method from ground and map information. 
We demonstrate the superiority and generality of our method through performance improvements in extensive experiments conducted on popular benchmarks, i.e., nuScenes, KITTI, and Lyft, especially for the datasets with large domain gaps captured by different LiDAR configurations.
The project webpage is https://just-add-100-more.github.io.

---

## 论文详细总结（自动生成）

# 论文总结：Just Add $100 More: Augmenting Pseudo-LiDAR Point Cloud for Resolving Class-imbalance Problem

## 1. 论文的核心问题与整体含义
- **核心问题**：在 LiDAR 3D 物体检测中，训练数据往往存在严重的类别不平衡问题（多数类样本过多，少数类如卡车、拖车等样本稀缺），导致检测模型对少数类目标识别性能差，限制了自动驾驶等应用的整体安全性。
- **研究动机**：现有数据增强方法（如 GT-Aug 复制粘贴）虽然可以缓解不平衡，但受限于少数类样本的多样性和放置位置的灵活性（只能从已有的场景中复制，位置受限）。
- **整体含义**：本文提出一种低成本、高效的数据增强框架 PGT-Aug，通过利用微缩模型和公开视频等外部来源生成伪 LiDAR 点云，并针对目标数据集进行域对齐和场景感知放置，在训练中模拟少数类样本，从而缩小类别间检测性能差距。

## 2. 论文提出的方法论
- **核心思想**：利用 2D 到 3D 视图合成技术从多视角图像（来自廉价微缩模型或网络视频）重建物体的完整三维形状，再将其转换为符合目标 LiDAR 传感器特性的伪点云，最后在训练时根据场景上下文智能插入，实现少数类样本的多样化增强。
- **关键技术步骤**：
  - **体积三维实例重建**：采用 Plenoxels 或高斯飞溅 (Gaussian-Splatting) 等视图合成模型，从多视图图像重建三维体积表示。提出视角无关颜色提取模块，通过多视角光线累积计算点云颜色，避免视图依赖性；随后执行前景分割和相机位姿估计（COLMAP）。
  - **对象级域对齐**：
    - **视角依赖点过滤与重排**：根据目标 LiDAR 传感器配置（FOV、通道数、方位角分辨率），将 RGB 点云投影至距离视图，滤除不可见面上的点，再通过球坐标重排使点云分布符合真实 LiDAR 扫描的规则模式。
    - **LiDAR 强度模拟**：基于 CycleGAN 框架构建非配对域迁移网络，将 RGB 点云转换为强度点云。设计球补丁区域匹配损失（Hungarian 匹配 + 组平均强度差）以解决点计数不匹配问题，提升强度估计准确性。
    - **实例尺寸设置**：根据目标数据集类别平均尺寸添加高斯噪声，获得逼真物体尺寸。
  - **伪 LiDAR 点云增强**：
    - **地图与地面融合插入**：融合地图语义信息（道路、人行道等）和地面点估计，构建栅格化可行区域，避免在不可行驶区域插入物体。
    - **数据几何对齐**：使用 PCA 对齐物体主轴，训练 PointNet++ 前后分类器确定朝向。
    - **虚拟扫描生成**：针对使用多帧扫描累积的数据集（如 nuScenes），利用类特定运动模型模拟物体运动轨迹，生成多帧扫描点云。

## 3. 实验设计
- **数据集与基准**：nuScenes（含验证集和测试集）、KITTI 和 Lyft，所有数据集均有类别不平衡问题。测试集参考对应榜单的官方指标。
- **对比方法**：
  - GT-Aug（随机放置复制）、Real-Aug（地面估计指导的放置）。
  - 不同检测模型架构：SECOND、CenterPoint-Pillar/Voxel、Transfusion-L、VoxelNeXt。
  - 类别不平衡损失调整方法：Dynamic Weight Average (DWA)、Class-Balanced Loss (CBLoss)。
  - 消融实验对比：仅改变放置方式、是否添加伪 LiDAR 样本、不同渲染器、传感器分辨率、强度模拟组件等。
- **评估指标**：每类 AP、所有 10 类的 mAP 和 NDS（nuScenes），以及 KITTI 上的不同难度 AP 和 Lyft 上的 mAP。

## 4. 资源与算力
- **检测模型训练**：所有检测器均使用 **4 块 NVIDIA A100 GPU** 训练，批量大小为 32，训练 20 个 epoch，每个模型训练耗时约 **36 小时**。硬件搭配 256Gi 内存和 4 个 AMD EPYC 7313 16 核 CPU。
- **伪点云生成**：
  - 2D 到 3D 渲染（含视角无关颜色提取）：每个物体约 **20 分钟**。
  - 强度模拟器训练：每类约 **30 分钟**。
  - 生成伪目标银行（含对齐、投影等）：约 **1 小时**。
  - 使用 **4 AMD EPYC 7313 CPU** 和 NVIDIA A100 加速。
- **推理/插入开销**：物体插入时从内存加载，每批次时间复杂度 O(n)，与 Real-Aug 同量级，总处理时间（强度估计+点采样+运动模型）每实例<300 ms。

## 5. 实验数量与充分性
- **实验组数丰富**：
  - 主实验对比（nuScenes val/test 上 多种放置 × 是否伪样本 × 5 种检测器）。
  - 其他数据集：KITTI（自行车/行人）、Lyft（对应少类）。
  - 消融研究：伪标签质量（FID 与检测性能相关性分析）、域对齐组件（RGB 特征、组损失、方位分辨率、渲染器选择）、银行尺寸与混合比率（GT:PGT 1:1 等）、与其他不平衡方法组合。
  - 额外验证：在 KITTI Car 上测试伪增强对多数类的效果，比较 LiDAR-Aug、3D-VField 等数据增强方法。
- **充分性与公平性**：
  - 所有实验基于 OpenPCDet 默认配置并固定随机种子，确保可比性。
  - 消融实验将银行特性（形状分布、FID）与最终 mAP/NDS 对应，验证构建模块有效性。
  - 未报告误差线，但通过固定对象银行和种子实现了确定性重现；实验覆盖多个公开基准、多种检测器，充分证明了方法的通用性和有效性。

## 6. 论文的主要结论与发现
- PGT-Aug 能够以远低于传统数据采集的成本生成高质量、多样化的伪 LiDAR 点云，有效缓解 LiDAR 3D 检测中的类别不平衡。
- 该增强方法显著提升少数类（如巴士、拖车、摩托车等）的 AP，同时不损害多数类的性能，整体 mAP 和 NDS 均获提高。
- 融合地图与地面的上下文感知放置技术比仅靠地面或随机插入更合理，扩展了有效插入区域。
- 生成点云的 FID 分数与检测性能正相关，说明域对齐（传感器匹配、强度模拟）对于提升伪样本质量至关重要。
- 方法可泛化至不同传感器配置和数据集，且能与类平衡损失等方法互补，进一步推高少数类检测精度。

## 7. 优点
- **低成本与高实用**：只需约 100 美元购买微缩模型，结合免费网络视频即可构建大规模伪点云库。
- **多样性注入**：能生成方位、距离、形状多变的全 3D 物体，突破了传统 GT-Aug 的复制限制。
- **物理逼真的域对齐**：点过滤、重排和基于 CycleGAN 的强度模拟有效缩小了生成数据与真实 LiDAR 数据的差距。
- **场景感知插入**：结合地图和地面信息避免不合理放置，提升数据增强的合理性。
- **通用验证**：在三个主流基准、五种检测器上一致有效，提供开源代码和数据以供复现。

## 8. 不足与局限
- **域差异残余**：尽管有域对齐，生成的伪点云与真实 LiDAR 间仍存在细微分布差异（FID 评分差距）。
- **对象类别限制**：当前方法主要针对刚性车辆类别，尚未扩展到动态或变形物体（如动物）。
- **多模态缺失**：目前的生成仅限于点云，未同步生成对应的相机图像数据，暂时无法用于多模态检测器增强。
- **统计显著性未充分报告**：实验未提供误差线或多次运行的结果方差，虽然宣称固定种子，但不同训练运行的波动未予讨论。
- **计算负担**：生成伪对象银行需要数小时的预运算，训练检测器需多块 A100 GPU，可能约束小算力团队的直接采用。
- **采集偏见**：伪点云质量依赖微缩模型或视频的覆盖度，可能对某些极端角度/光照不足或非常规车辆形状的重建效果有限。

（完）
