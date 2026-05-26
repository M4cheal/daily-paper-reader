---
title: Cross-Device Collaborative Test-Time Adaptation
title_zh: 跨设备协同测试时自适应
authors: "Guohao Chen, Shuaicheng Niu, Deyu Chen, Shuhai Zhang, Changsheng Li, Yuanqing Li, Mingkui Tan"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=YyMiO0DWmI"
tags: ["query:tta"]
score: 9.0
evidence: 提出了一种协同测试时自适应方法
tldr: 本文针对测试时自适应（TTA）在多设备场景下的性能瓶颈，提出了一种协同终生自适应范式CoLA。该方法通过维护跨设备共享的领域知识向量，并设计知识重编程学习策略和代理适应机制，使得不同计算资源的设备能协同提升自适应性能。实验表明该方法能显著提高多种现有TTA方法的效果，并降低延迟。为TTA在分布式系统中的实际部署提供了新思路。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-yymio0dwmi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1409, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yymio0dwmi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1305, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yymio0dwmi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1339, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yymio0dwmi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yymio0dwmi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1131, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yymio0dwmi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1409, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yymio0dwmi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1427, \"height\": 1482, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1339, \"height\": 454, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 471, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 693, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 690, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 581, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 806, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1451, \"height\": 795, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 860, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1448, \"height\": 1267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1438, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1090, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 861, \"height\": 153, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1447, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1449, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 873, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1335, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yymio0dwmi/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1445, \"height\": 351, \"label\": \"Table\"}]"
motivation: 现有TTA方法通常部署于单设备，忽略了多设备协同的潜力，导致适应效率低。
method: CoLA维护跨设备共享的领域知识向量，并设计知识重编程学习策略与代理适应机制，协同更新模型参数，适用于不同计算资源的设备。
result: 实验证明CoLA能有效提升多种TTA方法的适应性能和计算效率，在多个基准上取得最优结果。
conclusion: 提出的协同自适应范式为TTA在分布式系统中的实际应用提供了可行且高效的解决方案。
---

## Abstract
In this paper, we propose test-time Collaborative Lifelong Adaptation (CoLA), which is a general paradigm that can be incorporated with existing advanced TTA methods to boost the adaptation performance and efficiency in a multi-device collaborative manner. Specifically, we maintain and store a set of device-shared _domain knowledge vectors_, which accumulates the knowledge learned from all devices during their lifelong adaptation process. Based on this, CoLA conducts two collaboration strategies for devices with different computational resources and latency demands. 1) Knowledge reprogramming learning strategy jointly learns new domain-specific model parameters and a reweighting term to reprogram existing shared domain knowledge vectors, termed adaptation on _principal agents_. 2) Similarity-based knowledge aggregation strategy solely aggregates the knowledge stored in shared domain vectors according to domain similarities in an optimization-free manner, termed adaptation on _follower agents_. Experiments verify that CoLA is simple but effective, which boosts the efficiency of TTA and demonstrates remarkable superiority in collaborative, lifelong, and single-domain TTA scenarios, e.g., on follower agents, we enhance accuracy by over 30\% on ImageNet-C while maintaining nearly the same efficiency as standard inference. The source code is available at https://github.com/Cascol-Chen/COLA.

---

## 论文详细总结（自动生成）

# 跨设备协同测试时自适应（CoLA）论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有测试时自适应（TTA）方法通常假设在单设备上运行，忽略了多设备部署场景下的三个关键局限：
  1. 各设备独立适应，无法利用其他设备已学到的有用知识，导致适应性能次优。
  2. 部分设备因计算资源有限或延迟要求高，无法支持反向传播更新，从而无法使用基于学习的TTA方法。
  3. 单个设备在长期连续适应过程中，模型会遭遇灾难性遗忘，难以积累先前学到的知识。

- **整体含义**：提出一种**跨设备协同的终生自适应范式（CoLA）**，旨在实现知识跨设备的积累、共享与高效利用，同时兼顾隐私保护和通信效率，以适应现实世界中不同资源与延迟要求的多样化设备。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：维护一个跨设备共享的**领域知识向量集合 T**，每个向量表示模型在某个设备某个域上学到的参数变化（Δθ）。通过自动域变化检测，当设备检测到测试分布变化时，将当前学到的知识存储到 T 中。基于 T，为不同计算能力的设备设计两种协同策略。

- **关键技术细节**：
  - **域变化检测**：利用初始层（stem layer）的特征统计量（均值和标准差）计算当前批次与在线估计分布之间的 KL 散度，若超过阈值 z 则触发存储。
  - **主代理（Principal Agents）——知识重编程学习**：
    - 同时学习新的领域特定参数 Δθ 和重加权系数 α，通过反向传播优化（公式(2)）：  
      `θ_l = θ_o^l + Σ α_i Δθ_i + Δθ`（其中 Δθ_i ∈ T，Δθ 为新学参数，α 为归一化权重）。
    - 引入**自适应温度缩放 T_l**（α = softmax(β·T_l)）以促进快速适应。
    - 存储新学知识时进行初始化，确保模型稳定性。
  - **从代理（Follower Agents）——基于相似性的知识聚合**：
    - 无优化前向聚合：根据当前测试分布与各已存储知识对应的分布之间的相似性（KL 散度倒数），计算权重 γ（公式(4)），然后加权求和（公式(3)）。
    - 引入**温度缩放因子 T_f**（公式(5)）以防止 softmax 退化为 max 函数，鼓励多样化知识聚合。
  - **通信与隐私**：仅传输规范层（LN）的仿射参数（如 ViT-B 仅 0.15MB），且仅在域变化时间歇性传输，通信高效且保护隐私。

## 3. 实验设计：数据集、场景、对比方法

- **数据集**：
  - 源模型训练集：ImageNet-1K。
  - OOD 评估基准：ImageNet-C（15种损坏类型，5级严重度，主要使用 level 5）、ImageNet-R、ImageNet-Sketch、ImageNet-A、ImageNet-V2。

- **场景**：
  1. **终生 TTA**：单设备上连续适应 10 轮共 150 种损坏（从不重置模型）。
  2. **协同 TTA**：多主代理协同（设备间分享学到知识），以及从代理利用主代理共享的知识进行前向适应。
  3. **单域 TTA**：包括温和场景（随机顺序）和野场景（标签分布偏移、混合域偏移）。

- **对比方法**：
  - 基于反向传播：CoTTA, EATA, SAR, ETA, DeYO。
  - 无反向传播：LAME, T3A。
  - 额外对比：FedAvg, TPT（提示调优）。

## 4. 资源与算力

- 论文明确提到：所有实验在**单块 NVIDIA A100 GPU** 上使用 PyTorch 1.8.0 完成。
- 在表 5 中报告了具体耗时和显存占用（如 CoLA 在从代理上仅增加约 5MB 显存和 2 秒延迟），但**未提供总训练时长或具体实验运行时间**。

## 5. 实验数量与充分性

- **实验数量众多**：包含 8 个主表（表 1–7 及附录中的多个表格），以及 3 张图（图 3 及附录中的多张图）。
- **覆盖多种设置**：
  - 终生适应（10轮、150种损坏）。
  - 协同适应（3个主代理，34个权重，5.0MB）。
  - 单域适应（温和、标签偏移、混合域）。
  - 不同架构（ViT-B, ResNet50）。
  - 未见分布泛化（ImageNet-R/Sketch）。
  - 样本效率、温度 T_f / T_l 消融、阈值 z 敏感性、批量大小鲁棒性、统计显著性（5个种子实验）。
- **公平客观**：严格按照原论文超参数设置对比方法，采用公平的终生和协同协议。消融实验控制变量，分析充分。

## 6. 主要结论与发现

- CoLA 在各种场景下**显著提升**现有 TTA 方法的性能和效率：
  - 终生适应中：平均准确率提升 +18.4%（ETA+CoLA vs ETA），解决了持续遗忘问题。
  - 协同适应中：准确率提升至 63.7%（ETA+CoLA vs 61.2% ETA），且随着设备数增加持续改善。
  - 从代理上：在 ImageNet-C 上准确率从 29.9% 提升至 64.1%，同时保持几乎与标准推理相同的计算开销。
  - 主代理上：样本效率提升最高达 78.0×（使用更少的样本达到同等性能）。
- 可插拔：兼容多种现有 TTA 方法，无需修改原有算法。
- 通信高效且隐私友好：仅传输微小且稀疏的模型参数差分。

## 7. 优点

- **创新性强**：首次提出多设备协同 TTA 范式，同时解决知识利用、灾难性遗忘和资源受限三个实际问题。
- **实用性突出**：支持异构设备（主/从代理），仅在域变化时通信，适合真实分布式部署。
- **高效低开销**：主代理仅增少量参数（~5MB 显存），从代理无反向传播，速度与标准推理几乎一致。
- **实验全面深入**：覆盖多种协议、架构、分布，且包含统计误差和大量消融。
- **泛化能力**：在未见过的分布上也能提升性能（如 ImageNet-R +4.4%）。

## 8. 不足与局限

- **未验证语言模型**：仅使用视觉模型，虽提出可扩展至 LLM 微调，但缺乏验证。
- **共享向量持续增长**：随着设备增多和长时间适应，域向量集合会膨胀，尽管有简单丢弃策略（按 α 值），但跨设备压缩仍具挑战。
- **超参数敏感性**：域变化检测阈值 z 和从代理温度 T_f 需手动设定，虽给出默认值但未讨论自动调优。
- **实验架构限制**：主要基于 ViT-Base 和 ResNet50，对其他主干（如 CNN 变体）的泛化有待验证。
- **协同通信模式假设**：假设所有代理可随时共享域向量，未考虑网络延迟或设备离线等现实问题。

（完）
