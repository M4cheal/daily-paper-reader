---
title: Dual Prototype Evolving for Test-Time Generalization of Vision-Language Models
title_zh: 面向视觉语言模型测试时泛化的双原型演进
authors: "Ce Zhang, Simon Stepputtis, Katia P. Sycara, Yaqi Xie"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=jsgYYXaSiS"
tags: ["query:tta"]
score: 9.0
evidence: 基于双原型演进的视觉语言模型测试时自适应
tldr: DPE针对视觉语言模型在测试时仅从单模态适应且缺乏知识积累的问题，提出双原型演进方法。创建并演进两组原型，分别捕获视觉和语言模态的特征分布，在适应过程中有效积累多模态任务知识。实验表明，该方法在多种分布漂移下显著提升了VLMs的泛化能力。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-jsgyyxasis/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jsgyyxasis/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jsgyyxasis/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 725, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jsgyyxasis/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 475, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 904, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 754, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 802, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 800, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 730, \"height\": 124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 894, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 879, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1440, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 752, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1410, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 652, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1427, \"height\": 654, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jsgyyxasis/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1279, \"height\": 791, \"label\": \"Table\"}]"
motivation: 现有视觉语言模型测试时自适应方法仅关注单模态适应，无法积累多模态知识。
method: 提出双原型演进框架，分别维护和更新视觉和语言模态的原型。
result: 在多个基准数据集上，DPE显著提升了模型在分布漂移下的性能。
conclusion: 双原型演进行效促进了视觉语言模型的测试时多模态知识积累。
---

## Abstract
Test-time adaptation, which enables models to generalize to diverse data with unlabeled test samples, holds significant value in real-world scenarios. Recently, researchers have applied this setting to advanced pre-trained vision-language models (VLMs), developing approaches such as test-time prompt tuning to further extend their practical applicability. However, these methods typically focus solely on adapting VLMs from a single modality and fail to accumulate task-specific knowledge as more samples are processed. To address this, we introduce Dual Prototype Evolving (DPE), a novel test-time adaptation approach for VLMs that effectively accumulates task-specific knowledge from multi-modalities. Specifically, we create and evolve two sets of prototypes—textual and visual—to progressively capture more accurate multi-modal representations for target classes during test time. Moreover, to promote consistent multi-modal representations, we introduce and optimize learnable residuals for each test sample to align the prototypes from both modalities. Extensive experimental results on 15 benchmark datasets demonstrate that our proposed DPE consistently outperforms previous state-of-the-art methods while also exhibiting competitive computational efficiency.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：视觉语言模型（VLMs，如CLIP）经过大规模预训练后具备强大的零样本能力，但在实际部署中常遇到训练数据（源域）与测试数据（目标域）之间的分布偏移，导致性能显著下降。传统的测试时适应方法（如TTA）可利用无标注的目标域样本流来调整模型，然而现有的针对VLMs的测试时适应方法（如TPT、TDA）存在两个关键不足：
  1. **单模态适应**：仅从文本模态（如提示调优）或视觉模态（如特征缓存）进行适应，未能充分利用VLMs的多模态表征能力。
  2. **缺乏知识累积**：像TPT那样逐样本独立处理，无法从历史测试样本中提取并积累任务特定知识。
- **论文目标**：提出一种新型测试时适应方法**Dual Prototype Evolving (DPE)**，通过同时维护并演进文本和视觉两类原型，实现多模态任务知识的有效累积，从而提升VLMs在分布偏移下的泛化能力。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：在测试过程中动态创建并更新两类**类原型**（textual prototypes 和 visual prototypes），分别表征目标类别的文本和视觉特征分布。随着测试样本的流入，这些原型逐步演化，捕捉更准确的多模态表示。此外，针对每个测试样本，引入可学习的残差参数对原型进行微调，并利用对齐损失保持多模态一致性。

- **关键技术细节**：
  - **文本原型演进**：
    - 初始化：对每个类别使用多个提示模板（S个），计算嵌入均值作为初始文本原型 \( t_c \)。
    - 在线更新：采用累积平均策略，仅对置信度较高（自熵小于阈值 \( \tau_t \)）的样本更新原型。更新公式为 \( t \leftarrow \frac{(k-1)t + t^*}{\|(k-1)t + t^*\|} \)，其中 \( t^* \) 是经残差优化后的文本原型，\( k \) 为已更新样本计数。
  - **视觉原型演进**：
    - 为每个类别维护一个优先队列（最大容量 \( M \)），按自熵升序存储历史图像特征。
    - 使用测试样本的伪标签和自熵，将高置信度特征加入队列，若队列已满则替换最高熵（最不确信）的特征。
    - 队列中所有特征的平均值作为视觉原型 \( v_c \)。
  - **原型推理**：
    - 最终预测融合文本和视觉原型的相似度：\( f_v^\top t_c + A(f_v^\top v_c) \)，其中 \( A(x) = \alpha \exp(-\beta(1-x)) \) 是亲和函数。
  - **原型残差学习**：
    - 针对每个测试样本，初始化两组可学习残差 \( \hat{t}, \hat{v} \)（初始为0），按式(6)更新原型：\( t_c \leftarrow t_c + \hat{t}_c \) 并归一化，视觉同理。
    - 优化目标包含两部分：
      1. **自熵最小化损失** \( \mathcal{L}_{\text{aug}} \)：对多个增强视图的预测熵取平均，筛选低熵样本。
      2. **对齐损失** \( \mathcal{L}_{\text{align}} \)：基于InfoNCE损失，拉近同类别文本与视觉原型、推远异类原型。
    - 总损失 \( \mathcal{L} = \mathcal{L}_{\text{aug}} + \lambda \mathcal{L}_{\text{align}} \)，使用AdamW优化器单步更新。
    - 更新后的原型 \( t^*, v^* \) 用于演进在线文本原型和更新优先队列，作为下一个样本的初始化。

### 3. 实验设计：数据集/场景、基准、对比方法

- **数据集与场景**：
  - **自然分布偏移场景**：ImageNet及其4个变体（ImageNet-A、ImageNet-V2、ImageNet-R、ImageNet-Sketch）。
  - **跨数据集泛化场景**：10个细粒度识别数据集（FGVCAircraft、Caltech101、StanfordCars、DTD、EuroSAT、Flowers102、Food101、OxfordPets、SUN397、UCF101）。
  - **总计15个基准数据集**。
- **对比方法**：
  - 零样本CLIP（简单提示与集成提示）
  - 训练时适应方法：CoOp（有标注样本）
  - 测试时适应方法：TPT、DiffTPT、TDA、TPS、DMN-ZS
- **评估指标**：Top-1准确率，每个实验重复3次（不同随机种子）取平均值。

### 4. 资源与算力

- **硬件**：单张48GB NVIDIA RTX 6000 Ada GPU。
- **耗时对比**（ImageNet 5万样本）：
  - CLIP零样本：9分钟
  - TPT：9小时15分钟
  - DiffTPT：>20小时
  - TDA：1小时5分钟
  - TPS：55分钟
  - **DPE（本方法）**：1小时50分钟（约TPT的1/5，DiffTPT的1/10）
- **单样本推理时间**：
  - 零样本CLIP: 10.1ms
  - DPE（含残差学习）：64.7ms
  - DPE（含视觉原型演进）：132.1ms

### 5. 实验数量与充分性

- **实验数量**：涵盖15个数据集、两个评估场景、两个骨干网络（ResNet-50和ViT-B/16），并额外在OpenCLIP ViT-L/14上验证。消融实验包括：
  - 不同文本原型更新规则（无更新、全更新、指数平均、累积平均）
  - 超参数敏感分析（阈值\( \tau_t \)、队列大小M、亲和函数\( \alpha, \beta \)、对齐损失权重\( \lambda \)）
  - 不同可学习模块的影响（文本/视觉残差单独与联合）
  - 不同更新步数的影响
  - 各组件（VPE、TPE、PRL）的贡献分解
  - 两个损失项（自熵、对齐）的单独与联合效果
- **充分性与公平性**：实验设计系统，对比方法均引用原文结果，超参数通过敏感分析选择最优值；多次随机种子报告均值和标准差，结果可靠。但DiffTPT原文只用了1000子集，本实验也遵循，可能引入一定偏差，但整体实验覆盖面广、分析深入。

### 6. 论文的主要结论与发现

- **性能优势**：DPE在几乎所有数据集上超越现有SOTA方法，在自然分布偏移场景中平均提升3.55%（ResNet-50）和3.49%（ViT-B/16）相对于TPT；在跨数据集泛化场景中平均提升4.30%相对于TPT（ViT-B/16）。
- **知识累积有效**：随着测试样本增多，视觉原型（经由优先队列）的特征更聚类，性能持续提升，验证了累积策略的有效性。
- **多模态协同**：同时利用文本和视觉原型比单模态方法带来显著提升；对齐损失进一步改善多模态一致性。
- **效率竞争力**：相比TPT和DiffTPT，DPE推理速度快5-10倍，同时性能更优；虽然慢于TDA/TPS，但性能增益更大。

### 7. 优点

- **创新性**：首次在测试时适应中同时演进文本和视觉两类原型，实现多模态知识长期累积。
- **高效设计**：原型残差学习直接在嵌入空间优化，无需回传文本编码器梯度，大幅降低计算开销。
- **鲁棒性**：通过熵阈值筛选高质量样本用于更新原型，避免低置信样本污染；对齐损失防止过自信。
- **广泛验证**：在15个数据集、多个骨干、多种分布偏移场景下全面评估，消融实验精细，充分证明各组件贡献。

### 8. 不足与局限

- **仍需梯度反向传播**：虽然残差学习无需更新文本编码器，但仍需对原型参数求导，计算复杂度高于零样本CLIP；在实时性要求极高的场景可能受限。
- **额外内存开销**：维护每个类别的优先队列需存储图像特征（容量M），增加了推理时的显存占用。
- **超参数敏感**：队列大小M、阈值\( \tau_t \)、亲和函数参数\( \alpha, \beta \)等需根据数据集调优，文中虽提供了敏感分析但未见自动适应机制。
- **实验局限**：DiffTPT的比较基于其原文的子集（1000样本），可能不完全公平；所有实验仅在单一GPU上运行，未在多卡或分布式环境下验证。
- **应用边界**：主要针对分类任务，未涉及分割、检测等其他视觉任务；方法依赖CLIP的预训练能力，对更小模型或更弱VLM的效果未知。

（完）
