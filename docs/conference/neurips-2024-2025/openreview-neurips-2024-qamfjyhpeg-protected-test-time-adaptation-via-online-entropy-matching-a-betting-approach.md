---
title: "Protected Test-Time Adaptation via Online Entropy Matching: A Betting Approach"
title_zh: 基于在线熵匹配的保护性测试时自适应：一种投注方法
authors: "Yarin Bar, Shalev Shaer, Yaniv Romano"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=qamfjyhPeg"
tags: ["query:tta"]
score: 9.0
evidence: 针对流数据的在线测试时自适应
tldr: 该论文提出一种基于在线熵匹配的测试时自适应方法，通过统计框架检测分布偏移，并利用投注机制动态更新分类器。方法驱动测试熵分布匹配源域，从而对分布偏移建立不变性。实验表明该方法在多种流数据场景下有效。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-qamfjyhpeg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1208, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qamfjyhpeg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1304, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qamfjyhpeg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qamfjyhpeg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1234, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qamfjyhpeg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 813, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qamfjyhpeg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qamfjyhpeg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 766, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qamfjyhpeg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1318, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qamfjyhpeg/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1453, \"height\": 762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qamfjyhpeg/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1451, \"height\": 375, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-qamfjyhpeg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 445, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-qamfjyhpeg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-qamfjyhpeg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1083, \"height\": 589, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-qamfjyhpeg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 733, \"height\": 229, \"label\": \"Table\"}]"
motivation: 现有自训练方法在测试时适应中容易过度拟合，且缺乏对分布偏移的显式检测。
method: 提出熵匹配框架，结合投注算法进行在线分类器更新。
result: 在多个基准上优于现有在线TTA方法，具有鲁棒性。
conclusion: 该方法为在线测试时适应提供了统计保证和高效机制。
---

## Abstract
We present a novel approach for test-time adaptation via online self-training, consisting of two components. First, we introduce a statistical framework that detects distribution shifts in the classifier's entropy values obtained on a stream of unlabeled samples. Second, we devise an online adaptation mechanism that utilizes the evidence of distribution shifts captured by the detection tool to dynamically update the classifier's parameters. The resulting adaptation process drives the distribution of test entropy values obtained from the self-trained classifier to match those of the source domain, building invariance to distribution shifts. This approach departs from the conventional self-training method, which focuses on minimizing the classifier's entropy. Our approach combines concepts in betting martingales and online learning to form a detection tool capable of quickly reacting to distribution shifts. We then reveal a tight relation between our adaptation scheme and optimal transport, which forms the basis of our novel self-supervised loss. Experimental results demonstrate that our approach improves test-time accuracy under distribution shifts while maintaining accuracy and calibration in their absence, outperforming leading entropy minimization methods across various scenarios.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义

论文针对 **测试时自适应（Test-Time Adaptation, TTA）** 中普遍采用的 **自训练（self-training）** 方法存在的问题。传统的自训练通过最小化测试样本预测的**熵**来更新模型，这种方法虽然能提升分布偏移下的性能，但容易导致**过置信预测**、**模型坍塌**（输出恒定结果）以及**有害更新**，且在无偏移时反而会降低校准性和准确率。本文提出一种**统计上有理论基础**的新方法——**Protected Online Entropy Matching (POEM)**，其核心思想是**使测试时熵的分布与源域熵的分布相匹配**，而非直接最小化熵。该方法通过在线投注鞅实时检测分布偏移，并仅在检测到偏移时进行受控的模型更新，从而同时提升鲁棒性和稳定性。

### 2. 方法论

- **核心思想**：将测试时自适应视为一个**在线博弈**过程。通过监控分类器在测试数据上熵值的分布是否偏离源域，并基于偏离证据动态调整模型参数，使得目标域熵分布向源域对齐，从而建立对分布偏移的不变性。
- **关键技术细节**：
  1. **源熵分布估计**：使用无标签的源域 holdout 数据计算源熵（对原始模型输出的 softmax 求熵）的累积分布函数 \(F_s\)。
  2. **在线漂移检测**：对每个测试样本 \(X_t^j\)，计算分类器熵 \(Z_t^j\)，再通过概率积分变换得到 \(u_j = F_s(Z_t^j)\)。若 \(u_j\) 序列服从均匀分布 \(U[0,1]\)，则表明无偏移；否则存在偏移。使用**投注鞅**构建检验：
     \[
     S_j = S_{j-1} \cdot (1 + \epsilon_j (u_j - 0.5)), \quad S_0=1
     \]
     其中 \(\epsilon_j \in [-2,2]\) 由**尺度无关在线梯度下降（SF-OGD）** 在线学习，以最大化对数财富 \(\log S_j\)，确保鞅性质并快速检测漂移。
  3. **伪熵生成（最优传输映射）**：将投注函数视为似然比，得到替代分布 \(Q(u)\) 的 CDF：
     \[
     \tilde{u}_j = Q(u_j) = \frac{1}{2}\epsilon_j u_j^2 + (1-\frac{\epsilon_j}{2})u_j
     \]
     再通过逆源 CDF 得到匹配的伪熵 \(\tilde{Z}_j = F_s^{-1}(\tilde{u}_j)\)。理论上，若投注函数为真实似然比，此映射即为最优传输，最小化 Wasserstein 距离。
  4. **自训练损失函数**：使用**熵匹配损失**：
     \[
     \ell_{\text{match++}}(\!Z_t^j,\tilde{Z}_j) = \frac12 (Z_t^j - \tilde{Z}_j)^2 \cdot \mathbb{1}[Z_t^j < \lambda] \cdot \exp\{2(\lambda - Z_t^j)\}
     \]
     其中 \(\lambda\) 为阈值，用于过滤高熵（不可靠）样本，并给予低熵样本更高权重。
  5. **模型更新**：仅更新归一化层参数（如 LN/GN），使用 SGD 优化器最小化上述匹配损失。

### 3. 实验设计

- **数据集与场景**：
  - **ImageNet-C**：15 种 corruption，5 种 severity，包括**持续偏移**（连续改变 corruption 类型或 severity）和**单次偏移**场景。
  - **CIFAR10-C / CIFAR100-C**：类似结构，同样包含持续偏移和长序列适应性实验。
  - **OfficeHome**：从 “Real World” 域向 “Art”、“Clipart”、“Product” 域自适应。
  - **In-distribution**：使用原始 ImageNet 验证集评估无害性。
- **基准方法**：TENT、EATA、SAR、COTTA，以及无自适应基线（No adapt）。
- **模型**：Vision Transformer (ViT, LN) 和 ResNet50 (GN) 用于 ImageNet；ResNet32 (BN) 用于 CIFAR；ResNet50 (GN) 用于 OfficeHome。
- **对比指标**：Top-1 准确率、Expected Calibration Error (ECE)、模型参数变化 \(\|\omega\|_F^2\)、运行时 slowdown、学习率敏感性。

### 4. 资源与算力

文中 Appendix F.2 明确说明：
- **GPU**：16 块 NVIDIA A40（49GB）。
- **CPU**：192 核 Intel(R) Xeon(R) Gold 6336Y。
- **内存**：1TB RAM。
- **单次实验配置**：1 块 GPU + 8 个 CPU。
- **总体训练时长**：论文未给出每个实验或总实验时间的具体数字，仅提及计算资源。

### 5. 实验数量与充分性

- **大量实验**：包括 ImageNet-C 持续偏移（不同 corruption 长度 100～2000 样本）、单次偏移（15 种 corruption，severity 5）、in-distribution 评估；CIFAR10/100-C 持续偏移（短序列 ~15k 样本、长序列 112.5k 样本）；OfficeHome 单域自适应；消融实验（\(\ell_{\text{match}}\) vs \(\ell_{\text{match++}}\)）、学习率敏感性分析、运行时间对比。
- **统计可靠性**：每组实验重复 10 次，报告均值和标准误。
- **公正性**：与基线方法使用相同代码库、优化器、batch size（1 或 4），并为基线调优学习率。对比时更新相同的归一化层参数。
- **结论充分**：实验覆盖多种架构、数据集、偏移场景，结果显示 POEM 在大部分情况下优于或持平现有方法，且在无偏移时几乎不改变模型，验证了其“无害”性。

### 6. 主要结论与发现

- **性能优势**：在 ImageNet-C 单次偏移（severity 5）中，POEM 在 ViT 上平均准确率 67.36%，超过最佳基线 EATA（64.14%）3.22%；在 ResNet 上也达到 38.90%（EATA 38.63%）。持续偏移场景中，POEM 适应速度更快，尤其在短 corruption 段（如 100 样本）表现突出。
- **无害性**：在 in-distribution 数据上，POEM 几乎不改变模型参数（\(\|\omega\|_F^2\) 极小）、校准误差保持不变，而基线方法会增大 ECE 并大幅修改参数。
- **鲁棒性**：学习率敏感性分析表明 POEM 比 TENT、SAR 更稳定，与 EATA 相当。
- **计算效率**：运行时 slowdown 与 TENT、EATA 相近，快于 SAR（SAR 需额外重启机制）。

### 7. 优点

- **理论创新**：将统计检验（投注鞅）与测试时自适应有机结合，提供了分布偏移在线检测的统计保证（鞅有效性、最优传输联系）。
- **自适应受控**：检测到偏移才触发匹配损失，避免了盲目最小化熵导致的过置信和坍塌。
- **灵活性**：可直接嵌入现有自训练框架（仅需更换损失函数），且可扩展至其他自监督损失。
- **实验严谨**：多数据集、多架构、多次重复，对比公平，结论可信。

### 8. 不足与局限

- **需要源域 holdout 数据**：需预先用无标签源域样本估计熵 CDF，增加了预处理开销；且 CDF 的准确性依赖于 holdout 样本代表性。
- **超参数依赖**：涉及学习率 \(\eta\)、熵阈值 \(\lambda\)、投注剪裁值 \(D\)、SF-OGD 学习率 \(\gamma\) 等，虽实验表明鲁棒，但理论指导不足。
- **未处理标签偏移**：当前方法主要针对协变量偏移（covariate shift），若测试时出现标签偏移（如类别不平衡），熵分布变化可能被误判为偏移并触发不必要更新。作者在 Section G 中讨论了未来方向。
- **极端偏移场景**：实验未覆盖极强偏移或对抗性攻击，可能失效。
- **计算资源消耗较高**：虽运行时与轻量方法相当，但 SF-OGD 在线学习额外开销，且需存储梯度历史。
- **理论分析有待深入**：虽然建立了最优传输联系，但未严格证明熵匹配在所有情况下优于熵最小化。

（完）
