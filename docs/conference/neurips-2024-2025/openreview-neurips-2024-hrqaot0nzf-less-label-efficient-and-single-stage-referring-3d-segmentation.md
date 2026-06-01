---
title: "LESS: Label-Efficient and Single-Stage Referring 3D Segmentation"
title_zh: LESS：标签高效的单阶段指代3D分割
authors: "Xuexun Liu, Xiaoxu Xu, Jinlong Li, Qiudan Zhang, Xu Wang, Nicu Sebe, Lin Ma"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=hRqaot0NZF"
tags: ["query:ris"]
score: 9.0
evidence: 基于文本查询从点云中分割指定物体的指代3D分割任务
tldr: 本文针对指代3D分割中两阶段方法需要实例和语义标签、训练复杂的问题，提出LESS，一种单阶段标签高效流水线，通过点-词跨模态对齐仅需二值掩码监督，在多个数据集上达到领先性能，显著降低标注成本。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-hrqaot0nzf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1428, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-hrqaot0nzf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-hrqaot0nzf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1406, \"height\": 1110, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-hrqaot0nzf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1410, \"height\": 802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-hrqaot0nzf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1425, \"height\": 410, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-hrqaot0nzf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 703, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hrqaot0nzf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 377, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hrqaot0nzf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 649, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hrqaot0nzf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 824, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hrqaot0nzf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 697, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hrqaot0nzf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 678, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hrqaot0nzf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 940, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hrqaot0nzf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1464, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hrqaot0nzf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 795, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hrqaot0nzf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 796, \"height\": 182, \"label\": \"Table\"}]"
motivation: 现有两阶段方法需要实例和语义标签，训练复杂且耗时。
method: 设计点-词跨模态对齐模块，仅需二值掩码监督实现单阶段指代分割。
result: 在多个数据集上减少标注成本且性能相当。
conclusion: 单阶段范式可推广至其他指代分割任务。
---

## Abstract
Referring 3D Segmentation is a visual-language task that segments all points of the specified object from a 3D point cloud described by a sentence of query. Previous works perform a two-stage paradigm, first conducting language-agnostic instance segmentation then matching with given text query. However, the semantic concepts from text query and visual cues are separately interacted during the training, and both instance and semantic labels for each object are required, which is time consuming and human-labor intensive. To mitigate these issues, we propose a novel Referring 3D Segmentation pipeline, Label-Efficient and Single-Stage, dubbed LESS, which is only under the supervision of efficient binary mask. Specifically, we design a Point-Word Cross-Modal Alignment module for aligning the fine-grained features of points and textual embedding. Query Mask Predictor module and Query-Sentence Alignment module are introduced for coarse-grained alignment between masks and query. Furthermore, we propose an area regularization loss, which coarsely reduces irrelevant background predictions on a large scale. Besides, a point-to-point contrastive loss is proposed concentrating on distinguishing points with subtly similar features. Through extensive experiments, we achieve state-of-the-art performance on ScanRefer dataset by surpassing the previous methods about 3.7% mIoU using only binary labels. Code is available at https://github.com/mellody11/LESS.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与研究动机

- **任务背景**：指代3D分割（Referring 3D Segmentation）要求根据自然语言查询语句，从3D点云场景中分割出指定的物体点集。该任务在AR/VR、机器人、医学成像等领域有重要应用。
- **现有方法局限**：以往方法采用**两阶段范式**——先进行语言无关的实例分割（需要实例标签和语义标签），再与文本查询匹配。这种方式存在两个主要问题：① 实例/语义标签的标注成本极高（时间与人力）；② 训练过程中语言和视觉特征分离交互，无法充分利用文本语义指导分割。
- **论文目标**：提出一种**标签高效（仅需二值掩码）且单阶段**的指代3D分割方法LESS，降低标注成本同时保持/提升分割性能。

## 2. 方法论

### 核心思想
- 将任务构建为**单阶段**分割问题，仅使用目标物体的二值掩码（0/1标签）作为监督信号，省去实例和语义标签。
- 通过多级跨模态对齐（细粒度的点-词对齐和粗粒度的掩码-句子对齐）融合视觉与语言特征，并引入新的损失函数抑制背景干扰、区分相似物体。

### 关键技术
1. **视觉与文本特征提取器**：
   - 视觉：使用稀疏3D U-Net提取点云多尺度特征 \(V_i\)。
   - 文本：采用GRU/BERT/RoBERTa编码查询语句，获得词级特征 \(W\) 和句级特征 \(S\)。

2. **点-词跨模态对齐模块（PWCA）**：
   - 在每个U-Net编码器阶段，利用交叉注意力将词特征 \(W\) 与点云特征 \(V_i\) 对齐，再通过MLP+Tanh门控融合，生成语言感知的视觉特征 \(V'_i\)。
   - 公式：\(V'_i = \text{Tanh}(\text{MLP}(\text{CrossAttn}(V_i, W_i)) + V_i)\)。

3. **查询掩码预测器（QMP）**：
   - 基于可学习查询嵌入 \(Q_0\) 和融合特征 \(F\)，通过多层掩码交叉注意力逐步生成查询嵌入 \(Q_m\) 和候选掩码 \(M_m\)。
   - 掩码通过矩阵乘法 \(M_j = Q_j \otimes \text{Shared-MLP}(F)^\top\) 和 sigmoid 阈值化得到。

4. **查询-句子对齐模块（QSA）**：
   - 计算查询嵌入 \(Q_m\) 与句子特征 \(S\) 的相似度分数 \(R = \text{Softmax}(Q_m \otimes S)\)。
   - 用 \(R\) 加权求和候选掩码 \(M_m\)，得到最终掩码预测 \(\hat{M}\)。

5. **损失函数**（三部分加权组合）：
   - **分割损失** \(L_{seg}\)：二值交叉熵。
   - **面积正则化损失** \(L_{area}\)：抑制大面积背景预测，鼓励预测更紧凑的目标区域。公式：\(L_{area} = \frac{1}{N}\sum_{i=1}^N \sigma(\hat{M}_i)\)。
   - **点对点对比损失** \(L_{p2p}\)：拉近目标点（正样本）与平均正样本特征的距离，推远负样本（背景及其他物体），提升区分度。公式基于InfoNCE。

总损失：\(L = \lambda_{seg} L_{seg} + \lambda_{area} L_{area} + \lambda_{p2p} L_{p2p}\)，实验中设定 \(\lambda_{seg}=1, \lambda_{area}=1, \lambda_{p2p}=0.05\)。

## 3. 实验设计

- **数据集**：ScanRefer（来自ScanNet的800个场景，含51,583条查询语句，平均每场景13.81个物体、64.48条查询）。
- **评价指标**：mIoU（平均交并比）、Acc@0.25（IoU>0.25的准确率）、Acc@0.5（IoU>0.5的准确率）。
- **对比方法**：两阶段方法TGNN（GRU/BERT）和X-RefSeg（GRU/BERT），这些方法使用实例+语义标签。同时对比了同期工作3D-STMN（从零训练时）。
- **消融实验**：模块消融（PWCA、QSA）、损失消融（\(L_{area}\)、\(L_{p2p}\)）、语言粒度（词级 vs 句级 vs 都使用）、查询数量（5/15/20/60/100）、QMP层数（1/3/6）、掩码选择策略（Top-1 vs 加权聚合）。

## 4. 资源与算力

- 论文明确：所有实验在**单张NVIDIA 4090 GPU**上进行。
- 训练时长：LESS总训练时间约 **40.89小时**（对比两阶段方法TGNN需164.55小时、X-RefSeg需163.61小时）。
- 推理时间：全数据集推理 **7.09分钟**（平均每场景44.76ms），远快于两阶段方法（TGNN 27.98分钟、X-RefSeg 20.00分钟）。
- 批大小14，训练64个epoch，优化器Adam，初始学习率文本编码器2e-5，其余1e-4。

## 5. 实验数量与充分性

- **数据集**：主要在ScanRefer验证集上报告结果，未在更多数据集上验证（如ReferIt3D），论文提及这是未来工作方向。
- **对比方法**：与所有主流两阶段方法对比，且报告了不同文本编码器（GRU/BERT/RoBERTa）下的结果。
- **消融实验充分**：
  - 模块消融（3种配置）
  - 损失消融（3种配置）
  - 语言粒度（3种配置）
  - 查询数量（5种配置）
  - 层数（3种配置）
  - 掩码策略（2种配置）
  - 与同期方法3D-STMN从零训练的对比（附录）
- **公平性**：所有对比方法均在同一设置下复现（附录C说明）。标签标注成本进行了估算（表1脚注）。
- **局限性**：在Acc@0.5上低于两阶段方法，因为缺乏实例级先验知识。另外，对模糊查询仍存在误分割（附录B展示失败案例）。

结论：实验设计较为全面，消融实验覆盖了模型各组件和超参数，但数据集仅限ScanRefer，泛化性验证不足。

## 6. 主要结论与发现

- LESS在仅使用二值掩码监督的情况下，在ScanRefer上取得了**SOTA性能**：GRU下mIoU 32.19%（超TGNN 2.42%），BERT下mIoU 32.44%（超X-RefSeg 2.50%），RoBERTa下mIoU 33.74%（超最佳两阶段方法约3.7%）。
- 单阶段方法显著**降低标注成本**（节省约90%的标注时间/人力），且训练和推理时间均远快于两阶段方法。
- PWCA模块通过点-词细粒度对齐有效提升多模态特征质量；QSA模块提供粗粒度句子级对齐，两者互补。
- 面积正则化损失能大幅抑制背景预测（mIoU从25.86%提升至31.04%）；点对点对比损失进一步区分相似物体（mIoU提升至33.74%）。
- 使用20个查询、1层QMP为最优配置；过多查询或层数反而降低性能。

## 7. 优点

- **标签高效**：首次在指代3D分割中探索仅用二值掩码监督，显著降低标注成本。
- **单阶段流水线**：端到端训练，避免两阶段误差累积，且计算效率高。
- **新颖的损失设计**：面积正则化损失和点对点对比损失从粗到细精细化分割结果，有效解决大尺度背景干扰和相似物体混淆问题。
- **细致的消融实验**：验证了各组件和损失函数的贡献，提供了清晰的模块化理解。
- **开源代码**：提供github链接，便于复现和后续研究。

## 8. 不足与局限

- **Acc@0.5偏低**：在需要高精度IoU（>0.5）的场景下，LESS不如两阶段方法（因缺少实例级先验）。论文承认这是可接受的权衡。
- **数据集单一**：仅在ScanRefer上验证，未在ReferIt3D、Multi3DRefer等其他基准上测试，泛化性未知。
- **模糊查询处理能力有限**：附录B失败案例显示，当描述模糊时（如“角落里的黑色椅子”可能同时指代多把椅子），模型易误分割相似物体。
- **缺乏语义先验**：完全依赖二值掩码，无法利用物体类别信息来区分低层视觉相似的物体（如不同类但形状相近的物体）。
- **超参数λ需人工设定**：损失权重（0.05）需经验调整，缺乏自适应机制。
- **未报告统计显著性**：实验仅基于固定种子，未给出误差棒或多运行结果，结果稳定性未知。

（完）
