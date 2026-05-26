---
title: Ranked Entropy Minimization for Continual Test-Time Adaptation
title_zh: 持续测试时自适应的排名熵最小化
authors: "Jisu Han, Jaemin Na, Wonjun Hwang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=lHaGLJ65J9"
tags: ["query:tta"]
score: 9.0
evidence: 持续在线TTA与稳定性
tldr: 持续测试时自适应中，熵最小化方法易陷入模型坍塌（全预测同一类）。本文提出排名熵最小化，通过渐进式难度结构避免平凡解，在持续场景下稳定适应。实验证明该方法有效缓解了稳定性问题，扩展了熵最小化的适用范围。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lhaglj65j9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 800, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lhaglj65j9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1681, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lhaglj65j9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 866, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lhaglj65j9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 737, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lhaglj65j9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lhaglj65j9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1741, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lhaglj65j9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 799, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lhaglj65j9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1479, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lhaglj65j9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1475, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lhaglj65j9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1414, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lhaglj65j9/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 767, \"height\": 531, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1775, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1775, \"height\": 513, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 513, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 857, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1680, \"height\": 542, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1774, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1773, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 673, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 800, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1605, \"height\": 874, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1777, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 967, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1342, \"height\": 166, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 799, \"height\": 166, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 934, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1088, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lhaglj65j9/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 884, \"height\": 473, \"label\": \"Table\"}]"
motivation: 熵最小化在持续TTA中易导致模型崩塌，需要提升稳定性。
method: 提出排名熵最小化，通过渐进式难度结构组织预测。
result: 在持续TTA场景下抑制了模型崩塌，性能优于现有方法。
conclusion: 排名熵最小化有效解决了持续TTA中的稳定性问题。
---

## Abstract
Test-time adaptation aims to adapt to realistic environments in an online manner by learning during test time.  Entropy minimization has emerged as a principal strategy for test-time adaptation due to its efficiency and adaptability. Nevertheless, it remains underexplored in continual test-time adaptation, where stability is more important. We observe that the entropy minimization method often suffers from model collapse, where the model converges to predicting a single class for all images due to a trivial solution. We propose ranked entropy minimization to mitigate the stability problem of the entropy minimization method and extend its applicability to continuous scenarios. Our approach explicitly structures the prediction difficulty through a progressive masking strategy. Specifically, it gradually aligns the model's probability distributions across different levels of prediction difficulty while preserving the rank order of entropy. The proposed method is extensively evaluated across various benchmarks, demonstrating its effectiveness through empirical results.

---

## 论文详细总结（自动生成）

# 论文详细中文总结：Ranked Entropy Minimization for Continual Test-Time Adaptation

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：真实世界数据分布是非独立同分布的，深度学习模型在测试时面临分布偏移（distribution shift）导致性能下降。测试时自适应（Test-Time Adaptation, TTA）允许模型在测试阶段在线适应无标签的目标域数据。持续测试时自适应（Continual TTA, CTTA）进一步要求模型在连续变化的多个域中顺序适应，并克服灾难性遗忘。
- **核心挑战**：现有CTTA方法主要分为两类：
  - **熵最小化（EM）**：计算高效，但易陷入**模型坍塌**——模型对所有输入预测同一个类别（平凡解），如图2所示。这是因为EM的损失函数在完美置信预测时也为零（Case 2），且稳定性不足。
  - **一致性正则化（CR）**：通过教师-学生框架保持稳定性，但计算成本高，效率低。
- **研究动机**：作者观察到，对图像添加显式掩码（例如遮挡前景物体）会降低预测准确度并提高熵（见图1、图3）。受“阿喀琉斯与龟”悖论启发，他们希望**保持原始预测（龟）和掩码预测（阿喀琉斯）之间的排名关系**，通过逐步追赶的方式避免熵的骤降，从而在EM的高效性与CR的稳定性之间取得平衡。

## 2. 方法论

### 核心思想：排名熵最小化（Ranked Entropy Minimization, REM）

- **显式掩码链（Explicit Mask Chaining）**：
  - 利用ViT的自注意力结构计算每个图像块（patch）的注意力得分（公式2），选出得分最高的（即包含前景物体的）patch进行掩码。
  - 定义一系列递增的掩码比例 \(0 \le m_1 \le m_2 \le \cdots \le m_N \le 1\)，得到一组逐渐被遮挡更多前景的图像 \(\{x^{m_1}, x^{m_2}, \dots, x^{m_N}\}\)。
  - 经验表明（图3）：随着掩码比例增加，预测误差单调上升，熵单调上升，从而建立了**显式的预测难度排名**。

- **双重损失函数**：
  1. **掩码一致性损失（Masked Consistency Loss, MCL）**：
     \[
     \mathcal{L}_{\text{MCL}} = \sum_{i<j} H(f_t(x^{x_j}), \text{sg}(f_t(x^{x_i})))
     \]
     其中 \(H\) 是交叉熵，\(\text{sg}\) 是停止梯度操作。该损失让高掩码率（低置信度）的预测向低掩码率（高置信度）的预测对齐，间接降低熵，且避免了直接熵最小化导致的突变。
  2. **熵排名损失（Entropy Ranking Loss, ERL）**：
     \[
     \mathcal{L}_{\text{ERL}} = \sum_{i<j} \max(0, S(f_t(x^{x_i})) - \text{sg}(S(f_t(x^{x_j}))) + m)
     \]
     其中 \(S\) 是熵，\(m\) 是边距。该损失强制保持熵的排名：低掩码率图像的熵应低于高掩码率图像的熵。这防止了模型对遮挡背景的过置信预测，直接约束排名违反的样本。

- **总损失**：
  \[
  \mathcal{L}_{\text{REM}} = \mathcal{L}_{\text{MCL}} + \lambda \mathcal{L}_{\text{ERL}}
  \]

- **与现有方法的比较**：
  - 相比EM：不使用预测熵作为损失，而是通过交叉熵间接降低熵，更稳定。
  - 相比CR：不需要额外的教师模型或多次前向传播，仅用同一模型通过掩码链生成多个预测，计算开销小（仅需2次额外前向传播）。

## 3. 实验设计

### 数据集与场景
- **CTTA基准测试**：
  - ImageNet → ImageNet-C（15种损坏，严重度5）
  - CIFAR10 → CIFAR10C， CIFAR100 → CIFAR100C（同样15种损坏）
- **其他TTA场景（附录C、D）**：
  - 在线不平衡标签偏移、批大小1、混合分布偏移、域偏移（ImageNet-R/V2/Sketch）
  - 视觉语言模型（CLIP）下的TTA（CIFAR、VisDA、Office-Home、PACS、VLCS）
  - 时间约束场景（ImageNet-3DCC）
  - 不同网络架构（Mobile-ViT、Swin Transformer、WideResNet等）

### 对比方法
- 单模型方法：Pseudo-label、Tent、VDP、SAR、DeYO、EATA等
- 教师-学生方法：CoTTA、PETAL、ViDA、Continual-MAE
- 监督上限（使用目标标签的交叉熵）

### 评估指标
- 分类错误率（Error Rate，%），以及相对于源模型的增益（Gain）

## 4. 资源与算力

- 论文**未明确说明**使用的GPU型号、数量或训练总时长。
- 附录B给出了实现细节：优化器Adam，学习率1e-3，批大小50（ImageNet-C）。CIFAR数据集输入尺寸384×384，其他224×224。
- 表5提供了效率比较：REM在单张测试集上总耗时17分21秒（相比Tent的8分35秒更慢，但远快于Continual-MAE的59分56秒）；训练参数仅0.03M（仅更新归一化层），前向传播次数3，模型数量1。
- 推理时间上，REM因额外2次前向传播（通过掩码链）比纯EM稍慢，但仍显著优于CR方法。

## 5. 实验数量与充分性

- **实验数量很多**：
  - 主表：三个CTTA基准（表1-3），共45个域测试。
  - 前向/后向迁移分析（表4、图4-6）。
  - 消融实验：组件影响（图9）、掩码策略（前景/背景/随机，图10）、超参数敏感性（附录J，图12）、掩码比例（表18）。
  - 扩展实验：在线TTA场景（表7-10）、CLIP模型（表11）、时间约束（表12）、不同架构（表13-14）、校准误差（表15）、与增强方法比较（表16）、失败案例分析（表17）。
- **公平性**：所有对比方法均使用相同骨干网络（ViT-B/16），遵循已有开源框架（Continual-MAE、ViDA）的实现，超参数根据验证集调整。
- **客观性**：实验覆盖了多种分布偏移类型和实际场景，消融系统，可视化（图7-8）支持了设计动机。失败案例亦被讨论（附录I）。

## 6. 主要结论与发现

- REM在ImageNet-C上平均错误率39.2%，比源模型提升16.6%，超越之前的SOTA Continual-MAE（42.5%）3.3%，距离监督上限（35.7%）仅差3.5%。
- 在CIFAR10C和CIFAR100C上分别达到9.4%和23.4%错误率，同样大幅领先。
- 模型坍塌被有效抑制：可视化（图2、图7）显示REM保持预测多样性，而Tent在后期收敛到单一类别。
- 在效率方面，REM仅更新归一化层（0.03M参数），无需额外教师模型，总耗时为Continual-MAE的29%，兼具高效与稳定。
- 在不同TTA场景（标签偏移、小批大小、域偏移、CLIP等）中也取得SOTA或竞争性结果，证明了普适性。

## 7. 优点

1. **方法创新**：利用ViT自注意力显式定位前景进行掩码，构建自然难度排名，思路简洁直观。
2. **双损失互补**：MCL促进预测一致性，ERL保持熵排名，共同避免了熵最小化的平凡解问题。
3. **效率高**：仅需单模型、少量参数更新，比CR方法快很多，适合实时部署。
4. **实验充分**：在多个基准、多种场景、多种骨干网络上验证，消融全面，可视化支持清晰。
5. **可扩展性**：可以即插即用到其他TTA方法（如WATT+REM提升），也能推广到CNN架构（通过激活图或Grad-CAM替代注意力）。

## 8. 不足与局限

1. **缺乏严格理论证明**：作者承认排名熵的单调性假设（掩码增加→熵增加）主要基于经验观察，未给出理论保障，存在反例（如某些图像掩码后预测变化不单调）。
2. **依赖ViT自注意力**：原始方法基于ViT的注意力得分进行掩码。虽通过FA/Grad-CAM扩展到了CNN（表14），但性能提升较小，通用性仍需进一步验证。
3. **对简单域的适应可能较慢**：失败案例分析（附录I）显示，在亮度、JPEG等容易域，原始与掩码预测差异小，导致损失小，适应速度可能不及专门针对简单域的方法。
4. **额外前向开销**：相比纯EM方法（Tent），REM需要3次前向传播（原始+2个掩码），增加了约2倍的推理时间（表5），在严格时间约束下可能不占优势（见表12中的Episodic场景）。
5. **超参数敏感度**：掩码比例 \(M_N\)、边距 \(m\)、权重 \(\lambda\) 需要调整，尽管论文显示敏感性低，但最佳设置（N=3, λ=1, m=0）仍需在具体数据集上调。

（完）
