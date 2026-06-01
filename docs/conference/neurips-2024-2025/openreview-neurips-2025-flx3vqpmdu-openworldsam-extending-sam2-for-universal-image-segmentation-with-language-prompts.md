---
title: "OpenWorldSAM: Extending SAM2 for Universal Image Segmentation with Language Prompts"
title_zh: OpenWorldSAM：将SAM2扩展为通用语言提示图像分割模型
authors: "Shiting Xiao, Rishabh Kabra, Yuhang Li, Donghyun Lee, Joao Carreira, Priyadarshini Panda"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=fLx3vQPmDu"
tags: ["query:ris"]
score: 9.0
evidence: 使用语言提示驱动SAM2进行分割，直接实现类指代分割任务
tldr: 当前基于语言提示的分割模型在处理开放场景和未见类别时存在泛化瓶颈。本文提出OpenWorldSAM框架，通过冻结SAM2并集成轻量视觉语言模型提取多模态嵌入，支持类别级和句子级语言提示。该框架保持高效率，无需重新训练，在多个基准上达到开放词汇分割最优性能，直接服务于指代图像分割需求。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-flx3vqpmdu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1312, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flx3vqpmdu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 632, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flx3vqpmdu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1218, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flx3vqpmdu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1329, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flx3vqpmdu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1432, \"height\": 808, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flx3vqpmdu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1384, \"height\": 282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flx3vqpmdu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1019, \"height\": 780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flx3vqpmdu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 2150, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flx3vqpmdu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1167, \"height\": 415, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1246, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1454, \"height\": 560, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1453, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1211, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1177, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1456, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1212, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1428, \"height\": 1009, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 934, \"height\": 2186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 886, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1451, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1025, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flx3vqpmdu/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1025, \"height\": 459, \"label\": \"Table\"}]"
motivation: 现有SAM2无法直接处理开放词汇语言提示，缺乏对多样和未见类别的泛化能力。
method: 冻结SAM2，使用轻量VLM提取多模态嵌入作为提示，实现统一语言驱动的分割。
result: 在多个开放词汇分割数据集上超越现有方法，支持多种语言提示形式。
conclusion: 该方法为语言引导的通用分割提供了高效可扩展的框架，可直接用于指代分割任务。
---

## Abstract
The ability to segment objects based on open-ended language prompts remains a critical challenge, requiring models to ground textual semantics into precise spatial masks while handling diverse and unseen categories. We present OpenWorldSAM, a framework that extends the prompt-driven Segment Anything Model v2 (SAM2) to open-vocabulary scenarios by integrating multi-modal embeddings extracted from a lightweight vision-language model (VLM). Our approach is guided by four key principles: i) Unified prompting: OpenWorldSAM supports a diverse range of prompts, including category-level and sentence-level language descriptions, providing a flexible interface for various segmentation tasks. ii) Efficiency: By freezing the pre-trained components of SAM2 and the VLM, we train only 4.5 million parameters on the COCO-stuff dataset, achieving remarkable resource efficiency. iii) Instance Awareness: We enhance the model's spatial understanding through novel positional tie-breaker embeddings and cross-attention layers, enabling effective segmentation of multiple instances. iv) Generalization: OpenWorldSAM exhibits strong zero-shot capabilities, generalizing well on unseen categories and an open vocabulary of concepts without additional training. Extensive experiments demonstrate that OpenWorldSAM achieves state-of-the-art performance in open-vocabulary semantic, instance, and panoptic segmentation across multiple benchmarks. Code is available at https://github.com/GinnyXiao/OpenWorldSAM.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有分割模型（如 SAM2）局限于封闭词汇集，无法理解开放式的、多样化的语言提示（如类别名、指代表达），且难以处理单个语言提示对应多个实例的歧义性。
- **背景**：传统方法依赖两阶段流水线（检测 + 分类）或昂贵的大型语言模型，资源开销大，且无法同时支持语义、实例、全景和指代分割任务。
- **整体含义**：论文旨在构建一个统一的、轻量级的开放词汇分割框架，使得模型能够根据任意文本提示（名词或句子）分割任意物体，同时保持高效、零样本泛化和多实例感知能力。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：冻结 SAM2 和视觉语言模型（VLM）的预训练权重，仅训练一个轻量语言适配器（约 4.5M 参数），将多模态语义注入 SAM2 的掩码解码器。
- **关键技术细节**：
  - **多模态编码器**：使用 BEiT-3（早期融合）联合编码图像和文本，输出融合的语义向量 \( p_{lang} \in \mathbb{R}^{1024} \)。
  - **MLP 投影器**：将 1024 维向量投影到 SAM2 的 256 维提示空间，得到 \( u \)。
  - **位置 tie‑breaker 机制**：引入 \( K=20 \) 个可学习的偏置向量 \( t_i \)，与 \( u \) 相加生成多个查询 \( q_i = u + t_i \)，用于分割同一类别的不同实例。
  - **软提示交叉注意力 Transformer**：3 层 Transformer，包含自注意力和交叉注意力（与 SAM2 的 64×64 特征图交互），将语言查询锚定到视觉特征。
  - **掩码解码**：将精炼的查询输入 SAM2 的提示编码器和掩码解码器，输出 \( K \) 个掩码及置信度；通过匈牙利匹配和 focal loss 训练。
  - **推理后处理**：根据任务（语义/实例/全景）合并或过滤掩码；可选的两阶段推理通过将掩码作为视觉提示再次送入 SAM2 以细化轮廓。

### 3. 实验设计：数据集、基准、对比方法

- **训练数据集**：COCO2017-Stuff（104k 图像），含 132 个 thing/stuff 类别。
- **零样本评估数据集**：
  - 语义/实例/全景：ADE20K-150/857、PASCAL VOC-20、PASCAL Context-59/459、ScanNet-20/40、SUN-RGBD-37。
- **指代分割微调数据集**：RefCOCOg UMD 训练/验证集。
- **对比方法**：X‑Decoder, APE, OVSeg, MaskCLIP, OpenSeeD, SEEM, LISA, GLaMM, EVF-SAM 等。
- **评估指标**：语义：mIoU；实例：mAP；全景：PQ；指代：cIoU。
- **评价协议**：主流全局匹配协议（Global‑Matching）和额外提出的 Oracle‑Prompts 协议（直接提供真实类别名称作为提示，更公平比较）。

### 4. 资源与算力

- **GPU 型号**：单张 NVIDIA A100（80 GB）。
- **Batch size**：8。
- **训练时长**：COCO 预训练 25 个 epoch（约 250 万图像迭代）；RefCOCOg 微调 10 个 epoch。
- **参数量**：仅训练 4.5M 参数；冻结的 SAM2‑Hiera‑Large 和 BEiT‑3‑Large 共约 900M 参数。
- **推理速度**：单提示约 461 ms（A5000），其中非 SAM 模块占 19‑22% 开销。

### 5. 实验数量与充分性

- **数量**：表 1 展示了 8 个数据集×3 种任务的零样本性能；表 2 补充 Oracle‑Prompts 对比；表 3 指代分割对比；表 4‑5 消融实验（VLM 类型、训练模块、tie‑breaker、交叉注意力深度）；表 11‑12 额外消融（tie‑breaker 数量、cross‑attention 层数）；附录还包含 Cityscapes 局限分析。
- **充分性**：
  - **全面**：覆盖常见室内外、大/小词汇量、不同任务类型。
  - **对比公平**：与 SOTA 通用模型（X‑Decoder, APE）及专门模型（EVF-SAM）均做对比，并引入 Oracle‑Prompts 协议消除标签歧义。
  - **消融完备**：验证了每个设计组件的必要性（tie‑breaker、cross‑attention、预训练策略等）。
  - **客观性**：报告了多次实验的固定随机种子，未提供误差棒但说明原因。

### 6. 论文的主要结论与发现

1. **统一接口**：通过单一语言提示即可完成语义、实例、全景和指代分割，无需单独分类器或 LLM。
2. **高效性**：仅 4.5M 可训练参数即达到 SOTA，资源消耗远低于 LISA、GLaMM 等大模型。
3. **多实例能力**：位置 tie‑breaker 有效解决“单提示多实例”歧义，显著提升 AP 和 Recall。
4. **零样本泛化**：在未见类别和大词汇量数据集（如 ADE20K‑857、PASCAL Context‑459）上大幅超越先前方法（mIoU 提升 20+ 点）。
5. **指代分割竞争力**：cIoU 74.0% 接近专用模型 EVF-SAM（77.0%），但保留了交互和通用分割能力。
6. **设计验证**：早期融合（BEiT‑3）优于晚期融合（CLIP）；冻结 BEiT‑3 训练适配器优于微调整个 VLM；tie‑breaker 和 cross‑attention 缺一不可。

### 7. 优点：方法或实验设计上的亮点

- **创新性**：首次将位置 tie‑breaker 与轻量交叉注意力结合，在冻结 SAM2 基础上实现多实例开放词汇分割。
- **实用性**：训练成本低（单卡 A100，25 epoch），推理速度快，易于部署。
- **公平评估**：引入 Oracle‑Prompts 协议避免分类歧义，提供更真实的对比。
- **消融透彻**：从 VLM 选择、训练模块、组件数量到推理阶段逐一验证，结论可靠。
- **统一性**：一个模型同时解决四种分割任务，无需任务专用分支。

### 8. 不足与局限

- **户外场景泛化不足**：零样本在 Cityscapes 和 BDD10K 上表现下降（mIoU 39.4 vs X‑Decoder 52.0），主要归因于域偏移（训练数据多为室内或手持拍摄）和分辨率瓶颈（SAM2 默认 1024 尺寸对细长物体不友好）。
- **标签歧义未完全消除**：即使在 Oracle‑Prompts 下，模型仍可能对细粒度概念（如“arcade machine” vs “screen”）产生混淆。
- **tie‑breaker 数量固定**：K=20 在 COCO 上足够，但对于异常密集场景可能需要动态调整。
- **未在更多任务上验证**：如视频分割、3D 分割；论文仅针对图像分割。
- **未见大型真实用户研究**：交互式分割的实际效果缺少人类评估。

（完）
