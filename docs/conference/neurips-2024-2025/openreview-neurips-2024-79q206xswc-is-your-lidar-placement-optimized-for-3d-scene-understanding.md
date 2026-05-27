---
title: Is Your LiDAR Placement Optimized for 3D Scene Understanding?
title_zh: 面向3D场景理解的LiDAR放置优化
authors: "Ye Li, Lingdong Kong, Hanjiang Hu, Xiaohao Xu, Xiaonan Huang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=79q206xswc"
tags: ["query:stage-d-det"]
score: 9.0
evidence: 面向3D场景理解的LiDAR放置优化
tldr: 针对多LiDAR系统放置缺乏优化的问题，提出Place3D全周期流程，包含基于语义占用栅格的代理度量来评估LiDAR配置，并生成数据用于下游评估，显著提升3D场景理解性能。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1419, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1414, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1462, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1456, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1311, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1454, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1410, \"height\": 1343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1409, \"height\": 1347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1466, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1465, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1461, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1462, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1456, \"height\": 1797, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-79q206xswc/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1458, \"height\": 1798, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 152, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 667, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 666, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1369, \"height\": 1613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1444, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1448, \"height\": 1338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1439, \"height\": 1449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1441, \"height\": 1437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-79q206xswc/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1441, \"height\": 1286, \"label\": \"Table\"}]"
motivation: 现有驾驶数据集多采用单LiDAR且缺乏恶劣条件数据，难以反映真实环境复杂性。
method: 提出Place3D流程，引入M-SOG度量优化多LiDAR配置，并生成相应数据。
result: 优化后的LiDAR放置显著提高下游感知任务性能。
conclusion: 为多传感器系统设计提供了系统化评估与优化工具，推动可靠感知。
---

## Abstract
The reliability of driving perception systems under unprecedented conditions is crucial for practical usage. Latest advancements have prompted increasing interest in multi-LiDAR perception. However, prevailing driving datasets predominantly utilize single-LiDAR systems and collect data devoid of adverse conditions, failing to capture the complexities of real-world environments accurately. Addressing these gaps, we proposed Place3D, a full-cycle pipeline that encompasses LiDAR placement optimization, data generation, and downstream evaluations. Our framework makes three appealing contributions. 1) To identify the most effective configurations for multi-LiDAR systems, we introduce the Surrogate Metric of the Semantic Occupancy Grids (M-SOG) to evaluate LiDAR placement quality. 2) Leveraging the M-SOG metric, we propose a novel optimization strategy to refine multi-LiDAR placements. 3) Centered around the theme of multi-condition multi-LiDAR perception, we collect a 280,000-frame dataset from both clean and adverse conditions. Extensive experiments demonstrate that LiDAR placements optimized using our approach outperform various baselines. We showcase exceptional results in both LiDAR semantic segmentation and 3D object detection tasks, under diverse weather and sensor failure conditions.

---

## 论文详细总结（自动生成）

好的，请看以下对论文《Is Your LiDAR Placement Optimized for 3D Scene Understanding?》的总结分析。

### 1. 论文的核心问题与整体含义

*   **核心问题**：当前的自动驾驶感知系统大多依赖于**单一 LiDAR** 配置，且其数据均是在天气良好等**理想条件**下采集的。这忽略了现实世界中复杂的天气状况（雨、雪、雾等）和传感器可能发生的故障。更重要的是，对于如何系统性评估和优化**多 LiDAR** 在车辆上的**放置位置**，以最大化 3D 场景理解（包括物体检测和语义分割）能力，业界缺乏有效的方法，多依赖于直觉和经验。
*   **研究动机**：填补上述空白，通过提出一套全周期的评估与优化流程，系统性地探究不同 LiDAR 配置对下游感知任务性能及鲁棒性的影响，并最终找到接近最优的传感器布局。
*   **整体含义**：本研究旨在证明，通过科学的度量标准和优化算法，可以显著提升多 LiDAR 系统的感知性能和可靠性，为自动驾驶车辆传感器套件的设计提供理论依据和实践工具。

### 2. 论文提出的方法论

论文提出了名为 **Place3D** 的全周期流程，其核心技术包括：

*   **核心思想**：设计一个计算高效的代理度量来评估 LiDAR 配置的质量，然后利用该度量作为目标函数，通过进化算法寻找最优传感器布局。
*   **关键技术细节**：
    1.  **代理度量 (M-SOG)**：
        *   **概率语义占用栅格 (P-SOG)**：将自动驾驶场景的 3D 空间划分为体素。通过聚合多帧语义点云，为每个体素分配一个属于各类别的多项式概率分布，而非简单的二值占用概率。这更精确地描述了物体的物理边界和语义信息。
        *   **M-SOG 计算**：对于某一 LiDAR 配置，利用体素遍历算法找到所有被其激光射线“覆盖”的体素。M-SOG 度量即为这些被覆盖体素的 P-SOG 熵的负平均值。**熵值越低，表示传感器获取的信息确定性越高，即配置越好。**
    2.  **优化策略**：
        *   采用**协方差矩阵自适应进化策略 (CMA-ES)** 来优化 LiDAR 的 3D 坐标和滚转角度。目标函数 `G(u)` 由待最大化的 M-SOG 得分 `F(u)` 和违反物理约束的惩罚项 `λP(u)` 构成。
        *   通过迭代地从多变量正态分布中采样候选配置，评估其 M-SOG，并根据表现最佳的候选解更新搜索分布的均值和协方差矩阵，最终逼近最优配置。
    3.  **数据生成与评估**：利用 CARLA 模拟器，根据优化出的配置自动生成相应的点云数据集，并在清洁和多种恶劣条件下（雪、雾、运动模糊等）训练和评估下游感知模型。

### 3. 实验设计

*   **数据集与场景**：
    *   **自建数据集 (Place3D)**：包含 280,000 帧数据，来自 10 种 LiDAR 配置，涵盖 4 个 CARLA 地图和 6 条路线。
    *   **数据分割**：清洁数据（13,600 帧，用于训练/验证）和腐蚀数据（用于鲁棒性测试，包含 6 种恶劣条件，每种 2,400 帧）。
*   **对比基准 (Baselines)**：
    *   **7 种启发式 LiDAR 放置策略**：包括 Center, Line, Pyramid, Square, Trapezoid, Line-roll, Pyramid-roll，这些配置模拟了 Waymo, Cruise 等主流自动驾驶公司的设计。
    *   **下游任务模型**：
        *   **LiDAR 语义分割**：MinkUNet, SPVCNN, PolarNet, Cylinder3D。
        *   **3D 物体检测**：PointPillars, CenterPoint, BEVFusion-L, FSTR。
    *   **现有传感器放置方法**：对比了 S-MIG 度量，证明 M-SOG 具有更好的线性相关性。

### 4. 资源与算力

*   论文在附录中明确指出，所有 LiDAR 语义分割模型在 **8 块 NVIDIA A100 SXM4 80GB GPU** 上进行训练和测试。
*   所有 3D 物体检测模型在 **4 块 NVIDIA RTX 6000 Ada 48GB GPU** 上进行训练和测试。
*   未提及具体训练总时长。

### 5. 实验数量与充分性

实验设计非常充分，主要体现在：

*   **大量的横纵向对比**：
    *   对比了**7 种启发式 + 多种消融配置**共 10 种 LiDAR 布局。
    *   在**4 种分割模型**和**4 种检测模型**上进行了评估。
    *   在所有配置和模型上，均测试了**1 种清洁 + 6 种恶劣条件**下的性能。
*   **严谨的消融实验**：
    *   **2D 放置优化**：限制 LiDAR 高度相同，验证算法在受限条件下的有效性。
    *   **针对腐蚀条件的优化**：使用腐蚀数据生成的 P-SOG 进行优化，证明了定制化优化对提升鲁棒性的额外价值。
    *   **LiDAR 滚转角影响分析**：探讨了调整角度对分割和检测的不同影响。
*   **客观与公平性**：所有模型均采用统一的训练和评估配置（基于 MMDetection3D 框架），对比公平，指标一致。

### 6. 论文的主要结论与发现

*   **M-SOG 度量有效**：该代理度量与下游感知性能（mIoU/mAP）之间存在清晰的**正线性相关性**，可作为高效评估工具。
*   **优化配置性能优越**：采用 Place3D 优化的 LiDAR 配置，在**清洁和恶劣条件下，其分割和检测性能均显著优于所有启发式基线**，平均提升约 9% 的指标。
*   **鲁棒性强**：优化的配置不仅在清洁数据上表现优异，在面临雪、雾、传感器故障等恶劣条件时，也展现出最强的抗干扰能力。
*   **直觉性规律**：优化结果揭示了一些直观规律，如增加 LiDAR 的平均高度、增大高度差异和更均匀的分散布局有助于提升感知性能。

### 7. 优点

*   **创新性**：首次将 LiDAR 放置优化扩展到 **3D 语义分割任务**和**恶劣条件下的鲁棒性评估**，并提出了更精确的语义代理度量 M-SOG。
*   **系统性**：构建了从评估、优化到数据集生成和下游验证的**全周期流程 (Place3D)**，方法完整，逻辑闭环。
*   **理论支撑**：为优化算法提供了**最优性证明**，确保找到的解是接近全局最优的。
*   **可解释性**：通过分析找到了最有效配置背后的物理直觉，不仅仅是“黑盒”优化。

### 8. 不足与局限

*   **仿真与现实差距**：数据完全依赖 CARLA 模拟器生成，尽管精度高，但与真实世界的传感器噪声、物理特性（如透明物体）仍有差距，结论的实地泛化性有待验证。
*   **LiDAR 类型固定**：研究对象仅限于特定参数的**低通道数 (16线) 旋转式** LiDAR，结论可能不直接适用于半固态/固态 LiDAR 或不同垂直视场角的传感器。
*   **配置的“准最优”性**：CMA-ES 搜索到的配置是近似最优解，且优化空间限于较少参数（位置和滚转角），未考虑所有可能的自由度。
*   **场景泛化性**：研究仅在 CARLA 的几个城镇地图中进行，未在更多样化、更复杂的真实世界道路结构中进行测试。

（完）
