---
title: "UniDSeg: Unified Cross-Domain 3D Semantic Segmentation via Visual Foundation Models Prior"
title_zh: UniDSeg：基于视觉基础模型先验的统一跨域3D语义分割
authors: "Yao Wu, Mingwei Xing, Yachao Zhang, Xiaotong Luo, Yuan Xie, Yanyun Qu"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=dDDc3iNZA7"
tags: ["query:ris"]
score: 5.0
evidence: 利用视觉基础模型提升3D语义分割的跨域泛化能力
tldr: 针对3D语义分割的域适应和泛化任务，提出UniDSeg方法。通过引入预训练的视觉基础模型（如DINOv2）作为先验，设计层级特征融合策略，使编码器获得更强的通用表示。实验表明该方法在多个跨域设置下均优于专门设计的域适应/泛化方法，验证了基础模型在3D分割中的有效性。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-dddc3inza7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 819, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dddc3inza7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1421, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dddc3inza7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1352, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dddc3inza7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 609, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dddc3inza7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1314, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dddc3inza7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1304, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dddc3inza7/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1399, \"height\": 1472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dddc3inza7/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1397, \"height\": 1462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dddc3inza7/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1411, \"height\": 919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dddc3inza7/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1412, \"height\": 944, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 701, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1377, \"height\": 663, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 779, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 465, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 407, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1081, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 543, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1301, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1444, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1439, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dddc3inza7/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 723, \"height\": 201, \"label\": \"Table\"}]"
motivation: 3D语义分割跨域时编码器泛化能力不足，现有方法难以同时适应和泛化。
method: 利用现成视觉基础模型提取通用特征，通过层级融合增强编码器的域不变性。
result: 在多个域适应和域泛化基准上取得最佳性能，尤其在零样本跨域场景提升显著。
conclusion: 视觉基础模型的先验知识可显著提升3D分割的跨域能力。
---

## Abstract
3D semantic segmentation using an adapting model trained from a source domain with or without accessing unlabeled target-domain data is the fundamental task in computer vision, containing domain adaptation and domain generalization.
The essence of simultaneously solving cross-domain tasks is to enhance the generalizability of the encoder.
In light of this, we propose a groundbreaking universal method with the help of off-the-shelf Visual Foundation Models (VFMs) to boost the adaptability and generalizability of cross-domain 3D semantic segmentation, dubbed $\textbf{UniDSeg}$.
Our method explores the VFMs prior and how to harness them, aiming to inherit the recognition ability of VFMs.
Specifically, this method introduces layer-wise learnable blocks to the VFMs, which hinges on alternately learning two representations during training: (i) Learning visual prompt. The 3D-to-2D transitional prior and task-shared knowledge is captured from the prompt space, and then (ii) Learning deep query. Spatial Tunability is constructed to the representation of distinct instances driven by prompts in the query space.
Integrating these representations into a cross-modal learning framework, UniDSeg efficiently mitigates the domain gap between 2D and 3D modalities, achieving unified cross-domain 3D semantic segmentation.
Extensive experiments demonstrate the effectiveness of our method across widely recognized tasks and datasets, all achieving superior performance over state-of-the-art methods. Remarkably, UniDSeg achieves 57.5\%/54.4\% mIoU on ``A2D2/sKITTI'' for domain adaptive/generalized tasks. Code is available at https://github.com/Barcaaaa/UniDSeg.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：3D语义分割在自动驾驶等领域至关重要，但标注大规模3D数据成本高昂。跨域场景（如从合成数据到真实数据、不同城市布局）中，模型泛化能力不足是核心瓶颈。现有方法分别针对域适应（DA，访问无标签目标域）和域泛化（DG，完全未见目标域），缺乏统一框架。
- **核心问题**：如何同时提升编码器在DA和DG任务中的泛化能力，并利用2D视觉基础模型（VFMs）的强先验知识来弥补3D预训练数据的稀缺。
- **整体含义**：提出UniDSeg，利用冻结的VFMs（如CLIP/SAM）引入轻量级可学习模块（模态过渡提示MTP和可学习空间可调性LST），以参数高效方式继承VFMs的开放世界识别能力，实现跨域3D语义分割的统一解决方案。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：冻结VFMs的预训练参数，仅训练逐层插入的可学习模块，在不破坏原有知识的前提下适应跨域3D任务。通过3D到2D的过渡提示（MTP）提取深度先验和任务共享知识，通过可学习深度查询（LST）为不同实例构建空间可调性，并采用跨模态学习（2D↔3D）促进域不变表示。
- **关键技术细节**：
  - **VFM编码器**：基于ViT（如CLIP:ViT-B/L），冻结所有层参数，每层插入MTP（在输入前）和LST（在输出后）。
    - **MTP**：接收图像和稀疏深度（通过LiDAR投影），利用共享MLP和逐层专属MLP生成逐层提示，添加到patch嵌入中。
    - **LST**：使用可学习令牌（长度K=100，低秩分解）通过注意力机制与当前层输出交互，生成可调表示，再通过下投影/上投影调整。
  - **跨模态学习**：2D和3D分支分别编码，通过KL散度相互学习（源域和目标域），损失函数包括分割损失和跨模态KL损失。
  - **训练策略**：仅在源域有监督，目标域无标签（DA）或完全不可见（DG）。DG不使用目标域数据，DA使用无标签目标域数据。
- **公式/算法流程**（文字说明）：
  - 输入图像和稀疏深度 → 提取patch嵌入 → 每层ViT前加入MTP提示 → 经过ViT层 → 经过LST查询调整 → 最终输出2D特征。
  - 3D点云经SparseConvNet编码，与2D特征通过KL散度进行互学习，联合优化分割损失和跨模态损失。

### 3. 实验设计：数据集、场景、benchmark与对比方法

- **数据集**：使用nuScenes（美国/新加坡、昼/夜）、SemanticKITTI（sKITTI）、A2D2、VirtualKITTI（vKITTI）。共构建5个场景：
  1. nuScenes: USA/Sing.（域适应 & 泛化）
  2. nuScenes: Day/Night
  3. nuScenes: Sing./USA
  4. vKITTI → sKITTI（合成→真实）
  5. A2D2 → sKITTI（不同传感器）
- **Benchmark**：多模态DA3SS和DG3SS标准评测，评估指标为mIoU（%），分别报告2D、3D及集成结果（xM）。
- **对比方法**：
  - DA：Source-only、logCORAL、MinEnt、BDL、xMUDA、AUDA、DsCML、Dual-Cross、SSE、BFtD、MM2D3D、VFMSeg。
  - DG：xMUDA、MM2D3D。
  - 额外对比了全微调、冻结VFMs等训练策略，并验证了SAM作为2D骨干的效果。
- **消融实验**：分析了MTP、LST各自贡献；可学习令牌长度K的影响；稀疏深度作为提示vs深度编码；不同2D/3D骨干（CLIP vs SAM、SparseConvNet vs MinkowskiNet）；源自由域适应（SFDA）扩展等。

### 4. 资源与算力

- 论文明确说明：所有实验在**单个NVIDIA RTX 3090（24GB RAM）**上完成。训练迭代次数依场景不同：60k（USA/Sing.）、100k（Day/Night、A2D2/sKITTI等）、30k（vKITTI/sKITTI）。未提及使用的GPU数量（推测单卡）及总训练时间（小时）。

### 5. 实验数量与充分性

- **实验数量**：主表（Tab.1）涵盖5个场景的DA和DG共10个设置；消融实验包括8张表格（Tab.2-Tab.7），涉及训练策略、组件贡献、令牌长度、不同骨干、深度角色、SFDA扩展等；附录还有全监督（SemanticKITTI）和伪标签再训练等额外实验。
- **充分性与公平性**：
  - 对比了足够多的SOTA方法（12+个），涵盖了主流多模态和单模态方法。
  - 消融实验系统性强，验证了每个关键设计的必要性。
  - 所有方法均使用相同3D骨干（SparseConvNet）和2D解码器（SemanticFPN），确保对比公平。
  - 然而，未报告多次运行的统计误差（如标准差），可能影响可重复性。

### 6. 论文的主要结论与发现

- **VFMs先验的有效性**：利用冻结的VFMs（CLIP/SAM）并仅训练极少量参数（约2%），即可显著提升跨域3D语义分割性能，甚至超过全微调方法。
- **统一框架成功**：UniDSeg在DA和DG任务上均优于现有方法，在A2D2→sKITTI场景DA达57.5% mIoU，DG达54.4%，大幅领先。
- **组件贡献**：MTP和LST互补，共同提升泛化；可学习令牌长度100为最佳折中；稀疏深度作为提示比深度编码更好。
- **扩展性**：UniDSeg可轻松扩展到全监督3D分割、源自由域适应等任务，且性能优于专用方法。

### 7. 优点

- **创新性**：首次将提示调谐（prompt tuning）概念引入跨域3D语义分割，设计了专用的3D→2D过渡提示和空间可调性模块。
- **参数高效**：仅需微调约1-2%的编码器参数，即可继承大模型先验，避免灾难性遗忘。
- **统一性**：一个框架同时适用于DA和DG，无需修改结构，降低了工程复杂度。
- **广泛验证**：在多个真实/合成、不同传感器、不同天气/光照的复杂场景下均取得SOTA，鲁棒性强。
- **可扩展性**：可无缝迁移到其他3D分割子任务（全监督、SFDA），显示了通用价值。

### 8. 不足与局限

- **实验覆盖局限**：未在更多极端天气（强降雨、雪）场景测试，也未涉及多传感器模态缺失的情况。
- **统计显著性缺失**：未提供多次运行的标准差或置信区间，结果可能存在偶然性。
- **伪标签再利用效果有限**：作者指出，在DA中利用伪标签再训练时，2D预测提升微乎其微，可能是由于可学习参数容量受限，无法承载更多目标域信息。
- **对标准3D分割提升不大**：在全监督SemanticKITTI上，UniDSeg相比2DPASS仅有微小提升（0.4-0.9% mIoU），表明VFMs先验在无域移场景中优势不明显。
- **计算资源**：所有实验仅使用单卡RTX 3090，但未报告训练耗时，大规模实际部署时效率可能受限。
- **应用限制**：依赖2D-3D配对数据（投影），若缺乏多模态输入（如仅LiDAR）则无法直接使用UniDSeg。

（完）
