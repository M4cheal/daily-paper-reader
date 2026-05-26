---
title: Learning Topology-Aware Representations via Test-Time Adaptation for Anomaly Segmentation
title_zh: 通过测试时自适应学习拓扑感知表示用于异常分割
authors: "Ali Zia, Usman Ali, Kang Han, Abdul Rehman, Muhammad Umer Ramzan, shahnawaz qureshi, Wei Xiang"
date: 2025-05-10
pdf: "https://openreview.net/pdf?id=nwqaILb1vf"
tags: ["query:tta"]
score: 7.0
evidence: 使用拓扑伪标签进行异常分割的测试时自适应
tldr: 测试时自适应在异常分割中具有潜力但结构一致性不足。本文提出TopoTTA，将持久同调引入测试时自适应流程，通过多级立方复形滤波生成拓扑伪标签，指导轻量级分类器，无需重新训练骨干网络即可提升分割质量。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nwqailb1vf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1144, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nwqailb1vf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nwqailb1vf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1366, \"height\": 282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nwqailb1vf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nwqailb1vf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nwqailb1vf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 926, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nwqailb1vf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1420, \"height\": 976, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nwqailb1vf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1450, \"height\": 770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nwqailb1vf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1449, \"height\": 979, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nwqailb1vf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1456, \"height\": 476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nwqailb1vf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 700, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nwqailb1vf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1458, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nwqailb1vf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nwqailb1vf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 697, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nwqailb1vf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1456, \"height\": 474, \"label\": \"Table\"}]"
motivation: 利用测试时自适应增强异常分割中的结构一致性。
method: 结合持久同调生成拓扑伪标签，指导测试时分类器进行自适应。
result: 在异常分割任务中取得了更好的结构一致性，提升了分割质量。
conclusion: 为测试时自适应在异常分割中的应用提供了拓扑约束创新思路。
---

## Abstract
Test-time adaptation (TTA) has emerged as a powerful paradigm for handling distribution shifts in deep models, particularly for anomaly segmentation, where pixel-wise labels of anomalous regions are typically unavailable during training. We introduce TopoTTA (Topological Test-Time Adaptation), a novel framework that incorporates persistent homology, a tool from topological data analysis, into the TTA pipeline to enforce structural consistency in segmentation. By applying multi-level cubical complex filtrations to anomaly score maps, TopoTTA generates robust topological pseudo-labels that guide a lightweight test-time classifier, enhancing binary segmentation quality without retraining the backbone model. Our method eliminates the need for heuristic thresholding and generalises across both 2D and 3D modalities. Extensive experiments on MVTec AD and BraTS datasets demonstrate significant improvements over state-of-the-art unsupervised anomaly detection and segmentation methods in terms of F1 score, particularly on anomalies with complex geometries.

---

## 论文详细总结（自动生成）

# 论文总结：Learning Topology-Aware Representations via Test-Time Adaptation for Anomaly Segmentation

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：异常分割（Anomaly Segmentation）中，像素级的异常标签在训练时通常不可用，导致模型在面对测试时分布偏移（distribution shift）时泛化能力差。现有方法依赖启发式阈值（如µ+3σ）或局部峰值选择来生成伪标签，缺乏结构一致性，尤其对几何复杂的异常（如中空、不连续缺陷）表现不佳。
- **整体含义**：本文提出利用拓扑数据分析（Topological Data Analysis, TDA）中的持续同调（Persistent Homology）作为归纳偏置，在测试时自适应（Test-Time Adaptation, TTA）框架下生成结构稳定的伪标签，从而无需重新训练骨干网络即可提升分割质量。该工作旨在弥合“无监督异常检测”与“结构感知分割”之间的鸿沟，并推广到2D和3D模态。

## 2. 方法论

### 核心思想
- 对**异常得分图**（anomaly score map）进行**多级立方复形过滤**（multi-level cubical complex filtration），提取持续同调特征（如连通分量、空洞），生成稳定的**拓扑伪标签**。
- 这些伪标签用于监督一个轻量级的**像素级对比编码器**（Pixel-Level Contrastive Encoder for Binary Segmentation, PCES），在测试时对每个图像自适应训练，输出精细的二元分割掩码。

### 关键技术细节

1. **立方复形构造**：将异常得分图视为离散拓扑空间，构建立方复形K，其中像素定义0-胞腔，相邻像素定义更高维胞腔（边、面、体）。
2. **多级拓扑过滤**：
   - **子水平过滤**（sublevel filtration）：根据递增阈值逐步加入低强度区域。
   - **超水平过滤**（superlevel filtration）：根据递减阈值逐步加入高强度区域。
   - 对两个过滤分别计算持续同调，得到持续特征（出生-死亡对），保留最持久的特征（Top-K或超过阈值τ），生成二元掩码；通过IoU融合两个掩码以消除伪影。
3. **稳定性理论**（Lemma 1）：若两个异常得分图差异小于ε，则其持续图（persistence diagram）的瓶颈距离也小于ε，证明了伪标签对噪声的鲁棒性。
4. **像素级对比编码器（PCES）**：一个浅层MLP（3个线性层+GeLU），输入为预训练骨干网络提取的密集特征图F∈R^{H×W×B}，输出嵌入z。使用对比损失：
   - 对“相似对”（y=0，即同属正常或同属异常的区域）最小化欧氏距离；
   - 对“不相似对”（y=1，即正常与异常区域）施加 margin=1.0 的推远损失。
   - 训练后，基于嵌入的欧氏距离分类器生成最终二元分割。

### 整体流程
测试图像I → AD&S方法生成异常得分图Ψ → 使用冻结的特征提取器F得到特征图 → 对Ψ进行多级立方复形过滤 → 提取持续特征伪标签 → 训练PCES → 应用PCES至全图得到细化分割。

## 3. 实验设计

### 数据集
- **2D工业异常**：MVTec AD（15个类别，5354训练/1725测试图像）。
- **3D工业异常**：MVTec 3D-AD（10个类别，2656训练/1197测试样本）。
- **医学图像**：BraTS 2021（脑肿瘤分割，2040患者数据，二分类：正常vs肿瘤）。

### Benchmark与对比方法
- **基线AD&S模型**：PatchCore（2D）、CMM、M3DM（3D），均使用冻结特征提取器（DINOv2、WideResNet-50、Point-MAE等）。
- **对比策略**：
  - THR：固定阈值（µ+3σ或µ+1σ）。
  - TTT4AS：基于局部峰值和邻域富集生成伪标签的测试时训练方法（Costanzino et al., CVPR 2024）。
- **评价指标**：Precision、Recall、F1 Score（像素级）。
- 额外实验：PaDiM作为2D特征提取基线的补充（附录A.4）。

### 实验充分性
- 主表3个：2D PatchCore（Table 1）、3D CMM（Table 2）、3D M3DM（Table 3），每类详细列出Precision/Recall/F1。
- 消融实验2个：
  - Table 4：Top-K最持久成分的影响（K=1~5）。
  - Table 5：子水平/超水平过滤、IoU融合、PCES模块的独立效果。
- 额外定性结果：图4、5、8、9展示多种类别分割可视化。
- 时间/资源分析：附录A.6。

## 4. 资源与算力

- **GPU**：单张NVIDIA GeForce RTX 3080 Ti。
- **训练细节**：每个测试图像在推理时训练PCES（约0.14秒/图像），多级过滤约0.1秒/图像，总推理约0.23秒/图像（2D）。3D下总推理0.147秒/图像，显存1.52 GB。
- **说明**：论文提供了明确的硬件和运行时间信息，但未说明总实验时长或并行计算规模。

## 5. 实验数量与充分性

- **数量**：共3个数据集（含2D/3D/医学），每个数据集在3种基线模型+3种分割策略（THR、TTT4AS、TopoTTA）上对比；消融研究2个维度（Top-K、模块消融）；3D场景额外对比两种基线模型（CMM和M3DM）；2D补充PaDiM实验结果。
- **充分性**：
  - 覆盖了主流工业异常检测和医学分割场景，2D和3D模态均包括。
  - 消融验证了每个模块的必要性，且展示Top-1最持久成分最优。
  - 稳定性理论提供了数学保证。
  - 局限性：仅采用了固定骨干（PatchCore等），未测试其他AD&S方法；BraTS仅二分类，未涉及多类；无超参数敏感性分析（如margin、阈值τ等）。

## 6. 主要结论与发现

- TopoTTA在MVTec AD 2D上相比THR提升F1 Score 28.0%（0.136→0.476），相比TTT4AS提升9.7%（0.382→0.476）。在MVTec 3D-AD上，CMM基线下提升F1 19.3%（0.275→0.468），M3DM基线下提升28.8%（0.245→0.533）。在BraTS 2021上，比TTT4AS提升F1 4.82%。
- **消融关键发现**：仅使用最持久的拓扑特征（Top-1）即达最佳F1；结合子水平和超水平过滤+IoU+PCES效果最优；仅有超水平过滤虽然召回高但精度极低。
- 推理时间开销低（~0.23秒/2D图像），适用于实际部署。

## 7. 优点

- **方法论创新**：首次将持续同调集成到测试时自适应的异常分割中，取代启发式阈值，提供了理论稳定性保证。
- **模块化设计**：可作为任何输出异常得分图的AD&S方法的即插即用后处理模块，无需重训练骨干。
- **跨模态通用性**：在2D、3D、医学图像上均验证有效。
- **完备的消融实验**：清晰展示了每个组件贡献，验证了“最持久特征”的关键性。
- **高效推理**：轻量PCES和CPU过滤仅需额外约0.1秒，显存占用合理。

## 8. 不足与局限

- **依赖上游得分图质量**：如果预训练骨干或异常检测器生成噪声大、对比低的异常得分图，拓扑过滤可能无法提取有效持久特征。
- **未端到端可微**：当前过滤和伪标签生成不可微，与骨干联合训练受限。
- **未扩展至时空/视频**：仅处理静态图像，未探索时序一致性。
- **未提供置信度量**：缺乏不确定性感知机制，在模糊区域可能误判。
- **实验覆盖有限**：仅用PatchCore、CMM、M3DM三种模型，未测试其他特征提取器或异常检测方法（如cFlow、RD++）。BraTS仅二分类，未涉及多类分割。
- **未报告超参数敏感性**：如margin、阈值、Top-K的详细鲁棒性分析。
- **代码未开源**（声明接受后开源），可复现性当前受限。

（完）
