---
title: "WATT: Weight Average Test Time Adaptation of CLIP"
title_zh: "WATT: CLIP的权重平均测试时自适应"
authors: "David OSOWIECHI, Mehrdad Noori, Gustavo Adolfo Vargas Hakim, Moslem Yazdanpanah, Ali Bahri, Milad Cheraghalikhani, Sahar Dastani, Farzad Beizaee, Ismail Ben Ayed, Christian Desrosiers"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=4D7hnJ9oM6"
tags: ["query:tta"]
score: 9.0
evidence: 使用权重平均和提示集成的CLIP视觉-语言模型测试时自适应
tldr: 视觉-语言模型CLIP在零样本分类中表现出色，但在域迁移下性能下降。WATT方法在测试时利用多样化文本模板生成伪标签，对模型进行更新后通过权重平均融合全局信息，并引入文本集成策略提升性能。实验表明该方法有效缓解了域偏移，且无需额外训练数据，推动了多模态模型自适应的发展。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-4d7hnj9om6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1358, \"height\": 799, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4d7hnj9om6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1170, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4d7hnj9om6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1414, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4d7hnj9om6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1424, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4d7hnj9om6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4d7hnj9om6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 525, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4d7hnj9om6/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 524, \"height\": 514, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1350, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 592, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1145, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 722, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1456, \"height\": 826, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1395, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 540, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 611, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1451, \"height\": 547, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1457, \"height\": 827, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1314, \"height\": 848, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 728, \"height\": 809, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 746, \"height\": 808, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1444, \"height\": 788, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1446, \"height\": 836, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1432, \"height\": 692, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1349, \"height\": 864, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1439, \"height\": 852, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1457, \"height\": 866, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1458, \"height\": 809, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1456, \"height\": 865, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4d7hnj9om6/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1457, \"height\": 809, \"label\": \"Table\"}]"
motivation: CLIP等视觉-语言模型在域偏移下泛化能力受限，需要无需训练数据的自适应方法。
method: 采用多样化文本模板生成伪标签进行模型更新，然后通过权重平均巩固学习到的信息，并集成多种文本模板。
result: 在多个域偏移基准上，WATT显著提升了CLIP的分类准确率，优于现有零样本和自适应方法。
conclusion: WATT为多模态模型提供了一种简单有效的测试时自适应框架，可推广到其他视觉-语言任务。
---

## Abstract
Vision-Language Models (VLMs) such as CLIP have yielded unprecedented performances for zero-shot image classification, yet their generalization capability may still be seriously challenged when confronted to domain shifts. In response, we present Weight Average Test-Time Adaptation (WATT) of CLIP, a new approach facilitating full test-time adaptation (TTA) of this VLM. Our method employs a diverse set of templates for text prompts, augmenting the existing framework of CLIP. Predictions are utilized as pseudo labels for model updates, followed by weight averaging to consolidate the learned information globally. Furthermore, we introduce a text ensemble strategy, enhancing the overall test performance by aggregating diverse textual cues.
Our findings underscore the effectiveness of WATT across diverse datasets, including CIFAR-10-C, CIFAR-10.1, CIFAR-100-C, VisDA-C, and several other challenging datasets, effectively covering a wide range of domain shifts. Notably, these enhancements are achieved without the need for additional model transformations or trainable modules. Moreover, compared to other TTA methods, our approach can operate effectively with just a single image. The code is available at: https://github.com/Mehrdad-Noori/WATT.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：视觉-语言模型（如CLIP）在零样本分类中表现出色，但面对领域偏移（domain shift）时泛化能力严重下降。现有测试时自适应（TTA）方法往往依赖大量数据增强、额外的可训练模块或较大的批次大小，且在单图像场景下效果有限。
- **背景**：CLIP本身通过图像和文本编码器计算相似度进行分类。不同文本提示模板（如“a photo of a {class}”）编码了互补信息，但单一模板无法在所有领域偏移下鲁棒。作者观察发现，对模型在多个模板下独立自适应后，对它们的权重进行平均能收敛到损失和误差更低的区域（如图2所示），这为加权平均策略提供了动机。

#### 2. 方法论
- **核心思想**：提出**WATT**（Weight Average Test-Time Adaptation），利用**多种文本模板**分别自适应CLIP的视觉编码器（仅更新Layer Normalization层），然后对更新后的模型权重进行**平均**，获得鲁棒的全局模型。在评估阶段，再对所有模板的文本嵌入进行**平均**（text ensemble）以提升预测精度。
- **关键技术细节**：
  - **Transductive TTA损失**：基于CLIPArTT[24]的思路，使用图像-图像相似度矩阵 \(S_v\) 和文本-文本相似度矩阵 \(S_t\) 的均值构造伪标签 \(Q\)，然后对视觉-文本相似度 \(P\) 计算交叉熵损失：
    \[
    L_{TTA}(\theta) = -\frac{1}{B}\sum_{i=1}^B\sum_{j=1}^B q_{ij} \log p_{ij}
    \]
    其中 \(q_{ij} = \text{softmax}\left(\frac{S_v+S_t}{2\tau}\right)_{ij}\)，\(p_{ij}\) 为式(1)中的预测概率。
  - **多模板权重平均（MTWA）**：使用H=8个模板（图1a）。两种变体：
    - **并行MTWA（WATT-P）**：每个模板独立从初始权重开始，迭代L步（本文使用L=2）后平均权重，重复M次（M=5）。
    - **顺序MTWA（WATT-S）**：按随机顺序依次对每个模板迭代，每次迭代后更新权重，并在完成一轮所有模板后平均。
  - **评估阶段**：使用所有模板文本嵌入的均值作为文本特征，与权重平均后的视觉模型一起计算最终预测。
- **算法流程**：见附录伪代码Algorithm 1（WATT-P）和Algorithm 2（WATT-S）。

#### 3. 实验设计
- **数据集与场景**：覆盖155个评估场景，包括：
  - 自然图像：CIFAR-10、CIFAR-10.1、CIFAR-100
  - 常见损坏：CIFAR-10-C、CIFAR-100-C（15种腐蚀×5种严重程度，共75种）
  - 模拟与视频偏移：VisDA-C（3D渲染和YouTube帧）
  - 纹理与风格偏移：OfficeHome、PACS、VLCS
- **Benchmark**：以ViT-B/32为主干，对比方法包括TENT、SAR、MEMO、TPT、DiffTPT、TDA、CLIPArTT等。额外测试了ViT-B/16和ViT-L/14。
- **对比方法**：所有对比方法在同一环境下重新实现并运行3次。

#### 4. 资源与算力
- **显式说明**：附录A指出所有实验在**NVIDIA V100 32GB GPU**上运行，代码基于PyTorch 2.0.1。
- **计算成本**：表7给出详细对比：WATT-S适应时间2.34秒，显存1.5GB；WATT-P（并行实现）时间23.2秒（但可并行化），显存1.5GB×8。可学习参数仅占0.026%（仅更新Layer Norm层）。
- **未说明训练时长总量**：但每个实验运行3次，整体计算量在合理范围内。

#### 5. 实验数量与充分性
- **数量**：共155个评估场景，涵盖多种领域偏移类型。包含详细的消融实验（模板数量、迭代次数、批量大小、损失函数对比、不同平均策略等）以及多骨干网络实验（ViT-B/16、ViT-L/14）。
- **充分性与公平性**：所有对比方法在同一环境、相同骨干下重新实现，且报告了3次运行的标准差。消融实验系统全面，清晰展示了各组件贡献。实验设计客观，但缺少对更大规模数据集（如ImageNet变种）的测试。

#### 6. 主要结论与发现
- WATT在**所有测试的领域偏移场景下**均显著提升CLIP的零样本分类准确率，尤其在严重腐蚀（CIFAR-100-C平均提升16.14%）和风格偏移（PACS平均提升1.15%）上表现突出。
- **顺序MTWA（WATT-S）** 总体优于并行MTWA（WATT-P），且计算效率更高。
- **权重平均优于输出平均和文本嵌入平均**，且与适当的L和M参数（L=2, M=5）搭配最优。
- 在**单图像**（batch size=1）场景下WATT仍能提升1-2%准确率，优于需要大量数据增强的MEMO、SAR等。
- WATT无需额外可训练模块或扩散模型，适配速度快，资源需求低。

#### 7. 优点
- **方法简洁高效**：仅需更新LN层，无需额外模型或数据增强，适应速度快（WATT-S仅2.34秒）。
- **单图像有效**：突破了许多TTA方法对大批次的依赖，更具实用性。
- **全面的实验验证**：覆盖155种场景，包含多种偏移类型和骨干网络，消融研究详尽。
- **开源代码**：提供完整复现流程。

#### 8. 不足与局限
- **仅在CLIP上验证**：虽然附录表9在SigLip上也有提升，但主要实验集中在CLIP，对其他VLM（如Florence等）未充分测试。
- **参数依赖**：L和M的最优值仍依赖数据集（小偏移用L=1,M=10，大偏移用L=2,M=5），缺乏自动化选择机制。
- **无大规模/真实世界应用**：未在ImageNet-C等更大规模基准上评估，实际部署中的鲁棒性有待进一步验证。
- **在无偏移场景下不如TENT**：例如CIFAR-10上TENT略高于WATT，说明该方法在无偏移时可能引入轻微过拟合。
- **计算开销说明**：虽然声称轻量，但WATT-P在并行模式下显存线性增加（8×1.5GB），对资源有限的环境可能不现实。

（完）
