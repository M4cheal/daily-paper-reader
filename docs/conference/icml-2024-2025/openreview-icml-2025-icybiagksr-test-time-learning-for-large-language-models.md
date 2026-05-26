---
title: Test-Time Learning for Large Language Models
title_zh: 面向大型语言模型的测试时学习
authors: "Jinwu Hu, Zitian Zhang, Guohao Chen, Xutao Wen, Chao Shuai, Wei Luo, Bin Xiao, Yuanqing Li, Mingkui Tan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=iCYbIaGKSR"
tags: ["query:tta"]
score: 8.0
evidence: 使用无标签数据对LLM进行测试时学习
tldr: 大语言模型在专业领域和语言变体上泛化不足。本文提出测试时学习范式（TLM），在推理时仅用未标记测试数据通过最小化输入困惑度来动态适应目标域。理论和实验表明该方法有效缓解分布偏移，无需额外训练数据，显著提升LLM在下游任务上的性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-icybiagksr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-icybiagksr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 725, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-icybiagksr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 789, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-icybiagksr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 856, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-icybiagksr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1462, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-icybiagksr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1460, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-icybiagksr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1460, \"height\": 567, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1770, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 861, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 847, \"height\": 864, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 857, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1052, \"height\": 545, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1777, \"height\": 803, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 1491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1772, \"height\": 1167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1664, \"height\": 740, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1664, \"height\": 740, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1662, \"height\": 739, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1659, \"height\": 737, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1662, \"height\": 739, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1659, \"height\": 737, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-icybiagksr/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1658, \"height\": 737, \"label\": \"Table\"}]"
motivation: 大语言模型在专业领域和语言变体上存在分布偏移，需要动态适应。
method: 提出测试时学习范式，通过最小化未标记测试数据的输入困惑度进行自适应。
result: 理论分析和实验表明该方法有效缓解分布偏移，提升LLM性能。
conclusion: 测试时学习为LLM在推理时适应新领域提供了简单有效的无监督方案。
---

## Abstract
While Large Language Models (LLMs) have exhibited remarkable emergent capabilities through extensive pre-training,  they still face critical limitations in generalizing to specialized domains and handling diverse linguistic variations, known as distribution shifts. In this paper, we propose a Test-Time Learning (TTL) paradigm for LLMs, namely TLM, which dynamically adapts LLMs to target domains using only unlabeled test data during testing. Specifically, we first provide empirical evidence and theoretical insights to reveal that more accurate predictions from LLMs can be achieved by minimizing the input perplexity of the unlabeled test data. Based on this insight, we formulate the Test-Time Learning process of LLMs as input perplexity minimization, enabling self-supervised enhancement of LLM performance. Furthermore, we observe that high-perplexity samples tend to be more informative for model optimization. Accordingly, we introduce a Sample Efficient Learning Strategy that actively selects and emphasizes these high-perplexity samples for test-time updates. Lastly, to mitigate catastrophic forgetting and ensure adaptation stability, we adopt Low-Rank Adaptation (LoRA) instead of full-parameter optimization, which allows lightweight model updates while preserving more original knowledge from the model. We introduce the AdaptEval benchmark for TTL and demonstrate through experiments that TLM improves performance by at least 20% compared to original LLMs on domain knowledge adaptation.

---

## 论文详细总结（自动生成）

# 详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：大型语言模型（LLMs）在真实部署中面临严重的数据分布偏移（distribution shifts），具体体现在：  
  - **垂直领域术语**：在医学、农业等专业领域中，模型对罕见术语和结构化知识理解不足。  
  - **语言多样性变化**：方言、俚语等用户意图差异导致模型响应质量下降。  
- **现有方法局限**：  
  - **微调**：依赖大量标注数据，不适用于动态环境。  
  - **检索增强生成（RAG）**：依赖检索质量，额外延迟。  
  - **测试时适应（TTA）**：常用熵最小化（entropy minimization）退化LLM的自回归特性，导致负面效果（见Figure 1a）。  
  - **测试时训练（TTT）**：需要访问训练数据/知识库，不实用。  
- **本文目标**：提出一种**测试时学习（Test-Time Learning, TTL）**范式，使LLM在推理时**仅用未标记测试数据**动态适应目标域，无需额外训练数据或标注。

## 2. 提出的方法论
### 核心思想
- **输入困惑度最小化**（Input Perplexity Minimization）：  
  通过理论分析和实验验证（Observation 1），发现**输入困惑度 P(x;Θ) 与输出困惑度 P(y|x;Θ) 呈正相关**（Figure 1b），故将TTL目标转化为最小化输入困惑度：  
  \[
  \min_{\Theta} P(x;\Theta) \quad \text{（仅使用未标记输入x）}
  \]
  梯度分析表明，当问题-答案语义对齐时，输入困惑度最小化能提升答案预测概率（见公式(4)及验证：98.75%样本满足非负内积条件）。
- **样本高效学习策略**（Sample-Efficient Learning Strategy）：  
  基于Observation 2（高困惑度样本对模型更新贡献更大，低困惑度样本可能有害，Figure 1c），设计**困惑度加权选择机制**：  
  \[
  S(x) = \lambda \cdot e^{[\log P(x;\Theta) - \log P_0]} \cdot \mathbb{I}_{\{P(x;\Theta) > P_0\}}(x)
  \]
  仅对困惑度高于阈值 \(P_0\) 的样本进行反向传播，并赋予较高权重。
- **轻量参数更新**：  
  基于Observation 3（LoRA比全参数更新更有效防止灾难性遗忘，Figure 2），采用**低秩适应（LoRA）**，仅更新少量参数 \(\Delta\Theta = BA\)，目标函数变为：  
  \[
  \min_{\Delta\Theta} S(x) P(x; \Theta + \Delta\Theta)
  \]
- **算法流程**：  
  1. 初始化LoRA参数，添加到预训练LLM。  
  2. 对每个batch的测试样本：前向计算预测 → 计算选择分数S(x) → 用加权困惑度损失更新LoRA参数。  
  3. 输出适应后的模型。

## 3. 实验设计
### 数据集 / Benchmark
- **AdaptEval基准**：由作者构建，包含三类共10个数据集：
  - **DomainBench**：垂直领域知识（地理、农业、医学、金融），各5k样本。
  - **InstructionBench**：通用指令遵循（Alpaca-GPT4、Dolly、InstructionWild），各5k样本。
  - **ReasoningBench**：推理能力（GSM8K、MetaMath、Logiqa），各5k样本。
- **评估指标**：  
  - DomainBench & InstructionBench：主要使用 **Rouge-Lsum**（另报告BERTScore/BLEU等）。  
  - ReasoningBench：**Exact Match (EM)**。
- **对比方法**：  
  - 原始LLM（无适应）。  
  - **Tent**（测试时熵最小化）、**EATA**（高效抗遗忘TTA）、**COME**（保守熵最小化）——均调整为LLM场景的离线/在线版本。
- **LLM模型**：  
  - Llama3.2-3B-Instruct  
  - Llama3-8B-Instruct  
  - Llama2-13B-Chat  
  - Qwen2.5-7B-Instruct  
- **实现细节**：  
  - LoRA rank=8，仅更新 \(W_q, W_v\)。  
  - 学习率：DomainBench 5e-5 / InstructionBench 5e-5 / ReasoningBench 1e-6，batch size=1。  
  - 阈值 \(P_0 = e^3\)，\(\lambda = 0.10\)。  
  - 解码：贪心，温度0。

## 4. 资源与算力
- **硬件**：NVIDIA A800 GPU（80GB显存），CUDA 12.1。  
- **框架**：PyTorch 2.5.1 + LLaMA-Factory。  
- **说明**：论文**未明确给出训练时长、GPU数量或总计算量**，仅提到在单个A800上运行所有实验。由于LoRA轻量更新，推理时计算开销可控。

## 5. 实验数量与充分性
- **实验组数**：  
  - 主实验：在10个数据集 × 4种LLM（共40个组合）× 4种方法 + 原始LLM，呈现主要结果（Table 2, 3）。  
  - 消融实验：  
    - 输入困惑度最小化 vs 原始LLM（Table 4）。  
    - 样本选择策略有效性（Table 4）。  
    - 阈值 \(P_0\) 调参（Figure 3，5个值）。  
  - 额外实验：  
    - 在线设置（Table 5）。  
    - 量化LLM（4-bit NF4，Table 5）。  
    - 更多指标（BERTScore/BLEU等）补充（Table 10-16）。  
- **充分性与公平性**：  
  - 对比方法（Tent/EATA/COME）被调整为LLM场景，但原始论文设计用于图像分类，实验结果中这些基线在LLM上普遍退化（甚至低于原始模型），说明其不直接适用，**对比公平但方法优越性突出**。  
  - 实验覆盖领域多样、模型尺寸跨度大（3B~13B），**结论具有一定泛化性**。  
  - 消融实验验证了每个组件的必要性。

## 6. 主要结论与发现
- 输入困惑度最小化能有效提升LLM在目标域的性能（DomainBench上至少提升20%）。  
- 高困惑度样本比低困惑度样本对模型更新贡献更大，优先选择它们可减少计算量并提升效果。  
- LoRA相比全参数更新更能缓解灾难性遗忘，适合测试时短期适应。  
- 在指令遵循和推理任务上，TLM同样显著优于原始LLM和现有TTA方法。  
- 在线场景下，随着模型适应，高困惑度样本减少，反向传播次数可降低69.7%。  
- 量化LLM（4-bit）上仍能取得≥25%提升，验证了实用性。

## 7. 优点
1. **无监督、轻量**：仅需未标记测试数据，无需额外标注或外部知识，LoRA更新参数极少量。  
2. **机制简洁有效**：基于困惑度最小化，直接利用LLM的自回归特性，避免熵最小化的不匹配问题。  
3. **样本高效**：困惑度加权选择减少了无效反向传播，加速适应。  
4. **理论支撑**：通过梯度内积分析（98.75%非负）证明输入困惑度最小化与输出性能正相关。  
5. **全面基准**：构建AdaptEval，覆盖领域、指令、推理三大类，促进后续TTL研究。

## 8. 不足与局限
1. **实验覆盖范围**：  
   - 测试数据仅限英文，未考虑多语言场景。  
   - 领域较集中（地理、农业、医学、金融），其他专业领域（如法律、工程）未验证。  
   - 模型尺寸限于13B以下，更大模型（>30B）的适应性未知。  
2. **计算开销**：  
   - 尽管使用LoRA，仍需在推理时进行多次反向传播（尤其在离线设置），在实时性要求高的场景中仍有挑战。  
   - 在线设置中虽减少了更新次数，但首次处理仍需要计算困惑度并可能更新。  
3. **局限性**：  
   - 假设高困惑度样本总是有益，但可能包含噪声或错误数据，文中未讨论异常处理。  
   - 未考虑跨域连续适应（如从医学切换到金融），可能导致灾难性遗忘。  
   - 方法依赖LLM本身对困惑度的敏感度，对于高度预训练不充分的模型可能效果有限。  
4. **对比基线**：Tent/EATA/COME原为视觉任务设计，虽然调整但仍可能有偏见，可进一步加入面向NLP的TTL基线（如TTT+NN）进行比较。

（完）
