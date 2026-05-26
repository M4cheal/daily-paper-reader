---
title: "DPCore: Dynamic Prompt Coreset for Continual Test-Time Adaptation"
title_zh: DPCore：用于持续测试时自适应的动态提示核心集
authors: "Yunbei Zhang, Akshay Mehra, Shuaicheng Niu, Jihun Hamm"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=A6zDim0rQf"
tags: ["query:tta"]
score: 9.0
evidence: 针对动态流数据的持续测试时自适应，基于回放方法
tldr: 持续测试时自适应（CTTA）在真实场景中面临域频繁变化且时长不一的问题，现有方法难以应对。本文提出DPCore，结合动态提示核心集与选择性参数更新，有效应对域爆发、重访等动态模式。在多个CTTA基准上，DPCore在效率和性能上均优于现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-a6zdim0rqf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 872, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a6zdim0rqf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1775, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a6zdim0rqf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1799, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a6zdim0rqf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 843, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a6zdim0rqf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1749, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a6zdim0rqf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 830, \"height\": 498, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 869, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1770, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1774, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1768, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1753, \"height\": 131, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 872, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 869, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1769, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1768, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1771, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a6zdim0rqf/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1771, \"height\": 431, \"label\": \"Table\"}]"
motivation: 现有CTTA方法假设域变化均匀结构化，无法处理真实环境中的动态模式。
method: 提出动态提示核心集，为每个域分配可学习提示并通过回放机制保留知识，结合选择性参数更新避免遗忘。
result: 在多个基准上，面对域频繁变化和持续漂移，DPCore始终维持高准确率。
conclusion: 提示核心集与选择性更新是应对动态持续TTA的有效框架。
---

## Abstract
Continual Test-Time Adaptation (CTTA) seeks to adapt source pre-trained models to continually changing, unseen target domains. While existing CTTA methods assume structured domain changes with uniform durations, real-world environments often exhibit dynamic patterns where domains recur with varying frequencies and durations. Current approaches, which adapt the same parameters across different domains, struggle in such dynamic conditions—they face convergence issues with brief domain exposures, risk forgetting previously learned knowledge, or misapplying it to irrelevant domains. To remedy this, we propose **DPCore**, a method designed for robust performance across diverse domain change patterns while ensuring computational efficiency. DPCore integrates three key components: Visual Prompt Adaptation for efficient domain alignment, a Prompt Coreset for knowledge preservation, and a Dynamic Update mechanism that intelligently adjusts existing prompts for similar domains while creating new ones for substantially different domains. Extensive experiments on four benchmarks demonstrate that DPCore consistently outperforms various CTTA methods, achieving state-of-the-art performance in both structured and dynamic settings while reducing trainable parameters by 99% and computation time by 64% compared to previous approaches.

---

## 论文详细总结（自动生成）

# 论文总结：DPCore: Dynamic Prompt Coreset for Continual Test-Time Adaptation

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有Continual Test-Time Adaptation (CTTA) 方法大多假设目标域以**结构化、均匀时长**的方式变化（称为CSC设置），但真实世界中的域变化往往是**动态的**：域会以不同频率和时长反复出现（称为CDC设置）。在这种动态环境下，传统方法面临三大难题：
  - **收敛问题**：短时暴露的域导致参数难以充分收敛；
  - **灾难性遗忘**：持续更新同一组参数会丢失先前域的知识；
  - **负迁移**：不同域之间的知识互相干扰，降低性能。
- **动机**：设计一种能够适应动态域变化模式、同时保持计算效率的CTTA方法。现有SOTA方法（如ViDA）在CSC到CDC转换时误差率从43.4%升至52.1%，性能严重下降。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：采用**多模型策略**（而非单模型），为不同域组维护一个动态的**提示核心集**，通过区分相似域与不相似域来管理知识，避免遗忘和负迁移。
- **三个关键组件**：
  1. **Visual Prompt Adaptation (VPA)**  
     - 在ViT各层之前插入可学习的**提示令牌**（prompt tokens），仅通过最小化源域与目标域特征的**分布距离**（均值和标准差）来学习提示，无需标签或预热。
     - 损失函数：\( d(\Gamma_S, \Gamma_t(p)) = \|\mu_S - \mu_t(p)\|^2 + \|\sigma_S - \sigma_t(p)\|^2 \)。
  2. **Prompt Coreset**  
     - 维护一个核心集，每个元素为一个**提示**及其对应批次的**统计特征**（均值和标准差）。
     - 初始化空集，遇到新域时学习新提示并加入核心集；遇到已见域时通过加权组合更新现有提示。
  3. **Dynamic Update**  
     - 对新批次，首先计算无提示时的统计量，再计算与核心集中所有元素的距离，用**softmax权重**生成加权提示 \( p_w \)。
     - 若加权提示能显著减小域间隙（距离比 \( d(\Gamma_S,\Gamma_t(p_w))/d(\Gamma_S,\Gamma_t) \) 小于阈值 \( \rho \)），则将该批次视为已见域，**仅用一步更新**核心元素；否则视为新域，**从头学习**新提示并加入核心集。
- **算法流程**：见Algorithm 1，核心是动态判断是否属新域、选择性学习或更新。
- **理论分析**：在批间距离满足“良好分离”假设下，证明DPCore对批次顺序不敏感，正确聚类，且提示学习与顺序无关。

## 3. 实验设计
- **数据集**：
  - **分类任务**：ImageNet→ImageNet-C（15种损坏，severity 5）、CIFAR10→CIFAR10-C、CIFAR100→CIFAR100-C。
  - **分割任务**：Cityscapes→ACDC（4种天气条件，重复3轮）。
- **设置**：
  - **CSC**：传统结构化域变化（每个域固定长度，顺序出现）。
  - **CDC**：用Dirichlet分布（δ=1）生成动态域序列（域重复、时长不等）。
- **对比方法**：Tent, CoTTA, VDP, SAR, RoTTA, RDumb, EcoTTA, ViDA, BGD, C-MAE等SOTA。
- **实现细节**：ViT-Base (分类), Segformer-B5 (分割)；批次大小64；提示长度8；阈值ρ=0.8；优化器AdamW，lr=0.01；源统计量用300张无标签源图像计算。

## 4. 资源与算力
- 论文**未明确说明**使用的GPU型号、数量及具体训练时长。
- 但提供了**计算效率分析**（Table 4）：DPCore仅需0.08M可训练参数（ViDA需93.70M），每个批次平均1.8次前向传播（Tent为1.0），相对计算时间比Tent多80%但比ViDA少64%。
- 预处理只需对300张源图像做一次前向传播，无需完整数据集预热。

## 5. 实验数量与充分性
- **实验覆盖**：
  - 在4个基准（3个分类+1个分割）上进行了CSC和CDC两种设置的全面比较。
  - 消融实验：每个组件贡献（Table 3）、提示长度L（Fig.5a）、阈值ρ（Fig.5b）、批次大小（Fig.5d）、源样本数量（Fig.5c）。
  - 额外分析：核心集大小随域变化（Fig.3b）、跨10种随机域顺序的稳定性（Fig.3c）、不同Dirichlet参数（Fig.6）、无源数据情况（Appendix E.2）、固定大小核心集管理（Table 5）等。
- **公平性**：所有方法在相同超参数下对比，超参数通过验证集（4种损坏）确定，未在目标域上调整。
- **充分性**：实验设计较为充分，覆盖了主流设置、关键变量和极端情况，结果具有统计意义。

## 6. 主要结论与发现
- **核心结果**：
  - 在CSC下，ImageNet-C上DPCore误差率39.9%，比Source提高15.9%，超越ViDA（43.4%）3.5%。
  - 在CDC下，DPCore误差率42.1%，比ViDA（52.1%）低10.0%，且仅比CSC高2.2%，而ViDA上升8.7%。
  - 分割任务：DPCore在CSC和CDC下均取得最佳mIoU（62.5%和61.0%）。
- **效率**：可训练参数减少99%，计算时间减少64%。
- **动态管理**：核心集大小随域复杂度自然增长（CSC下约14个，CDC下约25个），有效分组相似域。
- **理论保证**：在分离集群假设下，提示学习与批次顺序无关，算法收敛稳定。

## 7. 优点
- **创新性**：首次将动态提示核心集引入CTTA，有效应对真实世界的动态域变化。
- **高效性**：参数极少、无需完整源数据集预热、计算开销低，适合边缘设备。
- **鲁棒性**：在CSC和CDC多种设置下均保持稳定性能，且对超参数（提示长度、阈值）不敏感。
- **可解释性**：通过核心集大小和域距离可视化，可直观理解域分组行为。
- **理论支持**：提供了简洁的在线K-Means理论分析，证明算法顺序无关性。

## 8. 不足与局限
- **单域批假设**：假设每个批次仅来自一个域。若批次跨域混合（如边界场景），性能可能下降（文中指出这是未来工作）。
- **仍需少量源数据**：需要300张源图像计算统计量；虽然无源时可使用公共数据集（如STL10），但效果略降（45.6% vs 39.9%）。
- **计算开销仍存在**：相比Tent需额外80%时间，对于超低延迟场景可能仍需优化。
- **未在更多实际任务上验证**：实验限于图像分类和语义分割，未推广到视频、医疗等场景。
- **阈值ρ依赖**：虽然实验显示ρ在0.6~0.9之间稳定，但最佳值可能因任务不同而需调整。

（完）
