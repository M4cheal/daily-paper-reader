---
title: "RG-SAN: Rule-Guided Spatial Awareness Network for End-to-End 3D Referring Expression Segmentation"
title_zh: RG-SAN：规则引导空间感知网络用于端到端3D指代表达分割
authors: "Changli Wu, Qi Chen, Jiayi Ji, Haowei Wang, Yiwei Ma, You Huang, Gen Luo, Hao Fei, Xiaoshuai Sun, Rongrong Ji"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=r5spnrY6H3"
tags: ["query:ris"]
score: 8.0
evidence: 基于规则引导空间感知的3D指代表达分割
tldr: 针对3D指代表达分割中过度分割或错分的问题，提出规则引导空间感知网络RG-SAN。仅利用目标实例的空间信息进行弱监督，通过文本驱动定位模块和规则引导弱监督模块准确建模文本描述的实体空间关系。在ScanRefer等数据集上显著提升分割准确率，为3D指代分割提供了轻量级监督方案。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-r5spnry6h3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 694, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-r5spnry6h3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1301, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-r5spnry6h3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1431, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-r5spnry6h3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 490, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-r5spnry6h3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 1281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-r5spnry6h3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1431, \"height\": 2285, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-r5spnry6h3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 632, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-r5spnry6h3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 685, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-r5spnry6h3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 687, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-r5spnry6h3/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 684, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-r5spnry6h3/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 683, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-r5spnry6h3/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-r5spnry6h3/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1118, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-r5spnry6h3/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 969, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-r5spnry6h3/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 998, \"height\": 262, \"label\": \"Table\"}]"
motivation: 3D指代分割常因空间信息利用不足导致过度分割或错分。
method: 设计文本驱动定位模块和规则引导弱监督模块，仅用空间信息监督。
result: "在ScanRefer等数据集上mIoU提升5%以上，推理更快。"
conclusion: 规则化空间弱监督可高效提升3D指代分割的准确性。
---

## Abstract
3D Referring Expression Segmentation (3D-RES) aims to segment 3D objects by correlating referring expressions with point clouds. However, traditional approaches frequently encounter issues like over-segmentation or mis-segmentation, due to insufficient emphasis on spatial information of instances. In this paper, we introduce a Rule-Guided Spatial Awareness Network (RG-SAN) by utilizing solely the spatial information of the target instance for supervision. This approach enables the network to accurately depict the spatial relationships among all entities described in the text, thus enhancing the reasoning capabilities. The RG-SAN consists of the Text-driven Localization Module (TLM) and the Rule-guided Weak Supervision (RWS) strategy. The TLM initially locates all mentioned instances and iteratively refines their positional information. The RWS strategy, acknowledging that only target objects have supervised positional information, employs dependency tree rules to precisely guide the core instance’s positioning. Extensive testing on the ScanRefer benchmark has shown that RG-SAN not only establishes new performance benchmarks, with an mIoU increase of 5.1 points, but also exhibits significant improvements in robustness when processing descriptions with spatial ambiguity. All codes are available at https://github.com/sosppxo/RG-SAN.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **任务定义**：3D Referring Expression Segmentation (3D-RES) 旨在根据自然语言指代描述在3D点云场景中分割出目标物体实例。
- **现有挑战**：传统方法（如两阶段或早期端到端模型）过度依赖文本推理，忽视实例间的空间关系建模，导致在涉及复杂空间术语（如“far away”、“left of”）的描述中容易发生过分割或误分割。例如，图1展示当有多个相似物体时，缺乏空间推理模型难以正确识别目标。
- **动机**：空间信息在3D场景理解中至关重要。论文分析ScanRefer数据集发现约92%的描述包含空间关系词汇，但已有方法未充分建模这些关系。作者希望仅利用目标实例的空间信息作为弱监督信号，引导网络学习所有提及实体的空间关系，从而提升推理和定位能力。

## 2. 论文提出的方法论

### 核心思想
- 提出 **Rule-Guided Spatial Awareness Network (RG-SAN)**，由两个核心模块组成：
  1. **Text-driven Localization Module (TLM)**：对描述中所有提及的实例（名词）初始化并迭代细化其在3D空间中的位置。
  2. **Rule-guided Weak Supervision (RWS)**：仅依赖目标实例的位置标签，通过依赖树规则确定核心实例，并对其实施加位置监督，从而间接学习其他实体的空间关系。

### 关键技术细节
1. **特征提取**：
   - **视觉编码**：使用预训练的Sparse 3D U-Net提取逐点特征，然后通过无监督分割得到超点（superpoints），再通过超点池化得到超点级特征 \(S_p \in \mathbb{R}^{N_s \times C_p}\)。
   - **语言编码**：使用预训练MPNet提取词级嵌入 \(E_0 \in \mathbb{R}^{N_t \times C_t}\)。

2. **文本驱动定位模块 (TLM)**：
   - **文本驱动初始化**：通过计算词嵌入与超点特征的相似度矩阵 \(A\)（公式2），得到每个词令牌位于各超点的概率分布，从而初始化每个词的空间位置 \(P^t_{0,i}\) 和对应的视觉表示 \(\hat{E}_{0,i}\)（公式3-4）。
   - **迭代位置细化**：经过多层多模态交互后，使用MLP预测每轮的位置偏移 \(\Delta P^t_l\)，并累加到上一轮位置（公式5），实现逐步精确化。
   - **位置编码**：采用绝对位置编码（APE）增强自注意力，再结合相对位置编码（RPE，如Table-based RPE或5D Euclidean RPE）进行跨模态聚合（公式6-10），得到更新后的分割核 \(\hat{E}_{l+1}\)。

3. **规则引导弱监督 (RWS)**：
   - **规则引导目标选择**：利用依赖树分析，通过Algorithm 1定义的规则（如查找主语、排除虚词等）精准定位核心实例（即目标名词）的索引。
   - **训练目标**：仅对核心实例的分割核 \(\hat{E}_{l+1}^{tgt}\) 和位置 \(P_{l+1}^{tgt}\) 进行监督。损失函数为：
     - 掩码损失：BCE + Dice（公式14-15）
     - 位置损失：L1 loss（公式16）
     - 辅助得分损失（mask quality prediction）
     - 加权和：\(\mathcal{L} = \lambda_{bce} \mathcal{L}_{bce} + \lambda_{dice} \mathcal{L}_{dice} + \lambda_{pos} \mathcal{L}_{pos} + \lambda_{score} \mathcal{L}_{score}\)（公式17）

## 3. 实验设计

- **主要数据集与基准**：使用 **ScanRefer** 数据集（51583个英文描述，11046个物体，800个ScanNet场景）。评估指标为 **mIoU** 和 **Acc@kIoU**（k=0.25和0.5），并区分“Unique”（唯一类别实例）和“Multiple”（存在同类干扰）两类情况。
- **对比方法**：
  - 两阶段方法：TGNN、InstanceRefer、3DVG-Transformer、X-RefSeg3D等。
  - 单阶段端到端方法：3D-STMN、3DRefTR-SP/HR、EDA-box2mask、3D-SPS等。
  - 多任务/LLM-based方法：UniSeg3D、SegPoint、Reason3D。
- **扩展实验**：在ReferIt3D数据集（包含Sr3D和Nr3D）上也进行了3D-RES任务评估（附录表6），进一步验证泛化性。

## 4. 资源与算力

- **硬件环境**：单张 NVIDIA Tesla A100 GPU。
- **训练超参数**：初始学习率0.0001，采用学习率衰减（epochs 26, 34, 46，衰减率0.5），batch size 32，最大句子长度80，默认6轮迭代（TLM轮数）。
- **推理时间**：RG-SAN为295ms，仅比最先进的3D-STMN（283ms）慢12ms，但远快于其他两阶段方法（如TGNN 27097ms，InstanceRefer 1181ms）。
- **注意**：论文未明确给出训练总时长，但可推断在单卡A100上可在合理时间内完成。

## 5. 实验数量与充分性

- **实验组数**：主实验（表1）对比了10+种方法；消融实验包括5个表格（表2-5）+ 附录7-9，覆盖：
  - TLM模块的初始化方式（表2）
  - 位置编码策略（表3）
  - 弱监督目标选择策略（表4）
  - 位置损失权重（表5）
  - 迭代轮数（表7）
  - 文本编码器选择（表8）
  - 视觉骨干网络（表9）
- **充分性与公平性**：消融实验设计合理，控制了变量；对比方法使用官方或复现结果（标注†和*），确保公平。另外在ReferIt3D上额外验证，增强了结论的泛化性。实验充分展示了各组件贡献，并分析了在多干扰场景下的提升。

## 6. 论文的主要结论与发现

- RG-SAN在ScanRefer上大幅超越之前最佳的单阶段模型3D-STMN：**mIoU提升5.1个点**（从39.5%到44.6%），**Acc@0.25提升7.1个点**（从54.6%到61.7%）。
- 性能提升主要来源于“Multiple”场景（同类干扰）：mIoU提升6.3个点（从31.1%到37.4%），表明空间建模显著增强了辨别能力。
- 在ReferIt3D上同样取得优势：Sr3D上Acc@0.50提升5.3点，mIoU提升5.2点；Nr3D上Acc@0.50提升2.9点。
- 推理速度接近最先进模型，仅增加12ms，实用性高。
- 消融实验证明：文本驱动初始化（TI）、相对位置编码（Table-based RPE）、规则引导目标选择（RTS）以及适当的位置损失权重（0.5）是关键设计。
- 可视化显示RG-SAN不仅能正确分割目标，还能准确识别描述中其他名词（如“coat”“couches”），甚至能处理复数名词，体现了强大的空间语义对齐能力。

## 7. 优点

- **创新性**：首次在3D-RES中利用**仅目标实例的空间信息实现弱监督**，通过依赖树规则自动确定核心实例，避免了额外标注其他实体的需求。
- **方法清晰有效**：TLM将文本实体映射到3D空间并迭代细化，RWS提供精准的弱监督信号，两者协同显著提升空间推理能力。
- **实验全面且结果显著**：在多个数据集和大量对比方法上取得SOTA，消融实验严谨，可视化直观佐证了空间建模效果。
- **效率出色**：与纯端到端模型相比，推理时间几乎无增加，具备实用潜力。
- **开放贡献**：代码已公开，便于复现和后续研究。

## 8. 不足与局限

- **复数名词定位困难**：论文指出，当前方法使用单个点代表实体位置，难以准确处理描述中的复数名词（如“couches”），需要探索多中心点表示。
- **对受损点云鲁棒性不足**：在点云数据出现缺失或损坏时，模型性能可能下降，未来需增强数据增强或鲁棒训练。
- **数据集规模有限**：主要实验仅在ScanRefer（800场景）和ReferIt3D上进行，未在更大规模或复杂场景（如室内外混合数据集）验证，泛化性有待进一步检验。
- **依赖预训练模型**：视觉骨干（Sparse 3D U-Net）和语言编码器（MPNet）的性能可能成为瓶颈，若使用更强大的基础模型（如3D-LLM）或许可进一步提升。
- **弱监督局限性**：虽然RWS避免了额外标注，但依赖树规则可能无法处理某些复杂句式（如嵌套从句），附录E显示LLAMA2 70B在某些情况下比规则更准确，说明规则仍有改进空间。
- **未探讨跨领域应用**：论文未讨论在自动驾驶、机器人等实际部署场景中的潜在偏差或安全风险，附录F仅简要提及伦理声明。

（完）
