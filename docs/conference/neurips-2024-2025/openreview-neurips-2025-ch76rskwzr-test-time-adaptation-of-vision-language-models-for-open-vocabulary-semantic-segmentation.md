---
title: Test-Time Adaptation of Vision-Language Models for Open-Vocabulary Semantic Segmentation
title_zh: 视觉语言模型在开放词汇语义分割中的测试时自适应
authors: "Mehrdad Noori, David OSOWIECHI, Gustavo Adolfo Vargas Hakim, Ali Bahri, Moslem Yazdanpanah, Sahar Dastani, Farzad Beizaee, Ismail Ben Ayed, Christian Desrosiers"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=CH76rSKWZr"
tags: ["query:tta"]
score: 9.0
evidence: 视觉语言模型的测试时自适应用于开放词汇语义分割
tldr: 针对开放词汇语义分割这一密集预测任务，现有测试时自适应方法尚未探索。本文提出多级多提示熵最小化（MLMP）方法，结合中间视觉编码层特征和不同文本提示模板，在全局和像素级别进行自适应。该方法可作为即插即用模块集成到任意分割网络中，显著提升了VLM在分割任务上的域自适应性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1419, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1370, \"height\": 766, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1417, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 399, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1212, \"height\": 899, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1284, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1283, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1282, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1283, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1284, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1283, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1286, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1288, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1284, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ch76rskwzr/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1283, \"height\": 519, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 767, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1301, \"height\": 1059, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 720, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 697, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1455, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 868, \"height\": 805, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1449, \"height\": 753, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 730, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 703, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 697, \"height\": 632, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 737, \"height\": 729, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1296, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 725, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1441, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 793, \"height\": 750, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1504, \"height\": 786, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1207, \"height\": 750, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1439, \"height\": 476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1447, \"height\": 752, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1448, \"height\": 750, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1447, \"height\": 753, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1450, \"height\": 852, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ch76rskwzr/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 866, \"height\": 507, \"label\": \"Table\"}]"
motivation: 针对开放词汇语义分割任务缺乏测试时自适应方法的问题，提出一种适用于视觉语言模型的分割自适应方法。
method: 提出多级多提示熵最小化方法，融合中间视觉编码层特征，使用不同文本提示模板在全局和像素级进行自适应。
result: 实验证明该方法可作为即插即用模块显著提升分割网络在域偏移下的性能。
conclusion: 本研究首次将测试时自适应引入开放词汇语义分割，为密集预测任务的域自适应提供了新途径。
---

## Abstract
Recently, test-time adaptation has attracted wide interest in the context of vision-language models for image classification. However, to the best of our knowledge, the problem is completely overlooked in dense prediction tasks such as Open-Vocabulary Semantic Segmentation (OVSS). In response, we propose a novel TTA method tailored to adapting VLMs for segmentation during test time. Unlike TTA methods for image classification, our Multi-Level and Multi-Prompt (MLMP) entropy minimization integrates features from intermediate vision-encoder layers and is performed with different text-prompt templates at both the global CLS token and local pixel-wise levels. 
Our approach could be used as plug-and-play for any segmentation network, does not require additional training data or labels, and remains effective even with a single test sample. Furthermore, we introduce a comprehensive OVSS TTA benchmark suite, which integrates a rigorous evaluation protocol, nine segmentation datasets, 15 common synthetic corruptions, and additional real and rendered domain shifts, with a total of 87 distinct test scenarios, establishing a standardized and comprehensive testbed for future TTA research in open-vocabulary segmentation. Our experiments on this suite demonstrate that our segmentation-tailored method consistently delivers significant gains over direct adoption of TTA classification baselines. Code and data are available at https://github.com/dosowiechi/MLMP.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：开放词汇语义分割（OVSS）旨在通过视觉语言模型（如CLIP）分割未见类别，但现有方法对测试时域偏移（如环境变化、图像损坏）非常脆弱，缺乏在线自适应机制。而现有测试时自适应（TTA）方法主要面向图像分类任务，尚未应用于密集预测任务（如OVSS）。
- **核心问题**：如何设计首个针对OVSS的TTA框架，使其能即插即用地集成到任意分割网络，在无标签、单样本条件下提升域鲁棒性。
- **整体贡献**：提出MLMP（多级多提示熵最小化）方法，填补了TTA在开放词汇语义分割领域的空白，并建立了包含87个测试场景的综合基准。

## 2. 方法论：核心思想、关键技术细节、公式/算法流程

- **核心思想**：将TTA从分类扩展到密集分割，通过两个关键创新——自适应多级特征融合和多提示损失集成——利用VLM的中间层特征和提示敏感性来提供稳健的自适应信号。
- **关键技术细节**：
  - **不确定性感知的多级融合（UAML）**：从视觉编码器的多个中间层提取特征（\( \mathbf{Q}^\ell_i \)），通过各层预测熵计算置信权重 \( \alpha_\ell \)，然后加权平均得到融合特征 \( \mathbf{Q} = \sum_{\ell=1}^L \alpha_\ell \mathbf{Q}^\ell \)。权重计算：\( \alpha_\ell = \frac{\exp(-\beta \cdot h_\ell)}{\sum_{\ell'}\exp(-\beta \cdot h_{\ell'})} \)，其中 \( h_\ell \) 是层ℓ的批量熵。自适应时β=0（均匀），推断时β=1（尖锐化）。
  - **图像级熵最小化（ILE）**：对CLS token的预测进行熵最小化，提供全局上下文稳定信号：\( \mathcal{L}_{\text{ILE}} = -\frac{1}{B}\sum_b \sum_k p_{\text{[cls]},b,k} \log p_{\text{[cls]},b,k} \)。
  - **多提示自适应**：同时使用多个文本提示模板（如7个），对每个模板计算UAML和ILE损失并取平均：\( \mathcal{L}_{\text{final}} = \frac{1}{T}\sum_{t=1}^T (\mathcal{L}_{\text{UAML}}(\mathbf{T}_t) + \mathcal{L}_{\text{ILE}}(\mathbf{T}_t)) \)。理论上证明梯度方差降低为 \( \sigma^2/T \)。
- **算法流程**：自适应阶段，冻结文本编码器，仅更新视觉编码器的LayerNorm参数，利用批量图像（batch size=2）通过Adam优化器进行10次迭代。每个批次后重置模型权重，避免信息泄漏。

## 3. 实验设计：数据集/场景、基准、对比方法

- **数据集与场景**：
  - **合成损坏**：Pascal VOC 20/21、Pascal Context 59/60、Cityscapes的原始版及15种合成损坏（高斯噪声、模糊、雪、JPEG压缩等，严重度5级），形成“-C”版本。
  - **真实域偏移**：ACDC（雾、夜晚、雨、雪）；GTA-V（游戏渲染）。
  - **总计**：9个数据集 ×（原始 + 15损坏 × 某些数据集）共87个不同测试场景。
- **基准**：基于NACLIP（ViT-L/14）作为OVSS基线，对比方法包括：
  - TENT（熵最小化基准）
  - TPT（测试时提示微调）
  - WATT（权重平均测试时自适应）
  - CLIPArTT（基于共形学习的伪标签）
- **公平性**：所有对比方法均修改为处理空间token，使用相同超参数（学习率、迭代次数、批量大小）。

## 4. 资源与算力

- 论文在附录E中详细报告了各方法的计算复杂度：
  - **GPU**：NVIDIA V100（32 GB）
  - **MLMP指标**：自适应时间0.541秒，评估时间0.041秒；GFLOPs：自适应82.4，评估82.9；峰值显存2,093.9 MB；可训练参数仅占模型0.02%（仅LayerNorm）。
  - **对比**：MLMP比TENT稍慢但远快于WATT和CLIPArTT，显存消耗最低。
- 未明确说明训练总时长/GPU数量，但提供了单样本延迟数据。

## 5. 实验数量与充分性

- **实验组数**：
  - 主要对比表（Table 5）覆盖7个数据集×16种条件（原始+15损坏），加上ACDC（4种条件）、GTA-V，以及消融实验（层数选择、组件分析、模板数量、融合策略、单样本、不同骨干/OVSS方法）共数十组。
  - 消融实验：表2（层范围）、表3（组件贡献）、表4（提示集成策略）、图4（模板数量）、表9（单样本）、表10-13（不同ViT骨干/OVSS方法/SigLIP-2）、表15-16（迭代次数、在线vs. episodic）。
- **充分性与公平性**：
  - 所有实验重复3次报告均值和标准差，保证统计稳健。
  - 所有对比方法使用相同批处理、优化设置，并修改为适用于分割。
  - 实验覆盖合成损坏、真实域偏移、不同骨干、不同VLM架构，范围广泛。

## 6. 论文的主要结论与发现

- **主要结论**：MLMP在所有87个测试场景上一致且显著优于现有TTA分类方法（如TENT、TPT、WATT、CLIPArTT），并在无分布偏移的原始数据上也能提升性能（无退化）。
- **关键发现**：
  - 中间层融合（尤其是最后75%层）比仅用最后一层效果更好。
  - 不确定性感知加权（β=1）优于均匀平均。
  - 多提示损失集成优于文本平均或参数平均策略。
  - 7个模板在性能与计算间取得最佳平衡。
  - 图像级熵项提供额外稳定增益。
  - 即使单样本仍有效。
- **量化结果**：在V20-C上MLMP达到77.58 mIoU，对比无自适应69.01，提升8.57；在ACDC上平均提升约7 mIoU；在GTA-V上提升3.75 mIoU。

## 7. 优点：方法或实验设计上的亮点

- **方法亮点**：
  - **首个针对OVSS的TTA框架**，填补重要空白。
  - **即插即用**，可集成到任意OVSS模型，无需额外训练数据或标签。
  - **多级融合**巧妙利用ViT中间层互补特征，并通过熵自适应加权。
  - **多提示损失集成**将提示敏感性转化为稳健信号，理论证明降低梯度方差。
  - **轻量级**：仅更新0.02%参数，计算开销小。
- **实验亮点**：
  - **极其全面的基准**：87个场景，涵盖9个数据集、合成损坏、真实域偏移、渲染域偏移。
  - **严密的消融**：逐组件验证贡献，并探索层范围、模板数、融合策略、骨干变体等。
  - **公平对比**：所有基线统一适配为分割版本，超参数一致，报告多次运行标准差。

## 8. 不足与局限

- **实验覆盖**：
  - 主要基于NACLIP+ViT-L/14，虽在SigLIP-2等上验证，但更多VLM（如SigLIP、EVA-CLIP）未充分覆盖。
  - 仅测试了单一样本和批量大小为2的设置，更大批量或在线场景下性能待探索。
  - 未涉及医学图像、遥感等特殊领域，泛化性未知。
- **方法局限**：
  - 层权重依赖于共享投影头的熵，可能未捕捉每层独特性，需更灵活架构（如独立适配器）。
  - 当前仅更新LayerNorm，更复杂的参数更新策略可能进一步提升性能。
  - 在线自适应（不重置）效果差于episodic，存在误差累积风险，需进一步稳定。
- **偏差风险**：使用7个固定模板，虽然通用但可能对某些场景存在语言偏差；模板选择依赖CLIP原始集合，未尝试动态优化。
- **应用限制**：需要多次前向传播（10次迭代×7模板×多级），实时应用仍有延迟挑战。

（完）
