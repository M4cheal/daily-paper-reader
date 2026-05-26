---
title: "Beyond Entropy: Region Confidence Proxy for Wild Test-Time Adaptation"
title_zh: 超越熵：面向野生测试时自适应的区域置信度代理
authors: "Zixuan Hu, Yichun Hu, Xiaotong Li, SHIXIANG TANG, LINGYU DUAN"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=QwxjjaGBUo"
tags: ["query:tta"]
score: 9.0
evidence: 基于区域置信度的野生测试时自适应
tldr: 本文针对野生测试时自适应（WTTA）中熵最小化框架的优化噪声问题，提出区域置信度作为替代目标，并设计ReCAP方法通过区域集成策略间接优化该目标，避免直接计算的高昂代价。实验表明ReCAP在多个WTTA基准上显著提升效率与性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-qwxjjagbuo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qwxjjagbuo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1760, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qwxjjagbuo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1661, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qwxjjagbuo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qwxjjagbuo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 857, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qwxjjagbuo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qwxjjagbuo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1239, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qwxjjagbuo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1741, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qwxjjagbuo/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1429, \"height\": 1018, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qwxjjagbuo/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1233, \"height\": 493, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-qwxjjagbuo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1760, \"height\": 884, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qwxjjagbuo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 837, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qwxjjagbuo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1760, \"height\": 884, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qwxjjagbuo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qwxjjagbuo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1761, \"height\": 430, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qwxjjagbuo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1764, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qwxjjagbuo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1240, \"height\": 253, \"label\": \"Table\"}]"
motivation: 熵最小化在WTTA中存在噪声优化问题，严重制约自适应效率。
method: 提出区域置信度代理（ReCAP），通过区域集成方法间接优化，避免直接计算的高昂代价。
result: 在多个野生域偏移数据集上，ReCAP优于现有WTTA方法，同时计算开销更低。
conclusion: 区域置信度是熵的更优替代，为WTTA提供了高效优化框架。
---

## Abstract
Wild Test-Time Adaptation (WTTA) is proposed to adapt a source model to unseen domains under extreme data scarcity and multiple shifts. Previous approaches mainly focused on sample selection strategies, while overlooking the fundamental problem on underlying optimization. Initially, we critically analyze the widely-adopted entropy minimization framework in WTTA and uncover its significant limitations in noisy optimization dynamics that substantially hinder adaptation efficiency. Through our analysis, we identify region confidence as a superior alternative to traditional entropy, however, its direct optimization remains computationally prohibitive for real-time applications. In this paper, we introduce a novel region-integrated method **ReCAP** that bypasses the lengthy process. Specifically, we propose a probabilistic region modeling scheme that flexibly captures semantic changes in embedding space. Subsequently, we develop a finite-to-infinite asymptotic approximation that transforms the intractable region confidence into a tractable and upper-bounded proxy. These innovations significantly unlock the overlooked potential dynamics in local region in a concise solution. Our extensive experiments demonstrate the consistent superiority of ReCAP over existing methods across various datasets and wild scenarios. The source code will be available at https://github.com/hzcar/ReCAP.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：测试时自适应（TTA）旨在让预训练模型在推理阶段适应目标域的分布偏移，但现有方法在“野生”场景（Wild TTA）下表现不佳。野生场景包含极端数据稀缺（如 batch size=1）、多种偏移同时存在（混合域、类别分布偏移）等挑战。
- **核心问题**：当前主流的TTA方法（如Tent、SAR、DeYO）均采用**熵最小化**作为优化目标。然而作者通过实验发现，在野生场景下熵最小化会导致**局部预测不一致**——语义相似的样本在局部区域内预测出现严重分歧，从而产生相互冲突的优化方向，极大地阻碍了自适应效率。
- **整体含义**：本文提出**区域置信度（Region Confidence）** 作为熵的替代目标，并设计高效代理优化框架ReCAP，以利用局部区域信息来提升自适应稳定性和效率。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：从“样本级”置信度转向“区域级”置信度。区域置信度同时考虑两个统计量：
  - **偏差项（Bias term）**：局部区域内所有样本熵的积分，反映整体不确定性；
  - **方差项（Variance term）**：样本预测与其邻域预测之间的KL散度，反映局部一致性。
  两者结合，引导优化方向更一致，减少冲突。

- **关键技术细节**：
  1. **概率区域建模**：将局部区域建模为多元高斯分布 \( \mathcal{N}(z_t, \tau \Sigma) \)，其中 \( \Sigma \) 用少量源数据估计的对角方差矩阵，\( \tau \) 控制区域范围。
  2. **有限到无限渐近近似**：直接计算区域置信度需要无穷采样，计算昂贵。作者推导出两个闭式上界：
     - **区域熵（Regional Entropy, \( L_{RE} \)）**：偏差项的上界，无需额外采样；
     - **区域不稳定性（Regional Instability, \( L_{RI} \)）**：方差项的上界。
  3. **整体优化目标**：
     \[
     \min_{\theta} \alpha(x) \cdot \mathbb{I}_{\{L_{RE}(x) < \tau_{RE}\}} \left( L_{RE}(x) + \lambda L_{RI}(x) \right)
     \]
     其中 \( \alpha(x) \) 为权重函数，\( \mathbb{I} \) 为基于 \( L_{RE} \) 的样本选择。

- **算法流程**：
  - 前向计算提取特征 \( z \)；
  - 利用源数据统计计算 \( \Sigma \)；
  - 根据公式计算 \( L_{RE} \) 和 \( L_{RI} \)；
  - 通过阈值 \( \tau_{RE} \) 筛选可靠样本，加权优化模型参数（仅更新归一化层的仿射参数）。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **ImageNet-C**（15种常见损坏，5个严重等级）：主要实验平台。
  - **ImageNet-R**（风格/纹理偏移，如素描、卡通）和 **VisDA-2021**（多种域偏移）：补充验证。
- **场景**：三种野生场景：
  1. 有限数据流（batch size=1）；
  2. 混合测试域（多个损坏类型混合）；
  3. 不平衡标签偏移（标签分布随时间变化）。
- **对比方法**：MEMO, DDA, Tent, EATA, SAR, DeYO 等 SOTA 方法，还包括 ReCAP 与 SAR/DeYO 的集成版本。
- **评测指标**：Top-1 准确率（%），多次独立运行取均值。

## 4. 资源与算力

- **文中明确说明**：运行时间对比实验使用单张 Nvidia RTX 4090 GPU，处理50,000张图像（Gaussian corruption类型），记录了各方法的前向、反向及其他计算时间。
- **未说明**：训练时长（小时级）、使用的GPU数量（单卡）、总计算量（FLOPs）等细节未提供。
- **结论**：ReCAP 在时间成本上接近 Tent（仅多5%），远低于需额外前向/反向的 SAR 和 DeYO。

## 5. 实验数量与充分性

- **实验数量**：
  - 主实验：ImageNet-C 上3种场景（batch=1、混合域、标签偏移），每种场景报告15种损坏的平均准确率。
  - 补充实验：ImageNet-R 和 VisDA-2021 上两种场景（batch=1、标签偏移）。
  - 消融实验：超参数 \( \lambda \) 和 \( \tau \) 的敏感性分析、\( \tau_{RE} \) 的敏感性、组件贡献（LRE vs LRI）、特征可视化（t-SNE）、局部一致性定量分析、运行时间对比。
  - 集成实验：ReCAP+SAR 和 ReCAP+DeYO 性能。
- **充分性**：
  - **优点**：覆盖多种架构（ResNet50、ViT-Base）、多种偏移类型、多种野生场景；消融实验全面，可视化直观；对比方法均使用官方或标准实现。
  - **不足**：仅聚焦分类任务，未涉及分割、检测等；数据集虽多但仍限于常见基准，真实世界极端场景（如低光照、运动模糊叠加）未被涵盖。

## 6. 论文的主要结论与发现

- 熵最小化在野生场景下会破坏局部一致性，导致优化冲突，是阻碍自适应效率的根本原因之一。
- 区域置信度能够有效缓解该问题，通过同时最小化区域平均熵和内部预测分歧，提升局部一致性和自适应稳定。
- 提出的 ReCAP 方法通过概率建模和渐近近似，实现了无需采样的高效代理优化，计算开销仅略高于纯熵优化。
- 在 ImageNet-C、ImageNet-R、VisDA-2021 上，ReCAP 全面超越现有 WTTA 方法（平均提升约 +2%），并且可无缝集成到其他基于熵的方法（如 SAR、DeYO）中，获得显著增益。
- 特征空间可视化显示 ReCAP 比 DeYO 实现更紧凑的类内聚类和更清晰的类间边界，且自适应过程收敛更快。

## 7. 优点

- **方法创新**：首次系统性地指出熵最小化在野生场景下的局部不一致问题，并提出区域级目标替代；理论推导严谨（给出闭式上界），避免采样带来的计算负担。
- **实用性**：计算效率高（仅比 Tent 慢5%），适合实时部署；可与其他样本选择方法正交结合，具有即插即用特性。
- **实验全面**：覆盖多种架构、多种偏移类型、多种野生场景；消融实验深入（超参数、组件贡献、特征演化），可视化充分。
- **泛化性验证**：在分类任务外（ImageNet-R、VisDA-2021）也取得一致优势，初步证明方法通用性。

## 8. 不足与局限

- **任务局限**：仅测试分类任务，未验证在语义分割、目标检测等更复杂任务上的效果。作者也承认这是主要局限性之一。
- **区域建模局限**：当前采用**域级别**固定的高斯区域（所有样本共享相同协方差）。作者指出更理想的方案应是**类别级或样本级**自适应区域，以应对不同类别边界距离的差异。
- **超参数敏感**：虽然文中展示 \( \tau \) 和 \( \lambda \) 在合理范围内性能稳定，但最优值（如 \( \tau=1.2, \lambda=0.5 \)）仍需通过验证集调参，实际部署可能需额外标定。
- **理论分析深度**：对区域置信度为何能优于熵的理论解释限于统计偏差-方差权衡，更低的优化噪声尚缺乏严格收敛性证明。
- **实验局限性**：虽然覆盖多种损坏和风格偏移，但真实世界可能同时存在数十种未预料的复合偏移，泛化边界有待进一步探索。

（完）
