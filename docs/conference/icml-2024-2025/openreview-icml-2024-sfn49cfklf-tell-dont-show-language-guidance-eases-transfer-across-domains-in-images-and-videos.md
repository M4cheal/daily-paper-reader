---
title: "Tell, Don't Show: Language Guidance Eases Transfer Across Domains in Images and Videos"
title_zh: "Tell, Don't Show: 语言引导缓解图像和视频的跨域迁移"
authors: "Tarun Kalluri, Bodhisattwa Prasad Majumder, Manmohan Chandraker"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=sFN49CfklF"
tags: ["query:ris"]
score: 7.0
evidence: 语言引导的域适应方法可迁移至指代分割泛化
tldr: 该论文提出LaGTran框架，利用文本监督引导判别性知识从标注源域迁移到未标注目标域，有效应对像素空间难以处理的域偏移。其核心思想（利用语言模态的丰富语义进行跨域泛化）可直接应用于指代分割的泛化场景，为解决指代分割中的域偏移问题提供了一种可迁移的范式。实验表明语言引导在多种跨域迁移任务中显著优于纯视觉方法。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-sfn49cfklf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 828, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-sfn49cfklf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 842, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-sfn49cfklf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 837, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-sfn49cfklf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 853, \"height\": 282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-sfn49cfklf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 831, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-sfn49cfklf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 804, \"height\": 819, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-sfn49cfklf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 757, \"height\": 494, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-sfn49cfklf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 885, \"height\": 537, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-sfn49cfklf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1495, \"height\": 673, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-sfn49cfklf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 836, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-sfn49cfklf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 787, \"height\": 522, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-sfn49cfklf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 856, \"height\": 186, \"label\": \"Table\"}]"
motivation: 现有无监督域适应方法仅操作像素空间，难以处理复杂域偏移，而文本模态具有更丰富的语义信息。
method: 利用源域训练文本分类器，对目标域文本描述生成预测，作为对应图像的伪标签，从而将语言知识迁移到视觉域。
result: 在多个图像和视频域适应基准上显著提升了目标域分类准确率，验证了语言引导的有效性。
conclusion: 语言引导是一种强大的跨域迁移机制，为指代分割等需要语言理解的视觉任务提供了新思路。
---

## Abstract
We introduce LaGTran, a novel framework that utilizes text supervision to guide robust transfer of discriminative knowledge from labeled source to unlabeled target data with domain gaps. While unsupervised adaptation methods have been established to address this problem, they show limitations in handling challenging domain shifts due to their exclusive operation within the pixel-space. Motivated by our observation that semantically richer text modality has more favorable transfer properties, we devise a transfer mechanism to use a source-trained text-classifier to generate predictions on the target text descriptions, and utilize these predictions as supervision for the corresponding images. Our approach driven by language guidance is surprisingly easy and simple, yet significantly outperforms all prior approaches on challenging datasets like GeoNet and DomainNet, validating its extreme effectiveness. To further extend the scope of our study beyond images, we introduce a new benchmark called Ego2Exo to study ego-exo transfer in videos and find that our language-aided approach LaGTran yields significant gains in this highly challenging and non-trivial transfer setting. Code, models, and proposed datasets are publicly available at https://tarun005.github.io/lagtran/.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：无监督域适应（UDA）方法在应对复杂域偏移（如地理差异、视角转换）时，因仅在像素空间操作而性能受限。论文提出利用**文本模态**来缓解跨域迁移困难，因为文本描述具有更丰富的语义信息且域差距更小。
- **整体含义**：提出一种简单且高效的框架 **LaGTran**，利用源域和目标域中易获取（或易生成）的文本描述，将语言知识迁移至视觉任务，显著提升目标域分类性能，并拓展至视频跨视角迁移。

### 2. 论文提出的方法论

- **核心思想**：通过训练源域文本分类器，对目标域文本描述生成伪标签，再以这些伪标签监督对应的目标域图像/视频，实现跨模态知识迁移。
- **关键技术细节**：
  - 使用预训练 **DistilBERT** 作为文本分类器 `B`，在源域文本-标签对 `(c_i^s, y_i^s)` 上微调（公式1：交叉熵损失）。
  - 冻结 `B`，对目标域文本 `c_i^t` 预测伪标签 `ŷ_i^t`（公式2：arg max）。
  - 构建伪标签目标数据集 `Ď_t = {(x_i^t, ŷ_i^t)}`，与源域数据联合训练图像/视频分类器 `G`（公式3：联合交叉熵损失）。
- **算法流程**：① 源域文本训练 BERT 分类器 → ② 目标域文本推理得到伪标签 → ③ 联合源域图像和目标域伪标签图像训练视觉分类器（推理时仅用视觉分支，无额外开销）。
- **开放世界扩展**：引入阈值 `τ=0.75` 检测无关类样本，将不属于源类别的目标样本标记为“异常类”（公式4），实现通用域适应。

### 3. 实验设计：数据集、benchmark、对比方法

- **图像分类**：
  - **GeoNet**（地理域偏移，600/205类）：对比 UDA 方法（CDAN、MemSAC、PMTrans 等）、零样本方法（CLIP、TextMatch、nGramMatch）。
  - **DomainNet**（345类，4域：真实、剪贴画、素描、绘画）：对比 MCD、MDD、CDTrans、PMTrans 等及零样本基线。
- **开放世界域适应**：
  - **GeoUniDA**（62共享类 + 138私有类）：对比 UniDA、DANCE、OVANet 等。
- **视频跨视角迁移**：
  - **Ego2Exo**（新基准，24类动作，来自 Ego-Exo4D 烹饪视频）：对比视频 UDA 方法（TA3N、TransVAE）、视频零样本方法（EgoVLP、LaVILA）及文本匹配基线。
- **评估指标**：Top-1 准确率（图像/视频）、H-score（开放世界）。

### 4. 资源与算力

- **未明确说明 GPU 型号、数量及总训练时长**。文中仅提及训练配置：
  - 图像分类器：ViT-B/Swin-B，90k 迭代，SGD 优化器，学习率 3e-4，batch size 64/域。
  - 文本分类器：DistilBERT，5 轮，AdamW 学习率 5e-5。
  - 视频分类器：Omnivore-base 特征 + 2层 MLP。
- 无具体算力统计，但方法复杂度低（训练时间应远低于传统 UDA 方法）。

### 5. 实验数量与充分性

- **实验数量**：覆盖 2 个图像数据集（含 8 种域对）、1 个开放世界基准、1 个视频基准，共约 15+ 组主实验。
- **消融实验**：
  - 文本监督比例（10%~100%）对精度的影响（图5）。
  - 不同文本分类器骨干（DistilBERT、T5、GPT2、CLIP-T）对比（表5）。
  - 联合训练 vs 仅目标训练（源域重要性分析）。
  - 文本 vs 图像特征最近邻可视化（图6）。
- **充分性与公平性**：
  - 对比方法均为近年 SOTA UDA 和零样本方法，且使用相同骨干（ViT-B / Swin-B）。
  - 视频任务中特征提取器（Omnivore）及数据划分一致。
  - 开放世界设置中采相同评估协议（H-score）。
- **结论**：实验设计全面、对比公平，消融验证了各组件贡献。

### 6. 论文的主要结论与发现

- **文本模态跨域迁移能力显著优于图像**：GeoNet 上文本分类器域下降仅 9.5%，而图像分类器下降 17.1%；t-SNE 可视化显示文本特征域对齐更好。
- **LaGTran 大幅超越所有基线**：
  - GeoNet 平均精度 60.24%（比最佳 UDA PMTrans 高 +10%，比零样本 CLIP 高 +10%）。
  - DomainNet 平均精度 72.41%（比 PMTrans 高 +2.8%）。
  - 开放世界 H-score 61.16%（比 OVANet 高 +13.9%）。
  - Ego2Exo 平均 21.55%（比 TransVAE 高 +3.85%）。
- **数据高效**：仅需 20%（GeoNet）或 50%（DomainNet）的文本监督即可超越图像 UDA 方法。
- **简单扩展可处理开放世界和视频**：无需修改核心流程，仅调整伪标签生成规则。

### 7. 优点

1. **方法简洁有效**：仅需训练文本分类器 + 联合训练视觉分类器，无复杂对抗/对齐模块，易于复现。
2. **跨模态迁移**：利用语言模态的丰富语义，自然缓解域偏移，且推理时无额外开销（仅需图像）。
3. **数据易获取**：文本描述可通过元数据或现成 caption 模型（BLIP-2）获得，无需人工标注。
4. **泛化性强**：在图像、视频、开放世界多个场景均显著优于纯视觉 UDA 方法。
5. **可扩展性**：可轻松适配开放世界（异常检测）和不同骨干网络。
6. **开源**：代码、模型、数据集均公开。

### 8. 不足与局限

1. **依赖外部 VLM 生成文本**：在缺乏元数据时需用 BLIP-2 等模型，这些模型可能失效或产生非判别性描述，限制应用。
2. **文本模态仍有域差距**：虽然比图像小，但文本分类器在目标域伪标签仍有错误，未引入文本域适应机制。
3. **未探讨多语言/低资源场景**：GeoNet 中文本包含多语言标签，但未专门分析对非英语区域的鲁棒性。
4. **视频基准规模有限**：Ego2Exo 仅 24 类、约 9000 段视频，且动作粒度粗，可能不足以检验复杂场景。
5. **计算资源未报告**：缺少 GPU 型号、数量及训练时间，影响可复现性评估。
6. **消融不够深入**：例如未分析伪标签质量（错误积累）、阈值 τ 的敏感性、不同 caption 模型的影响等。

（完）
