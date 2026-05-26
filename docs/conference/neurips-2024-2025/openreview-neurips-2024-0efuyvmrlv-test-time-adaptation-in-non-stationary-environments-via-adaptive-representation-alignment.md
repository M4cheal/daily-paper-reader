---
title: Test-time Adaptation in Non-stationary Environments via Adaptive Representation Alignment
title_zh: 非平稳环境下通过自适应表征对齐的测试时自适应
authors: "Zhen-Yu Zhang, Zhiyu Xie, Huaxiu Yao, Masashi Sugiyama"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=0EfUYVMrLv"
tags: ["query:tta"]
score: 8.0
evidence: 非平稳流中的在线测试时自适应通过表征对齐
tldr: 在非平稳环境中，数据流连续变化且仅有少量无标签数据可用。现有持续TTA方法使用伪标签但忽略表征对齐。本文提出非平稳表征学习来自适应对齐无标签数据流与源域表征，从而提升伪标签质量并实现更鲁棒的在线自适应。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-0efuyvmrlv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1398, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0efuyvmrlv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1393, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0efuyvmrlv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 684, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0efuyvmrlv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 684, \"height\": 391, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-0efuyvmrlv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1422, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0efuyvmrlv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1418, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0efuyvmrlv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1265, \"height\": 111, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0efuyvmrlv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1412, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0efuyvmrlv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 89, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0efuyvmrlv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1414, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0efuyvmrlv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0efuyvmrlv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1418, \"height\": 496, \"label\": \"Table\"}]"
motivation: 持续TTA中伪标签方法缺乏对源域表征的探索，在非平稳环境中性能有限。
method: 利用非平稳表征学习自适应对齐无标签数据流与源域表征。
result: 在多个非平稳数据流基准上达到更优的持续自适应效果。
conclusion: 该方法强调了表征对齐在持续TTA中的重要性，适用于流式数据场景。
---

## Abstract
Adapting to distribution shifts is a critical challenge in modern machine learning, especially as data in many real-world applications accumulate continuously in the form of streams. We investigate the problem of sequentially adapting a model to non-stationary environments, where the data distribution is continuously shifting and only a small amount of unlabeled data are available each time. Continual test-time adaptation methods have shown promising results by using reliable pseudo-labels, but they still fall short in exploring representation alignment with the source domain in non-stationary environments. In this paper, we propose to leverage non-stationary representation learning to adaptively align the unlabeled data stream, with its changing distributions, to the source data representation using a sketch of the source data. To alleviate the data scarcity in non-stationary representation learning, we propose a novel adaptive representation alignment algorithm called Ada-ReAlign. This approach employs a group of base learners to explore different lengths of the unlabeled data stream, which are adaptively combined by a meta learner to handle unknown and continuously evolving data distributions. The proposed method comes with nice theoretical guarantees under convexity assumptions. Experiments on both benchmark datasets and a real-world application validate the effectiveness and adaptability of our proposed algorithm.

---

## 论文详细总结（自动生成）

好的，遵照您的要求，以下是对论文《Test-time Adaptation in Non-stationary Environments via Adaptive Representation Alignment》的结构化、深入、客观的中文总结。

---

### 论文核心问题与整体含义（研究动机和背景）

- **核心问题**：在非平稳环境中进行持续测试时自适应（Continual Test-time Adaptation, TTA）。具体而言，模型部署后，测试数据以流的形式连续到达，其数据分布会随时间不断变化（例如天气变化、传感器退化等），且每一时刻仅有少量无标签数据可用。现有方法主要依赖可靠的伪标签来更新模型，但在非平稳环境下对源域表征的探索不足，导致自适应效果受限。
- **整体含义**：本文提出通过非平稳表征学习（Non-stationary Representation Learning）来自适应地将不断变化的无标签数据流与源域表征对齐，从而提升伪标签质量，实现更鲁棒的在线自适应。该方法旨在解决在线学习中数据量少、分布变化未知且连续的挑战。
- **研究动机**：现有持续TTA方法（如CoTTA、SAR）虽能通过重置或筛选样本缓解遗忘，但未充分利用源域表征信息；而传统表征对齐方法（如TTAC）假设分布固定，直接应用于非平稳流时存在高偏差或高方差的问题。

### 论文提出的方法论

- **核心思想**：利用源数据的一个“概要”（sketch，即均值和协方差）作为锚点，通过在线学习框架持续更新表征学习模块，使得每个时刻无标签数据经过投影后的表征分布与源域表征分布尽可能接近。同时，使用熵最小化并辅以对初始分类器的正则化，进一步优化分类器。
- **关键技术细节**：
    1. **问题形式化**：模型由表征学习模块 \( \phi_t(\cdot) \) 和线性分类器 \( w_t \) 组成。目标是最小化动态遗憾（Dynamic Regret），即学习到的模型序列与每个时刻最优模型之间的累计期望损失差。
    2. **表征对齐损失**：使用高斯近似衡量表征差异，损失函数为：  
       \( L_t(\phi, \phi_0) = \|\mu_t - \mu_0\|_2^2 + \lambda \|\Sigma_t - \Sigma_0\|_F^2 \)  
       其中 \( \mu_0, \Sigma_0 \) 是源表征的均值和协方差，\( \mu_t, \Sigma_t \) 是当前时刻目标表征的均值和协方差。
    3. **自适应表征对齐算法（Ada-ReAlign）**：
       - **基学习器（Base Learner）**：一组具有不同学习窗口长度（长度分别为 \( 2^i \)）的在线梯度下降模型。每个基学习器在窗口结束时重启，重新从初始模型开始学习。窗口短的模型适应快速变化，窗口长的模型利用更多历史数据。
       - **元学习器（Meta Learner）**：采用AdaNormalHedge算法，根据每个基学习器在当前时刻的损失动态调整其权重，输出加权组合的表征。
       - **分类器更新**：在得到对齐后的表征后，通过熵最小化加初始分类器正则化更新线性分类器。
- **算法流程（文字说明）**：
    1. 初始化所有基学习器参数为 \( \phi_0 \)。
    2. 对于每个时间步 \( t \)：
       - 判断哪些基学习器到达窗口终点，将其参数重置为 \( \phi_0 \)。
       - 使用当前批次数据计算每个基学习器的损失（式3），并更新其参数（式4）。
       - 元学习器根据AdaNormalHedge更新权重（式6）。
       - 组合基学习器输出最终表征（式5）。
       - 基于最终表征，通过熵最小化更新分类器（式7）。
- **理论保证**：在凸损失和凸模型假设下，算法达到 \( O(T^{2/3} V_T^{1/3}) \) 的动态遗憾，其中 \( V_T \) 衡量分布变化程度。

### 实验设计

- **数据集与场景**：
  - **基准数据集**：CIFAR10-C（CIFAR10到CIFAR10-C）和 ImageNet-C（ImageNet到ImageNet-C）。这些数据集包含不同种类和严重程度的 corruption，用于模拟非平稳流。
  - **分布偏移类型**：
    - 渐近偏移（Gradual Shift）：保持 corruption 类型不变，每隔 \( M \) 轮改变严重程度。
    - 序列偏移（Sequential Shift）：保持严重程度不变，每隔 \( M \) 轮改变 corruption 类型。
  - **真实世界应用**：iWildCam 野生动物分类数据集，数据按时间和地点自然变化。
- **Benchmark 与对比方法**：
  - 包括非自适应基线（Non-adapt）、每轮重置的方法（MEMO、TENT-RE）、持续累积更新的方法（TENT-CT、TTAC）、以及专为非平稳环境设计的 SOTA 方法（CoTTA、SAR）。
- **主要实验设置**：每轮数据量 \( N_t = 10 \)，分布持续时间 \( M = 10 \)，模型为 ResNet-50，仅更新归一化层的仿射参数。

### 资源与算力

- **硬件配置**：论文附录 A.1 明确说明使用了 2 个 Intel Xeon Gold 6242R CPU（3.1 GHz）、8 块 NVIDIA GeForce 3090 GPU（24GB VRAM）、以及 768GB RAM。操作系统为 Ubuntu 20.04。
- **训练时长**：论文未报告具体的运行时间，但提到 Ada-ReAlign 每轮处理时间约为单模型方法（如 SAR）的 5 倍，因为需要维护多个基学习器（最多 \( \log(T) \) 个，例如 T=100,000 时仅需 11 个）。实际耗时与轮次数、模型大小相关。

### 实验数量与充分性

- **实验数量**：
  - 主实验：两大数据集（CIFAR10-C, ImageNet-C）在两种偏移（渐近、序列）下，各 15 种 corruption 类型，报告平均分类错误率及标准差（5 次随机初始化）。
  - 消融实验：包括组件分析（有无表征对齐、有无熵最小化）、重启机制比较（随机重启、持续更新、阈值重启）、不同窗口大小的元学习器权重可视化。
  - 超参数敏感性：不同每轮数据量 \( N_t \)（1,5,10,20,50）和分布持续时间 \( M \)（5,10）的对比。
  - 真实世界数据集：iWildCam 上与非自适应、TTAC、CoTTA、SAR 的对比。
- **充分性评价**：实验较为充分。覆盖了主流 benchmark、多种偏移模式、多个 SOTA 对比方法，并进行了详细的消融和敏感性分析。结果均报告均值和标准差，具有良好的可重复性。公平性方面，所有对比方法采用了作者说明书中的默认超参数，且 Ada-ReAlign 保持了相似的训练设置（仅更新仿射参数）。因此实验设计客观公平。

### 论文的主要结论与发现

1. **Ada-ReAlign 在非平稳 TTA 中效果领先**：在 CIFAR10-C 和 ImageNet-C 的渐近和序列偏移下，Ada-ReAlign 均取得最低的平均分类错误率，尤其在序列偏移（分布类型频繁变化）场景下优势显著。
2. **自适应表征对齐是关键**：消融实验表明，同时使用表征对齐和熵最小化效果最好，且表征对齐贡献更大，验证了自适应对齐在非平稳环境中的重要性。
3. **元学习器能自动选择合适的历史窗口**：权重可视化显示，元学习器会根据数据分布变化的周期，自动将高权重赋予与之匹配的基学习器，实现了对历史数据的最优利用。
4. **理论保证有效**：动态遗憾的理论界与实验性能一致，表明算法能适应未知的连续分布变化。

### 优点

1. **方法新颖且动机明确**：将非平稳表征学习引入持续 TTA，解决了现有方法忽视源域表征对齐的问题，思路清晰。
2. **算法设计巧妙**：利用在线集成框架（基学习器+元学习器）自适应平衡偏差-方差，无需预设变化检测机制，通用性强。
3. **理论与实践结合**：在凸假设下提供了严谨的动态遗憾分析，为算法有效性提供理论基础。
4. **实验全面**：涵盖多种主流 benchmark、真实世界数据，以及详尽的消融、敏感性和效率分析，结论可信。

### 不足与局限

1. **理论假设较强**：理论分析依赖于模型和损失函数的凸性假设，而实际深度神经网络通常是非凸的。虽然作者指出用于指导，但理论结论与深度模型实践的鸿沟仍然存在。
2. **计算开销**：由于维护多个基学习器，每轮正向传播和反向传播次数成比例增加（约 5 倍于单模型 SAR），对于实时性要求极高的应用可能存在瓶颈。作者通过仅更新仿射参数来缓解，但未与其他轻量方法（如只更新 BN 统计量）进行效率对比。
3. **对源数据概要的依赖**：需要预先计算源域表征的均值和协方差，若源域数据不可用或隐私受限，该方法的适用性降低（尽管作者提及可用最近数据集技术生成）。
4. **实验覆盖有限**：未涉及大规模语言模型或视觉 Transformer 等现代大模型场景，也未探索更复杂的时间依赖性分布变化（如周期性循环、随机跳变）。此外，仅测试了 ResNet-50，缺少对其他架构的迁移性验证。
5. **未讨论灾难性遗忘的量化**：虽然用动态遗憾间接衡量，但没有像 CoTTA 等专门分析遗忘的指标（如向旧分布回测性能）。

---

（完）
