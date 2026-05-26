---
title: "L-TTA: Lightweight Test-Time Adaptation Using a Versatile Stem Layer"
title_zh: L-TTA：使用通用茎层的轻量级测试时自适应
authors: "Jin Shin, Hyun Kim"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=G7NZljVOol"
tags: ["query:tta"]
score: 8.0
evidence: 通过重构第一层实现轻量级测试时自适应
tldr: 现有测试时自适应方法通常最小化熵，但需要整个模型的前向/反向传播。本文提出L-TTA，通过重构模型的第一层（stem层）来最小化不确定性，仅需少量主干网络参与。该方法摆脱了对熵最小化的依赖，实现了更高效的在线自适应。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-g7nzljvool/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-g7nzljvool/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-g7nzljvool/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-g7nzljvool/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 711, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-g7nzljvool/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 710, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-g7nzljvool/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 706, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-g7nzljvool/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 703, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-g7nzljvool/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 427, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-g7nzljvool/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 953, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-g7nzljvool/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-g7nzljvool/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 734, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-g7nzljvool/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 714, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-g7nzljvool/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 705, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-g7nzljvool/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1445, \"height\": 799, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-g7nzljvool/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-g7nzljvool/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 577, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-g7nzljvool/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 647, \"height\": 389, \"label\": \"Table\"}]"
motivation: 现有TTA方法过度依赖熵最小化且需要完整模型更新，计算成本高。
method: 通过重构模型第一层（茎层）来最小化不确定性，减少主干网络参与。
result: 仅需轻微修改茎层即可实现高效自适应，保持主干网络不变。
conclusion: L-TTA提供了一种轻量级、即插即用的TTA方案，降低了计算开销。
---

## Abstract
Test-time adaptation (TTA) is the most realistic methodology for adapting deep learning models to the real world using only unlabeled data from the target domain. Numerous TTA studies in deep learning have aimed at minimizing entropy. However, this necessitates forward/backward processes across the entire model and is limited by the incapability to fully leverage data based solely on entropy. This study presents a groundbreaking TTA solution that involves a departure from the conventional focus on minimizing entropy. Our innovative approach uniquely remodels the stem layer (i.e., the first layer) to emphasize minimizing a new learning criterion, namely, uncertainty. This method requires minimal involvement of the model's backbone, with only the stem layer participating in the TTA process. This approach significantly reduces the memory required for training and enables rapid adaptation to the target domain with minimal parameter updates. Moreover, to maximize data leveraging, the stem layer applies a discrete wavelet transform to the input features. It extracts multi-frequency domains and focuses on minimizing their individual uncertainties. The proposed method integrated into ResNet-26 and ResNet-50 models demonstrates its robustness by achieving outstanding TTA performance while using the least amount of memory compared to existing studies on CIFAR-10-C, ImageNet-C, and Cityscapes-C benchmark datasets. The code is available at https://github.com/janus103/L_TTA.

---

## 论文详细总结（自动生成）

以下是基于论文《L-TTA: Lightweight Test-Time Adaptation Using a Versatile Stem Layer》的详细中文总结，按照指定要点依次展开。

---

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：深度学习模型在真实世界中常面临**域偏移 (domain shift)**，即训练域（源域）与测试域（目标域）数据分布不一致。测试时自适应（TTA）旨在仅利用目标域无标签数据、无需源域数据，在线调整模型以提升泛化能力。
- **现有问题**：主流 TTA 方法（如 TENT、EATA、SAR、REALM）基于**最小化预测熵**来适应目标域。然而，计算熵需要在整个模型上执行前向/反向传播，导致：
  - 训练成本和内存占用巨大（梯度存储、全局前向/反向）；
  - 仅依赖熵值难以充分挖掘单样本中的信息；
  - 对噪声数据敏感，需要额外过滤机制。
- **本文目标**：提出一种**轻量级 TTA 方案**，放弃熵最小化策略，转而**最小化特征通道的不确定性**，并仅对模型的第一层（stem layer）进行微调，大幅降低训练开销，同时保持甚至提升适应性。

### 2. 论文提出的方法论

#### 核心思想
- 重构模型的第一层（stem layer），使其能**端到端地提取通道注意力及其不确定性**，并通过**负对数似然 (NLL) 损失**最小化不确定性，而非最小化预测熵。
- 仅更新重构后的 stem layer 参数，主干网络（backbone）完全冻结，无需全局前向/反向。

#### 关键技术细节
- **GCAL (Gaussian Channel Attention Layer)**：基于 Squeeze-and-Excitation (SE) 块，但输出不是单一的 scale 因子，而是**高斯分布的均值和方差**（通道数翻倍）。对每个通道，令 \(\gamma_\mu\) 和 \(\gamma_P\) 分别表示均值和方差，不确定性定义为方差 \(\gamma_P\)。损失函数为：
  \[
  \mathcal{L}_{\text{uncertainty}} = \frac{1}{C} \sum_{i=0}^{C-1} -\log p_i(\mu_{\text{gt}}; \gamma_\mu, \gamma_P)
  \]
  其中 \(\mu_{\text{gt}}=1\)（sigmoid 最大值），该损失在预训练和 TTA 阶段均适用。

- **DEL (Domain Embedding Layer)**：在 stem layer 的卷积操作前加入**二维离散小波变换 (2D DWT)**，将输入特征分解为多个频域（低频 LFC 和高频 HFC），使得 GCAL 能独立计算每个频道的 uncertainty；最后通过逆 DWT (IDWT) 恢复原特征形状，实现**非侵入式设计**，便于集成到任意 CNN 模型。

- **全向分解 (ODD)**：进行两次 DWT 分解（level=2），进一步分离边缘和噪声信息，提高对单样本的敏感性。

- **间隔训练 (Interval Training)**：为应对连续 TTA 中的灾难性遗忘，每若干迭代（如 CIFAR-10-C 每 20 次，ImageNet-C 每 10 次）将 stem layer 权重重新初始化为预训练权重，然后继续自适应。

#### 算法流程
1. 将预训练模型中的 stem layer 替换为重构后的 stem layer（包含 DWT → CONV → GCAL → IDWT）。
2. 在源域数据上进行少量预热训练（10 epochs），同时最小化任务损失（交叉熵）和不确定性损失。
3. 测试时，仅对新输入的 stem layer 计算 GCAL 的不确定性，更新 stem layer 参数（仅反向传播到 stem layer），主干网络不变。
4. 使用间隔训练策略周期性重置 stem layer 权重，防止遗忘。

### 3. 实验设计

- **数据集**：
  - **分类任务**：CIFAR-10-C、CIFAR-100-C、ImageNet-C（各含 15 种 corruption，严重度 5）。
  - **语义分割**：Cityscapes-C（4 种天气 corruption：brightness、foggy、frost、snow，严重度 5）。
  - **鲁棒性扩展**：ImageNet-Sketch、ImageNet-R、ImageNet-A（见附录 C）。

- **基准模型**：ResNet-26、ResNet-50（分类）；DeepLabV3Plus with ResNet-50 backbone（分割）。

- **对比方法**：
  - 基于熵最小化：TENT、MEMO、EATA、SAR、REALM。
  - 记忆高效：EcoTTA、BN STAT。
  - 扩散驱动：DDA。
  - 其他：CoTTA、TTT++、SWRNSP、T3A、LAME、NOTE 等（见附录）。

- **评估指标**：分类任务使用**预测错误率**（越低越好）；分割任务使用 **mIoU**（越高越好）；同时报告**内存占用 (MB)** 和**训练延迟**。

- **消融实验**：
  - GCAL 与 DEL 的贡献（w/o GCAL、w/o DEL）。
  - DWT 层级（level 1 vs level 2）。
  - SE 块缩减比例（reduction size）。
  - 间隔训练迭代数。
  - 小批量场景（batch size = 1,2,4,8）。

### 4. 资源与算力

- **硬件配置**：Intel® Xeon® Gold 5218R CPU，NVIDIA Tesla A100 80G GPU。
- **最小 GPU 内存需求**：约 **12GB**（作者注明）。
- **训练时间**：在图 5 中，L-TTA 的总延迟（CPU+GPU）比 TENT 快 4.25 倍，比 DDA 快 49.56 倍，比 EcoTTA 快 1.76 倍。
- **实验成本**：论文未详细报告每次实验的精确训练时长或总 GPU 小时数，但给出了相对比较。

### 5. 实验数量与充分性

- **实验数量**：非常充分。
  - 主要结果（表 1）涵盖 3 个分类数据集 × 15 种 corruption，对比 7 种以上方法。
  - 分割任务（表 2）对比 4 种方法。
  - 消融实验（图 6、图 7、表 4、表 5）覆盖 DWT 层级、缩减比例、小批量、间隔迭代。
  - 扩展实验（附录 C、E、F）：3 个极端数据集、不同 backbone（MobileViT）、与 SFDA 方法对比、多种子稳定性测试（10 种子，平均精度 64.85%，标准差 0.02）。
- **充分性与公平性**：
  - 实验设置规范（严重度统一为 5、使用公开 benchmark）。
  - 内存占用使用 TinyTL 提供的官方测量方法，与 EcoTTA 一致。
  - 在 CIFAR-10-C 上，明显优于所有对比方法；在 ImageNet-C 上，精度虽略低于部分方法（如 REALM），但内存仅为 1.7%，符合轻量级目标。
  - 消融实验设计清晰，验证了各组件贡献。

### 6. 论文的主要结论与发现

- **核心发现**：用**不确定性最小化替代熵最小化**，并仅微调第一层（stem layer）即可在多种域偏移下取得有竞争力的 TTA 性能，同时**内存消耗极低**（在 ImageNet-C 上仅为 SOTA 方法的 1.7%）。
- **性能总结**：
  - CIFAR-10-C：平均错误率 17.1%，比 SOTA (REALM) 降低 5.4%。
  - ImageNet-C：平均错误率 64.9%，虽略高于 REALM (62.2%)，但内存仅 6.4 MB（REALM 约 373 MB）。
  - Cityscapes-C：mIoU 达 59.8%，比记忆高效方法 EcoTTA 高 4.6%，内存仅 0.4 MB。
  - **小批量鲁棒性**：在 batch size=1 时，错误率 75.16%，而 TENT 等接近 100%。
- **结构发现**：DWT (DEL) 引入的多频域分解能明显提升单样本数据利用率；GCAL 的不确定性最小化在小批量下表现稳定。

### 7. 优点

- **创新性**：首次提出从熵最小化转向不确定性最小化，重构 stem layer 而非整个模型。
- **高效性**：仅更新 stem layer，计算和内存开销极低；训练时间远快于现有方法。
- **非侵入性**：通过 DEL 的 IDWT 保证输出形状不变，可即插即用到任意 CNN 模型（ResNet、MobileViT 均验证）。
- **鲁棒性**：小批量（甚至单样本）下仍能保持有效自适应，解决了传统 TTA 在批量小、样本少时的瘫痪问题。
- **实验全面**：覆盖分类、分割、多种数据集、消融、小批量、连续训练等场景，且进行多种子稳定性验证。

### 8. 不足与局限

- **分类数依赖**：当类别数很多（如 ImageNet-C 1000 类）时，仅 stem layer 调优带来的性能提升有限，不如部分全局调优方法（但代价是内存大增）。作者在附录 F 中承认这是维度灾难的影响。
- **需要间隔训练**：若不做间隔重置，持续最小化不确定性可能导致过拟合或发散（尤其在 ImageNet-C 上表现不一），增加了调参复杂性。
- **仅适用于 CNN backbone**：虽在 MobileViT（含 transformer）上测试，但整体设计依赖卷积操作和 DWT 的空间特性，对纯 transformer 模型可能不直接适用。
- **未充分讨论社会影响**：论文未涉及公平性、隐私等议题，但作为基础方法学论文，影响较小。
- **资源报告不完整**：未给出单次实验的精确 GPU 小时数，仅给出相对延迟比较。

---

（完）
