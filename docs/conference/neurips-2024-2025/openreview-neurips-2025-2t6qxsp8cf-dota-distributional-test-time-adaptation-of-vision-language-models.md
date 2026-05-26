---
title: "DOTA: Distributional Test-time Adaptation of Vision-Language Models"
title_zh: DOTA：面向视觉语言模型的分布性测试时自适应
authors: "Zongbo Han, Jialong Yang, Guangyu Wang, Junfan Li, Qianli Xu, Mike Zheng Shou, Changqing Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2T6QXSP8Cf"
tags: ["query:tta"]
score: 9.0
evidence: 面向视觉语言模型的分布性测试时自适应
tldr: DOTA针对缓存式测试时自适应中灾难性遗忘问题，提出分布性测试时自适应方法。不是简单存储样本特征，而是维护整体分布统计量，在更新时可以无缝融合新知识而不丢失旧信息。实验表明，该方法在多种视觉语言任务上显著优于现有缓存方法，且不增加存储开销。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2t6qxsp8cf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 677, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2t6qxsp8cf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2t6qxsp8cf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 649, \"height\": 464, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1404, \"height\": 551, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 867, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 544, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 617, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 698, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 657, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 816, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1193, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1159, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1454, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1019, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1303, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1336, \"height\": 851, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1451, \"height\": 115, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1457, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1305, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2t6qxsp8cf/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1453, \"height\": 249, \"label\": \"Table\"}]"
motivation: 现有缓存式测试时自适应方法因容量限制导致灾难性遗忘。
method: 提出分布性统计量维护方法，替代原始特征缓存，实现无损知识积累。
result: 在多个视觉语言基准上，DOTA优于现有方法且无需额外存储。
conclusion: 分布性缓存机制为视觉语言模型的测试时自适应提供了高效的解决方案。
---

## Abstract
Vision-language foundation models (VLMs), such as CLIP, exhibit remarkable performance across a wide range of tasks. However, deploying these models can be unreliable when significant distribution gaps exist between training and test data, while fine-tuning for diverse scenarios is often costly. Cache-based test-time adapters offer an efficient alternative by storing representative test samples to guide subsequent classifications. Yet, these methods typically employ naive cache management with limited capacity, leading to severe catastrophic forgetting when samples are inevitably dropped during updates. In this paper, we propose DOTA (DistributiOnal Test-time Adaptation), a simple yet effective method addressing this limitation. Crucially, instead of merely memorizing individual test samples, DOTA continuously estimates the underlying distribution of the test data stream. Test-time posterior probabilities are then computed using these dynamically estimated distributions via Bayes' theorem for adaptation. This distribution-centric approach enables the model to continually learn and adapt to the deployment environment. Extensive experiments validate that DOTA significantly mitigates forgetting and achieves state-of-the-art performance compared to existing methods.

---

## 论文详细总结（自动生成）

# 论文总览：DOTA：面向视觉语言模型的分布性测试时自适应

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：视觉语言基础模型（如CLIP）在训练数据和测试数据之间存在显著分布偏移时性能不稳定，而传统测试时自适应方法中基于缓存的方法受限于固定缓存容量，存储少量代表性样本，在更新时被迫丢弃旧样本，导致严重灾难性遗忘，无法持续适应不断变化的测试环境。
- **整体含义**：本文提出从“实例级存储”转向“分布级估计”，通过持续估算测试数据流中各类别的统计分布（均值、协方差），利用贝叶斯定理计算后验概率实现自适应，从而克服缓存方法的遗忘问题，使模型能在测试过程中持续学习并保持稳定性能。

## 2. 论文提出的方法论

### 核心思想
- 假设每个类别的图像嵌入服从高斯分布，在线估计各类的均值和协方差矩阵。
- 利用零样本预测概率作为软标签（通过EM算法一步迭代），对样本加权，无需真实标签。
- 采用在线更新公式（仿照Dasgupta & Hsu 2007），逐批更新分布参数。
- 最终通过贝叶斯判别函数计算后验概率，并与零样本分类结果动态融合（融合系数 λ = min(ρc, η)，随测试样本数增加而增大）。

### 关键技术细节
- **在线分布估计**：初始化 μₖ = ω1, Σₖ = σ²I；每步根据零样本概率加权更新均值和协方差，累积有效样本量 cₖ。
- **协方差矩阵简化**：使用所有类别共享的协方差矩阵减少求逆次数，并施加收缩正则化（ϵ=1e-4）保证可逆性。
- **动态融合**：P_final = softmax( cos(x,wₖ)/τ + λ·fₖ(x) )，其中 λ 从0逐渐增至 η。

### 伪代码（文字描述）
1. 初始化各类别分布参数（均值、协方差）和有效样本数。
2. 对每个测试样本：
   - 计算零样本概率（式1）。
   - 用式(6)在线更新均值和协方差。
   - 计算测试时后验概率（式2）。
   - 通过式(7)动态融合零样本和测试时结果，得到最终预测。

## 3. 实验设计

### 使用的数据集和场景
- **跨域泛化**：10个数据集（Aircraft、Caltech101、Cars、DTD、EuroSAT、Flower102、Food101、Pets、SUN397、UCF101）。
- **自然分布偏移**：ImageNet、ImageNet-A、ImageNet-R、ImageNet-S、ImageNet-V2。
- **医学图像**：Kather Colon、PanNuke、WSSS4LUAD，使用病理基础模型PLIP。
- **非i.i.d.数据流**：使用Dirichlet分布模拟不同非均匀程度（5/10个时间切片）。

### 对比方法
- 零样本CLIP、TPT、DiffTPT、TDA、BoostAdapter、HisTPT、ZERO、DMN等。
- 所有对比方法采用相同骨干网络（ViT-B/16）和相同评价指标（Top-1准确率）。

## 4. 资源与算力
- 论文明确说明：所有实验使用**单张NVIDIA RTX 4090 GPU**和**12核Intel Xeon Platinum 8352V CPU**。
- 推理时间对比（ImageNet数据集，ViT-B/16）：DOTA推理时间22分钟，与TDA相当；TPT需要447分钟，DiffTPT需要1346分钟（61倍于DOTA）。

## 5. 实验数量与充分性
- 主要实验包括：
  - 跨域泛化（10个数据集，表1）及自然分布偏移（4个数据集，表2）。
  - 医学图像（3个数据集，表3）。
  - 推理时间对比（表4）。
  - 失败案例分析（样本不足，表5）。
  - 连续学习能力分析（图3、表6）。
  - 消融实验（表7）：软标签 vs 高置信伪标签、是否使用协方差。
  - 超参数分析（表8）：σ²、ρ、η。
  - 统计显著性（表17-19）：5个随机种子，给出均值、标准差、95%置信区间。
  - 非i.i.d.测试（表13-14）。
  - 额外遗忘实验（表9-11）。
- **充分性评价**：实验覆盖了多种数据分布场景、多种基础模型、多个维度分析，且提供了统计误差棒和随机种子重复，对比公平（相同骨干、相同评价指标），消融设计合理，结论客观。

## 6. 论文的主要结论与发现

- **持续学习能力**：DOTA随测试样本增多性能持续提升，而TDA出现先升后降的遗忘现象。
- **性能优势**：在跨域泛化平均提升1.03%（69.71% vs 68.68% BoostAdapter），自然分布偏移提升1.21%（66.31% vs 65.10% TDA），医学图像提升6.89%（70.56% vs 63.67% TDA）。
- **效率**：与TDA推理速度相当（约22分钟/ImageNet），远快于TPT等梯度方法。
- **鲁棒性**：对非i.i.d.数据流和不同数据顺序均有强鲁棒性。
- **超参数敏感性低**：性能在小范围内波动，仍始终优于零样本。

## 7. 优点

- **方法论创新**：从实例缓存转向分布估计，从根本上缓解了灾难性遗忘，是测试时自适应领域的新范式。
- **高效无梯度**：无需回传梯度，适合实时部署。
- **理论支撑**：EM算法解释，零样本概率作为软标签的合理性有证明；在线更新公式有收敛保证。
- **实验充分**：涵盖多种任务、多种基模型、统计显著性检验、非i.i.d.测试等，验证了泛化性和鲁棒性。
- **代码开源**（https://github.com/skylineeeeen/DOTA）。

## 8. 不足与局限

- **高斯分布假设限制**：每个类别单高斯不能很好地建模多模态或复杂分布，可能影响性能（文中提及）。
- **均匀先验假设**：假设每个类别先验概率相等，与现实不平衡场景不符，未来可引入自适应先验估计。
- **融合策略启发式**：动态融合系数λ = min(ρc, η)缺少理论最优性，可能不是最优解。
- **样本不足时的退化**：当每类样本极少（如ImageNetV2中每类10张），性能略低于TDA（表5），说明分布估计对样本量有依赖。
- **可扩展性**：虽使用共享协方差减少了求逆次数，但若类别数极大（如10万类），参数更新和矩阵求逆可能仍存挑战（文中未讨论）。
- **实验局限性**：仅基于CLIP ViT-B/16和PLIP模型，未扩展到更大模型（如ViT-L）或其他VLM系列（如BLIP、ALIGN），泛化性需进一步验证。

（完）
