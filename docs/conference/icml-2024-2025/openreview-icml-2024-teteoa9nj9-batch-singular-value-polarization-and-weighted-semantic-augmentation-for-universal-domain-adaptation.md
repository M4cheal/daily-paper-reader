---
title: Batch Singular Value Polarization and Weighted Semantic Augmentation for Universal Domain Adaptation
title_zh: 批奇异值极化和加权语义增强用于通用域适应
authors: "WangZiQi, Wei Wang, Chao Huang, Jie Wen, Cong Wang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=teteOa9nJ9"
tags: ["query:ris"]
score: 6.0
evidence: 通用域适应方法处理域偏移，可用于指代分割的域泛化
tldr: 本文提出一种通用域适应方法BSP-WSA，通过批奇异值极化和加权语义增强来应对域偏移和类别偏移。该方法使用对抗分类器识别目标未知类别并对齐特征分布，并通过SVD操作抑制错误分类。实验验证了其在域适应任务上的有效性，其处理域偏移的技术可迁移至指代图像分割的泛化问题。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-teteoa9nj9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-teteoa9nj9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-teteoa9nj9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 847, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-teteoa9nj9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1778, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-teteoa9nj9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 853, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-teteoa9nj9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 850, \"height\": 394, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-teteoa9nj9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1770, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-teteoa9nj9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-teteoa9nj9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1768, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-teteoa9nj9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 837, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-teteoa9nj9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 842, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-teteoa9nj9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 837, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-teteoa9nj9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 861, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-teteoa9nj9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 863, \"height\": 200, \"label\": \"Table\"}]"
motivation: 通用域适应面临域偏移和类别偏移的双重挑战，需要识别目标域中的未知类别并避免误分类。
method: 提出BSP-WSA方法，采用对抗分类器对齐域分布，并通过批SVD极化（增强大奇异值、抑制小奇异值）防止目标样本被错误划分到源私有类别。
result: 在多个域适应基准上取得先进性能，有效处理了未知类别和域偏移。
conclusion: 该方法为通用域适应提供了有效框架，其域偏移处理策略可应用于指代分割的跨域泛化。
---

## Abstract
As a more challenging domain adaptation setting, universal domain adaptation (UniDA) introduces category shift on top of domain shift, which needs to identify unknown category in the target domain and avoid misclassifying target samples into source private categories. To this end, we propose a novel UniDA approach named Batch Singular value Polarization and Weighted Semantic Augmentation (BSP-WSA). Specifically, we adopt an adversarial classifier to identify the target unknown category and align feature distributions between the two domains. Then, we propose to perform SVD on the classifier's outputs to maximize larger singular values while minimizing those smaller ones, which could prevent target samples from being wrongly assigned to source private classes. To better bridge the domain gap, we propose a weighted semantic augmentation approach for UniDA to generate data on common categories between the two domains. Extensive experiments on three benchmarks demonstrate that BSP-WSA could outperform existing state-of-the-art UniDA approaches.

---

## 论文详细总结（自动生成）

```markdown
# 论文结构化总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：通用域适应（UniDA）是域适应中最具挑战性的设置，它不仅面临域偏移（domain shift），还面临类别偏移（category shift）。源域和目标域既共享公共类别，又各自拥有私有类别，且没有先验知识哪些类别是公共的。目标域中属于私有类别的样本应被识别为“未知”，而公共类别样本需正确分类到源域对应类别。同时，需要防止目标样本被误分类到源域私有类别中。
- **动机**：现有方法难以同时处理类别偏移和域偏移，尤其是目标样本被误判为源私有类别的风险。受SVD在域适应中的应用启发，论文旨在通过奇异值极化降低预测结果的类别多样性，并引入加权语义增强来更好地对齐公共类别的分布。

## 2. 方法论：核心思想、关键技术细节
- **整体框架**：提出BSP-WSA方法，包含三个模块：
  1. **对抗分类器**：采用输出维度为C+1的分类器（C为源域已知类别数，多一类为未知）。分类器试图将目标样本归为未知类，而特征生成器则试图混淆分类器使其将目标样本归为已知类，通过对抗训练同时实现未知类检测和特征分布对齐。
  2. **批奇异值极化（BSP）**：对分类器输出的预测矩阵（去除未知类概率）进行SVD。以最大化较大奇异值、最小化较小奇异值为目标，使奇异值曲线变陡峭，从而减少预测结果的多样性。这能有效抑制目标样本被错误分配到源私有类别。具体地，利用记忆库平滑当前批次的预测矩阵，对每个类别取均值后组成矩阵B，通过损失函数 \( L_{\text{bsp}} = \sum_{m=1}^{r} (\sigma_{sm} - \sigma_{lm}) \) 实现极化，r控制极化强度。
  3. **加权语义增强（WSA）**：在源域和目标域之间生成语义增强样本，但为每个类别赋予不同权重。权重 \(\gamma_j = (\hat{n}_{tj}/n_{sj}) / \sum_k (\hat{n}_{tk}/n_{sk})\)，其中 \(\hat{n}_{tj}\) 是目标域被预测为第j类的样本数，\(n_{sj}\) 是源域第j类样本数。此设计使公共类别获得更大增强权重，源私有类别的增强被削弱，避免负面影响。
- **整体目标**：联合优化对抗损失、BSP损失和WSA损失。

## 3. 实验设计：数据集、场景、基准与对比方法
- **数据集**：三个跨域目标识别基准：
  - **Office-31**：3个域（A、D、W），31个类别，4110张图像。
  - **Office-Home**：4个域（A、C、P、R），65个类别，15588张图像。
  - **VisDA-2017**：合成域(S)到真实域(R)，12个类别，207785张图像。
- **场景设置**：按照通用域适应惯例，构造三种子场景：
  - **OPDA**（开放部分域适应）： \(\tilde{Y}, Y_s, Y_t\) 均非空。对应Office-31（10/10/11），Office-Home（10/5/50），VisDA（6/3/3）。
  - **PDA**（部分域适应）： \(\tilde{Y}, Y_s\) 非空，\(Y_t\) 为空。对应Office-31（10/21/0），Office-Home（25/40/0），VisDA（6/6/0）。
  - **ODA**（开放域适应）： \(\tilde{Y}, Y_t\) 非空，\(Y_s\) 为空。对应Office-31（10/0/11），Office-Home（25/0/40），VisDA（6/0/6）。
- **评价指标**：H-score（调和平均准确率），综合衡量公共类别准确率和未知类准确率。
- **对比方法**：7种SOTA方法：UAN (CVPR'19)、CMU (ECCV'20)、DANCE (NeurIPS'20)、DCC (CVPR'21)、OVANet (ICCV'21)、GATE (CVPR'22)、GLC (CVPR'23)。

## 4. 资源与算力
- **文中未明确说明GPU型号、数量及训练时长**。仅提及使用PyTorch实现，采用ResNet50预训练主干，训练40K次迭代，mini-batch SGD优化器（动量0.9，权重衰减5e-4），batch size为36。未提供硬件配置。

## 5. 实验数量与充分性
- **实验数量**：共包含三大数据集上的三种场景（OPDA、PDA、ODA），每场景有多个迁移任务（如Office-31有6个任务，Office-Home有12个任务，VisDA有1个任务），总计约（6+12+1）×3 = 57个任务结果。此外还进行了：
  - **消融实验**（表4-6）：在三个数据集上分别对BSP和WSA进行消融。
  - **Plug-and-Play实验**（表7-8）：将BSP模块应用到GLC方法。
  - **不同设置下的深入分析**（图4）：改变公共/私有类别数量。
  - **特征可视化**（图5）：t-SNE可视化。
  - **超参数敏感性分析**（图6）：对θ和r进行调参。
- **充分性评价**：实验覆盖了主流数据集和多种子场景，对比了多个SOTA方法，消融实验验证了各组件有效性，还做了可迁移性分析。整体充分且客观。注意：ODA场景下BSP反而退化，说明方法设计有明确适用前提（源域存在私有类别），作者也如实报告了。

## 6. 主要结论与发现
- BSP-WSA在OPDA和PDA设置下显著优于所有对比方法，在Office-31、Office-Home、VisDA上平均H-score分别提升0.7%、1.4%、0.7%（OPDA）和1.3%、0.7%、2.4%（PDA）。
- BSP能有效减少目标样本被误分到源私有类别的数量，WSA能更好地对齐公共类别分布。
- 在ODA设置下（源域无私有类别），BSP无效，但WSA仍有效，总体性能与最佳方法（OVANet）接近。
- BSP可作为即插即用模块，提升GLC等方法的性能。
- 超参数θ在0.15~0.25、r在3附近表现稳健。

## 7. 优点
- **方法创新**：首次将奇异值极化概念引入UniDA，利用SVD分析预测矩阵中奇异值与类别私有/公共关系，设计极化损失抑制误分类。
- **针对性设计**：加权语义增强针对UniDA场景，自适应地加强公共类别数据生成，降低源私有类别的干扰。
- **即插即用**：BSP模块可轻松集成到其他DA框架。
- **实验全面**：在多种场景和数据集上验证，并进行了详尽的消融、可视化、敏感性分析。

## 8. 不足与局限
- **假设依赖**：BSP有效的前提是目标样本被分配到源私有类别的概率很小，这要求分类器具有较强判别能力且对抗分类器能准确检测未知类，否则性能可能受影响。
- **未知类处理**：将目标域未知类别视为单一类别，未挖掘未知类内部的聚类结构，可能损失性能（作者指出这是未来方向）。
- **ODA场景缺陷**：当源域无私有类别时，BSP反而降低性能，说明该方法并非通用所有设置。
- **算力资源未提供**：未报告训练硬件和时长，不利于复现和资源评估。

（完）
```
