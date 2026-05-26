---
title: Lightweight Online Adaption for Time Series Foundation Model Forecasts
title_zh: 时序基础模型预测的轻量在线自适应
authors: "Thomas L Lee, William Toner, Rajkarn Singh, Artjom Joosen, Martin Asenov"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=gAxYbvoOQz"
tags: ["query:tta"]
score: 8.0
evidence: 时序基础模型的在线自适应
tldr: 针对时序基础模型在线部署时无法适应新数据的问题，本文提出ELF轻量在线自适应机制。它包含ELF预测器学习当前数据分布，以及ELF加权器聚合历史预测。在多个时间序列基准上，ELF显著提升了基础模型在在线环境下的预测精度，且计算开销极小。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1783, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 850, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 838, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 877, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 855, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 855, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 863, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1766, \"height\": 1319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1756, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1758, \"height\": 531, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1529, \"height\": 1524, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1716, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1763, \"height\": 869, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1762, \"height\": 1387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 924, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1613, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1395, \"height\": 1518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1007, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 959, \"height\": 723, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 816, \"height\": 715, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1689, \"height\": 924, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1784, \"height\": 924, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 908, \"height\": 1446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1528, \"height\": 1525, \"label\": \"Table\"}]"
motivation: 时序基础模型部署后因固定权重无法适应新数据分布。
method: 提出ELF机制，包含在线预测器和加权器，利用新数据反馈轻量调整模型输出。
result: 在多个时间序列数据集上提升在线预测精度，计算开销低。
conclusion: 轻量在线自适应可有效提升时序基础模型的预测性能和实时性。
---

## Abstract
Foundation models (FMs) have emerged as a promising approach for time series forecasting. While effective, FMs typically remain fixed during deployment due to the high computational costs of learning them online. Consequently, deployed FMs fail to adapt their forecasts to current data characteristics, despite the availability of online feedback from newly arriving data. This raises the question of whether FM performance can be enhanced by the *efficient* usage of this feedback. We propose *ELF* to answer this question. ELF is a lightweight mechanism for the online adaption of FM forecasts in response to online feedback. ELF consists of two parts: **a)** the *ELF-Forecaster* which is used to learn the current data distribution; and **b)** the *ELF-Weighter* which is used to combine the forecasts of the FM and the ELF-Forecaster. We evaluate the performance of ELF in conjunction with several recent FMs across a suite of standard time series datasets. In *all* of our experiments we find that using ELF improves performance. This work demonstrates how efficient usage of online feedback can be used to improve FM forecasts.

---

## 论文详细总结（自动生成）

# 论文《Lightweight Online Adaption for Time Series Foundation Model Forecasts》中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题**：时间序列基础模型（Foundation Models, FMs）在部署后通常保持固定参数，无法利用新到达的数据反馈（如真实观测值）来适应数据分布的变化或漂移。虽然 FMs 在零样本场景下表现良好，但在在线滚动预测中，其性能会因缺少自适应而受限。
- **动机**：在线场景下，每个时间步都能获得上一轮预测的误差反馈，计算高效地利用这些反馈可以提升 FMs 的预测准确度。
- **整体含义**：提出一种轻量级的在线自适应机制 ELF（Ensembling with online Linear Forecaster），将部署时的 FMs 转化为能动态调整预测的在线模型，同时保持极低的算力开销，使得该方法可以落地到实际应用。

## 2. 论文提出的方法论
### 核心思想
- 不修改 FM 本身的参数，而是通过一个在线训练的轻量线性预测器（ELF-Forecaster）和一个动态加权器（ELF-Weighter）来调整 FM 的最终预测结果，相当于对 FM 与在线预测器进行加权集成。

### 关键技术细节

#### 2.1 ELF-Forecaster（在线轻量预测器）
- **结构**：基于傅里叶域线性模型（受 FITS 启发），将输入上下文 `x ∈ R^L` 经 DFT 变换后丢弃高频分量（保留比例 α=0.9），得到一个低维复向量，再乘以可学习的复数权重矩阵 `W ∈ C^{αL × αH/2}`，经逆实傅里叶变换 iRFT 得到预测 `ˆy ∈ R^H`。
- **在线拟合**：采用正则化最小二乘（OLS），利用 Woodbury 矩阵恒等式高效更新 `(X̃*X̃ + λI)^{-1}`，避免存储全部历史数据；同时通过 Welford 在线算法维护标准差来数值缩放数据。
- **更新频率**：每 M=200 个时间步更新一次（称为一个更新步 τ）。
- **初始化**：线性模型初始化为朴素季节预测器，直到积累足够数据（L+H 步）后才完成首次拟合。

#### 2.2 ELF-Weighter（动态加权器）
- **功能**：根据历史预测误差动态调整 FM 和 ELF-Forecaster 的权重 `w_τ`（0~1），则最终预测为：
  ```
  ˆy_ELF = w_τ * ˆy_FM + (1 - w_τ) * ˆy_EF
  ```
- **结构**：
  - **慢加权器**（Exponential Weighting）：基于全部历史损失，权重更新公式：
    ```
    w_slow_τ = w_slow_{τ-1} e^{-η·Loss_τ,FM} / [ w_slow_{τ-1} e^{-η·Loss_τ,FM} + (1-w_slow_{τ-1}) e^{-η·Loss_τ,EF} ]
    ```
  - **快加权器**：仅使用最近 B=5 个更新步的损失，计算指数权重，更快适应分布漂移。
  - **合并加权器**：再用一个指数加权器动态融合快、慢加权器给出的权重，得到最终 `w_τ`。
- **理论支持**：引用在线学习中的指数加权遗憾界（Theorem 4.1）。

## 3. 实验设计
### 数据集
- **标准数据集**：ETTh1、ETTh2、ETTm1、ETTm2、Weather、Traffic、ECL、Solar、US Weather。这些数据集均未出现在 FM 预训练中（TimesFM 除外，其使用了 Traffic/ECL 训练，因此对这两数据集不报告 TimesFM 结果）。
- **高频率数据集**（每秒采样）：Wind-PerSec、Solar-PerSec、Cloud-PerSec。
- **预测长度**：H ∈ {30, 96, 336}，上下文长度 L=520。

### Benchmark 与对比方法
- **基础模型（FMs）**：TTM（revision 2）、TimesFM、VisionTS、Chronos（tiny）、Moirai（small）。
- **在线自适应对比方法**：
  - TAFAS（基于门控校准的测试时自适应）
  - FSNet（改进的时序卷积网络）
  - OneNet（在线集成双预测器）
  - OneNet-TTM（以 TTM 为组件）
  - 持续微调 TTM（带经验回放的增量更新）
- **指标**：主要使用 MASE（Mean Absolute Scaled Error），同时报告 RMSSE 验证一致性。

### 实验场景
- 模拟滚动窗口部署，每 M=200 步更新一次 ELF；对 baseline 按各自原始设定调整更新频率（OneNet等每步更新，以最大化其性能）。

## 4. 资源与算力
- 论文明确指出所有在线更新与预测均在 **2 个 Intel Xeon Platinum 8168 CPU 上**运行，未使用 GPU 进行 ELF 的更新（FMs 的推理可能依赖 GPU，但 ESF 本身设计为 CPU 友好）。
- **计算效率**：
  - ELF 每个更新步仅需 0.38 秒（CPU）。
  - 对比 TAFAS 为 3.76 秒（10x 慢），OneNet 为 43.12 秒（113x 慢），FSNet 为 23.69 秒（62x 慢），持续微调 TTM 为 911.52 秒（2506x 慢）。
- 未给出 FMs 推理的详细 GPU 配置或训练时长，仅强调 ELF 本身的低开销。

## 5. 实验数量与充分性
- **实验覆盖面**：在 9 个标准数据集和 3 个高频数据集上测试了 5 种 FMs，并对每种 FM + ELF 组合报告了 3 个预测长度的结果，共产生 100+ 组主要结果。
- **消融实验**：
  - 更新频率的影响（图 5）。
  - 频率丢弃比例的影响（图 6, 8；表 C.8）。
  - Woodbury 更新的加速效果（图 7）。
  - 使用不同替换预测器（OGD、FITS、FSNet、残差预测）替代 ELF-Forecaster（表 C.9）。
  - 单独使用快/慢/合并加权器的影响（表 C.10）。
  - 对比未加权平均和 Hedge 算法（表 C.10）。
- **公平性**：对比在线方法时，均按各自原始论文设置（如 OneNet 每个时间步更新），确保比较合理；所有实验在相同滚动窗口条件下重复，指标统一为 MASE/RMSSE。
- **充分性判断**：实验设计较为全面，涵盖了主流 FMs、多种在线方法、多个数据集和消融分析，论证了方法的有效性、鲁棒性和高效性。但缺少在更复杂真实场景（如多步误差累积、缺失值）下的验证。

## 6. 主要结论与发现
- **ELF 始终提升预测性能**：在所有 FM、所有数据集、所有预测长度下，MASE 均降低（绿色标记）。
  - 例如：TTM + ELF 在 ETTh1 (H=30) 上 MASE 从 0.930 降至 0.911；VisionTS + ELF 平均提升超过 10%。
- **计算效率显著优于其他在线方法**：ELF 每个更新步仅 0.38 秒，比最快的对比方法 TAFAS 快 10 倍，比持续微调快 2506 倍。
- **自适应能力**：ELF-Weighter 能快速捕捉分布漂移（如周末模式）；ELF-Forecaster 可学习数据集特有模式（如云服务流量尖峰）从而弥补 FM 的不足。
- **重要结论**：在部署场景中，即使是轻量级在线自适应也能大幅提升 FM 的表现，且不同 FMs 之间的性能差距在使用 ELF 后缩小。

## 7. 优点
1. **轻量且模型无关**：不修改 FM 权重，可插拔应用于任意 FM，仅需 CPU 即可在线运行。
2. **高效在线更新**：利用 Woodbury 恒等式和频率降维实现快速最小二乘更新，避免了高斯过程或梯度下降的高开销。
3. **双重适应机制**：ELF-Forecaster 学习时序特定分布，ELF-Weighter 动态调整集成权重，两者互补。
4. **理论支撑**：加权集成享有在线学习遗憾界；经验验证充分。
5. **实验设计严谨**：覆盖多种 FM、多种数据集、多种预测长度，并按原始 baselines 设定复现对比，结果可靠。

## 8. 不足与局限
1. **实验覆盖范围**：数据集主要集中在电力、天气、交通等领域，未涵盖金融、医疗、传感器网络等更多元类型的时间序列，可能限制通用性论断。
2. **超参数敏感性**：文中固定了 α=0.9、M=200、λ=20、η=0.5 等超参数，虽然声称“a priori 选择”，但未讨论这些参数在不同场景下的鲁棒性。
3. **仅考虑单变量独立预测**（channel independent），忽略了多变量间的相关性，可能丢失跨序列信息（尽管这避免了归一化问题）。
4. **更新频率与延迟假设**：每 M=200 步更新一次，假定新数据以恒定速率到达；在实时性要求极高（如毫秒级）或数据到达不规则时，更新机制可能需要适配。
5. **未解决持续学习中的关键问题**：虽然 ELF 自身避免了灾难性遗忘（线性模型），但未与 FM 的持续微调结合（实验中表明结合后反而更差），不涉及 FM 本身的衰减或塑性损失问题。
6. **基线对比可能不全面**：对比的其他在线方法（如 FSNet、OneNet）多为较早期的深度学习方法，且其最优更新频率设定与 ELF 不同，虽然论文说明了合理性，但仍有改进空间（如对比最新的测试时自适应方法）。
7. **缺少理论解释**：尽管给出了加权集成的遗憾界，但未从理论上证明 ELF 为何总能优于单一 FM 或预测器，更多依赖实验。

（完）
