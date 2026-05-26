---
title: "TabLog: Test-Time Adaptation for Tabular Data Using Logic Rules"
title_zh: TabLog：基于逻辑规则的表格数据测试时间自适应
authors: "Weijieying Ren, Xiaoting Li, Huiyuan Chen, Vineeth Rakesh, Zhuoyi Wang, Mahashweta Das, Vasant G Honavar"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=LZeixIvQcB"
tags: ["query:tta"]
score: 8.0
evidence: 基于逻辑规则且保持逻辑结构不变的表格数据测试时间自适应
tldr: 针对表格数据测试时间自适应中异构特征和复杂依赖的挑战，本文提出TabLog方法。它假设源域和目标域之间的逻辑规则结构保持不变，仅调整数值参数和规则权重，从而在无需源数据的情况下适应目标域。在多个表格数据集上相比现有TTA方法取得更优性能。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-lzeixivqcb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1528, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lzeixivqcb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 534, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lzeixivqcb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 532, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lzeixivqcb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 537, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lzeixivqcb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 399, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lzeixivqcb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 398, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lzeixivqcb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 817, \"height\": 255, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-lzeixivqcb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1608, \"height\": 651, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-lzeixivqcb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1716, \"height\": 688, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-lzeixivqcb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1771, \"height\": 273, \"label\": \"Table\"}]"
motivation: 现有TTA方法难以处理表格数据的异构特征和复杂依赖关系。
method: 假设逻辑规则结构跨域不变，仅自适应调整数值参数与规则权重。
result: 在多个表格数据集上优于现有测试时间自适应方法。
conclusion: 利用逻辑结构不变性可有效实现表格数据的测试时间自适应。
---

## Abstract
We consider the problem of test-time adaptation of predictive models trained on tabular data. Effective solution of this problem requires adaptation of predictive models trained on the source domain to a target domain, using only unlabeled target domain data, without access to source domain data. Existing test-time adaptation methods for tabular data have difficulty coping with the heterogeneous features and their complex dependencies inherent in tabular data. To overcome these limitations, we consider test-time adaptation in the setting wherein the logical structure of the rules is assumed to remain invariant despite distribution shift between source and target domains whereas the numerical parameters associated with the rules and the weights assigned to them can vary to accommodate distribution shift. TabLog discretizes numerical features, models dependencies between heterogeneous features, introduces a novel contrastive loss for coping with distribution shift, and presents an end-to-end framework for efficient training and test-time adaptation by taking advantage of a logical neural network representation of a rule ensemble. We present results of experiments using several benchmark data sets that demonstrate TabLog is competitive with or improves upon the state-of-the-art methods for test-time adaptation of predictive models trained on tabular data. Our code is available at https://github.com/WeijieyingRen/TabLog.

---

## 论文详细总结（自动生成）

# TabLog：基于逻辑规则的表格数据测试时间自适应 —— 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题定义**：表格数据在部署时常面临分布偏移（covariate shift），导致源域训练的模型在目标域精度骤降。现有测试时间自适应（TTA）方法大多面向图像/文本数据，难以处理表格数据中**异构特征**（数值、布尔、类别）及其**复杂未知的依赖关系**。
- **核心挑战**：如何在**不访问源域数据**、仅利用无标签目标域数据的情况下，有效调整预测模型以适应分布偏移。
- **研究动机**：现有TTA方法（如特征对齐、特征迁移）因表格数据的特殊性而失效；而基于规则的方法具有可解释性和结构可迁移性，可能更适合表格数据的TTA。
- **核心假设**：源域与目标域之间，**规则集的逻辑结构（原子、连接词）保持不变**，仅需调整**数值参数（阈值）和规则权重**。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：学习一个由逻辑规则组成的集成分类器，规则结构在源域固定后迁移到目标域，仅在目标域上微调离散化阈值和规则权重。
- **关键技术细节**：
  - **特征编码为原子**：
    - 数值特征：通过学习可微的阈值 \( b_t^k \)，将数值转换为两个指示函数（≥ 和 ≤），使用 sigmoid 软近似实现端到端优化。
    - 类别/布尔特征：直接 one-hot 编码得到原子。
  - **逻辑连接学习**：
    - 采用逻辑神经网络（Logical Neural Network）实现可微的合取（∧）和析取（∨）算子。
    - 每个规则由多个原子通过可学习的参数（α, β）组合而成，实现“哪些原子参与规则”的自动选择。
  - **规则集成与预测**：
    - 逻辑神经网络的最后一层输出 K 个规则得分，通过可学习的投票权重 \( v_c \in \mathbb{R}^K \) 得到每个类别的概率（softmax）。
  - **测试时间自适应**：
    - **不变部分**：逻辑连接结构（Conj/Disj 的连线模式）以及大部分网络参数固定。
    - **可调部分**：数值特征的离散化阈值 \( b_t^k \) 和规则投票权重 \( v_c \)。
    - **损失函数**：熵损失 + 自监督对比损失（式(2)）。
  - **新型对比损失（LS）**：
    - 基于binning：将数值特征按分位数等分为若干bin。
    - **正样本**：对同一样本，将部分特征值替换为同bin内随机值。
    - **负样本**：替换为不同bin内的随机值。
    - 优化 InfoNCE 损失，使原始样本与正样本的特征表示相近，与负样本相远。
- **训练和适应流程**（图1）：
  - 源域训练：联合优化交叉熵损失 + 对比损失（λ = 0.1）。
  - 目标域适应：固定规则结构，仅优化阈值和投票权重，目标为熵损失 + 对比损失。

## 3. 实验设计
- **数据集**：
  - **真实分布偏移**：4个TableShift基准数据集（ASSISTments、Sepsis、Hospital Readmission、PhysioNet）。
  - **模拟分布偏移**：4个数据集（Airbnb、Channel、Jigsaw、Wine），分别施加高斯噪声、均匀噪声、随机特征替换三种偏移。
- **对比方法**：
  - **监督基线**：Logistic Regression、XGBoost、Catboost。
  - **源域无自适应**：VIME、TransTab、Scarf（自监督预训练，无目标域调整）。
  - **目标域感知TTA**：TENT、EATA、SHOT、TAST，分别基于MLP和FT-Transformer两种骨干。
- **评估指标**：Accuracy、Macro-F1，报告5次随机种子下的均值和标准差。

## 4. 资源与算力
- 论文明确提到实验在 **Linux服务器 + A100 GPU** 上进行。
- **未提供** GPU 数量、训练时长、模型参数量等具体算力信息。
- 可以推断：由于表格数据规模不大（最大约几万样本），且逻辑神经网络结构较简单，算力需求属于中等水平。

## 5. 实验数量与充分性
- **主实验**：表1（4个自然偏移数据集）和表2（4个模拟偏移数据集），共8个数据集，对比10+种方法，充分覆盖常见SOTA。
- **消融/分析实验**：
  - 规则数量对性能的影响（图2，输出节点数 1~128）。
  - 分箱数对性能的影响（图3，0~100）。
  - 超参数 λ 的影响（图4，0.01~100）。
  - 规则与阈值自适应可视化（表3、图5-6）。
- **公平性**：所有基线采用公开实现和推荐参数，报告多次随机种子，结果客观。但未进行统计显著性检验（如t-test）。
- **充分性判断**：实验设计合理，覆盖多种偏移场景和对比方法，超参数分析较全面，但缺少对标签偏移、新特征涌现等更复杂场景的评估。

## 6. 论文的主要结论与发现
- TabLog 在**所有8个数据集**上的 Accuracy 和 Macro-F1 均一致优于或持平所有对比方法（包括最强基线TAST）。
- 验证了核心假设：**规则逻辑结构不变，仅调整数值参数和权重** 可有效适应表格数据的分布偏移。
- 自监督**对比损失**（基于特征分箱扰动）对TTA性能有显著提升。
- 骨干网络选择重要：FT-Transformer 通常优于 MLP，TabLog 的逻辑神经网络设计兼具可解释性和适应能力。

## 7. 优点
- **创新性假设**：首次将逻辑规则结构不变性用于表格数据TTA，具有理论依据（规则代表模式，分布偏移不应改变模式形态，只改变尺度/阈值）。
- **端到端可微**：通过sigmoid近似离散化、逻辑神经网络的软连接，使得规则学习与阈值调整可同步优化。
- **针对性对比损失**：基于分箱的特征扰动策略利用了表格数据特性，比通用的数据增强更有效。
- **可解释性**：能够提取具体规则（表3），便于理解模型适应过程。
- **实验全面**：覆盖自然偏移和模拟偏移，对比多种现代TTA方法，且进行了广泛的参数分析。

## 8. 不足与局限
- **假设的局限性**：规则逻辑结构不变假设在强分布偏移（如特征空间变化、标签偏移）下可能不成立，论文未测试此类场景。
- **实验覆盖有限**：8个数据集均为中小规模（可能小于10万样本），未在更大规模的表格数据（如医疗、金融）上验证。
- **对比方法范围**：缺少与最新表格专用TTA方法（如TabPFN、AutoGluon等）的直接对比；某些基线（如SHOT）在表格上表现较差，可能因方法设计针对图像。
- **算力资源未详述**：难以复现和评估实际开销。
- **性能提升幅度**：在某些数据集（如Wine）上提升有限，且整体Accuracy仍然较低（如Airbnb仅~66%），说明领域适应仍具挑战。
- **未讨论多分类/不平衡类别**：实验数据集多为二分类或类别较平衡，对类别严重不平衡的情况缺乏分析。

（完）
