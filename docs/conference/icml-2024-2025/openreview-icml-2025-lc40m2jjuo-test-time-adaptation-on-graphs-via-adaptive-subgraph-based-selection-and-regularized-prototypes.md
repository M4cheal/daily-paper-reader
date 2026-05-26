---
title: Test-time Adaptation on Graphs via Adaptive Subgraph-based Selection and Regularized Prototypes
title_zh: 基于自适应子图选择与正则化原型的图测试时自适应
authors: "Yusheng Zhao, Qixin Zhang, Xiao Luo, Junyu Luo, Wei Ju, Zhiping Xiao, Ming Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=lC40m2jjUO"
tags: ["query:tta"]
score: 8.0
evidence: 图数据上的测试时自适应，采用子图选择与正则化
tldr: 本文针对图数据上的测试时自适应问题，提出ASSESS方法。该方法通过自适应子图选择与正则化原型监督，在不依赖源数据的情况下，有效缓解图神经网络的测试时域偏移。实验表明，ASSESS在多个图域偏移数据集上显著优于现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lc40m2jjuo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1757, \"height\": 999, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lc40m2jjuo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 769, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lc40m2jjuo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 850, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lc40m2jjuo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 755, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lc40m2jjuo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1746, \"height\": 604, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lc40m2jjuo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1765, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lc40m2jjuo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1763, \"height\": 471, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lc40m2jjuo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 808, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lc40m2jjuo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 802, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lc40m2jjuo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 893, \"height\": 185, \"label\": \"Table\"}]"
motivation: 现有测试时自适应主要针对欧氏数据，图数据上的研究匮乏，且面临域偏移性能下降。
method: 提出ASSESS，结合自适应子图选择与正则化原型监督，在测试阶段调整模型。
result: 在多个图域偏移基准上，ASSESS显著提升分类准确率，且适应稳定。
conclusion: 该工作为图数据上的测试时自适应提供了有效且鲁棒的方法。
---

## Abstract
Test-time adaptation aims to adapt a well-trained model using test data only, without accessing training data. It is a crucial topic in machine learning, enabling a wide range of applications in the real world, especially when it comes to data privacy. While existing works on test-time adaptation primarily focus on Euclidean data, research on non-Euclidean graph data remains scarce. Prevalent graph neural network methods could encounter serious performance degradation in the face of test-time domain shifts. In this work, we propose a novel method named Adaptive Subgraph-based Selection and Regularized Prototype Supervision (ASSESS) for reliable test-time adaptation on graphs. Specifically, to achieve flexible selection of reliable test graphs, ASSESS adopts an adaptive selection strategy based on fine-grained individual-level subgraph mutual information. Moreover, to utilize the information from both training and test graphs, ASSESS constructs semantic prototypes from the well-trained model as prior knowledge from the unknown training graphs and optimizes the posterior given the unlabeled test graphs. We also provide a theoretical analysis of the proposed algorithm. Extensive experiments verify the effectiveness of ASSESS against various baselines.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有测试时自适应（Test-time Adaptation, TTA）方法主要针对欧氏数据（如图像、文本），而图数据（非欧氏结构）上的研究非常稀缺。图神经网络（GNN）在遇到测试时的分布偏移（如图结构、节点属性变化）时，性能会严重下降。
- **动机**：实际应用中，训练数据常因隐私保护不可得，仅能获得预训练模型。因此需要一种无需访问源数据、仅利用测试图数据进行自适应的方案。
- **挑战**：
  1. **标签稀缺**：测试图无标签，且结构偏移导致模型预测不可靠，伪标签噪声大。
  2. **知识利用**：自适应时需平衡训练图知识（先验）与测试图信息（后验），防止过拟合或欠适应。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：先通过自适应子图选择（ASBS）筛选出可靠的测试图，再对这些图进行正则化原型监督（RPS）自训练，同时利用互信息估计与原型贝叶斯更新。
- **关键技术细节**：
  - **自适应子图选择（ASBS）**：
    - 为每个测试图计算其与随机子图之间的互信息（MI），使用 Jensen-Shannon MI 估计器。
    - 基于 MI 修正每个图的置信度阈值：$\tau_G = \tau_0 - \omega \hat{I}_\theta(G;\tilde{G})$，实现个体级、结构感知的选择。
    - 采用时序集成（exponential moving average）稳定 MI 估计。
  - **正则化原型监督（RPS）**：
    - 从已训练模型的最后一层权重初始化类别原型 $\mathbf{R}$。
    - 利用贝叶斯公式，将原型后验最大化分解为：先验正则项 $\|\mathbf{R}-\mathbf{W}\|_2^2$ 与基于 Sinkhorn-Knopp 算法求解的软分配自监督项 $\sum_i q(G,i)\|f_\theta(G)-\mathbf{r}_i\|_2^2$。
    - 最终损失：$L = L_{\text{RPS}} + \alpha_2 L_{\text{MI}}$，其中 $L_{\text{RPS}}$ 在可靠图上计算，$L_{\text{MI}}$ 在整个测试集上计算。
  - **课程学习**：逐步提高基准阈值 $\tau_0$，先宽松后严格。
- **算法流程**：迭代进行选择-训练-更新阈值，直至收敛。

## 3. 实验设计
- **数据集**：5个真实世界图数据集，涵盖化学、生物、社交网络：
  - FRANKENSTEIN, Mutagenicity, PROTEINS, NCI1, IMDB-BINARY。
  - 每个数据集按图密度分成三个子集（如 F0, F1, F2），构成源-目标域偏移（共6种迁移方向）。
- **对比方法**：
  - 基础 GNN：GCN, GraphSAGE, GIN, GAT。
  - 无监督/半监督：MeanTeacher, GraphCL。
  - 测试时自适应方法：SHOT, TAST, RNA。
- **评估指标**：分类准确率（%），每实验重复多次取均值与标准差。

## 4. 资源与算力
- **明确说明**：使用 NVIDIA A40 GPU，优化器为 Adam，学习率 $10^{-4}$，默认超参数（$\omega=0.1$, $\alpha_1=0.1$, $\alpha_2=10^{-2}$）。
- **未明确**：未提及 GPU 数量、总训练时长（仅给出每 epoch 时间，约 0.04~0.21 秒/epoch，epoch 数 10~30）。算力开销较小。

## 5. 实验数量与充分性
- **实验数量**：覆盖 5 个数据集，每个数据集 6 种迁移方向，共 30 个实验设置；与 9 种基线对比；另外进行了消融实验、参数敏感性分析、可视化（t-SNE）、选择精度分析。
- **充分性**：实验设计较全面，基线覆盖了 GNN、自监督、TTA 三类方法；消融验证了 ASBS 和 RPS 各组件有效性；参数敏感性显示鲁棒性；可视化定性支持。
- **客观公平**：采用多次重复报告均值与标准差，统计严谨；但未提供显著性检验。

## 6. 主要结论与发现
- ASSESS 在所有数据集上平均准确率显著优于所有基线（例如在 PROTEINS 上平均 78.9% 对比次优 75.4%）。
- 自适应子图选择比统一阈值或类级阈值能选出更可靠的测试图（选择精度约 0.8）。
- 正则化原型监督有效平衡了先验知识与后验自适应，防止灾难性遗忘。
- 模型对超参数不敏感，适应过程稳定。

## 7. 优点
- **问题新颖实用**：首次系统研究图数据上的测试时自适应，解决了数据隐私与域偏移的实际需求。
- **方法创新**：将子图互信息用于个体级选择阈值，贝叶斯框架形式化原型正则化，理论推导收敛性（Theorem 3.1）。
- **实验扎实**：多数据集、多基线、多角度验证。
- **计算高效**：时间复杂度与普通 GNN 同阶（$O(N_{\text{te}}E)$），适应仅需数秒。

## 8. 不足与局限
- **仅考虑离线 TTA**：所有测试输入同时可用，未探索在线（streaming）场景。
- **域偏移类型单一**：仅按图密度划分，未覆盖更复杂的结构/属性协同偏移。
- **理论假设较强**：收敛性证明依赖 Tsybakov 条件、PL 条件等，实际中可能不严格满足。
- **超参数依赖**：需手动调节基阈值 $\tau_0$、课时策略等，缺乏自动调整机制。
- **实验偏差风险**：虽有多数据集，但均为中等规模（千级图），未在超大规模图上验证。
- **应用局限**：仅针对图分类任务，未拓展到节点级或边级任务。

（完）
