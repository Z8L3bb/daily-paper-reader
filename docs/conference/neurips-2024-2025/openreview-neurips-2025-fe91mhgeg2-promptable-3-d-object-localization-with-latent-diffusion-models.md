---
title: Promptable 3-D Object Localization with Latent Diffusion Models
title_zh: 基于潜在扩散模型的可提示三维物体定位
authors: "Cheng-Yao Hong, Li-Heng Wang, Tyng-Luh Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=FE91MHgEg2"
tags: ["query:lidar-d-det"]
score: 6.0
evidence: 提出基于扩散模型的可提示3D物体检测，可应用于点云
tldr: 针对现有3D检测方法依赖直接坐标回归导致灵活性和适应性不足的问题，本文提出基于潜在扩散模型的可提示三维物体定位框架，将检测转化为噪声到包围盒的扩散过程，支持灵活的文本或条件引导。该方法为3D物体检测提供了一种新颖的生成式范式，有潜力应用于点云等数据形式的检测任务。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fe91mhgeg2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fe91mhgeg2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1424, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fe91mhgeg2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fe91mhgeg2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 694, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fe91mhgeg2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 744, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fe91mhgeg2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1076, \"height\": 2365, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 588, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 826, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 770, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 633, \"height\": 168, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 838, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1435, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1443, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1441, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fe91mhgeg2/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1441, \"height\": 349, \"label\": \"Table\"}]"
motivation: 现有3D检测方法多依赖坐标回归，限制了灵活的条件引导检测。
method: 将检测建模为扩散过程，通过编码边界框为令牌实现可提示的3D物体识别框架。
result: 在多个3D检测基准上展示了扩散模型的有效性和灵活性。
conclusion: 扩散模型为3D物体检测提供了一种新的灵活范式，支持开放词汇和条件引导。
---

## Abstract
Accurate identification and localization of objects in 3-D scenes are essential for advancing comprehensive 3-D scene understanding. Although diffusion models have demonstrated impressive capabilities across a broad spectrum of computer vision tasks, their potential in both 2-D and 3-D object detection remains underexplored. Existing approaches typically formulate detection as a ''noise-to-box'' process, but they rely heavily on direct coordinate regression, which limits adaptability for more advanced tasks such as grounding-based object detection. To overcome these challenges, we propose a promptable 3-D object recognition framework, which introduces a diffusion-based paradigm for flexible and conditionally guided 3-D object detection. Our approach encodes bounding boxes into latent representations and employs latent diffusion models to realize a ''promptable noise-to-box'' transformation. This formulation enables the refinement of standard 3-D object detection using textual prompts, such as class labels. Moreover, it naturally extends to grounding object detection through conditioning on natural language descriptions, and generalizes effectively to few-shot learning by incorporating annotated exemplars as visual prompts. We conduct thorough evaluations on three key 3-D object recognition tasks: general 3-D object detection, few-shot detection, and grounding-based detection. Experimental results demonstrate that our framework achieves competitive performance relative to state-of-the-art methods, validating its effectiveness, versatility, and broad applicability in 3-D computer vision.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的结构化中文总结。

### 1. 论文的核心问题与整体含义

本论文着眼于 **3D 场景理解中的物体检测任务**，核心研究动机在于：

-   **现有范式局限**：当前主流的 3D 物体检测方法，包括演进中的扩散模型（如 DiffusionDet）方案，大多依赖从“噪声到边界框 （noise-to-box）”的直接坐标回归。这种方式在处理需要更强条件引导的复杂任务（如基于文本的物体定位、小样本检测）时，适应性和灵活性不足。
-   **整体含义**：论文提出一个**统一、可提示（promptable）的 3D 物体定位框架**，将检测过程重塑为在潜在空间中的条件扩散生成过程。通过将边界框编码到潜在空间，并借助条件（如类别文本、自然语言描述、少量标注样例）引导去噪过程，使得一个单一模型能够灵活应对**通用检测、小样本检测和基于语言描述的目标定位**这三类关键 3D 视觉任务。

### 2. 论文提出的方法论

论文的核心创新在于将**潜在扩散模型 （Latent Diffusion Models, LDMs）** 与 3D 物体检测相结合，构建了一个名为“可提示噪声到边界框”的框架。其主要技术细节分三部分：

-   **语言引导的物体锚点特征**：
    -   使用视觉-语言基础模型 （如 CLIP2Point 或 Uni3D） 从点云中提取 3D 视觉特征，并将其与类别名称的文本嵌入通过**交叉注意力机制**进行融合。
    -   融合后的特征作为富含语义信息的“物体锚点” （Object Anchors），充当后续扩散过程的查询 （Query），其作用类似于 DETR 架构中的物体查询，但信息更为丰富。

-   **盒子表示（Box VAE）**：
    -   借鉴 V-DETR 设计一个**变分自编码器 （VAE）**，将物体的锚点特征、初始化的边界框坐标与全局场景特征共同编码到一个紧凑的**潜在表示 ˆb**中。
    -   编码器包含自注意力与交叉注意力模块，用于建模物体间关系和场景上下文。解码器则负责从潜在表示中重构和优化最终的边界框。

-   **条件潜在扩散模型进行盒子优化**：
    -   核心过程是在 Box VAE 生成的潜在表示 **ˆb** 上执行扩散与去噪。前向过程对 **ˆb** 加噪，得到**ˆb_t**。
    -   模型学习一个去噪网络，该网络不直接预测边界框，而是**预测潜在空间中的噪声**，训练目标为：**Lθ = ∥ϵθ(ˆbt， c， t) − ϵ∥2**。其中，c 是任务相关的条件输入。
    -   推理时，从随机噪声开始，通过 DDIM 采样迭代去噪，最终通过 Box VAE 解码器得到精确的 3D 边界框。不同任务仅需调整条件输入 **c**：
        -   **通用检测**：类别名称的文本嵌入。
        -   **小样本检测**：新类别少量标注样例的视觉特征。
        -   **语言目标定位**：自然语言的指代表达式。

### 3. 实验设计

论文在三个核心 3D 物体识别任务上进行了评估，覆盖多个标准基准：

-   **通用 3D 物体检测**：
    -   **数据集**：ScanNetV2 （18类）， SUN RGB-D （10类）。
    -   **评价指标**：IoU 阈值为 0.25 和 0.5 时的平均精度 （mAP@25， mAP@50）。
    -   **对比方法**：传统的 VoteNet， DETR 系列方法 （3DETR， Group-Free， V-DETR） 以及扩散模型检测器 （Diffusion-SS3D， Diff3DETR， CatFree3D）。

-   **小样本 3D 物体检测**：
    -   **数据集**：FS-SUNRGBD （10类， 6/4划分）， FS-ScanNet （18类， 12/6划分）。
    -   **评价指标**：在 1-shot， 3-shot， 5-shot 设置下的 mAP@25 和 mAP@50。
    -   **对比方法**：VoteNet， GeneralizedFS3D， Meta-Det3D， 以及基于原型学习的方法 （Prototypical-VoteNet， Prototypical-VAE）。

-   **基于语言描述的目标定位**：
    -   **数据集**：ScanRefer （单目标）， Multi3DRefer （多目标）， ViGiL3D （混合诊断）， OpenLex3D （开放词汇，零样本）。
    -   **评价指标**：IoU 阈值为 0.25 和 0.5 时的准确率 （Acc@25/50） 和 F1-Score （F1@25/50）。
    -   **对比方法**：ScanRefer， Multi3DRefer， D-LISA， Chat-Scene， PQ3D 等。

### 4. 资源与算力

论文在“Training and loss functions”一节明确说明了使用的算力资源：

-   **GPU型号与数量**：8 块 **NVIDIA RTX A6000 Ada** GPU。
-   **训练细节**：
    -   总训练迭代次数：18K 次迭代。
    -   有效批量大小 （Batch Size）：8，并通过梯度累积 16 步来模拟更大的批量。
    -   优化器与学习率：使用 Adam 优化器，初始学习率 5×10-4，带 500 步线性预热的余弦退火调度。

### 5. 实验数量与充分性

实验设计较为全面和充分，旨在从多维度验证方法的有效性、鲁棒性和灵活性。

-   **多任务评估**：实验覆盖了三个性质完全不同的 3D 物体检测任务，从闭集检测到小样本泛化再到开放词汇定位，充分验证了模型的统一性和“可提示”能力。
-   **多数据集与基准**：在至少 8 个不同的数据集或基准上进行了评估，包括 ScanNetV2， SUN RGB-D， FS-SUNRGBD， FS-ScanNet， ScanRefer， Multi3DRefer， ViGiL3D 和 OpenLex3D。
-   **丰富的对比方法**：与各类任务的代表性 SOTA 方法进行了广泛比较，涵盖传统方法、DETR 系列和扩散模型系列。
-   **全面的消融实验**：对模型的三个核心组件（语言引导锚点、潜在扩散优化、可提示条件）进行了消融研究，清晰展示了每个组件对性能的贡献。此外，还额外分析了不同初始盒子策略、基础模型选择和锚点数量的影响，结论客观。

### 6. 论文的主要结论与发现

-   **有效性与竞争力**：提出的方法在通用 3D 物体检测任务上达到了与最先进方法媲美的性能，尤其是在 ScanNetV2 数据集上，相比其他扩散模型检测器有显著提升。
-   **灵活性与统一性**：该框架成功地将单一模型应用于三种截然不同的 3D 检测任务，仅通过改变条件输入即可实现，展示了卓越的“可提示”能力和通用性。
-   **关键模块贡献**：
    -   **可提示条件机制**对语言驱动的定位任务至关重要。
    -   **潜在扩散优化**在小样本等数据稀缺场景下提供了鲁棒的学习能力。
    -   **语言引导的锚点**增强了语义对齐，提升了开放词汇场景的性能。
-   **范式革新潜力**：论文认为，将扩散过程引入潜在空间并结合多模态条件，为 3D 物体检测提供了一种更灵活、更强大的新范式，打破了现有方法对直接坐标回归的依赖。

### 7. 优点

-   **高度原创与统一**：首次将潜在扩散模型系统性地用于统一多种 3D 物体检测任务，提出“可提示”的噪声到边界框范式，思想新颖。
-   **技术方案精巧**：将 Box VAE 与 LDM 结合，实现从坐标空间到潜在空间的转换与优化，解决了直接回归的局限性，并利用了预训练的视频 LDM 权重，加速了模型收敛。
-   **实验全面详实**：在三大类任务、八个基准上进行了充分的实验论证，提供了丰富的消融研究和加速变体分析，结论可靠，说服力强。
-   **强适应性与泛化能力**：在小样本和开放词汇场景下的表现尤为突出，验证了其在数据稀缺和语义理解要求高的情况下的优势。

### 8. 不足与局限

-   **计算效率**：作者明确指出，基于扩散模型的迭代去噪过程计算开销较大，虽然提供了 LCM-LoRA 加速方案，但在实时性要求高的应用中可能仍是瓶颈。
-   **模态局限**：目前的条件输入主要限于文本和视觉模态，对于音频或视频等更为复杂的提示形式尚未探索。
-   **基础模型依赖与偏差**：方法依赖于视觉-语言基础模型 （如 CLIP， Uni3D），因此可能继承这些预训练模型中存在的偏见，影响在实际场景下部署的公平性。
-   **实验覆盖范围**：评估主要集中在室内场景数据集，其在室外大规模自动驾驶场景（如 nuScenes， Waymo）上的表现和泛化能力有待验证。

（完）
