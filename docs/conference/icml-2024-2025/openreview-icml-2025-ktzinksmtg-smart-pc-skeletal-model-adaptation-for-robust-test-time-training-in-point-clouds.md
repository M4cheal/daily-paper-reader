---
title: "SMART-PC: Skeletal Model Adaptation for Robust Test-Time Training in Point Clouds"
title_zh: SMART-PC：基于骨架模型的自适应实现鲁棒点云测试时训练
authors: "Ali Bahri, Moslem Yazdanpanah, Sahar Dastani, Mehrdad Noori, Gustavo Adolfo Vargas Hakim, David OSOWIECHI, Farzad Beizaee, Ismail Ben Ayed, Christian Desrosiers"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=KTZinkSMTG"
tags: ["query:tta"]
score: 7.0
evidence: 三维点云分类的测试时训练
tldr: 测试时训练在3D点云分类中通常计算开销大。本文提出SMART-PC，预训练时学习骨架表示，提取鲁棒几何特征，实现实时无反向传播的测试时自适应。实验表明该方法在多种损坏下分类准确率高且速度快。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ktzinksmtg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 724, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ktzinksmtg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1581, \"height\": 718, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ktzinksmtg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 847, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ktzinksmtg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 832, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ktzinksmtg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 776, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ktzinksmtg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1049, \"height\": 710, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ktzinksmtg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1768, \"height\": 1413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ktzinksmtg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1507, \"height\": 1014, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ktzinksmtg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1292, \"height\": 822, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ktzinksmtg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1078, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ktzinksmtg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 874, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ktzinksmtg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 514, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ktzinksmtg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1593, \"height\": 721, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ktzinksmtg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1593, \"height\": 626, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ktzinksmtg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1590, \"height\": 657, \"label\": \"Table\"}]"
motivation: 现有点云TTA方法计算量大，难以实时应用。
method: 预训练预测骨架表示，提取几何特征，无需反向传播即可适应。
result: 在多个点云损坏数据集上实现了实时高精度分类。
conclusion: SMART-PC提供了高效的点云TTA解决方案。
---

## Abstract
Test-Time Training has emerged as a promising solution to address distribution shifts in 3D point cloud classification. However, existing methods often rely on computationally expensive backpropagation during adaptation, limiting their applicability in real-world, time-sensitive scenarios. In this paper, we introduce SMART-PC, a skeleton-based framework that enhances resilience to corruptions by leveraging the geometric structure of 3D point clouds. During pre-training, our method predicts skeletal representations, enabling the model to extract robust and meaningful geometric features that are less sensitive to corruptions, thereby improving adaptability to test-time distribution shifts.
Unlike prior approaches, SMART-PC achieves real-time adaptation by eliminating backpropagation and updating only BatchNorm statistics, resulting in a lightweight and efficient framework capable of achieving high frame-per-second rates while maintaining superior classification performance. Extensive experiments on benchmark datasets, including ModelNet40-C, ShapeNet-C, and ScanObjectNN-C, demonstrate that SMART-PC achieves state-of-the-art results, outperforming existing methods such as MATE in terms of both accuracy and computational efficiency. The implementation is available at: \url{https://github.com/AliBahri94/SMART-PC}.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义
**研究动机**：在3D点云分类中，实际部署时常遇到**数据分布偏移**（如传感器噪声、环境变化等），导致模型性能严重下降。**测试时训练**通过在推理阶段利用无标签目标数据动态调整模型，是缓解该问题的有效途径。然而，现有方法（如MATE）依赖**反向传播更新全部参数**，计算开销大，不适合实时应用（如自动驾驶、机器人）。
**核心思想**：提出基于**骨架表示**的框架SMART-PC，在预训练阶段让模型学习点云的内在几何结构（骨架点和半径），从而提取对损坏**不敏感**的特征；在测试时仅更新**BatchNorm统计量**（均值和方差），实现**无反向传播的轻量自适应**，同时保持高分类精度和高帧率。

## 2. 方法论
### 核心思想
- **骨架表示**：将点云抽象为一系列骨架球（中心点 + 半径），刻画局部几何结构，具有**可恢复性**和**抽象性**，能滤除高频噪声和局部畸变。
- **预训练目标**：联合优化三项骨骼损失和分类损失，使编码器学习鲁棒几何特征。
- **测试时自适应**：分为**在线模式**和**标准模式**。在线模式下可选择仅更新BatchNorm统计量（无反向传播）或更新全部参数；标准模式下由于无跨批次信息积累，采用全参数更新。

### 关键技术细节
1. **点云分块**：
   - 使用**最远点采样（FPS）**选取 M 个中心点 C ∈ ℝ^{M×3}。
   - 对每个中心点用 **K近邻** 获取局部邻域 P_local ∈ ℝ^{M×K×3}。
2. **网络架构**（图2）：
   - **共享编码器 E**（Point-MAE骨干）提取特征 F_enc ∈ ℝ^{M×d}。
   - **解码器 D** 输出 F_dec ∈ ℝ^{M×d}。
   - **骨骼分支**：两个MLP分别预测骨架点 c_s ∈ ℝ^{M×3} 和半径 r ∈ ℝ^{M×1}。
   - **分类分支**：将 F_enc 与 F_dec 相加后经MLP分类。
3. **骨骼损失函数**（式11-14）：
   - **点-球损失 L_p2s**：确保输入点位于对应骨骼球表面上。
   - **采样损失 L_sampling**：计算骨骼球表面采样点与输入点的倒角距离，降低高频噪声。
   - **半径正则化损失 L_radius**：鼓励更大半径，提升对局部噪声的鲁棒性。
   - 总骨骼损失 L_skel = L_p2s + λ₁ L_sampling + λ₂ L_radius。
4. **分类损失**：标准交叉熵 L_cls。
5. **测试时适应**：
   - **在线模式（无反向传播）**：仅更新BatchNorm层的 running mean 和 running variance。
   - **在线模式（有反向传播）**：同时优化骨骼损失更新全部参数。
   - **标准模式**：每批独立进行全参数更新（20次迭代）。

## 3. 实验设计
### 数据集与基准
- **ModelNet40-C**（15种损坏类型，如高斯噪声、背景噪声、下采样等）
- **ShapeNet-C**（基于ShapeNetCore-v2，同样15种损坏）
- **ScanObjectNN-C**（真实扫描数据，15种损坏）
- **基准**：采用Point-MAE骨干，与MATE保持相同设置以确保公平比较。

### 对比方法
1. **源模型无适应**：Org-SO, MATE-SO, SMART-PC-SO
2. **标准适应**：TENT, SHOT, DUA, T3A, TTT-Rot, MATE-Standard, BFTT3D, CloudFixer, DDA 等
3. **在线适应**：MATE-Online, SMART-PC-Online（含无反向传播变体）

### 主要结果（表1）
- **ModelNet40-C**：SMART-PC-Online 平均准确率 **72.9%**（MATE-Online 70.6%）；无反向传播版本 70.8%。
- **ShapeNet-C**：SMART-PC-Online 67.1% vs MATE-Online 69.1%（略低，但无反向传播版 65.9% 仍优于其他方法）。
- **ScanObjectNN-C**：SMART-PC-Online **47.4%**（MATE-Online 36.9%），大幅领先。

## 4. 资源与算力
- **GPU**：单张 **NVIDIA A6000**（明确说明）。
- **训练时长**：文中**未明确给出**预训练或适配的具体时间。
- **帧率对比**（图3）：SMART-PC 无反向传播版可达 **59.52 FPS**（表4），而 MATE 仅 10.79 FPS，远超实时阈值（30 FPS）。

## 5. 实验数量与充分性
- **三大主流点云损坏基准**覆盖多种真实场景，包含15种不同损坏类型，测试全面。
- **消融实验**：
  - **Batch Size**（图5）：从8到128，精度上升，但主体实验采用 batch size=1 公平对比。
  - **数据增强**（图4）：无增强、旋转、水平翻转、平移，验证鲁棒性。
  - **特征求和**：编码器+解码器特征组合提升准确率。
  - **骨骼损失系数**（表2）：原始Point2Skeleton系数 (0.3,1.0,0.4) 最优。
  - **预训练策略对比**（表3）：用BFTT3D方法评估不同预训练（Org-SO, MATE-SO, SMART-PC-SO），SMART-PC-SO均最优。
- **可视化**：展示骨架球在原图与损坏图上的稳定性（图6、图8）。
- **公平性**：均采用Point-MAE骨干，batch size 1，迭代次数与MATE一致；结果含复现标记。
- **结论**：实验设计系统，覆盖全面，对比充分，消融完整，结论可信。

## 6. 主要结论与发现
1. **骨架预训练使特征对损坏高度鲁棒**：SMART-PC-SO（无适应）即显著优于MATE-SO和Org-SO，证明骨架抽象过滤了表面噪声。
2. **无反向传播的在线适应可行且高效**：仅更新BatchNorm统计量即可在多个数据集上超越或接近全参数更新的MATE，同时帧率提升数倍。
3. **SMART-PC在大部分真实损坏场景下达到SOTA**，尤其在ScanObjectNN-C上相对MATE提升超10个百分点。
4. **速度-精度权衡优异**：在实时约束（30 FPS）下仍能保持高分类精度，适合部署。

## 7. 优点
- **新颖性**：首次将**骨架表示**引入测试时训练，充分利用点云几何先验提升鲁棒性。
- **轻量高效**：提出**免反向传播**适应策略，大幅降低计算成本，实现实时处理。
- **全面验证**：在三个标准损坏基准上系统评测，消融详尽，复现设置透明。
- **可比性**：与MATE共用同一骨干和训练协议，对比公平。
- **实用性**：可轻松扩展至其他3D任务（如分割、检测），源代码已开源。

## 8. 不足与局限
- **特定损坏下性能波动**：在ShapeNet-C在线模式中，SMART-PC-Online（67.1%）略低于MATE-Online（69.1%），表明某些场景（如低密度噪声）仍存提升空间。
- **高强度损坏能力有限**：如“lidar”类损坏（表5-7中准确率普遍低于10%），所有方法均表现不佳，骨架抽象可能仍不足以应对极端退化。
- **计算开销前置**：预训练阶段需额外训练骨骼分支，增加原始训练成本（文中未量化）。
- **未讨论跨域泛化**：实验集中在同一数据集的不同损坏上，未测试源域到完全不同目标域（如合成→真实）的迁移能力。
- **BatchNorm依赖性**：无反向传播版本仅能更新BN统计量，若骨干使用其他归一化层（如LayerNorm）则需调整；且对于极小的batch size（=1）可能存在统计不稳定风险。
- **未与其他高效TTA方法（如T3A）在相同FPS下对比**：虽然帧率远高于MATE，但未与同样无需反向传播的T3A作详细速度-精度联合比较。

（完）
