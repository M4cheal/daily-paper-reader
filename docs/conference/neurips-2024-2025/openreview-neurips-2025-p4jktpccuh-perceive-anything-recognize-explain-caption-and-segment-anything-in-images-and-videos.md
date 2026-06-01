---
title: "Perceive Anything: Recognize, Explain, Caption, and Segment Anything in Images and Videos"
title_zh: 感知一切：识别、解释、描述和分割图像与视频中的任意物体
authors: "Weifeng Lin, Xinyu Wei, Ruichuan An, Tianhe Ren, Tingwei Chen, Renrui Zhang, Ziyu Guo, Wentao Zhang, Lei Zhang, Hongsheng Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=p4jKtPCcUh"
tags: ["query:ris"]
score: 8.0
evidence: 语言指导的图像/视频任意区域分割
tldr: 本文提出Perceive Anything Model（PAM），在SAM2基础上引入大语言模型和语义感知器，将视觉特征转化为多模态token，实现任意区域的类别识别、功能解释、详细描述和分割，为通用区域视觉理解提供了高效框架。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1414, \"height\": 1131, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1390, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1409, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1432, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1428, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 929, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1426, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1428, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1409, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1415, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1340, \"height\": 547, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-p4jktpccuh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1324, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p4jktpccuh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p4jktpccuh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 906, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p4jktpccuh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 536, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p4jktpccuh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 495, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p4jktpccuh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 478, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p4jktpccuh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 482, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p4jktpccuh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1453, \"height\": 628, \"label\": \"Table\"}]"
motivation: 现有区域理解模型缺乏语义多样化输出，需要统一分割与语义生成。
method: 在SAM2基础上引入语义感知器，将视觉特征转化为多模态token供LLM理解。
result: 在多粒度理解任务上表现优异。
conclusion: 为通用区域视觉理解提供高效框架。
---

## Abstract
We present Perceive Anything Model (PAM), a conceptually straightforward and efficient framework for comprehensive region-level visual understanding in images and videos. Our approach extends the powerful segmentation model SAM 2 by integrating Large Language Models (LLMs), enabling simultaneous object segmentation with the generation of diverse, region-specific semantic outputs, including categories, label definition, functional explanations, and detailed captions. A key component, Semantic Perceiver, is introduced to efficiently transform SAM 2's rich visual features, which inherently carry general vision, localization, and semantic priors into multi-modal tokens for LLM comprehension. To support robust multi-granularity understanding, we also develop a dedicated data refinement and augmentation pipeline, yielding a high-quality dataset of 1.5M image and 0.6M video region-semantic annotations, including novel region-level streaming video caption data. PAM is designed for lightweightness and efficiency, while also demonstrates strong performance across a diverse range of region understanding tasks. It runs 1.2$-$2.4$\times$ faster and consumes less GPU memory than prior approaches, offering a practical solution for real-world applications. We believe that our effective approach will serve as a strong baseline for future research in region-level visual understanding.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：现有区域级视觉理解模型（如基于 SAM 的方法）大多只能输出类别标签或简短描述，缺乏对物体在上下文中定义、功能、详细描述等多维度语义的生成能力，且多数模型仅支持单一模态（图像或视频），依赖外部分割模型导致计算效率低。
- **整体含义**：本文提出 **Perceive Anything Model (PAM)**，在 SAM 2 基础上集成大语言模型，实现**同时对指定区域进行分割、类别识别、标签定义与功能解释、详细描述**，并支持**图像、视频及流式视频**，旨在建立一个通用、高效、轻量的区域级视觉理解基线。

### 2. 论文提出的方法论

- **核心思想**：保留 SAM 2 作为视觉特征提取器和分割模块，新增**语义解码器**（基于 LLM），通过**语义感知器（Semantic Perceiver）** 桥接 SAM 2 中间视觉特征与 LLM 输入，并行生成掩码和语义输出。
- **关键技术细节**：
  - **Semantic Perceiver**：轻量两层 Transformer，含自注意力、交叉注意力和 MLP，接收 S2-FFM 输出的增强掩码 token 和图像嵌入，结合可学习的语义 token（默认 16 个），输出视觉 token 和语义 token。
  - **投影器**：先进行像素混洗（Pixel Shuffle）降维，再用两个独立 MLP 分别投影视觉 token 和语义 token 给 LLM。
  - **语义解码器**：使用预训练 Qwen2.5-1.5B/3B 作为 LLM，处理视觉与语义 token 及任务指令。
  - **流式视频编码**：对上一片段最后一帧应用 2×2 像素混洗保持高密度视觉信息，作为下一片段首帧；同时引入前一片段文本描述作为上下文。
  - **训练策略**：三阶段课程学习（图像预训练对齐 → 视频增强预训练对齐 → 多模态微调），SAM 2 参数冻结，逐步开放语义感知器、投影器、LLM 的训练。
- **数据构建**：开发数据精炼与增强流水线，利用 GPT-4o 和 Qwen2.5-VL 对现有数据集进行标注增强，生成**1.5M 图像区域‑语义三元组**和 **0.6M 视频区域‑语义三元组**，包括首次提出的**区域级流式视频描述**数据，并支持中英双语。

### 3. 实验设计

- **使用数据集/场景**：
  - **图像识别**：LVIS（物体）、PACO（部件）、COCO-Text、Total-Text（场景文本）。
  - **图像描述**：RefCOCOg、Visual Genome、Ref-L4（详细描述）、Ferret-Bench、MDVP-Bench（GPT‑4o 评测）。
  - **视频区域描述**：Elysium、BensMOT、HC-STVG、VideoRefer-Bench-D。
  - **流式视频区域描述**：ActivityNet（人工筛选 400 样本，标注目标框和事件级描述）。
- **对比方法**：Shikra、GPT4RoI、Osprey、Ferret、VP-LLaVA、VP-SPHINX、DAM、Omni-RGPT、VideoRefer、Merlin、Artemis 等（含 7B‑13B 参数）。
- **评价指标**：语义相似度、语义 IoU、METEOR、CIDEr、ROUGE‑L 以及自提出的 GPT-4o 评估时空连续性得分（G‑STDC）。

### 4. 资源与算力

- **硬件**：8 块 NVIDIA A100 GPU（80GB 显存）。
- **训练细节**：三阶段训练，每阶段 1 epoch；全局 batch size 分别为 1024（阶段 1/1.5）和 256（阶段 2）；学习率从 1e‑4 递减至 1e‑5；使用 AdamW 优化器。未报告总训练时长，但论文强调推理速度快 1.2‑2.4 倍且显存占用更低。

### 5. 实验数量与充分性

- **实验数量**：覆盖 4 类任务（图像识别、图像描述、视频描述、流式视频描述）共 10+ 个 benchmark；消融实验 3 组（语义 token 数量、训练策略、中间特征选择）；效率对比；定性可视化。
- **充分性**：实验设计较全面，对比了当前主流方法，且采用零样本测试避免过拟合；消融验证了核心组件有效性；但流式视频描述仅在一个数据集（ActivityNet）上人工筛选子集测试，覆盖度有限。整体公平且客观。

### 6. 论文的主要结论与发现

- PAM 在多数基准上达到或超越现有 SOTA，尤其是在 PACO 部件识别（+3.2%）、LVIS 语义 IoU、视频区域描述（Elysium、BensMOT、HC-STVG）上表现突出。
- 在流式视频区域描述任务上，PAM-3B 的 METEOR 和 G‑STDC 均优于专用流式模型（如 Streaming Vid2Seq）。
- 推理效率显著提升（1.2‑2.4× 更快，显存更低），适合实际部署。
- 语义感知器和三阶段课程学习对性能提升至关重要；16 个语义 token 达到最佳效率‑准确率平衡。

### 7. 优点

- **架构创新**：在 SAM 2 基础上通过轻量 Semantic Perceiver 高效融合视觉与语义特征，实现分割与语义生成并行，避免串行计算开销。
- **数据贡献**：构建大规模、多粒度、双语的区域‑语义数据集，尤其是首个区域级流式视频描述数据，推动领域发展。
- **通用性**：统一支持图像、视频、流式视频；输出类别、定义、功能、详细描述等语义，甚至支持中英双语。
- **效率**：参数量小（1.5B/3B），推理速度快，显存占用低，便于实际应用。

### 8. 不足与局限

- **任务覆盖不全**：目前仅支持四种特定区域理解任务，不支持通用 VQA 或多轮对话。
- **流式实时性不足**：虽然比已有模型快，但 LLM 处理大量视觉 token 仍无法达到严格实时。
- **长视频处理**：默认 16 帧采样只能提供粗粒度描述；流式分段方法可改善但增加延迟。
- **数据偏差**：标注过程中 GPT 可能倾向于描述最显著物体而非指定区域，导致某些失败案例（如目标消失时描述错误）。
- **验证集规模有限**：流式视频描述仅用 ActivityNet 子集（400 样本），泛化性需更多测试。
- **双语支持**：中文标注主要靠机器翻译，质量可能有限。

（完）
