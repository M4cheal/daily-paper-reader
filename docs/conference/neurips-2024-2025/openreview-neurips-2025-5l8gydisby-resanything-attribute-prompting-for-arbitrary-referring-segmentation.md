---
title: "RESAnything: Attribute Prompting for Arbitrary Referring Segmentation"
title_zh: RESAnything：面向任意指代分割的属性提示方法
authors: "Ruiqi Wang, Hao Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=5l8GydIsby"
tags: ["query:ris"]
score: 9.0
evidence: 任意指代表达分割，开放词汇零样本
tldr: 针对现有指代分割方法处理复杂表达（如属性、部分）能力不足，本文提出RESAnything，利用LLM进行属性提示（Attribute Prompting）生成详细描述，再结合基础图像分割模型生成候选掩码。在多种指代分割任务上，包括对象级、部分级和隐式引用，RESAnything实现了零样本的优异性能，拓展了指代分割的适用范围。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1416, \"height\": 498, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 661, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1323, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 733, \"height\": 250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 623, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 703, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 688, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 937, \"height\": 2117, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 383, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 386, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 386, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 385, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 383, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 385, \"height\": 294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 385, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 384, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 384, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 385, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 385, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 310, \"height\": 2100, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 313, \"height\": 2081, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1812, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 960, \"height\": 2216, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1722, \"height\": 1191, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1638, \"height\": 2007, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1758, \"height\": 2217, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1755, \"height\": 2131, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1769, \"height\": 2272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1759, \"height\": 2219, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1443, \"height\": 2345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1442, \"height\": 2210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1453, \"height\": 2224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1442, \"height\": 2230, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1437, \"height\": 2194, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1772, \"height\": 2286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1780, \"height\": 2223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1498, \"height\": 2285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1773, \"height\": 2254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1787, \"height\": 2344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5l8gydisby/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1699, \"height\": 2232, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 631, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 680, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 677, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 989, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 548, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 844, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 413, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 437, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 702, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 646, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 691, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 707, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 639, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5l8gydisby/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1782, \"height\": 1838, \"label\": \"Table\"}]"
motivation: 现有指代分割无法处理属性级、部分级及隐式引用等复杂输入表达。
method: 利用LLM链式思考推理，通过属性提示生成形状、颜色、位置等描述，然后结合基础分割模型生成分割候选。
result: 在多种指代分割任务（对象级、部分级、隐式引用）上实现零样本最优或相当性能。
conclusion: 属性提示结合LLM能有效扩展指代分割的输入形式，实现开放词汇零样本分割。
---

## Abstract
We present an open-vocabulary and zero-shot method for arbitrary referring expression segmentation (RES), targeting input expressions that are more general than what prior works were designed to handle. Specifically, our inputs encompass both object- and part-level labels as well as implicit references pointing to properties or qualities of object/part function, design, style, material, etc. Our model, coined RESAnything, leverages Chain-of-Thoughts (CoT) reasoning, where the key idea is attribute prompting. We generate detailed descriptions of object/part attributes including shape, color, and location for potential segment proposals through systematic prompting of a large language model (LLM), where the proposals are produced by a foundational image segmentation model. Our approach encourages deep reasoning about object or part attributes related to function, style, design, etc., enabling the system to handle implicit queries without any part annotations for training or fine-tuning. As the first zero-shot and LLM-based RES method, RESAnything achieves clearly superior performance among zero-shot methods on traditional RES benchmarks and significantly outperforms existing methods on challenging scenarios involving implicit queries and complex part-level relations. Finally, we contribute a new benchmark dataset to offer ~3K carefully curated RES instances to assess part-level, arbitrary RES solutions.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：现有的指代分割（Referring Expression Segmentation, RES）方法大多局限于处理带有明确语义标签的**整体对象**。当输入表达式指代**对象部件**、或包含**隐式引用**（如功能、材质、风格、设计等属性）时，现有方法表现不佳。此外，许多方法需要大量的标注数据进行有监督训练或微调，缺乏零样本泛化能力。
- **研究动机**：为了解决上述限制，作者提出一种**开放词汇、零样本**的**任意指代分割**方法（Arbitrary Referring Segmentation），使得输入表达式可以涵盖：对象/部件语义标签、材质/风格属性、功能/设计描述、LOGO/包装文字等隐含引用。
- **整体含义**：该工作首次将基于大语言模型（LLM）的链式思考（Chain-of-Thought, CoT）推理与基础分割模型（SAM）相结合，实现无需任何微调即可处理复杂、隐式、部件级的指代分割，显著拓展了RES的应用场景（如电商、机器人、人机交互等）。

## 2. 方法论：核心思想、关键技术细节

### 核心思想：属性提示（Attribute Prompting）
- 通过LLM生成目标区域和候选区域的**详细属性描述**（形状、颜色、位置等），将隐式的、抽象的表达转化为具体、可比较的文本，从而弥合文本与视觉之间的鸿沟。
- 使用**两阶段框架**：
  1. **属性提示阶段**：输入图像和指代表达，利用SAM生成一系列分割掩码建议；再利用MLLM（多模态大语言模型）生成：  
     - **参考文本（Reference Text）**：描述输入表达式所指区域的视觉属性。  
     - **候选文本（Candidate Texts）**：描述每个分割掩码建议的视觉属性。  
  2. **掩码选择阶段**：通过多度量评估（文本-文本、文本-图像）从候选中选择最佳掩码，或返回解释（如果目标不可见/不存在）。

### 关键技术细节
- **SAM**：用于生成初始的分割掩码建议（使用0.015%像素采样，过滤小于图像面积0.1%的片段，去重）。
- **MLLM**：使用Pixtral 12B（默认），参考文本和候选文本生成均通过精心设计的提示（Prompt）实现，要求描述形状、颜色、位置等属性。
- **视觉提示选择**：采用 **mask-cropped**（掩码裁剪）和 **bounding box**（边界框）两种视觉提示的组合以兼顾区域细节和空间上下文。
- **多度量选择算法**：  
  1. **文本-文本比较**：MLLM二分类决策（是否匹配）+ CLIP标量相似度评分。  
  2. **文本-图像比较**：MLLM二分类决策 + CLIP标量相似度评分（针对参考文本与掩码裁剪图像）。  
  3. **分组与选择**：优先采用MLLM的“是”决策，再结合CLIP评分选出最佳候选，支持合并多个掩码以处理遮挡/多部件情况。无候选时返回参考文本的解释。
- **零样本、无需训练**：所有组件均为预训练模型，无任何微调。

## 3. 实验设计

### 数据集与场景
- **传统RES基准**：RefCOCO, RefCOCO+, RefCOCOg（用于对象级指代分割）。
- **推理分割基准**：ReasonSeg（包含需常识推理的隐式表达式）。
- **新构建的基准**：**ABO-Image-ARES**——基于ABO数据集，包含2,989个手动精选的指代-分割对，覆盖语义标签、LOGO/包装、功能/设计、材质/风格四类复杂引用，用于评估部件级、任意指代分割。
- **额外评估**：COCO-Tasks（任务导向分割）、gRefCOCO（多对象GRES）、R-RefCOCO/RefZOM（多对象指代）。
- **评价指标**：gIoU（平均每个图像的IoU）、cIoU（累积IoU）。

### 对比方法
- **零样本方法**：GLCLIP, CaR（CLIP as RNN）。
- **有监督/预训练方法**：VLT, CRIS, LAVT, GRES（全监督）；UniRES, LISA, GSVA, GLaMM, SAM4MLLM（预训练）；TOIST, TaskCLIP, CoTDet（任务驱动分割）。

### 实验设置
- MLLM默认用Pixtral 12B，消融实验也测试了Claude 3.5 Sonnet和Qwen2-VL。
- SAM采用ViT-H模型。
- CLIP采用ViT-B-32模型。
- 推理在单块NVIDIA 24GB 4090 GPU上即可运行（开发时使用8块V100 32GB并行）。

## 4. 资源与算力
- **论文中明确说明**：实验在8块NVIDIA 32GB V100 GPU上并行推理，但整个推理过程**可仅在一张NVIDIA 24GB 4090 GPU上有效运行**。
- 未提供训练时长（因为方法零样本，无训练阶段），仅提供推理时间：平均每张图像约12.1秒（使用Qwen2-VL MLLM时）。
- 对比方法运行时：CaR 5.3s, LISA 7.0s, GLaMM 8.6s，RESAnything- Qwen2-VL 12.1s。

## 5. 实验数量与充分性
- **实验数量丰富**：超过5个基准数据集（RefCOCO/+/g、ReasonSeg、ABO-Image-ARES、COCO-Tasks、gRefCOCO、R-RefCOCO、RefZOM、RefCOCOm等），每种数据集包含多个子集（val/testA/testB等）。
- **消融实验充分**：包括：
  - 属性提示 vs 标准提示。
  - 不同视觉提示组合（mask-cropped, bounding box, contour, blur等）。
  - 不同MLLM骨干（Pixtral, Claude, Qwen）。
  - 不同掩码选择器（CLIP only, LLM only, both）。
  - 多次重复实验报告平均结果（RESAnything重复8次）。
- **公平性**：与最先进的有监督/零样本方法比较，基线代码和数据均公开或引用；新数据集ABO-Image-ARES由4名评估者审校，使用Fleiss Kappa保证一致性；所有评估指标标准化。
- **充分结论**：实验覆盖了对象级、部分级、隐式推理、多对象等多种场景，对比方法全面，消融验证了各组件有效性。论文同时报告了部分失败案例，分析客观。

## 6. 主要结论与发现
- RESAnything在**传统RES基准**上以**零样本方式**显著优于所有先前零样本方法，例如RefCOCO val上gIoU达到68.5%（GLCLIP仅26.2%），接近早期有监督方法（如VLT的67.5%）。
- 在**推理分割基准ReasonSeg**上，RESAnything的gIoU达74.6%，cIoU达72.5%，大幅超越LISA-13B（57.7%/60.3%）和SAM4MLLM（58.4%/60.4%）等需要微调的方法。
- 在**新构建的ABO-Image-ARES**基准上，RESAnything的gIoU达78.2%，cIoU达72.4%，远高于GLaMM（46.2%/38.7%）。
- 在**任务驱动分割COCO-Tasks**上达到54.6%（带提示优化），接近有监督方法CoTDet（56.9%）。
- 关键启示：**属性提示**能有效激活MLLM的推理能力，使系统理解隐式、部件级表达；**多度量选择**结合MLLM二分类和CLIP评分可稳健挑选最佳掩码。

## 7. 优点（方法与实验设计亮点）
- **零样本无需训练**：避免了昂贵的标注和微调开销，可快速部署于新场景。
- **属性提示创新**：通过生成详细的视觉属性文本，将复杂的跨模态匹配转化为文本-文本/文本-图像比较，提升推理准确性。
- **多度量融合**：结合MLLM的定性判断和CLIP的定量评分，兼顾准确性与区分能力。
- **视觉提示组合**：采用mask-cropped + bounding box，既保留精细区域细节，又提供空间上下文，经实验验证最优。
- **广泛的实验验证**：涵盖传统+推理+部件级+多对象+任务驱动等多个维度，对比方法包括多种有监督和零样本基线，消融实验完整。
- **新基准贡献**：构建的ABO-Image-ARES填补了部件级、隐式引用评估的空白，包含2989个实例，质量通过多人审核保障。

## 8. 不足与局限
- **对SAM依赖**：SAM偶尔无法生成最优掩码候选，导致分割精度下降（文中承认）。
- **推理效率**：每图像平均12.1秒（Qwen2-VL），相比零样本CaR（5.3s）较慢；需进一步优化（如RoI过滤、尺寸修剪等）。
- **MLLM质量敏感**：性能在不同MLLM间有所波动（Pixtral 12B 74.6 gIoU vs Claude 3.5 76.2 gIoU），依赖特定LLM的推理能力。
- **处理超大完整对象时较弱**：部分对象级分割不及有监督方法（如GLaMM），因为SAM生成的小掩码建议难以覆盖整个物体（需合并，可能遗漏）。
- **实验覆盖有限**：仅在静态图像上评估，未涉及视频、实时场景；未在真实机器人/电商系统中测试。
- **未能完全消除歧义**：在多对象、严重遮挡时，分组算法可能合并错误的掩码或丢失部分（如“腿”可能只选中一条腿）。
- **可重复性限制**：代码未开源（当前提交未包含），但论文提供了足够的提示和算法细节。

（完）
