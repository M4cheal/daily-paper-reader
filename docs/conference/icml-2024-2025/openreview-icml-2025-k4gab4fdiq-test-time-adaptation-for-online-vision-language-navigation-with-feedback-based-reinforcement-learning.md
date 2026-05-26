---
title: Test-Time Adaptation for Online Vision-Language Navigation with Feedback-based Reinforcement Learning
title_zh: 面向在线视觉语言导航的测试时自适应：基于反馈的强化学习方法
authors: "Sungjune Kim, Gyeongrok Oh, Heeju Ko, Daehyun Ji, Dongwook Lee, Byung-Jun Lee, Sujin Jang, Sangpil Kim"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=K4GaB4fdIq"
tags: ["query:tta"]
score: 9.0
evidence: 在线测试时自适应用于视觉语言导航，结合强化学习
tldr: 本文针对视觉语言导航（VLN）中的在线测试时自适应问题，提出FeedTTA框架。该框架利用二元情景反馈信号，通过强化学习更新导航策略，同时保持模型的可塑性与稳定性平衡。实验表明，FeedTTA在未见过的环境中能有效提升导航成功率，且适应速度快。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1774, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 880, \"height\": 232, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1780, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1741, \"height\": 411, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1733, \"height\": 552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 755, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 873, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1724, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 865, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1539, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 724, \"height\": 109, \"label\": \"Table\"}]"
motivation: 在线VLN中测试时自适应未得到充分研究，现有方法难以处理环境变化与稳定性权衡。
method: 提出FeedTTA框架，利用二元情景反馈和强化学习，在测试时动态调整导航策略。
result: 在多种VLN基准上，FeedTTA显著提升导航成功率，且适应效率高。
conclusion: 基于反馈的强化学习是实现在线TTA的有效范式。
---

## Abstract
Navigating in an unfamiliar environment during deployment poses a critical challenge for a vision-language navigation (VLN) agent. Yet, test-time adaptation (TTA) remains relatively underexplored in robotic navigation, leading us to the fundamental question: what are the key properties of TTA for online VLN? In our view, effective adaptation requires three qualities: 1) flexibility in handling different navigation outcomes, 2) interactivity with external environment, and 3) maintaining a harmony between plasticity and stability. To address this, we introduce FeedTTA, a novel TTA framework for online VLN utilizing feedback-based reinforcement learning. Specifically, FeedTTA learns by maximizing binary episodic feedback, a practical setup in which the agent receives a binary scalar after each episode that indicates the success or failure of the navigation. Additionally, we propose a gradient regularization technique that leverages the binary structure of FeedTTA to achieve a balance between plasticity and stability during adaptation. Our extensive experiments on challenging VLN benchmarks demonstrate the superior adaptability of FeedTTA, even outperforming the state-of-the-art offline training methods in REVERIE benchmark with a single stream of learning.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在视觉语言导航（VLN）任务的在线部署阶段，导航策略可能遇到训练时未见过的新环境，导致可靠性下降。现有的测试时自适应（TTA）方法，尤其是基于熵最小化的方法（如FSTTA），在处理导航失败时存在过度拟合、探索不足等问题，无法满足在线导航对灵活性、交互性和可塑性-稳定性平衡的需求。
- **研究动机**：探索TTA用于在线VLN的关键属性，提出一种能同时具备灵活性（适应不同导航结果）、交互性（利用外部反馈信号）以及可塑性与稳定性平衡的适应框架。
- **整体含义**：本文提出FeedTTA，一种基于反馈的强化学习（RL）的TTA框架，通过在测试时接收二元情景反馈（成功/失败）来在线更新策略，有效提升了导航性能，甚至超越离线训练方法。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：利用二元情景反馈作为强化学习的奖励信号，通过REINFORCE算法最大化累积反馈，实现导航策略的在线自适应。同时提出随机梯度反转（SGR）正则化技术，缓解二元反馈带来的非平稳性，保持可塑性与稳定性平衡。
- **关键技术细节**：
  - **二元情景反馈机制**：每次导航回合结束后，由人类或AI（如GPT-4）给出+1（成功）或-1（失败）的标量反馈。
  - **基于反馈的策略梯度**：利用REINFORCE算法，梯度近似为：
    \[
    \nabla_\theta J(\theta) \approx \mathbb{E}_{a,s\sim\tau}\left[\sum_{t=0}^{T-1} \nabla_\theta \log \pi_\theta(a_t|s_t) \gamma^{T-t-1}F\right]
    \]
    其中F为二元反馈，折扣因子γ用于计算回报。
  - **随机梯度反转（SGR）**：对梯度向量中的随机子集（由伯努利采样p决定）施加反转系数α<0，其余部分缩放以保持期望不变。修改后的梯度为：
    \[
    \nabla_\theta J(\theta)' = \begin{cases} \alpha g_{\theta_m} & \text{if } g_{\theta_m} \in G \\ \frac{1}{\alpha p + (1-p)} g_{\theta_m} & \text{otherwise} \end{cases}
    \]
    其中G为随机采样的子集。这模拟了反事实场景，降低梯度幅值，从而缓解非平稳性和灾难性遗忘。
- **算法流程**（文字说明）：
  1. 初始化预训练策略πθ。
  2. 对每个测试样本Xn（指令+初始视觉状态），生成轨迹τ。
  3. 从Oracle接收二元反馈F（成功+1，失败-1）。
  4. 计算策略梯度（式3）。
  5. 应用SGR：随机选择一部分梯度维度进行反转（式4、5），得到修正梯度。
  6. 通过梯度上升更新参数（式6）。
  7. 重复直到所有样本处理完成。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：REVERIE（目标导向，高层指令）、R2R（细粒度指令）、R2R-CE（连续环境变体）。
- **基准（Benchmark）**：标准评估协议，包含TL、NE、SR、OSR、SPL、RGS、RGSPL等指标。本文还提出了“自适应成功率（ASR）”指标，衡量样本级前-后结果转换。
- **对比方法**：
  - 离线训练方法：VLN⟳BERT、HOP+、BEVBert、KERM、NaviLLM、VLN-VER等。
  - 测试时自适应基线：Tent（熵最小化）、FSTTA（快速慢速TTA）。
- **实验设置**：在REVERIE上以HAMT和DUET为基础策略；在R2R和R2R-CE上以DUET、BEVBert、ETPNav为基础策略。Tensor维度更新仅从跨模态编码器开始，冻结视觉和语言编码器。

## 4. 资源与算力

- 论文中明确：所有实验在单张NVIDIA Tesla A100 GPU上进行。未提及训练时长或具体GPU数量细节。但提到FeedTTA不依赖高端服务器级GPU，可在实用硬件（如GTX 1080）上高效部署。

## 5. 实验数量与充分性

- **实验数量**：包含三个主要数据集（REVERIE, R2R, R2R-CE），每个数据集包含验证可见、验证不可见、测试不可见等多个数据划分。对比了多种离线方法和TTA方法。
- **消融实验**：分析了反馈准确率、反馈数量（前K样本和更新间隔）、SGR中不同α值的效果、不同正则化变体（GD、GS、SGR）的比较、权重幅度分析、灾难性遗忘分析、不同反馈策略（稀疏vs密集）的比较、LLM作为Oracle的效果、不同序列顺序的影响、轨迹可视化等。共约10组以上正式实验。
- **充分性与客观性**：实验设计较为充分，覆盖了核心变量（反馈质量、数量、正则化方法、不同策略等），并支持统计显著性。对比方法均基于官方或重实现版本，并在同一设定下比较。但缺乏在更多真实物理环境中的验证，可能局限于模拟器。

## 6. 论文的主要结论与发现

- FeedTTA在三个数据集上显著优于现有TTA方法，在REVERIE验证不可见集上DUET的SR从46.98提升至66.49（+41.5%）。
- 仅通过单一在线学习流，FeedTTA即可超越多个最新的离线训练方法。
- SGR通过梯度反转有效缓解非平稳性，改善可塑性与稳定性平衡，特别是在失败样本转换成功方面（CSR显著提升）。
- 二元情景反馈非常高效：仅使用20%的反馈样本即超越基线性能；反馈准确率在50%以上即可获益。
- LLM可以作为可行的人反馈替代，但可靠性仍需提升（准确率72%）。
- 提出的ASR能更全面评估适应过程中的可塑性与稳定性。

## 7. 优点

- **方法创新**：将二元情景反馈与REINFORCE结合用于在线TTA，设计简洁且实用。
- **SGR正则化**：利用二元反馈的极端梯度特性，通过反转部分梯度实现反事实推理，平滑梯度分布，同时保持期望无偏。
- **新评估指标ASR**：能清晰分离样本级成功保留与失败转换能力，更全面反映适应效果。
- **实验全面**：覆盖主流数据集、多种基线、多角度消融，包括反馈质量、数量、正则化效果、序列顺序等，结果稳健。
- **实际可行性**：人类反馈只需终点评判，成本低；且LLM可替代，进一步降低人力需求。

## 8. 不足与局限

- **LLM Oracle可靠性**：目前LLM判断导航成功准确率仅72%，尚不能完全替代人类。论文指出这是未来方向，但未提出改进方案。
- **跨任务泛化有限**：在R2R→REVERIE跨任务场景下，虽然SR略有提升，但RGSPL几乎不变（3.47→3.49），说明适应新任务的能力有限。
- **连续环境仅测试R2R-CE**：未在更真实的物理机器人环境中验证，可能暴露外部噪声、延迟等实际问题。
- **超参数敏感**：需要针对不同数据集手动选择p和α（如REVERIE vs R2R不同），未给出自适应策略。
- **对比方法覆盖**：与Tent、FSTTA的比较基于重实现，而FSTTA原代码存在问题，虽经修复但仍可能引入差异。
- **训练/推理开销**：TTA方法引入额外梯度计算，推理时间增加（例如DUET+FeedTTA约672ms vs 基础176ms），在实时场景下可能受限。

（完）
