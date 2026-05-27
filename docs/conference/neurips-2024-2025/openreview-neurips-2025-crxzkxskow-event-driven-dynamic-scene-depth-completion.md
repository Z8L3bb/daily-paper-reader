---
title: Event-Driven Dynamic Scene Depth Completion
title_zh: 事件驱动的动态场景深度补全
authors: "Zhiqiang Yan, Jianhao Jiao, Zhengxue Wang, Gim Hee Lee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cRxzKxsKow"
tags: ["query:lidar-d-det"]
score: 8.0
evidence: 使用LiDAR测量的事件驱动深度补全
tldr: 针对动态场景中传统RGB-D传感器难以精确对齐和捕获深度的问题，提出事件驱动的深度补全框架EventDC。该框架利用事件相机的高时间分辨率与LiDAR稀疏测量，通过事件调制对齐和局部深度滤波自适应学习卷积偏移和权重，在动态环境下实现鲁棒的密集深度估计，为自动驾驶和机器人动态深度感知提供了有效解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-crxzkxskow/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1369, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-crxzkxskow/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1420, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-crxzkxskow/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1382, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-crxzkxskow/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1279, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-crxzkxskow/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 387, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-crxzkxskow/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 386, \"height\": 545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-crxzkxskow/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1413, \"height\": 896, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-crxzkxskow/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1369, \"height\": 1402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-crxzkxskow/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1444, \"height\": 594, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-crxzkxskow/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 912, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-crxzkxskow/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1446, \"height\": 522, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-crxzkxskow/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1284, \"height\": 554, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-crxzkxskow/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1032, \"height\": 537, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-crxzkxskow/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1033, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-crxzkxskow/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 680, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-crxzkxskow/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1148, \"height\": 271, \"label\": \"Table\"}]"
motivation: 动态场景下传统RGB-D传感器深度补全失效，事件相机可提供高速运动线索。
method: 提出EventDC，包含事件调制对齐(EMA)和局部深度滤波(LDF)两个自适应学习模块。
result: 在动态场景深度补全基准上显著优于已有方法，表现出强鲁棒性。
conclusion: 首次实现事件驱动的深度补全，为动态环境下的多模态融合感知提供了新思路。
---

## Abstract
Depth completion in dynamic scenes poses significant challenges due to rapid ego-motion and object motion, which can severely degrade the quality of input modalities such as RGB images and LiDAR measurements. Conventional RGB-D sensors often struggle to align precisely and capture reliable depth under such conditions. In contrast, event cameras with their high temporal resolution and
sensitivity to motion at the pixel level provide complementary cues that are beneficial in dynamic environments. To this end, we propose EventDC, the first event-driven depth completion framework. It consists of two key components: Event-Modulated Alignment (EMA) and Local Depth Filtering (LDF). Both modules adaptively learn the two fundamental components of convolution operations: offsets and weights conditioned on motion-sensitive event streams. In the encoder, EMA leverages events to modulate the sampling positions of RGB-D features to achieve pixel redistribution for improved alignment and fusion. In the decoder, LDF refines depth estimations around moving objects by learning motion-aware masks from events. Additionally, EventDC incorporates two loss terms to further benefit global alignment and enhance local depth recovery. Moreover, we establish the first benchmark for event-based depth completion comprising one real-world and two synthetic datasets to facilitate future research. Extensive experiments on this benchmark demonstrate the superiority of our EventDC. [Project page](https://yanzq95.github.io/projectpage/EventDC/index.html).

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**：在动态场景（快速自运动 + 物体运动）中，传统 RGB‑D 深度补全方法严重失效。主要原因是：
  - RGB 图像出现运动模糊；
  - LiDAR 测量与 RGB 图像间产生严重错位；
  - 快速移动物体附近的深度估计极不准确。
- **事件相机的优势**：事件相机具有微秒级时间分辨率和对像素级运动的高度敏感性，能够在传统传感器失效的区域提供低延迟、可靠的互补信号。
- **核心问题**：如何将事件相机的高频运动信息有效融入深度补全框架，以解决动态场景下的全局错位与局部深度误差。
- **整体含义**：本文提出首个事件驱动的深度补全框架 EventDC，旨在借助事件数据显著提升动态环境中的稠密深度预测质量，并为此建立首个基准数据集。

## 2. 论文提出的方法论

EventDC 的核心思想是利用事件流自适应地调节卷积操作的两个基本要素——采样位置（偏移）与权重，从而在编码器端实现多模态对齐，在解码器端实现运动区域深度细化。

### 2.1 整体架构
- 三个结构一致的编码器分别提取彩色图像 I、稀疏深度 S 和事件 E 的多尺度特征。
- 在编码器各阶段插入 **事件调制对齐** 模块（EMA）；在解码器各阶段插入 **局部深度滤波** 模块（LDF）。

### 2.2 事件调制对齐（EMA）
- **输入**：第 j 阶段的 RGB 特征 Iⱼ、稀疏深度特征 Sⱼ、事件特征 Eⱼ。
- **流程**：
  1. 对事件特征做卷积并分离通道，分别与 RGB 和深度特征相加（带可学习权重 α,β），得到中间特征 `Q̄ⱼ` 和 `Q̃ⱼ`。
  2. 由中间特征预测偏移量 Δp̄ⱼ, Δp̃ⱼ 及对应的权重。
  3. 利用动态卷积（DCNv2 形式）对 Iⱼ 和 Sⱼ 进行像素重分布，得到对齐后的特征 Îⱼ, Ŝⱼ。
  4. 将对齐后的 RGB‑D 特征相加并通过卷积融合，输出 Fⱼ。
- **辅助损失**：结构感知损失 Lₛₜᵣ 约束 Îⱼ 与 Ŝⱼ 的梯度一致性，减少自运动导致的 RGB‑D 不一致。

### 2.3 局部深度滤波（LDF）
- **输入**：解码器第 i 阶段的深度特征 Dᵢ 和事件特征 Eᵢ。
- **流程**：
  1. 类似 EMA，基于深度和事件特征预测偏移量与调制权重，对 Dᵢ 做动态卷积得到 D̂ᵢ。
  2. 由 Eᵢ 经单通道卷积 + Sigmoid 预测运动掩码 mᵢ（0~1）。
  3. 利用掩码组合精细化深度：`D̊ᵢ = mᵢ·D̂ᵢ + (1−mᵢ)·Dᵢ`。
- **辅助损失**：运动感知损失 Lₘₒₜ 仅作用于运动掩码超过均值的区域，让这部分预测深度更接近真值。

### 2.4 总损失函数
- 重建损失：Lᵣₑ = 1/n (‖D−Z‖₂² + ‖D−Z‖₁)
- 总损失：Lₜ = Lᵣₑ + λ·Lₛₜᵣ + μ·Lₘₒₜ，其中 λ=1，μ=0.1。

## 3. 实验设计

### 3.1 数据集
论文建立了首个事件驱动深度补全基准，包含三个数据集：
- **EventDC‑Real**（真实场景）：手持/机器人采集，传感器包括 FLIR 彩色相机、Ouster OS1‑128 LiDAR、DAVIS346 事件相机；14,845 训练 / 1,000 测试，分辨率 320×256。
- **EventDC‑SemiSyn**（半合成）：基于 KITTI 原始数据，对彩色图像施加径向运动模糊，并用 VID2E 由连续帧生成事件；7,094 训练 / 2,213 测试，分辨率 1216×256。
- **EventDC‑FullSyn**（全合成）：CARLA 模拟器生成，同样添加运动模糊；21,000 训练 / 500 测试，分辨率 512×256。

### 3.2 对比方法
与多种代表性深度补全方法对比，所有方法均在上述三个数据集上从头重新训练以保证公平：
- CSPN, S2D, FusionNet, RigNet, DySPN, Prompting, OGNI-DC, SigNet, LPNet。
- 评价指标：RMSE (mm), MAE (mm), REL, δ1.05, δ1.10, δ1.15。

## 4. 资源与算力

- **硬件**：2 块 NVIDIA RTX 4090 GPU。
- **训练策略**：Distributed Data Parallel；优化器 AdamW；OneCycle 学习率策略（warm‑up 10% 迭代从 2e‑5 升至 1e‑3，随后余弦退火至 2e‑4）；批大小每 GPU 为 2（总批大小 4）。
- **训练时长**：文中未明确给出总训练时间或 epoch 数，但提供了推理速度（41.5 ms/帧，RTX 4090）。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 在 3 个数据集上分别进行全面的定量对比（含多个指标）。
  - 消融实验（EventDC‑i 到 ‑ix）共 9 组变体，系统验证各模态、动态卷积、EMA、LDF 的作用。
  - 复杂度分析：比较参数量、显存占用、推理时间。
  - 定性分析：误差图、深度可视化、特征分布直方图。
- **充分性与公平性**：
  - 所有对比方法均在同一基准上重训，消除数据差异影响。
  - 消融实验逐步叠加组件，因果关系清晰。
  - 实验覆盖真实、半合成、全合成三种域，检验了泛化性。
  - 实验结果充分支撑了论文的核心主张。

## 6. 论文的主要结论与发现

- 事件数据能够有效补偿动态场景中传统 RGB‑D 传感器的不足，显著提升深度补全在运动区域的精度。
- 提出的 EMA 模块通过事件调制对齐显著改善了 RGB 与 LiDAR 特征的一致性；LDF 模块则利用事件预测运动掩码，在物体边界和移动物体周围恢复更精确的局部深度。
- EventDC 在三个数据集上均以较大优势超越现有方法（如 RMSE 在 EventDC‑Real 上比次优方法低 84.1 mm），同时具有较低的参数量和显存开销。
- 构建的基准数据集为事件驱动深度补全研究提供了标准化评测平台。

## 7. 优点

- **首个事件驱动深度补全方法**，填补了领域空白。
- **模块设计合理且有效**：EMA 和 LDF 分别针对全局错位和局部深度误差，分工明确，效果显著。
- **损失函数配合设计**：结构感知损失和运动感知损失进一步增强了训练信号。
- **实验全面扎实**：三个数据集、多种对比方法、详细的消融与复杂度分析，结论可信。
- **模型效率**：在取得最佳性能的同时，参数和显存消耗远低于部分大型方法（如 Prompting）。
- **公开基准**：所建数据集有助于社区开展后续研究。

## 8. 不足与局限

- **传感器要求高**：严重依赖高质量事件数据和精确的多传感器标定，实际部署中可能难以保障。
- **计算开销**：EMA 与 LDF 虽提升了精度，但引入额外计算，推理速度仍有优化空间（41.5 ms），可能不适用于极低延迟场景。
- **数据集局限**：真实数据集规模较小，场景多样性有限；合成数据集中的事件由图像生成（VID2E），与真实事件分布可能存在差异，对真实世界泛化性待进一步验证。
- **未充分讨论鲁棒性**：如对传感器噪声、不同运动模式、极端光照等条件下的表现缺乏专门实验。
- **应用限制**：在资源受限的边缘设备上部署可能较为困难，且需要事件相机这一特殊硬件。

（完）
