---
title: Test-time Correlation Alignment
title_zh: 测试时相关对齐
authors: "Linjing You, Jiabao Lu, Xiayuan Huang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=0dualJz9OI"
tags: ["query:tta"]
score: 9.0
evidence: 提出测试时相关对齐（TCA）以应对分布偏移
tldr: 针对测试时自适应中实例级对齐忽略特征相关性的问题，本文提出测试时相关对齐（TCA），通过高置信度实例间的相关性对齐来实现自适应，无需复杂反向传播，减轻了计算开销和遗忘问题。理论分析验证了可行性，实验表明TCA有效应对分布偏移。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-0dualjz9oi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 735, \"height\": 710, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0dualjz9oi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 691, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0dualjz9oi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 689, \"height\": 646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0dualjz9oi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 691, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0dualjz9oi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1763, \"height\": 1064, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0dualjz9oi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1755, \"height\": 1059, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 916, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 958, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 861, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 867, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 862, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1533, \"height\": 614, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1528, \"height\": 615, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1523, \"height\": 612, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1527, \"height\": 615, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1528, \"height\": 615, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1524, \"height\": 612, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1759, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1763, \"height\": 613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1750, \"height\": 615, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1780, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1779, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1779, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1780, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1778, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1779, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1780, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1779, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0dualjz9oi/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1779, \"height\": 466, \"label\": \"Table\"}]"
motivation: 现有测试时自适应方法主要关注实例级对齐，忽略特征相关性，且存在计算开销和遗忘问题。
method: 提出TCA，在高置信度实例间进行相关对齐，无需反向传播更新模型。
result: 理论分析和实验表明TCA有效应对分布偏移，优于现有方法。
conclusion: TCA为测试时自适应提供了轻量级且有效的特征对齐方案。
---

## Abstract
Deep neural networks often degrade under distribution shifts. Although domain adaptation offers a solution, privacy constraints often prevent access to source data, making Test-Time Adaptation (TTA)—which adapts using only unlabeled test data—increasingly attractive. However, current TTA methods still face practical challenges: (1) a primary focus on instance-wise alignment, overlooking CORrelation ALignment (CORAL) due to missing source correlations; (2) complex backpropagation operations for model updating, resulting in overhead computation and (3) domain forgetting. To address these challenges, we provide a theoretical analysis to investigate the feasibility of **T**est-time **C**orrelation **A**lignment (**TCA**), demonstrating that correlation alignment between high-certainty instances and test instances can enhance test performances with a theoretical guarantee. Based on this, we propose two simple yet effective algorithms: LinearTCA and LinearTCA+. LinearTCA applies a simple linear transformation to achieve both instance and correlation alignment without additional model updates, while LinearTCA+ serves as a plug-and-play module that can easily boost existing TTA methods. Extensive experiments validate our theoretical insights and show that TCA methods significantly outperforms baselines across various tasks, benchmarks and backbones. Notably, LinearTCA achieves higher accuracy with only 4\% GPU memory and 0.6\% computation time compared to the best TTA baseline. It also outperforms existing methods on CLIP over 1.86\%. Code: https://github.com/youlj109/TCA

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- 深度神经网络在分布偏移下性能严重下降。域适应（Domain Adaptation）是一种解决方案，但隐私约束常使得源数据不可访问，因此测试时自适应（Test-Time Adaptation, TTA）——仅使用无标签测试数据进行自适应——变得更具吸引力。
- 现有TTA方法面临三个主要挑战：
    - **忽略特征相关性**：大多数方法仅关注实例级对齐（instance-wise alignment），忽略了特征间的二阶统计相关性（如CORAL所强调的）。实验表明，随着域偏移增大，特征相关性的变化也增大。
    - **计算开销大**：现有TTA方法依赖反向传播更新模型，在资源受限的边缘设备上难以部署。
    - **域遗忘**：更新模型参数会导致模型逐渐丧失对源域知识的保持，回源域时性能下降。
- 作者提出将CORAL思想引入TTA，但由于无法访问源数据，需要构造“伪源相关”（pseudo-source correlation）。因此核心问题：能否用高置信度测试实例的相关性近似源相关性？这种对齐能否有效提升TTA性能？

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：测试时相关对齐（Test-time Correlation Alignment, TCA）。通过理论分析证明：高置信度测试实例的特征相关性可近似源域相关性，且对齐该伪源相关与测试相关可降低测试错误率。
- **关键技术**：
    - **伪源构建**：对每个测试实例，计算预测不确定性 ω = ∥ŷ - p∥²_F，其中ŷ是one-hot编码。维护一个伪源库M，存储k个不确定性最低的实例及其嵌入。更新规则：若|M|≤k则直接加入，否则替换M中不确定性最高者。
    - **LinearTCA**：在线性变换下最小化测试相关性与伪源相关性的Frobenius范数距离。通过特征值分解得到变换矩阵W的闭式解：W = U_t Λ_t^{1/2} Û_s^T Â_s^{-1/2}。然后对测试嵌入进行变换：Z'_t = (Z_t - μ_t)W + ˆμ_s，最后用解码器g得到预测。
    - **LinearTCA+**：作为即插即用模块，可提升现有TTA方法。在其他TTA方法更新模型后，对其输出的嵌入和预测再次应用LinearTCA。
- **理论贡献**：定理3.5给出伪源相关与真实源相关距离的上界，定理3.6建立测试误差与均值、相关距离的关系，推论3.7表明对齐伪源相关可降低测试误差。

### 3. 实验设计：数据集、基准、对比方法
- **数据集与场景**：
    - 域泛化任务：PACS、OfficeHome、DomainNet。
    - 图像损坏任务：CIFAR-10-C、CIFAR-100-C、ImageNet-C（含多种损坏类型和等级）。
    - 多模态任务：基于CLIP在PACS、OfficeHome、VLCS上评估。
- **对比方法**：
    - 无反向传播方法：BN、T3A、AdaNPC。
    - 基于反向传播方法：TENT、PLC、EATA、SAR、TSD、TIPI、TEA。
- **骨干网络**：ResNet-18/50、ViT-B/16、CLIP-ViT-B/16。
- **实验充分性**：共进行了大量实验，包括：
    - 主要结果（Table 1）：涵盖3个域泛化数据集×3骨干 + 3个图像损坏数据集×3骨干，共18组对比。
    - 效率对比（Table 2）：GPU内存、运行时间。
    - 遗忘抵抗性（Table 4）：回源域准确率。
    - CLIP上的对比（Table 5）。
    - 消融实验：伪源实例数量k、测试采样数量k2的影响（Figure 4c,d）。
    - 线性/非线性变换对比（Table 6）。
    - 上界分析（Table 7）：使用真实源域进行相关对齐。
    - 批大小影响（Table 8）。
    - 此外还有大量附录表格（共26个详细表格）覆盖所有损坏类型和域。
- **公平性**：作者声明超参数在不同数据集上独立调优（使用默认域验证），且对每种方法统一搜索学习率、熵过滤阈值等。对比方法均使用官方或广泛认可的设置。

### 4. 资源与算力
- 论文未明确说明训练时长、GPU型号数量。仅在效率对比中给出了CIFAR-10-C上的峰值GPU内存和运行时间（表2）。例如，LinearTCA在ResNet-18上仅增加0.06秒，内存增加0 MB；而TEA需增大约15倍内存、332秒运行时间。
- 未提及训练阶段算力开销（因为TTA方法不重新训练模型，只进行推理和少量适应）。

### 5. 实验数量与充分性
- 实验数量非常充分：覆盖3种任务（域泛化、图像损坏、多模态）、3种骨干、10+对比方法、多个数据集、消融研究、效率/遗忘/非线性扩展/上界/批大小等多种分析。
- 实验设计客观公平：统一基准、明确超参数搜索范围、报告多次运行结果（如CLIP实验显示标准差）。
- 不足：在图像损坏任务上，LinearTCA本身弱于一些基于反向传播的方法，但LinearTCA+能显著提升。作者对此进行了分析（有效范围、线性假设限制）。

### 6. 论文的主要结论与发现
- **理论可行**：高置信度测试实例的相关性可近似源相关性，且对其对齐能降低测试错误率（定理3.5-3.6，推论3.7）。
- **线性TCA有效**：LinearTCA在域泛化任务上普遍超越源模型，部分超越所有基线；在资源受限场景下效率极高（内存几乎无增加，时间增加<0.1秒）。
- **即插即用提升**：LinearTCA+可稳定提升现有TTA方法，尤其在ViT-B/16上在CIFAR-10-C提升4.95%，在CLIP上超越1.86%。
- **遗忘抵抗**：TCA方法返回源域时性能下降最小，甚至PACS上出现正向迁移（准确率提升0.08%）。
- **局限性**：线性变换在处理非线性分布偏移时不足；当伪源与真实源差异较大时（如ResNet-18特征提取能力弱），性能受限。

### 7. 优点
- **理论驱动**：为TTA中的特征对齐提供严格的理论保证，不仅仅是经验启发。
- **极简高效**：LinearTCA无需反向传播，近乎零额外内存和时间开销，适合边缘部署。
- **即插即用**：LinearTCA+可无缝增强现有TTA方法，通用性强。
- **遗忘抵抗**：通过避免更新模型参数，有效保持源域知识。
- **实验全面**：涵盖多种任务、骨干、数据集，并深入分析有效范围、批大小、非线性扩展等。

### 8. 不足与局限
- **线性假设局限**：仅用线性变换对齐相关性，对于复杂非线性分布偏移效果有限（如CIFAR-10-C上LinearTCA弱于BP-based方法）。作者通过引入MLP初步验证了非线性扩展能进一步提升。
- **伪源构建依赖高置信度**：若严重损坏图像导致所有实例置信度都低，则伪源与真实源差距可能大（在ImageNet-C等极端损坏场景下可能受限）。
- **未提及训练阶段资源**：实验基于预训练模型，未评估TTA方法本身在训练时的算力需求（通常可忽略）。
- **超参数k需调优**：虽然整体鲁棒，但最优k值在不同数据集上有差异，需验证域选择调优。
- **应用限制**：仅适用于分类任务，未扩展到其他任务（如分割、检测）。

（完）
