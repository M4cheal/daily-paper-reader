---
title: Lifelong Test-Time Adaptation via Online Learning in Tracked Low-Dimensional Subspace
title_zh: 通过跟踪低维子空间中的在线学习实现终身测试时自适应
authors: "Dexin Duan, Rui Xu, Peilin Liu, Fei Wen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=NFvAa2hNzH"
tags: ["query:tta"]
score: 9.0
evidence: 在跟踪的低维子空间中进行在线学习实现终身测试时自适应
tldr: 现有测试时自适应方法因熵欺骗样本导致退化。本文发现梯度低维结构，区分真实样本与欺骗样本，并在跟踪的低维子空间中进行在线学习，避免退化。该方法在连续分布偏移场景下保持高精度，推动终身测试时自适应发展。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfvaa2hnzh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 951, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfvaa2hnzh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1001, \"height\": 911, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfvaa2hnzh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1013, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfvaa2hnzh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1145, \"height\": 1208, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfvaa2hnzh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 711, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfvaa2hnzh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1426, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfvaa2hnzh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1430, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfvaa2hnzh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1421, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfvaa2hnzh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1423, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfvaa2hnzh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1414, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfvaa2hnzh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1381, \"height\": 1068, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1216, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 569, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 738, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 812, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1028, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1450, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1449, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1444, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1443, \"height\": 131, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfvaa2hnzh/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 134, \"label\": \"Table\"}]"
motivation: 熵最小化导致退化，因欺骗样本产生低熵错误预测。
method: 基于梯度低维性，在跟踪的低维子空间中进行在线学习。
result: 在多个持续分布偏移数据集上抑制退化，提升自适应鲁棒性。
conclusion: 利用梯度结构可实现更稳定的终身测试时自适应。
---

## Abstract
Test-time adaptation (TTA) aims to adapt a source model to a target domain using only test data. Existing methods predominantly rely on unsupervised entropy minimization or its variants, which suffer from degeneration, leading to trivial solutions with low-entropy but inaccurate predictions. In this work, we identify *entropy-deceptive* (ED) samples, instances where the model makes highly confident yet incorrect predictions, as the underlying cause of degeneration. Further, we reveal that the gradients of entropy minimization in TTA have an intrinsic low-dimensional structure, driven primarily by *entropy-truthful* (ET) samples whose gradients are highly correlated. In contrast, ED samples have scattered, less correlated gradients. Leveraging this observation, we show that the detrimental impact of ED samples can be suppressed by constraining model updates within the principal subspace of backward gradients. Building on this insight, we propose LCoTTA, a lifelong continual TTA method that tracks the principal subspace of gradients online and utilizes their projections onto this subspace for adaptation. Further, we provide theoretical analysis to show that the proposed subspace-based method can enhance the robustness against detrimental ED samples. Extensive experiments demonstrate that LCoTTA effectively overcomes degeneration and significantly outperforms existing methods in long-term continual adaptation scenarios. Code is available online.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

测试时自适应（Test-time Adaptation, TTA）旨在仅利用测试数据将源模型适应到目标域，因无需源数据而极具实用性。然而，现有TTA方法大多依赖无监督熵最小化（Entropy Minimization, EM）或其变体，在持续自适应（lifelong continual TTA）场景中容易发生**退化**：模型产生低熵但高错误率的预测（即“平凡解”）。作者识别出退化问题的根本原因在于**熵欺骗样本**（Entropy-Deceptive, ED samples）——模型对它们做出高度自信但错误的预测。EM在优化时会被这些样本误导，导致误差累积和性能崩溃。

## 2. 方法论

### 核心思想
- 引入**熵可靠性分数**（ERS）来量化预测可靠性，区分**熵真实样本**（ET samples，ERS>0）和熵欺骗样本（ERS≤0）。
- 发现ET样本的梯度高度相关，形成低维主子空间；而ED样本的梯度分散、相关性弱。因此，将模型更新约束在梯度主子空间中，可以有效抑制ED样本的不良影响。
- 提出**LCoTTA**：在线跟踪梯度主子空间，将梯度投影到该子空间后用于参数更新，实现稳定、鲁棒的终身TTA。

### 关键技术细节
1. **问题形式化**：模型参数θ，批数据Bt，熵损失Le。梯度gt = ∇θ Le(Bt; θ)。
2. **梯度低维结构分析**：收集最近k个梯度构成矩阵Gt ∈ ℝ^{n×k}，对其进行PCA，提取前r个主成分构成子空间Ur,t。实验表明前10个主成分可解释超过90%方差。
3. **子空间投影更新**：将当前梯度gt投影到子空间再反投影：ĝt = Ur,t Ur,t^T gt；参数更新：θ_{t+1} = θ_t - η ĝt。
4. **在线跟踪**：动态维护梯度队列（长度k），每隔一定间隔（如每50次迭代）重新计算子空间。仅更新归一化层参数（BN/LN）以节省内存。
5. **与熵过滤结合**：先滤除高熵（模糊）样本，使子空间更纯粹地捕捉ET方向。

### 理论支撑（Theorem 1）
在局部平衡邻域内，全空间SGD的稳定性条件为ET梯度漂移需超过ED偏差与扩散噪声之和。子空间投影后，由于ED偏差被大幅消除（Pr ĝED ≈ 0），且扩散噪声由Σ_{i=1}^n λ_i + nσ²_ED降为Σ_{i=1}^r λ_i + rσ²_ED（r≪n），稳定性条件被显著放宽，从而增强了鲁棒性。

## 3. 实验设计

### 数据集与场景
- **ImageNetC**：15种损坏，5种严重级别，主要用severity=5。长期设置：50个循环，每个循环遍历所有15种损坏（每类50000样本），共3.75×10^7样本。
- **CIFAR100C**：类似损坏，100个循环（1.5×10^7样本）。
- **CarlaTTA**（语义分割）：day2night, clear2fog, clear2rain, dynamic setting四个场景。
- **Cityscapes**（语义分割可视化）：实际城市街景在损坏下的持续适应。

### Benchmark指标
- 分类任务：top-1 accuracy（%）
- 分割任务：mIoU（%）

### 对比方法
包括AdaContrast、BN、TENT、CoTTA、SAR、RoTTA、ETA、PETAL、DeYO、BeCoTTA、AEA、TCA等SOTA方法。论文还报告了单个循环的标准TTA结果（单epoch适应）以展示短程竞争力。

## 4. 资源与算力

- **主实验（50 cycles TTA）**：使用8块NVIDIA V100 GPU（32GB内存），Intel Xeon Platinum 8280 CPU @ 2.70GHz。
- **消融实验与效率分析**：单块NVIDIA RTX 3090 GPU（24GB内存）。
- 未明确报告单次训练总时长，但提供了各方法的运行时间对比（ImageNetC单循环）：LCoTTA耗时257.6秒，内存10.67 GB，与TENT（241.1秒/10.37 GB）相当，远低于CoTTA（659.9秒/10.86 GB）等。

## 5. 实验数量与充分性

论文进行了：
- **主要长期实验**：ImageNetC 50 cycles（两种架构ResNet-50, ViT-B/16）、CIFAR100C 100 cycles（ResNeXt-29）。
- **短期单循环实验**：各数据集上报告每个损坏类型的准确率。
- **消融实验**：子空间投影 vs 无策略/仅熵过滤/仅子空间；子空间维度r（10,25,50,100）；梯度队列长度k；采样间隔；学习率鲁棒性；子空间跟踪方式（固定/延迟/在线）的对比。
- **分割任务实验**：4种场景的mIoU，以及Cityscapes可视化。
- **统计分析**：5个不同随机种子的标准差。
- **理论分析**：定理证明与局部稳定性条件。

实验覆盖了多个架构、多种分布偏移、长短期场景，且与当前主流方法公平对比（部分结果直接引用原文）。实验设计充分、客观，结论稳健。

## 6. 主要结论与发现

- ED样本是导致EM退化**根本原因**，ET样本梯度形成低维主结构。
- 通过将参数更新约束在梯度主子空间，可**有效抑制ED样本影响**，避免长期自适应中的性能崩溃。
- LCoTTA在ImageNetC、CIFAR100C、语义分割任务上**显著优于**所有对比方法，尤其是在50-100循环的极端长期场景中保持稳定高精度，而其他方法（如Tent、CoTTA）性能急剧下降。
- 子空间投影增强了**学习率鲁棒性**，减少超参数调优需求。
- 方法**计算开销低**，仅需存储梯度队列和进行PCA（n很小），与Tent复杂度相近。

## 7. 优点

- **理论深度**：首次解释EM退化的根源（ED样本）和梯度低维结构，并提供局部稳定性证明。
- **方法简洁且有效**：在线子空间跟踪+投影更新，无需教师网络、模型重置、额外正则化，即可实现强鲁棒性。
- **通用性**：适用于BN和LN架构，可用于分类和分割任务，在短时和长时场景均表现优异。
- **实验充分**：对比大量基线，包含消融、鲁棒性分析、可视化，验证了各方面设计。
- **效率高**：内存和计算开销合理，适合实际部署。

## 8. 不足与局限

- **固定子空间维度r**：论文仅使用固定值（r=25），未实现自适应选择。可能在不同分布漂移强度下需要不同r，文中承认“adaptive selection may further improve performance”。
- **理论分析局部性**：稳定性定理仅在局部平衡邻域有效，对全局动态缺乏完整刻画。
- **对极端分布可能不完全鲁棒**：虽然方法显著提升了鲁棒性，但在非常严重的分布偏移或噪声下，子空间可能受到污染（通过熵过滤部分缓解，但未彻底消除）。
- **仅更新归一化层**：虽然节省内存、效果良好，但可能限制模型学习能力（如全参数微调可能带来更优性能，但内存开销大）。
- **数据集多样性有限**：主要基于合成损坏（ImageNetC、CIFAR100C），真实域漂移（如自然天气变化）仅通过Carla模拟评估，未在更复杂的开放场景测试。

（完）
