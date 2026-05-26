---
title: Test-Time Adaptation with Binary Feedback
title_zh: 基于二元反馈的测试时自适应
authors: "Taeckyung Lee, Sorn Chottananurak, Junsu Kim, Jinwoo Shin, Taesik Gong, Sung-Ju Lee"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=A5l37HL8vX"
tags: ["query:tta"]
score: 9.0
evidence: 基于二元反馈的测试时自适应方法与设置
tldr: 本文提出一种新的测试时自适应（TTA）设置——二元反馈TTA，利用少量标注者提供的正确/错误二元反馈来指导模型适应。作者设计BiTTA框架，使用双路径优化和强化学习平衡反馈引导与自监督信号，有效应对严重域偏移，降低了标注成本。实验表明BiTTA在多种域偏移场景下优于现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1755, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 854, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 619, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 533, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 527, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 532, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 537, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 551, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 551, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 555, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5l37hl8vx/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 552, \"height\": 381, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1768, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1777, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1766, \"height\": 107, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1780, \"height\": 108, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1773, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1770, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1770, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1772, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1768, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 634, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1774, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1770, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 504, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1770, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1769, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1769, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1776, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5l37hl8vx/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1776, \"height\": 427, \"label\": \"Table\"}]"
motivation: 现有TTA方法在严重域偏移下失效，而主动TTA需要完整类别标签，成本过高。
method: 提出BiTTA框架，采用双路径优化和强化学习，利用少量二元反馈信号指导模型自适应。
result: 在多种域偏移基准上取得优异性能，仅需少量二元反馈即可接近全监督TTA的效果。
conclusion: 二元反馈TTA是降低标注成本、提升鲁棒性的有效途径。
---

## Abstract
Deep learning models perform poorly when domain shifts exist between training and test data. Test-time adaptation (TTA) is a paradigm to mitigate this issue by adapting pre-trained models using only unlabeled test samples. However, existing TTA methods can fail under severe domain shifts, while recent active TTA approaches requiring full-class labels are impractical due to high labeling costs. To address this issue, we introduce a new setting of TTA with binary feedback, which uses a few binary feedbacks from annotators to indicate whether model predictions are correct, thereby significantly reducing the labeling burden of annotators. Under the setting, we propose BiTTA, a novel dual-path optimization framework that leverages reinforcement learning to balance binary feedback-guided adaptation on uncertain samples with agreement-based self-adaptation on confident predictions. Experiments show BiTTA achieves substantial accuracy improvements over state-of-the-art baselines, demonstrating its effectiveness in handling severe distribution shifts with minimal labeling effort.

---

## 论文详细总结（自动生成）

# 基于二元反馈的测试时自适应（TTA with Binary Feedback）——论文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：深度模型在训练与测试数据之间存在域偏移时性能大幅下降。现有的测试时自适应（TTA）方法仅利用无标签测试样本进行自适应，在严重域偏移下容易失效（如依赖熵或置信度等不可靠的自我监督信号）。而近期提出的主动TTA需要完整类别标签，标注成本高昂，实际应用中难以扩展。
- **整体含义**：本文提出一种新的TTA设置——**二元反馈TTA**，即仅需标注者对模型的预测结果提供“正确/错误”二元反馈（1比特信息），显著降低标注负担。在此设置下，作者设计了BiTTA框架，利用强化学习融合少量二元反馈与大量无标签样本，有效应对严重域偏移。

## 2. 方法论

- **核心思想**：采用双路径优化策略，将TTA建模为强化学习问题，以模型预测概率作为策略，使用REINFORCE算法优化期望奖励。两条路径分别为：
  1. **二元反馈引导自适应（BFA）**：选择**不确定性最高**的样本（MC-dropout置信度最低），获取二元反馈（正确奖励+1，错误奖励-1），通过策略梯度更新模型。
  2. **一致性自自适应（ABA）**：对**预测置信的样本**（标准预测与MC-dropout预测一致），给予正奖励（+1），直接增强正确预测概率；对不一致样本则不作用（奖励0），避免有害更新。
- **关键技术细节**：
  - 使用蒙特卡洛（MC）dropout估计预测概率和不确定性（多次前向传播取平均），实现更好的校准和不确定性估计。
  - 利用两个FIFO存储池（正确样本池MC、错误样本池MI）存储BFA样本，ABA则直接从当前未标记批次中选取一致样本。
  - 最终损失函数为BFA损失（对正确样本最小化交叉熵，对错误样本最大化交叉熵）与ABA损失（对一致样本最小化交叉熵）的加权和。
- **算法流程**（文字说明）：每个测试批次→选择k个最不确定样本→获取二元反馈→更新存储池→冻结BN统计→执行E轮迭代：从MC和MI中采样计算BFA损失；从未标记样本中选出一致样本计算ABA损失；联合优化更新模型参数。

## 3. 实验设计

- **数据集与场景**：
  - 图像损坏数据集：CIFAR10-C、CIFAR100-C、Tiny-ImageNet-C（全部15种损坏类型，严重度5）。
  - 域泛化场景：PACS数据集（四个域：art painting, cartoon, sketch, photo），包括域连续数据流和混合数据流。
  - 额外实验：ImageNet-C、ImageNet-R、ColoredMNIST、VisDA-2021、DomainNet。
- **基准方法**：
  - 无监督TTA：SrcValid, BN-Stats, TENT, EATA, SAR, CoTTA, RoTTA, SoTTA（这些方法被修改为利用二元反馈，即加入正确/错误样本的损失项）。
  - 主动TTA：SimATTA（原为全类标签，文中将其改为使用二元反馈版本SimATTA*）。
- **对比设置**：所有TTA基线均使用与BiTTA相同数量的二元反馈样本（每批次64个样本中仅3个反馈样本，占比<5%）。

## 4. 资源与算力

- 论文未明确说明具体的GPU型号、数量或训练时长。仅在附录D中提及实验主要使用NVIDIA RTX 3090和TITAN GPU。未提供总计算时间或能耗数据。

## 5. 实验数量与充分性

- **实验数量**：主实验覆盖4个数据集（3个损坏+1个域泛化），每种数据集下对比了9种基线方法+BiTTA。此外包含大量扩展实验：
  - 不同反馈错误率下的鲁棒性（图6）。
  - 不同反馈样本数量（k）的影响（图7）。
  - 不同样本选择策略（图9）。
  - 不同超参数α/β的敏感性（图10）。
  - 间歇/延迟标注场景（图11, 12）。
  - 不同MC-dropout迭代次数（图13）。
  - 不同架构（ResNet50, ViT-Base）验证（表11）。
  - 额外大规模数据集（表7）。
  - 非iid标签分布和batch size=1场景（表8）。
  - 与近期方法（DeYO, OWTTT, TAST）对比（表9,10）。
- **充分性**：实验设计较为全面，覆盖多种域偏移类型、多种标注预算、多种不确定性估计方式、多种架构、多种挑战场景，消融实验充分。对比方法均公平调整（使用同等数量二元反馈）。但缺少对真实人类标注噪声的模拟（仅用随机翻转模拟反馈错误）。

## 6. 主要结论与发现

- BiTTA在三个损坏数据集上平均准确率比最优基线提升13.3个百分点。
- 在等标注成本下（考虑信息增益），BiTTA（仅二元反馈）优于使用全类标签的主动TTA（SimATTA），最高提升32%。
- 将全类标签替换为GPT-4o生成伪标签时性能大幅下降，说明可靠的人类二元反馈更具价值。
- BFA与ABA协同工作：单独BFA仅58.9%，单独ABA为82.64%，结合后达到87.20%。
- MC-dropout比确定性softmax提供更优的校准（ECE降低38%），对样本选择和策略估计至关重要。
- BiTTA对超参数鲁棒，在间歇/延迟标注下保持稳定。

## 7. 优点

- **新颖的问题设置**：提出二元反馈TTA，大幅降低标注成本，更具实际可行性。
- **方法设计巧妙**：将强化学习与MC-dropout结合，统一处理二元反馈和无标签样本，双路径互补。
- **实验充分且公平**：涵盖多种数据集、多种基线、多种场景，所有基线均修改为使用相同数量的二元反馈。
- **性能显著**：在多个基准上大幅超越现有方法，甚至超越全类标签的主动TTA。
- **鲁棒性强**：对标注错误率、样本选择策略、超参数选择均表现出稳定性。

## 8. 不足与局限

- **仍依赖少量人类反馈**：尽管仅有二元反馈，在快速变化的域偏移下仍需持续提供反馈。
- **计算开销**：MC-dropout需多次前向传播，增加推理时间（但文中通过MECTA和梯度累积可减少内存）。
- **缺乏真实标注员实验**：仅通过模拟反馈误差验证鲁棒性，未在真实人机交互中测试。
- **可扩展性受限**：在大规模数据集（如ImageNet-C）上性能提升有限（仅约1-2个百分点），且随机选择样本已足够，说明不确定性选择策略可能不是关键瓶颈。
- **局限性**：未考虑反馈延迟/丢失等更实际的人为因素；未讨论隐私、偏见等伦理问题（仅在Impact Statement提及）。

（完）
