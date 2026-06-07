# 日报 · 2026-06-07

- 生成时间：2026-06-07 21:18:32 UTC
- 当次推荐总数：1
- 精读区：1
- 速读区：0

## 今日简报（AI）
今日精读了一篇关于RGB-红外目标检测的融合新作，探讨如何复用融合时刻的光谱可靠性来动态路由专家与自适应特征融合。
最值得关注的方向是：光谱可靠性不是一次性信号，它可以被存下来作为融合质量的“记忆”，用于后续自适应融合权重分配和专家网络选择，在跨模态检测中显著提升鲁棒性。
如果你也在做多模态感知，建议回头检查你的融合模块是否有可复用的中间质量度量——把不确定性的“历史”用起来，可能比堆更多融合层更有效。

## 精读区
1. [Reusing Fusion-Time Spectral Reliability for Adaptive Fusion and Expert Routing in RGB-Infrared Object Detection](/202606/07/2606.01173v1-reusing-fusion-time-spectral-reliability-for-adaptive-fusion-and-expert-routing-in-rgb-infrared-object-detection) （8.0/10）

## 速读区
- 本次无速读推荐。

---
使用键盘方向键可在日报/论文之间快速切换。
