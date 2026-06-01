---
title: Adapter Naturally Serves as Decoupler for Cross-Domain Few-Shot Semantic Segmentation
title_zh: 适配器自然成为跨域小样本语义分割的解耦器
authors: "Jintao Tong, Ran Ma, Yixiong Zou, Guangyao Chen, Yuhua Li, Ruixuan Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Pokj70ZAxJ"
tags: ["query:ris"]
score: 6.0
evidence: 跨域小样本语义分割中的适配器解耦域信息
tldr: 跨域小样本语义分割面临域间隙和少量标注数据两大挑战。本文发现适配器不仅能辅助下游任务微调，还能自然作为域信息解耦器，通过分析模型内部结构揭示了这一机制。在多个跨域分割数据集上验证了适配器方法的有效性，为域适应分割提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 833, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 806, \"height\": 217, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1777, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 844, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 635, \"height\": 277, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 860, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 835, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 772, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 775, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 865, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 902, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 443, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 618, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 779, \"height\": 241, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 834, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 848, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1770, \"height\": 737, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 431, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 394, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 859, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 842, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 856, \"height\": 100, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 851, \"height\": 100, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 400, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 859, \"height\": 129, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 861, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 861, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 857, \"height\": 177, \"label\": \"Table\"}]"
motivation: 跨域小样本分割中域间隙和数据稀缺导致微调困难。
method: 利用适配器天然具备的域信息解耦能力进行微调。
result: 在多个跨域分割基准上取得了优异性能。
conclusion: 适配器可同时解决域适应和小样本微调问题。
---

## Abstract
Cross-domain few-shot segmentation (CD-FSS) is proposed to first pre-train the model on a source-domain dataset with sufficient samples, and then transfer the model to target-domain datasets where only a few training samples are available for efficient finetuning. There are majorly two challenges in this task: (1) the domain gap and (2) finetuning with scarce data. To solve these challenges, we revisit the adapter-based methods, and discover an intriguing insight not explored in previous works: the adapter not only helps the fine-tuning of downstream tasks but also naturally serves as a domain information decoupler. Then, we delve into this finding for an interpretation, and we find the model's inherent structure could lead to a natural decoupling of domain information. Building upon this insight, we propose the Domain Feature Navigator (DFN), which is a structure-based decoupler instead of loss-based ones like current works, to capture domain-specific information, thereby directing the model's attention towards domain-agnostic knowledge. Moreover, to prevent the potential excessive overfitting of DFN during the source-domain training, we further design the SAM-SVN method to constrain DFN from learning sample-specific knowledge. On target domains, we freeze the model and fine-tune the DFN to learn knowledge specific to target domains. Extensive experiments demonstrate that our method surpasses the state-of-the-art method in CD-FSS significantly by 2.69% and 4.68% average MIoU in 1-shot and 5-shot scenarios, respectively.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题定义**：跨域小样本语义分割（CD-FSS）旨在利用源域（如PASCAL）大量标注数据预训练模型，然后迁移至仅有少量标注样本的目标域（如医学影像、卫星图像等）进行高效微调。
- **两大挑战**：
  1. **域间隙**：源域与目标域数据分布差异巨大（如自然图像 vs. 皮肤镜图像）。
  2. **数据稀缺**：目标域仅提供极少量（1-shot或5-shot）带标注样本，易导致过拟合。
- **现有方法局限**：现有的解耦方法多为基于损失函数的（如对抗损失、正则化项），而本文发现**适配器（adapter）** 本身无需额外损失即可自然解耦域信息，同时解决域间隙和小样本微调问题。

## 2. 方法论

### 2.1 核心思想
- **发现**：插入在预训练、冻结的骨干网络深层、并带有残差连接的适配器，能够自动吸收域特定信息，而让骨干网络和编码器-解码器专注于域不变（domain-agnostic）知识。这种现象不依赖任何域解耦损失，仅由结构和位置决定。
- **理论解释**：基于信息瓶颈（IB）理论，适配器容量远小于主干网络，倾向于吸收更具信息量的域特定信号，残差结构使梯度流自然分离，主干网络优化域不变特征，适配器优化域特定特征。

### 2.2 关键技术细节
- **Domain Feature Navigator (DFN)**：
  - 结构：1×1卷积层，插入在冻结的骨干网络深层（如ResNet50的stage-4输出），通过残差连接与主特征相加。
  - 在多层级特征（低、中、高层）上分别应用DFN，确保语义一致性。
  - 源域训练时，DFN吸收域特定信息，引导整体模型学习域不变表示。目标域微调时，仅微调DFN（冻结其余模型）以适配目标域特征。

- **SAM-SVN（Sharpness-Aware Minimization on Singular Value Matrix）**：
  - 动机：纯结构解耦的DFN可能过度过拟合源域样本（而非域本身），表现为损失景观尖锐，阻碍后续微调。
  - 方法：对DFN权重进行奇异值分解（SVD），仅在奇异值矩阵上应用Sharpness-Aware Minimization（SAM），而保持其他参数不变。这样既限制了过度过拟合，又保留了DFN吸收域信息的能力。
  - 实现：在源域训练时，计算梯度后先对奇异值矩阵施加扰动（ρ=0.5），再更新参数；目标域微调时不使用SAM。

### 2.3 算法流程（文字说明）
1. 源域训练：使用PASCAL数据，冻结ResNet50骨干，插入DFN，联合训练DFN与编码器-解码器。每步训练使用SAM-SVN对DFN的奇异值矩阵进行锐度感知更新。
2. 目标域微调：冻结骨干和编码器-解码器，仅微调DFN（不使用SAM），学习目标域特定特征。与源域训练得到的域不变特征融合，对齐特征空间。
3. 推理：使用微调后的DFN处理查询图像和支持图像，构建4D超相关张量，经金字塔编码器和解码器得到分割结果。

## 3. 实验设计

### 3.1 数据集与Benchmark
- **源域**：PASCAL-5ⁱ（PASCAL VOC 2012扩展版）。
- **目标域（4个）**：
  - FSS-1000（自然图像，1000类，每类10张）
  - Deepglobe（卫星图像，7类，803张）
  - ISIC2018（皮肤病图像）
  - Chest X-ray（胸部X光，566张）
- **基准**：采用PATNet提出的CD-FSS标准设置，图像尺寸400×400。

### 3.2 对比方法
包括CaNet、PANet、RPMMs、PFENet、RePRI、HSNet、PATNet、RestNet、PerSAM、ABCDFSS、APSeg、APM等。涵盖传统FSS方法、跨域专用方法、基于SAM的方法等。

### 3.3 主要实验结果
- 在1-shot和5-shot设置下，平均MIoU超越当时最优方法APSeg分别**2.69%**和**4.68%**（基于ResNet50）；基于ViT-Base骨干时也显著领先。
- 在四个目标域上均取得一致提升，尤其在Chest X-ray上提升最大（1-shot达85.21%）。
- 与IFA（batch size=96）公平对比仍取得更优结果。

## 4. 资源与算力
- **GPU**：单张NVIDIA GeForce RTX 4090。
- **训练时长**：论文未明确给出具体训练时长，仅提及使用单卡训练和测试。
- **计算开销**：提出的方法参数量增加约21%，FLOPs增加仅0.02%（从20.11G到20.51G），属于参数高效方法。

## 5. 实验数量与充分性
- **消融实验**（约5组）：
  - 验证DFN、SAM、SVD各组件贡献（表7）。
  - 对比SAM施加于不同模块（全模型、仅DFN、仅SVN）。
  - 分析DFN使用方式（移除、重新初始化、固定参数等）。
  - 分析适配器不同位置（浅层/深层/间于编码解码器）和结构（传统/LoRA、残差/串行）对解耦能力的影响。
  - 超参数实验（学习率、SAM的ρ）。
- **可视化分析**：
  - 特征图可视化（图4、9、11、12）。
  - CKA/MMD域相似性度量（表1-4、图8、15）。
  - 损失景观锐度测量（表5、10、11）。
  - 风格迁移鲁棒性测试（图10）。
- **统计结果**：多次运行取最优点，给出性能波动（表8）。
- **总体评价**：实验设计较为充分，涵盖消融、可视化、鲁棒性、与多种SOTA对比，结论可信。但未报告多次运行的平均值和方差（仅报告最优和最差波动），统计严谨性略有欠缺。

## 6. 主要结论与发现
1. **适配器天然解耦域信息**：当适配器插入冻结骨干网络深层、并带残差连接时，自动吸收域特定信息，引导模型学习域不变知识，无需额外解耦损失。
2. **结构决定解耦能力**：解耦能力主要取决于残差连接和插入位置（深层），而非适配器内部设计（如LoRA vs. 1×1卷积）。
3. **SAM-SVN有效防止过度过拟合**：仅约束奇异值矩阵，保留域信息吸收能力，同时降低损失景观锐度，提升微调鲁棒性。
4. **方法显著提升CD-FSS性能**：在四个跨域场景下均超越当前最优，且计算开销极小。

## 7. 优点
- **新颖性**：首次发现并系统证明适配器天然解耦域信息的现象，与现有基于损失的方法不同。
- **简洁高效**：仅需在骨干网络深层添加1×1卷积，参数增加少，FLOPs几乎不变。
- **理论分析**：从信息瓶颈和梯度解耦角度给出数学推导，增强可解释性。
- **实验充分**：涵盖多种目标域、多种骨干（ResNet-50和ViT-Base）、多种对比方法，且进行了丰富的消融和可视化分析。
- **鲁棒性**：SAM-SVN设计有效平衡了域信息吸收与过拟合抑制，提升了微调稳定性。

## 8. 不足与局限
- **实验统计严谨性不足**：未报告多次运行的平均值和标准偏差，仅用“best−worst”表示波动，可能受随机种子影响。
- **未考虑多shot场景的充分分析**：仅测试了1-shot和5-shot，未探索更多shot数量下的性能趋势。
- **理论假设有待验证**：IB分析和正交投影假设在实证中未直接验证，仅通过间接实验推断。
- **应用限制**：方法依赖预训练冻结骨干，若骨干网络未经充分预训练（如从零开始训练），性能可能下降。另外，目标域微调时需单独设置学习率，不同域差异较大（从1e-3到5e-1），可能需调参。
- **未与最新方法对比**：论文发表于ICML 2025，但对比方法截至2024年，最新2025年方法（可能同期出现）未纳入比较。

（完）
