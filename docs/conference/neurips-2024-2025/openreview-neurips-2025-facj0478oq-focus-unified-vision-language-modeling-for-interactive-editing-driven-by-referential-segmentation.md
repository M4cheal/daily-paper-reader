---
title: "FOCUS: Unified Vision-Language Modeling for Interactive Editing Driven by Referential Segmentation"
title_zh: FOCUS：基于参照分割的统一视觉语言交互编辑模型
authors: "Fan Yang, Yousong Zhu, Xin Li, Yufei Zhan, Hongyin Zhao, Shurong Zheng, Yaowei Wang, Ming Tang, Jinqiao Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=FACJ0478oQ"
tags: ["query:ris"]
score: 9.0
evidence: 基于参照分割的交互编辑
tldr: 本文针对当前视觉语言模型将视觉理解和生成分离的问题，提出FOCUS，一个统一的大视觉语言模型，通过双分支视觉编码器同时实现分割感知和可控目标生成，在参照分割驱动的交互编辑任务中达到最优性能，证明了端到端框架的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 960, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1347, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 354, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 353, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 355, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 354, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 358, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 353, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 357, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 355, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 349, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 356, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 356, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 351, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1395, \"height\": 1653, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 662, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1422, \"height\": 432, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 719, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1456, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1188, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1377, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1412, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1441, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 952, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1434, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1370, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1363, \"height\": 524, \"label\": \"Table\"}]"
motivation: 现有方法将视觉理解和生成编辑分离，需要多个模型，效率低下。
method: 提出双分支视觉编码器的端到端LVLM，融合分割感知和可控生成。
result: 在编辑和分割任务上取得最优性能。
conclusion: 统一的端到端框架有效结合了视觉理解和生成。
---

## Abstract
Recent Large Vision Language Models (LVLMs) demonstrate promising capabilities in unifying visual understanding and generative modeling, enabling both accurate content understanding and flexible editing. However, current approaches treat \textbf{\textit{"what to see"}} and \textbf{\textit{"how to edit"}} separately: they either perform isolated object segmentation or utilize segmentation masks merely as conditional prompts for local edit generation tasks, often relying on multiple disjointed models. To bridge these gaps, we introduce FOCUS, a unified LVLM that integrates segmentation-aware perception and controllable object-centric generation within an end-to-end framework. FOCUS employs a dual-branch visual encoder to simultaneously capture global semantic context and fine-grained spatial details. In addition, we leverage a MoVQGAN-based visual tokenizer to produce discrete visual tokens that enhance generation quality. To enable accurate and controllable image editing, we propose a progressive multi-stage training pipeline, where segmentation masks are jointly optimized and used as spatial condition prompts to guide the diffusion decoder. This strategy aligns visual encoding, segmentation, and generation modules, effectively bridging segmentation-aware perception with fine-grained visual synthesis.
Extensive experiments across three core tasks, including multimodal understanding, referring segmentation accuracy, and controllable image generation, demonstrate that FOCUS achieves strong performance by jointly optimizing visual perception and generative capabilities.

---

## 论文详细总结（自动生成）

# FOCUS 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前大视觉语言模型（LVLM）虽然尝试统一视觉理解和生成，但普遍将“看什么”（分割感知）和“如何编辑”（生成与编辑）分开处理。现有方法要么执行孤立的物体分割，要么仅将分割掩膜作为局部生成的条件提示，且常依赖多个不连续的模型（如 InstructEdit 使用外部 Grounded-SAM 获取掩膜），缺乏端到端的统一建模。
- **研究动机**：旨在构建一个统一的端到端 LVLM，将像素级分割感知与区域可控的物体级生成无缝融合，使模型既能理解图像内容，又能根据自然语言指令进行精确的交互式编辑。
- **整体含义**：FOCUS 通过联合优化视觉编码、分割解码和扩散生成，证明了在同一框架内实现高精度分割感知与可控生成是可行且有效的，为交互式、通用化的多模态编辑系统奠定了基础。

## 2. 论文提出的方法论

### 核心思想
- 设计双分支视觉编码器（全局语义 + 细粒度空间细节）和一个生成式视觉分词器（MoVQGAN 架构），将视觉信息离散化为语义和像素 token。
- 引入门控交叉注意力（Gated Cross-Attention）融合多尺度特征，并用连续预量化特征输入 LLM 以减少信息损失。
- 采用渐进式多阶段训练策略，逐步增加图像分辨率和任务复杂度，使分割解码器和扩散生成器在不同尺度上对齐。
- 将联合优化的分割掩膜作为空间条件注入扩散解码器（基于 SDXL），实现区域级可控编辑。

### 关键技术细节
- **双分支视觉编码器**：
  - 低分辨率图像（256×256）经 Vanilla Encoder（QwenViT）提取全局语义。
  - 高分辨率图像（768×768）经 Hierarchical Encoder（ConvNeXt-L）提取多尺度局部特征。
  - 通过交叉注意力融合，再用 MLP 和残差连接得到融合特征 \(E_{\text{img}}\)。
- **生成式视觉分词器**（MoVQGAN）：
  - 语义分支：下采样率 28×，码本大小 32768，用余弦相似度损失监督。
  - 像素分支：下采样率 16×，码本大小 98304，用 L1、感知损失和对抗损失训练。
  - 两分支的 token 拼接后经解码器重建图像。
- **LLM 与输入架构**：
  - 采用 Qwen2.5-3B，输入为 \((E_{\text{img}}, X_S, X_T, h^{(l)}_{\text{Adapter}})\)。
  - 输出包括语义增强的掩膜 token（需先预测所有物体名称）和离散视觉 token（先语义后像素）。
- **分割模块**：
  - 基于 Mask2Former，输入三类信息：任务提示嵌入、LLM 输出的掩膜 token、视觉编码器的多尺度特征。
  - 输出二进制掩膜、类别分数、实例嵌入（用于视频时序关联）。
- **扩散解码器**：
  - 从 SDXL 初始化，利用 LLM 生成的语义和像素 token 映射为连续嵌入，与噪声潜变量拼接送入 UNet。
  - 预测的分割掩膜下采样后经线性投影得到空间引导序列 \(f_m\)，通过交叉注意力注入 UNet 各层。
- **渐进多阶段训练**：
  - Stage1：预训练双分支视觉分词器和扩散解码器（58M 图文对，256→512 分辨率）。
  - Stage2：可视化语言适配器预热（投影头、门控交叉注意力，仅语言建模损失）。
  - Stage3：多模态预训练与分割感知对齐（联合训练 LLM、适配器、掩膜解码器，256/512 分辨率）。
  - Stage4：指令微调用于区域可控编辑（引入扩散交叉注意力层，512→1024 分辨率，桶切策略）。

## 3. 实验设计

### 使用的数据集 / 场景与基准
- **多模态理解**：POPE、MMBench、SEED、MME-P、MM-Vet、MMMU、AI2D（通用）；VQA-text、ChartQA、DocVQA、InfoVQA、OCRBench（文档）。
- **可控生成与编辑**：
  - 生成：MJHQ-30K（FID）、GenAI-bench（Basic/Adv）、GenEval（六项子指标）。
  - 编辑：Emu Edit 基准（DINO、CLIP-I、CLIP-T、CLIP-DIR）。
- **参照分割**：RefCOCO、RefCOCO+、RefCOCOg、gRefCOCO（mIoU）。
- **额外分割任务**：ReasonSeg、ReVOS（视频推理分割）、COCO-Interactive（交互式）、DAVIS17、Ref-YT、Ref-DAVIS、YouTube-VIS（视频分割）。

### 对比的方法
- 多模态理解：InstructBLIP、Qwen-VL-Chat、LLaVA-1.5、ShareGPT4V、LLaVA-NeXT、Emu3-Chat、Unified-IO、Chameleon、LWM、Show-o、VILA-U、Janus、Janus-Pro、ILLUME+ 等。
- 生成：SDv1.5、PixArt-α、SDXL、Emu3-Gen、Chameleon、LWM、Show-o、VILA-U、Janus、ILLUME+ 等。
- 编辑：InstructPix2Pix、MagicBrush、OmniGen、Emu Edit、PUMA、ILLUME、ILLUME+ 等。
- 分割：CRIS、LAVT、PolyFormer、LISA、PixelLM、PSALM、HyperSeg 等。

### 消融实验
- 多阶段训练效果（不同分辨率 256/512/1024 vs 渐进 256→1024）。
- 门控交叉注意力中多尺度特征层数（单尺度、双尺度、三尺度）。
- 连续 token 输入 vs 离散 token 输入。
- 分割掩膜的作用（无掩膜、通用掩膜、FOCUS 自身掩膜）。

## 4. 资源与算力

- 论文明确提到：双分支视觉分词器和扩散解码器的训练各耗时约 3 天（在计算集群上）；3B 参数的 MLLM 需要约 13 天完成三阶段训练。
- **未明确说明**：GPU 型号（可能为 A100 等）、具体数量、显存大小。仅提及“计算集群”。

## 5. 实验数量与充分性

- 实验覆盖三大核心任务，共十多个标准化基准，对比了十余种 SOTA 方法，包含全面定量比较。
- 消融实验包括：分辨率影响（4种设置）、多尺度特征融合（4种变体）、连续 token 输入（2种）、掩膜引导（3种）。此外还包含视频分割、交互式分割等扩展评估。
- 实验设计较为充分客观：所有基准均为公开标准，指标主流（mIoU、FID、CLIP score 等），对比方法均来自近期文献。不足之处在于对 OOD 泛化、长尾场景的评估较少。

## 6. 论文的主要结论与发现

- FOCUS 在三个核心任务（多模态理解、参照分割、可控生成与编辑）上均达到或超越 SOTA 性能，尤其以 3B 参数模型取得与 7B 模型相当甚至更好的结果。
- 统一的端到端框架有效结合了像素级感知和生成编辑，分割感知信号对提升编辑精度至关重要。
- 渐进式多阶段训练策略能够平衡高分辨率下的视觉精度与语言理解，避免直接使用高分辨率导致的幻觉增加。
- 连续视觉 token 输入和门控多尺度融合显著提升模型性能，证明了这些设计选择的必要性。

## 7. 优点

- **端到端统一性**：首次在同一 LVLM 中紧密耦合分割感知与掩膜引导的扩散生成，避免模块堆积和特征隔离。
- **双分支视觉编码**：同时捕获全局语义和局部细节，兼顾理解与生成的需求。
- **生成式视觉分词器**：MoVQGAN 离散化视觉信息，语义+像素双码本设计保证了重建质量。
- **渐进训练策略**：从低分辨率简单任务向高分辨率复杂任务过渡，逐阶段激活模块，有效缓解优化冲突。
- **连续 token 输入**：保留量化前的连续特征，减少信息损失，提升 LLM 的细粒度理解。
- **广泛的实验验证**：覆盖多种任务和基准，消融实验详实，对比方法充分。

## 8. 不足与局限

- **计算资源需求高**：整个训练流程（分词器+扩散+3B MLLM）需约 19 天集群计算，对普通研究者复现门槛高。
- **高分辨率下的理解下降**：消融实验中直接使用 1024×1024 图像导致 POPE、MMBench 等理解指标下降，虽通过渐进训练缓解，但表明模型对分辨率敏感。
- **视频处理方式较简易**：采用逐帧处理，未显式建模时序依赖（如光流、运动注意力），可能限制复杂视频编辑的连贯性。
- **泛化性评估不足**：实验仅在 COCO 风格等标准数据集上进行，未测试极端 OOD 场景、艺术风格迁移等实际应用中的鲁棒性。
- **模型规模较小**：仅使用 3B LLM，更大规模（7B 或 13B）可能进一步提升性能，但论文未探索 scaling 规律。
- **潜在偏差风险**：训练数据来自互联网（COYO、LAION-2B 等），可能包含社会偏见或不当内容，论文未讨论公平性和去偏措施（如模型审核机制）。

（完）
