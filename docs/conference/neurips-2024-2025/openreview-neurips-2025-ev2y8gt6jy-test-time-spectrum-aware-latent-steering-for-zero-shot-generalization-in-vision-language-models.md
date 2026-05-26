---
title: Test-Time Spectrum-Aware Latent Steering for Zero-Shot Generalization in Vision-Language Models
title_zh: 测试时间频谱感知潜在引导用于视觉语言模型零样本泛化
authors: "Konstantinos M. Dafnis, Dimitris N. Metaxas"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=eV2Y8Gt6JY"
tags: ["query:tta"]
score: 9.0
evidence: 面向视觉语言模型的测试时间自适应
tldr: 视觉语言模型在测试时面临域漂移。现有测试时间自适应需要反向传播或修改模型核心组件。STS提出一种轻量级框架，从文本嵌入中提取谱子空间定义语义方向，然后以谱感知方式引导潜在表示。该方法无需反向传播，在零样本泛化任务上取得了高效的域适应效果。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ev2y8gt6jy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ev2y8gt6jy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ev2y8gt6jy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 699, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ev2y8gt6jy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 569, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ev2y8gt6jy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1148, \"height\": 692, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1423, \"height\": 764, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1100, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 734, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1340, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1406, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 998, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1441, \"height\": 675, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1148, \"height\": 692, \"label\": \"Table\"}]"
motivation: 减少测试时间自适应对反向传播和模型核心修改的依赖。
method: 通过谱子空间学习语义方向，以少量可学习参数引导潜在表示。
result: 在多个域漂移基准上以极低开销提升零样本分类准确率。
conclusion: 频谱感知引导为VLM测试时间自适应提供了高效实用的方案。
---

## Abstract
Vision–Language Models (VLMs) excel at zero-shot inference but often degrade under test-time domain shifts. For this reason, episodic test-time adaptation strategies have recently emerged as powerful techniques for adapting VLMs to a single unlabeled image. However, existing adaptation strategies, such as test-time prompt tuning, typically require backpropagating through large encoder weights or altering core model components. In this work, we introduce Spectrum-Aware Test-Time Steering (STS), a lightweight adaptation framework that extracts a spectral subspace from the textual embeddings to define principal semantic directions, and learns to steer latent representations in a spectrum-aware manner by adapting a small number of per-sample shift parameters to minimize entropy across augmented views. STS operates entirely at inference in the latent space, without backpropagation through or modification of the frozen encoders. Building on standard evaluation protocols, our comprehensive experiments demonstrate that STS largely surpasses or compares favorably against state-of-the-art test-time adaptation methods, while introducing only a handful of additional parameters and achieving inference speeds up to 8× faster with a 12× smaller memory footprint than conventional test-time prompt tuning. The code is available at https://github.com/kdafnis/STS.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

- **核心问题**：视觉-语言模型（VLM，如CLIP）在零样本推理中表现优异，但在测试时会遇到分布偏移（out-of-distribution, OOD），导致性能严重下降。现有的测试时自适应（TTA）方法（如Test-Time Prompt Tuning, TPT）通常需要反向传播通过大型编码器权重，计算开销大且内存占用高，不适用于资源受限或需要快速推理的场景。
- **整体含义**：本文旨在提出一种轻量级、高效的TTA方法，在不修改VLM编码器、不进行反向传播的前提下，仅通过调整少量参数实现零样本泛化能力提升，使VLM能快速适应单个无标注测试样本。

### 论文提出的方法论

- **核心思想**：利用文本嵌入的谱结构（Singular Value Decomposition, SVD）提取一个低维语义子空间，并在该子空间内学习一个共享的系数向量，该系数向量定义了一个偏移量（steering vector），用于调整所有类别的文本原型，从而更好地匹配当前测试图像的视觉特征。
- **关键技术细节**：
    1. **谱子空间识别**：对初始文本原型矩阵 \( Z_T^{init} \in \mathbb{R}^{C \times D} \) 进行SVD，保留前 \( k_t \) 个右奇异向量作为正交基 \( B_T \in \mathbb{R}^{D \times k_t} \)。\( k_t \) 通过Gavish-Donoho最优硬阈值方法自动确定，以捕获主要语义变化。
    2. **潜空间引导**：定义可学习系数向量 \( \gamma \in \mathbb{R}^{k_t} \)，偏移量 \( \Delta z_T = B_T \gamma \)。调整后的原型为 \( (z_T^{adapted})_c = \text{normalize}((z_T^{init})_c + \Delta z_T) \)。
    3. **测试时优化目标**：对测试图像生成N个增广视图，保留置信度最高的10%视图（基于初始原型的熵过滤）。优化目标是使所有保留视图的预测边际熵 \( H(\bar{P}_{\text{adapted}}) \) 最小化，并加入L2正则项 \( \lambda_R \|\Delta z_T\|^2 \)。系数 \( \gamma \) 初始化为0，使用AdamW优化器单步更新（学习率5e-3）。
    4. **推理**：使用最终调整的原型对所有保留视图的平均softmax概率进行预测。

### 实验设计

- **使用的数据集与场景**：
    - **自然分布偏移**：ImageNet及其OOD变体（ImageNet-A, ImageNet-V2, ImageNet-R, ImageNet-Sketch）。
    - **细粒度分类（跨数据集泛化）**：Flowers102、DTD、OxfordPets、UCF101、Caltech101、Aircraft、EuroSAT、StanfordCars、Food101、SUN397。
    - **鲁棒性测试**：CIFAR10-C（最高严重等级5）。
- **基准与对比方法**：
    - **骨干网络**：CLIP ViT-B/16为主，部分实验使用MaPLe初始化或CLIP ViT-L/14。
    - **对比方法**：Zero-shot、Ensemble (7个通用模板)、CoOp、TPT、DiffTPT、C-TPT、TTL、TPS。所有TTA方法采用相同的单步更新设置进行公平比较。
- **评估指标**：Top-1准确率，报告三次随机种子的平均值和标准差。

### 资源与算力

- **GPU**：单张NVIDIA RTX8000 GPU（45GB内存）。
- **训练/推理耗时**：文中未报告总训练时长，但给出了推理速度对比：STS单样本0.09秒（依赖7个模板的Ensemble版本），TPT需0.75秒；STS内存占用1.4GB，TPT为17.6GB。
- **注**：论文没有说明完整实验（所有数据集）的总计算时长，但强调了STS的推理高效性。

### 实验数量与充分性

- **实验数量**：非常充分。主要包括：
    - 自然分布偏移实验（5个数据集，表1）。
    - 细粒度分类实验（10个数据集，表2）。
    - 鲁棒性实验（CIFAR10-C，图3a）。
    - 视图数影响分析（图3b）。
    - 更新步数消融（附录B.2）。
    - 共享vs逐类系数消融（附录B.3）。
    - 不同SVD选择方法对比（附录C）。
    - 更大规模VLM实验（ViT-L/14，附录B.4）。
    - 误差条报告（附录B.1）。
- **充分性与公平性**：实验覆盖了主流OOD和细粒度基准，对比方法均在同一设置下复现，消融研究充分，统计指标合理。总体客观公平。

### 论文的主要结论与发现

1. STS在OOD数据集上平均准确率62.64%，显著超过TPT（60.71%），且仅用极少参数。
2. STS Ensemble（7个模板）达到64.96%，在所有对比方法中最高。
3. 推理速度比TPT快8倍，内存占用减少12倍。
4. 在CIFAR10-C上，STS匹配TPT性能（差异<0.05%），优于TPS。
5. 共享系数向量与逐类系数的性能几乎相同（差距<0.03%），表明全局偏移足以应对域偏移。
6. 低秩子空间（前几个奇异向量）捕获了光谱能量的大部分，验证了利用低秩结构的有效性。

### 优点

- **方法创新**：首次将文本嵌入的SVD子空间用于VLM的测试时自适应，既高效又具有语义指导性。
- **计算高效**：无需反向传播编码器，仅优化少量系数，实现8×速度提升和12×内存节省，非常适合实时应用。
- **黑盒友好**：将VLM编码器视为冻住的特征提取器，不修改内部结构，适用于专有模型。
- **实验完备**：在多个OOD和细粒度数据集上验证，消融和鲁棒性分析丰富，统计报告规范。
- **自动确定秩**：采用Gavish-Donoho阈值自动选择子空间维度，避免手动调参。

### 不足与局限

1. **线性假设**：偏移量是子空间内的线性组合，对于高度复杂的非线性域偏移可能表达能力不足。
2. **增广视图线性缩放**：每个测试样本需要独立前向传播多个增广视图（默认64个），计算量与视图数线性相关，限制了极低延迟场景的适用性。
3. **数据集局限**：在EuroSAT（卫星图像）上表现不佳，作者指出这是一个已知的TTA困难场景；未在更多样化的领域（如医疗、自动驾驶）验证。
4. **超参数敏感**：虽然大部分超参数固定（如单步更新、学习率5e-3），但对不同域可能不是最优的，文中未进行跨域调参分析。
5. **更大规模模型验证不足**：仅在ViT-L/14上做了单种子实验（附录B.4），缺乏统计意义和更全面的对比。
6. **理论分析缺失**：对于为什么低秩子空间有效、收敛性如何等问题没有提供理论保证。

（完）
