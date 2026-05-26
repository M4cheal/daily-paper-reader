---
title: Bayesian Weight Enhancement with Steady-State Adaptation for Test-time Adaptation in Dynamic Environments
title_zh: 动态环境中测试时间自适应的贝叶斯权重增强与稳态自适应
authors: Jae-Hong Lee
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=rRQ8hvILhb"
tags: ["query:tta"]
score: 9.0
evidence: 动态环境中测试时间自适应的贝叶斯权重增强框架
tldr: 针对在线TTA中无监督梯度噪声导致权重退化的问题，本文提出贝叶斯权重增强框架。它通过建模权重分布来考虑多样化的权重，并进一步引入稳态自适应以应对动态环境中的时变分布漂移。理论分析和实验表明该方法在多种非平稳分布下比现有TTA方法更鲁棒。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-rrq8hvilhb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 825, \"height\": 1264, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rrq8hvilhb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rrq8hvilhb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rrq8hvilhb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 850, \"height\": 611, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rrq8hvilhb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1752, \"height\": 475, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 884, \"height\": 961, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1759, \"height\": 505, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1760, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1757, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 850, \"height\": 562, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 686, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 871, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 870, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 872, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 488, \"height\": 483, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1229, \"height\": 131, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rrq8hvilhb/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 885, \"height\": 220, \"label\": \"Table\"}]"
motivation: 在线TTA中无监督梯度噪声导致权重退化，现有方法忽略时变特性。
method: 提出贝叶斯权重增强框架，建模权重分布并引入稳态自适应处理时变漂移。
result: 在多种非平稳分布下取得优于现有方法的鲁棒自适应性能。
conclusion: 贝叶斯框架能有效解决在线TTA的权重退化问题，提升动态环境适应性。
---

## Abstract
Test-time adaptation (TTA) addresses the machine learning challenge of adapting models to unlabeled test data from shifting distributions in dynamic environments. 
A key issue in this online setting arises from using unsupervised learning techniques, which introduce explicit gradient noise that degrades model weights. To invest in weight degradation, we propose a Bayesian weight enhancement framework, which generalizes existing weight-based TTA methods that effectively mitigate the issue. Our framework enables robust adaptation to distribution shifts by accounting for diverse weights by modeling weight distributions.
Building on our framework, we identify a key limitation in existing methods: their neglect of time-varying covariance reflects the influence of the gradient noise. To address this gap, we propose a novel steady-state adaptation (SSA) algorithm that balances covariance dynamics during adaptation. SSA is derived through the solution of a stochastic differential equation for the TTA process and online inference. The resulting algorithm incorporates a covariance-aware learning rate adjustment mechanism. Through extensive experiments, we demonstrate that SSA consistently improves state-of-the-art methods in various TTA scenarios, datasets, and model architectures, establishing its effectiveness in instability and adaptability.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究问题**：在动态环境中，测试时自适应（Test-time Adaptation, TTA）需要在无标签测试数据上在线更新模型，以应对不断变化的数据分布。然而，由于使用无监督学习（如熵最小化），梯度估计中存在显式的梯度噪声，导致模型**权重退化**（weight degradation），即模型权重随自适应过程逐渐被噪声污染，性能下降。
- **已有解决方案**：现有的基于权重的TTA方法（如SAR、ROID、CMF）通过将当前权重与预训练的源权重进行加权平均来缓解权重退化，但这些方法**忽略了协方差随时间的变化**，即没有考虑梯度噪声的动态特性。
- **本文目标**：提出一个统一的贝叶斯权重增强框架（Bayesian Weight Enhancement），并基于此框架设计稳态自适应算法（Steady-State Adaptation, SSA），通过动态平衡协方差来同时保证**稳定性**和**适应性**。

## 2. 方法论：核心思想、关键技术细节、算法流程（文字描述）

### （1）贝叶斯权重增强框架
- 将模型权重视为概率分布，而不是确定性点估计。后验分布为：
  - 先验：`p(u|w_k) = N(u|w_k, Q)`
  - 似然：`p(w_{k+1}|u) = N(w_{k+1}|w_0, R)`
  - 后验：`p(u|w_k, w_{k+1}) = N(u|m, P)`
- 后验均值：`m = (I - A) w_k + A w_0`，其中 `A = Q(Q+R)^{-1}`。这恰好是现有权重平均方法的泛化形式。
- 局限性：假设协方差**时不变**（A为常数），忽略了梯度噪声随时间的变化。

### （2）稳态自适应算法（SSA）
- **步骤1：SDE近似** 将随机梯度下降（SGD）的动力过程用随机微分方程建模：
  `du_t = -g_t dt + √η Σ_t^{1/2} dW_t`
  其中 `Σ_t = σ_t^2 I` 是梯度协方差。
- **步骤2：在线后验推断** 利用贝叶斯滤波（Chapman-Kolmogorov方程）递推计算：
  - 一步预测：`m^+_{k+1|k} = m_k - α_k η g_k`，`P^+_{k+1|k} = P_k + α_k^2 η^2 Σ_k`
  - 后验更新：`m_{k+1} = m^+_{k+1|k} + A (w_0 - m^+_{k+1|k})`，`P_{k+1} = (I - A) P^+_{k+1|k}`
- **步骤3：稳态协方差平衡** 通过求解稳态条件 `P_{k+1} ≈ P_k`，得到学习率调节因子：
  `α_k = √(σ_λ^2 / (η^2 σ_k^2))`
  其中 `σ_λ` 为稳态方差参数。当梯度噪声高时降低学习率（增加稳定性），噪声低时提高学习率（增加适应性）。
- **最终算法**（见论文Algorithm 1）：
  - 计算梯度 `g_k` 及梯度方差 `σ_k^2`
  - 计算 `α_k` 并调整更新步长
  - 执行贝叶斯加权平均得到增强后权重 `m_{k+1}`

## 3. 实验设计

### 数据集与场景
- **ImageNet-C**：15种损坏（噪声、模糊、天气、数字），最高严重等级5。
- **D109**：来自DomainNet的5个领域（clipart, infograph, painting, real, sketch），109类。
- **Rendition & Sketch**：自然分布偏移数据集。
- **TEDLIUM3**：真实语音识别场景（连续说话人切换）。
- **场景类型**：
  - 协变量偏移（γ=∞）：按领域顺序流式输入。
  - 标签偏移（γ=0.1, 0.0）：依次呈现特定类别样本。
  - 周期性场景：重复领域序列（最多15轮）。
  - 多种顺序场景（Order-1~4）。

### 对比方法
- **基线**：Source（不更新）
- **样本/梯度级方法**：TENT, LAME, RoTTA, SAR, EATA, DeYO
- **权重级方法**：ROID, CMF
- 所有方法均使用官方代码和推荐超参数。

### 评价指标
- 平均错误率（Error Rate, %）及其标准差（5个随机种子）。

## 4. 资源与算力

- **文中明确说明**：实验使用**单个 NVIDIA GeForce RTX 3090 GPU**（见附录B.1）。
- 训练时长、总GPU小时数等未具体报告。

## 5. 实验数量与充分性

### 实验数量
- 主实验：**3个数据集 × 3种偏移场景（γ=∞, 0.1, 0.0）**，共约9个表格（部分在正文，部分在附录）。
- 额外实验：
  - Rendition & Sketch（表9）
  - 周期性场景（表4）
  - 多种顺序场景（图2）
  - 学习率敏感性分析（图3）
  - 效率对比（表5）
  - 协方差演化分析（图4）
  - 不同模型架构（ViT, Swin, D2V）（表11）
  - 稳态尺度因子敏感性（图5）
  - 真实语音场景（表10）
- **总计约15+组定量实验**，涵盖不同数据集、偏移类型、模型、超参数和消融分析。

### 充分性与客观性
- 实验设计**全面**：覆盖了主流的TTA基准场景和动态环境模拟；对比了7~8种最新方法；多个随机种子报告均值和标准差；代码和配置均公开。
- **公平**：所有对比方法使用原作者推荐的超参数，模型架构一致（ViT/D2V为主，额外验证Swin）。
- 消融实验（如学习率、稳态因子、协方差）直接验证了核心设计的作用。
- 结论具有**泛化性**：在图像分类、语音识别等不同任务上均得到验证。

## 6. 主要结论与发现

1. **贝叶斯权重增强框架**统一解释了现有权重平均方法，并揭示了它们的时不变协方差假设的不足。
2. **SSA算法**通过动态调节学习率来平衡协方差，在多种动态分布偏移场景下**一致提升**了ROID和CMF的性能，达到最先进水平。
3. SSA能有效缓解因学习率增大导致的性能崩溃，扩大可用的学习率范围（最高15倍默认值）。
4. SSA仅带来极小的额外计算开销（相对时间增加1%~4.3%），同时性能提升显著（如TENT提升4.0%）。
5. **协方差是影响TTA性能的关键因素**：SSA通过维持小且稳定的协方差来提高稳定性与适应性。

## 7. 优点

- **理论创新**：将SDE近似与贝叶斯滤波相结合，为权重退化提供了数学解释和解决方案，并给出稳态协方差的解析条件。
- **方法简洁有效**：SSA仅需在现有TTA框架中增加一个学习率缩放因子，易于实现和集成。
- **实验全面且稳健**：覆盖多个数据集、多种动态场景、多种架构，且与多种基线比较，结果统计显著。
- **计算效率高**：无需额外前向/反向传播，只增加了少量标量计算。
- **鲁棒性强**：对超参数（如稳态因子）不敏感，在宽范围内表现稳定。

## 8. 不足与局限

- **线性高斯假设**：框架假定权重分布为高斯且协方差为标量倍单位矩阵，可能无法刻画更复杂的多模态分布。尽管实验有效，但理论上的表达能力有限（论文也承认此局限，并列为未来工作）。
- **小学习率前提**：SDE近似要求学习率足够小，当学习率过大（超过论文阈值）时，SSA性能急剧下降，限制了在快速适应场景中的适用性。
- **模型更新范围限制**：实验仅更新归一化层（不到1%参数），未验证全参数微调等更激进的自适应策略，可能限制方法在更复杂任务中的表现。
- **实验场景仍偏合成**：主要使用ImageNet-C等合成损坏，真实世界动态环境（如自动驾驶连续视频流）的验证有限（仅TEDLIUM3语音任务）。
- **缺乏与贝叶斯神经网络的直接比较**：论文虽基于贝叶斯视角，但未与深度贝叶斯方法（如SWAG、MC Dropout）在TTA任务上进行对比。
- **仅讨论了权重的平均，未涉及样本选择或数据增强**：与样本级方法（如EATA、DeYO）的互补性未深入探讨。

（完）
