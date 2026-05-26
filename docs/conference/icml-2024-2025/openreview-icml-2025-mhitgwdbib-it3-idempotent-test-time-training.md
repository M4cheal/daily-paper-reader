---
title: "IT$^3$: Idempotent Test-Time Training"
title_zh: IT³：幂等测试时训练
authors: "Nikita Durasov, Assaf Shocher, Doruk Oner, Gal Chechik, Alexei A Efros, Pascal Fua"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=MHiTGWDbIb"
tags: ["query:tta"]
score: 9.0
evidence: 理论连接幂等性与预测置信度，用于测试时训练
tldr: 现有测试时训练方法通常需要辅助任务或额外数据，限制了实用性。本文提出幂等测试时训练（IT3），通过强制函数幂等性替代辅助任务，仅利用当前测试样本实现自适应。理论上连接幂等性与预测置信度，在多种分布偏移基准上取得最优性能，且无需任务特定设计。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1586, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 757, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1545, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 747, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 806, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1563, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 826, \"height\": 239, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 850, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 852, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 846, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1735, \"height\": 749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 864, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mhitgwdbib/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1682, \"height\": 2092, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-mhitgwdbib/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 670, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mhitgwdbib/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 916, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mhitgwdbib/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 842, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mhitgwdbib/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 765, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mhitgwdbib/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 846, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mhitgwdbib/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 904, \"height\": 143, \"label\": \"Table\"}]"
motivation: 测试时训练通常需要领域特定的辅助任务，限制了通用性。
method: 提出幂等性约束：对同一输入多次应用模型应得到相同输出，作为自监督信号进行测试时微调。
result: 在图像分类、语义分割等多个分布偏移基准上超越现有方法。
conclusion: 幂等性是一种有效的通用测试时训练目标，无需辅助任务设计。
---

## Abstract
Deep learning models often struggle when deployed in real-world settings due to distribution shifts between training and test data. While existing approaches like domain adaptation and test-time training (TTT) offer partial solutions, they typically require additional data or domain-specific auxiliary tasks. We present Idempotent Test-Time Training (IT3), a novel approach that enables on-the-fly adaptation to distribution shifts using only the current test instance, without any auxiliary task design. Our key insight is that enforcing idempotence---where repeated applications of a function yield the same result---can effectively replace domain-specific auxiliary tasks used in previous TTT methods. We theoretically connect idempotence to prediction confidence and demonstrate that minimizing the distance between successive applications of our model during inference leads to improved out-of-distribution performance. Extensive experiments across diverse domains (including image classification, aerodynamics prediction, and aerial segmentation) and architectures (MLPs, CNNs, GNNs) show that IT3 consistently outperforms existing approaches while being simpler and more widely applicable. Our results suggest that idempotence provides a universal principle for test-time adaptation that generalizes across domains and architectures.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：深度学习模型在真实部署中常因训练与测试数据分布不一致（distribution shift）而导致性能下降。现有方法如领域适应（domain adaptation）和测试时训练（Test-Time Training, TTT）需要额外数据或领域特定的辅助任务（如旋转预测、图像修复），通用性差。
- **研究动机**：希望找到一种无需设计辅助任务、仅利用当前测试样本即可在线适应分布偏移的通用方法。
- **整体含义**：论文提出利用“幂等性”（idempotence）——即对函数多次应用结果不变——作为替代辅助任务的自监督信号，实现测试时训练。该方法可广泛应用于图像分类、语义分割、空气动力学预测等不同领域和架构（MLP、CNN、GNN），性能优于现有方法。

## 2. 论文提出的方法论

### 2.1 核心思想
- 关键洞察：强制模型在测试时对同一输入（包括辅助输入）的重复应用产生相同输出（即幂等性），可以替代传统TTT中领域特定的辅助任务。
- 理论连接：幂等误差（连续两次预测间的距离）与预测置信度强相关；最小化该误差可提升分布外（OOD）性能。

### 2.2 技术细节
- **训练阶段**：修改网络输入层使其接受第二个参数（可以是真实标签y或中性信号0）。训练损失：
  \[
  L_{\text{train}} = \|f_\theta(x, y) - y\| + \|f_\theta(x, 0) - y\|
  \]
  这迫使 \(f_\theta(x, 0) \approx y\) 且 \(f_\theta(x, y) = y\)，从而保证 \(f_\theta(x, \cdot)\) 在训练集上近似幂等。
- **测试时训练（IT3）**：
  - 冻结初始训练好的模型 \(F = f_\Theta\)（固定权重）。
  - 对每个测试样本 \(x\)，用可更新的 \(f_\theta\) 计算 \(y_0 = f_\theta(x, 0)\)，然后用冻结模型计算 \(y_1 = F(x, y_0)\)。
  - 最小化损失 \(L_{\text{IT3}} = \|F(x, f_\theta(x, 0)) - f_\theta(x, 0)\|\)，仅更新 \(f_\theta\) 而固定 \(F\)，避免错误放大或退化为恒等函数。
  - 处理完一批样本后重置 \(f_\theta\) 为初始 \(F\)。
- **在线版本（Online IT3）**：
  - 用于数据流场景（分布连续偏移）。
  - 不重置模型，而是用指数移动平均（EMA）替代冻结模型：\(L_{\text{online}} = \|f_{\text{EMA}}(x, f_\theta(x, 0)) - f_\theta(x, 0)\|\)，允许模型随时间平滑演进。

## 3. 实验设计

### 3.1 数据集与场景
| 任务 | 数据集 | OOD构造 |
|------|--------|---------|
| 表格数据回归 | UCI Boston Housing | 随机特征置零（概率5%~20%） |
| 图像分类 | CIFAR-10 → CIFAR-10-C（15种损坏，5个严重等级） | 常见图像损坏 |
| 年龄预测 | UTKFace（训练：20-60岁；测试：<20或>60） | 年龄超出训练范围 |
| 遥感语义分割 | RoadTracer训练 → Massachusetts Road测试 | 不同地理区域（城市vs乡村） |
| 空气动力学预测（2D翼型） | NACA参数生成+XFoil仿真（L/D>60视为OOD） | 高性能翼型 |
| 空气动力学预测（3D汽车） | ShapeNet汽车子集+OpenFOAM阻力系数 | 流线型汽车 |
| 大规模分类 | ImageNet → ImageNet-C（15种损坏，5个等级） | 常见图像损坏 |

### 3.2 对比方法
- 基础模型（未优化）
- ActMAD（激活匹配，适用于多模态）
- TTT（原始方法，仅用于图像分类）
- TENT、ETA、MEMO（仅用于ImageNet-C）
- 不同批大小（batch size）下的对比

### 3.3 评估指标
- MAE（表格、年龄、翼型、汽车）
- 分类准确率（CIFAR、ImageNet）
- Correctness/Completeness/Quality（道路分割）

## 4. 资源与算力

论文**未明确说明**使用的GPU型号、数量或训练时长。仅在附录中给出了推理时间对比（相对倍数）和内存消耗（ImageNet-C batch=128时峰值内存7.4GB），但未详细说明训练阶段的计算资源。因此无法量化算力投入。

## 5. 实验数量与充分性

- **实验数量**：涵盖7种不同任务/数据集（表格、CIFAR、年龄、道路、翼型、汽车、ImageNet），对比了多种最先进方法（ActMAD、TTT、TENT、ETA、MEMO），并测试了不同批大小（1~128）和不同OOD等级（1~4或1~5）。
- **消融实验**：在ImageNet-C上分析了幂等性与准确率的负相关关系（Pearson r = -0.94），验证了方法动机。
- **在线版本验证**：在道路分割、翼型、汽车三个任务上测试了在线IT3，并显示显著优于离线版本。
- **充分性判断**：实验覆盖了多种数据类型（图像、表格、3D网格）、多种任务（回归、分类、分割）和多种架构（MLP、CNN、GNN、ResNet、DLA、DRU-Net），具有较强的泛化性。对比方法选择合理，且所有实验均控制相同OOD设定，结论可靠。但未对大模型（如ViT）进行测试，且未与其他TTT变体（如TTT++）在非图像任务上比较（因后者需特定辅助任务）。

## 6. 论文的主要结论与发现

1. **幂等性可作为通用TTT目标**：无需领域特定辅助任务，仅通过最小化两次预测的差异即可有效适应分布偏移。
2. **IT3在几乎所有任务上优于现有方法**：在表格、图像分类、年龄预测、道路分割、空气动力学预测等任务中，IT3在不同OOD等级和批大小下均取得最佳或相当结果。
3. **在线版本可进一步适应连续分布偏移**：通过EMA锚定，避免灾难性遗忘，性能提升显著（如道路分割Quality从48.7提升至69.8）。
4. **幂等误差与模型精度强相关**：ImageNet-C上相关系数-0.94，验证了优化幂等性的合理性。

## 7. 优点

- **通用性极强**：无需设计辅助任务，适用于多种数据类型和架构，填补了TTT方法缺乏通用原则的空白。
- **方法简洁有效**：训练和测试过程仅需修改输入层和添加一个冻结分支，实现简单。
- **理论支撑**：从数学上连接幂等性与能量模型、投影原理，并提供详细推导（附录B、C）。
- **实验丰富且公平**：跨领域、多基线、多OOD等级，并提供了定性结果（如道路分割的可视化改善）。
- **在线与离线双模式**：覆盖单实例和数据流两种场景，实用性更强。

## 8. 不足与局限

- **缺少领域专业知识**：在某些信息有限的单实例场景（如单张图像内容极少）可能难以收敛。论文自述未来可与领域专用方法结合。
- **算力开销未透明**：虽推理时间可比（约4-6倍于基础模型），但训练阶段资源消耗未报告，不易复现。
- **未涉及大模型/Transformer架构**：实验集中在ResNet、DLA、DRU-Net等，未测试ViT等现代架构。
- **对比方法覆盖不全**：在非图像任务中，仅与ActMAD对比（因TTT等方法需辅助任务），缺少与其他通用TTT方法（如TTT++）的比较。
- **在线版本评估有限**：仅测试了三个任务（道路、翼型、汽车），且未与其他在线TTA方法（如TENT online）对比。
- **理论深度有限**：幂等性与置信度的关联主要基于经验观察，缺乏严格的数学证明或泛化界。

（完）
