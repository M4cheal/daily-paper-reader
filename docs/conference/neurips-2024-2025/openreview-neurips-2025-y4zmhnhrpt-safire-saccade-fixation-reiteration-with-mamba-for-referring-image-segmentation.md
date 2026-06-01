---
title: "SaFiRe: Saccade-Fixation Reiteration with Mamba for Referring Image Segmentation"
title_zh: SaFiRe：基于扫视-注视迭代与Mamba的指代图像分割
authors: "Zhenjie Mao, Yuhuan Yang, Chaofan Ma, Dongsheng Jiang, Jiangchao Yao, Ya Zhang, Yanfeng Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Y4ZMHNhrPT"
tags: ["query:ris"]
score: 10.0
evidence: 使用Mamba处理复杂指代表达的分割任务
tldr: 针对指代图像分割中复杂表达（含多实体干扰或隐含类别）导致歧义的问题，提出SaFiRe模型。模仿人眼扫视-注视机制，结合Mamba状态空间模型迭代聚合上下文线索。在RefCOCO等数据集上超越现有方法，尤其对长难句和隐含指代表现优异，提升了RIS在真实场景的鲁棒性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-y4zmhnhrpt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1436, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y4zmhnhrpt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y4zmhnhrpt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1425, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y4zmhnhrpt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1450, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y4zmhnhrpt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 650, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y4zmhnhrpt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 663, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y4zmhnhrpt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 513, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y4zmhnhrpt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 506, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y4zmhnhrpt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1452, \"height\": 1116, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y4zmhnhrpt/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1452, \"height\": 893, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-y4zmhnhrpt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 608, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y4zmhnhrpt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 769, \"height\": 446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y4zmhnhrpt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 458, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y4zmhnhrpt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 587, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y4zmhnhrpt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 659, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y4zmhnhrpt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 464, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y4zmhnhrpt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 458, \"height\": 226, \"label\": \"Table\"}]"
motivation: 现有RIS方法主要处理简单短语，难以应对含多实体干扰或隐含类别的复杂表达。
method: 设计扫视-注视迭代模块，结合Mamba高效编码序列化上下文信息，逐步聚焦目标。
result: 在RefCOCO/+/g数据集上超越SOTA，复杂表达场景下mIoU提升显著。
conclusion: 模仿视觉关注机制可有效解决RIS中的指代歧义问题。
---

## Abstract
Referring Image Segmentation (RIS) aims to segment the target object in an image given a natural language expression. While recent methods leverage pre-trained vision backbones and more training corpus to achieve impressive results, they predominantly focus on simple expressions—short, clear noun phrases like “red car” or “left girl”. This simplification often reduces RIS to a key word/concept matching problem, limiting the model’s ability to handle referential ambiguity in expressions. In this work, we identify two challenging real-world scenarios: object-distracting expressions, which involve multiple entities with contextual cues, and category-implicit expressions, where the object class is not explicitly stated. To address the challenges, we propose a novel framework, SaFiRe, which mimics the human two-phase cognitive process—first forming a global understanding, then refining it through detail-oriented inspection. This is naturally supported by Mamba’s scan-then-update property, which aligns with our phased design and enables efficient multi-cycle refinement with linear complexity. We further introduce aRefCOCO, a new benchmark designed to evaluate RIS models under ambiguous referring expressions. Extensive experiments on both standard and proposed datasets demonstrate the superiority of SaFiRe over state-of-the-art baselines. Project page: https://zhenjiemao.github.io/SaFiRe/.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
现有指代图像分割（RIS）方法主要处理简单、清晰的名词短语（如“红车”、“左边的女孩”），将任务简化为关键词/概念匹配问题。然而，真实场景中存在两类复杂的指代歧义：
- **对象干扰型表达**：句子包含多个名词短语，但只有一个是真正目标，如“与蓝衬衫男人相比，他更靠近两只长颈鹿”，容易误导注意力。
- **类别隐式表达**：目标对象未明确给出类别，如“他是较高的那个”，依赖代词或比较级，缺乏类级语义线索。  
这些歧义导致现有基于关键词匹配的方法性能下降。受认知心理学中人类两阶段认知过程（全局理解→细节精炼）启发，论文提出SaFiRe框架，模仿扫视（Saccade）与注视（Fixation）交替机制，并利用Mamba状态空间模型的高效序列建模能力，实现粗到细的跨模态对齐。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：模拟人类认知的两阶段过程：先快速全局扫描建立粗略对应（Saccade），再逐区域精细检查并反复确认文本（Fixation）。通过多轮迭代，逐步精炼跨模态理解。
- **关键技术细节**：
  - **整体架构**：使用Swin-Transformer作为视觉编码器，BERT作为文本编码器。设计多个Saccade-Fixation Layer（SFLayer），每个SFLayer依次执行Saccade和Fixation操作。
  - **Saccade操作**：通过对图像特征进行全局文本语义调制（类似DiT的Norm Adaptation），快速建立粗略跨模态对应。具体：对文本序列池化得到全局向量，生成缩放、偏置、移位因子，调制图像特征，再经VSSM层处理。
  - **Fixation操作**：采用“分组-扫描-恢复”模式。将图像分割为不重叠的窗口（如4×4），在每个窗口后重复插入完整文本序列，形成混合序列：`[window1, text, window2, text, ...]`。利用SSM的顺序敏感性，使模型始终聚焦于目标描述，并保持全局记忆。最后恢复图像和文本特征。
  - **复杂度**：Fixation引入的额外长度为`(L/w²)HW`，实际`w=4, L~15`，复杂度增加约0.9倍，仍保持线性复杂度。
  - **损失函数**：Dice损失与Focal损失的组合（权重0.5）。
- **公式/算法流程**：视觉和文本特征经Swin/BERT提取后，通过4个SFLayer交替处理，最终用多层级视觉特征通过mask head预测二值掩码。

## 3. 实验设计
- **数据集**：
  - **标准基准**：RefCOCO、RefCOCO+、RefCOCOg，分别对应简单、中等（无绝对空间词）、复杂描述场景。
  - **新基准**：aRefCOCO（ambiguous RefCOCO），重新标注来自RefCOCO和RefCOCOg的7050个图像-文本对，包含更多对象干扰和类别隐式表达，平均句子长度12.6词，同类别干扰物每张3.1个（比RefCOCOg的1.6高87.5%）。
- **对比方法**：包括VLT、LAVT、ReLA、CGFormer、MagNet、ReMamber、LISA、PSALM等20余种方法，涵盖传统RIS、LLM驱动、SAM基模型等。
- **实验设置**：
  - 单数据集训练与混合数据集训练两种设置。
  - 零样本迁移到aRefCOCO（不在此数据集上训练）。
  - 消融实验（模块、窗口大小、骨干网络等）。
  - 推理效率比较（GFLOPs、FPS）。

## 4. 资源与算力
论文在**实验部分**（Section 4.2 Implementation Details）说明：所有实验在2张NVIDIA A100 GPU上完成，使用AdamW优化器，学习率5e-5，训练50个epoch，批量大小未明确但可推测为常规设置。未提供总训练时长或单次训练时间。

## 5. 实验数量与充分性
- **实验数量**：非常充分。
  - 在3个标准数据集上对比了单数据集训练（Table 1）和混合数据训练（Table 2）的oIoU/mIoU指标。
  - 在aRefCOCO上零样本评估（Table 3），包含5个指标（oIoU, mIoU, Pr@50/70/90）。
  - 消融实验：
    - 模块消融（Saccade vs Fixation vs 全模型，Table 4）。
    - Fixation窗口尺寸消融（2×2, 4×4, 8×8，Table 5）。
    - 骨干网络消融（ViT-B, Swin-B, Swin-L，Table 6）。
    - 层间特征图可视化分析（Fig. 3）。
  - 推理效率对比（Table 7）。
  - 更多可视化（Fig. 4, Fig. 7）。
- **充分性**：实验设计全面，覆盖了不同难度、不同训练范式、不同消融维度，公平性较好（对比方法使用官方设置或复现）。但未报告多次运行的标准差，这在RIS领域常见，但可能削弱统计显著性。

## 6. 论文的主要结论与发现
- SaFiRe在所有标准基准上均达到或超越当前最先进方法，尤其在复杂表达场景（RefCOCOg、aRefCOCO）提升显著。
- Saccade和Fixation操作互补：Saccade提供全局定位，Fixation提供精细对齐，二者协同增强跨模态理解。
- 使用Mamba的序列处理特性模拟人类认知过程是有效且高效的：线性复杂度支持密集区域-文本交互。
- 新基准aRefCOCO有效揭示现有方法在指代歧义下的不足，SaFiRe在该基准上领先（oIoU 65.1% vs 第二名C3VG 62.9%）。
- 推理效率：SaFiRe在384 GFLOPs下达到8.26 FPS，远优于LLM驱动的LISA（4880 GFLOPs, 2.67 FPS）和PSALM（455 GFLOPs, 2.19 FPS）。

## 7. 优点
- **创新性强**：从认知心理学获得灵感，将两阶段视觉注意机制引入RIS，与Mamba的扫描-更新特性天然契合，设计巧妙。
- **方法简洁有效**：仅通过序列重排和重复文本即可实现精细跨模态交互，无需复杂注意力或大规模LLM。
- **性能突出**：在多个基准上取得SOTA，尤其在高难度场景表现出色。
- **高效性**：保持Mamba的线性复杂度，推理速度远超同类方法，实用价值高。
- **贡献完整**：除方法外，还贡献了aRefCOCO新基准，有助于推动该方向研究。

## 8. 不足与局限
- **实验覆盖**：尽管数据集多，但主要基于COCO系列，未在更广泛场景（如自动驾驶、医疗图像）验证，真实世界多样性可能未充分覆盖。
- **偏差风险**：aRefCOCO的生成依赖大语言模型（Qwen-VL-Max），可能引入生成偏差或人工筛选的主观性。论文虽提及进行了人工验证，但未详细说明标注者间一致性。
- **语言多样性不足**：论文承认当前数据集可能无法完全代表真实世界中的语言多样性，尤其是更复杂或方言化的表达。
- **失败案例分析**：指出了两个典型失败场景（视觉语义极度相似、长关系链推理），表明方法在极端条件下仍有局限。
- **未报告多次运行统计**：缺乏误差棒或置信区间，难以评估结果稳定性。

（完）
