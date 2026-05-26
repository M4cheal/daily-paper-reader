---
title: "BECoTTA: Input-dependent Online Blending of Experts for Continual Test-time Adaptation"
title_zh: BECoTTA：面向持续测试时自适应的输入依赖在线专家混合
authors: "Daeun Lee, Jaehong Yoon, Sung Ju Hwang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=5zXTwX92qv"
tags: ["query:tta"]
score: 9.0
evidence: 在线持续测试时自适应，混合专家策略
tldr: 持续测试时自适应面临实时性、内存和泛化挑战。本文提出BECoTTA框架，通过输入依赖的在线专家混合策略，高效更新参数，适应不断变化的环境。在多个连续域转移场景下，BECoTTA在保持旧域性能的同时快速适应新域，证明了其有效性和扩展性。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-5zxtwx92qv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5zxtwx92qv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1545, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5zxtwx92qv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1693, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5zxtwx92qv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 823, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5zxtwx92qv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 861, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5zxtwx92qv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 875, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5zxtwx92qv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1251, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5zxtwx92qv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1635, \"height\": 544, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1779, \"height\": 717, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1773, \"height\": 662, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 828, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1686, \"height\": 476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 859, \"height\": 447, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 815, \"height\": 115, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 771, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1688, \"height\": 608, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1777, \"height\": 712, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1779, \"height\": 708, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1705, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1682, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 990, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1058, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1136, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1227, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1182, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1644, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1091, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1176, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5zxtwx92qv/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1772, \"height\": 857, \"label\": \"Table\"}]"
motivation: 持续测试时自适应需要实时、内存高效且能泛化到新域并保持旧域性能。
method: 提出BECoTTA，通过输入依赖的在线专家混合，高效更新参数。
result: 在多个连续域转移基准上，BECoTTA优于现有方法，实现实时自适应。
conclusion: BECoTTA为持续测试时自适应提供了参数高效且有力的解决方案。
---

## Abstract
Continual Test-Time Adaptation (CTTA) is designed to optimize the model during deployment under changing conditions. CTTA is an important problem as it enables models to remain effective and reliable in dynamic and evolving environments. However, tackling the CTTA problem is nontrivial. The model needs to be computationally and memory-efficient to rapidly update its parameters for ever-changing environments in real-time. Also, the model should generalize well to new unseen domains while maintaining its capability on previously encountered ones, as old domains can be revisited in future adaptation phases. To tackle these challenges, this paper proposes BECoTTA, a parameter/memory-efficient yet powerful framework for CTTA. We introduce Mixture-of-Domain Low-rank Experts (MoDE) that contains two core components: i) Domain-Adaptive Routing, which can aid in selectively capturing the domain-adaptive knowledge, and ii) Domain-Expert Synergy Loss to maximize the dependency between each domain and expert. We validate our proposed method over multiple CTTA benchmarks, getting 5.81% performance gain, while only requiring 0.001x trainable parameters. We also provide analyses of our BECoTTA, including expert assignment and target domain relation.

---

## 论文详细总结（自动生成）

# 论文详细中文总结：BECoTTA: Input-dependent Online Blending of Experts for Continual Test-time Adaptation

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：持续测试时自适应（CTTA）要求模型在部署后，连续地适应多个未见过的目标域，同时避免遗忘先前学到的知识，并保持计算和内存效率。
- **现有局限**：
  - 现有方法（如CoTTA、TENT、SAR）或更新全模型导致计算昂贵且易遗忘，或仅更新少量模块导致次优收敛。
  - 多数方法假设测试域是**不连续切换**的（如一个时段只出现一种天气），但真实世界往往是**渐进变化**（如天气逐渐从阴天变为雨天）。
  - 缺乏对域间知识协同与隔离的建模，导致负向干扰。
- **本文目标**：提出一种**输入依赖、参数高效、模块化**的CTTA框架BECoTTA，实现高效的持续自适应，并引入更现实的**渐进域偏移（CGS）**基准。

## 2. 方法论
### 核心思想
- 在预训练ViT每个块之上插入**Mixture-of-Domain Low-rank Experts (MoDE)**层。
- 通过**多个域路由器**（Domain-Adaptive Routers）根据输入分配不同的低秩专家，实现输入依赖的稀疏激活。
- 利用**域-专家协同损失**最大化域与专家之间的互信息，促进专家间合作与特化。
- 仅更新MoDE层参数（冻结其他部分），大幅减少可训练参数量。

### 关键技术细节
- **MoDE层**：
  - 低秩专家 \( A_i = \sigma(x W_i^{\text{down}}) W_i^{\text{up}} \)，其中秩 \( r \) 远小于嵌入维度。
  - \( N \) 个专家，每个专家独立处理输入。
- **域自适应路由**：
  - 对每个域 \( d \) 设置独立路由器 \( G_d \)，参数为 \( W_d^g, W_d^{\text{noise}} \)。
  - 通过带噪声的top-k softmax选择 \( K \) 个专家。
  - 输出：\( h_d(x) = \sum_i G_d^i(x) \cdot A_i(x) \)，再与原始输入残差连接。
- **域-专家协同损失**：
  - 基于路由器输出的条件分布 \( P(A_i|d) \)，计算联合分布 \( P(A_i, d) \)（假设域均匀分布）。
  - 最大化互信息 \( \Theta(D;A) = \sum_d \sum_i P(A_i,d) \log \frac{P(A_i,d)}{P(A_i)P(d)} \)。
- **训练流程**：
  - **初始化阶段**（warm-up）：使用源域增强（SDA）生成D个代理域，训练MoDE层和域判别器（DD），损失包括分割交叉熵、DD分类交叉熵和协同损失。
  - **测试时自适应**：冻结Backbone和DD，对于每个输入 \( x_t \)，DD输出伪域标签 \( \hat{d} \)，激活对应路由器，用熵最小化损失（带置信度滤波）更新MoDE层。
- **可选变体**：
  - BECoTTA（无SDA，单路由器）
  - BECoTTA+（有SDA，多路由器）

## 3. 实验设计
### 数据集与场景
- **CDS-Easy**（平衡天气偏移）：Cityscapes→ACDC（fog, night, rain, snow），每类400张，4个任务。
- **CDS-Hard**（不平衡天气+区域偏移）：新增BDD-100k的Clear和Overcast共5个域，每类500张。
- **CGS**（连续渐变偏移）：基于CDS-Easy，按高斯采样分布构造4个渐变任务（blurry boundaries）。
- **分类基准**：CIFAR10→CIFAR10C、CIFAR100→CIFAR100C（15种常见损坏，severity 5）。
- **域泛化基准**：零样本测试在BDD-100k、Mapillary、GTAV、Synthia。

### 对比方法
- CoTTA、TENT、SAR、EcoTTA、DePT、VDP、TTN、BN Stats Adapt、TTT++, SWRNSP, NOTE, EATA 等。
- 均采用公平对比：分别报告w/o SDA和w/ SDA的基线结果。

## 4. 资源与算力
- **论文未明确说明使用的GPU型号、数量及训练时长**。
- 仅提及优化器（AdamW/Adam），学习率0.00006，批次大小1（在线），warm-up 10 epoch。
- 因此无法量化具体算力消耗，但可推断由于参数量极低（0.09M~3.32M），所需资源远小于CoTTA（54.72M）。

## 5. 实验数量与充分性
- **实验覆盖广泛**：包括3个CTTA语义分割场景（Easy/Hard/CGS）、2个分类任务、1个域泛化任务。
- **消融实验充分**：
  - 对MoDE各组件（DD、MoDE、协同损失）进行消融。
  - 对专家数量、隐藏维度、路由策略、不同初始化方式（随机、源域、SDA）、SDA质量、Warm-up损失权重等进行系统分析。
  - 测量了5次运行的标准差，证明稳定性。
- **公平性**：分别报告w/o SDA和w/ SDA两种设置，与基线严格对齐（如EcoTTA也采用相同warm-up）。
- **整体实验数量较多（文中表格超过20个）**，结论可信。

## 6. 主要结论与发现
- BECoTTA在**所有CTTA场景**中均取得最佳性能：
  - CDS-Hard中，BECoTTA-S比CoTTA提升+1.0% mIoU，参数减少**608倍**（0.09M vs 54.72M）。
  - CDS-Easy中，BECoTTA-M比EcoTTA提升+3.7% mIoU，参数更少。
  - CGS场景中，BECoTTA-L比EcoTTA提升+3.2% mIoU。
- 分类任务：CIFAR100C中平均错误率35.5%，低于CoTTA（38.1%）和EcoTTA（36.4%）。
- **遗忘问题得到有效控制**：多轮后性能几乎不下降（BWT为正），而TENT、SAR严重遗忘。
- **专家分析**显示：语义相似域（如Clear与Overcast）共享专家，独特域（Night）激活独立专家，验证了协同与特化效果。

## 7. 优点
- **参数/内存极高效率**：可训练参数仅为CoTTA的0.1%~2%，内存占用极低，适合嵌入式设备。
- **模块化与灵活**：可任意调整专家数、隐藏维度、路由器数量，适应不同资源约束。
- **解决了遗忘-适应权衡**：通过域专属路由和协同损失，新域学习不影响旧域知识。
- **提出了更现实的CGS基准**：模拟连续渐变域，贴近真实自动驾驶等场景。
- **分析深入**：提供了专家分配频次、域间相似性可视化，以及伪标签质量对比。

## 8. 不足与局限
- **需要用户选择超参数**：专家数 \( N \)、路由数 \( D \)、隐藏维度 \( r \)、top-k \( K \) 等需手动调优，存在轻微性能波动。
- **依赖源域初始化**：虽然随机初始化也可工作，但使用SDA warm-up性能显著提升，这要求预训练阶段访问源数据（但符合CTTA惯例）。
- **主要验证在语义分割和分类**：其他任务（如目标检测、多模态）未探索，适用性有限。
- **未报告实际硬件部署细节**：缺乏推理时实际功耗、延迟等关键指标。
- **渐进场景CGS仍为基于高斯采样**：与真实连续流（如视频帧）可能仍有差距。

（完）
