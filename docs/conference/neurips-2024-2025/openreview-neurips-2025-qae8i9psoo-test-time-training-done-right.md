---
title: Test-Time Training Done Right
title_zh: 正确实施的测试时训练
authors: "Tianyuan Zhang, Sai Bi, Yicong Hong, Kai Zhang, Fujun Luan, Songlin Yang, Kalyan Sunkavalli, William T. Freeman, Hao Tan"
date: 2025-04-30
pdf: "https://openreview.net/pdf?id=qae8I9PSoo"
tags: ["query:tta"]
score: 7.0
evidence: 通过快速权重进行测试时训练以适应长序列数据
tldr: 现有测试时训练方法在处理长序列时计算效率极低。本文通过分析快速权重更新策略，优化在线小批量大小，显著提升了GPU利用率，使测试时训练能够高效处理长序列数据，扩展了其应用范围。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qae8i9psoo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1388, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qae8i9psoo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1428, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qae8i9psoo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1370, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qae8i9psoo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1398, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qae8i9psoo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1372, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qae8i9psoo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1392, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qae8i9psoo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1388, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qae8i9psoo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1384, \"height\": 500, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qae8i9psoo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qae8i9psoo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qae8i9psoo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1458, \"height\": 396, \"label\": \"Table\"}]"
motivation: 提升测试时训练在长序列数据上的计算效率。
method: 通过调整在线小批量大小和优化快速权重更新策略来提高FLOPs利用率。
result: 在长序列任务中实现了更高效的测试时训练，超越了现有方法。
conclusion: 为测试时训练在实际长序列应用中的部署提供了有效优化。
---

## Abstract
Test-Time Training (TTT) models context dependencies by adapting part of the model's weights (often referred to as fast weights) at inference time. This adapted fast weight, similar to recurrent states in RNNs, stores temporary memories of past tokens in the current sequence. Existing TTT methods have struggled to demonstrate effectiveness in handling long-sequence data, due to their computational inefficiency on modern GPUs. The TTT layers in
many of these approaches operate with extremely low FLOPs utilization (often below 5\%) because they deliberately apply small online mini-batch sizes (e.g., updating fast weights every 16 or 64 tokens). Moreover, a small mini-batch implies fine-grained block-wise causal dependencies in the data, making them unsuitable for data beyond 1D ordered sequences, like sets or N-dimensional grids such as images or videos.
In contrast, we pursue the opposite direction by proposing an extremely large chunk update, ranging from 2K to 1M tokens across tasks of varying modalities, which we refer to as Large Chunk Test-Time Training (LaCT). 
This approach improves hardware utilization by orders of magnitude, and more importantly, facilitates scaling of nonlinear state size (up to 40\% of model parameter size), hence
substantially improving state capacity, all without requiring cumbersome and error-prone custom kernel implementations.
It also allows easy integration of sophisticated optimizers like Muon for online memory updates.
We validate our approach across diverse data modalities and tasks, including novel view synthesis from image sets, language models, and auto-regressive video diffusion models. 
Our approach can scale up to 14-billion-parameter auto-regressive video diffusion models handling sequences of up to 56K tokens. 
In our longest sequence experiment, we perform novel view synthesis with more than one million context length. Our results highlight the computational and performance benefits of large-chunk test-time training, paving the way for more efficient and scalable long-context sequence modeling. We hope that this work will inspire and accelerate new research in the field of long-context modeling and test-time training.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究动机**：现有Test-Time Training (TTT) 方法在处理长序列数据时计算效率极低，其TTT层的FLOPs利用率常低于5%。原因在于它们使用很小的在线mini-batch大小（每16或64个token更新一次快速权重），导致并行度差和计算强度低。
- **问题影响**：小mini-batch也意味着细粒度的块状因果依赖，不适合图像、视频等N维网格数据。
- **本文目标**：提出相反策略——Large Chunk Test-Time Training (LaCT)，使用极大块（2K到1M tokens）作为更新基本单元，显著提升硬件利用率和状态容量，同时无需自定义CUDA内核，易于集成高级优化器。

### 2. 论文提出的方法论
- **核心思想**：将序列划分为大块，在块内对快速权重进行一次更新，然后对块内所有查询应用更新后的权重。结合窗口注意力机制捕获块内局部依赖。
- **关键技术细节**：
  - **快速权重网络**：采用SwiGLU-MLP，权重矩阵 W={W1,W2,W3}，输出 f_W(x)=W2[SiLU(W1x)∘(W3x)]。
  - **损失函数**：简单点积损失 L = −f_W(k)^⊤ v。
  - **更新操作**：计算块内所有键值对损失之和的梯度 g = ∇W∑η_i L(f_W(k_i), v_i)，然后执行权重更新。
  - **权重更新规则**：基础使用梯度下降后L2归一化；高级使用Muon优化器（基于牛顿-舒尔茨迭代近似SVD）后L2归一化。
  - **执行顺序**：通过调整“apply”与“update”的顺序，可实现等效于全注意、块状因果、移位块状因果、步进块状因果等注意力掩码。
  - **窗口注意力**：在每个LaCT块中加入局部窗口注意力，处理块内结构。
  - **上下文并行性**：利用梯度线性可加性，将块内token分片到各设备，通过all-reduce sum聚合梯度，支持分布式训练。
- **算法流程（文字说明）**：输入序列先经过窗口注意力层捕获局部依赖，然后进入LaCT层：对当前块内所有键值对计算梯度并更新快速权重，之后用更新后的权重对块内所有查询计算输出，最后经过前馈网络。快速权重在块间传递。

### 3. 实验设计
- **任务与数据集**：
  | 任务 | 数据集 | 评价指标 | 对比方法 |
  |------|--------|----------|----------|
  | 新颖视图合成 (NVS) | 训练：Objaverse；评估：GSO (256×256, 512×512)、DL3DV (536×960) | PSNR | 全注意力、Perceiver注意、LongLRM (结合Mamba和全注意力)、3D Gaussian Splatting |
  | 语言建模 | Long-Data-Collections (~60B tokens) | 逐token损失、检索准确率 (S-NIAH) | Transformer (全注意+滑动窗口)、GLA+滑动窗口、DeltaNet+滑动窗口 |
  | 自回归视频扩散 | 内部过滤专有视频，16FPS/480×832 | 损失（时间步550-950） | 仅滑动窗口注意、Mamba2+滑动窗口、全块状因果注意 |
- **Benchmark设置**：每个任务都公平地给基线方法添加了相同的窗口注意力（如适用）。NVS中对比了计算复杂度（如表2），语言建模中控制了状态大小和训练吞吐量。

### 4. 资源与算力
- **NVS任务**：对象模型训练1.25万亿tokens，场景模型训练1.8万亿tokens，渐进式分辨率。使用A100 GPU（文中给出A100上预填充速度和渲染FPS），但未报告具体卡数和时长。
- **语言建模**：760M模型训练40B tokens，3B模型训练60B tokens，序列长度32768，使用A100-40GB GPU。训练吞吐量在表3中给出（如Ours Muon为4.3K TPS）。
- **视频扩散**：微调Wan 2.1 (14B参数)，训练5秒视频，后微调8.8秒视频。未报告GPU数量或训练总时长。
- **总体情况**：论文未提供完整算力消耗（总GPU小时数），仅给出部分相对速度指标。

### 5. 实验数量与充分性
- **实验组数**：三大任务，每个任务包含多个子实验（如NVS有对象级和场景级、不同输入数；语言建模有760M和3B两种规模、多个基线；视频扩散有不同窗口大小和评估时长）。此外有专门的分析实验：
  - 状态大小缩放（图7a）
  - 测试时优化器对比（图7b）
  - 线性 vs 非线性快速权重（图8a）
  - 大块递归 vs 逐token递归（图8b）
- **充分性与公平性**：消融实验设计系统，基线对比时控制了状态大小、滑动窗口等变量。NVS中对比了计算复杂度表，语言建模中所有线性方法训练吞吐量相近。实验覆盖多模态，验证了方法的通用性。
- **客观性**：主要指标为客观数值（PSNR、损失、准确率），无主观评价。

### 6. 论文的主要结论与发现
- LaCT显著提升GPU利用率（可达70%，图1a），使得在纯PyTorch下也能高效训练。
- 增大块大小和状态大小能持续提升性能（图7a），最大状态占模型参数40%。
- 非线性快速权重（SwiGLU）在更小状态下也优于线性权重（图8a）。
- Muon优化器优于普通梯度下降和动量（图7b）。
- 在NVS任务上，LaCT达到或超越3D Gaussian Splatting，处理百万级token。
- 在语言建模上，LaCT（非线性+大状态+Muon）优于GLA、DeltaNet等逐token递归方法，尤其在长上下文检索准确率上。
- 在自回归视频扩散上，LaCT微调14B模型后，验证损失低于Mamba2+滑动窗口和仅滑动窗口基线，且接近全注意力。

### 7. 优点
- **实现简单高效**：仅需几十行纯PyTorch代码即可获得高硬件利用率，无需复杂自定义内核。
- **强扩展性**：快速权重大小可扩展至模型参数的40%，且支持高效上下文并行。
- **灵活性与通用性**：可调节块大小和更新/应用顺序以适应不同数据类型（集合、1D序列、图像序列等），且能轻松集成Muon等高级优化器。
- **实验验证充分**：在三类不同模态的任务上均取得SOTA或竞争性结果，并有详尽的消融分析支持设计选择。

### 8. 不足与局限
- **任务覆盖有限**：虽然涉及三个任务，但作者承认NVS本质是有姿势的3D重建，无姿势重建更困难但未探索。
- **语言模型推理与扩展**：受限于计算资源，未测试大规模参数（如7B以上）的语言模型以及推理能力评估。作者指出这些能力可能需要更多训练计算才能显现。
- **视频扩散评估指标**：难以找到可靠区分性指标，仅使用验证损失，这是该领域通用问题。
- **方法本身的局限性**：长序列假设下块大小需精心调整；跨任务时需针对数据结构调整块大小和窗口注意力配置，不是完全免调参的。

（完）
