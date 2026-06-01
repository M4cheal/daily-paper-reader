---
title: Hyperbolic Active Learning for Semantic Segmentation under Domain Shift
title_zh: 双曲主动学习用于域偏移下的语义分割
authors: "Luca Franco, Paolo Mandica, Konstantinos Kallidromitis, Devin Guillory, Yu-Teng Li, Trevor Darrell, Fabio Galasso"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=hKdJPMQvew"
tags: ["query:ris"]
score: 6.0
evidence: 针对域偏移下的语义分割主动学习，可迁移至指代分割的域适应
tldr: 本文提出双曲主动学习方法HALO，用于域偏移下的语义分割。通过双曲半径近似认知不确定性，结合预测熵作为数据获取策略，选择最不确定的像素进行标注。在合成到真实场景的域迁移基准上验证了有效性。该方法的核心思想可应用于指代图像分割的域偏移问题。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-hkdjpmqvew/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1758, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hkdjpmqvew/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1603, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hkdjpmqvew/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 688, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hkdjpmqvew/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1749, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hkdjpmqvew/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 837, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hkdjpmqvew/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 885, \"height\": 545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hkdjpmqvew/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1764, \"height\": 801, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hkdjpmqvew/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1766, \"height\": 1595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hkdjpmqvew/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1762, \"height\": 1974, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hkdjpmqvew/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1738, \"height\": 1046, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-hkdjpmqvew/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 1061, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hkdjpmqvew/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 621, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hkdjpmqvew/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 934, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hkdjpmqvew/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 941, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hkdjpmqvew/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1060, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hkdjpmqvew/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 702, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hkdjpmqvew/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1205, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hkdjpmqvew/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 671, \"height\": 186, \"label\": \"Table\"}]"
motivation: 域偏移下语义分割模型性能下降，主动学习需要高效识别最有益标注的样本。
method: 利用双曲神经网络，将双曲半径作为数据稀缺性的指示，结合熵近似认知不确定性，主动选取不确定区域进行标注。
result: 在GTAV→Cityscapes和SYNTHIA→Cityscapes上优于现有主动学习方法。
conclusion: 双曲主动学习能有效应对域偏移，为域适应分割提供高效数据选择策略。
---

## Abstract
We introduce a hyperbolic neural network approach to pixel-level active learning for semantic segmentation. Analysis of the data statistics leads to a novel interpretation of the hyperbolic radius as an indicator of data scarcity. In HALO (Hyperbolic Active Learning Optimization), for the first time, we propose the use of epistemic uncertainty as a data acquisition strategy, following the intuition of selecting data points that are the least known. The hyperbolic radius, complemented by the widely-adopted prediction entropy, effectively approximates epistemic uncertainty. We perform extensive experimental analysis based on two established synthetic-to-real benchmarks, i.e. GTAV $\rightarrow$ Cityscapes and SYNTHIA $\rightarrow$ Cityscapes. Additionally, we test HALO on Cityscape $\rightarrow$ ACDC for domain adaptation under adverse weather conditions, and we benchmark both convolutional and attention-based backbones. HALO sets a new state-of-the-art in active learning for semantic segmentation under domain shift and it is the first active learning approach that surpasses the performance of supervised domain adaptation while using only a small portion of labels (i.e., 1%).

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：语义分割需要昂贵的像素级标注，尤其在域偏移（例如从合成数据到真实场景）下，模型在目标域性能严重下降。主动学习（Active Learning）旨在通过只标注最“有价值”的像素来降低标注成本，但现有方法主要基于预测熵（预测不确定性），忽略了数据稀缺性等认知不确定性成分。
- **动机**：作者认为，在域适应任务中，模型对目标域数据的“不了解”本质上是认知不确定性（epistemic uncertainty），而不仅限于预测误差。因此，提议利用双曲几何（Hyperbolic Geometry）中的“半径”作为数据稀缺性的代理，并结合预测熵来更全面地近似认知不确定性，从而选择最需要标注的像素。
- **整体含义**：本文首次将双曲神经网络引入主动学习，提出HALO（Hyperbolic Active Learning Optimization）方法，在多个域偏移语义分割基准上取得新SOTA，并首次在仅使用少量标签（5%）的情况下超越全监督域适应性能。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- **双曲半径 → 数据稀缺性**：将像素嵌入到庞加莱球（Poincaré ball）中，发现不同类别的平均半径与该类别在数据集中的像素占比呈强负相关（ρ=-0.899）。即罕见类（如rider、motorcycle）嵌入半径较大，常见类（如road）半径较小。因此，半径可作为数据稀缺性的有效指标。
- **预测熵 → 预测误差**：预测熵（softmax概率的熵）与类别准确率呈强负相关（ρ=-0.913），用于指示预测的不确定性。
- **认知不确定性近似**：通过模型集成计算总不确定性和偶然不确定性，两者之差为认知不确定性。半径和熵的乘积与认知不确定性的相关系数高达ρ=0.824，表明两者互补。

### 关键技术细节
1. **双曲分割网络**：采用Atigh等人提出的双曲语义分割模型，使用双曲多项逻辑回归（HyperMLR）进行分类，但去除了手动定义的分层标签。像素特征经指数映射投影到庞加莱球。
2. **获取分数（Acquisition Score）**：每个像素的获取分数 A = R ⊙ H，其中R为双曲半径（式3），H为预测熵（式略）。该分数用于在每次主动学习轮次中选择高价值像素进行标注。
3. **双曲特征重加权（HFR）**：为解决双曲训练不稳定（靠近球边界时梯度消失），在特征投影前引入可学习的重加权模块。给定特征图Z，计算权重L = HFR(Z) ∈ R^{H̃×W̃}，然后重加权归一化特征：Z̃ = Z / |Z| ⊙ L。该模块端到端训练，防止嵌入过度靠近边界。
4. **主动学习流程**：先在大规模源数据集（如GTAV）上预训练模型，然后在目标数据集上进行多轮主动学习。每轮包括：使用当前模型预测，根据获取分数选择像素，人工标注，加入训练集，微调模型。预算通常为总像素的2.2%或5%，分5轮均匀分配。

## 3. 实验设计

### 数据集与场景
- **合成→真实**：GTAV（24,966张）→ Cityscapes（2,975训练+500验证）；SYNTHIA（9,000张）→ Cityscapes（19类/16类）。
- **真实→恶劣天气**：Cityscapes → ACDC（4,006张，含雾、夜、雨、雪）。

### 基准（Benchmark）
- 对比方法：LabOR, RIPU, AADA, MADA, D2ADA等。其中RIPU为当前SOTA。
- 骨干网络：DeepLab-v3+（ResNet-101）和SegFormer-B4（Transformer），部分实验用DeepLab-v2。
- 评估指标：平均交并比（mIoU），对GTAV→CS和CS→ACDC用19类，对SYNTHIA→CS分别报告13类和16类mIoU。

### 对比方法
- 所有对比方法均采用相同骨干和预训练设置，确保公平。HALO分别用2.2%和5%预算进行报告，并与全监督域适应（使用100%目标标签）比较。

## 4. 资源与算力

- **硬件**：4× Tesla V100 GPU（16GB显存）。
- **软件**：PyTorch + PyTorch Lightning，批量大小8（每GPU 2张）。
- **训练时间**：RIPU约12.5小时，HALO约13.5小时（增加8%）。
- **推理时间**（Cityscapes验证集）：RIPU约1分29秒，HALO约1分46秒。
- **参数量**：HALO与RIPU均约60.1M参数（因双曲空间可用更低嵌入维度64 vs 512，且HFR模块仅增加约10k参数）。
- **FLOPs**：分类层相比RIPU增加（125M→280M），但整体模型约1.7 TFLOPS。

论文未明确提及超参数调优成本或完整训练轮次次数。

## 5. 实验数量与充分性

- **主要实验**：三大基准（GTAV→CS, SYNTHIA→CS, CS→ACDC）各报告了2.2%和5%预算下的结果，并与多个SOTA方法对比。
- **消融实验**：
  - 获取准则消融：仅熵、仅半径、两者结合（HALO）——显示结合后mIoU从~63%提升至74.5%。
  - HFR消融：有无HFR，提升1.2% mIoU并稳定训练。
  - 区域vs像素式获取：性能相近（74.1% vs 74.5%）。
  - 源自由域适应测试：2.2%预算下比RIPU高3% mIoU。
- **Oracle实验**：用真实边界标签替代伪标签进行边界选择，结果反而下降1.4 mIoU，证明仅选边界并非最优。
- **相关性分析**：半径与数据稀缺性、熵与准确率的相关系数随时间变化趋势；半径与熵对认知不确定性的贡献。
- **预算递增实验**：从0.1%到10%预算，展示性能饱和并分析数据不平衡影响。
- **公平性**：与基线方法使用相同骨干、训练流程、预训练设置；代码将开源。

总体实验设计较为充分，覆盖了多种域适应场景和骨干，消融严谨，但缺少对更多任务（如目标检测）和更大规模真实域数据集（如BDD100K）的验证。

## 6. 主要结论与发现

- HALO在GTAV→Cityscapes（2.2%: +1.2%, 5%: +3.3% mIoU）、SYNTHIA→Cityscapes（+2.4%, +4.2%）、Cityscapes→ACDC（5%: +2.9%）上均超越所有现有ADA方法。
- 首次在主动学习中（仅5%标签）超越全监督域适应性能（GTAV→CS +2.6% mIoU）。
- 双曲半径与预测熵互补，共同近似认知不确定性，是有效的主动获取策略。
- 双曲特征重加权（HFR）提升了双曲训练的稳定性和最终性能。

## 7. 优点

- **创新性强**：首次将双曲几何引入主动学习，并赋予了双曲半径新的解释（数据稀缺性）。
- **实践有效**：在多个标准域适应基准上显著提升，且首次超越全监督适应。
- **设计合理**：将认知不确定性分解为数据稀缺性和预测误差，并用两种互补信号进行近似。
- **训练稳定**：提出的HFR模块解决了双曲网络训练不稳定的问题，且计算开销极小。
- **通用性好**：支持CNN和Transformer骨干，适用于不同天气条件下的域适应。

## 8. 不足与局限

- **缺乏理论证明**：双曲半径作为数据稀缺性指标的解释主要基于实验观察，缺乏严格的数学推导。
- **依赖源域预训练**：目前需要大型合成数据集进行预训练，若源域不可用或域差异极大，可能受限。论文未探讨无源域适应或自监督预训练替代方案。
- **标注成本仍高**：虽然只选少量像素，但像素级人工标注本身耗时，论文未讨论如何优化标注流程。
- **评估范围有限**：仅在语义分割任务上验证，未推广到其他密集预测任务（如目标检测、实例分割）。
- **数据不平衡风险**：当预算超过5%时，由于目标域数据固有不平衡，性能提升趋于饱和，可能限制了更高预算下的收益。
- **实验资源细节缺失**：未明确提及超参数搜索过程、种子设置、以及训练轮次数量的精确值，可能影响可复现性。

（完）
