---
title: "Test-Time Preference Optimization: On-the-Fly Alignment via Iterative Textual Feedback"
title_zh: 测试时偏好优化：通过迭代文本反馈实现即时对齐
authors: "Yafu Li, Xuyang Hu, Xiaoye Qu, Linjie Li, Yu Cheng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ArifAHrEVD"
tags: ["query:tta"]
score: 6.0
evidence: 通过测试时偏好优化实现LLM自适应
tldr: 大型语言模型在推理时难以快速适应人类偏好。本文提出测试时偏好优化（TPO）框架，将奖励信号转化为文本批评，通过迭代文本反馈逐步优化输出，无需更新模型参数。在指令遵循、安全等基准上，TPO持续提升对齐效果，展示了测试时自适应在偏好对齐中的潜力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-arifahrevd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 780, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arifahrevd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1748, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arifahrevd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1726, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arifahrevd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1720, \"height\": 805, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arifahrevd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arifahrevd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arifahrevd/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 630, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arifahrevd/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1646, \"height\": 1091, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arifahrevd/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1643, \"height\": 1090, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arifahrevd/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1596, \"height\": 1044, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arifahrevd/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1631, \"height\": 1031, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-arifahrevd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1608, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arifahrevd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 845, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arifahrevd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1320, \"height\": 138, \"label\": \"Table\"}]"
motivation: 现有大语言模型缺乏推理时快速适应人类偏好的灵活性，需要重训练。
method: 提出TPO框架，将奖励信号转化为文本批评并作为文本奖励，迭代优化输出。
result: 在指令遵循、偏好对齐、安全等基准上，TPO持续提升对齐效果。
conclusion: TPO为测试时自适应提供了新范式，无需参数更新即可实现偏好对齐。
---

## Abstract
Large language models (LLMs) have presented impressive performance but often lack the flexibility to adapt to human preferences quickly without retraining. Inspired by the recent efforts on test-time scaling, we make the first attempt to propose Test-time Preference Optimization (TPO), a framework that aligns LLM outputs with human preferences during inference, eliminating the need to update model parameters. Instead of relying on purely numerical rewards, TPO translates reward signals into \emph{textual} critiques and uses them as textual rewards to iteratively refine its response. Evaluations on benchmarks covering instruction following, preference alignment, safety, and mathematics reveal that TPO progressively improves alignment with human preferences. Notably, after only a few TPO steps, the initially unaligned Llama-3.1-70B-SFT model can surpass the aligned counterpart, Llama-3.1-70B-Instruct. Furthermore, TPO scales efficiently with both the search width and depth of the inference process. Through case studies, we illustrate how TPO exploits the innate capacity of LLM to interpret and act upon reward signals. Our findings establish TPO as a practical, lightweight alternative for test-time preference optimization, achieving alignment on the fly.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究问题**：大型语言模型（LLMs）在训练后难以在不进行重训练的情况下快速适应新的人类偏好或动态变化的需求。传统的偏好优化方法（如RLHF、DPO）依赖于梯度更新模型参数，缺乏推理时的灵活性。
- **背景与动机**：近期测试时计算扩展（test-time scaling）显示出通过增加推理计算量提升性能的潜力。本文首次提出测试时偏好优化（TPO），旨在利用LLM固有的文本理解和生成能力，在推理阶段通过迭代文本反馈实现即时对齐，无需参数更新。
- **核心含义**：将偏好优化从训练时转移到测试时，提供一种轻量级、可解释且高效的替代方案。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：将传统梯度下降中的数值损失、梯度、参数更新类比为文本形式。通过奖励模型（RM）的数值分数，挑选最优（chosen）和最差（rejected）响应，然后让策略模型生成**文本损失**（critique）和**文本梯度**（改进建议），最后基于文本梯度更新响应（“变量”）。迭代进行，称为“测试时训练”。
- **关键技术步骤**（每步对应传统优化类比）：
    1. **变量定义**：模型响应 v = M(x)。
    2. **损失计算**：使用提示 Ploss 让模型比较 chosen 与 rejected 响应，生成文本损失 L(x,v) = M(Ploss(x,v,ˆv))。
    3. **梯度计算**：通过提示 Pgrad 将文本损失转为改进指令 ∂L/∂v = M(Pgrad(L(x,v)))。
    4. **变量优化**：使用提示 Pupdate 应用文本梯度生成新响应 vnew = M(Pupdate(∂L/∂v))。
    5. **迭代**：将新响应加入缓存，重新选择最优/最差响应，重复步骤2-4直到最大迭代次数D。
- **初始化**：采样N个候选响应，用RM评分，选出chosen和rejected。
- **最终输出**：从所有缓存响应中选最高分响应。
- **公式类比**：传统参数更新 θ ← θ − α∇θL(θ)，TPO更新上下文 ϕ (即改进指令) 来改变输出分布 p(yw|ϕ;θ,x)。

## 3. 实验设计
- **数据集/场景**：覆盖指令遵循（AlpacaEval 2, Arena-Hard）、通用偏好对齐（HH-RLHF）、安全（BeaverTails-Evaluation, XSTest）、数学推理（MATH-500）。
- **基准方法**：
    - **未对齐模型**：Llama-3.1-70B-SFT（基于Tulu-3 SFT）
    - **对齐模型**：Llama-3.1-70B-Instruct, Mistral-Small-Instruct-2409 (22B), Llama-3.1-70B-DPO（自行训练的DPO基线）
    - 对比方法：Best-of-N (BoN)采样，BoN-30/60
    - 消融变体：Multi-Ploss TPO（仅宽度无迭代）、Mid-TPO（使用中等级别对比对）
- **评估指标**：AlpacaEval 2 报告LC和WR；Arena-Hard报告WR；HH-RLHF和BeaverTails报告平均奖励（FsfairX-LLaMA3-RM）；XSTest报告WildGuard分类准确率；MATH-500报告pass@1准确率。

## 4. 资源与算力
- **训练时DPO成本**：训练Llama-3.1-70B-DPO在UltraFeedback（64k实例，最大长度2048）需约72,840 PFLOPs。
- **TPO测试时成本**：默认配置（D=2, N=5）下，每查询约9.3 PFLOPs，约为训练时DPO的0.01%。使用vLLM推理，温度0.7，top-p 0.95。未明确说明GPU型号与数量。

## 5. 实验数量与充分性
- **主要实验**：测试时训练曲线（5步迭代）和基准性能（D=2, N=5）在6个数据集上对多种模型进行。额外超设置D=5, N=20展示潜力。
- **消融实验**：对比Multi-Ploss（无迭代）和Mid-TPO（弱对比），证明迭代和强对比的必要性。
- **稳定性分析**：测量多次生成的标准差，证明TPO提升稳定性。
- **宽度/深度缩放分析**：改变N和D，对比BoN，展示迭代深度优于纯宽度。
- **Win-rate对比**：对100样本用GPT-4评估TPO vs BoN-30/60。
- **案例研究**：多个示例展示文本损失和梯度的可解释性。
- **充分性**：覆盖多种任务和模型规模（70B、22B、8B），消融全面，对比方法包括训练时对齐和多种BoN基线，实验较充分、客观。但8B模型失败表明存在规模依赖。

## 6. 主要结论与发现
- TPO能在仅2-5次迭代内将未对齐模型提升至超越强对齐模型（如Llama-3.1-70B-SFT超过Instruct版本）。
- 对齐模型也可进一步受益，如22B Mistral-Instruct经TPO后AlpacaEval 2 LC达53.4%，接近GPT-4-Turbo。
- 迭代深度（sequential revision）比纯宽度采样（BoN）更有效，TPO-D2-N5优于BoN-60。
- 测试时训练曲线显示奖励分数随迭代单调增加，且第一轮提升最大。
- 模型必须具备足够的指令遵循能力（8B模型失败），这是TPO有效的前提。

## 7. 优点
- **无需重训练**：完全测试时进行，参数固定，经济高效（0.01%训练成本）。
- **可解释性**：文本损失和文本梯度提供了清晰的分析和建议，便于调试和信任。
- **即时适应**：能快速适应新偏好或环境变化，无需等待训练周期。
- **灵活性**：可通过调整宽度（N）和深度（D）灵活扩展测试时计算，权衡性能与效率。
- **通用性**：在指令遵循、安全性、数学等多个任务上一致有效。
- **可作为BoN的升级**：无需大量采样，通过迭代精炼实现更好性能。

## 8. 不足与局限
- **依赖模型能力**：小模型（如Llama-3.1-8B-Instruct）因指令遵循能力不足而失败，限制了在弱模型上的应用。
- **测试时成本**：虽然远低于训练，但在高延迟场景下多次调用LLM仍可能不实用（每查询约9.3 PFLOPs）。
- **奖励模型依赖**：TPO有效性取决于奖励模型质量；若RM有偏，可能放大偏见。
- **缺乏理论保证**：目前为经验验证，缺乏收敛性或最优性理论分析。
- **安全性双刃剑**：可能被用于对齐恶意目标，需加伦理护栏。
- **实验范围**：主要关注70B及22B模型，未在更大或更小规模广泛测试；数学任务上提升有限（MATH-500从61.8%到71.8%，但大幅增益来自超设置）。

（完）
