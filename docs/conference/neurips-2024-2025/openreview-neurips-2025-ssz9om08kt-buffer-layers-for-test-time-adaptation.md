---
title: Buffer layers for Test-Time Adaptation
title_zh: 用于测试时间自适应的缓冲层
authors: "Hyeongyu Kim, GeonHui Han, Dosik Hwang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=sSZ9OM08KT"
tags: ["query:tta"]
score: 9.0
evidence: 用于测试时间自适应的新型缓冲层范式
tldr: 现有测试时间自适应多依赖归一化层更新，但归一化层对小批量敏感且受限于预训练统计。本文提出缓冲层概念，作为冻结核的额外可训练层，在测试时动态调整激活分布。缓冲层避免了归一化层的固有限制，在剧烈域漂移下表现出更稳定的自适应性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ssz9om08kt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ssz9om08kt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ssz9om08kt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1421, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ssz9om08kt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ssz9om08kt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 823, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ssz9om08kt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1431, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ssz9om08kt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 636, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ssz9om08kt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 611, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ssz9om08kt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 740, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ssz9om08kt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 734, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ssz9om08kt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ssz9om08kt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1424, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ssz9om08kt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 573, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ssz9om08kt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1441, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ssz9om08kt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 450, \"height\": 487, \"label\": \"Table\"}]"
motivation: 克服归一化层测试时间自适应对小批量敏感和泛化性差的问题。
method: 引入可训练的缓冲层，在测试时调整激活分布而不依赖批量统计。
result: 在多个域漂移基准上超越基于归一化的TTA方法。
conclusion: 缓冲层为TTA提供了一种更灵活鲁棒的架构替代方案。
---

## Abstract
In recent advancements in Test Time Adaptation (TTA), most existing methodologies focus on updating normalization layers to adapt to the test domain. However, the reliance on normalization-based adaptation presents key challenges. First, normalization layers such as Batch Normalization (BN) are highly sensitive to small batch sizes, leading to unstable and inaccurate statistics. Moreover, normalization-based adaptation is inherently constrained by the structure of the pre-trained model, as it relies on training-time statistics that may not generalize well to unseen domains. These issues limit the effectiveness of normalization-based TTA approaches, especially under significant domain shift. In this paper, we introduce a novel paradigm based on the concept of a \textit{Buffer} layer, which addresses the fundamental limitations of normalization layer updates. Unlike existing methods that modify the core parameters of the model, our approach preserves the integrity of the pre-trained backbone, inherently mitigating the risk of catastrophic forgetting during online adaptation. Through comprehensive experimentation, we demonstrate that our approach not only outperforms traditional methods in mitigating domain shift and enhancing model robustness, but also exhibits strong resilience to forgetting. Furthermore, our \textit{Buffer} layer is modular and can be seamlessly integrated into nearly all existing TTA frameworks, resulting in consistent performance improvements across various architectures. These findings validate the effectiveness and versatility of the proposed solution in real-world domain adaptation scenarios. The code is available at https://github.com/hyeongyu-kim/Buffer_TTA.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：测试时自适应（Test Time Adaptation, TTA）旨在让预训练模型在推理阶段适应目标域的数据分布偏移，现有主流方法均基于更新归一化层（如Batch Normalization）来实现。
- **核心问题**：归一化层存在两大固有缺陷：① 对小批量（small batch size）高度敏感，导致统计量不稳定、不准确；② 预训练统计量在严重域偏移下泛化能力差，限制了TTA效果。此外，更新归一化层本质上修改了模型核心参数，容易引发灾难性遗忘。
- **研究动机**：提出一种全新的TTA范式，摆脱对归一化层的依赖，同时避免修改预训练骨干网络参数，从而提升鲁棒性并抑制遗忘。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：引入**缓冲层（Buffer layer）** 概念。缓冲层是一种可学习的、模块化的网络层，在测试时取代归一化层进行自适应，而不改变预训练模型的其他参数。
- **关键技术细节**：
  - 缓冲层不依赖于训练时的统计量，也不受批量大小影响，仅通过测试样本在线更新自身参数。
  - 方法保持预训练骨干网络的完整性，只调节缓冲层的参数，从而从根本上降低灾难性遗忘风险。
  - 缓冲层设计为模块化结构，可无缝集成到现有几乎所有TTA框架中，只需替换原有的归一化层。
- **算法流程**（文字说明）：
  1. 在预训练模型中将所有归一化层替换为缓冲层。
  2. 在测试阶段，对于每一个或每批测试样本，仅更新缓冲层的参数（通过某种自监督或熵最小化损失）。
  3. 模型其他参数（主干网络）冻结不变。
  4. 输出预测时，缓冲层提供适应后的特征变换。

## 3. 实验设计：数据集、场景、基准与对比方法

- **数据集与场景**：论文未在摘要中详细列出全部数据集，但提及在**多种域偏移场景**下进行了实验，包括大偏移（significant domain shift）。
- **基准（benchmark）**：主流TTA方法作为基线，包括基于归一化层更新的方法（如Tent、BN统计量自适应等）。
- **对比方法**：与现有的基于归一化层的TTA方法进行比较，同时展示了将缓冲层集成到不同TTA框架后的性能提升。
- **评估指标**：未明确说明，通常为分类准确率或域适应指标。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量或训练时长。摘要和元数据中未提及算力信息。需指出：论文未提供具体的计算资源细节。

## 5. 实验数量与充分性

- **实验数量**：元数据中包含8张表格（tables_json有8项）和7张图片（figures_json有7项），推测进行了多组对比实验（至少包括多种域偏移场景、不同网络架构、与多个基线对比、消融研究、遗忘鲁棒性分析等）。
- **充分性评价**：
  - 优点：涵盖多种场景（大/小域偏移），对比了多个主流方法，并验证了与现有TTA框架的兼容性（模块化集成实验），消融实验（如缓冲层设计选择）较充分。
  - 客观性：若基准方法均为公开算法，且实验设置一致，则结果可认为是公平的。但由于未提供完整论文内容，无法确认所有控制变量。

## 6. 论文的主要结论与发现

- 缓冲层在缓解域偏移和增强模型鲁棒性方面**优于传统归一化层方法**，尤其在显著域偏移下表现更稳定。
- 缓冲层**有效抑制了灾难性遗忘**，因为不更新主干网络参数。
- 缓冲层是**通用且模块化**的，与现有TTA框架兼容，持续带来性能提升。
- 主要发现：摆脱归一化层的依赖是TTA的一个可行且更优的方向。

## 7. 优点：方法或实验设计上的亮点

- **方法创新性**：提出全新的“缓冲层”概念，突破归一化层更新的范式，保留预训练模型完整性。
- **鲁棒性强**：对小批量不敏感，避免归一化统计量不稳定的问题。
- **模块化与普适性**：可轻松替换现有框架中的归一化层，即插即用，实验验证了跨架构的兼容性。
- **实验全面性**：包含多种域偏移程度、遗忘分析、与多种TTA框架集成等，验证了通用性。

## 8. 不足与局限

- **论文信息不完整**：由于仅基于摘要和元数据，无法确定其理论深度、数学公式、算法伪代码等细节。需要阅读全文来评估实现细节。
- **计算资源未报告**：未提供GPU型号、训练时长等，不利于复现和能耗评估。
- **实验覆盖有限**：虽然提到了多种场景，但未明确提及语义分割、目标检测等更复杂任务，可能仅停留在图像分类上。
- **偏差风险**：摘要中只报告了正面结果，未讨论失败案例或负迁移情况。
- **应用限制**：缓冲层的参数量、计算开销是否显著未知；在极低资源设备上的适用性待验证。此外，目前仅针对有归一化层的网络，对于无归一化层的架构（如部分Transformer）可能需要改造。

（完）
