---
title: Lightweight Frequency Masker for Cross-Domain  Few-Shot Semantic Segmentation
title_zh: 面向跨域少样本语义分割的轻量级频率掩码器
authors: "Jintao Tong, Yixiong Zou, Yuhua Li, Ruixuan Li"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=GCmmy4At6i"
tags: ["query:ris"]
score: 5.0
evidence: 轻量级频率掩码器处理跨域少样本分割中的域偏移
tldr: "跨域少样本分割中域间隙导致性能下降，本文发现频率滤波可显著提升性能，并提出轻量级频率掩码器来降低特征图跨通道相关性。实验在多个跨域分割场景下实现高达14% mIoU提升，揭示频率信息在域泛化中的关键作用，对RIS域偏移具有启发意义。"
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-gcmmy4at6i/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1398, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gcmmy4at6i/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gcmmy4at6i/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gcmmy4at6i/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gcmmy4at6i/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 735, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gcmmy4at6i/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1447, \"height\": 274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gcmmy4at6i/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 560, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gcmmy4at6i/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1450, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gcmmy4at6i/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1449, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gcmmy4at6i/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1085, \"height\": 543, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-gcmmy4at6i/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gcmmy4at6i/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1305, \"height\": 523, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gcmmy4at6i/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 698, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gcmmy4at6i/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 611, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gcmmy4at6i/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 661, \"height\": 150, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gcmmy4at6i/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 697, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gcmmy4at6i/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 813, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gcmmy4at6i/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 700, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gcmmy4at6i/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 697, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gcmmy4at6i/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1233, \"height\": 262, \"label\": \"Table\"}]"
motivation: 跨域少样本分割中源域与目标域间domain gap导致性能剧降。
method: 发现对目标域进行不同频率成分滤波可大幅提升性能，据此设计轻量级频率掩码器减少特征间跨通道相关性。
result: "在多个跨域少样本分割数据集上实现最高14% mIoU提升。"
conclusion: 频率掩码是一种简单有效的跨域分割域偏移缓解手段。
---

## Abstract
Cross-domain few-shot segmentation (CD-FSS) is proposed to first pre-train the model on a large-scale source-domain dataset, and then transfer the model to data-scarce target-domain datasets for pixel-level segmentation. The significant domain gap between the source and target datasets leads to a sharp decline in the performance of existing few-shot segmentation (FSS) methods in cross-domain scenarios. In this work, we discover an intriguing phenomenon: simply filtering different frequency components for target domains can lead to a significant performance improvement, sometimes even as high as 14% mIoU. Then, we delve into this phenomenon for an interpretation, and find such improvements stem from the reduced inter-channel correlation in feature maps, which benefits CD-FSS with enhanced robustness against domain gaps and larger activated regions for segmentation. Based on this, we propose a lightweight frequency masker, which further reduces channel correlations by an Amplitude-Phase Masker (APM) module and an Adaptive Channel Phase Attention (ACPA) module. Notably, APM introduces only 0.01% additional parameters but improves the average performance by over 10%, and ACPA imports only 2.5% parameters but further improves the performance by over 1.5%, which significantly surpasses the state-of-the-art CD-FSS methods.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义

- **研究背景**：少样本语义分割（FSS）旨在从有限标注样本中分割未见类别，但在源域（如PASCAL VOC）与目标域（如医学图像、卫星图像）之间存在显著域偏移时，现有方法性能急剧下降。
- **核心问题**：跨域少样本语义分割（CD-FSS）面临严重的域间隙，导致模型泛化能力不足。
- **整体含义**：本文从频域角度探索域偏移问题，发现简单滤波不同频率成分即可显著提升性能，并据此提出轻量级频率掩码器，以极小参数代价大幅缓解域间隙，为CD-FSS提供了一种高效、可解释的解决方案。

---

## 2. 方法论

### 核心思想
- 滤波频率成分（特别是调整幅度和相位）可降低特征图通道间的互信息（即减少通道相关性），从而缓解通道偏差、扩大激活区域，提升跨域鲁棒性。
- 从数学上推导：特征通道间的空间相关性可转化为频域中相位差与幅度差的函数，因此通过频域操作可实现特征通道解耦。

### 关键技术细节
- **整体流程**：采用 episodic 训练方式，在源域预训练模型，在目标域微调阶段插入两个轻量模块。
- **Amplitude-Phase Masker (APM)**：
  - 对特征图进行 FFT，分解为幅值谱 A 和相位谱 P。
  - 用可学习的掩码（sigmoid 激活）分别对 A 和 P 做哈达玛积，滤波负面频率成分。
  - 再通过 IFFT 恢复增强后的特征图。
  - 提供两种变体：APM-S（h×w 矩阵，参数极少）和 APM-M（c×h×w 矩阵，参数稍多）。
- **Adaptive Channel Phase Attention (ACPA)**：
  - 基于 APM 增强后的特征图，利用相位信息（视为内容表示）通过 SE 模块生成通道注意力权重，聚焦有效通道并对齐支撑集与查询集特征空间。
- **损失与优化**：在目标域微调阶段，仅优化 APM 和 ACPA（不更新主干网络），通过交叉熵损失迭代 60 轮。

### 公式与算法流程（文字说明）
1. 提取特征图 → FFT → 分解为 A 和 P。
2. APM：A_enh = sigmoid(M_a) ⊗ A，P_enh = sigmoid(M_p) ⊗ P。
3. IFFT 得到 F_enh。
4. ACPA：对 P_enh 用 SE 模块得到通道权重 W_phase，加权到 F_enh 得到最终特征。
5. 使用余弦相似度计算支撑-查询亲和度图，输入解码器生成分割结果。

---

## 3. 实验设计

- **源域**：PASCAL-5i（基于 PASCAL VOC 2012 + SDS 增强）。
- **目标域**：四个具有较大域间隙的数据集：
  - FSS-1000（自然图像，1000 类）
  - Deepglobe（卫星图像，7 类，803 张）
  - ISIC2018（皮肤镜病变图像）
  - Chest X-ray（胸部 X 光片，结核诊断）
- **基准与对比方法**：
  - 基线：HSNet（ICCV 2021）
  - 对比方法：PANet、CaNet、RPMMs、PFENet、RePRI、PATNet 等 10 余种 FSS/CD-FSS 方法。
  - 额外对比：频率域方法（DFF、GFNet、ARP、DAC）和相关性降低方法（MMC、SRIP、whitening）。
  - 也对比了基于 SAM 的 PerSAM 和基于 Transformer 的 FPTrans。
- **评估指标**：mIoU（1-shot 和 5-shot）。

---

## 4. 资源与算力

- 论文未明确说明 GPU 型号、数量、总训练时长等具体算力信息。
- 仅在实现细节中提到：使用 ResNet-50 编码器（ImageNet 预训练），图像尺寸 400×400，优化器 Adam（学习率 1e-3），目标域微调阶段分别设置不同学习率（0.1/0.01/1e-5），每任务 60 轮迭代。
- 代码已开源（GitHub）。

---

## 5. 实验数量与充分性

- **主要实验**：在 4 个目标域上报告 1-shot 和 5-shot 结果，对比 10+ 种方法。
- **消融实验**：逐一验证 APM-S、APM-M、ACPA 模块的效果，以及两者组合。
- **额外实验**：
  - 在 Transformer 架构（FPTrans）上验证方法无关性。
  - 与全参数微调、空间域特征解耦（MI Loss）对比。
  - 与多种频率域/相关性降低方法对比。
  - 分析 APM 对通道互信息、CDF 分布、CKA 距离的影响。
  - 可视化特征热图、相位差直方图、被滤波的频率成分。
- **充分性评价**：实验覆盖了多个具有代表性的跨域场景（自然、卫星、皮肤镜、X光），消融充分，公平对比了 SOTA 和基线变体，结论可靠。但缺少在更多目标域（如遥感、医学其他模态）上的测试，也缺少对更大规模骨干网络（如 ResNet-101）的评估。

---

## 6. 主要结论与发现

1. **关键发现**：简单滤波目标域图像的特定频率成分可显著提升 CD-FSS 性能（最高 14% mIoU），其机制是通过降低特征图通道间相关性来实现通道解耦，从而缓解通道偏差、扩大激活区域。
2. **方法有效性**：APM-S 以 0.01% 参数提升平均 mIoU 超 10%；加入 ACPA 后再提升 1.5%。完整方法（APM-M + ACPA）在 1-shot 和 5-shot 上分别达到 60.03% 和 65.18% 平均 mIoU，远超现有 SOTA（PATNet 分别为 56.06% 和 61.99%）。
3. **模型无关性**：方法同样适用于 Transformer 架构（FPTrans），进一步提升性能。
4. **优于传统方法**：频率域滤波比全参数微调、空间域特征解耦、正交性约束、白化等手段更轻量、更稳定、效果更好。

---

## 7. 优点

- **极轻量**：APM-S 仅增加 0.01% 参数，ACPA 增加 2.5%，整个方法无需在源域训练，只在目标域微调少量可学习参数。
- **强解释性**：通过数学推导和实验（互信息、MMC曲线、相位差直方图、CDF、热力图）深入解释了频率滤波 → 降低通道相关性 → 提升泛化与激活区域的内在机制。
- **跨域效果显著**：在四个差异极大的目标域上均取得大幅提升，尤其在 Chest X-ray 上提升超过 30% mIoU。
- **无需修改主干网络**：即插即用，兼容多种架构（CNN 和 Transformer）。

---

## 8. 不足与局限

- **实验局限性**：
  - 仅在 ResNet-50 上作为主要骨干进行完整实验，未展示在更大骨干（如 ResNet-101、ViT-L）上的表现。
  - 仅在四个目标域上验证，覆盖的跨域场景数量有限（缺少遥感、医学其他领域如 OCT、CT 等）。
  - 未提供误差棒或多次重复实验的统计显著性分析。
- **潜在偏差风险**：
  - APM 的掩码在目标域微调时依赖少量标注样本，当标注样本极不充分（如 1-shot 中仅有一张标注支撑图）时，可能过拟合到单一实例；作者在 Chest X-ray 上设置了较高学习率（0.1）可能隐含该问题。
  - 方法需要手动为每个目标域设置不同的学习率（0.1/0.01/1e-5），调参成本较高，通用性受限。
- **应用限制**：
  - 当前设计仅应用于中间特征图（conv5_x，空间尺寸 13×13），若特征图分辨率更大，APM 的 h×w 掩码空间复杂度可能上升。
  - 未讨论在实时或资源受限设备上的推理效率。

---

（完）
