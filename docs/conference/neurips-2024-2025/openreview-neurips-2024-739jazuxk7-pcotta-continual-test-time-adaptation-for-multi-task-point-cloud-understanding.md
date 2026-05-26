---
title: "PCoTTA: Continual Test-Time Adaptation for Multi-Task Point Cloud Understanding"
title_zh: PCoTTA：面向多任务点云理解的持续测试时自适应
authors: "Jincen Jiang, Qianyu Zhou, Yuhang Li, Xinkui Zhao, Meili Wang, Lizhuang Ma, Jian Chang, Jian Jun Zhang, Xuequan Lu"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=739jAzUXk7"
tags: ["query:tta"]
score: 7.0
evidence: 面向多任务点云理解的持续测试时自适应
tldr: PCoTTA针对多任务点云理解在持续变化目标域下的自适应问题，提出持续测试时自适应框架。通过自动原型混合、高斯散点特征移位和对比原型排斥三大组件，有效缓解灾难性遗忘并增强跨域迁移能力。实验表明，该方法在多任务点云场景下显著优于现有持续自适应方法。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-739jazuxk7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-739jazuxk7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-739jazuxk7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-739jazuxk7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1416, \"height\": 701, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-739jazuxk7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-739jazuxk7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1342, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-739jazuxk7/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1381, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-739jazuxk7/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1351, \"height\": 2188, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-739jazuxk7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 715, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-739jazuxk7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 665, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-739jazuxk7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 760, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-739jazuxk7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 497, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-739jazuxk7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 487, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-739jazuxk7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 661, \"height\": 267, \"label\": \"Table\"}]"
motivation: 点云模型在持续变化环境中需要同时处理多个任务，但缺乏统一的自适应框架。
method: 提出自动原型混合、高斯散点特征移位和对比原型排斥三种机制实现持续自适应。
result: 在多个点云任务上验证了框架的有效性，显著减少了遗忘并提升了目标域性能。
conclusion: PCoTTA为多任务点云理解提供了实用的持续测试时自适应方案。
---

## Abstract
In this paper, we present PCoTTA, an innovative, pioneering framework for Continual Test-Time Adaptation (CoTTA) in multi-task point cloud understanding, enhancing the model's transferability towards the continually changing target domain. We introduce a multi-task setting for PCoTTA, which is practical and realistic, handling multiple tasks within one unified model during the continual adaptation. Our PCoTTA involves three key components: automatic prototype mixture (APM), Gaussian Splatted feature shifting (GSFS), and contrastive prototype repulsion (CPR). Firstly, APM is designed to automatically mix the source prototypes with the learnable prototypes with a similarity balancing factor, avoiding catastrophic forgetting. Then, GSFS dynamically shifts the testing sample toward the source domain, mitigating error accumulation in an online manner. In addition, CPR is proposed to pull the nearest learnable prototype close to the testing feature and push it away from other prototypes, making each prototype distinguishable during the adaptation. Experimental comparisons lead to a new benchmark,  demonstrating PCoTTA's superiority in boosting the model's transferability towards the continually changing target domain. Our source code is available at: https://github.com/Jinec98/PCoTTA.

---

## 论文详细总结（自动生成）

# PCoTTA：面向多任务点云理解的持续测试时自适应 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的点云理解模型在训练和测试通常仅在单一域上进行，当部署到不断变化的目标域（如从合成数据到真实扫描数据）时，会因域偏移导致性能严重下降。持续测试时自适应（Continual Test-Time Adaptation, CoTTA）旨在在线自适应不断变化的目标分布，但现有方法主要针对2D图像或单任务设计，直接应用于3D点云时效果不佳，且存在灾难性遗忘和误差累积两大挑战。
- **研究动机**：作者旨在提出一个统一的多任务点云CoTTA框架，使一个预训练模型能够在测试时同时处理重建、去噪、配准等多个任务，并持续适应不断变化的目标域，而无需为每个任务重新设计或训练。
- **整体含义**：PCoTTA通过创新的原型机制和特征移位策略，有效缓解遗忘和累积误差，显著提升模型向连续变化目标域的迁移能力，为点云理解在真实在线场景下的实用化提供了新思路。

## 2. 方法论：核心思想与关键技术细节

- **核心思想**：利用源域原型（source prototypes）作为稳定知识，结合可学习原型（learnable prototypes）捕获当前域知识，通过自动混合、高斯注意力加权移位和对比排斥三个模块，在测试时动态对齐目标样本到源域，同时保持原型可区分性。
- **关键技术细节**：
  - **自动原型混合（APM）**：
    - 预训练后保存所有源域每个类别的特征均值作为源原型 \(Z_s\)。
    - 建立原型库，包含源原型 \(Z_s\) 和一组可学习原型 \(Z_l\)（数量等于潜在目标域数）。
    - 计算测试样本特征 \(F(I_t)\) 与各源原型、可学习原型的相似度（点积归一化后取平均）。
    - 提出自动相似性平衡因子（ASBF），按相似度比例混合对应源原型和可学习原型，得到混合原型 \(Z_m\)，公式：\(Z_m = \frac{S_s}{S_s+S_l} Z_s + \frac{S_l}{S_s+S_l} Z_l\)。
    - 保留源原型固定，仅更新可学习原型，避免灾难性遗忘。
  - **高斯散点特征移位（GSFS）**：
    - 将测试样本与所有混合原型节点构成图结构，以测试特征为中心节点。
    - 将测试样本与源原型、可学习原型的相似度视为2D高斯投影坐标，计算每个节点的高斯值（与相似度负相关），再引入参数 \(\omega\) 确保更高相似度赋予更大权重。
    - 使用Softmax归一化后，通过可学习的卷积层 \(\Psi_\theta\) 动态更新边权重 \(W_{i,j}\)。
    - 按权重融合中心节点与所有混合原型，得到移位后的特征 \(F'(I_t)\)：  
      \(F'(I_t) = \frac{1}{R\times S} \sum_{i,j} \big( (1-W_{i,j}) F(I_t) + W_{i,j} Z_{i,j}^m \big)\)。
    - 动态调整移位幅度，减轻误差累积。
  - **对比原型排斥（CPR）**：
    - 将移位后的测试特征 \(F'(I_t)\) 与最近的可学习原型构成正对，其他可学习原型为负对。
    - 使用InfoNCE损失：\(L_{pr} = -\frac{1}{S}\sum \log \frac{e^{F'(I_t)\cdot Z_t^l /\tau}}{e^{F'(I_t)\cdot Z_t^l /\tau} + \sum_{k\neq t} e^{F'(I_t)\cdot Z_k^l /\tau}}\)。
    - 使可学习原型对当前样本更具区分性，防止域扁平化。
  - **总体损失**：\(L = L_{cd} + \alpha L_{pr}\)，其中 \(L_{cd}\) 为Chamfer距离损失（用于重建、去噪、配准任务），\(\alpha\) 为平衡系数。

## 3. 实验设计

- **数据集与场景**：
  - 精心筛选4个数据集：ModelNet40（合成）、ShapeNet（合成）、ScanNet（真实）、ScanObjectNN（真实），包含7个相同物体类别，共30,954个点云样本。
  - 任务：重建（从稀疏点生成密集点）、去噪（去除噪声点）、配准（恢复随机旋转后的原始方向）。注意：这些任务定义与常规略有不同，但统一为位置输出，可用Chamfer损失训练。
  - 设置：预训练时使用ScanNet和ShapeNet作为源域，测试时在ModelNet40和ScanObjectNN上评估持续适应能力（默认3轮独立重复，每轮样本随机打乱）。
- **基准（Benchmark）**：首次提出多任务点云CoTTA基准，统一评估框架。
- **对比方法**：
  - 传统点云方法：PointNet、DGCNN、PCT、Pointmixup、PointCutMix（单项任务和多任务两种设置）。
  - ICL方法：PIC及其基线。
  - CoTTA方法：AdaBN、TENT、CoTTA、ViDA、RMT、SANTA（均以PIC为骨干网络，并适配多任务设置）。
- **核心指标**：Chamfer距离（CD，×10⁻³），越低越好。

## 4. 资源与算力

- **硬件**：两个NVIDIA A40 GPU。
- **训练配置**：PyTorch实现，batch size 128，AdamW优化器，初始学习率0.001，余弦学习率调度，权重衰减0.05。
- **预训练**：300个epoch（多任务多源域预训练），之后在源域上再训练3个epoch以初始化原型库。
- **测试**：在线持续适应，推理速度极快（运行时间0.06s，远快于其他方法）。
- **说明**：文中未明确给出总训练时长或单轮测试耗时细节，但提供了效率对比表。

## 5. 实验数量与充分性

- **主要实验**：
  - Table 1：与12种方法在3个任务、3个轮次上的全面对比（共36个数值结果），PCoTTA在所有设置下均大幅领先。
  - Table 2：消融研究，逐步添加APM、GSFS、CPR，验证每个组件的贡献。
  - Table 3：消融可学习原型数量（0~4个），表明2个为最优，且无学习性原型（仅源原型）性能下降。
  - Table 4：交叉验证（交换源域和目标域），PCoTTA仍显著优于CoTTA。
  - Table 5：效率分析（运行时间、FLOPs、参数量），PCoTTA最优。
  - 附录Table A：进一步分析单独使用各模块的效果，以及缺失源原型时的性能。
  - 可视化：t-SNE特征分布、多任务预测结果定性展示。
- **充分性与公平性**：
  - 涵盖了不同数据类型（合成/真实）、不同任务、多轮连续适应。
  - 对比方法均按其官方设置复现，并调整为多任务统一骨干网络，确保公平。
  - 消融研究了各设计因素，验证了必要性。
  - 实验设计系统，统计结果稳定（多轮重复）。

## 6. 论文的主要结论与发现

- PCoTTA在重建、去噪、配准三个任务上均显著优于所有对比方法，CD值降低数倍（例如在ModelNet40重建任务上，PCoTTA为5.4×10⁻³，而第二名RMT为30.4×10⁻³）。
- 三个模块（APM、GSFS、CPR）互补，共同发挥效果，缺一不可；其中APM对防止遗忘最关键。
- 可学习原型数量敏感度低（2个即可），但完全无学习性原型会导致性能下降。
- 模型参数少（28.91M）、推理快（0.06s），适合实时部署。
- 无需伪标签或教师模型，从根本上避免了伪标签噪声引起的误差累积。
- t-SNE可视化显示PCoTTA能有效对齐源域与目标域特征，分布更均匀。

## 7. 优点

- **创新性**：首次将CoTTA引入多任务点云理解，提出统一框架，而非为每个任务单独设计。
- **模块设计**：
  - APM巧妙混合源原型与可学习原型，既保留源知识又适应新域。
  - GSFS利用高斯注意力动态调整特征移位权重，自适应性强。
  - CPR通过对比学习使可学习原型可区分，提升适应稳定性。
- **实验充分**：对比方法多、消融全面、交叉验证和效率分析完备。
- **实用性**：端到端、无需额外标注或离线数据，推理效率高，代码开源。
- **性能提升大**：在多个任务和域上取得压倒性优势（CD降低50%~90%）。

## 8. 不足与局限

- **多任务平衡**：文中承认，统一模型难以对所有任务同时最优，例如去噪任务相比专业去噪方法仍有差距。
- **任务定义差异**：论文采用的重建、去噪、配准任务定义与常规略有不同（如配准实际为旋转恢复），未来可扩展至更标准的任务集合。
- **原型数量选择**：虽然对数量不敏感，但最佳配置需要手动设定（2个），且需要预知目标域数量。
- **域覆盖**：实验仅包含4个数据集，更多样化或更大尺度数据集上的泛化性未验证。
- **失效场景**：当目标域与源域极度不相似或出现全新类别时，原型可能无法有效对齐，性能可能下降（作者未讨论）。
- **社会影响**：自动化可能导致岗位替代，需关注伦理和公平性（文中已提及但未深入展开）。

（完）
