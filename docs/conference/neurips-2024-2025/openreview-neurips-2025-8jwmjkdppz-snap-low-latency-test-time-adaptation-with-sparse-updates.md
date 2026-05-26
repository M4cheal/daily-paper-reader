---
title: "SNAP: Low-Latency Test-Time Adaptation with Sparse Updates"
title_zh: SNAP：基于稀疏更新的低延迟测试时自适应
authors: "Hyeongheon Cha, Dong Min Kim, Hye Won Chung, Taesik Gong, Sung-Ju Lee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=8JwMjKDppz"
tags: ["query:tta"]
score: 8.0
evidence: 基于稀疏更新的低延迟测试时自适应用于流式数据
tldr: "SNAP针对边缘环境中测试时自适应计算成本高的问题，提出稀疏更新框架。通过类别和领域代表性记忆模块，仅从流数据中选取1%的样本进行自适应，仍能保持高精度。方法降低了适应频率和数据使用量，适用于资源受限的流式场景。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-8jwmjkdppz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8jwmjkdppz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 730, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8jwmjkdppz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8jwmjkdppz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8jwmjkdppz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 875, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8jwmjkdppz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 698, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8jwmjkdppz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 435, \"height\": 274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8jwmjkdppz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8jwmjkdppz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 713, \"height\": 453, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 785, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 759, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 740, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 879, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 879, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 880, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1025, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 598, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1452, \"height\": 648, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1444, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1173, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1449, \"height\": 557, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1020, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1452, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1440, \"height\": 117, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 480, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 440, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1447, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1446, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1445, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 524, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1446, \"height\": 1725, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1447, \"height\": 1397, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1446, \"height\": 1725, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1447, \"height\": 1398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1446, \"height\": 1724, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1446, \"height\": 1398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1454, \"height\": 814, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8jwmjkdppz/table-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1452, \"height\": 811, \"label\": \"Table\"}]"
motivation: 现有测试时自适应方法频率高、计算成本大，不适合边缘设备。
method: 提出类别和领域代表性记忆，仅对关键样本进行稀疏更新。
result: "仅使用1%的流数据样本即可保持竞争性精度，大幅降低延迟。"
conclusion: 稀疏更新策略为边缘设备上的测试时自适应提供了实用且高效的方案。
---

## Abstract
Test-Time Adaptation (TTA) adjusts models using unlabeled test data to handle dynamic distribution shifts. However, existing methods rely on frequent adaptation and high computational cost, making them unsuitable for resource-constrained edge environments. To address this, we propose SNAP, a sparse TTA framework that reduces adaptation frequency and data usage while preserving accuracy. SNAP maintains competitive accuracy even when adapting based on only 1\% of the incoming data stream, demonstrating its robustness under infrequent updates. Our method introduces two key components: (i) Class and Domain Representative Memory (CnDRM), which identifies and stores a small set of samples that are representative of both class and domain characteristics to support efficient adaptation with limited data; and (ii) Inference-only Batch-aware Memory Normalization (IoBMN), which dynamically adjusts normalization statistics at inference time by leveraging these representative samples, enabling efficient alignment to shifting target domains. Integrated with five state-of-the-art TTA algorithms, SNAP reduces latency by up to 93.12\%, while keeping the accuracy drop below 3.3\%, even across adaptation rates ranging from 1\% to 50\%. This demonstrates its strong potential for practical use on edge devices serving latency-sensitive applications. The source code is available at https://github.com/chahh9808/SNAP.

---

## 论文详细总结（自动生成）

# 论文总结：SNAP: Low-Latency Test-Time Adaptation with Sparse Updates

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：测试时自适应（Test-Time Adaptation, TTA）通过利用无标注的测试数据流来调整模型，以应对部署环境中的分布偏移。然而，现有TTA方法通常依赖频繁的模型更新和高计算开销（如反向传播、数据增强、模型集成），这导致在资源受限的边缘设备（如树莓派、Jetson Nano）上产生严重的延迟瓶颈，无法满足延迟敏感型应用（如自动驾驶、实时健康监测）的需求。
- **核心挑战**：在边缘设备上，既要保证TTA的性能，又要大幅降低每批次的延迟，同时适应不同速率的流式数据。
- **整体含义**：作者提出一种“稀疏TTA”（Sparse TTA, STTA）策略，通过降低更新频率来减少计算开销，但直接降低频率会导致性能严重下降。因此需要设计高效的样本选择机制，使得在极少的更新次数下仍能保持模型精度。

## 2. 方法论

- **核心思想**：构建一个轻量级的稀疏TTA框架SNAP，包含两个关键组件：**类别与领域代表性记忆（CnDRM）** 和 **仅推理的批量感知记忆归一化（IoBMN）**。
- **CnDRM**：
  - 维护一个有限容量的记忆库（大小等于批大小），用于存储对自适应最具信息量的样本。
  - **类别代表性**：选择高置信度（伪标签概率高）且类别预测平衡的样本，避免低置信度样本带来的噪声。
  - **领域代表性**：利用早期归一化层的特征统计量（均值、方差），计算每个样本与当前域质心之间的Wasserstein距离，选择距离最近的样本。
  - 域质心通过动量更新（beta=0.9）平滑跟踪流数据分布。
  - 当记忆库满时，删除被预测类别中离域质心最远的样本，确保库内保持类别平衡且域代表性。
- **IoBMN**：
  - 在推理阶段（非自适应批次），利用CnDRM记忆样本的归一化统计量（记忆均值、方差），并基于当前推理批次的统计量通过软收缩函数（soft shrinkage）进行修正，得到矫正后的归一化参数。
  - 公式：`μ_IoBMN = μ_m + S_λ(μ_c - μ_m; α s_μm)`，其中`S_λ(x; λ) = sign(x)·max(|x|-λ, 0)`，α控制对记忆统计的依赖程度。
  - 这样做可以缓解稀疏更新导致的统计量老化，使模型在非自适应批次也能保持与当前数据分布的对齐。
- **算法流程**：每个批次先通过前向传播获取样本特征和置信度，将合格样本加入CnDRM；每k个批次（由自适应率控制）执行一次基于CnDRM中所有样本的模型更新；在非更新批次，使用IoBMN进行归一化。

## 3. 实验设计

- **数据集**：
  - 主要基准：CIFAR10-C、CIFAR100-C、ImageNet-C（各15种损坏，最高严重程度）。
  - 额外泛化测试：ImageNet-R、ImageNet-Sketch。
  - 连续分布偏移场景：ImageNet-C按顺序流式输入所有损坏类型。
  - 持久性偏移场景：基于CIFAR10-C循环10轮的持久TTA设置。
- **模型**：ResNet18（CIFAR系列）、ResNet50（ImageNet-C）、ViT-Base（部分实验）。
- **对比方法**：五种SOTA TTA算法：Tent、CoTTA、EATA、SAR、RoTTA。对比它们在完全自适应（AR=1）和不同稀疏自适应率（AR=0.01, 0.03, 0.05, 0.1, 0.3, 0.5）下的性能，以及集成SNAP后的性能。
- **评价指标**：分类准确率（平均15种损坏）和每批次平均延迟（在树莓派4、Jetson Nano、树莓派Zero 2 W上测量）。
- **消融实验**：评估CnDRM（类别代表性 vs 域代表性 vs 二者结合）、IoBMN（对比EMA、标准BN等）的贡献。

## 4. 资源与算力

- 论文未明确说明训练总GPU小时数，但提到：
  - 精度测量使用NVIDIA GeForce RTX 3090 GPU。
  - 延迟测量使用CPU-only的边缘设备（树莓派4、零号2W、Jetson Nano）。
  - 所有实验运行3个随机种子（0,1,2）。
- 未报告完整的训练时长或总计算量。

## 5. 实验数量与充分性

- **实验数量**：非常丰富。包括3个主要数据集（每个含15种损坏）× 6种自适应率 × 5种TTA方法 × 3个种子 = 大量组合；加上两种额外数据集、ViT实验、连续/持久偏移、单样本自适应、学习率/记忆大小分析、消融实验等。附录中提供了完整数据表格。
- **充分性**：实验设计比较充分，覆盖了多种常见分布偏移、不同模型架构、多种自适应率和边缘硬件。对比了5种主流TTA方法，并做了消融。但缺少对真实移动端应用（如视频流）的端到端延迟测量，也未与更多前向传播式TTA（如T3A、FOA）进行系统比较（附录B.10有部分比较）。
- **公平性**：使用了官方实现和推荐超参数；对于自适应率实验，保持了统一的学习率（但附录B.17表明学习率对稀疏自适应有显著影响，这可能是潜在的混淆因素）。整体而言实验方法客观。

## 6. 主要结论与发现

- SNAP在自适应率低至0.1（即仅使用10%的流数据）时，能将所有五种TTA方法的延迟降低最多93.12%（如CoTTA），同时精度下降不超过3.3%。
- 即使在自适应率0.01（仅1%数据）时，SNAP仍能保持接近完全自适应的准确率。
- 在连续和持久性分布偏移下，SNAP比朴素STTA稳定性显著更好，能防止模型崩溃。
- 在ViT上同样有效，实现高达2.9×延迟降低且精度不减。
- 与内存效率TTA模块MECTA兼容，可进一步降低峰值内存32%。
- 消融表明CnDRM和IoBMN缺一不可，二者协同效果最佳。

## 7. 优点

- **实践导向**：直面边缘设备延迟瓶颈，提出可落地的稀疏更新框架，而非仅仅追求精度。
- **方法简洁高效**：CnDRM和IoBMN设计轻量，易于集成到现有TTA方法中。
- **实验全面**：覆盖多种数据集、模型、硬件、自适应率、偏移类型；消融和超参数分析详实。
- **鲁棒性验证**：在连续/持久偏移、单样本（BS=1）极端条件下均有良好表现。
- **代码开源**：提供完整源码，促进可复现性。

## 8. 不足与局限

- **自适应率固定**：使用全局固定自适应率，未能根据分布漂移程度或系统负载动态调整。
- **置信度阈值固定**：CnDRM的置信度阈值为定值，可能不适应不同数据特性。
- **理论分析较弱**：附录B.1的理论分析较简略，缺乏严格的泛化界。
- **硬件覆盖有限**：仅测试了三款边缘设备，未覆盖更多常见嵌入式平台（如手机芯片、MCU）。
- **学习率敏感性**：实验结果（附录B.17）显示稀疏自适应时需要调高学习率，但主实验使用固定学习率，可能未达到最优折衷。
- **延迟测量粒度**：论文测量的是每批次平均延迟，未对不同批次类型的延迟分布（如更新批次 vs. 推理批次）做详细分解，也未考虑真正的实时流约束（如帧率匹配）。
- **与前沿前向式TTA比较不足**：与T3A、FOA的比较仅见于附录，且后者在ViT上性能不如SNAP，但在CNN上是否有直接比较？缺乏全面对比。

（完）
