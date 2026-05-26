---
title: Class-aware Domain Knowledge Fusion and Fission for Continual Test-Time Adaptation
title_zh: 面向持续测试时自适应的类别感知领域知识融合与分裂
authors: "Jiahuan Zhou, Chao Zhu, Zhenyu Cui, Zichen Liu, Xu Zou, Gang Hua"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=F74FXkicGK"
tags: ["query:tta"]
score: 7.0
evidence: 基于类别感知知识融合与分裂的持续测试时自适应
tldr: 该文针对持续测试时自适应中灾难性遗忘与新知学习不足的矛盾，提出类别感知领域知识融合与分裂方法。通过动态管理各类别知识，在适应新域的同时保留历史知识，避免有害干扰。在多域切换场景下，该方法有效提升了模型的持续适应能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-f74fxkicgk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 736, \"height\": 874, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f74fxkicgk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1429, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f74fxkicgk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 576, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f74fxkicgk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 565, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f74fxkicgk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1456, \"height\": 768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f74fxkicgk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 557, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f74fxkicgk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1364, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f74fxkicgk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 873, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f74fxkicgk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 732, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f74fxkicgk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 904, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f74fxkicgk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 876, \"height\": 352, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1460, \"height\": 685, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 652, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1458, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1458, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1459, \"height\": 486, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1183, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 714, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 890, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 710, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1386, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 709, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-f74fxkicgk/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 707, \"height\": 204, \"label\": \"Table\"}]"
motivation: 持续测试时自适应中，现有方法难以平衡新知识学习与历史知识遗忘。
method: 提出类别感知的知识融合与分裂机制，动态管理不同类别知识。
result: 在多个持续自适应基准上，该方法显著缓解了遗忘并提升了新域性能。
conclusion: 类别感知知识管理有效提升了持续测试时自适应的效果。
---

## Abstract
Continual Test-Time Adaptation (CTTA) aims to quickly fine-tune the model during the test phase so that it can adapt to multiple unknown downstream domain distributions without pre-acquiring downstream domain data. 
To this end, existing advanced CTTA methods mainly reduce the catastrophic forgetting of historical knowledge caused by irregular switching of downstream domain data by restoring the initial model or reusing historical models. However, these methods are usually accompanied by serious insufficient learning of new knowledge and interference from potentially harmful historical knowledge, resulting in severe performance degradation. To this end, we propose a class-aware domain Knowledge Fusion and Fission method for continual test-time adaptation, called KFF, which adaptively expands and merges class-aware domain knowledge in old and new domains according to the test-time data from different domains, where discriminative historical knowledge can be dynamically accumulated. Specifically, considering the huge domain gap within streaming data, a domain Knowledge FIssion (KFI) module is designed to adaptively separate new domain knowledge from a paired class-aware domain prompt pool, alleviating the impact of negative knowledge brought by old domains that are distinct from the current domain. Besides, to avoid the cumulative computation and storage overheads from continuously fissioning new knowledge, a domain Knowledge FUsion (KFU) module is further designed to merge the fissioned new knowledge into the existing knowledge pool with minimal cost, where a greedy knowledge dynamic merging strategy is designed to improve the compatibility of new and old knowledge while keeping the computational efficiency.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与研究动机

持续测试时自适应（CTTA）旨在让预训练模型在不接触下游域数据的前提下，在线适应不断变化的多重未知目标域。现有先进方法主要通过恢复初始模型或复用历史模型来减少因目标域数据不规则切换引起的灾难性遗忘。然而，这些方法通常伴随新知识学习不足以及潜在有害历史知识的干扰，导致性能严重退化。

## 2. 方法论：类别感知知识融合与分裂（KFF）

### 核心思想
提出一种**类别感知的知识融合与分裂框架**（KFF），自适应地在新旧域之间扩展和合并类别感知的域知识，从而动态积累具有判别性的历史知识。

### 关键技术模块

- **知识分裂模块（KFI）**  
  - **类别知识分裂**：对每个测试样本，通过余弦相似度比较伪标签与提示池中每个提示的键，选取相似度高于阈值（γc）的提示，加权组合形成当前样本的类别提示。若无匹配，则分裂出新提示。初始池为空时，为每个样本分裂新提示。  
  - **域知识分裂**：以每个测试批次的统计量（均值μ、标准差σ）作为输入键，计算与域提示池中各提示键的欧几里得距离，选取距离小于阈值（γd）的提示加权组合。若无匹配，则分裂出新域提示。

- **知识融合模块（KFU）**  
  - **类别知识融合**：对学习后的新类别提示，若其预测熵低于阈值γh，则按组成权重更新原池中对应的提示；若为分裂出的新提示，则直接加入。当池大小达到上限时，使用最小生成树（MST）算法将相似提示聚类并合并为一组。  
  - **域知识融合**：类似地，对学习后的新域提示，按组成权重更新原池对应提示；若为分裂新提示则加入。池满时，合并距离最近的一对提示。

### 损失函数
- **批级域对齐损失** \( \mathcal{L}_d = \|\mu_s - \mu_{T_j}(\mathbf{P})\|_2 + \alpha\|\sigma_s - \sigma_{T_j}(\mathbf{P})\|_2 \)  
  利用约300个无标注源样本计算源域统计量。  
- **实例级熵损失** \( \mathcal{L}_c = \frac{1}{b}\sum_{t} H(\hat{y}_t) \)  
  总损失：\( \mathcal{L} = \mathcal{L}_d + a\mathcal{L}_c \)

### 算法流程
每批测试数据先通过KFI选择或分裂提示，对模型预测并优化提示，然后用KFU将优化后的提示合并回提示池，控制池大小并保留历史知识。

## 3. 实验设计

### 数据集与场景
- **数据集**：ImageNet-to-ImageNet-C、CIFAR100-to-CIFAR100C、CIFAR10-to-CIFAR10C。每个数据集包含15种损坏类型、5种严重等级，实验使用最高等级（severity 5）。
- **场景**：
  - 非重复域（一次性遍历所有15种损坏）
  - 重复域（遍历15种损坏10轮）

### 对比方法
包括通用TTA方法（TENT、SAR、POEM）和CTTA方法（CoTTA、VDP、RoTTA、C-MAE、ROID、ViDA、CoLA、PALM、DPCore）等。

### 实现细节
- 骨干网络：ViT-B/16
- 优化器：AdamW，域提示学习率0.1，类别提示学习率0.001
- 批大小64
- 超参数通过预留的4种验证损坏（Speckle Noise, Gaussian Blur, Spatter, Saturate）确定

## 4. 资源与算力

- **GPU**：单张NVIDIA 4090 GPU（如表7所示）
- **训练时长**：未明确给出绝对时长，但表7给出了相对推理时间比例（Ours约为Tent的1.9倍）。无大规模分布式训练。
- **可学习参数**：约0.09M（占模型总参数的0.1%），远少于ViDA（93.70M）和CoTTA（86.57M）。

## 5. 实验数量与充分性

实验设置全面，包括：
- **主实验结果**：表1（ImageNet-C非重复）、表2（ImageNet-C重复10轮）、表5（CIFAR100-C）、表6（CIFAR10-C）
- **消融实验**：表3（各组件贡献）、表4（类别提示选择策略）  
- **超参数分析**：图8、图11（Nc、Nd）、表8（γ、α、γh的影响）
- **功能验证**：图9（域/类提示分离验证）
- **效率分析**：图4（参数-性能对比）、图6（重复域参数增长）、表7（时间、内存、FLOPs对比）
- **稳定性**：表9（10种随机种子，标准差0.3）
- **可视化**：图5（注意力图对比）、图7和10（t-SNE分析）
- **理论证明**：附录A。  

实验数量足够，覆盖了主要基准、场景、消融和效率对比，对比方法均为该领域最新SOTA，公平性较好（超参数通过验证集确定）。

## 6. 主要结论与发现

- KFF在ImageNet-C非重复域上达到34.8%错误率，比此前SOTA方法DPCore低5.1%。
- 在重复域场景（10轮）中，KFF误差稳定在34.5%，而DPCore从39.9%升至46.8%，KFF展现出优越的抗遗忘能力。
- 参数效率极高（仅0.09M），且不会随轮次无限增长（DPCore在10轮后参数为1.03M，KFF为0.20M）。
- 注意力图和t-SNE可视化表明KFF能聚焦于物体判别区域，并为不同域和类分配正确的提示，避免了域冲突。

## 7. 优点

- **创新性**：首次在CTTA中引入类别感知的域知识分裂与融合机制，同时处理域冲突和知识冗余。
- **性能优势**：在三个标准CTTA基准上均达到SOTA，尤其在重复域场景表现突出（比DPCore降低10%以上错误率）。
- **参数高效**：仅增加0.09M参数，且池大小受控，避免了历史模型无限增长。
- **理论支撑**：提供形式化证明（附录A），保证在聚类假设下方法能为测试批分配正确提示。
- **稳定性**：对超参数和随机种子不敏感（表8、表9）。

## 8. 不足与局限

- **依赖源域统计**：域对齐损失需要约300个无标注源样本计算统计量，在源数据不可得（如隐私保护场景）时无法直接使用。
- **合成损坏局限**：所有实验基于合成损坏（ImageNet-C等），未在真实世界自然分布偏移（如视频监控、医疗影像）上验证，泛化性存疑。
- **额外计算开销**：虽然相比多数方法高效，但仍引入了提示分裂/融合和MST聚类等步骤，在资源受限设备或实时应用中可能带来延迟。
- **未测试更大规模骨干**：仅使用ViT-B/16，未在更大模型（如ViT-L）或更复杂任务（如目标检测、分割）上评估。

（完）
