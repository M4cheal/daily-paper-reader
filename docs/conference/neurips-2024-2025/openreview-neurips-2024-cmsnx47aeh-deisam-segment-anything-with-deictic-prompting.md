---
title: "DeiSAM: Segment Anything with Deictic Prompting"
title_zh: DeiSAM：用指向性提示分割一切
authors: "Hikaru Shindo, Manuel Brack, Gopika Sudhakaran, Devendra Singh Dhami, Patrick Schramowski, Kristian Kersting"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=cmSNX47aEH"
tags: ["query:ris"]
score: 9.0
evidence: 指向性提示分割，类似于指代分割
tldr: 针对现有方法难以理解复杂指向性描述（如“桌上的杯子后面的物体”）的局限，DeiSAM将大型预训练模型与可微分逻辑推理器结合，实现基于自然语言描述的分割。该方法利用大语言模型解析描述，并通过逻辑推理定位目标，在复杂场景中表现出强大的零样本分割能力。实验表明，DeiSAM能够准确分割基于上下文指代的对象，为指代分割任务提供了新范式。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1315, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 368, \"height\": 257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 529, \"height\": 278, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1421, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 654, \"height\": 200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 733, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1174, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1111, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 799, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-cmsnx47aeh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1452, \"height\": 983, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-cmsnx47aeh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 732, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-cmsnx47aeh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 740, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-cmsnx47aeh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 708, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-cmsnx47aeh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 708, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-cmsnx47aeh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 553, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-cmsnx47aeh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 710, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-cmsnx47aeh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1327, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-cmsnx47aeh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 690, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-cmsnx47aeh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 774, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-cmsnx47aeh/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 765, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-cmsnx47aeh/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1039, \"height\": 229, \"label\": \"Table\"}]"
motivation: 现有方法无法可靠解释复杂语境下的指向性描述，导致分割不准确。
method: 融合大语言模型与可微分逻辑推理器，将自然语言描述转化为可执行的分割逻辑。
result: 在零样本指向性分割任务上取得优异性能，能理解复杂指代关系。
conclusion: DeiSAM有效结合语言推理与视觉分割，为指代分割提供新思路。
---

## Abstract
Large-scale, pre-trained neural networks have demonstrated strong capabilities in various tasks, including zero-shot image segmentation. To identify concrete objects in complex scenes, humans instinctively rely on deictic descriptions in natural language, i.e., referring to something depending on the context such as "The object that is on the desk and behind the cup.". However, deep learning approaches cannot reliably interpret such deictic representations due to their lack of reasoning capabilities in complex scenarios. To remedy this issue, we propose DeiSAM — a combination of large pre-trained neural networks with differentiable logic reasoners — for deictic promptable segmentation. Given a complex, textual segmentation description, DeiSAM leverages Large Language Models (LLMs) to generate first-order logic rules and performs differentiable forward reasoning on generated scene graphs. Subsequently, DeiSAM segments objects by matching them to the logically inferred image regions. As part of our evaluation, we propose the Deictic Visual Genome (DeiVG) dataset, containing paired visual input and complex, deictic textual prompts. Our empirical results demonstrate that DeiSAM is a substantial improvement over purely data-driven baselines for deictic promptable segmentation.

---

## 论文详细总结（自动生成）

# DeiSAM：用指向性提示分割一切 — 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **背景**：大规模预训练神经网络（如SAM、Grounding DINO）在零样本图像分割任务上表现优异，但在理解**指向性描述**（deictic descriptions）时存在明显不足。指向性描述依赖语境和物体间关系，例如“桌上杯子后面的物体”或“船上且举着伞的人”，这类复杂描述需要高阶推理能力。
- **问题**：纯数据驱动方法缺乏结构化推理能力，常将描述中的参照物（如“船”）误判为目标，导致分割错误。人类则能自然利用指向性描述来定位物体，现有AI系统无法可靠模拟这一过程。
- **核心动机**：将大型神经模型与显式、可微分的逻辑推理结合起来，使模型能够忠实理解复杂语境下的自然语言提示，提升分割准确性和可解释性。

## 2. 方法论
### 2.1 核心思想
提出**DeiSAM**（Deictic Segment Anything Model），一种模块化神经符号框架：
- 输入：图像 + 指向性文本提示。
- 输出：目标物体的分割掩码。
- 关键：将自然语言提示转化为一阶逻辑规则，并在场景图上进行可微分前向推理，最终定位并分割目标。

### 2.2 技术流程
1. **场景图生成（SGG）**：使用预训练场景图生成器（如VETO或真实场景图）将图像解析为事实集合，例如 `on(person, boat)`, `holding(person, umbrella)`。
2. **LLM规则生成**：利用大语言模型（如GPT-3.5-turbo）将指向性提示解析为逻辑规则。规则格式为：
   ```
   cond1(X):-on(X,Y), type(Y,boat).
   cond2(X):-holding(X,Y), type(Y,umbrella).
   target(X):-cond1(X), cond2(X).
   ```
   采用少样本+链式思维（CoT）提示策略提升生成质量。
3. **语义统一器**：由于LLM生成规则中的术语（如“boat”）可能与场景图中的术语（如“barge”）不同，使用词嵌入模型（如OpenAI ada-002）计算语义相似度，将规则中的术语映射到场景图中存在的术语。
4. **可微分前向推理**：基于NEUMANN框架构建双向推理图，通过软逻辑运算（乘积为合取、log-sum-exp为析取）进行消息传递，迭代更新事实置信度，最终输出目标物体置信度。
5. **分割**：将置信度最高的目标边界框送入SAM模型，生成分割掩码。

### 2.3 关键技术细节
- **规则格式优化**：限制变量为X和Y，通过增加规则数量而非变量个数来应对复杂提示，实现线性计算资源增长，避免指数级内存消耗。
- **可微分性**：整个推理过程可微分，支持端到端梯度回传，可用于学习场景图生成器的加权混合等下游任务。

## 3. 实验设计
### 3.1 数据集与基准
- **DeiVG**：论文提出新基准，基于Visual Genome构建，包含三个子集（DeiVG 1/2/3），分别对应1/2/3个关系的指向性提示，每子集约10k样本。
- **RefCOCO+ / DeiRefCOCO+**：RefCOCO+的标准指代分割数据集；DeiRefCOCO+则是去除目标名称的抽象版本（如将“kid wearing navy shirt”改为“an object that is wearing navy shirt”）。
- **DeiCLEVR**：基于CLEVR的抽象推理分割任务，涉及删除和排序操作（如“删除灰色物体后的第二个最左物体”），考察高阶逻辑推理。

### 3.2 对比方法
- **纯数据驱动基线**：SEEM、OFA-SAM、GLIP-SAM、GroundingDINO-SAM（均为“检测+分割”流水线）。
- **推理模型**：LISA（当前最先进的推理分割模型，基于多模态LLM微调）。
- **消融变体**：不同LLM（Mistral-7B、Llama-2-7B/13B、GPT-3.5-turbo）、不同嵌入模型、不同提示策略。

### 3.3 评价指标
- **平均精度（mAP）**：将预测分割掩码转为边界框后计算。聚焦于物体识别而非分割质量本身。

## 4. 资源与算力
- **文中未明确说明**使用的GPU型号、数量或训练总时长。实验主要依赖：
  - 公开预训练模型（SAM、GroundingDINO等）。
  - OpenAI API（GPT-3.5-turbo、ada-002嵌入模型）。
  - 本地可微分推理器（NEUMANN）在CPU上即可运行。
- **端到端学习实验**：在约2000样本的小数据集上优化200步，使用RMSProp，并未提及GPU。推理速度分析显示，语义统一最耗时可到6-7秒/样本（API调用），整体DeiSAM约10秒/样本，远慢于GroundedSAM（0.01秒/样本）。因此计算瓶颈在于API而非本地推理。

## 5. 实验数量与充分性
- **实验数量丰富**：
  - 主实验结果（Tab.1）在3个DeiVG子集上对比5种基线，并附有定性案例（Fig.4-5）。
  - 消融实验：
    - LLM规则生成（Tab.2）：提示策略、多种LLM（Tab.7）。
    - 语义统一（Tab.8）：8种嵌入模型。
    - 端到端训练（Tab.6）。
  - 额外场景：RefCOCO+/DeiRefCOCO+（Tab.3-4）；DeiCLEVR抽象推理（Tab.5）。
  - 运行时分析（Tab.9-10）。
- **充分性与公平性**：
  - 基线选择覆盖了主流检测-分割流水线和专门推理模型。
  - 实验设计考虑了不同复杂度（关系数量）、不同抽象程度（有无目标名称）。
  - 但存在一定不足：未报告错误棒（作者解释大部分实验为确定性；LLM调用可能产生随机性，但通过错误重试尽量消除）；DeiVG数据集基于Visual Genome，可能存在标注噪声，未手动清洗全部样本（附录D指出不一致示例）。

## 6. 主要结论与发现
- **DeiSAM显著优于纯数据驱动方法**：在DeiVG 1/2/3上mAP分别达65.14%、85.40%、87.83%，而最强基线LISA仅为14.90%、56.03%、75.79%。
- **少样本+CoT提示对LLM规则生成至关重要**：仅指令或CoT失败率为100%，而少样本+CoT成功率>90%。
- **语义统一仍有瓶颈**：最佳模型（MPNet-Base-v2）仅72%成功率，同义词匹配易出错（如sofa→pillow而非couch）。
- **抽象推理能力突出**：在DeiCLEVR上接近100%mAP，而纯神经基线低于16%；在DeiRefCOCO+（去除目标名称）上，DeiSAM性能保持（~71%），而LISA和GroundedSAM分别下降约30%和45%。
- **端到端可微分训练可行**：通过学习SGG加权混合，mAP从37.61%提升至64.44%（DeiVG1），且置信度更高、分割更准确。

## 7. 优点
- **模块化设计**：场景图生成、LLM规则生成、语义统一、推理器、分割模型均可独立替换，便于扩展和改进。
- **首次将可微分逻辑推理与大模型结合**用于指向性分割任务，填补了领域空白。
- **提出新基准**：DeiVG、DeiRefCOCO+和DeiCLEVR，为社区评估复杂提示分割提供标尺。
- **强可解释性**：显式的逻辑规则和推理过程，避免了神经网络的“黑箱”行为，便于调试和验证。
- **可端到端训练**：梯度可回传至场景图生成组件，支持下游任务适应（如学习多SGG混合权重）。

## 8. 不足与局限
- **规则生成依赖LLM**：少样本提示虽有效，但LLM可能产生语法错误或幻觉，需进一步约束（如语法约束采样）或专用微调。
- **语义统一准确性有限**：当前最佳模型仅72%，容易将查询匹配到不相关的同音/近义词，制约了整体性能。
- **场景图瓶颈**：零样本SGG质量不足，许多目标或关系缺失（如“black shirt”在训练数据中不存在），导致推理失败。端到端训练仅在小规模上验证，且仅学习权重而非整个SGG参数。
- **推理速度慢**：依赖API调用（LLM、嵌入模型），每样本约10秒，不适合实时应用。本地部署可能缓解但模型质量会下降。
- **数据集局限**：DeiVG基于Visual Genome，存在标注错误和不完整（附录D示例），可能引入噪声。DeiCLEVR为合成数据，真实场景泛化性未知。
- **实验统计性**：未提供误差棒或置信区间，部分实验（如端到端训练）仅单次运行，可能受随机性影响。
- **开放性问题**：如何处理完全未见过的关系或物体组合？当前方法需要场景图中提前包含相关事实。

（完）
