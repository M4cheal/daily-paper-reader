---
title: Statistics Caching Test-Time Adaptation for Vision-Language Models
title_zh: 视觉-语言模型的统计缓存测试时自适应
authors: "Zenghao Guan, Zhou Yucan, Wu Liu, Xiaoyan Gu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=iqsjzVqmWF"
tags: ["query:tta"]
score: 8.0
evidence: 用于视觉-语言模型的统计缓存测试时自适应
tldr: 测试时自适应需要在测试过程中持续积累知识，但传统特征缓存方法容易遗忘且受限于固定大小。SCA通过维护增量更新的特征统计量（如均值和协方差）来替代原始特征，将过去特征的重用转化为最小二乘问题。该方法在多个VLM任务上实现了鲁棒且连续的知识积累，性能优于现有缓存方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqsjzvqmwf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1427, \"height\": 816, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqsjzvqmwf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 481, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqsjzvqmwf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1314, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqsjzvqmwf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 219, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqsjzvqmwf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1437, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqsjzvqmwf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1155, \"height\": 775, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqsjzvqmwf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1419, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqsjzvqmwf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1420, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqsjzvqmwf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1277, \"height\": 508, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-iqsjzvqmwf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 961, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iqsjzvqmwf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 919, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iqsjzvqmwf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 654, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iqsjzvqmwf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 758, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iqsjzvqmwf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1430, \"height\": 615, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iqsjzvqmwf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iqsjzvqmwf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1440, \"height\": 228, \"label\": \"Table\"}]"
motivation: 现有缓存式TTA方法受限于固定容量且容易遗忘，无法鲁棒地积累知识。
method: 利用最小二乘公式，维护特征统计量（均值、协方差）而非原始特征，实现无容量限制的增量更新。
result: 在多个VLM域迁移基准上，SCA持续提升性能，超越了固定缓存方法。
conclusion: 统计缓存策略为TTA提供了一种高效且可扩展的知识积累方式，适用于多模态模型。
---

## Abstract
Test-time adaptation (TTA) for Vision-Language Models (VLMs) aims to enhance performance on unseen test data. However, existing methods struggle to achieve robust and continuous knowledge accumulation during test time. To address this, we propose Statistics Caching test-time Adaptation (SCA), a novel cache-based approach. Unlike traditional feature-caching methods prone to forgetting, SCA continuously accumulates task-specific knowledge from all encountered test samples. By formulating the reuse of past features as a least squares problem, SCA avoids storing raw features and instead maintains compact, incrementally updated feature statistics. This design enables efficient online adaptation without the limitations of fixed-size caches, ensuring that the accumulated knowledge grows persistently over time. Furthermore, we introduce adaptive strategies that leverage the VLM's prediction uncertainty to reduce the impact of noisy pseudo-labels and dynamically balance multiple prediction sources, leading to more robust and reliable performance. Extensive experiments demonstrate that SCA achieves compelling performance while maintaining competitive computational efficiency.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义

**研究动机与背景**  
视觉语言模型（如CLIP）在零样本任务中表现优异，但在真实场景中面对分布漂移（out-of-domain / out-of-distribution）时性能下降。测试时自适应（Test-Time Adaptation, TTA）旨在仅利用无标签的测试数据在线调整模型，无需额外标注。然而，现有TTA方法存在两大不足：  
- **测试时提示调优方法**（如TPT、DiffTPT）为每个样本独立优化提示，丢弃先前样本信息，无法积累知识，且需反向传播导致计算开销大。  
- **缓存方法**（如DPE、TDA）虽尝试存储特征，但受限于固定容量的缓存，容易因低置信度错误样本导致**灾难性遗忘**（错误特征覆盖正确知识）和**阻塞效应**（早期高置信度错误样本占据缓存槽位，阻止后续正确样本进入）。  

因此，论文的核心问题是：**如何实现鲁棒且持续的知识积累，避免遗忘和噪声干扰，同时保持计算效率？**

## 2. 方法论

**核心思想**  
提出**统计缓存测试时自适应（SCA）**，将过去所有测试样本的特征复用建模为**最小二乘问题**，只需维护紧凑的**特征统计量**（Gram矩阵G和交叉统计量C），而非存储原始特征，从而实现无遗忘的知识积累，并支持增量更新。

**关键技术细节**  

1. **统计积累**  
   - 定义 \( G_{1:t} = X_{1:t}^\top X_{1:t} \in \mathbb{R}^{d \times d} \) 和 \( C_{1:t} = X_{1:t}^\top Y_{1:t} \in \mathbb{R}^{d \times K} \)。  
   - 利用闭式解 \( W_t = (G_{1:t} + \gamma I)^{-1} C_{1:t} \) 构建分类器。  
   - 在线更新：每来一个样本 \( X_t \)，更新 \( G_{1:t} = G_{1:t-1} + X_t^\top X_t \)，\( C_{1:t} = C_{1:t-1} + X_t^\top \hat{Y}_t \)。

2. **动态软伪标签分配**  
   - 为解决硬伪标签的噪声放大问题，根据零样本预测概率动态生成软标签。  
   - 选择最小类集Ω，使得累积概率 ≥ τ·(1-p_top)，然后对Ω内概率进行softmax后作为伪标签。  
   - 对不确定样本产生更软的标签，对确信样本产生更锐利的标签。

3. **实例级自适应融合**  
   - 分别计算缓存分类器和零样本分类器的预测熵，通过softmax得到自适应权重：  
     \( [\alpha_1, \alpha_2] = \text{softmax}(-\beta [H_{\text{cache}}, H_{\text{text}}]) \)。  
   - 融合logits：\( z_{\text{final}} = \alpha_1 z_{\text{cache}} + \alpha_2 z_{\text{text}} \)。  
   - 默认β=0.5，无需针对每个数据集调优融合系数。

**算法流程**（文字说明）  
- 初始化 \( G = \gamma I \)，\( C = 0 \)。  
- 对每个测试样本：  
  1. 提取图像特征 \( X_t \)，零样本预测得到概率 \( p_{\text{text}} \)。  
  2. 根据动态软标签策略生成伪标签 \( \hat{Y}_t \)。  
  3. 更新 \( G \leftarrow G + X_t^\top X_t \)，\( C \leftarrow C + X_t^\top \hat{Y}_t \)。  
  4. 计算缓存分类器 \( W_t = G^{-1} C \)，得到缓存logits \( z_{\text{cache}} = X_t W_t \)。  
  5. 计算零样本logits \( z_{\text{text}} \)。  
  6. 计算两类预测熵，自适应融合得到最终logits，取argmax作为预测。

## 3. 实验设计

**数据集与benchmark**  
- **跨域基准（Cross-Domain）**：10个数据集，包括FGVCAircraft、Caltech101、StanfordCars、DTD、EuroSAT、Flowers102、Food101、OxfordPets、SUN397、UCF101。  
- **OOD基准（Out-of-Distribution）**：ImageNet及其4个变体：ImageNet-A、ImageNet-V2、ImageNet-R、ImageNet-Sketch。  
- **总计15个数据集**，覆盖细粒度识别、场景识别、卫星图像、纹理、动作等多种领域。

**对比方法**  
- 零样本CLIP（简单提示/集成提示）。  
- 少样本方法：CoOp（16-shot）、CoCoOp。  
- 测试时提示调优：TPT、DiffTPT、Dynaprompt。  
- 缓存方法：TDA、DMN-ZS、DPE、BCA（贝叶斯方法）。  
- 排除了依赖外部强模型（如ViT-L-14）或跨样本批量信息的RLCF、COSMIC、transductive方法。

**评估指标**：Top-1准确率。

## 4. 资源与算力

- 论文明确说明：所有实验在**单张NVIDIA A100 RTX GPU**上运行。  
- 未具体报告单次训练时间或总GPU小时，但提供了计算效率比较（表3）：在SUN397上每张图像处理时间SCA为0.012秒，远快于TPT（0.218秒），略慢于TDA（0.009秒）。  
- 整体算力需求较低，因其免除了反向传播。

## 5. 实验数量与充分性

**实验数量**  
- 在15个数据集上进行了完整的性能对比（表1、表2）。  
- 消融实验（表4）：验证统计积累和动态软标签的有效性。  
- 融合系数消融（图4）：对比固定α和自适应α。  
- 超参数分析（图5左、中）：β和τ的敏感性。  
- 样本顺序敏感性（图5右）：验证对测试流顺序的鲁棒性。  
- 额外附录实验：遗忘与阻塞的量化分析、不同缓存大小的影响、与DMN-ZS的公平对比、提示初始化影响等。

**充分性与公平性**  
- 对比方法均采用官方或公开结果，设置相同（如batch size=1）。  
- 注意：OOD基准上ResNet-50的性能略低于DPE，但论文指出SCA无需额外训练；在ViT-B/16上全面超越。  
- 消融实验覆盖统计积累和软标签两个关键设计，且调整不同缓存大小验证了SCA的优势来源不只是二阶信息。  
- 实验设计较为全面，未发现明显偏向。

## 6. 主要结论与发现

- SCA在跨域基准上平均准确率显著优于现有方法（ResNet-50下63.29%，ViT-B/16下70.34%），比DPE高约0.94%~1.36%。  
- 在OOD基准上，ViT-B/16下平均64.77%，优于所有对比方法。  
- 与TPT相比，计算效率提升10倍以上，且无需反向传播。  
- 统计积累能有效缓解遗忘和阻塞问题，动态软标签比硬标签带来更稳定的知识积累。  
- 自适应融合无需针对每个数据集调参，且在不同数据集上表现稳健。

## 7. 优点

- **创新性强**：将缓存从原始特征改为特征统计量，从根本上解决了容量限制和遗忘问题。  
- **无遗忘的知识积累**：通过增量更新Gram矩阵和交叉统计量，利用所有历史样本。  
- **鲁棒性**：动态软标签利用不确定性信息，减少噪声伪标签影响；自适应融合根据熵动态权衡缓存与零样本输出。  
- **计算高效**：免除了反向传播，推理速度接近纯特征提取。  
- **超参数友好**：默认参数在多个数据集上表现良好，无需复杂调优。  
- **实验详尽**：在15个数据集、两种Backbone上验证，消融和敏感性分析充分。

## 8. 不足与局限

- **存储开销**：虽然避免了存储海量特征，但Gram矩阵 \( d \times d \) 当特征维度较大时仍有一定存储需求（论文指出在类别数多时比传统缓存更优，但维度d通常为512/768，仍可接受）。  
- **错误累积仍存在**：软标签仅能缓解但不能完全消除错误积累，理想情况（有真实标签）仍有差距。  
- **仅关注单域场景**：所有测试样本来自同一数据集，未考虑多域混合场景。论文在结论中承认这一局限，并提出未来方向（按域分别积累统计量）。  
- **OOD基准ResNet-50上略低于DPE**：虽解释为DPE需额外训练，但实际准确率略低仍属不足。  
- **未报告方差或统计显著性**：实验缺少多次重复的误差棒，可能影响对稳定性的判断。  
- **硬件资源细节不够充分**：未给出总GPU小时数，难以精确复现算力需求。

（完）
