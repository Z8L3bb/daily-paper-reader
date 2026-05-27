---
title: A Linear Time and Space Local Point Cloud Geometry Encoder via Vectorized Kernel Mixture (VecKM)
title_zh: 基于向量化核混合的线性时空局部点云几何编码器 (VecKM)
authors: "Dehao Yuan, Cornelia Fermuller, Tahseen Rabbani, Furong Huang, Yiannis Aloimonos"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=oYltxxam2t"
tags: ["query:stage-d-det"]
score: 4.0
evidence: 提出一种描述性强且高效的局部点云几何编码器，可应用于LiDAR三维感知任务。
tldr: VecKM提出一种线性时间与空间复杂度的局部点云几何编码器，通过向量化核混合表示局部形状，克服下采样不足，利用所有邻域点。定理证明其重建与保持形状相似性，实验显示描述性同时大幅降低计算与内存开销。该编码器为大规模点云处理提供可扩展的几何特征提取基础。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-oyltxxam2t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 745, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-oyltxxam2t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 718, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-oyltxxam2t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 421, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-oyltxxam2t/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 848, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-oyltxxam2t/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 842, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-oyltxxam2t/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 881, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-oyltxxam2t/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 366, \"height\": 277, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-oyltxxam2t/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1237, \"height\": 961, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-oyltxxam2t/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1218, \"height\": 947, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-oyltxxam2t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-oyltxxam2t/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 893, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-oyltxxam2t/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 893, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-oyltxxam2t/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 889, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-oyltxxam2t/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 642, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-oyltxxam2t/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 353, \"label\": \"Table\"}]"
motivation: 现有局部点云编码器常需下采样，丢失细节且计算代价高。
method: 提出向量化核混合 (VecKM)，将局部点云表示为向量化核混合，利用所有邻域点。
result: VecKM在保持描述性的同时，将内存从O(n^2+nKd)降至O(nd+np)，并减少主要计算成本。
conclusion: VecKM为大规模点云提供了一种高效且描述性强的几何编码方法。
---

## Abstract
We propose VecKM, a local point cloud geometry encoder that is descriptive and efficient to compute. VecKM leverages a unique approach by vectorizing a kernel mixture to represent the local point cloud. Such representation's descriptiveness is supported by two theorems that validate its ability to reconstruct and preserve the similarity of the local shape. Unlike existing encoders downsampling the local point cloud, VecKM constructs the local geometry encoding using all neighboring points, producing a more descriptive encoding. Moreover, VecKM is efficient to compute and scalable to large point cloud inputs: VecKM reduces the memory cost from $(n^2+nKd)$ to $(nd+np)$; and reduces the major runtime cost from computing $nK$ MLPs to $n$ MLPs, where $n$ is the size of the point cloud, $K$ is the neighborhood size, $d$ is the encoding dimension, and $p$ is a marginal factor. The efficiency is due to VecKM's unique factorizable property that eliminates the need of explicitly grouping points into neighbors. In the normal estimation task, VecKM demonstrates not only 100x faster inference speed but also highest accuracy and strongest robustness. In classification and segmentation tasks, integrating VecKM as a preprocessing module achieves consistently better performance than the PointNet, PointNet++, and point transformer baselines, and runs consistently faster by up to 10 times.

---

## 论文详细总结（自动生成）

# A Linear Time and Space Local Point Cloud Geometry Encoder via Vectorized Kernel Mixture (VecKM) 论文总结

## 1. 核心问题与整体含义
- **研究背景**：在三维点云处理（自动驾驶、机器人、遥感等）中，局部几何编码是提取点局部形状特征的基础步骤，直接影响后续分类、分割等任务。
- **现有局限**：现有局部编码器（如PointNet、KPConv、DGCNN）普遍需要显式构建邻域（计算所有点对距离，复杂度O(n²)），再对每个点的K个邻居单独应用MLP或卷积，产生O(n² + nKd)的内存开销和nK次MLP运算。因此常被迫下采样邻居点数K，导致局部细节丢失。
- **核心问题**：能否设计一种既保持高描述性（使用全部邻域点），又具有线性时间与空间复杂度的局部几何编码器？
- **整体含义**：论文提出VecKM，通过“向量化核混合”新范式，在不显式分组的情况下实现线性复杂度局部编码，理论上可重建局部形状分布并保持形状相似性，在多个任务上验证了高效性和准确性。

## 2. 方法论
### 2.1 核心思想
- 将局部点云视为一个**核混合分布**（连续函数），利用随机傅里叶特征（Random Fourier Features）将其向量化为固定维度的复向量。
- 该复向量的内积可近似高斯核，从而建立编码与形状分布之间的**重建性**和**等距性**。
- 借助指数函数的因式分解性质：exp(i(x-y)) = exp(ix)/exp(iy)，避免显式邻域分组，实现**稠密编码的高效计算**。

### 2.2 关键技术细节
#### 点级局部编码（Theorem 1）
对于中心点x₀的邻居集合N(x₀) = {xₖ - x₀}，其编码为：
\[
E_A(N(x₀)) = \frac{1}{n} \sum_{k=1}^{n} \exp(i (x_k - x_0) A_{3\times d})
\]
其中 A 的每个元素服从 N(0, α²)，d 为编码维度。  
**理论保证**（命题1,2）：
- **重建性**：当d足够大时，编码与高斯核混合等价，可从编码近似重建局部形状分布函数。
- **相似性保持**：不同局部形状间的函数内积可由编码内积近似，保持形状相关性。

#### 稠密编码的线性时间计算（Theorem 2）
利用矩阵分解与soft邻接矩阵近似：
\[
G_{n\times d} = \text{normalize}\left( (B \times B^H \times A) \, ./ \, A \right)
\]
- A = exp(i X_{n×3} A_{3×d}), B = exp(i X_{n×3} B_{3×p})，其中A、B为随机高斯矩阵（参数α和β控制带宽）。
- B × B^H 近似软邻接矩阵（指数衰减，β控制感受野），避免了n×n硬邻接矩阵计算。
- 复杂度降为O(np d)，内存O(nd + np)，仅需计算n个MLP（而非nK），p为边际因子（远小于n）。

#### 集成到深度架构
VecKM输出复数向量，后续通过复数线性层、复数ReLU，最后取模平方转为实数特征，可直接替换PointNet++的第一层或作为PointNet的前置模块，也可嵌入Transformer。

### 2.3 参数作用
- **α**：控制编码保留的细节层次。α越大保留高频细节越多，适合低层任务（如法线估计）；α越小则抽象程度高，适合高层分类/分割。
- **β**：控制局部感受野大小，与硬邻域半径r有对应关系（β越大感受野越小）。
- **d, p**：控制编码质量，越大越接近理论近似，但计算开销增加。

## 3. 实验设计
### 3.1 数据集与场景
| 任务 | 数据集 | 说明 |
|------|--------|------|
| 法线估计 | PCPNet | 8个训练形状，19个测试形状，每形状10万点，含噪声和密度变化测试 |
| 分类 | ModelNet40 | 9,843训练/2,468测试，均匀采样1024点 |
| 部件分割 | ShapeNet | 14,006训练/2,874测试，2048点 |
| 语义分割 | S3DIS | 6个区域271个房间，13类，场景点数1万~10万 |

### 3.2 对比方法
- **法线估计**：PointNet（K=300,500,700）、KPConv（核点数16/32/64）、DGCNN（邻点数32/64/128）
- **分类/分割**：PointNet、PointNet++、PCT、PointMLP 及其 VecKM 集成版本（→表示新增模块，⇋表示替换原有局部编码模块）
- **语义分割**：PointNet++、Point Transformer 及对应集成版本

### 3.3 评估指标
- 法线估计：角度RMSE；速度：推理时间（ms）；内存：峰值内存占用
- 分类：Instance Accuracy, Avg. Class Accuracy, 推理时间/批
- 分割：Instance mIoU, Class mIoU, 推理时间
- 语义分割：mIoU, OA, 推理时间

## 4. 资源与算力
- **测试环境**：所有模型在单个 RTXA-5000 GPU（24 GB 显存）上测量推理时间和内存。
- **训练算力**：文中未明确报告训练所用GPU型号、数量、批量大小下的训练时长。仅在训练细节中提及batch size、epoch数、优化器设定，未给出训练总时间。因此**训练阶段算力消耗未知**。

## 5. 实验数量与充分性
- 共覆盖**4个任务**（低层法线估计、高层分类/分割/语义分割）。
- 每个任务设有多个对比基线（至少3种编码器，多种参配），并提供了**消融实验**：
  - ModelNet40分类上网格搜索α、β组合（16组）。
  - 法线估计中分析网络层数影响。
  - 定性展示d,p的影响（附录）。
- 实验**公平性**：统一训练策略（相同epochs、优化器、数据增强）、相同输入点数，对比编码器使用可比的邻域规模。
- 覆盖了**效率、精度、噪声鲁棒性、内存消耗**多个维度，实验设计充分且客观。

## 6. 主要结论与发现
- VecKM在**法线估计**任务中误差最低（平均RMSE 17.34°，相对PointNet降幅16%以上），推理速度快100倍以上，内存占用仅数GB，且对点扰动和密度变化鲁棒性最强。
- 在**分类**任务中，VecKM集成模型（VecKM⇋PCT）达到93.1%实例准确率，超越原始PCT和PointNet++，速度提升至5.98倍；VecKM→PointNet以更少参数（9M）超越PointNet++并快7倍多。
- 在**部件分割**上，集成模型在mIoU与基线持平或略优，速度提升明显（如VecKM⇋PN++快98%）。
- 在**S3DIS语义分割**上，VecKM显著提升PointNet++的性能（+3.43 mIoU），对Point Transformer小幅加速但准确度提升微弱（可能因Transformer本身几何推理足够强）。
- 参数α和β需根据任务调整，过大/过小均影响性能，存在任务相关的敏感区间。
- 整体结论：VecKM实现了线性时空复杂度的局部编码器，理论保证其描述力，可高效集成到主流架构中，实现精度与速度的双重提升。

## 7. 优点
- **理论创新**：将局部点云建模为核混合，并通过随机傅里叶特征向量化，提供重建和等距性质的理论支撑。
- **极致效率**：首个实现线性时间和空间复杂度的局部编码器，消除了O(n²)邻近矩阵和nK次MLP，内存占用极小。
- **使用全部邻域点**：无需下采样，保留完整局部信息，提升描述力。
- **即插即用**：可无缝替换PointNet++、Transformer等结构的第一层，代码实现简洁（仅需复数矩阵乘法）。
- **鲁棒性强**：对噪声和密度变化不敏感，得益于高斯核的平滑特性。
- **全面实验验证**：覆盖多任务、多指标、多基线，展示了效率与效果的显著优势。

## 8. 不足与局限
- **训练成本未知**：未报告训练过程的GPU消耗和时长，可复现性参考不足。
- **参数敏感**：α和β对任务和点云尺度较敏感，需要调参，缺乏自动选取机制。
- **复数计算开销**：引入复数线性层，某些框架下复数运算的优化不如实数，可能影响实际加速比；最终仍需转为实数图才能接入预训练网络。
- **理论近似依赖高维度**：实际d=256，可能仅部分逼近理论性质，对于极高精度要求场景可能有近似误差。
- **高输入点数时p需增大**：当n极大（如百万级）时，p也需要相应增大以控制近似噪声，线性复杂度中的常数因子可能上升。
- **在强特征提取器（如Point Transformer）上增益有限**：当后续网络已经具备强大几何推理时，VecKM的边际贡献降低，主要体现为加速而非提点。
- **现有对比方法均为较早基线**：未与最新的高效编码器（如PointNeXt, Fast Point Transformer等）直接比较，基线选择略微有限。

---
（完）
