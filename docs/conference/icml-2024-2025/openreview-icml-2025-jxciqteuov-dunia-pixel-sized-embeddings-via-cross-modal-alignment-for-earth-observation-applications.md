---
title: "DUNIA: Pixel-Sized Embeddings via Cross-Modal Alignment for Earth Observation Applications"
title_zh: DUNIA：通过跨模态对齐获得像素级嵌入用于地球观测应用
authors: "Ibrahim Fayad, Max Zimmer, Martin Schwartz, Fabian Gieseke, Philippe CIAIS, Gabriel Belouze, Sarah Brood, Aurélien de Truchis, Alexandre d'Aspremont"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JXCiQteuOv"
tags: ["query:lidar-d-det"]
score: 7.0
evidence: 使用RGB图像与全波形LiDAR的跨模态对齐获得像素级嵌入，增强地球观测感知
tldr: 地球观测中，自监督多模态学习产生的嵌入通常粒度粗糙，难以与LiDAR等模态精细对齐。该文提出DUNIA，通过图像和全波形LiDAR的跨模态对比对齐，学习像素级密集嵌入，实现零样本环境监测。实验在冠层高度制图等多个任务上证明其有效性。该方法为多模态融合感知提供了精细表示，对LiDAR点云与图像融合的3D目标检测具有直接借鉴意义，尤其在需要密集对应时。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1669, \"height\": 1092, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 1333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1697, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1576, \"height\": 1390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1580, \"height\": 1407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1582, \"height\": 1442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1725, \"height\": 955, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1591, \"height\": 2038, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1574, \"height\": 2002, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1577, \"height\": 2006, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jxciqteuov/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1577, \"height\": 2011, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1646, \"height\": 519, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1210, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1711, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 787, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 703, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 461, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 569, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 743, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1305, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 898, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 695, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 696, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 870, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jxciqteuov/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1022, \"height\": 171, \"label\": \"Table\"}]"
motivation: 现有地球观测自监督学习产生的嵌入粒度较粗，难以与LiDAR等模态有效融合。
method: 提出DUNIA，通过图像和全波形LiDAR的对比学习，生成像素级对齐嵌入。
result: 在七个零样本环境监测任务中验证了嵌入的有效性，如冠层高度映射。
conclusion: 为LiDAR多模态融合感知提供了精细粒度的自监督学习方法。
---

## Abstract
Significant efforts have been directed towards adapting self-supervised multimodal learning for Earth observation applications. However, most current methods produce coarse patch-sized embeddings, limiting their effectiveness and integration with other modalities like LiDAR. To close this gap, we present DUNIA, an approach to learn pixel-sized embeddings through cross-modal alignment between images and full-waveform LiDAR data. As the model is trained in a contrastive manner, the embeddings can be directly leveraged in the context of a variety of environmental monitoring tasks in a zero-shot setting. In our experiments, we demonstrate the effectiveness of the embeddings for seven such tasks: canopy height mapping, fractional canopy cover, land cover mapping, tree species identification, plant area index, crop type classification, and per-pixel waveform-based vertical structure mapping. The results show that the embeddings, along with zero-shot classifiers, often outperform specialized supervised models, even in low-data regimes. In the fine-tuning setting, we show strong performances near or better than the state-of-the-art on five out of six tasks.

---

## 论文详细总结（自动生成）

# DUNIA：像素级跨模态对齐嵌入用于地球观测 — 论文详细总结

## 1. 研究动机与核心问题
- **核心问题**：现有面向地球观测（EO）的自监督多模态学习方法大多生成粗糙的 **patch 级别的嵌入**，难以与高分辨率、稀疏的模态（如全波形 LiDAR）有效集成。
- **整体含义**：为了解决 **嵌入粒度粗** 导致的跨模态融合局限，本工作提出 DUNIA，通过图像（Sentinel-1/2）与全波形 LiDAR（GEDI）在 **像素级别** 进行对比对齐，学习密集的像素级嵌入，使模型能在多种环境监测任务中实现零样本甚至超越专用监督模型的性能。

## 2. 方法论
### 2.1 总体框架
DUNIA 采用多编码器‑多解码器架构，将**水平结构** (图像) 与**垂直结构** (LiDAR 波形) 嵌入到共享的像素级表示空间中。
- **预训练模型**：以单幅中值合成图像 (S-1 & S-2) 为输入，通过 ViT 编码器及两个独立解码器，产生两组像素级嵌入：
  - **OV**：用于像素‑波形对齐（垂直结构）
  - **OH**：用于像素‑像素对齐（水平结构）
- **多时相图像自编码器**：输入多个时相的中值合成图像，通过 ConvLSTM 构建的 U‑Net 生成时相特征图 X，再经时间平均池化得到嵌入 OT，与 OH 进行像素‑像素对齐。
- **波形自编码器 (VQ‑VAE)**：将 GEDI 全波形编码为离散潜在向量 z，再经平均池化与线性投影得到嵌入 OW，与 OV 进行像素‑波形对齐。

### 2.2 对齐损失
- **像素‑波形对齐**：采用 **Zero‑CL** 损失（实例对比 + 特征对比），因其在小批次（波形样本少）中效果好。公式为 `L_ZeroCL = L_Fea + L_Ins`，其中涉及 ZCA 白化矩阵。
- **像素‑像素对齐**：采用 **层次化 VICReg** 损失（方差‑不变性‑协方差），作用于解码器各层级输出 `(OH_d, OT_d)`。总的损失 `L_VICReg = Σ_d α_v L_var + β_i L_inv + γ_c L_cov`。
- **重建损失**：同时对波形、多时相图像、单时相图像进行 MSE 重建，保持语义结构。

### 2.3 波形生成
利用**潜在扩散模型 (LDM)**，以像素嵌入 OV 为条件，对波形自编码器的量化潜变量 z₀ 进行去噪生成，再通过冻结的波形解码器恢复出完整波形。

## 3. 实验设计
### 3.1 数据集
- **预训练数据**：
  - Sentinel‑2 L2A (10 m, 14 波段) 和 Sentinel‑1 IW GRD (VV+VH) 的 2020 年中值合成图像。
  - GEDI L1B/L2A/L2B 2019‑2021 年波形及衍生产品 (共约 1900 万条波形，仅占法国面积 <1%)。
  - 最终 836K 张 64×64 像素的图像，平均每张约 26 个 GEDI 波形。
- **下游评价数据集**：
  - **垂直结构任务** (回归)：冠层高度 (Wrh)、冠层覆盖度 (Wc)、植物面积指数 (Wpai)、波形检索/生成 (W)，使用 GEDI 产品作为参考。
  - **水平结构任务** (分类)：土地覆盖 (CLC+Backbone, 11 类)、作物类型 (PASTIS, 18 类+背景)、树种识别 (PureForest, 13 树种)。

### 3.2 基准与对比方法
- **零样本设置**：使用训练集嵌入作为检索库，测试集嵌入作为查询，采用 KNN 加权投票。
- **微调设置**：冻结除最后一层邻域注意力外的所有参数，添加上下游头。
- **对比模型**：SatMAE、DOFA、DeCUR、CROMA、AnySat (均在同一数据上预训练 250K 步)。

### 3.3 评估指标
- 回归：RMSE、Pearson 相关系数 r。
- 分类：加权 F1 (wF1)，对于 PASTIS 也有 OA。
- 波形：检索/生成波形与参考波形的 r。

## 4. 资源与算力
- 预训练模型在**单块 NVIDIA A6000 48GB** 上训练 **250K 步**，批大小 60，优化器为 Lion (lr=5e‑5)，约耗时数天。
- 扩散模型在相同 GPU 上训练 **100K 步**，批大小 4096，优化器 AdamW。
- 后训练/微调使用 AdamW，训练至收敛。
- 未使用多 GPU 集群，资源需求相对可控。

## 5. 实验数量与充分性
实验设计非常丰富，覆盖面广，包括：
- **7 个下游任务**的零样本和微调评估。
- **不同检索数据库大小** (100%→5%) 和 KNN 值实验。
- **6 个基线模型**的公平对比 (同数据预训练)。
- **大量消融实验**：损失函数选择 (VICReg vs Zero‑CL)、共享/分离解码器、层次化 VICReg、邻域注意力 vs 卷积、嵌入方向敏感性、输入图像尺寸 (128²~512²)、时间稳定性 (2019‑2021)、单模态 vs 多模态输入、中值合成 vs 单日期图像等。
- **定性分析**：全波形对比图、不同模型生成的专题图 (覆盖度、高度、土地覆盖)。
- 实验规模大，对比公平 (相同预训练数据与步数)，消融涵盖主要设计要素，整体充分且客观。

## 6. 主要结论与发现
- **零样本性能突出**：DUNIA 在冠层高度、冠层覆盖、植物面积指数上**大幅超越**现有专用监督模型 (例如高度 RMSE 2.0 m vs 5.2‑8.5 m)，且仅需极少样本 (50K 点) 的检索库。
- **微调表现强劲**：在 5/6 个任务上微调性能接近或达到 SOTA，尤其垂直结构任务远超其他基础模型。
- **跨模态理解生效**：分离解码器与分别对齐的策略，使水平与垂直结构嵌入保持高度语义一致性，而共享解码器或反向查询则大幅衰退。
- **波形生成能力**：扩散模型能以像素输入为条件生成合理的全波形，相关性达 0.78，模型量减至 20% 时仍有 0.75。
- **低数据泛化**：即便检索库缩小至 5%，垂直结构任务的性能保持稳定，表明嵌入具有很强的表达能力。
- **时间稳定性佳**：模型在同区域不同年份上表现一致，无需重新预训练。

## 7. 优点
- **像素级对齐**：首次实现卫星图像与全波形 LiDAR 的像素级跨模态对齐，保留了高空间分辨率，可以生成任意尺度输出。
- **垂直与水平结构解耦**：使用两个独立解码器分别处理水平和垂直理解，嵌入专业化且可检索对应结构的属性。
- **零样本 / 低样本能力**：无需额外标注即可完成多项任务，可用于数据匮乏地区的快速评估。
- **波形生成**：赋予模型从单张图像生成完整植被垂直剖面波形的能力，这是已有方法无法做到的。
- **模块化设计**：编码器可替换为其他预训练组件，便于扩展；同时训练和推理无需完整时间序列，降低数据需求。
- **公平的实验对比**：在相同数据、相同训练量下比较多个 SOTA 基础模型，结果可靠。
- **详尽的消融与分析**：对关键设计选择和稳健性进行了系统验证。

## 8. 不足与局限
- **多时相信息利用不足**：仅通过中值合成和时相池化捕获部分物候特征，对于高度依赖时序变化的任务 (如作物类型分类) 表现较差，不如专门利用时序的模型 (如 AnySat)。
- **地理与时间泛化未系统评估**：模型仅在法国大都市区 2020 年数据上预训练，迁移到其他生态区或年份可能需要重新训练，文中提到了该局限但尚未充分验证跨区域泛化。
- **依赖稀疏 LiDAR 标签**：GEDI 波形的覆盖密度低 (<1% 面积)，训练样本分布受限，可能影响对不常见森林结构的建模。
- **输入模态限制**：仅使用 S‑1 和 S‑2 的 10 m 分辨率数据，未融入更高分辨率或更多样的传感器 (如高光谱、热红外)。
- **任务覆盖**：虽然任务丰富，但仍然集中于森林和土地覆盖，未探索如火灾后恢复、生物量直接估算等更复杂的生态过程。
- **扩散模型生成代价**：波形生成虽然独特，但需额外训练扩散模型且推理步骤较多，实际应用效率需进一步优化。
- **公平性对比的局限**：对于 AnySat 等依赖超高分辨率时序数据的模型，在 S‑1&2 输入上重新训练可能未完全发挥其原有设计优势。

（完）
