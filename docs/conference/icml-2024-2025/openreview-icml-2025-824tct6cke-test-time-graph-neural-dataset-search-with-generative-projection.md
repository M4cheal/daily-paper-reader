---
title: Test-Time Graph Neural Dataset Search With Generative Projection
title_zh: 基于生成投影的测试时图神经网络数据集搜索
authors: "Xin Zheng, Wei Huang, Chuan Zhou, Ming Li, Shirui Pan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=824TCt6CkE"
tags: ["query:tta"]
score: 7.0
evidence: 通过生成投影实现图神经网络的测试时自适应
tldr: 图神经网络在测试时面临分布偏移，现有数据驱动方法泛化性不足。本文提出测试时图神经网络数据集搜索问题，并设计生成投影方法（PGNDS），通过生成过程将未见测试图分布映射回已知训练分布。包含三个关键模块，实验证明能显著提升GNN在偏移测试图上的推理性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-824tct6cke/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1766, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-824tct6cke/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-824tct6cke/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 558, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-824tct6cke/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 550, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-824tct6cke/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 550, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-824tct6cke/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 727, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-824tct6cke/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1791, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-824tct6cke/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 729, \"height\": 586, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-824tct6cke/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-824tct6cke/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1766, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-824tct6cke/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-824tct6cke/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 838, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-824tct6cke/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1772, \"height\": 540, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-824tct6cke/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1763, \"height\": 430, \"label\": \"Table\"}]"
motivation: 图神经网络在测试时遇到未见图结构分布偏移，缺乏灵活的适应方法。
method: 提出PGNDS框架，利用生成模型将测试图分布投影到训练分布，结合图结构生成和节点特征重构。
result: 在多个图分类和节点分类数据集上，适应后的GNN性能提升明显。
conclusion: 生成式投影是一种有效的图测试时自适应策略。
---

## Abstract
In this work, we address the test-time adaptation challenge in graph neural networks (GNNs), focusing on overcoming the limitations in flexibility and generalization inherent in existing data-centric approaches. To this end, we propose a novel research problem, test-time graph neural dataset search, which seeks to learn a parameterized test-time graph distribution to enhance the inference performance of unseen test graphs on well-trained GNNs. Specifically, we propose a generative Projection based test-time Graph Neural Dataset Search method, named PGNDS, which maps the unseen test graph distribution back to the known training distribution through a generation process guided by well-trained GNNs. The proposed PGNDS framework consists of three key modules: (1) dual conditional diffusion for GNN-guided generative projection through test-back-to-training distribution mapping; (2) dynamic search from the generative sampling space to select the most expressive test graphs; (3) ensemble inference to aggregate information from original and adapted test graphs. Extensive experiments on real-world graphs demonstrate the superior ability of our proposed PGNDS for improved test-time GNN inference.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：图神经网络（GNN）在训练阶段表现良好，但在测试阶段遇到未见图时，由于训练图与测试图之间存在分布偏移（distribution shifts），导致推理性能显著下降。传统的测试时自适应（TTA）方法分为两类：模型自适应（微调GNN参数）和数据自适应（修改测试图数据），但两者均存在不足：
  - 模型自适应：在实际部署中微调GNN参数不切实际，计算成本高、受在线应用限制。
  - 数据自适应（如GTRANS）：虽无需修改模型参数，但灵活性差、泛化能力弱，需要对每张测试图逐图参数化调整，且适应空间有限。
- **新视角**：论文提出一种数据驱动的解决方案——**不逐个修改测试图，而是学习一个参数化的测试图集分布**，利用生成过程将整个测试图集分布投影回训练分布，从而增强已训练GNN在测试图上的推理性能。
- **核心贡献**：引入新研究问题“测试时图神经网络数据集搜索”（Test-time Graph Neural Dataset Search），并提出生成投影方法 **PGNDS**，通过条件扩散模型、动态搜索、集成推理实现有效自适应。

## 2. 方法论：核心思想与关键技术

### 核心思想
PGNDS 通过学习测试图集的最优分布参数，将测试图生成式地“投影”回训练分布，使得生成的新测试图与训练分布对齐，同时保留原有图的关键特征，从而提升已冻结GNN模型的测试推理性能。

### 总体框架（两阶段）
- **S1：测试时图神经网络数据集搜索**，包含两个子步骤：
  - **S1-1：双条件扩散（Dual Conditional Diffusion）**  
    - 对测试图进行少量前向扰动（T步，T ≪ Ttr），添加高斯噪声到节点特征和边连接。
    - 使用已训练的扩散模型（DIFF）和已训练GNN（GNN θ*_tr）进行反向扩散，并引入**双条件指导**：
      - **任务特定信息**：来自GNN预测的伪标签，用于引导生成图保持标签一致性。
      - **图数据约束**：通过结构距离（MSE）和全局多样性距离（Fused Gromov-Wasserstein distance）约束，确保生成图结构不偏离原始图且多样化。
    - 反向扩散得分修正函数：`s_feat_te` 和 `s_struc_te`，分别对节点特征和结构进行修正。
  - **S1-2：动态搜索（Dynamic Search）**  
    - 在整个反向扩散步骤中，根据最小化三约束（任务、结构、多样性）的加权和，选择最优的适应测试图（每张测试图选取最佳时间步的生成图）。
    - 设置动态停止条件（若损失不下降则提前终止）。
- **S2：测试时集成推理（Ensemble Inference）**  
  - 对原始测试图与适应后的测试图进行集成：分类任务取平均置信度；回归任务融合图嵌入后输入预测头。

### 理论保证（Proposition 2.2 & 2.3）
- 证明了无指导的扩散过程无法保证分布对齐；引入双条件指导后，能将生成分布偏差控制在可控边界内（通过梯度约束），使最终分布接近训练分布与GNN模型分布的交集。

## 3. 实验设计

### 数据集与任务
- **图分类**：4个数据集（蛋白质图Enzymes，分子图Ogbg-BBBP、Ogbg-BACE、Ogbg-ClinTox），使用ROC-AUC（↑）评价。
- **图回归**：5个任务（QM9的4个子任务A/B/C/Alpha，Ogbg-FreeSolv），使用RMSE（↓）评价。
- **数据划分**：遵循前人工作（Liu et al., 2024; Jo et al., 2022）的预处理与划分方式，训练/测试比例见附录表A2。

### 基线方法
- **模型中心方法**：ERM（标准训练）、DropEdge、FeatMask、EERM（面向节点级OOD）、TENT（熵最小化微调）。
- **数据中心方法**：GTRANS（当前最优的测试时图变换方法）。
- **GNN骨干**：统一使用GIN（图同构网络）作为已训练模型。

### 对比结果
- **图分类**（表1）：PGNDS在所有数据集上取得最高ROC-AUC，如Ogbg-BACE从0.8338提升至0.8873。
- **图回归**（表2）：PGNDS在所有任务上取得最低RMSE，如QM9-A从2.2022降至2.1985；GTRANS在某些任务上甚至崩溃（QM9-alpha RMSE超1000+）。

### 消融实验（表3、图3-4）
- 将完整模型拆解为6个模块索引（Idx01-06），逐步加入双条件扩散、三种约束（r_gtask, r_struc, r_gdist）、动态搜索、集成推理。
- 结果表明，每增加一个组件性能均提升，全模型（Idx06）最优，说明各组件的协同作用。

### 超参数敏感性实验（图5、图A1）
- 针对α、β、γ三个超参数（分别控制任务、结构、多样性约束权重）进行网格搜索，表明中等值最佳，极端值导致轻微下降。

### 运行时间对比（表4）
- 在5 epoch内比较：PGNDS运行时间与EERM相当（2.244~2.635秒），GTRANS最快（~0.24秒），PGNDS在效率与性能间取得平衡。

### 可视化（附录图A2）
- 展示QM9中原图与PGNDS生成图的对比，表明关键化学特征（原子类型、连接性）被保留，但结构有所调整以对齐训练分布。

## 4. 资源与算力

- **文中明确提到**：运行时间实验使用单个NVIDIA A100 GPU（表4注释），但未给出具体训练/推理总时长、GPU数量、训练轮次数、模型大小等细节。消融实验和超参数分析使用了同一硬件，但未详述完整训练时间。因此，算力信息不充分，仅知使用单卡A100。

## 5. 实验数量与充分性

- **实验数量**：
  - 图分类：4个数据集 × 1次主实验 + 消融1个数据集 + 超参1个数据集 = 约6组结果（表1、图3、图5）。
  - 图回归：5个任务 × 1次主实验 + 消融1个数据集 = 约6组结果（表2、图4）。
  - 运行时间对比：3个分类数据集（表4）。
  - 可视化：2个生成图示例。
- **充分性评价**：
  - **优点**：覆盖了图分类与回归两种任务、分子与蛋白质两种图类型；消融实验系统性地验证了每个模块；超参数敏感性分析展示了鲁棒性；与多种基线（包括当前SOTA）对比充分。
  - **不足**：
    - 仅使用了6个数据集（4分类+2回归中的5任务），规模中等，未在高维/大规模图（如OGBN-Products, OGBG-MolPCBA）上验证。
    - 基线中缺少部分方法（如GT3、GraphTTA、HomoTTT），作者解释为代码不可用或场景不同，但可能削弱对比全面性。
    - 未进行统计显著性检验（如多次运行的标准差），结果仅呈现单次/均值？文中未明确报告重复次数。
    - 仅使用GIN作为GNN骨干，未在不同架构（如GCN、GAT、GraphSAGE）上验证泛化性。
- **总体**：实验设计合理、结果清晰，但可进一步扩展数据集、架构和统计评估以增强公平性。

## 6. 主要结论与发现

- **PGNDS显著提升GNN在测试时分布偏移条件下的推理性能**，在图分类与回归任务上均优于所有基线，包括当前SOTA的GTRANS。
- **双条件扩散是生成有效适应图的关键**：任务伪标签、结构一致性、全局多样性三者缺一不可，且动态搜索能自动选择最优生成步骤。
- **集成推理进一步提升鲁棒性**：融合原始图与适应图信息，弥补生成空间的不确定性。
- **理论分析**证明了所提方法能有效约束分布偏差。

## 7. 优点

- **问题新颖**：提出“测试时图神经网络数据集搜索”这一新范式，从数据分布角度解决测试时自适应，而非逐图微调。
- **方法创新**：
  - 首次将扩散模型用于测试时图分布投影，并引入GNN作为条件指导。
  - 动态搜索机制在反向扩散中自动选择最佳生成图，避免全空间枚举。
  - 集成推理设计方案合理，对分类和回归分别处理。
- **实验充分**：消融实验、超参数分析、运行时间、可视化等多角度验证。
- **理论支撑**：提供了数学证明，说明约束能控制分布偏移。

## 8. 不足与局限

- **实验覆盖有限**：
  - 仅测试了分子和蛋白质图，未涵盖社交网络、交通网络等常见图类型。
  - 仅使用单一GNN架构（GIN），未验证在不同GNN（如GCN、GAT）上的表现。
  - 未提供多次实验的标准差或置信区间，无法评估统计稳定性。
  - 基线选择虽合理，但缺少与更多同类方法（如GraphTTA、HomoTTT）的直接对比（作者解释为代码不可用）。
- **计算开销**：虽然运行时间与EERM相近，但扩散模型生成过程（尤其动态搜索需遍历多步）仍可能比简单数据增强方法耗时。
- **对超参数的敏感性**：虽然中等值最优，但实际应用中需要调参，可能降低易用性。且仅在一个数据集上分析超参，泛化性待验证。
- **理论分析较弱**：Proposition 2.2和2.3属于存在性/上界证明，未给出具体收敛速率或最优性保证，且仅以节点特征为例，结构部分陈述类似但未严格证明。
- **未讨论失败场景**：当测试分布与训练分布差异极大时，投影可能失败或生成无意义图，文中未分析边界情况。
- **应用限制**：依赖预训练好的扩散模型（需要额外训练阶段），不适用于完全无源的测试场景（如仅提供测试图而无法使用任何训练数据或预训练生成模型）。文中假设GNN和扩散模型均已在训练集上预训练好，并保持冻结。

（完）
