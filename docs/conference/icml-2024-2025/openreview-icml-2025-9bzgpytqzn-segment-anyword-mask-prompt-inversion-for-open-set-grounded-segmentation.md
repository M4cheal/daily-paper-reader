---
title: "Segment Anyword: Mask Prompt Inversion for Open-Set Grounded Segmentation"
title_zh: "Segment Anyword: 用于开放集引导分割的掩码提示逆变换"
authors: "Zhihua Liu, Amrutha Saseendran, Lei Tong, Xilin He, Fariba Yousefi, Nikolay Burlutskiy, Dino Oglic, Tom Diethe, Philip Alexander Teare, Huiyu Zhou, Chen Jin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=9bzgpYtQZn"
tags: ["query:ris"]
score: 7.0
evidence: 训练-free的开放集语言引导分割，方法与指代分割任务相关
tldr: 本文提出Segment Anyword，一种无需训练的语言引导开放集分割方法。利用冻结扩散模型的交叉注意力图生成掩码提示，并通过迭代细化得到目标掩码。该方法避免了传统方法的微调需求，能够处理复杂的图像-文本表达，对于指代分割任务具有重要借鉴意义。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1773, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1674, \"height\": 821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 850, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 876, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 815, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 894, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1048, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1504, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1762, \"height\": 1643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1737, \"height\": 1308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1767, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1057, \"height\": 1287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1074, \"height\": 1218, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1417, \"height\": 1401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1071, \"height\": 1524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1295, \"height\": 1501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1269, \"height\": 234, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1724, \"height\": 1987, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1240, \"height\": 2202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1224, \"height\": 2220, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1671, \"height\": 2126, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1041, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1247, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1132, \"height\": 1680, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 531, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 874, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 871, \"height\": 681, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 540, \"height\": 520, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 802, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 463, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 748, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 583, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1297, \"height\": 282, \"label\": \"Table\"}]"
motivation: 现有开放集分割需要大量训练或微调，且难以一致地分割不同文本表达式所指的物体。
method: 提出训练-free的视觉概念提示学习方法，利用扩散模型交叉注意力生成掩码提示并细化。
result: 在开放集语言引导分割任务上取得良好效果。
conclusion: 提供了一种无需训练的灵活分割方案。
---

## Abstract
Open-set image segmentation poses a significant challenge because existing methods often demand extensive training or fine-tuning and generally struggle to segment unified objects consistently across diverse text reference expressions. Motivated by this, we propose Segment Anyword, a novel training-free visual concept prompt learning approach for open-set language grounded segmentation that relies on token-level cross-attention maps from a frozen diffusion model to produce segmentation surrogates or *mask prompts*, which are then refined into targeted object masks. Initial prompts typically lack coherence and consistency as the complexity of the image-text increases, resulting in suboptimal mask fragments. To tackle this issue, we further introduce a novel linguistic-guided visual prompt regularization that binds and clusters visual prompts based on sentence dependency and syntactic structural information, enabling the extraction of robust, noise-tolerant mask prompts, and significant improvements in segmentation accuracy. The proposed approach is effective, generalizes across different open-set segmentation tasks, and achieves state-of-the-art results of 52.5 (+6.8 relative) mIoU on Pascal Context 59, 67.73 (+25.73 relative) cIoU on gRefCOCO, and 67.4 (+1.1 relative to fine-tuned methods) mIoU on GranDf, which is the most complex open-set grounded segmentation task in the field.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：开放集图像分割（open-set image segmentation）中，现有方法通常需要大量训练或微调，且难以在不同文本描述下稳定地分割同一物体。当文本表达变化（如同义词、不同句式）时，性能波动大，且无法泛化到未见过的概念。
- **研究动机**：人类可以通过自由形式的语言描述任意物体，但现有模型（如基于CLIP或MLLM的方法）依赖固定词表或昂贵训练，缺乏对多样化术语的适应性。作者通过激励性实验发现，当前SOTA方法在不同表达间IoU标准差大，表明存在视觉-语言对齐不足的问题。
- **整体含义**：提出一种无需训练、仅利用冻结扩散模型的交叉注意力图来生成掩码提示的方法，实现开放集语言引导分割，兼具高效性与泛化能力。

## 2. 论文提出的方法论
- **核心思想**：利用预训练文本到图像扩散模型的**交叉注意力图**作为定位先验，通过**测试时文本嵌入优化**（textual inversion）对齐视觉概念，再从中采样点作为**掩码提示**（mask prompts）输入给SAM（Segment Anything Model）进行精细化分割。同时引入**语言学引导的正则化**，基于句子依存句法和结构信息绑定和聚类提示，提升鲁棒性。
- **关键技术细节**：
  - **冻结扩散模型**：使用LDM（Latent Diffusion Model），仅更新与目标名词/形容词对应的文本嵌入向量V，其余参数冻结。
  - **测试时文本嵌入更新**：通过图像重建损失优化V（公式2），采用直接反演（Direct Inversion）保持输入图像细节。
  - **交叉注意力收集**：在去噪过程中，对每个token的交叉注意力图按时间步平均，得到高响应区域作为定位先验。
  - **掩码提示生成**：从平均注意力图中随机采样点（正/负），输入冻结SAM作为点提示，获得最终分割掩码。
  - **语言学正则化**：
    - **正向形容词提示聚类**：将名词及其修饰形容词的注意力图点提示聚类为同一组正提示，增强完整性。
    - **负向互斥提示绑定**：利用句法结构（如不同名词短语）将互斥物体的点提示作为负样本，促进边界分离。
- **算法流程**（伪代码见Algorithm 1）：
  1. 输入图像x和文本s。
  2. 冻结文本编码器c_θ和扩散模型ϵ_θ，仅更新文本嵌入V（多概念文本反演）。
  3. 反演得到噪声潜变量Z⋆。
  4. 去噪过程中收集所有时间步的交叉注意力图M，平均得到M̄。
  5. 利用语言学信息对M̄中的点进行聚类/绑定，生成正负提示。
  6. 将提示输入SAM，输出最终分割掩码。

## 3. 实验设计
- **数据集与场景**：
  - **开放集语言引导分割**：GranDf（验证集2.5K，测试集5K）
  - **多目标指代分割**：gRefCOCO（3个split：Val/TestA/TestB）
  - **单目标指代分割**：RefCOCO、RefCOCO+、RefCOCOg（各含Val/TestA/TestB或Val(U)/Test(U)）
  - **开放词汇语义分割**：Pascal Context 59（PC-59，验证集5.1K）
- **Benchmark指标**：AP50、mIoU、Recall（GranDf）；cIoU、gIoU（gRefCOCO、RefCOCO等）；mIoU（PC-59）
- **对比方法**：
  - 传统方法：MattNet、LAVT、VLT等
  - VLM/MLLM方法：CRIS、ReLA、LISA、GSVA、GLaMM、OMG-LLaVA、SAM4MLLM、BuboGPT、Kosmos-2等
  - 训练-free方法：CLIPasRNN、PSALM（零样本）、OVDiff、EmerDiff等
  - 扩散模型方法：ODISE（微调）、EmerDiff（训练-free）
- **实验设置**：严格遵循各数据集的官方评估协议，并报告多项指标，确保公平对比。

## 4. 资源与算力
- **硬件**：单张NVIDIA A100 GPU（40GB显存）。
- **训练/优化**：
  - 测试时文本嵌入更新：默认1100步，使用LoRA微调文本编码器后降至50步。
  - 微调设置：在训练集随机选取500对图像-文本进行LoRA微调（r=16），仅更新BERT编码器。
  - **未提供完整训练时长**，但报告了推理时间：Segment Anyword（1100步）约470秒/图；fast版本（50步）约28秒/图。
- **可训练参数**：<0.1M（仅更新文本嵌入，其余冻结）。

## 5. 实验数量与充分性
- **主要实验**：6个数据集上的量化结果（Table 2-5），涵盖开放集、指代分割、开放词汇语义分割，共约10组对比。
- **消融实验**：在GranDf验证集上对SAM后处理、文本嵌入更新步数、两种正则化（R1、R2）进行系统消融（Table 6），验证每个组件贡献。
- **附加实验**：
  - 谓语动词分割定性展示（Figure 7）
  - 不同词性标注工具对比（附录Table 7）
  - 不同扩散骨干网络和反演算法对比（附录Figure 15）
  - 压力测试（新概念、噪声文本、OOD医学图像）
  - 失败案例分析（微小物体、细长结构）
- **充分性判断**：实验设计全面，覆盖多个任务和数据集，消融完整，对比方法丰富（包括SOTA训练-free和微调方法）。结果客观、公平，统计显著。

## 6. 论文的主要结论与发现
- **主要结论**：
  - Segment Anyword在多个开放集分割任务上达到**训练-free方法新SOTA**，甚至在GranDf上超越部分微调方法。
  - 提出的**语言学引导正则化**显著提升掩码提示质量，正向聚类增强完整性，负向绑定改善边界分离。
  - **测试时文本嵌入更新**有效弥合视觉-语言对齐鸿沟，对多样化术语鲁棒。
- **具体性能提升**：
  - GranDf Val：mIoU 67.4（+1.1 vs 微调方法），AP50 31.3
  - gRefCOCO：cIoU 67.73（+25.73 vs 之前训练-free方法）
  - Pascal Context 59：mIoU 52.5（+6.8 vs EmerDiff）
- **附加发现**：模型能分割谓语动词（如“pulling”），具备潜在推理能力；对OOD医学图像也表现良好。

## 7. 优点
- **无需训练/微调**：完全测试时优化，可快速适应新概念和领域。
- **参数高效**：仅更新极小部分文本嵌入（<0.1M），计算开销低。
- **通用性强**：同时支持开放集、指代、开放词汇语义分割及OOD分割，无需针对任务定制。
- **语言学引导创新**：首次将依存句法信息显式融入视觉提示正则化，有效提升鲁棒性。
- **方法简洁**：冻结扩散模型+SAM，流程清晰，易于复现和扩展。
- **竞争力**：在多个基准上超越或媲美完全微调的MLLM方法，展示了生成模型在判别任务中的潜力。

## 8. 不足与局限
- **微小/细长物体分割困难**：由于交叉注意力图分辨率仅16×16，对细小物体（如“skis”）或细长结构（如“surfboard”）定位不准，易产生碎片化掩码。
- **推理时间较长**：默认1100步需约8分钟/图，即使fast版（50步）仍需28秒，在实时场景中受限。
- **依赖外部语言模型**：词性标注和依存句法解析依赖LLM（如Vicuna或GPT-4o），可能引入错误或额外开销。
- **跨注意力图噪声**：虽经过正则化，但在复杂场景中仍可能出现伪阳性区域，如图像背景杂乱时。
- **缺乏对遮挡和重叠物体的处理**：当多个物体紧密相邻时，负向提示可能不够精准，导致边界混淆。
- **未在纯零样本（无任何领域数据）下评测**：虽为训练-free，但LoRA微调仍利用了目标领域少量数据（500对），并非完全零样本。

（完）
