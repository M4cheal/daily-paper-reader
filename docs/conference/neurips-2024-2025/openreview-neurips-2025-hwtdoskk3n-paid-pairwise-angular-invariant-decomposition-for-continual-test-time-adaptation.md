---
title: "PAID: Pairwise Angular-Invariant Decomposition for Continual Test-Time Adaptation"
title_zh: "PAID: 用于连续测试时自适应的成对角度不变分解"
authors: "Kunyu Wang, Xueyang Fu, Yuanfei Bao, Chengjie Ge, Chengzhi Cao, Wei Zhai, Zheng-Jun Zha"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=HWTdOSKK3n"
tags: ["query:tta"]
score: 8.0
evidence: 利用几何不变分解进行连续测试时自适应以应对流式数据
tldr: 连续测试时自适应（CTTA）需要模型在线适应不断变化的环境。现有方法仅关注目标数据，忽略了预训练权重中蕴含的域不变先验。PAID系统分析了权重的几何属性，发现成对角度结构在不同域中保持稳定，以此设计成对角度不变分解。实验表明PAID在多个连续域偏移数据集上显著减少了灾难性遗忘，并提升了适应性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-hwtdoskk3n/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hwtdoskk3n/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hwtdoskk3n/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hwtdoskk3n/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hwtdoskk3n/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 789, \"height\": 843, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hwtdoskk3n/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1425, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hwtdoskk3n/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 352, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 129, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 655, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 740, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1444, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1447, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1447, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hwtdoskk3n/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1440, \"height\": 206, \"label\": \"Table\"}]"
motivation: 现有连续测试时自适应方法忽略预训练权重的域不变几何信息，导致在流式数据中性能下降。
method: 提取预训练权重的成对角度结构作为域不变先验，在自适应过程中保留该结构，同时更新其他几何分量。
result: 在CIFAR-10C等连续域偏移数据集上，PAID优于现有CTTA方法，有效缓解了遗忘问题。
conclusion: PAID揭示了预训练权重的几何结构价值，为在线流式场景下的自适应提供了新思路。
---

## Abstract
Continual Test-Time Adaptation (CTTA) aims to online adapt a pre-trained model to changing environments during inference. Most existing methods focus on exploiting target data, while overlooking another crucial source of information, the pre-trained weights, which encode underutilized domain-invariant priors. This paper takes the geometric attributes of pre-trained weights as a starting point, systematically analyzing three key components: magnitude, absolute angle, and pairwise angular structure. We find that the pairwise angular structure remains stable across diverse corrupted domains and encodes domain-invariant semantic information, suggesting it should be preserved during adaptation. Based on this insight, we propose PAID (Pairwise Angular Invariant Decomposition), a prior-driven CTTA method that decomposes weight into magnitude and direction, and introduces a learnable orthogonal matrix via Householder reflections to globally rotate direction while preserving the pairwise angular structure. During adaptation, only the magnitudes and the orthogonal matrices are updated. PAID achieves consistent improvements over recent SOTA methods on four widely used CTTA benchmarks, demonstrating that preserving pairwise angular structure offers a simple yet effective principle for CTTA. Our code is available at https://github.com/wangkunyu241/PAID.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：持续测试时自适应（CTTA）旨在使预训练模型在推理过程中在线适应不断变化的目标环境。现有方法大多聚焦于利用目标域数据，而忽略了预训练权重中蕴含的域不变先验。
- **核心动机**：作者从预训练权重的几何属性出发，系统地分析了三个分量：幅度（magnitude）、绝对角度（absolute angle）和成对角度结构（pairwise angular structure）。通过统计、功能和可视化实验发现：成对角度结构在不同损坏域下保持稳定，且编码了与语义相关的域不变信息，应在自适应过程中予以保留；而幅度和绝对角度则反映域特定变化，可被调整。
- **整体含义**：提出一种先验驱动的CTTA方法，通过保留成对角度结构来缓解灾难性遗忘和误差累积，提升在线自适应性能。

---

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将预训练线性权重分解为幅度矩阵 \(M\) 和方向矩阵 \(\hat{W}\)，冻结方向矩阵，引入可学习正交矩阵 \(O\) 对方向进行全局旋转，从而在调整绝对角度的同时保持成对角度结构不变。仅更新幅度和正交矩阵。
- **关键技术细节**：
  - 权重分解：\(W = M \odot \hat{W}\)，其中 \(\hat{W}\) 每列为单位向量。
  - 正交矩阵构造：使用 Householder 反射链 \(O = \prod_{i=1}^r (I - 2 u_i u_i^\top)\)，\(u_i\) 为单位向量，\(r\) 为可调系数（控制表达能力与效率的权衡）。
  - 自适应过程：冻结原始方向矩阵 \(\hat{W}\)，仅更新幅度 \(M\) 和正交矩阵 \(O\)：\(W' = M \odot (\hat{W} \cdot O)\)。
- **优化目标**：采用特征分布对齐损失，对齐源域（预计算统计量 \(\mu_s, \sigma_s\)）与目标域当前批次的特征均值与标准差：\(\mathcal{L} = \|\mu_s - \mu_t\|^2 + \lambda \|\sigma_s - \sigma_t\|^2\)。特征取自 ViT 的 CLS token 经最后层归一化后的输出。
- **理论解释**：将 pairwise angular structure 类比于傅里叶变换中的相位谱（保留语义），将幅度和绝对角度类比为幅度谱（对域变化敏感）。并利用线性分类模型在类无关损坏（可通过共享正交变换适应）与类相关语义偏移（必须改变角度结构）下的理论分析，证明设计的合理性。

---

### 3. 实验设计：使用的数据集/场景、基准、对比方法

- **数据集**：
  - 分类任务：CIFAR10 → CIFAR10-C、CIFAR100 → CIFAR100-C、ImageNet → ImageNet-C（各含 15 种损坏类型，最高严重程度）。
  - 分割任务：Cityscapes → ACDC（含 Fog、Night、Rain、Snow 四种恶劣条件，循环 3 轮）。
- **基准**：四个标准 CTTA 基准，按分类错误率（↓）或 mIoU（↑）评估。
- **对比方法**：Source、Pseudo、TENT、CoTTA、VDP、SAR、RoTTA、EcoTTA、ViDA、C-MAE 等。此外还对比了 LoRA、DoRA 等参数高效微调方法。
- **骨干网络**：分类使用 ViT-Base（输入 224×224 或 384×384）；分割使用 Segformer-B5。另在附录中扩展到 CNN 骨干（ResNet-50、ResNeXt-29、WideResNet-28）。

---

### 4. 资源与算力

- 文中明确说明：实验在 **NVIDIA RTX 3090 GPU** 上进行。
- 未提及具体的 GPU 数量、训练时长或总计算量。仅提供了相对计算时间（归一化于 TENT）和可学习参数量（1.24M，额外参数较少），说明开销适中。

---

### 5. 实验数量与充分性

- **实验组数**：在 4 个基准（3 分类 + 1 分割）上与 10 余种 SOTA 方法对比；消融实验包括：组件选择（幅度/方向/正交注入）、正交矩阵系数 \(r\)、源样本数、批大小、损失平衡系数 \(\lambda\)、线性层注入位置、10 轮循环 CTTA、卷积骨干扩展等。
- **充分性与公平性**：对比方法均来自公开代码库或论文一致报道；消融实验系统且全面，验证了每个设计选择的重要性；额外提供了注意力图可视化及理论分析支持结论。实验设置符合领域惯例，结果具有可复现性和说服力。

---

### 6. 论文的主要结论与发现

- 预训练权重的 **成对角度结构** 是域不变的语义先验，在自适应过程中应被保留；而幅度和绝对角度是域特定分量，可以在保留该结构的前提下调整。
- 提出的 **PAID** 方法通过 Householder 反射链实现结构保留的全局旋转，在四个 CTTA 基准上均取得最优或最优秀的平均性能，提升幅度显著（如 ImageNet-C 上降低错误率 13.6%，CIFAR100-C 降低 10.5%，ACDC 分割提升 mIoU 5.5%）。
- 保留成对角度结构不仅提升性能，还能使注意力聚焦于语义区域，且计算开销较小。

---

### 7. 优点：方法与实验设计的亮点

- **视角新颖**：从权重几何结构出发，揭示了被忽略的预训练先验，提供了 CTTA 的新方向。
- **方法简洁有效**：仅需引入可学习正交矩阵和幅度更新，无需复杂模块或多次前向传播。
- **理论支撑充实**：包括频率类比（相位 vs 幅度）、线性分类器下的理论分析、以及消融实验、注意力可视化等多角度证据。
- **实验全面**：涵盖分类与分割、ViT 与 CNN 骨干、多种损坏类型、多轮循环、超参数敏感性分析，对比方法代表性强。
- **高效性**：额外参数少（1.24M），前向/反向次数仅为 1，相对时间开销低，优于多次前向的方法。

---

### 8. 不足与局限

- **假设的泛化边界**：方法核心假设“成对角度结构在域偏移下保持稳定”可能不适用于极度非平稳或类相关语义偏移场景（如开放世界类别变化），文中虽有理论分析但未充分实验验证。
- **超参数依赖**：损失平衡系数 \(\lambda\) 和正交矩阵系数 \(r\) 在不同数据集上需手动调整（如 ImageNet-C 对 \(\lambda=0.1\) 更优，CIFAR 需 \(\lambda=1.0\)）；缺乏自动调优策略。
- **批大小敏感**：当批大小 ≤4 时性能下降明显，限制了在单样本或小批量实际场景下的应用。
- **未探索极端任务**：未测试少样本学习、终身学习等更复杂的连续自适应场景，方法的通用性有待进一步验证。
- **计算资源细节缺失**：未提供训练 GPU 数量、总耗时、能耗等，不利于计算成本评估。

---

（完）
