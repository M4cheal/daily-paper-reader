---
title: "SAM as the Guide: Mastering Pseudo-Label Refinement in Semi-Supervised Referring Expression Segmentation"
title_zh: SAM作为指导：半监督指代表达分割中的伪标签精炼
authors: "Danni Yang, Jiayi Ji, Yiwei Ma, Tianyu Guo, Haowei Wang, Xiaoshuai Sun, Rongrong Ji"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=M5kn9NKIs4"
tags: ["query:ris"]
score: 10.0
evidence: 半监督指代表达分割，直接对应指代图像分割需求
tldr: 本文提出半监督指代表达分割框架SemiRES，针对RES中伪标签噪声尤其是边界不准确的问题，引入SAM模型进行伪标签精炼。SemiRES提供两种匹配策略（IoU最优匹配和组合部分集成）从SAM输出中提取精确掩码，从而指导学生模型训练。实验表明该方法有效提升了半监督RES的性能，为减少标注依赖提供了可行方案。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-m5kn9nkis4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-m5kn9nkis4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1745, \"height\": 680, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-m5kn9nkis4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 718, \"height\": 1069, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-m5kn9nkis4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1645, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-m5kn9nkis4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1740, \"height\": 970, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-m5kn9nkis4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1754, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-m5kn9nkis4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 778, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-m5kn9nkis4/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1434, \"height\": 2185, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-m5kn9nkis4/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1475, \"height\": 2273, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-m5kn9nkis4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1781, \"height\": 877, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-m5kn9nkis4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 764, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-m5kn9nkis4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 819, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-m5kn9nkis4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 787, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-m5kn9nkis4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-m5kn9nkis4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-m5kn9nkis4/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 869, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-m5kn9nkis4/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 792, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-m5kn9nkis4/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 901, \"height\": 275, \"label\": \"Table\"}]"
motivation: 半监督指代表达分割面临伪标签噪声问题，尤其是目标边界不准确。
method: 提出SemiRES框架，利用SAM的精确边界提取能力，通过IoU最优匹配和组合部分集成两种策略精炼伪标签，并基于精炼后的掩码训练学生模型。
result: 在半监督RES设置下，SemiRES显著优于现有方法，有效提升了分割精度。
conclusion: 证明了利用SAM进行伪标签精炼在半监督指代分割中的有效性，为低资源场景下的RES提供了新思路。
---

## Abstract
In this paper, we introduce SemiRES, a semi-supervised framework that effectively leverages a combination of labeled and unlabeled data to perform RES. A significant hurdle in applying semi-supervised techniques to RES is the prevalence of noisy pseudo-labels, particularly at the boundaries of objects. SemiRES incorporates the Segment Anything Model (SAM), renowned for its precise boundary demarcation, to improve the accuracy of these pseudo-labels. Within SemiRES, we offer two alternative matching strategies: IoU-based Optimal Matching (IOM) and Composite Parts Integration (CPI). These strategies are designed to extract the most accurate masks from SAM's output, thus guiding the training of the student model with enhanced precision. In instances where a precise mask cannot be matched from the available candidates, we develop the Pixel-Wise Adjustment (PWA) strategy, guiding the student model's training directly by the pseudo-labels. Extensive experiments on three RES benchmarks—RefCOCO, RefCOCO+, and G-Ref reveal its superior performance compared to fully supervised methods, especially in low-data scenarios. Remarkably, with only 1% labeled data, our SemiRES outperforms the supervised baseline by a large margin, e.g. +18.64% gains on RefCOCO val set.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

**研究动机与背景：**  
指代分割（Referring Expression Segmentation, RES）需要根据自然语言描述对图像中的目标进行像素级分割。然而，获取高质量的分割标注成本极高（平均每标注一个掩码约需79.1秒），这严重限制了RES在医疗影像、自动驾驶等领域的应用。现有半监督学习方法应用于RES时面临伪标签噪声严重的问题，尤其在目标边界处不准确。因此，本文旨在减少对大量昂贵像素级标注的依赖，利用少量标注数据和大量无标注数据有效训练RES模型。

## 2. 方法论

**核心思想：**  
提出一个半监督框架SemiRES，利用Segment Anything Model（SAM）强大的边界分割能力来精炼教师模型生成的伪标签，从而提高学生模型的训练质量。框架基于教师-学生网络结构，包含两个阶段：Burn-In阶段（仅用标注数据训练初始化）和Mutual-Learning阶段（师生互学）。核心创新在于SAM-based伪标签精炼和像素级加权调整策略。

**关键技术细节：**  
- **SAM-based Pseudo-Label Refinement**：离线使用SAM的“Segment Everything”功能为每张图像生成多尺度候选掩码库（采用游程编码RLE压缩存储）。设计两种匹配策略从库中选出最优掩码替换伪标签：  
  - **IoU-based Optimal Matching (IOM)**：计算伪标签与每个候选掩码的IoU，取IoU率超过阈值（默认0.5）的最高分候选掩码作为精炼后的伪标签。  
  - **Composite Parts Integration (CPI)**：当候选库中无理想整体掩码时，分别处理**欠分割**（CPI-U）和**过分割**（CPI-O）问题。CPI-U基于重叠率（式7）选择大区域候选掩码合并；CPI-O基于重叠率（式8）选择小区域候选掩码过滤噪声。最终将满足条件的候选掩码取并集作为精炼伪标签。  
- **Pixel-Wise Adjustment (PWA)**：当IOM或CPI均无法匹配到合适掩码时，直接使用原始伪标签，但根据每个像素的置信度赋予权重（式9），高置信度像素（接近0或1）权重高，低置信度像素（接近0.5）权重低，从而减少不确定像素对损失的贡献。

**公式与算法流程（文字说明）：**  
- 训练损失：监督损失（式1）+ 无监督损失（式10，经PWA加权）。  
- 教师参数通过指数移动平均（EMA，式5）更新。  
- 算法1给出了SemiRES中伪标签精炼的整体流程，包括遍历所有候选掩码，根据选择策略（IOM或CPI）计算分数并替换伪标签；若无可匹配结果则保留原始伪标签并应用PWA。

## 3. 实验设计

**数据集与场景：**  
使用了三个标准RES基准数据集：  
- **RefCOCO**：约5万标注对象，14.2万表达式，分割为train/val/testA/testB。  
- **RefCOCO+**：类似规模，表达式侧重属性信息。  
- **G-Ref**：约5.5万对象，10.4万表达式，表达式更复杂（平均长8.4词），使用UMD划分。

**Benchmark与对比方法：**  
以LAVT（Swin Transformer + BERT）作为基础RES模型。比较了：  
- **Supervised**：仅用少量标注数据进行全监督训练。  
- **Baseline**：普通的半监督师生框架（含数据增强和EMA）。  
- **SemiRES**（本文方法）。  
在0.5%、1%、2%、5%标注比例下进行对比。此外，还进行了消融实验、与基于置信度过滤方法的对比、不同匹配策略对比、不同阈值影响、组件有效性实验等。

## 4. 资源与算力

论文明确说明：  
- 使用**4块RTX3090 GPU**。  
- 每GPU加载3个标注样本和3个无标注样本。  
- 优化器：AdamW，初始学习率5e-5，权重衰减1e-2。  
- 训练总时长未具体给出，但标注成本估算显示：1%标注数据约需0.5天人工标注，而全标注需45.8天。

## 5. 实验数量与充分性

**实验数量与多样性：**  
- 主要结果（表1）：在3个数据集、4种标注比例（0.5%/1%/2%/5%）下对比，共3×3×4=36个主要结果（含Supervised/Baseline/SemiRES）。  
- 消融实验（表2-5）：包括匹配策略（IOM/CPI/U/O）、阈值（IoU_rate/inter1/inter2）、与过滤方法对比、组件（MLT/DA/PWA/Refine）逐步消融。  
- 额外实验：  
  - 更大标注比例（10%-50%）（表6）。  
  - 迁移至另一RES框架GRES（ReLA）（表7）。  
  - 与其他类无关提案网络（SEEM）对比（表8）。  
  - 小目标检测潜力（表9）。  
  - 定量统计正/负/无校正次数（图6）。  
  - 训练收敛曲线（图7）。  
- 定性可视化（图4、图8）展示多场景比较。

**充分性与公平性：**  
实验设计较为全面，覆盖了多种标注比例、多种策略变体、跨框架验证，并分析了阈值敏感性。对比方法均为公开基准，且使用了相同的基础模型（LAVT），保证了公平性。但未与其他半监督RES方法对比（因该领域较新），仅与自身基线比较，略欠广度。

## 6. 主要结论与发现

- **显著提升**：在1%标注数据下，SemiRES在RefCOCO val集上比全监督基线提升+18.64%，比半监督基线提升+8.28%。  
- **SAM精炼有效**：IOM和CPI均能有效改善伪标签质量，其中CPI-U在欠分割问题上表现最佳。  
- **PWA补充作用**：当SAM无法匹配时，PWA仍能利用原始伪标签并赋予像素级权重，进一步带来增益。  
- **接近全监督性能**：当标注比例达到30%时，SemiRES性能接近全监督模型（68.54% vs 72.73%）。  
- **泛化性**：该方法可迁移至其他RES框架（如GRES），提升显著。  
- **小目标检测**：在小目标子集上，SemiRES比全监督提升更大（例如Top 5%小目标val集20.45% vs 11.37%）。

## 7. 优点

- **创新性强**：首次将SAM引入半监督RES的伪标签精炼，设计两种匹配策略分别处理不同噪声类型。  
- **实用价值高**：大幅降低标注成本（仅需0.5%标注数据即可获得可用性能），适用于标注困难场景。  
- **方法灵活**：两种匹配策略可替代使用，且包含无匹配时的后备机制（PWA）。  
- **实验充分**：在多个数据集、多种标注比例、跨模型框架下验证，消融实验详细，分析了阈值影响和正负校正统计。  
- **代码开源**：提供Github仓库，利于复现和扩展。

## 8. 不足与局限

- **依赖SAM质量**：方法的性能受限于SAM生成的候选掩码质量，若SAM在某些场景（如医学图像）表现不佳，精炼效果可能下降。  
- **计算开销**：SAM离线生成多尺度掩码库需要额外存储和计算成本（尽管采用了RLE压缩），且CPI需要遍历所有候选掩码，可能较慢。  
- **未与其他半监督RES方法比较**：由于该领域工作尚少，仅与自身基线对比，缺乏与后续工作或更复杂半监督方法的横向对比。  
- **仅使用单一基础模型（LAVT）**：尽管在GRES上也验证了，但未测试在更多不同架构（如CNN-based）上的表现。  
- **阈值需要手动调节**：IOM和CPI的阈值（IoU_rate/inter1/inter2）通过实验设定，可能在不同数据集上需要重新调整。  
- **实验覆盖偏差风险**：主要基于COCO衍生数据集，场景相对受限，未在更复杂的真实场景（如自动驾驶街景）中验证。  
- **没有分析失败案例**：定性可视化只展示了成功案例，未深入讨论哪些场景下方法仍然失效。

（完）
