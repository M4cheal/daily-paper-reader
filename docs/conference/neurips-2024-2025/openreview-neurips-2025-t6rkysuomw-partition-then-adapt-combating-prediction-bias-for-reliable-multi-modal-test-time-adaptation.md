---
title: "Partition-Then-Adapt: Combating Prediction Bias for Reliable Multi-Modal Test-Time Adaptation"
title_zh: 分区然后自适应：为可靠的多模态测试时间自适应消除预测偏差
authors: "Guowei Wang, Fan Lyu, Changxing Ding"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=T6RkYsuoMW"
tags: ["query:tta"]
score: 9.0
evidence: 多模态测试时间自适应
tldr: 现有TTA方法主要针对单模态领域偏移，多模态同时偏移时因预测偏差而失效。本文提出PTA方法，包含分区与去偏重加权（PDR）和多模态注意力引导对齐（AGA）两部分。PDR根据预测标签频率分布划分批次并重新加权，AGA用注意力机制对齐多模态特征。实验表明在多模态偏移场景下显著提升识别准确率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 多模态同时领域偏移时现有TTA由于预测偏差难以利用可靠样本。
method: 采用分区重加权降低预测偏差，并结合注意力引导的多模态对齐。
result: 在多个多模态数据集上优于现有单模态和多模态TTA方法。
conclusion: 提供了一种有效应对多模态领域偏移的TTA解决方案。
---

## Abstract
Existing test-time adaptation (TTA) methods primarily focus on scenarios involving domain shifts in a single modality. However, they often prove ineffective when multiple modalities simultaneously undergo domain shifts, as they struggle to identify and utilize reliable samples within testing batches amid severe prediction bias. To address this problem, we propose Partition-Then-Adapt (PTA), a novel approach combating prediction bias for TTA with multi-modal domain shifts. PTA comprises two key components: Partition and Debiased Reweighting (PDR) and multi-modal Attention-Guided Alignment (AGA). Specifically, PDR evaluates each sample’s predicted label frequency relative to the batch average, partitioning the batch into potential reliable and unreliable subsets. It then reweights each sample by jointly assessing its bias and confidence levels through a quantile-based approach. By applying weighted entropy loss, PTA simultaneously promotes learning from reliable subsets and discourages reliance on unreliable ones. Moreover, AGA regularizes PDR to focus on semantically meaningful multi-modal cues. Extensive experiments validate the effectiveness of PTA, surpassing state-of-the-art method by 6.1\% on Kinetics50-MC and 5.8\% on VGGSound-MC, respectively. Code of this paper is available at https://github.com/MPI-Lab/PTA.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
现有测试时间自适应（TTA）方法主要针对单模态领域偏移场景，即仅一个模态（如视频或音频）发生分布变化。然而在实际多模态应用中（如自动驾驶、视频理解），多个模态可能同时遭受领域偏移（如光照变化影响视觉，背景噪声影响音频）。此时，预训练模型在融合多模态特征时会产生严重的预测偏差，导致模型输出集中在少量类别上（即“平凡解”），且高置信度样本中大量为假阳性。传统方法依赖置信度或熵来筛选可靠样本，但在多模态同时偏移下失效。为此，论文提出**PTA（Partition-Then-Adapt）**，通过对抗预测偏差实现可靠的多模态测试时间自适应。

## 2. 论文提出的方法论：核心思想、关键技术细节
### 核心思想
将在线数据批次划分为“潜在可靠”和“潜在不可靠”子集，然后分别赋予正/负权重进行熵优化，并利用注意力引导对齐使得不可靠样本的注意力分布向可靠样本靠拢。

### 关键技术细节
- **Partition and Debiased Reweighting (PDR)**  
  1. **偏度量**：对每个样本，计算其预测标签在批次内的出现频率 \(Z(x)\)，定义偏差水平为 \(\bar{Z} - Z(x)\)，其中 \(\bar{Z}\) 是批次平均频率。  
  2. **分区**：将样本划分为 \(X^+\)（偏差较小，即 \(Z \ge \bar{Z}\)）和 \(X^-\)（偏差较大）。  
  3. **分位数重加权**：对 \(X^+\) 中的样本，联合考虑其偏差水平和置信度（softmax 最大值），通过分位数排名得到权重 \(Q(Z^+)\cdot Q(K^+)\)；对 \(X^-\) 中的样本，统一赋予固定负权重 \(-s\)（\(s \ge 0\)）。  
  4. **加权熵损失**：对 \(X^+\) 做熵最小化（鼓励学习），对 \(X^-\) 做熵最大化（抑制错误传播），公式为 \(\mathcal{H}(X) = -I(X) \cdot \sum p \log p\)。

- **Multi-modal Attention-Guided Alignment (AGA)**  
  熵最大化可能导致不可靠样本的注意力图趋近均匀分布，从而忽视有意义的跨模态线索。AGA 采用最大均值差异（MMD）正则化，将可靠子集 \(X^+\) 的注意力分布 \(A^+\) 作为引导，约束不可靠子集 \(A^-\) 的分布与之对齐，从而保留语义有效的多模态信息。

- **总体损失**：\(\mathcal{L}(X) = \mathcal{H}(X) + \lambda \cdot \mathcal{R}(A^+, A^-)\)，其中 \(\mathcal{R}\) 为 MMD 项。

## 3. 实验设计
### 数据集与场景
- **合成偏移**：  
  - Kinetics50-MC 和 VGGSound-MC：视频应用15种常见损坏（高斯噪声、模糊等，5级严重度），音频应用6种真实/合成噪声（共90种组合）。  
- **真实偏移**：  
  - CMU-MOSI、CMU-MOSEI、CH-SIMS：文本、音频、视频三模态情感分析，跨域评估。

### Benchmark
对比方法包括：TENT、ETA、MMTTA、READ、SuMi、ABPEM 等单模态和多模态 TTA 方法。

### 评估指标
主要使用分类准确率（Accuracy）。所有实验重复5次随机种子并报告平均值。

## 4. 资源与算力
文中说明：所有实验在**1块 NVIDIA 4090 GPU** 上运行。未提及具体训练时长，但提到推理效率与其他方法相当（图6展示了样本吞吐量和可训练参数量）。

## 5. 实验数量与充分性
### 实验组别
- **主实验**：在 Kinetics50-MC 和 VGGSound-MC 上对比7种方法（15种视频损坏×6种音频损坏，共90组合，最高严重度5）。  
- **真实场景**：3个三模态数据集上的迁移实验（9个源→目标组合）。  
- **消融实验**：  
  - 组件贡献（基线 vs +PDR vs +PDR+AGA）  
  - 不同重加权策略对比（LE、EW、RA等）  
  - PDR 超参数（s、λ、学习率、可调参数）  
  - AGA 变体（不同注意力块组合、MMD vs MSE/L2/KL）  
- **额外分析**：  
  - 动态环境（不同严重度组合）  
  - 单模态偏移对比（仅视频/音频损坏）  
  - 连续 TTA 设置  
  - 不同批次大小、CIFAR-10/100-C 和 ImageNet-C 单模态验证、CLIP 模型验证。

**充分性**：实验覆盖合成与真实偏移、单/多模态、静态/动态环境、消融全面，对比方法均为当时 SOTA，结果客观公平。

## 6. 论文的主要结论与发现
- 现有方法在多模态同时偏移下因预测偏差失效，高置信度样本中假阳性增多。  
- PDR 通过联合评估预测偏差和置信度，有效区分可靠与不可靠样本，并采用正/负重加权熵损失，显著减少错误累积。  
- AGA 通过 MMD 对齐注意力分布，防止不可靠样本的注意力退化，保持了语义多模态信息。  
- PTA 在 Kinetics50-MC 上比此前最好方法（READ）平均高 6.1%，在 VGGSound-MC 上高 5.8%，在真实场景情感数据集上也全面领先。  
- 在单模态偏移下同样优于或持平现有方法，且对动态环境和连续 TTA 具有鲁棒性。

## 7. 优点
- **问题新颖且实际**：首次系统研究多模态测试时间自适应中同时发生多模态领域偏移的挑战。  
- **方法巧妙**：基于预测标签频率的偏度量简单有效，分位数重加权避免了噪声影响。  
- **双重机制**：PDR 负责样本级别的可靠/不可靠分离，AGA 负责注意力级别的语义保持，两者互补。  
- **实验扎实**：90种合成组合+3个真实场景+大量消融，结果统计充分。  
- **效率可接受**：可训练参数量约2.5M，吞吐率与其他方法相近。

## 8. 不足与局限
- **效率仍需提升**：虽然与其他方法持平，但实际部署可能仍有进一步加速空间（文中在附录H提及）。  
- **仅测试单GPU**：未探索多GPU并行加速。  
- **未提及对隐私/公平性的影响**（附录I声称无负面影响）。  
- **超参数 s 和 λ 依赖简单搜索**：虽给出默认值（s=0.5, λ=1），但未提供严格的自适应选择策略。  
- **实验仅基于 CAV-MAE 架构**：在其他多模态架构（如更大规模的视听模型）上的泛化性未验证。

（完）
