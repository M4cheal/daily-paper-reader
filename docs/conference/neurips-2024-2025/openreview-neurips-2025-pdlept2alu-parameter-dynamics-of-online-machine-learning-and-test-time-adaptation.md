---
title: Parameter Dynamics of Online Machine Learning and Test-time Adaptation
title_zh: 在线机器学习和测试时间自适应的参数动力学
authors: Jae-Hong Lee
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=pdlepT2alu"
tags: ["query:tta"]
score: 9.0
evidence: 测试时间自适应的理论基础和稳定性分析
tldr: 在线学习设置中测试时间自适应常因非独立同分布数据导致参数不稳定。本文提出一个概率框架，利用随机微分方程建模自适应过程中的参数动力学。该框架从理论上分析了非独立同分布环境对参数稳定性的影响，揭示了现有方法忽略的风险，并为设计更稳定的TTA算法提供了指导。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1300, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1299, \"height\": 737, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 576, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 650, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1435, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 650, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1307, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1441, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 704, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 723, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 562, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 559, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdlept2alu/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1440, \"height\": 307, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdlept2alu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdlept2alu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdlept2alu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 358, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdlept2alu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1463, \"height\": 1165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdlept2alu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdlept2alu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdlept2alu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 698, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdlept2alu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1441, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdlept2alu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 518, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdlept2alu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 700, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdlept2alu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 713, \"height\": 282, \"label\": \"Table\"}]"
motivation: 为在线测试时间自适应中的参数不稳定现象提供理论分析。
method: 使用随机微分方程建模参数更新过程，分析稳定性条件。
result: 理论推导了非独立同分布数据下的参数动力学，实验验证了理论预测。
conclusion: 该框架为理解并改进在线TTA的稳定性提供了理论基础。
---

## Abstract
Pre-trained models based on deep neural networks hold strong potential for cross-domain adaptability. However, this potential is often impeded in online machine learning (OML) settings, where the breakdown of the independent and identically distributed (i.i.d.) assumption leads to unstable adaptation. While recent advances in test-time adaptation (TTA) have addressed aspects of this challenge under unsupervised learning, most existing methods focus exclusively on unsupervised objectives and overlook the risks posed by non-i.i.d. environments and the resulting dynamics of model parameters. In this work, we present a probabilistic framework that models the adaptation process using stochastic differential equations, enabling a principled analysis of parameter distribution dynamics over time. Within this framework, we find that the log-variance of the parameter transition distribution aligns closely with an inverse-gamma distribution under stable and high-performing adaptation conditions. Motivated by this insight, we propose Structured Inverse-Gamma Model Alignment (SIGMA), a novel algorithm that dynamically regulates parameter evolution to preserve inverse-gamma alignment throughout adaptation. Extensive experiments across diverse models, datasets, and adaptation scenarios show that SIGMA consistently enhances the performance of state-of-the-art TTA methods, highlighting the critical role of parameter dynamics in ensuring robust adaptation.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在线机器学习（OML）和测试时间自适应（TTA）中，数据流通常违反独立同分布（i.i.d.）假设，导致模型参数动态不稳定、性能退化甚至崩溃。现有TTA方法大多只关注无监督损失函数设计（如熵最小化），忽视了非i.i.d.环境对参数演化过程的影响。
- **研究动机**：作者认为，理解并显式控制参数动态对于稳定自适应至关重要。通过建立概率框架，可以揭示参数分布随时间的演化规律，并利用这一规律指导算法设计。
- **整体含义**：本文从随机微分方程（SDE）角度建模参数更新过程，发现参数过渡分布的**对数方差（log-variance）**在稳定且高性能的自适应条件下始终服从**逆伽马（Inverse-Gamma, IG）分布**。偏离这一对齐是性能退化的先兆。基于此，提出SIGMA算法动态维持IG对齐，从而显著提升现有TTA方法的鲁棒性和性能。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 将随机梯度下降（SGD）近似为连续时间SDE，得到参数过渡分布 \( p(\mathbf{w}(t_k)|\mathbf{w}(t_{k-1})) \approx \mathcal{N}(\mathbf{w}(t_k)|\boldsymbol{\mu}_{k|k-1}, \boldsymbol{\Sigma}_{k|k-1}) \)，其中均值 \(\boldsymbol{\mu}_{k|k-1} = \mathbf{w}(t_{k-1}) - \mathbf{g}_k \Delta t\)，协方差 \(\boldsymbol{\Sigma}_{k|k-1} = \sigma_k^2 \Delta t^2 \mathbf{I}\)，\(\Delta t = \eta\)（学习率）。
- 定义**对数方差** \( v_k = \log(\sigma_k^2 \Delta t^2) \)，收集所有 \( v_k \) 构成**对数方差画像**（log-variance portrait）。实证发现，在稳定条件下该画像与IG分布高度吻合。
- 显式维护log-variance与IG分布的对齐，通过动态调整有效更新间隔 \(\Delta t_k\) 来调节参数更新轨迹。

### 关键技术细节（SIGMA算法）
1. **Estimate Step**：利用过去已校正的对数方差 \(\tilde{v}_{1:k-1}\)，通过最小化KL散度（使用Nelder-Mead无导数优化）估计一个参考IG分布 \( q(v;\alpha_{k-1}) \)。
2. **Align Step**：在当前步，通过优化负对数似然求解最优位置修正系数 \( c_k^* \) 和尺度因子 \( b_k^* \)，将当前 \( v_k \) 校正为 \(\tilde{v}_k = (v_k - c_k^*)/b_k^* + 2\log\lambda\)，其中 \(\lambda\) 为对齐强度超参数。由此得到有效更新间隔 \(\Delta t_k = (\lambda r_k T_k)\Delta t\)，其中 \( r_k = \exp(-c_k^*/2b_k^*)\)（放大间隔以修正位置偏移），\( T_k = (\sigma_k \Delta t)^{(1-b_k^*)/b_k^*}\)（缩小间隔以响应高方差）。
3. **Conjugate Step**：使用修正后的 \(\Delta t_k\) 更新参数的后验均值 \(\boldsymbol{\mu}_k = \hat{\mathbf{w}}_0 - \sum_{i=1}^k \mathbf{g}_i \Delta t_i\)，并以此均值进行预测。

- 整个流程不引入额外隐变量，计算开销极小，仅依赖标量方差观测。

## 3. 实验设计：数据集/场景、benchmark、对比方法

### 数据集与场景
- **多域自适应**：ImageNet-C（15种 corruption，5级严重度，默认按Noise→Blur→Weather→Digital顺序）、D109（DomainNet子集，5个自然域，109类）。
- **单域自适应**：Rendition（30,000张风格化图像，200类）、Sketch（50,000张素描，1000类）。
- **小规模多域**：CIFAR10-C、CIFAR100-C（ResNet模型）。
- **现实场景**：TEDLIUM3语音识别（8/11个说话人，WER指标）。
- **非i.i.d.设置**：
  - **Correlated Input**：域按固定顺序连续呈现。
  - **Correlated Label**：标签分布由Dirichlet(γ)生成，γ越小标签局部性越强，γ=0.1和0.0分别测试。
- 重复数据集实验：同一域序列重复15次。

### Benchmark
- 遵循标准化TTA基准协议，所有结果来自4个随机种子的平均错误率（AER）和标准差。

### 对比方法
- **基线TTA方法**：TENT、EATA、DeYO、ROID、RoTTA、SAR。
- **学生-教师方法**：CoTTA、PETAL（FIM变体）、RMT。
- **语音TTA**：Pseudo Label、SUTA。
- **消融/变体**：SIGMA作为插件集成到TENT、EATA、DeYO、ROID中。

## 4. 资源与算力

- 论文明确说明：**所有实验使用单张NVIDIA GeForce RTX 4090 GPU**。
- 未给出总训练时长，但提及SIGMA额外开销极小（例如对EATA和ROID仅增加约0.04 ms/样本）。

## 5. 实验数量与充分性

- **实验数量**：非常充分。
  - 主表3张（Correlated Input、Correlated Label γ=0.1、γ=0.0 on ImageNet-C）。
  - 附录表6张（ViT、Swin、Rendition、Sketch、D109 Correlated Input/Label、CIFAR10/100-C）。
  - 额外实验：不同域顺序（4种排列）、对齐强度λ的敏感性（9个值）、重复数据集（15轮）、语音识别场景（2个集）。
  - 可视化：log-variance画像对比（多个设置、多个模型架构）。
- **客观性/公平性**：
  - 使用官方实现和默认超参数，参考标准化TTA基准库。
  - 禁用ROID的可选先验修正模块以保证公平。
  - 报告4个随机种子平均和标准差，体现统计可靠性。
  - 跨模型（ViT, Swin, D2V）、跨数据集、跨场景的一致结果增强了结论可信度。

## 6. 论文的主要结论与发现

1. **IG对齐是稳定自适应的关键标志**：在SL i.i.d.条件下log-variance始终服从IG分布；非i.i.d.或无监督条件下该对齐破坏，导致性能下降。
2. **IG-GoF（拟合优度）与性能正相关**：K-S检验p值越高，RAER（相对错误率改善）越好；p值低于约0.01时出现性能退化。
3. **现有样本过滤方法隐式促进IG对齐**：DeYO和ROID比TENT更接近IG形状，但仍存在偏差。
4. **SIGMA显式维持IG对齐可显著提升性能**：在所有测试方法、架构、数据集上一致改进，例如在ImageNet-C Correlated Input上将EATA的AER从50.2%降至44.8%，ROID从44.3%降至41.8%。
5. **SIGMA效率高**：额外计算开销极小，适合在线场景。
6. **SIGMA防止崩溃**：在Correlated Label等困难设置下，TENT+IGMA逆转了TENT的严重退化（γ=0.1时AER从55.4%降至50.5%）。

## 7. 优点：方法或实验设计上的亮点

- **理论切入新颖**：不同于仅设计损失函数，从SDE角度建模参数动态，发现log-variance与IG分布的联系，提供了统计诊断信号。
- **算法简洁高效**：SIGMA仅依赖标量方差和无导数优化，不引入额外隐变量，内存和计算开销可忽略。
- **实验非常全面**：覆盖多种非i.i.d.场景（域序、标签偏移）、多种模型（ViT, Swin, D2V, ResNet）、多种数据集（合成腐蚀、自然域、语音、小规模），且包含重复数据和敏感度分析，结果高度一致。
- **公平性考量**：严格执行基准协议，禁用可能带来不公平优势的模块，报告标准差。
- **可解释性强**：log-variance画像可视化直观展示了不同条件下参数稳定性的变化。
- **即插即用**：SIGMA作为插件能显著增强现有TTA方法，实用价值高。

## 8. 不足与局限

- **高斯假设**：论文假设参数分布为高斯形式（通过SDE线性化），可能限制了对真实复杂分布的刻画。作者坦言这是局限，并计划未来扩展到非高斯情况。
- **超参数λ的敏感性**：虽通过实验证明在一定范围内鲁棒，但λ需针对不同方法手动设定（文中固定值），过于极端的λ会导致性能急剧下降（见附录C.4）。
- **未覆盖全部场景**：虽然实验丰富，但未在更大规模模型（如LLM）或更极端的非平稳流上进行测试。
- **依赖历史方差**：最初几个时间步没有足够历史数据时算法可能不稳定（算法中仅在|˜v1:k|>1时激活）。
- **忽略标签分布内部动态**：Correlated Label测试中，标签偏移只由Dirichlet生成，未探索更结构化的标签转移。
- **算力信息不完整**：未报告总实验耗时，仅提及GPU类型和每样本耗时。

（完）
