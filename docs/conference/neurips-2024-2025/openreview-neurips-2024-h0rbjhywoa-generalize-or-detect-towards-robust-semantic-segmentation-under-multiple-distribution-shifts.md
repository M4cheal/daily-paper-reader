---
title: Generalize or Detect? Towards Robust Semantic Segmentation Under Multiple Distribution Shifts
title_zh: 泛化还是检测？多重分布偏移下的鲁棒语义分割
authors: "Zhitong Gao, Bingnan Li, Mathieu Salzmann, Xuming He"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=h0rbjHyWoa"
tags: ["query:ris"]
score: 6.0
evidence: 处理语义分割中的分布偏移，方法可迁移至指代分割域偏移
tldr: 现有语义分割模型在开放世界中难以区分域偏移和语义偏移，导致异常检测和泛化性能差。本文提出一种生成式增广方法，同时合成包含异常物体和多种协变量偏移的图像，并设计训练策略使模型能泛化到新域同时精确检测语义偏移。实验表明该方法在多个合成和真实分布偏移场景下提升了鲁棒性，为指代分割中的域偏移问题提供了可迁移的方法论。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-h0rbjhywoa/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-h0rbjhywoa/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-h0rbjhywoa/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-h0rbjhywoa/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-h0rbjhywoa/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-h0rbjhywoa/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1432, \"height\": 520, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 644, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1156, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 665, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 657, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 359, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 357, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1235, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1444, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1449, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1108, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1443, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-h0rbjhywoa/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1448, \"height\": 257, \"label\": \"Table\"}]"
motivation: 针对开放环境中域偏移与语义偏移混杂导致现有分割模型泛化与检测能力不足的问题。
method: 设计生成式增广方法产生同时包含异常物体和协变量偏移的合成图像，并引入训练策略区分两种偏移。
result: 在多个分布偏移基准上显著提升语义分割模型的泛化能力和异常检测准确率。
conclusion: 所提方法有效增强了模型对多层次分布偏移的鲁棒性，可推广至指代分割等下游任务。
---

## Abstract
In open-world scenarios, where both novel classes and domains may exist, an ideal segmentation model should detect anomaly classes for safety and generalize to new domains. However, existing methods often struggle to distinguish between domain-level and semantic-level distribution shifts, leading to poor OOD detection or domain generalization performance. In this work, we aim to equip the model to generalize effectively to covariate-shift regions while precisely identifying semantic-shift regions. To achieve this, we design a novel generative augmentation method to produce coherent images that incorporate both anomaly (or novel) objects and various covariate shifts at both image and object levels. Furthermore, we introduce a training strategy that recalibrates uncertainty specifically for semantic shifts and enhances the feature extractor to align features associated with domain shifts. We validate the effectiveness of our method across benchmarks featuring both semantic and domain shifts. Our method achieves state-of-the-art performance across all benchmarks for both OOD detection and domain generalization. Code is available at https://github.com/gaozhitong/MultiShiftSeg.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在开放世界场景中，语义分割模型同时面临两类分布偏移：**协变量偏移**（如天气、时间、地点等新域）和**语义偏移**（如未知物体或异常类别）。现有方法要么专注于域泛化，要么专注于异常检测，但无法有效区分二者。域泛化方法会降低异常检测能力，而异常检测方法会对域偏移区域产生过高不确定性，导致泛化性能下降。
- **研究动机**：为了在真实世界中同时处理两种偏移，需要一个既能对语义偏移区域进行精确检测（高不确定性），又能对协变量偏移区域进行有效泛化（低不确定性）的统一模型。
- **整体含义**：本文首次深入研究语义分割中同时存在两类分布偏移的挑战，提出一种生成式增广和两阶段训练策略，使模型学会区分并分别应对两种偏移，从而在多个基准上达到最优性能。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过生成同时包含异常物体和多种协变量偏移的连贯图像，训练模型区分两类偏移；并设计一个针对语义偏移的可学习不确定性函数以及两阶段训练流程，确保模型对语义偏移给出高不确定性，对域偏移给出低不确定性。
- **关键技术细节**：
  1. **生成式增广（CG-Aug）**：
     - 使用**ControlNet**（基于Stable Diffusion）实现**零样本语义到图像生成**。
     - 过程：首先将已知类别的训练图像标签与从辅助OOD集（如ADE20K的thing类）中裁剪的异常物体掩码拼接，得到增强的语义掩码；然后输入ControlNet，配合文本提示（指定地点、天气、时间及OOD类别），生成包含两种偏移的连贯图像。
     - **自动过滤**：利用预训练分割模型和SAM对生成图像进行质量检查，剔除未生成物体或生成错误类别的样本。
  2. **可学习不确定性函数**：
     - 对于像素级模型（DeepLabv3+），采用能量函数形式：`u(x) = log Σ_c exp(f(x)W^o_c)`。
     - 对于掩码级模型（Mask2Former），采用最大softmax概率形式（MSP）。
     - 初始化时，将可学习投影矩阵W^o设置为原分割网络的类别权重。
  3. **相对对比损失（Relative Contrastive Loss）**：
     - 定义三类像素：原始图像中的已知类（Ω_in）、增强图像中的已知类（Ω_aug，即协变量偏移区域）、所有图像中的未知类（Ω_out，即语义偏移区域）。
     - 损失函数：鼓励未知类与已知类之间的不确定性差距大（前两项），同时鼓励协变量偏移区域与原始已知类之间的不确定性差距小（第三项）。
     - 使用边际对比损失 `τ_λ(x)=max(λ−x,0)`。
  4. **两阶段噪声感知训练（Two-Stage Noise-Aware Training）**：
     - **第一阶段**：冻结特征提取器，仅训练不确定性函数（使用相对对比损失）。
     - **第二阶段**：微调特征提取器，同时使用分割损失（交叉熵或Dice+BCE）和对比损失。
     - **噪声感知选择**：对生成图像，计算每个像素的交叉熵损失，只保留损失较小的像素进行反向传播（“小损失”准则），避免生成错误区域影响训练。
- **整体损失**：`L = L_unc + β1 * L_in_seg + β2 * L_aug_seg`。

### 3. 实验设计：数据集、基准、对比方法

- **训练集**：Cityscapes（所有方法均在其上训练）。
- **测试集**：
  - **异常分割基准**：RoadAnomaly（60张真实道路异常图），SMIYC RA21/RO21（共约100+327张测试图，包含域偏移）。
  - **联合测试基准**：ACDC-POC（基于ACDC验证集，包含200张不同天气/夜晚场景的生成异常图），MUAD（合成数据集，240张包含多种域偏移和异常）。
- **基准**：采用AUC、AP、FPR95评估异常检测；mIoU、mAcc评估已知类分割。
- **对比方法**：
  - 异常检测方法：MaxSoftmax、ODIN、Mahalanobis、Image Resynthesis、SynBoost、MaxEntropy、PEBAL、DenseHybrid、RPL+CoroCL、Mask2Anomaly、RbA、M2F-EAM。
  - 域泛化方法：RuleAug（规则增广）、RobustNet（实例选择性白化）。
  - 结合方法：RPL（含DG+OOD）、OOD+RuleAug。
- **消融实验**：评估CG-Aug、可学习不确定性函数、相对对比损失、噪声感知选择、两阶段训练、生成数据规模、超参数等。

### 4. 资源与算力

- 论文在**附录A.3和A.4**中明确说明：
  - **DeepLabv3+架构**：使用2×NVIDIA A40 48GB GPU，Adam优化器，学习率1e-6，batch size 8。
  - **Mask2Former架构**：使用1×NVIDIA A40 48GB GPU，AdamW优化器，batch size 8。
  - **生成阶段**：采用ControlNet（Stable Diffusion）离线生成，但未报告生成所需的具体GPU型号和时长。
- 总体而言，论文提供了推理和训练所需的硬件信息，但未详细报告总训练时长和生成数据的时间成本。

### 5. 实验数量与充分性

- **主要实验**：
  - 表1：在3个异常分割基准上的性能对比（DeepLabv3+和Mask2Former两组骨干）。
  - 表2：在ACDC-POC和MUAD上的联合评估（异常检测+域泛化），包含8种对比方法。
  - 表3：消融CG-Aug和训练策略（以Mask2Anomaly为基线）。
  - 表4：CG-Aug各变体对比（语义偏移、域偏移、两步骤等）。
  - 表5：训练组件消融（可学习不确定性、对比损失、选择机制）。
  - 表6-12（附录）：超参数鲁棒性、生成数据规模影响、RPL上的解耦分析、ACDC各域拆分结果、每类分割结果、与POC对比、与域泛化方法在原始ACDC上的对比。
- **充分性**：实验覆盖了多个具有挑战性的数据集，对比了当前最先进的异常检测、域泛化及组合方法，进行了充分的消融（数据、损失、训练策略、超参数）。实验设计客观、公平（保持骨干和训练设置一致）。统计指标（AUC、AP、FPR95、mIoU、mAcc）全面。不足之处在于未提供误差线（论文未说明重复次数），但这在语义分割的此类基准中常见。

### 6. 论文的主要结论与发现

- 现有域泛化方法会损害异常检测性能，异常检测方法会降低域泛化性能，简单组合效果有限。
- 提出的生成式增广（CG-Aug）能同时生成两种偏移的连贯图像，显著优于分离生成或仅使用一种偏移的方法。
- 相对对比损失和两阶段训练能有效区分两种偏移，使模型对语义偏移区域保持高不确定性，对域偏移区域保持低不确定性。
- 在两款骨干（DeepLabv3+和Mask2Former）上，该方法在所有5个基准上均达到最先进性能，同时提升异常检测和域泛化。

### 7. 优点

- **方法创新**：首次在单一框架内同时处理多种分布偏移，设计了生成式增广和针对性训练策略，概念清晰。
- **架构无关**：可应用于像素级和掩码级分割模型，具有泛化潜力。
- **实验全面**：覆盖多个真实世界和合成基准，与大量基线对比，消融充分，结果可靠。
- **鲁棒性**：对超参数变化不敏感（表6），生成数据规模增大性能持续提升（附录B.2）。
- **代码开源**：提供了可复现的实现。

### 8. 不足与局限

- **依赖生成模型质量**：ControlNet生成的图像可能在OOD物体渲染上存在瑕疵（形状、纹理不一致）。尽管有自动过滤和在线选择，某些类别（如植被、栅栏）的生成质量差，导致对应类别分割性能下降（表9中植被mIoU下降3%）。
- **性能饱和**：生成数据规模增大到2x/3x后性能提升趋于平缓，可能受限于生成噪声。
- **未处理特定场景**：生成失败率较高的情况包括远景、小物体、文字相关元素（附录E）。
- **计算开销**：生成阶段需要大量离线计算，训练阶段需两阶段微调，整体资源消耗较大。
- **无误差棒报告**：未给出多次实验的方差，统计严谨性稍弱。
- **可迁移性**：方法依赖于Cityscapes作为源域，对其他源域的泛化能力未验证。

（完）
