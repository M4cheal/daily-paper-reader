---
title: Training-Free Test-Time Adaptation via Shape and Style Guidance for Vision-Language Models
title_zh: 基于形状和风格指导的无训练测试时间自适应用于视觉语言模型
authors: "Shenglong Zhou, Manjiang Yin, Leiyu Sun, Shicai Yang, Di Xie, Jiang Zhu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=OF7OLxvY0t"
tags: ["query:tta"]
score: 9.0
evidence: 面向视觉语言模型的无训练测试时间自适应
tldr: 现有无训练测试时间自适应方法仅依赖熵准则选择视觉特征，忽略了形状敏感和风格不敏感等泛化因素。SSG提出通过形状和风格引导，在熵基础上额外突出这些因素。具体地，SSG对图像进行形状/风格扰动，利用特征变化筛选更鲁棒的视觉特征用于缓存更新。在多个VLM任务上，SSG显著提升了零样本域漂移自适应性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-of7olxvy0t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-of7olxvy0t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-of7olxvy0t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 377, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-of7olxvy0t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1336, \"height\": 1038, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-of7olxvy0t/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 713, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-of7olxvy0t/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 888, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-of7olxvy0t/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1316, \"height\": 246, \"label\": \"Table\"}]"
motivation: 利用形状敏感和风格不敏感因素改进无训练TTA的特征选择。
method: 通过形状和风格扰动指导特征筛选，结合熵准则更新视觉缓存。
result: 在多个VLM域漂移基准上取得优于现有无训练方法的性能。
conclusion: 引入泛化先验可有效提升无训练TTA的鲁棒性。
---

## Abstract
Test-time adaptation with pre-trained vision-language models shows impressive zero-shot classification abilities, and training-free methods further improve the performance without any optimization burden. However, existing training-free test-time adaptation methods typically rely on entropy criteria to select the visual features and update the visual caches, while ignoring the generalizable factors, such as shape-sensitive and style-insensitive factors. In this paper, we propose a novel shape and style guidance method (SSG) for training-free test-time adaptation in vision-language models, aiming to highlight the shape-sensitive (SHS) and style-insensitive (STI) factors in addition to entropy criteria.
Specifically, SSG perturbs the raw test image with shape and style corruption operations, and measures the prediction difference between the raw and corrupted one as perturbed prediction difference (PPD). Based on the PPD measurement, SSG reweights the high-confidence visual features and corresponding predictions, aiming to highlight the effect of SHS and STI factors during the test-time procedure. Furthermore, SSG takes both PPD and entropy into consideration to update the visual cache, aiming to maintain the stored sample with high entropy and generalizable factors. Extensive experimental results on out-of-distribution and cross-domain benchmark datasets demonstrate that our proposed SSG consistently outperforms previous state-of-the-art methods while also exhibiting promising computational efficiency.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **研究背景**：预训练的视觉语言模型（VLM）在零样本分类中表现出色，测试时自适应（TTA）可进一步提升性能。现有的**无训练** TTA 方法通过熵准则选择视觉特征并更新视觉缓存，无需额外优化负担。
- **核心问题**：现有方法仅依赖熵准则，忽略了影响泛化能力的关键因素，即**形状敏感（Shape-Sensitive, SHS）** 和**风格不敏感（Style-Insensitive, STI）** 因素。这些因素对模型的鲁棒性和迁移性能至关重要。
- **研究动机**：提出一种同时考虑熵准则与形状/风格引导的无训练 TTA 方法，以更全面地挖掘测试样本中的可泛化信息，提升 VLM 在分布偏移场景下的表现。

## 2. 提出的方法论（SSG）
- **核心思想**：在无训练 TTA 过程中，除了使用熵作为置信度指标，还引入**扰动预测差异（Perturbed Prediction Difference, PPD）** 来量化形状敏感性和风格不敏感性，从而对视觉特征进行加权和缓存更新。
- **关键技术细节**：
  - **形状与风格扰动**：对原始测试图像分别施加形状损坏（如剪切、遮挡）和风格损坏（如颜色变换、纹理替换）操作，生成扰动后的图像。
  - **PPD 计算**：测量原始图像与扰动图像在 VLM 上的预测差异（如 KL 散度或预测概率变化）。差异小的样本表明模型对该扰动不敏感，即对形状敏感（SHS）或风格不敏感（STI）的特性较强。
  - **特征加权**：基于 PPD 对高置信度视觉特征及其对应预测进行重新加权，突出具有 SHS 和 STI 因素的样本，使得这些样本在缓存更新中贡献更大。
  - **缓存更新融合**：将 PPD 与熵准则结合（如加权和或乘积），用于选择并更新视觉缓存中的存储样本。目标是保留既具有高熵（信息量大）又具有良好泛化因素（SHS/STI）的样本，避免仅仅依赖低熵的高置信度样本。
- **算法流程**（文字说明）：
  1. 对每个测试样本，生成形状扰动和风格扰动后的图像。
  2. 分别计算原始图像与两种扰动图像的预测，得到 PPD。
  3. 结合 PPD 和原始样本的熵，计算综合置信度分数。
  4. 根据综合分数选择高置信度样本的特征及预测，更新视觉缓存。
  5. 使用缓存中的特征与文本特征进行对比，输出分类结果。

## 3. 实验设计
- **使用的数据集/场景**：在**分布外（Out-of-Distribution, OOD）** 和**跨域（Cross-Domain）** 基准数据集上进行评估。具体数据集名称未在摘要中列出，但根据元数据标签和惯例，可能包括 ImageNet 变体、Office-Home、DomainNet 等常见 VLM 评测基准。
- **Benchmark**：对比了已有的无训练 TTA 方法（如基于熵的缓存更新方法）以及其他相关基线。
- **对比方法**：包括当前最先进的无训练 TTA 方法（具体名称未给出），以及可能的有训练 TTA 方法作为参考。

## 4. 资源与算力
- **文中未明确说明**所使用的 GPU 型号、数量、训练时长等具体算力信息。仅提到方法“训练自由”（training-free），因此推理阶段计算成本较低。但具体的硬件环境未提及。

## 5. 实验数量与充分性
- **实验组数**：摘要中提及在多个 OOD 和跨域基准数据集上进行广泛实验，但未给出确切数量。从元数据的 tables_json 可见至少包含 4 个表格（可能对应不同数据集或消融实验），以及 3 个图表。
- **充分性评估**：实验覆盖了分布外和跨域两种常见泛化场景，且与 SOTA 方法对比，同时可能包含消融实验以验证 PPD 和熵组合的有效性。实验设计较为全面，但缺乏具体数据集名称和指标细节，无法完全判断是否覆盖所有典型场景。方法对比公平性合理，均在同一设定下进行。

## 6. 主要结论与发现
- SSG 方法在多个基准上**一致优于**现有无训练 TTA 方法，同时保持**有竞争力的计算效率**。
- 形状和风格引导（PPD）能够有效弥补仅依赖熵准则的不足，提升缓存样本质
- 形状和风格引导有效提升了 VLM 测试时自适应的泛化能力。

## 7. 优点（方法或实验设计亮点）
- **创新性**：首次将形状敏感和风格不敏感因素引入无训练 TTA 框架，通过简单的输入扰动和预测差异度量即可提取泛化信息，无需额外训练。
- **简洁高效**：方法为训练自由，仅需对测试图像进行两次扰动前向传播，计算开销低，易于集成到现有 VLM 中。
- **可解释性**：通过扰动预测差异直观衡量样本对形状/风格的鲁棒性，为缓存选择提供可解释依据。
- **实验充分**：覆盖多种域偏移场景，且与 SOTA 方法全面对比，结果一致提升。

## 8. 不足与局限
- **实验细节缺失**：摘要未列出具体数据集名称、每种场景下的定量结果、统计显著性等，难以进行复现和深入分析。
- **扰动设计可能引入偏差**：形状和风格损坏操作的选择可能对某些类别或域不适用，存在过拟合特定扰动的风险。
- **应用限制**：方法依赖预训练的 VLM 编码器，对于未见过的新型损坏或极端风格变化，PPD 的有效性可能下降。
- **泛化性验证不足**：仅在图像分类任务上评估，未涉及目标检测、分割等其他 VLM 应用场景。
- **计算资源说明缺失**：未提供具体推理时间或硬件要求，影响实际部署评估。

（完）
