---
title: Evaluation of Test-Time Adaptation Under Computational Time Constraints
title_zh: 计算时间约束下的测试时间自适应评估
authors: "Motasem Alfarra, Hani Itani, Alejandro Pardo, shyma yaser alhuwaider, Merey Ramazanova, Juan Camilo Perez, zhipeng cai, Matthias Müller, Bernard Ghanem"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=6FtAXU4ean"
tags: ["query:tta"]
score: 9.0
evidence: 考虑时间约束的TTA方法在线评估协议
tldr: 现有TTA评估忽略计算成本对实际性能的影响。本文提出在线评估协议，假设数据以恒定速率流式到达，根据方法适应速度调整可用样本数。在多个基准上重新评估现有TTA方法，发现速度快的简单方法在时间约束下表现更好，揭示了TTA方法部署时的重要权衡。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-6ftaxu4ean/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 819, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-6ftaxu4ean/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1736, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-6ftaxu4ean/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1682, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-6ftaxu4ean/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 828, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-6ftaxu4ean/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 804, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-6ftaxu4ean/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1763, \"height\": 1319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-6ftaxu4ean/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1769, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-6ftaxu4ean/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 828, \"height\": 492, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-6ftaxu4ean/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 773, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6ftaxu4ean/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 844, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6ftaxu4ean/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1768, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6ftaxu4ean/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6ftaxu4ean/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1767, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6ftaxu4ean/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 857, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6ftaxu4ean/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1764, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6ftaxu4ean/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1727, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6ftaxu4ean/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1767, \"height\": 763, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6ftaxu4ean/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 861, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6ftaxu4ean/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 861, \"height\": 230, \"label\": \"Table\"}]"
motivation: 当前TTA评估忽略计算开销，导致对实际部署场景的指导有限。
method: 提出在线评估协议，以恒定速率流式输入数据，根据方法适应速度动态调整可用样本。
result: 在多个基准上重新评估显示，适应速度快的方法在时间约束下性能更优。
conclusion: 计算时间是TTA方法评估中不可忽略的重要因素。
---

## Abstract
This paper proposes a novel online evaluation protocol for Test Time Adaptation (TTA) methods, which penalizes slower methods by providing them with fewer samples for adaptation. TTA methods leverage unlabeled data at test time to adapt to distribution shifts. Though many effective methods have been proposed, their impressive performance usually comes at the cost of significantly increased computation budgets. Current evaluation protocols overlook the effect of this extra computation cost, affecting their real-world applicability. To address this issue, we propose a more realistic evaluation protocol for TTA methods, where data is received in an online fashion from a constant-speed data stream, thereby accounting for the method's adaptation speed. We apply our proposed protocol to benchmark several TTA methods on multiple datasets and scenarios. Extensive experiments shows that, when accounting for inference speed, simple and fast approaches can outperform more sophisticated but slower methods. For example, SHOT from 2020, outperforms the state-of-the-art method SAR from 2023 under our online setting. Our results reveal the importance of developing practical TTA methods that are both accurate and efficient.

---

## 论文详细总结（自动生成）

# 计算时间约束下的测试时间自适应评估：详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有测试时间自适应（TTA）方法在离线评估中表现优秀，但往往以显著增加计算开销为代价。然而，真实部署场景中数据以恒定速率流式到达，模型若处理速度慢，会错过后续样本，从而减少可用于适应的样本量。当前评估协议完全忽略计算速度对性能的影响，导致对方法实际适用性的错误判断。
- **核心问题**：如何设计一个更现实的评估协议，将TTA方法的适应速度纳入考量，从而真实反映其在连续数据流下的性能。
- **整体含义**：本文揭示了一个重要权衡：在时间约束下，简单快速的TTA方法（如AdaBN、SHOT）可能优于复杂但缓慢的方法（如SAR、DDA）。这促使研究者在追求精度的同时必须关注推理效率。

## 2. 方法论：核心思想、关键技术细节与算法流程

- **核心思想**：模拟真实数据流场景，假设数据以恒定速率 `r`（等于基础模型前向传播速度）连续到来。TTA方法 `g` 具有相对适应速度 `C(g)`（即数据流速度与 `g` 处理速度的整数比），定义 `C(g) = ⌈r / R(g(x))⌉`。当 `C(g) = k` 时，方法每 `k` 个批次才能适应一次，其余批次直接由最近更新的模型 `f_θ` 预测。
- **关键技术细节**：
  - 在线计算 `C(g(xt))`：每次处理一个批次时，通过实际计时（使用 `torch.cuda.synchronize()` 确保GPU同步）动态计算相对速度比，并向上取整。
  - 评估流程（RTTA协议）：
    - 步骤1：数据流揭示样本 `xt`。
    - 步骤2：如果 `(t mod C(g)) == 0`，则执行适应（更新参数），否则使用当前模型 `f_θt` 直接预测，不进行适应。
  - 该协议可退化到离线协议（设置 `C(g)=1` 所有方法）。
- **算法流程说明**：无需公式，如上所述。对于每次迭代，根据方法速度决定是否执行适应操作，保证了高开销方法自然会错失更多适应机会。

## 3. 实验设计：数据集、基准场景与对比方法

- **数据集**：
  - 主数据集：ImageNet-C（15种腐蚀，严重等级5）。
  - 扩展数据集：CIFAR10-C、ImageNet-R（200类，不同渲染版本）、ImageNet-3DCC（基于深度的空间一致性腐蚀）。
- **场景**：
  - 阶段式（Episodic）：每次只适应单一腐蚀，完成后模型重置。
  - 持续式（Continual）：所有腐蚀依次呈现，模型不重置，最后接清洁验证集。
  - 流速度分析：将数据流速率设为 `η·r`，`η ∈ {1/16, 1/8, 1/4, 1/2, 1}`。
  - 实际TTA（PTTA）场景：结合标签不平衡与持续适应，使用CIFAR10-C和RoTTA方法。
- **基准方法**：共15种TTA方法，包括AdaBN（2017）、BN（2020）、SHOT/SHOT-IM（2020）、TENT（2020）、EATA/ETA（2022）、SAR（2023）、CoTTA（2022）、TTAC-NQ（2022）、MEMO（2021）、DDA（2022）、LAME（2022）、Pseudo Label（2013）、RoTTA（2023）等。所有方法使用官方代码与推荐超参数。
- **评估指标**：错误率（Error Rate），越低越好。报告平均值与标准差（3个随机种子）。

## 4. 资源与算力

- **明确说明**：论文未明确列出所使用的具体GPU型号、数量或训练时长。仅提到在NVIDIA GPU上运行，并使用 `torch.cuda.synchronize()` 进行精确计时。
- **可推断信息**：实验涉及对15种方法在多个大型数据集上的评估，通常需要单卡或多卡GPU（如V100或A100），但具体细节未给出。作者使用了torchvision预训练的ResNet-50-BN和ViT，且代码已开源，可以复现。

## 5. 实验数量与充分性

- **实验组数量**：
  - 主实验：表2（Episodic on ImageNet-C，15种腐蚀×12种方法×3种子）。
  - 拓展实验：表3（ViT架构，3种方法）、表4（ImageNet-R和ImageNet-3DCC，10种方法）、表5（CIFAR10-C下的PTTA，2种方法）。
  - 持续适应实验：图3（6种方法，11种腐蚀顺序，3种子），表8（平均结果）。
  - 流速度分析：图4（5种方法，5种速度，3种子），图8（类似针对ImageNet-3DCC）。
  - 消融实验：不同batch size（图6，12种方法，4种batch size）、超参数调优（表6，TENT的不同学习率）。
  - 单模型评估：表10（限制只有一个模型时）。
  - 其他架构：ResNet-18（表11）。
- **充分性评价**：实验覆盖了多种场景（阶段式、持续式、速度变化、标签不平衡）、多种骨干网络（ResNet-50、ResNet-18、ViT）、多个数据集（ImageNet-C/R/3DCC、CIFAR10-C），并包含消融与鲁棒性分析（随机种子、标准差）。整体非常充分、客观，对比方法全面且包含了近年最新成果。公平性体现在统一使用官方实现和默认超参数，并明确计算相对速度比，避免硬件偏差。

## 6. 主要结论与发现

1. **慢速方法在在线评估中性能显著下降**：高计算开销方法（如TTAC-NQ、SAR、CoTTA、MEMO、DDA）因适应次数少，错误率大幅提升（最高达17.6%）。例如DDA，原地踏步于源模型水平。
2. **快速简单方法成为竞争者**：AdaBN、BN、LAME这类几乎不增加计算的方法（C=1）不受影响，在时间约束下表现最佳，甚至优于近年先进技术。
3. **样本拒绝方法表现良好**：EATA凭借高效样本拒绝机制（只依赖前向传播）在在线评估中始终领先，其误差率仅小幅上升（≤4%），成为综合最优。
4. **SHOT意外受益于在线评估**：因为适应样本减少，避免了过度拟合，在多个腐蚀上错误率反而下降（-0.8%平均）。
5. **持续适应场景中，有限适应可防止过拟合**：在持续设置下，SHOT、TENT等方法在离线时严重退化，但在在线评估中因错过部分批次而减轻了过拟合，性能有提升。
6. **适应速度与性能存在动态权衡**：不同流速度下方法排序会发生逆转（例如TENT在快速流下优于SAR，慢速流下相反），因此评价时应根据实际部署速度选择合适方法。

## 7. 优点

- **问题新颖性与现实意义**：首次系统性地将计算速度纳入TTA评估，揭示了传统离线评估的严重局限性，推动领域向实际部署靠拢。
- **方法简洁且通用**：提出的RTTA协议基于简单的相对速度比，无需修改TTA方法自身，即插即用，易于复现和扩展。
- **全面深入的实验**：涵盖多种场景、数据集、架构、超参数、消融，且多次报告标准差，结果可靠。特别包含流速度分析和单模型评估，增强了洞察。
- **明确对比基线**：从2017年的AdaBN到2023年的SAR、RoTTA，时间跨度大，覆盖代表性方法，结论具有普适性。
- **代码开源**：促进社区验证与后续研究。

## 8. 不足与局限

- **资源开销细节缺失**：未详细记录和报告各种方法的实际浮点运算量、GPU使用情况或能耗，仅靠时间比衡量，可能受硬件波动影响（尽管已使用同步）。
- **假设局限**：前提是基础模型 `f_θ` 的速度等于流速率，且整个推理过程中流速率恒定。现实场景可能存在突发高负载或变速率。
- **未考虑并发机制**：默认 `g` 和 `f_θ` 可同时运行（双模型），但在“单模型评估”实验中证明该假设对慢方法有利。实际可能无法同时维持两个模型。
- **部分方法效果需谨慎解读**：SHOT在在线评估中的“改善”可能源于某些腐蚀下的偶然，需进一步分析其泛化性。作者未深入探讨原因。
- **缺乏对更大规模模型（如ViT-Large）的测试**：仅测试了ViT-Base，无法推断扩展规律。
- **应用领域单一**：仅限图像分类（ImageNet/CIFAR系列），未涉及语义分割、目标检测等更复杂任务，而这些任务中时间约束更为关键。
- **超参数适应性问题**：所有方法使用固定默认参数，并未针对在线评估重新调优（仅对TENT做了学习率探索）。若方法能在离线/在线间自适应调整参数，结果可能不同。

（完）
