---
title: "Cascade-CLIP: Cascaded Vision-Language Embeddings Alignment for Zero-Shot Semantic Segmentation"
title_zh: "Cascade-CLIP: 级联视觉-语言嵌入对齐用于零样本语义分割"
authors: "Yunheng Li, Zhong-Yu Li, Quan-Sheng Zeng, Qibin Hou, Ming-Ming Cheng"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=WUdq1WFUPr"
tags: ["query:ris"]
score: 4.0
evidence: 零样本语义分割使用视觉-语言对齐，与指代分割的泛化相关
tldr: 本文针对零样本语义分割中多层级视觉特征与文本对齐困难的问题，提出Cascade-CLIP方法，通过一系列独立解码器级联对齐各层特征与文本嵌入。该方法改善了零样本分割性能，对于研究指代分割中未见类别的泛化有参考意义。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-wudq1wfupr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 839, \"height\": 718, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wudq1wfupr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1667, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wudq1wfupr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1716, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wudq1wfupr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 837, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wudq1wfupr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1728, \"height\": 966, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wudq1wfupr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1598, \"height\": 1259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wudq1wfupr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1289, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wudq1wfupr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1595, \"height\": 2191, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 1043, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 571, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 803, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 447, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 827, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 826, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 836, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 849, \"height\": 803, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 836, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 861, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 860, \"height\": 820, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 850, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 819, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 844, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 835, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wudq1wfupr/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 836, \"height\": 249, \"label\": \"Table\"}]"
motivation: 现有CLIP方法只利用最后一层视觉特征，且直接聚合多级特征会削弱零样本能力。
method: 引入一系列独立解码器，将多层视觉特征与文本嵌入级联对齐。
result: 在零样本语义分割任务上提升了性能，尤其对未见类别的泛化。
conclusion: 提供了一种有效的多级特征对齐策略。
---

## Abstract
Pre-trained vision-language models, e.g., CLIP, have been successfully applied to zero-shot semantic segmentation. Existing CLIP-based approaches primarily utilize visual features from the last layer to align with text embeddings, while they neglect the crucial information in intermediate layers that contain rich object details. However, we find that directly aggregating the multi-level visual features weakens the zero-shot ability for novel classes. The large differences between the visual features from different layers make these features hard to align well with the text embeddings. We resolve this problem by introducing a series of independent decoders to align the multi-level visual features with the text embeddings in a cascaded way, forming a novel but simple framework named Cascade-CLIP. Our Cascade-CLIP is flexible and can be easily applied to existing zero-shot semantic segmentation methods. Experimental results show that our simple Cascade-CLIP achieves superior zero-shot performance on segmentation benchmarks, like COCO-Stuff, Pascal-VOC, and Pascal-Context. Our code is available at https://github.com/HVision-NKU/Cascade-CLIP.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：零样本语义分割旨在分割训练时未见过的类别。预训练的视觉-语言模型（如CLIP）具有强大的零样本分类能力，但直接用于像素级分割存在困难。现有基于CLIP的方法大多仅利用视觉编码器最后一层的特征与文本嵌入对齐，忽略了中间层包含的丰富物体细节信息。
- **关键挑战**：直接融合多级视觉特征会破坏CLIP预训练时建立的视觉-语言关联，因为不同层特征差异巨大，导致对齐困难，从而削弱对未见类别的零样本能力。
- **整体意义**：提出一种有效利用CLIP中间层细节信息同时保持零样本能力的方法，提升零样本语义分割性能。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将CLIP视觉编码器划分为多个阶段（stage），每个阶段内特征差异较小；为每个阶段分配独立的文本-图像解码器，以级联方式对齐多级视觉特征与文本嵌入；最后融合各阶段生成的分割掩码。
- **关键技术细节**：
  - **级联对齐框架**：将CLIP编码器（ViT-B/16共12层）划分为S个阶段。每个阶段包含一组连续的Transformer块。对于第s个阶段，使用**邻域高斯聚合（NGA）**模块融合该阶段内各块的视觉特征，得到聚合特征 \( Z_s \)。为每个阶段获取独立的文本嵌入 \( \hat{T}_s \)（通过对原始文本嵌入线性投影得到）。每个阶段使用独立的文本-图像解码器 \( D_s \) 生成分割掩码 \( M_s \)。最终所有阶段的掩码通过元素求和融合：\( M = \text{Softmax}(\sum_{s=1}^S D_s(\hat{T}_s, Z_s)) \)。
  - **邻域高斯聚合（NGA）**：对于包含d个块的阶段s，给每个块l分配高斯权重 \( W_{s,l} = \exp\left(-\frac{(d-l+1)^2}{2\sigma^2}\right) \)，其中 \(\sigma\) 默认为1。聚合特征 \( Z_s = \sum_{l=1}^d H_l \cdot W_{s,l} \)。该权重可学习，使邻近块权重更大，减少远距离特征干扰。
  - **损失函数**：使用Dice损失和Focal损失组合：\( L_{\text{pixel}} = \alpha L_{\text{dice}}(Y, M) + \beta L_{\text{focal}}(Y, M) \)，默认 \(\alpha=1, \beta=100\)。
  - **视觉提示调优**：在冻结的编码器中每层引入可学习token，使梯度能反向传播到中间层，促进层间对齐。
- **算法流程**：输入图像→CLIP视觉编码器（冻结，带可学习token）→按阶段提取特征→NGA聚合→每个阶段的独立文本-图像解码器→级联掩码融合→计算损失→反向传播更新。

## 3. 实验设计：数据集、Benchmark、对比方法
- **数据集**：
  - COCO-Stuff 164K（171类，156 seen / 15 unseen）
  - Pascal VOC 2012（20类，15 seen / 5 unseen）
  - Pascal Context（59类，49 seen / 10 unseen）
- **评价指标**：seen类mIoU（mIoU S）、unseen类mIoU（mIoU U）、调和平均IoU（hIoU）。
- **对比方法**：
  - 两阶段方法：ZegFormer、Zsseg、DeOP等（使用ResNet+CLIP双编码器）。
  - 一阶段方法：ZegCLIP、SPT-SEG（均为单CLIP编码器）。
  - 还包括SPNet、ZS3Net、CaGNet等传统零样本方法。
  - 在归纳（inductive）和传导（transductive）设置下均进行对比。
- **结果**：Cascade-CLIP在三个数据集上均达到SOTA，尤其对unseen类提升显著。

## 4. 资源与算力
- **明确说明**：所有实验使用4张NVIDIA RTX 3090 GPU，batch size为4（每卡），输入分辨率512×512，优化器AdamW，训练迭代次数与ZegCLIP一致（COCO-Stuff默认80k迭代）。模型参数量：Cascade-CLIP总参数量193.1M，可训练参数量40.5M，GFLOPs 123.8，FPS 18.4（单卡3090）。未提及具体训练时长。

## 5. 实验数量与充分性
- **实验组数**：
  - 主实验：3个数据集，归纳/传导共约6组（表2、表3）。
  - 消融实验：组件消融（表4）、块划分方式（表5）、级联解码器数量（表6）、NGA vs.其他聚合（表8）、共享/独立文本嵌入（表9）、损失权重（表18）、可学习token数量（表14）、方差参数（表16）、训练迭代影响（图7）等约10组。
  - 泛化实验：迁移到其他数据集（表13）、扩展到其他方法（表10）。
  - 效率对比：表12。
  - 可视化：余弦相似度图、定性分割结果。
- **充分性评估**：实验设计较为充分，覆盖了主要组件、超参数、不同设置（归纳/传导）、泛化能力，对比方法全面，消融实验系统。公平性方面，与ZegCLIP等在同一代码框架（MMSegmentation）、相同训练迭代下比较，结果可靠。

## 6. 主要结论与发现
- 利用CLIP中间层特征可以显著提升零样本语义分割中对未见类别的性能，但简单融合会破坏对齐；提出级联对齐方式有效解决了此问题。
- Cascade-CLIP在COCO-Stuff、Pascal VOC、Pascal Context上均超越先前方法，尤其对unseen类提升大（如Pascal VOC unseen mIoU提升5.3%）。
- 方法具有通用性，可无缝嵌入Frozen CLIP、ZegCLIP、SPT-SEG等方法进一步提升性能。
- 邻域高斯聚合（NGA）比简单求和、拼接、自注意力等聚合方式更优，能减少特征空间破坏。

## 7. 优点
- **创新性**：首次系统研究CLIP中间层特征在零样本分割中的作用，并提出级联对齐这一简洁有效的方案。
- **技术细节**：NGA模块设计巧妙，通过可学习高斯权重平衡不同块贡献；独立解码器避免了特征差异带来的对齐破坏。
- **通用性和灵活性**：可轻松集成到现有方法中，提升性能。
- **效率**：虽然参数略有增加，但计算量几乎不变（GFLOPs与基线相当），推理速度较快。
- **实验充分**：多个数据集、多种设置、大量消融和可视化，验证了方法的有效性和泛化能力。

## 8. 不足与局限
- **实验覆盖**：
  - 仅使用ViT-B/16作为视觉编码器，未探索其他尺寸（如ViT-L、ResNet）或CLIP变体。
  - 仅测试了三个常见数据集（COCO-Stuff、Pascal VOC、Pascal Context），规模中等，未在更大规模或更复杂场景下验证。
  - 未与最新开集分割（open-vocabulary segmentation）方法进行充分对比（虽然提到了部分，但侧重点不同）。
- **偏差风险**：
  - 实验数据集均为常见场景，可能存在领域偏差；对极端或长尾类别的表现未深入分析。
  - 训练数据中seen和unseen的分割基于人为设定，未必代表真实零样本场景。
- **应用限制**：
  - 方法依赖CLIP预训练模型，其固有偏差（如种族、性别偏见）可能传递到分割结果。
  - 级联架构增加了模型设计和调参复杂度（如阶段划分、σ选择），需要一定经验。
- **论文未提及**：
  - 训练耗时具体数值。
  - 对失败案例的分析。
  - 在不同输入分辨率或骨干网络下的鲁棒性测试。

（完）
