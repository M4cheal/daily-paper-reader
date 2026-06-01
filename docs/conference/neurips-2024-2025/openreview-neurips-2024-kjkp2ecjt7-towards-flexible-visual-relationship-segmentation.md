---
title: Towards Flexible Visual Relationship Segmentation
title_zh: 迈向灵活的视觉关系分割
authors: "Fangrui Zhu, Jianwei Yang, Huaizu Jiang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=kJkp2ECJT7"
tags: ["query:ris"]
score: 7.0
evidence: 统一视觉关系分割，包含指代关系分割
tldr: 视觉关系理解任务孤立发展，本文提出FleVRS单一模型整合人-物交互检测、场景图生成和指代关系分割，并支持开放词汇分割。通过视觉-语言对齐，FleVRS在多个关系理解基准上取得优异结果，为指代关系分割提供了统一的灵活框架。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-kjkp2ecjt7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1368, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kjkp2ecjt7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kjkp2ecjt7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kjkp2ecjt7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1277, \"height\": 963, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kjkp2ecjt7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1152, \"height\": 900, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kjkp2ecjt7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1141, \"height\": 852, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kjkp2ecjt7/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1024, \"height\": 230, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kjkp2ecjt7/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1311, \"height\": 515, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-kjkp2ecjt7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1154, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kjkp2ecjt7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1326, \"height\": 741, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kjkp2ecjt7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 875, \"height\": 710, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kjkp2ecjt7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1011, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kjkp2ecjt7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 627, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kjkp2ecjt7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 609, \"height\": 609, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kjkp2ecjt7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 756, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kjkp2ecjt7/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1266, \"height\": 1194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kjkp2ecjt7/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 873, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kjkp2ecjt7/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 874, \"height\": 1232, \"label\": \"Table\"}]"
motivation: 现有视觉关系理解任务（HOI、SGG、指代关系）分离，缺乏统一灵活框架。
method: 提出单一模型FleVRS，利用视觉-语言协同将文本特征映射到图像，同时处理三类关系并支持开放词汇。
result: 在多个标准基准上取得竞争性结果，并展现开放词汇泛化能力。
conclusion: 统一框架能有效融合多种视觉关系分割任务，增强灵活性和泛化性。
---

## Abstract
Visual relationship understanding has been studied separately in human-object interaction(HOI) detection, scene graph generation(SGG),  and referring relationships(RR) tasks. 
Given the complexity and interconnectedness of these tasks, it is crucial to have a flexible framework that can effectively address these tasks in a cohesive manner.
In this work, we propose FleVRS, a single model that seamlessly integrates the above three aspects in standard and promptable visual relationship segmentation, and further possesses the capability for open-vocabulary segmentation to adapt to novel scenarios. 
FleVRS leverages the synergy between text and image modalities, 
to ground various types of relationships from images and use textual features from vision-language models to visual conceptual understanding.
Empirical validation across various datasets demonstrates that our framework outperforms existing models in standard, promptable, and open-vocabulary tasks, e.g., +1.9 $mAP$ on HICO-DET, +11.4 $Acc$ on VRD,  +4.7 $mAP$ on unseen HICO-DET.
Our FleVRS represents a significant step towards a more intuitive, comprehensive, and scalable understanding of visual relationships.

---

## 论文详细总结（自动生成）

# 论文总结：Towards Flexible Visual Relationship Segmentation

## 1. 核心问题与整体含义

- **研究动机**：现有的视觉关系理解任务（如人-物交互检测 HOI、场景图生成 SGG、指代关系 RR）通常被孤立地研究，缺乏一个能够同时处理标准关系分割、基于提示（promptable）的关系分割以及开放词汇（open-vocabulary）关系的统一框架。这种碎片化导致模型必须针对每个任务单独设计，无法高效地适应多变的实际应用场景。
- **整体含义**：本文提出 FleVRS——一个**灵活的单一模型**，能够无缝整合上述三方面能力，并在同一架构下支持标准、提示驱动和开放词汇的视觉关系分割（输出 <subject mask, predicate, object mask> 三元组），向着更直观、更全面、更具扩展性的场景理解迈出重要一步。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 利用视觉-语言模型的协同作用，将文本特征映射到图像特征，实现基于查询的关系分割。模型可接受纯图像输入（标准模式），也可接受结构化文本 prompt（提示模式），并借助 CLIP 文本编码器处理未见类别（开放词汇模式）。

### 关键技术细节
- **输入输出**：给定图像 I，输出 <subject mask, predicate class, object mask> 三元组。支持三种 prompt 格式：缺主语/谓语/宾语中的部分元素。
- **架构组件**：
  - **Image Encoder**：使用 Focal-T/L 提取多尺度特征。
  - **Pixel Decoder**：基于 Transformer 的像素解码器，生成逐像素嵌入。
  - **Textual Encoder**：采用 CLIP 文本编码器（冻结），将 prompt 转为文本查询 $Q_t$。
  - **Relationship Decoder**：基于 Transformer 解码器，使用隐式查询 $Q_v$（无 prompt 时）或 $Q_v$ 与 $Q_t$ 的拼接（有 prompt 时）进行跨注意力与自注意力计算。每个查询输出共享五个头：两个掩码头（主语/宾语）、两个分类头（主语/宾语类别）、一个关系分类头。
- **开放词汇机制**：将分类转化为匹配问题——预测的视觉嵌入与 CLIP 文本特征（通过模板如 "A photo of [predicate-ing]" 编码）计算相似度，从而支持未见类别。
- **损失函数**：标准 VRS 使用 focal loss + dice loss（掩码）+ cross-entropy loss（类别）。提示式 VRS 额外增加了 grounding loss $L_g$（匹配 triplet 嵌入与 prompt 文本特征之间的交叉熵）。
- **训练策略**：匈牙利匹配对齐预测与真值；对提示式训练，随机采样不同 prompt 类型，每个图像只选一个真值三元组并搭配随机 prompt，避免捷径学习。

## 3. 实验设计

### 数据集与场景
- **HOI 分割**：HICO-DET（520 类 HOI，44,329 张图）、V-COCO（263 类 HOI，10,396 张图）。将标注框通过 SAM 转为掩码，用 IoU 阈值 0.2 过滤低质量掩码。
- **全景 SGG**：PSG 数据集（48,749 张图，133 物体类别，56 谓语类别）。
- **提示式 VRS**：VRD 数据集（与 SSAS 对比），HICO-DET 和 PSG 上做定性展示。
- **开放词汇 HOI**：HICO-DET 上的零样本设置（Unseen Composition, Unseen Object, Unseen Verb）。

### Benchmark 与对比方法
- **标准 HOI**：对比多种方法，包括 bottom-up（SCG, UPT, ViPLO 等）、两阶段（UniVRD, RLIPv2）、单阶段（HOTR, QPIC, CDN, GEN-VLKT, MUREN 等）。报告 box mAP 和 mask mAP。
- **全景 SGG**：对比 IMP, MOTIFS, VCTree, PSGTR, PSGFormer, HiLo 等。报告 R@K 和 mR@K。
- **提示式 VRS**：对比 SSAS（VRD 数据集），使用 sIoU 指标。
- **开放词汇 HOI**：对比 VCL, ATL, FCL, GEN-VLKT。

## 4. 资源与算力

论文未明确说明具体 GPU 型号、数量及训练总时长。但提供了训练超参数：输入图像 640×640，batch size 64，优化器 AdamW（weight decay 1e-4），训练 30 个 epoch（PSG 为 60 epoch），初始学习率 1e-4（图像编码器 1e-5），在第 20 epoch 降为 1/10。文本编码器冻结（除 logit scale）。可推测使用了多卡 GPU（如 8×V100 或 A100），但具体细节未公布。

## 5. 实验数量与充分性

- **实验数量**：覆盖三大任务（标准、提示式、开放词汇）共 5 个数据集（HICO-DET, V-COCO, PSG, VRD）。标准 HOI 对比了 20+ 方法；全景 SGG 对比 7 种；开放词汇对比 4 种；提示式对比 1 种基线并做了后处理基线。
- **消融实验**：在 Table 7 中针对损失类型（解耦 CE vs. triplet CE）、骨干网络（Focal-T vs. Focal-L）、设计选择（仅 box head vs. 仅 mask head vs. 两者）、多数据集联合训练等进行系统消融。
- **充分性与公平性**：实验较为充分，消融覆盖关键组件。公平性方面：标准 HOI 既报告 box mAP 也报告 mask mAP，并将其他方法输出转换为 mask 做平等对比；提示式 VRS 对比了后处理标准输出的基线。但开放词汇提示式缺乏定量基准（仅定性展示），且提示式 VRS 在 HICO-DET/PSG 上无直接可比方法，公平性略受限。

## 6. 主要结论与发现

- FleVRS 在标准 HOI 分割上取得 **40.5 mask mAP**（HICO-DET Full set），超越所有单阶段方法（GEN-VLKT: 35.6），与两阶段 RLIPv2（48.6）有差距但模型更轻量、不依赖大规模预训练检测数据。
- 在全景 SGG 上获得竞争性结果（R@20 27.0 / mR@20 15.4），但不如 HiLo（40.6 / 29.7），归因于长尾谓语分布和 CLIP 对抽象关系（如 entering/exiting）建模困难。
- 提示式 VRS 在 VRD 上显著优于 SSAS（subject IoU 0.568 vs. 0.335），表明结构化的 prompt 查询能有效定位关系主体。
- 开放词汇 HOI 在所有设置（UC, UO, UV）下均优于此前最佳方法（GEN-VLKT），例如 Unseen Object 上 mAP 14.48 vs. 10.51。解耦编码谓语和物体有助于泛化。
- 消融表明：解耦 CE 损失对 HICO-DET 更好（因谓语与物体独立），而 triplet CE 损失对 V-COCO 更好（因区分谓语高度依赖物体上下文）；更大骨干（Focal-L 优于 Focal-T）带来提升；掩码头比框头更有效，二者结合效果最优；多数据集联合训练提升有限（因谓语空间差异大）。

## 7. 优点

- **统一框架**：首次将标准、提示式、开放词汇三种模式整合到单一 one-stage 模型中，无需额外检测器或数据预处理，便于部署。
- **灵活交互**：支持部分缺失的 prompt（如仅指定谓语），输出对应掩码和类别，更符合自然用户交互。
- **开放词汇泛化**：利用 CLIP 文本特征实现零样本关系理解，无需针对未见类别重新训练。
- **细粒度掩码输出**：将框标注转换为分割掩码，提供更精确的空间定位，消除框的冗余（如重叠）。
- **实验设计严谨**：同时报告 box 和 mask mAP，并利用 SAM 生成 mask 对比公平性，消融实验覆盖关键维度。

## 8. 不足与局限

- **对 SAM 的依赖**：训练时需要将已有的框标注通过 SAM 转为掩码，SAM 生成低质量掩码时需通过 IoU 过滤（丢失约 5% 数据），且该过程引入了额外噪声。
- **开放词汇能力受限**：完全依赖 CLIP 文本编码器，对于抽象或空间关系（如 "entering/exiting"）的语义理解不足，导致全景 SGG 性能受限。
- **提示式 VRS 缺乏标准基准**：在 HICO-DET 和 PSG 上仅有定性结果，无定量可比基线；VRD 上对比 SSAS 时训练数据量差异大（x50 更少），公平性存疑。
- **跨数据集联合训练增益有限**：因不同数据集谓语类别差异大，联合训练未显著提升性能。
- **计算代价**：使用 Focal-L 骨干（198M 参数，15.6 GFLOPs），虽轻于 RLIPv2（640M），但比 ResNet-50 类方法更重，且未报告实际 GPU 训练时间。
- **局限的 prompt 形式**：目前仅支持结构化标记 prompt（如 `<s>person</s><p>ride</p>`），未探索自然语言 prompt，缺乏预处理的规模化方案。
- **未解决长尾分布**：在全景 SGG 上仍偏向高频谓语，低频关系预测困难。

（完）
