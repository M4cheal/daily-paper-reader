---
title: "Echoes of the Visual Past: Test-Time Prompt Tuning with Multi-Scale Visual Memory"
title_zh: 视觉回声：基于多尺度视觉记忆的测试时提示调优
authors: "Ziqiang Wang, Zhixiang Chi, Li Gu, Zhi Liu, Konstantinos N. Plataniotis, Yang Wang"
date: 2025-05-11
pdf: "https://openreview.net/pdf?id=Gsj3oN2Ipy"
tags: ["query:tta"]
score: 9.0
evidence: 视觉语言模型的测试时提示调优
tldr: 针对现有测试时提示调优（TPT）仅从单张图像学习有限类别视觉知识的问题，本文提出多尺度视觉记忆机制，存储历史视觉特征以丰富提示。在多个基准上，该方法超越了手工提示和现有TPT方法，缩小了与提示工程的性能差距。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gsj3on2ipy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gsj3on2ipy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1146, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gsj3on2ipy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1425, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gsj3on2ipy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 594, \"height\": 384, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gsj3on2ipy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1418, \"height\": 568, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gsj3on2ipy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1429, \"height\": 731, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gsj3on2ipy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 721, \"height\": 266, \"label\": \"Table\"}]"
motivation: 现有TPT方法从单张图像获取的视觉知识有限，导致性能不如手工提示。
method: 提出多尺度视觉记忆，结合测试时提示调优，利用历史视觉特征。
result: 在多个分类和可视化任务上超越现有TPT和提示工程方法。
conclusion: 多尺度视觉记忆有效增强了测试时提示的丰富性，无需手工设计。
---

## Abstract
Test-time prompt tuning (TPT) aims to adapt pre-trained vision-language models (VLMs) to various downstream tasks by learning textual prompts using unlabeled data at test time. However, existing TPT methods exhibit a performance gap compared to a line of prompt-engineering-based methods that leverage hand-crafted or LLM-generated prompts for VLM adaptation. We attribute this gap to a core limitation of previous TPT approaches: they learn prompts from only limited class-specific visual knowledge derived from a single test image. As a result, the learned prompts underperform compared to hand-crafted and LLM-generated prompts enriched with diverse, class-specific knowledge. To address this limitation, we propose $\textbf{T}$est-time $\textbf{P}$rompt $\textbf{T}$uning with $\textbf{M}$ulti-scale visual $\textbf{M}$emory $(\text{M}^2\text{TPT})$. Specifically, the memory is constructed to store past seen class-relevant image patches as multi-scale visual descriptions for each class. For each test image, we use it to query the memory and learn the textual prompt using both the test image and the retrieved class-relevant visual memory. Additionally, we introduce holistic visual memory to better handle holistic visual recognition tasks that require global image-level context, and an irrelevance suppression strategy to mitigate the impact of noisy memory entries at test time. We evaluate our method on 15 commonly used benchmark datasets and show that it outperforms existing TPT methods. Furthermore, our framework can incorporate human-designed prompts and achieves state-of-the-art performance compared to recent VLM adaptation methods that use hand-crafted or LLM-generated prompts.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：视觉-语言模型（VLM）在多种下游任务中表现出强大的表征能力。测试时提示调优（TPT）通过利用无标签测试数据优化可学习文本提示，是一种高效的自适应方法。
- **核心问题**：现有TPT方法仅从单张测试图像及其增广样本中学习提示，获取的类别特定视觉知识极其有限，导致其性能显著低于基于手工设计或LLM生成提示的提示工程方法（如CuPL、DMN、AWT等）。
- **动机**：如何在不依赖先验数据集知识的前提下，赋予TPT方法更丰富、多样化的类别级视觉信息，从而缩小与提示工程方法的性能差距。

## 2. 方法论：核心思想、关键技术细节

- **总体框架**：提出 **M²TPT（Test-time Prompt Tuning with Multi-scale Visual Memory）**，核心是构建并利用一个多尺度视觉记忆库，存储历史测试图像中与类别高度相关的图像块特征，并实现可学习提示与记忆库之间的相互促进。

- **关键技术组件**：
  1. **多尺度视觉记忆（Multi-scale Visual Memory）**  
     - 存储结构：`M ∈ R^(C×S×d)`，C为类别数，S为每类记忆容量（默认50），d为特征维度。  
     - 存储内容：由CLIP图像编码器提取的图像块特征（冻结编码器，仅存特征）。
  2. **三步推理流程（每张测试图像独立执行）**：
     - **记忆检索**：用测试图像特征 `v` 查询记忆，通过加权相似度计算得到伪标签 `˜y`，并取出对应类别的记忆块 `M_˜y`。
     - **提示调优**：从通用提示 `p_init` 出发，进行一步梯度更新。优化目标包括两项：
       - 熵最小化损失（在测试图像的低熵随机裁剪块上计算）。
       - 交叉熵损失（在检索到的视觉记忆块上计算，以伪标签为监督）。
       - 公式：`p_ada = p_init - η·∇_p[ H(¯p(X[n],p)) - log ¯p(y=˜y|M_˜y,p) ]`
     - **记忆更新**：用优化后的提示 `p_ada` 对测试图像的随机裁剪块进行预测，选择置信度高（预测与聚合标签一致、熵最低）的块，替换记忆中最不可靠的条目（熵最高）。
  3. **整体视觉记忆（Holistic Visual Memory）**  
     - 为场景理解等需要全局上下文的任务设计，存储完整图像特征而非块特征。  
     - 与多尺度记忆协同工作：检索时选取两者中熵更低的，用于提示调优和最终预测融合。
  4. **不相关抑制策略（Irrelevance Suppression）**  
     - **过滤检索**：在检索时过滤掉相似度较低的条目，仅保留前γ比例（γ=0.5）的高相关记忆。
     - **类无关记忆**：构建一个存储高置信但预测不一致（与记忆聚合预测矛盾）的误导性块，并在提示调优中加入一个平坦标签KL散度损失，惩罚这些错误线索。

- **最终预测**：融合两个预测分数——`P_pt`（来自优化提示）和 `P_memo`（来自更新后的记忆加权分类），取和作为最终预测。

## 3. 实验设计

- **数据集**：
  - **下游分类（10个）**：Flowers102, DTD, OxfordPets, StanfordCars, UCF101, Caltech101, Food101, SUN397, FGVC-Aircraft, EuroSAT。
  - **OOD基准（5个）**：ImageNet验证集、ImageNet-A、ImageNet-V2、ImageNet-R、ImageNet-S。
- **基准方法**：
  - **提示调优方法**：CoOp, CoCoOp, MaPLe（需训练数据），TPT, DiffTPT, C-TPT, DynaPrompt（纯测试时）。
  - **提示工程方法**：VisDesc, WaffleCLIP, CuPL, TDA, DMN, AWT。
- **实现细节**：CLIP ViT-B/16，优化器AdamW，学习率0.003，单步更新，默认记忆大小50，随机裁剪块数32/64，选择比例0.1。
- **公平性**：所有比较均在相同骨干和设置下进行，作者声称结果根据官方代码复现。

## 4. 资源与算力

- **明确说明**：在DTD数据集上使用RTX A4500 GPU测试计算资源。
  - M²TPT：显存1.66 GB，每张图像运行时间0.11秒。
  - 对比：TPT（batch=32）显存1.53 GB，运行时间0.11秒；DynaPrompt显存9.98 GB，运行时间0.41秒。
- **未说明**：完整实验所用GPU数量、总训练/推理时间及能耗细节。主要实验推断为单GPU顺序推理。

## 5. 实验数量与充分性

- **实验数量**：
  - 主表性能对比：10个下游分类 + 5个OOD数据集，共15个数据集，与至少10种方法对比。
  - 消融实验：
    - 主要组件消融（图3a）：逐项添加多尺度记忆、整体记忆、不相关抑制，在10个数据集上平均。
    - 相互促进分析（图3b/c）：验证记忆辅助提示、提示辅助记忆的效果。
    - 记忆大小影响（图4）：在ImageNet验证集上测试S=10~50~100。
    - 计算资源对比（表3）：显存和运行时对比。
- **充分性**：实验覆盖面较广，涵盖了多个领域和分布偏移场景，消融设计合理。但缺少：
  - 多次重复实验标准差（作者声称在补充材料中有误差棒，主文未展示）。
  - 不同骨干网络（如ViT-L）的泛化验证。
  - 非分类任务（如检测、分割）的适应性测试。

## 6. 主要结论与发现

- M²TPT在10个下游分类上平均准确率68.44%，优于所有现有TPT方法（最优DynaPrompt 65.52%），平均提升2.92%。在EuroSAT上提升高达15.94%。
- 在OOD数据集上平均64.80%，同样优于其他TPT方法（DynaPrompt 63.37%）。
- 若整合手工/LLM生成提示，M²TPT†达到71.34%，超越所有提示工程方法（最优AWT 70.51%），证明其兼容性和进一步提升潜力。
- 记忆与提示的相互促进得到验证：记忆辅助的提示调优和提示辅助的记忆更新均比各自基线有显著提升。
- 计算开销小：相比TPT只增加0.13 GB显存，运行时间持平。

## 7. 优点

- **创新性**：首次将多尺度视觉记忆引入测试时提示调优，解决了TPT类别知识贫乏的根本瓶颈。
- **协同设计**：提示–记忆互促框架使得两者在推理过程中共同进化，优于单向利用历史信息的方法。
- **鲁棒性增强**：整体视觉记忆和不相关抑制策略分别解决了全局上下文丢失和噪声记忆干扰问题，设计周全。
- **效率高**：仅需单步优化，计算资源接近原始TPT，显著优于在线连续TPT方法（如DynaPrompt的高内存与高延迟）。
- **兼容性强**：可无缝整合手工/LLM提示，达到SOTA，为未来TPT与提示工程的结合提供了新思路。

## 8. 不足与局限

- **实验局限性**：
  - 仅使用CLIP ViT-B/16，未验证其他骨干（如ViT-L、RN50）的泛化性。
  - 仅评估图像分类任务，未涉及开放词汇检测、分割等更复杂应用。
  - 记忆大小固定（50），对于大规模类别（如ImageNet-21K）或极度长尾分布可能不够灵活。
- **依赖伪标签**：记忆检索和更新依赖于无监督伪标签，初始阶段或噪声样本可能引入错误积累。
- **未提供可重复代码**：作者称接受后开源，当前复现依赖文本描述。
- **对比公平性**：与提示工程方法对比时，M²TPT†使用了相同的提示信息，但统计显著性未在主文明确报告（需检查补充材料）。
- **社会影响讨论不足**：虽在补充材料提及，但未在正文详述潜在偏见或安全风险。

（完）
