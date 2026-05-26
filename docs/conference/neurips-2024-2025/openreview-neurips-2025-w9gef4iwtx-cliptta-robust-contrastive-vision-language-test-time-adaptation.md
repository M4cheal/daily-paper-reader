---
title: "CLIPTTA: Robust Contrastive Vision-Language Test-Time Adaptation"
title_zh: CLIPTTA：鲁棒的对比视觉语言测试时自适应
authors: "Marc Lafon, Gustavo Adolfo Vargas Hakim, Clément Rambour, Christian Desrosiers, Nicolas THOME"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=w9gEF4Iwtx"
tags: ["query:tta"]
score: 9.0
evidence: 基于对比损失的CLIP测试时自适应及理论分析
tldr: 视觉语言模型如CLIP在分布偏移下泛化能力下降。现有TTA常用熵最小化，但与CLIP的对比训练目标不匹配，导致伪标签漂移和类别崩溃。本文提出CLIPTTA，采用与CLIP预训练一致的软对比损失，并通过理论分析证明其批次感知设计有效缓解了崩溃风险。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9gef4iwtx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 806, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9gef4iwtx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9gef4iwtx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1389, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9gef4iwtx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9gef4iwtx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9gef4iwtx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1392, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9gef4iwtx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1156, \"height\": 572, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 500, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 808, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 767, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 594, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1445, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 761, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 667, \"height\": 806, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1454, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1456, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1457, \"height\": 1090, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1412, \"height\": 486, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1456, \"height\": 493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1455, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1456, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1455, \"height\": 613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 937, \"height\": 620, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 878, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1085, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 940, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1153, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9gef4iwtx/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1225, \"height\": 204, \"label\": \"Table\"}]"
motivation: 熵最小化与CLIP的对比学习训练目标不一致，导致自适应性能受限且易出现类别崩溃。
method: 提出软对比损失作为TTA目标，与CLIP预训练对齐，并采用批次感知设计。
result: 理论分析和实验验证了方法能有效避免崩溃，在多个基准上超越现有方法。
conclusion: CLIPTTA为VLM提供了与预训练目标一致的TTA方法，提升了鲁棒性。
---

## Abstract
Vision-language models (VLMs) like CLIP exhibit strong zero-shot capabilities but often fail to generalize under distribution shifts. Test-time adaptation (TTA) allows models to update at inference time without labeled data, typically via entropy minimization. However, this objective is fundamentally misaligned with the contrastive image-text training of VLMs, limiting adaptation performance and introducing failure modes such as pseudo-label drift and class collapse. We propose CLIPTTA, a new gradient-based TTA method for vision-language models that leverages a soft contrastive loss aligned with CLIP’s pre-training objective. We provide a theoretical analysis of CLIPTTA’s gradients, showing how its batch-aware design mitigates the risk of collapse. We further extend CLIPTTA to the open-set setting, where both in-distribution (ID) and out-of-distribution (OOD) samples are encountered, using an Outlier Contrastive Exposure (OCE) loss to improve OOD detection. Evaluated on 75 datasets spanning diverse distribution shifts, CLIPTTA consistently outperforms entropy-based objectives and is highly competitive with state-of-the-art TTA methods, outperforming them on a large number of datasets and exhibiting more stable performance across diverse shifts.

---

## 论文详细总结（自动生成）

# 论文《CLIPTTA: Robust Contrastive Vision-Language Test-Time Adaptation》中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：视觉-语言模型（VLM）如CLIP在零样本任务中表现优异，但在面对分布偏移（如合成损坏、域迁移、细粒度变化）时泛化能力显著下降。测试时自适应（TTA）允许模型在推理阶段无标签地更新参数，但主流方法（如TENT）采用**熵最小化**目标，该目标与VLM的**对比学习预训练目标**（图像-文本对比损失）存在根本性不对齐，导致伪标签漂移和类别崩溃两大失败模式。
- **核心问题**：如何设计一种更适合VLM梯度式TTA的损失函数，使其与预训练目标对齐，从而提升鲁棒性？
- **整体贡献**：提出CLIPTTA，一种基于**软对比损失**的TTA方法，与CLIP的预训练目标自然对齐，通过理论分析证明其批次感知设计能缓解崩溃风险，并扩展至开放集场景。

## 2. 方法论

### 核心思想
- 使用**软对比损失**（soft contrastive loss）替代传统熵最小化，该损失在批内同时计算图像到伪文本描述和文本到图像的熵，保留了CLIP对比学习的结构，同时显式建模伪标签的不确定性。

### 关键技术细节
- **软对比损失（Ls-cont）**：
  - 给定一个批次的N个样本，根据预测类别为每个图像生成伪文本描述（pseudo-caption）。
  - 计算图像与文本之间、文本与图像之间的概率分布（归一化在批次内），并计算其熵的负和作为损失：
    \[
    L_{\text{s-cont}} = -\sum_{i=1}^N \left[ \sum_{j=1}^N p(\hat{t}_j|x_i) \log p(\hat{t}_j|x_i) + \sum_{j=1}^N p(x_j|\hat{t}_i) \log p(x_j|\hat{t}_i) \right]
    \]
  - 该损失类似熵最小化的“软版本”，但作用于跨模态的批次级分布。

- **完整的CLIP TTA损失**：
  - 结合软对比损失、边际熵正则化项（促进预测多样性）以及类级别置信记忆（CCM，存储高置信样本）：
    \[
    L_{\text{CLIP TTA}} = \frac{1}{2} \left[ L_{\text{s-cont}} + L_{\text{s-cont}}^M \right] + \lambda_{\text{reg}} L_{\text{reg}}
    \]
  - 通过将当前批次和记忆批次损失平均，降低噪声敏感度。

- **理论分析**：
  - 推导了软对比损失的梯度形式：每个样本的梯度会收到批次内所有伪文本的加权贡献，其中权重β_i,j与相似度和置信度相关。这使得梯度可以在伪标签错误时指向正确类别（通过其他样本的修正），而熵方法会盲目强化错误预测。
  - 当类别不平衡趋于崩溃（某一类占绝对多数）时，梯度会自动衰减为零，形成自调节机制，防止崩溃。熵方法则无此机制。

- **开放集拓展**：
  - 使用MCM得分（最大类概率）作为异常检测依据，并引入可学习阈值α生成权重w_i（sigmoid函数）。
  - 提出**异常对比暴露损失（OCE）**，旨在拉大ID样本得分均值与OOD样本得分均值之间的差距，提升ID/OOD分离性能。
  - 最终优化目标：min L_CLIP TTA + λ_oce L_OCE，同时更新模型参数和阈值α。

## 3. 实验设计

### 数据集与场景
- **合成损坏**：CIFAR-10/100-C、ImageNet-C（各15种扰动，最高严重级别）。
- **域迁移**：VisDA-C、PACS、OfficeHome、ImageNet-Domains（ImageNet-V2/R/S/A）。
- **语义粗粒度**：CIFAR-10、CIFAR-100。
- **语义细粒度**：ImageNet及10个零样本数据集（Aircraft、Caltech101、Cars、DTD、EuroSAT、Flowers102、Food101、Pets、SUN397、UCF101）。
- **开放集TTA**：以SVHN为OOD（针对CIFAR-10/100），以Places365为OOD（针对ImageNet），并扩展至对应的损坏版本。

### 对比方法
- **熵基方法**：TENT、ETA、SAR、RoTTA。
- **CLIP专用方法**：CLIPArTT、WATT。
- **其他VLM TTA方法**：TPT（提示微调）、TDA（无梯度缓存法）。
- **开放集方法**：OSTTA、SoTTA、STAMP、UniEnt。
- **额外对比**：RPL、BATCLIP。

### 评价指标
- 闭集：Top-1准确率。
- 开放集：AUROC（AUC）、FPR95（假阳性率@95%真阳性率）。

### 实现细节
- 主干：CLIP ViT-B/16。
- 批次大小128，Adam优化器，学习率1e-4，每个批次10次迭代，非分集模式（不恢复参数）。
- 更新视觉编码器的归一化层仿射参数；开放集每批另加128个OOD图像。
- λ_reg = 1，λ_oce = 1。

## 4. 资源与算力
- 文中明确说明实验使用**两块NVIDIA V100 32GB GPU**。未提及训练总时长，但给出了单批次运行时间（CLIP TTA 315秒，TENT 312秒等，推测为整个数据集运行时间或单次推理时间），显存占用约8.1GB。

## 5. 实验数量与充分性
- **总实验数量**：覆盖**75个数据集**，包括4种分布偏移类型（损坏、域迁移、粗粒度、细粒度），消融实验（表4）、开放集实验（表3、表8、表9）、架构泛化（表18）、超参数敏感性（图7、表21-22）、运行时分析（表20）。
- **充分性**：实验设计较为全面，不仅对比了多类基线，还覆盖了不同困难程度（低初始准确率和高初始准确率）的场景。消融实验验证了三个组件（Ls-cont、Lreg、CCM）各自贡献。提供了统计显著性（95%置信区间）和多次重复结果，证明稳定性。
- **公平性**：所有方法在相同设置下（非分集、同批次大小、同主干）进行，基线超参数根据原文设置。对部分方法做了适应性调整（如CLIPArTT）。

## 6. 主要结论与发现
1. **软对比损失优于熵最小化**：在所有75个数据集上，CLIP TTA（仅软对比损失）平均提升超过TENT约9.8个百分点；在低准确率场景（如CIFAR-100-C、ImageNet-C）提升尤为显著（+19.4%和+22.7%）。
2. **稳定性和抗崩溃能力**：CLIP TTA在自适应过程中准确率持续上升（图4a），预测熵保持稳定（图4b），误标退化率仅7%而TENT超过30%（图4c）。
3. **开放集场景最优**：CLIP TTA+OCE在ImageNet+Places下AUC达97.7%，FPR95降至9.7%，超过专为开放集设计的UniEnt（AUC 95.4%，FPR95 17.1%）。
4. **对不同主干和模型的泛化性**：在CLIP-ResNet50、ViT-B/32、ViT-L/14以及SigLIP上均取得一致提升。
5. **超参数鲁棒**：λ_reg在0.5-2范围内性能稳定；λ_oce在0.25-2范围内有效提升OOD检测而不显著降低准确率；即使在批次大小为1时，借助CCM仍能达到93.4%准确率（TENT仅40.3%）。

## 7. 优点
- **方法原理明确**：损失函数设计直接继承CLIP预训练目标，有理论梯度分析支持，可解释性强。
- **批处理智慧**：梯度内自然地利用批内样本之间的对比信息，实现伪标签错误纠正和类别崩溃抑制，不需要额外滤波或正则化。
- **简单高效**：仅需修改损失函数，不改变网络结构或引入复杂模块，计算开销与TENT相当（表20）。
- **实验坚实**：覆盖大规模、多样化数据集，包含多种分布偏移类型，结果可靠；开放集拓展设计新颖且有效。

## 8. 不足与局限
- **局限一**：当前仅利用全局图像-文本交互，可能对细粒度或局部偏移的适应不够充分。
- **局限二**：评估限于分类任务，未拓展至更通用的多模态设置（如图像分割、视觉问答）。
- **局限三**：与大多数TTA方法类似，需要额外的推理时间和计算资源，不适用于对实时性要求极高的部署场景。
- **局限四**：开放集实验中OOD数据集仅选取SVHN和Places365，规模有限，可能在更广泛OOD类型下泛化性有待验证。
- **局限五**：实验仅采用ViT-B/16作为主要主干，虽验证了其他架构，但整体基准均基于同一预训练模型，可能存在偏差风险。

（完）
