---
title: "GS-Bias: Global-Spatial Bias Learner for Single-Image Test-Time Adaptation of Vision-Language Models"
title_zh: GS-Bias：面向视觉语言模型的全局-空间偏差学习器用于单图像测试时间自适应
authors: "Zhaohong Huang, Yuxin Zhang, JingJing Xie, Fei Chao, Rongrong Ji"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=gdE3HbHkIL"
tags: ["query:tta"]
score: 9.0
evidence: 视觉语言模型的测试时间自适应
tldr: 现有视觉语言模型的测试时间自适应方法在性能与效率之间难以取得平衡。本文提出的GS-Bias框架引入了全局偏差和空间偏差两种可学习参数，在单幅图像上高效调整模型输出，无需多视图增强或文本提示调优。实验表明该方法在多个零样本基准上取得优越性能，同时保持较低计算开销。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gde3hbhkil/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gde3hbhkil/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1751, \"height\": 617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gde3hbhkil/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 845, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gde3hbhkil/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 837, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gde3hbhkil/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1683, \"height\": 853, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gde3hbhkil/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1672, \"height\": 714, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-gde3hbhkil/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gde3hbhkil/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 585, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gde3hbhkil/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gde3hbhkil/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 853, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gde3hbhkil/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 861, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gde3hbhkil/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1767, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gde3hbhkil/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1778, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gde3hbhkil/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 821, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gde3hbhkil/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 875, \"height\": 280, \"label\": \"Table\"}]"
motivation: 现有TTA方法在视觉语言模型上性能与效率难以兼顾，亟需轻量有效的解决方案。
method: 引入全局偏差和空间偏差两种可学习参数，在测试时仅更新这些偏置项以实现高效自适应。
result: 在多个零样本分类任务上取得更优性能，且计算开销显著低于对比方法。
conclusion: GS-Bias为视觉语言模型提供了一种高效实用的单图像测试时间自适应范式。
---

## Abstract
Recent advances in test-time adaptation (TTA) for Vision-Language Models (VLMs) have garnered increasing attention, particularly through the use of multiple augmented views of a single image to boost zero-shot generalization. Unfortunately, existing methods fail to strike a satisfactory balance between performance and efficiency, either due to excessive overhead of tuning text prompts or unstable benefits from handcrafted, training-free visual feature enhancement. In this paper, we present Global-Spatial Bias Learner (GS-Bias), an efficient and effective TTA paradigm that incorporates two learnable biases during TTA, unfolded as the global bias and spatial bias. Particularly, the global bias captures the global semantic features of a test image by learning consistency across augmented views, while spatial bias learns the semantic coherence between regions in the image’s spatial visual representation. It is worth highlighting that these two sets of biases are directly added to the logits outputed by the pretrained VLMs, which circumvent the full backpropagation through VLM that hinders the efficiency of existing TTA methods. This endows GS-Bias with extremely high efficiency while achieving state-of-the-art performance on 15 benchmark datasets. For example, it achieves a 2.23% improvement over TPT in cross-dataset generalization and a 2.72% improvement in domain generalization, while requiring only 6.5% of TPT's memory usage on ImageNet.

---

## 论文详细总结（自动生成）

# 论文详细中文总结：GS-Bias: Global-Spatial Bias Learner for Single-Image Test-Time Adaptation of Vision-Language Models

## 1. 核心问题与整体含义（研究动机与背景）

- **研究动机**：视觉语言模型（VLM，如CLIP）在零样本任务上表现优异，但实际部署中面临训练数据与下游任务之间的分布偏移，且缺乏高质量任务特定训练数据。测试时间自适应（TTA）通过在线适配单张测试样本来解决这一问题，但现有方法存在性能与效率的矛盾。
- **现有方法的不足**：
  - **测试时提示优化器**（如TPT、DiffTPT）：通过优化文本提示（prompt）来最小化多增强视图的熵，性能好，但需要在整个网络上反向传播，内存和计算开销巨大，且需要二次推理。
  - **测试时视觉优化器**（如MTA）：通过无参数方式直接优化视觉特征（如MeanShift），效率高，但性能受限于增强视图质量，在未见类等复杂场景下效果不稳定。
- **本文目标**：提出一种同时兼顾性能与效率的TTA方法，在保持高泛化能力的同时显著降低计算开销。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：在VLM（以CLIP为例）的输出logits上直接添加两组可学习的偏置项——**全局偏置**（Global Bias）和**空间偏置**（Spatial Bias），通过仅对这些偏置进行轻量级反向传播来适配单张测试图像，避免对整个网络进行反向传播和二次推理。
- **关键技术细节**：
  - **全局偏置学习器**：
    - 初始化一个可学习向量 \( B_g \in \mathbb{R}^{1 \times C} \)（C为类别数），初始值为零。
    - 对测试图像生成N个增强视图，计算每个视图的logits，并添加 \( B_g \)。
    - 通过熵过滤（保留低熵的ρ比例视图）后，计算平均预测分布 \( \tilde{p}_g \)，然后最小化其熵，更新 \( B_g \)。
    - 更新后的 \( B_g \) 直接加到原始CLIP输出logits上得到最终预测。
  - **空间偏置学习器**：
    - 利用视觉编码器中的空间特征图 \( F_s \in \mathbb{R}^{(h \times w) \times d} \)，计算每个空间区域与各类别文本特征之间的相似度，得到空间概率矩阵。
    - 通过类别感知的空间特征图 \( M \)（对相似度取softmax后平均），选择Top-K最相关的空间区域。
    - 在这些选中的区域上添加共享的可学习空间偏置 \( B_s \in \mathbb{R}^{1 \times C} \)，计算平均预测 \( \tilde{p}_s \)，并最小化其熵来更新 \( B_s \)。
  - **最终预测**：将原始CLIP输出、全局偏置、空间偏置三者相加：\( p_{\text{GS-Bias}}(y|x) = p_{\text{CLIP}}(y|x) + B_g + B_s \)。
- **关键优势**：优化只在logits层面进行，反向传播仅涉及少量参数，不需要通过整个VLM，因此极轻量；且无需二次推理。

## 3. 实验设计

- **使用的数据集/场景**：
  - **跨数据集泛化**：10个数据集，涵盖植物/动物（Flowers102, OxfordPets）、交通工具（StanfordCars, FGVC-Aircraft）、食物（Food101）、卫星图像（EuroSAT）、人类动作（UCF101）、纹理（DTD）、场景（SUN397）、通用物体（Caltech101）。
  - **域泛化**：ImageNet及其4个OOD变体（ImageNet-V2, ImageNet-Sketch, ImageNet-A, ImageNet-R）。
- **Benchmark**：采用标准的TTA评估协议，以Top-1准确率（%）为指标。
- **对比方法**：
  - 零样本CLIP（含手工提示与集成提示）
  - 训练时适应方法：CoOp、CoCoOp（在ImageNet上每类16样本训练）
  - 测试时适应方法：TPT、DiffTPT、MTA（及其带集成提示的变体）
- **实验充分性**：
  - 在15个数据集上进行了全面评估（10个跨数据+5个域泛化）。
  - 在不同骨干网络（ViT-B/16和ResNet50）上验证。
  - 进行了详尽的消融实验，包括全局/空间偏置的作用、学习率α/β、空间区域数量K、TTA步数、增强视图数量N等。
  - 提供了效率对比（FPS、GPU内存）、定性结果（示例概率分布可视化）。
  - 附录中还包含与历史数据流方法的兼容性分析、空间视图与随机裁剪视图的对比等。

## 4. 资源与算力

- 论文中明确提到：所有效率对比实验在**单个NVIDIA A800 GPU**上进行，使用官方公开代码复现。
- 未说明训练时长，但给出了FPS和内存消耗数据：
  - TPT：1.38 FPS，19997 MiB
  - MTA：8.59 FPS，3576 MiB
  - GS-Bias（带集成提示）：12.34 FPS，1308 MiB
- 表明GS-Bias在单卡上即可高效运行，无需昂贵多卡训练。

## 5. 实验数量与充分性评价

- **实验数量**：核心结果表格4个（跨数据集、域泛化、效率对比、消融），附录中额外6个表/图，总计超过10组实验分析。
- **充分性**：实验覆盖了主流TTA基准，消融实验系统全面，对比方法均为最新SOTA，且包含不同骨干、不同超参数分析。实验设计客观公平，如使用相同增强策略、相同评价指标，并复现了对比方法的官方结果。
- **潜在不足**：超参数（如α、β、K、步数）是基于多个数据集经验设定的，论文承认可能不是每个测试实例的最优值；但通过消融验证了方法对这些参数不敏感。

## 6. 主要结论与发现

- GS-Bias在跨数据集泛化和域泛化上均达到SOTA性能，例如比TPT分别提升2.23%和2.72%，同时内存占用仅为TPT的6.5%。
- 全局偏置有效捕获图像全局语义，空间偏置增强细粒度空间信息，两者互补。
- 在未见类场景下，GS-Bias通过保留原始CLIP输出避免了性能退化（而TPT、MTA在某些数据集上出现下降）。
- 多步TTA可进一步小幅提升跨数据集性能，但在ImageNet上一步即饱和。
- 空间区域选择K=16在多数数据集上最佳，与统计的“显著区域”平均数目一致。
- 该方法与历史数据流方法兼容，可进一步改进（如GS-Bias+TDA在保持内存不变的情况下性能提升）。

## 7. 优点（方法与实验设计的亮点）

- **创新性**：首次在VLM的TTA中引入logits层面的可学习偏置，同时利用全局一致性和空间语义一致性，思路简洁有效。
- **效率极高**：仅更新两个小向量，避免全网络反向传播和二次推理，FPS是TPT的约9倍，内存仅6.5%。
- **泛化性强**：在15个数据集上一致优于或持平SOTA，且不会损害原始CLIP性能（零风险）。
- **兼容性好**：可与历史数据流、多种骨干（ViT、ResNet）和提示集成策略结合。
- **实验严谨**：消融实验覆盖所有核心组件和超参数，定性结果直观展示偏置的纠正作用，效率对比在同硬件条件下进行。

## 8. 不足与局限

- **超参数依赖经验设置**：α、β、K、步数等需要针对不同数据集调整，论文虽通过消融证明不敏感，但未提供自适应机制，可能限制实际部署的便捷性。
- **仅支持单图像TTA**：未探索批量或流式TTA场景，虽然附录中展示了与历史数据流的初步兼容，但非核心方案。
- **实验覆盖范围**：主要聚焦于分类任务，未在分割、检测等其他VLM任务上验证；仅使用了CLIP，未测试其他VLM架构（如Flamingo、BLIP等）。
- **风险与偏差**：依赖随机裁剪作为唯一增强策略，可能对某些任务（如图像风格变化大的域）不够鲁棒；空间区域选择可能引入背景噪声（当K过大时）。
- **未讨论计算资源详细消耗**：除了内存和FPS，未给出训练步骤的绝对时间或不同显存配置下的表现。

（完）
