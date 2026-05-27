---
title: Towards Learning to Complete Anything in Lidar
title_zh: 学习在激光雷达中完成任意物体
authors: "Ayça Takmaz, Cristiano Saltori, Neehar Peri, Tim Meinhardt, Riccardo de Lutio, Laura Leal-Taixé, Aljosa Osep"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vWPzKn6usZ"
tags: ["query:lidar-d-det"]
score: 6.0
evidence: 利用多模态时序上下文进行零样本LiDAR形状补全
tldr: 针对现有LiDAR场景补全方法只能处理封闭词汇的问题，提出CAL零样本方法。利用多模态传感器序列的时序上下文挖掘物体形状和语义特征，并将其蒸馏到纯LiDAR模型中，实现任意物体的形状补全与识别。实验表明该模型能从多个部分观测中推断完整形状，为开放词汇点云补全提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1652, \"height\": 946, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1758, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 838, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1514, \"height\": 850, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 815, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1771, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1311, \"height\": 2042, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1516, \"height\": 842, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1765, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 857, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1077, \"height\": 1938, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1249, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1247, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1245, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1244, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1245, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1767, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1720, \"height\": 849, \"label\": \"Table\"}]"
motivation: 现有LiDAR补全方法受限于封闭词汇的标注数据集，无法泛化到开放世界中的任意物体。
method: 提出CAL，利用多模态时序上下文挖掘物体形状与语义，通过知识蒸馏训练纯LiDAR模型进行实例级补全和识别。
result: 实验表明蒸馏后的模型能从多个部分观测中学习推断完整形状，在开放词汇补全上表现良好。
conclusion: CAL为LiDAR点云的开放词汇形状补全提供了新范式，提升了点云感知的泛化能力。
---

## Abstract
We propose CAL (Complete Anything in Lidar) for Lidar-based shape-completion in-the-wild. This is closely related to Lidar-based semantic/panoptic scene completion. However, contemporary methods can only complete and recognize objects from a closed vocabulary labeled in existing Lidar datasets. Different to that, our zero-shot approach leverages the temporal context from multi-modal sensor sequences to mine object shapes and semantic features of observed objects. These are then distilled into a Lidar-only instance-level completion and recognition model. Although we only mine partial shape completions, we find that our distilled model learns to infer full object shapes from multiple such partial observations across the dataset. We show that our model can be prompted on standard benchmarks for Semantic and Panoptic Scene Completion, localize objects as (amodal) 3D bounding boxes, and recognize objects beyond fixed class vocabularies.

---

## 论文详细总结（自动生成）

好的，以下是对论文《Towards Learning to Complete Anything in Lidar》的结构化深度总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：当前的激光雷达（LiDAR）场景补全方法（如语义场景补全SSC、全景场景补全PSC）存在一个关键瓶颈——它们只能在**闭集词汇**（即训练数据中标注过的特定类别，如车辆、行人等约20类）下完成和识别物体，泛化能力有限。
*   **研究动机与整体含义**：论文旨在打破闭集限制，实现**零样本（Zero-Shot）的LiDAR全景场景补全**。核心目标是使模型仅凭单帧稀疏的LiDAR点云，就能补全出任意物体的完整三维形状，并允许在测试时通过文本提示来识别物体，从而迈向“在LiDAR中完成任意物体”（Learning to Complete Anything in Lidar）。

### 2. 论文提出的方法论

论文方法（CAL）分为两个核心阶段：**伪标签引擎**和**零样本补全模型**。

*   **伪标签引擎**
    *   **核心思想**：利用无标注的多模态传感器序列（RGB相机 + LiDAR）和强大的2D视觉基础模型，自动挖掘物体的完整三维形状和语义特征作为训练伪标签。
    *   **关键技术细节**：
        1.  **视频对象分割与追踪**：使用SAM（Segment Anything Model）和SAM 2在RGB视频序列中，以类别无关的方式分割和追踪所有可能的物体实例，生成时空掩膜（Masklets）。
        2.  **语义特征聚合**：对每个追踪到的物体实例，使用CLIP模型从多帧图像中提取并聚合视觉-语言特征，得到一个固定的语义嵌入向量。
        3.  **3D投影与聚合**：将2D掩膜通过标定参数反投影到LiDAR坐标系，得到每帧的3D掩膜。然后，利用已知的车辆位姿将多帧3D掩膜累积到同一坐标系下，构建完整的3D形状，并通过多数投票得到每个物体的体素占有率。
        4.  **标签优化**：为了提升标签覆盖率，该方法聚合了360° LiDAR扫描以获得密集的二元占用标签，并利用**条件随机场（CRF）** 在占用区域传播实例标签，从而将仅有部分观测的形状补全为更完整的伪标签。
*   **零样本补全模型**
    *   **核心思想**：训练一个以单帧稀疏LiDAR点云为输入的生成式模型，预测完整的场景级占用、实例掩膜以及每个实例的语义CLIP特征。
    *   **架构与训练**：
        1.  **骨干网络**：采用稀疏-生成3D U-Net架构，包含稀疏特征编码器和密集3D卷积，通过多尺度生成解码器逐步从粗到细地估计完整的场景占用。
        2.  **实例解码器**：使用基于Transformer的查询解码器与占用的体素特征交互，预测一组**类别无关的实例掩膜**，并为每个实例回归一个CLIP特征向量。
        3.  **辅助语义正则化**：为了解决伪标签语义信息缺失和形状学习困难的问题，将实例的CLIP特征聚类成`C`个伪原型（pseudo-prototypes）。训练时，增加一个**伪语义头`S`** 预测每个体素所属的原型类别，作为形状先验的隐式正则化，此预测在测试时不使用。
        4.  **损失函数**：总损失为四个部分的加权和：`L_occ`（二元占用损失）、`L_prot`（原型分类损失）、`L_mask`（实例掩膜损失）、`L_CLIP`（CLIP特征蒸馏损失）。
*   **推理流程**：给定一帧点云，模型输出`K`个实例掩膜和对应的CLIP特征。测试时，用CLIP文本编码器编码用户提供的**开放类别词汇**，通过计算特征间的余弦相似度来为每个实例分配语义标签，实现零样本识别。

### 3. 实验设计

*   **数据集与场景**：实验主要在两大自动驾驶场景的PSC基准上进行：
    *   **SemanticKITTI**：包含19类语义标签，其中8类为“物体”（thing）类别。
    *   **SSCBench-KITTI360**：包含18类语义标签，其中5类为“物体”类别。
*   **基准与对比方法**：
    *   **全监督基准**：与LMSCNet、JS3CNet、SCPNet（均结合MaskPLS）以及当前最优的PaSCo进行对比。这些方法均使用完整的人工标注进行训练。
    *   **零样本基准**：由于无直接可比的零样本PSC方法，论文构建了两个强大的基线：将LODE和LiDiff（两类完成补全的模型）与SAL（一个零样本全景分割模型）相结合，以在补全后的点云上进行分割和识别。
*   **评估指标**：语义场景补全使用**mIoU**；全景场景补全使用**全景质量（PQ†、SQ、RQ）**。为解耦补全和识别性能，区分了**语义预言机（SO）** 和**零样本（ZS）** 两种评估设置。

### 4. 资源与算力

*   **硬件配置**：论文在“Further Implementation Details”部分明确指出，模型训练使用了**8块NVIDIA A100 GPU**。
*   **训练时长**：训练周期为**50个epochs**，批处理大小为8（每块GPU处理1个样本）。

### 5. 实验数量与充分性

实验设计**丰富、客观且公平**，具体体现在：

*   **主要对比实验**：在2个数据集上对比了4个全监督和2个精心构建的零样本基线。
*   **消融实验**：
    1.  **伪标签引擎分析**：研究了前/后向追踪帧数（`T_fw`， `T_bw`）、步长（`w`）及CRF精炼对伪标签质量的影响。
    2.  **伪标签覆盖度分析**：量化了掩膜标签和二元占用标签在不同阶段（有无CRF，有无360°聚合）的覆盖率。
    3.  **模型组件分析**：系统消融了模型的关键设计，包括二元占用头的标签覆盖度、伪语义头（`S`）和辅助二元头（`B_s`）的作用。
    4.  **关键参数敏感性分析**：探讨了CLIP原型数量（`C`）对性能的影响。
    5.  **公平性**：严格限制训练数据规模与全监督基线一致，确保性能提升来源于方法本身而非更多的训练数据。

### 6. 论文的主要结论与发现

*   **任务可行性**：首次证明了在稀疏LiDAR上进行零样本全景场景补全是可行的。
*   **性能优势**：CAL显著优于所有构建的零样本基线，且在不使用任何人工语义标注的情况下，取得了接近甚至超越早期全监督方法的性能（如在SemanticKITTI上，ZS设置下的PQ†达到PaSCo的~50%）。
*   **伪标签有效性**：即使伪标签仅包含部分形状补全信息，通过CRF优化和精心设计的训练策略，蒸馏出的模型也能从数据集中学习到推断完整物体形状的能力。
*   **通用性**：CAL方法不局限于特定类别，能够完成并识别“任意”物体，展示了其在开放词汇3D感知任务（如非模态3D目标检测）上的潜力。

### 7. 优点

*   **创新性强**：首次提出了零样本LiDAR全景补全任务，打破了传统闭集词汇的限制。
*   **方法新颖有效**：巧妙利用2D基础模型和多模态时序上下文，自动挖掘宝贵的3D形状和语义先验，作为训练纯LiDAR模型的“免费”伪标签，框架优雅。
*   **模型设计合理**：在生成式补全基础上引入Transformer实例解码器和CLIP特征蒸馏，并通过伪语义原型、CRF精炼等设计，有效解决了伪标签噪声、不完备等问题。
*   **实验扎实全面**：从伪标签引擎到最终模型，进行了多层次、多维度的对比和消融，论证充分，说服力强。

### 8. 不足与局限

*   **对基础模型的依赖与偏差**：方法的上限受限于所用的2D基础模型（SAM、CLIP）。视频追踪的ID切换、遮挡等错误会导致伪标签噪声和不完整，而零样本识别的性能也直接受CLIP开放词汇能力的影响，对罕见类（如“骑自行车的人”）效果较差。
*   **伪标签计算成本高**：论文承认伪标签引擎的计算开销巨大，尤其是SAM 2在长视频序列上的掩膜传播耗时很长。
*   **覆盖率仍有限**：尽管通过CRF等机制提升了覆盖率，但伪标签仍然无法覆盖场景中的所有区域，尤其是在相机视野盲区或被严重遮挡的区域，存在偏差风险。
*   **性能差距**：与当前最先进的全监督方法（如PaSCo）相比，仍存在较大性能差距，说明人工标注数据所蕴含的精确形状和类别先验知识仍有其不可替代的价值。

（完）
