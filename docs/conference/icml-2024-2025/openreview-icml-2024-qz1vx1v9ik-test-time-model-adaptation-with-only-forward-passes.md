---
title: Test-Time Model Adaptation with Only Forward Passes
title_zh: 仅前向传播的测试时模型自适应
authors: "Shuaicheng Niu, Chunyan Miao, Guohao Chen, Pengcheng Wu, Peilin Zhao"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=qz1Vx1v9iK"
tags: ["query:tta"]
score: 8.0
evidence: 仅前向传播的TTA方法
tldr: 现有TTA依赖反向传播，无法用于量化硬件。本文提出FOA，仅通过无导数优化学习输入提示，在推理时在线适应。该方法在无反向传播条件下实现了与反向传播方法相当的适应性能，适用于FPGA等资源受限设备。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-qz1vx1v9ik/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1697, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-qz1vx1v9ik/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1758, \"height\": 770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-qz1vx1v9ik/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-qz1vx1v9ik/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1540, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-qz1vx1v9ik/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 627, \"height\": 491, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1766, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1765, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 856, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 857, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 857, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 854, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 855, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 858, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1586, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1595, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1595, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1768, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qz1vx1v9ik/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1769, \"height\": 335, \"label\": \"Table\"}]"
motivation: 资源受限设备无法支持反向传播，需要无需BP的TTA。
method: 使用无导数的协方差矩阵自适应进化策略学习输入提示。
result: 在多个视觉任务上取得与BP方法相近的自适应效果。
conclusion: FOA使得TTA在无反向传播设备上成为可能。
---

## Abstract
Test-time adaptation has proven effective in adapting a given trained model to unseen test samples with potential distribution shifts. However, in real-world scenarios, models are usually deployed on resource-limited devices, e.g., FPGAs, and are often quantized and hard-coded with non-modifiable parameters for acceleration. In light of this, existing methods are often infeasible since they heavily depend on computation-intensive backpropagation for model updating that may be not supported. To address this, we propose a test-time Forward-Optimization Adaptation (FOA) method. In FOA, we seek to solely learn a newly added prompt (as model's input) via a derivative-free covariance matrix adaptation evolution strategy. To make this strategy work stably under our online unsupervised setting, we devise a novel fitness function by measuring test-training statistic discrepancy and model prediction entropy. Moreover, we design an activation shifting scheme that directly tunes the model activations for shifted test samples, making them align with the source training domain, thereby further enhancing adaptation performance. Without using any backpropagation and altering model weights, FOA runs on quantized 8-bit ViT outperforms gradient-based TENT on full-precision 32-bit ViT, while achieving an up to *24*-fold memory reduction on ImageNet-C. The source code is available at: https://github.com/mr-eggplant/FOA.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有的测试时自适应（Test-Time Adaptation, TTA）方法大多依赖反向传播（backpropagation）来更新模型权重，而实际部署场景中（如智能手机、FPGA、嵌入式系统）的模型通常经过量化（如 8-bit、6-bit）或硬编码，不支持反向传播，导致现有方法不可行。
- **整体含义**：本文提出一种仅依赖前向传播（forward-only）的 TTA 方法——FOA（Forward-Optimization Adaptation），使得 TTA 能够在资源受限、无反向传播能力的设备上有效运行，显著拓展了 TTA 的实际应用范围。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：不修改模型权重，仅在线学习一个新增的输入提示（prompt），并使用无导数优化器（CMA-ES）进行更新，同时通过激活偏移（activation shifting）将测试样本的特征分布拉回源域分布。
- **关键技术细节**：
  - **仅前向的提示自适应（Forward-Only Prompt Adaptation）**：
    - 在 Vision Transformer（ViT）的输入层之前插入一个可学习的 prompt embedding（维度 d，数量 Np=3）。
    - 使用协方差矩阵自适应进化策略（CMA-ES）优化 prompt，避免梯度计算。
    - **适应度函数**（公式 5）由两部分组成：
      - 预测熵（最小化模型不确定性）；
      - 激活分布差异（测试样本与源域样本在每一层的 CLS token 均值和标准差的 L2 距离）。
    - 源域统计量（{μᵢˢ, σᵢˢ}）只需少量无标签源样本（如 32 张 ImageNet 图片）提前计算一次。
  - **回源激活偏移（Back-to-Source Activation Shifting）**：
    - 在最后一个 Transformer 层的 CLS 特征 e₀ᴺ 上加上偏移向量：e₀ᴺ ← e₀ᴺ + γ·d（公式 7）。
    - 偏移方向 d = μₛᴺ - μₙ(t)，其中 μₛᴺ 是源域特征中心，μₙ(t) 是测试域特征中心（通过指数移动平均更新，公式 9）。
- *算法流程*（Algorithm 1）：对每个测试 batch，采样 K 个 prompt 候选 → 前向传播 → 计算适应度 → 更新 CMA-ES 分布参数 → 选择最佳预测。

## 3. 实验设计
- **数据集与场景**：
  - ImageNet-C（15 种合成 corruption，5 级严重度，主要报告 level 5）
  - ImageNet-R（200 类的艺术化风格）
  - ImageNet-V2（匹配频率子集）
  - ImageNet-Sketch（草图）
  - 非 i.i.d. 场景（在线标签不平衡、混合域偏移）
- **基准（benchmark）**：分类准确率（Accuracy ↑）和期望校准误差（ECE ↓）。
- **对比方法**：
  - 无梯度方法：LAME, T3A
  - 梯度方法：TENT, CoTTA, SAR, MEMO
- **模型**：主要使用 ViT-Base（全精度 32-bit），并扩展到 8-bit/6-bit 量化模型（PTQ4ViT 量化），以及 ResNet-50 和 VisionMamba。

## 4. 资源与算力
- 论文未明确说明训练源模型所需的算力（因源模型从开源仓库获取）。
- 在推理效率实验中，使用 **单张 RTX 3090 GPU** 测量了处理 50,000 张 ImageNet-C 图像的 wall-clock time 和峰值内存。
- 未提供具体训练时长；FOA 的运行时间取决于 CMA-ES 种群大小 K（K 越大耗时越长）。

## 5. 实验数量与充分性
- **主要实验**：包含 4 个 OOD 数据集上的准确率和 ECE（表 2、表 3）、量化模型对比（表 4）、消融研究（表 5，组件、可学习参数、优化器、损失函数）、参数敏感性（种群大小 K、prompt 数量 Np、源样本数量，图 2）、单样本自适应（表 6）、内存与计算复杂度（表 7、表 8）、非 i.i.d. 场景（表 11）、源域性能（表 12）、对不同架构（ResNet/VisionMamba，表 10）的验证。
- **充分性**：实验设计较为全面，覆盖了主流 OOD benchmark、多种设置（在线、非 i.i.d.、量化、小批量等），对比方法公平（相同 batch size 等超参数调整），消融明确验证了各组件的贡献（表 5）。结论具有较强说服力。

## 6. 主要结论与发现
- FOA 在不使用反向传播的前提下，在 ImageNet-C 上平均准确率达 66.3%，优于梯度方法 TENT（59.6%）和 SAR（62.7%），且 ECE 最低（3.2%）。
- 在 8-bit 量化 ViT 上，FOA 准确率（63.5%）反超全精度 32-bit 的 TENT（59.6%），内存节省最高达 24 倍（208 MB vs 5165 MB）。
- 在 ImageNet-R/V2/Sketch 上，FOA 取得与或优于梯度方法相当的性能。
- FOA 在非 i.i.d. 场景下保持稳定，且在源域数据上几乎不损失原有准确率（仅下降 0.06%）。

## 7. 优点
- **无需反向传播**：突破现有 TTA 对 BP 的依赖，使 TTA 适用于 FPGA、智能手机等无 BP 能力的设备。
- **不修改模型权重**：避免遗忘源域知识，保持源域性能。
- **兼容量化模型**：直接在 8-bit/6-bit 模型上运行，显著降低内存和能耗。
- **高效内存**：相比梯度方法（如 TENT 5,165 MB，CoTTA 16,836 MB），FOA 仅需 832 MB（BS=64），且可通过更小种群 K 进一步降低。
- **新颖的适应度函数**：结合预测熵和激活分布差异，为无监督 CMA-ES 提供稳定学习信号，避免退化解。
- **激活偏移机制**：直接调整最终层特征，无需额外模型更新，进一步显著提升性能。

## 8. 不足与局限
- **CMA-ES 种群开销**：FOA 需要多次前向传播（K 次），K 较大时（如 K=28）计算时间较长；虽然可通过减小 K 平衡效率，但性能会略有下降。
- **对 CNN 架构适应性有限**：在 ResNet-50 上，FOA 性能（22.6%）远低于梯度方法 TENT（29.4%），因为卷积的局部操作使输入 prompt 难以有效影响全局；仅在 Transformer 和 Mamba 等架构上表现良好。
- **需要少量源域数据**：计算源统计量需要少量无标签源样本（如 32 张），虽然实际中较易获取，但增加了部署前准备工作。
- **未在更大规模或更多样化的实际部署场景（如自动驾驶、医疗）中验证**：实验局限于 ImageNet 变体，领域偏移主要为合成 corruption 和风格变化。
- **未与最新的高效 TTA 方法（如仅更新部分层的梯度方法）在相同算力约束下全面对比**：论文主要对比了 TENT、SAR、CoTTA 等，但可能存在更优的 BP 方法在特定设置下接近 FOA 的性能。
- **批大小敏感**：当批大小为 1 时，需要间隔更新策略（FOA-I），增加了复杂度；虽在论文中提供了解决方案，但实际部署需考虑缓存。

（完）
