---
title: Variational Continual Test-Time Adaptation
title_zh: 变分连续测试时自适应
authors: "Fan Lyu, Kaile Du, Yuyang Li, hanyu zhao, Fuyuan Hu, Zhang Zhang, Guangcan Liu, Liang Wang"
date: 2024-05-10
pdf: "https://openreview.net/pdf?id=mdK1vhgpa5"
tags: ["query:tta"]
score: 9.0
evidence: 提出变分连续测试时自适应方法
tldr: 针对连续测试时自适应（CTTA）中的误差累积和不确定性问题，本文提出了VCoTTA方法。该方法在源阶段通过变分预热策略将预训练模型转换为贝叶斯神经网络，在测试阶段利用均值教师框架进行变分推断。实验表明，该方法有效缓解了误差累积，提升了在连续域偏移下的鲁棒性。
source: NeurIPS-2024-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-mdk1vhgpa5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1059, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-mdk1vhgpa5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1028, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-mdk1vhgpa5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 887, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-mdk1vhgpa5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 714, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-mdk1vhgpa5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 711, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-mdk1vhgpa5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 992, \"height\": 512, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 875, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1434, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 705, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 710, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 728, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 705, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1062, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 841, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1313, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 843, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 676, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mdk1vhgpa5/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 702, \"height\": 224, \"label\": \"Table\"}]"
motivation: 连续测试时自适应面临模型更新不确定性导致的误差累积问题。
method: 提出变分贝叶斯方法VCoTTA，包括变分预热和均值教师变分推断。
result: 在多个CTTA基准上取得SOTA性能，有效降低误差累积。
conclusion: VCoTTA通过贝叶斯框架为CTTA提供了一种鲁棒的解决方案。
---

## Abstract
Continual Test-Time Adaptation (CTTA) task investigates effective domain adaptation under the scenario of continuous domain shifts during testing time. 
Due to the utilization of solely unlabeled samples, there exists significant uncertainty in model updates, leading CTTA to encounter severe error accumulation issues.
In this paper, we introduce VCoTTA, a variational Bayesian approach to measure uncertainties in CTTA. 
At the source stage, we transform a pre-trained deterministic model into a Bayesian Neural Network (BNN) via a variational warm-up strategy, injecting uncertainties into the model. 
During the testing time, we employ a mean-teacher update strategy using variational inference for the student model and exponential moving average for the teacher model. 
Our novel approach updates the student model by combining priors from both the source and teacher models. 
The evidence lower bound is formulated as the cross-entropy between the student and teacher models, along with the Kullback-Leibler (KL) divergence of the prior mixture. 
Experimental results on three datasets demonstrate the method's effectiveness in mitigating error accumulation within the CTTA framework.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：连续测试时自适应（CTTA）任务中，模型需要在测试阶段持续应对不断变化的域偏移，且只能使用无标签样本，导致模型更新存在显著不确定性，引发严重的**误差累积**问题。
- **研究动机**：现有CTTA方法（如熵最小化）容易产生过于自信且校准不佳的预测，无法可靠量化不确定性。可靠的不确定性估计在连续域偏移场景下至关重要。
- **整体含义**：本文旨在设计一种CTTA流程，既能在域偏移下提升预测精度，又能提供可靠的不确定性估计，从而缓解误差累积。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：利用贝叶斯神经网络（BNN）和在线变分推断（VI）来度量CTTA中的不确定性，通过均值教师结构结合源模型先验与教师先验，缓解不可靠先验导致的误差传播。
- **关键技术细节**：
  1. **变分预热（Variational Warm-up）**：在源阶段，将预训练的确定性CNN通过变分推断（引入局部重参数化技巧）转换为BNN，注入不确定性。
  2. **均值教师架构（Mean-Teacher）**：测试阶段，学生模型通过VI更新，教师模型通过指数移动平均（EMA）更新。
  3. **先验混合（Mixture of Priors）**：学生模型更新时，当前先验为源先验与教师先验的加权和，权重由两个模型在多种数据增强下的平均熵动态计算。对应的ELBO由学生-教师之间的对称交叉熵和两个KL散度的上界组成（公式15）。
  4. **模型推理**：使用混合先验进行预测，仅用期望值减少随机性。
- **算法流程**（文字说明）：
  - 输入：源数据、预训练模型、无标签测试域序列。
  - 步骤1：变分预热获得源BNN。
  - 步骤2：对于每个测试样本，先用混合先验预测标签，然后更新学生模型（优化公式15），最后通过EMA更新教师模型。

## 3. 实验设计：数据集、场景、benchmark、对比方法

- **数据集**：CIFAR10C、CIFAR100C、ImageNetC，每个包含15种常见腐蚀（如高斯噪声、散粒噪声等），每种有5个严重等级。
- **场景**：标准的CTTA场景，即连续改变腐蚀类型和严重等级；还测试了逐渐腐蚀（严重等级渐变）和循环腐蚀。
- **Benchmark**：采用分类错误率（%）作为主要指标，还使用负对数似然（NLL）和Brier分数（BS）评估不确定性估计。
- **对比方法**：Source（无适应）、BN、Tent、CoTTA、RoTTA、PETAL、SATA、DSS、SWA等9种方法，所有方法使用相同骨干网络和预训练模型。

## 4. 资源与算力

- 论文附录K明确说明：实验使用**单张RTX-4090 GPU**。
- 提供了时间与内存成本：VCoTTA占用11.1GB显存，每腐蚀类型处理时间279秒（CoTTA为272秒，PETAL为261秒）。
- 未说明总训练时长或预热阶段的具体耗时。

## 5. 实验数量与充分性

- **实验组数**：主要包括：
  - 三个标准数据集的主要结果（表1-3）。
  - 消融实验（表4）：验证变分预热和对称交叉熵的作用。
  - 先验混合权重分析（表5）：对比不同加权策略。
  - 不确定性估计（表6）：NLL和BS对比。
  - 逐渐腐蚀场景（表7）。
  - 自信度边缘参数分析（表8）、增强数量影响（表9）。
  - 预热策略对比（表10、附录F）：预热epoch数、数据比例、与直接训练BNN对比。
  - 不同腐蚀顺序的鲁棒性（表11）：10个随机顺序的均值和标准差。
  - 循环测试（图6）、严格在线学习（表12）、时间和内存成本（表13）。
- **充分性**：实验覆盖了标准CTTA评估的多个维度，消融和对比全面，结果呈现了均值和方差，比较客观、公平。但在更复杂的真实场景（如自动驾驶视频）中未验证。

## 6. 论文的主要结论与发现

- VCoTTA在所有三个数据集上均取得最佳平均错误率（CIFAR10C：13.1%；CIFAR100C：28.4%；ImageNetC：64.2%），显著优于现有SOTA方法（如SWA、CoTTA）。
- 变分预热和对称交叉熵两个组件均对性能提升有贡献。
- 自适应先验混合权重优于固定权重或仅使用单一先验。
- 在不确定性估计（NLL和BS）上，VCoTTA也优于对比方法，表明其能提供更可靠的预测置信度。
- 在逐渐腐蚀和循环腐蚀场景下，VCoTTA仍保持优势，体现其缓解误差累积的有效性。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：首次将变分贝叶斯推断系统性地引入CTTA，通过先验混合策略有效应对不可靠先验问题，这是对传统贝叶斯持续学习在无监督场景下的重要扩展。
- **实用性**：变分预热策略允许直接利用现成的预训练CNN模型快速转换为BNN，无需从头训练，降低了使用门槛。
- **实验全面**：不仅报告了标准错误率，还评估了不确定性校准、顺序鲁棒性、循环适应、严格在线学习等，分析深入。

## 8. 不足与局限

- **依赖源数据预热**：变分预热需要使用源数据，若预训练已完成且源数据不可获取，则该方法无法直接应用（论文Limitation已指出）。
- **计算成本较高**：BNN模型比CNN更复杂，高斯混合依赖多重数据增强，增加了计算和内存开销（表13显示显存略高）。
- **实验覆盖有限**：仅在图像分类的合成腐蚀数据集上验证，未在真实域偏移（如自动驾驶、医疗影像）上测试，泛化性需进一步验证。
- **假设依赖**：方法基于类别可分离假设（附录B.1），若类别严重重叠，熵最小化有效性可能下降。
- **超参数敏感**：需要调节自信度边缘ϵ、温度τ等，不同数据集最优值可能不同。

（完）
