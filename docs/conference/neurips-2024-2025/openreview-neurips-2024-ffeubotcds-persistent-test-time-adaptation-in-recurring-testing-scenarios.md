---
title: Persistent Test-time Adaptation in Recurring Testing Scenarios
title_zh: 循环测试场景中的持久性测试时自适应
authors: "Trung-Hieu Hoang, MinhDuc Vo, Minh N. Do"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=ffeUBoTcdS"
tags: ["query:tta"]
score: 9.0
evidence: 持续性测试时自适应在循环场景中的理论与方法
tldr: 现有测试时自适应方法在长期重复出现的环境中的性能尚不明确。本文提出了循环测试时自适应设置，并基于扰动高斯混合模型分类器进行理论分析，揭示了数据集和算法相关因素对误差累积的影响，为长期适应提供了理论基础。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 794, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1411, \"height\": 749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 730, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1401, \"height\": 935, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1437, \"height\": 1477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 2117, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 725, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1439, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1457, \"height\": 2311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ffeubotcds/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1460, \"height\": 2315, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 758, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 662, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1019, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1441, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1433, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1445, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1448, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1447, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1022, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1442, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1441, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1442, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1441, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1445, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1438, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1442, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1440, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ffeubotcds/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 658, \"height\": 160, \"label\": \"Table\"}]"
motivation: 探究测试时自适应方法在长期重复出现的环境中的误差累积问题。
method: 引入循环测试时自适应诊断设置，并使用扰动高斯混合模型进行理论模拟。
result: 分析了数据集和算法相关因素对误差累积的影响，提供了理论见解。
conclusion: 为长期测试时自适应提供了理论分析框架，有助于设计更鲁棒的算法。
---

## Abstract
Current test-time adaptation (TTA) approaches aim to adapt a machine learning model to environments that change continuously. Yet, it is unclear whether TTA methods can maintain their adaptability over prolonged periods. To answer this question, we introduce a diagnostic setting - **recurring TTA** where environments not only change but also recur over time, creating an extensive data stream. This setting allows us to examine the error accumulation of TTA models, in the most basic scenario, when they are regularly exposed to previous testing environments. Furthermore, we simulate a TTA process on a simple yet representative $\epsilon$-**perturbed Gaussian Mixture Model Classifier**, deriving theoretical insights into the dataset- and algorithm-dependent factors contributing to gradual performance degradation. Our investigation leads us to propose **persistent TTA (PeTTA)**, which senses when the model is diverging towards collapse and adjusts the adaptation strategy, striking a balance between the dual objectives of adaptation and model collapse prevention. The supreme stability of PeTTA over existing approaches, in the face of lifelong TTA scenarios, has been demonstrated over comprehensive experiments on various benchmarks. Our project page is available at [https://hthieu166.github.io/petta](https://hthieu166.github.io/petta).

---

## 论文详细总结（自动生成）

# 论文《Persistent Test-time Adaptation in Recurring Testing Scenarios》中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **研究动机**：现有的测试时自适应（TTA）方法通常假设测试环境只出现一次或简单变化，但实际应用中环境往往周期性重复（如监控摄像头每天经历不同光照）。目前缺乏对TTA模型在长期、重复环境中性能退化问题的理论理解。
- **核心问题**：当模型反复暴露于之前遇到过的测试环境时，其自适应能力是否会逐渐丧失？是否存在误差累积导致模型崩溃的风险？
- **整体含义**：作者提出了**重复TTA（Recurring TTA）** 这一诊断场景，系统性地揭示了现有TTA方法在长期运行中性能持续下降的现象，并通过理论分析解释了退化机制，最终提出**PeTTA**方法以平衡“自适应”与“防止崩溃”两个目标。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 通过实时监测模型参数相对于初始模型的偏离程度（即“模型分歧度”），动态调整适应过程中的两个关键超参数：正则化系数λ和更新率α，从而在适应新环境与保持模型稳定性之间取得平衡。

### 关键技术细节
- **分歧度感知（Sensing the Divergence）**：使用特征空间中各类的**马氏距离（Mahalanobis distance）** 来衡量当前特征均值 \( \hat{\mu}_y^t \) 与源数据集特征均值 \( \mu_y^0 \) 的偏离程度：
  \[
  \gamma_y^t = 1 - \exp\left( - (\hat{\mu}_y^t - \mu_y^0)^T (\Sigma_y^0)^{-1} (\hat{\mu}_y^t - \mu_y^0) \right)
  \]
  其中 \(\Sigma_y^0\) 是源数据集特征协方差矩阵（对角简化）。

- **自适应超参数**：对当前batch中所有出现类别的 \(\gamma\) 取平均得到 \(\bar{\gamma}_t\)，然后动态调整：
  \[
  \lambda_t = \bar{\gamma}_t \cdot \lambda_0, \quad \alpha_t = (1 - \bar{\gamma}_t) \cdot \alpha_0
  \]
  - 当模型偏移严重时，\(\bar{\gamma}_t\) 增大，增强正则化（大λ）并降低模型更新速度（小α），优先防止崩溃。
  - 当模型接近初始状态时，\(\bar{\gamma}_t\) 较小，允许更快适应。

- **锚点损失（Anchor Loss, LAL）**：额外约束模型输出概率与源模型输出概率的KL散度，防止过度偏离。

- **整体算法流程**（每一测试步t）：
  1. 使用教师模型 \(f_{t-1}\) 对当前批次 \(X_t\) 生成伪标签 \(\hat{Y}_t\)。
  2. 计算每个类别的分歧度 \(\gamma_y^t\)，更新特征统计量。
  3. 计算平均分歧度 \(\bar{\gamma}_t\)，得到动态 \(\lambda_t, \alpha_t\)。
  4. 更新学生模型参数：最小化分类损失 \(L_{CLS}\)、锚点损失 \(L_{AL}\) 以及正则化项 \(\lambda_t R(\theta)\)。
  5. 通过指数移动平均（EMA）更新教师模型：\(\theta_t = (1 - \alpha_t) \theta_{t-1} + \alpha_t \theta'_t\)。
  6. 使用更新后的教师模型进行最终预测。

- **理论分析支撑**：利用ϵ-扰动高斯混合模型分类器（ϵ-GMMC）推导出模型崩溃的条件（Corollary 1），指出伪标签错误率（FNR）\(ϵ_t\) 与数据分布、更新率α等因素的关系，为PeTTA的自适应调整提供了理论基础。

## 3. 实验设计

- **数据集与场景**：
  - **标准TTA基准**：CIFAR-10→CIFAR-10-C、CIFAR-100→CIFAR-100-C、ImageNet→ImageNet-C（均使用最严重腐败等级5），以及DomainNet（real→clipart, painting, sketch）。
  - **重复TTA场景**：将上述测试集循环访问20次（K=20），每次内部保持领域顺序变化（如颜色→噪声→模糊等），且每个batch内类别分布呈时间相关性（Dirichlet分布）。
  - **额外场景**：连续变化腐败（CCC）[45] 设置，用于验证PeTTA在更长、非循环流上的稳定性。

- **对比方法**：
  - 通用TTA：CoTTA, EATA, RMT, MECTA
  - 实用TTA：RoTTA
  - 复位基线：RDumb
  - 无参数方法：LAME
  - 其他：ROID, TRIBE
  - 源模型（无适应）作为下限参考。

- **实现细节**：
  - 使用ResNet-50（ImageNet/DomainNet）或Hendrycks2020AugMix_ResNeXt（CIFAR-100）等预训练模型，仅更新BatchNorm层。
  - 优化器：Adam（lr=1e-3, β=(0.9,0.999)）。
  - EMA更新率α₀=1e-3，正则化系数λ₀=10（CIFAR/ImageNet）或1（DomainNet）。
  - 源数据集特征统计量从一小部分未标注源样本计算（假设可获取）。

## 4. 资源与算力

- **文中明确说明**：
  - 硬件环境：Intel i7-10700K CPU、64GB RAM、一块NVIDIA GeForce RTX 3090 GPU（24GB VRAM）。
  - 未提及总训练时长或具体GPU小时数，也未对每个实验的运行时间进行详细报告。

## 5. 实验数量与充分性

- **实验组数**：
  - 4个基准数据集 × 20次重复访问，共约80条实验曲线。
  - 额外CCC实验（ImageNet-C，80000步）。
  - 消融实验（Tab.4-5，共8种变体）覆盖各组件（λ/α自适应、锚点损失、正则化）的贡献。
  - 敏感度分析（λ₀不同取值）、随机顺序验证、不同重置频率比较（RDumb对比）。
  - 40次访问的扩展实验。
  - 每个PeTTA实验重复5次取平均，报告标准差。

- **充分性与公平性**：
  - 对比方法均采用原论文推荐超参数，且与PeTTA共享相同基础模块（如RoTTA的稳健BatchNorm和记忆库）。
  - 实验覆盖了多种数据类型（合成、自然图像、领域泛化）和多种TTA场景（重复、长流、CCC）。
  - 消融实验系统性地验证了各设计选择的有效性。
  - 不足之处：仅测试了分类任务，未涉及更复杂的任务（如语义分割、目标检测）；内存库和源特征统计假设可能限制部分实际场景的适用性。

## 6. 主要结论与发现

1. **确认性能退化**：在重复TTA场景中，现有方法（RoTTA, CoTTA, EATA等）的测试误差随访问次数显著上升，甚至超过无适应的源模型，表明存在“模型崩溃”风险。
2. **理论解释**：利用ϵ-GMMC分析揭示了退化取决于数据先验分布、类别间区分度（|μ₀-μ₁|）、更新率α和伪标签错误率ϵ。条件满足时，模型会收敛到将所有样本判为同一类。
3. **PeTTA优越性**：提出的PeTTA在所有数据集上均比基准方法更稳定，平均误差在20次访问内几乎无上升（如CIFAR-10-C从24.3%到23.0%），而RoTTA从24.6%升至70.3%。在CCC长流中也保持低误差（0.64 vs RoTTA的0.95）。
4. **自适应机制有效**：通过动态调整λ和α，PeTTA在适应新环境与防止过度偏离之间取得平衡，消融实验证明各组件协同作用。
5. **复位方法局限性**：RDumb需精细调参复位频率，且即使有“或acles”信息（知道域切换时刻）仍不如PeTTA。

## 7. 优点

- **诊断场景创新**：提出重复TTA作为简单却有效的诊断工具，能暴露现有方法在长期下的脆弱性。
- **理论贡献**：首次在简化概率模型上严格推导了TTA模型崩溃的条件，为设计持久算法提供了理论指导。
- **方法简洁高效**：PeTTA只增加少量计算开销（特征统计计算和自适应超参数），没有复杂结构，易于集成到现有TTA框架。
- **实验全面且稳健**：涵盖多种数据集、多种对比方法、消融和敏感性分析，结果一致性高。
- **开源与可复现**：提供了项目页面和代码，实验细节详尽。

## 8. 不足与局限

- **不能完全消除误差累积**：作者承认通过正则化无法严格保证零误差累积，未来需要从设计上实现“无累积”的算法。
- **依赖条件**：
  - 需要一个小型记忆库（64张图）来缓解时间相关性，这在某些隐私或存储受限场景可能不适用。
  - 需要源数据集的特征均值与协方差，虽然可从少量未标注样本估计，但并非所有实际部署都能获得源数据。
- **仅分类任务**：当前只在图像分类上验证，未扩展至更广泛的测试时适应任务（如分割、检测）。
- **超参数敏感度有限**：虽然λ₀和α₀有一定鲁棒性，但最优值仍需针对不同任务微调（如CIFAR-10-C的λ₀=10，DomainNet的λ₀=1），而验证集不可用时调参困难。
- **计算资源未充分报告**：未给出总训练时间，不利于复现成本评估。

（完）
