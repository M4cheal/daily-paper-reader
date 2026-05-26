---
title: "R2-T2: Re-Routing in Test-Time for Multimodal Mixture-of-Experts"
title_zh: R2-T2：多模态混合专家模型的测试时重新路由
authors: "Zhongyang Li, Ziyue Li, Tianyi Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=oqPcOMafOF"
tags: ["query:tta"]
score: 9.0
evidence: 多模态混合专家模型中的测试时路由调整
tldr: 本文针对大型多模态模型（LMM）中视觉表征与语言推理能力不匹配的问题，提出测试时重新路由策略（R2-T2）。该方法在测试阶段动态调整混合专家（MoE）路由器的权重，从而为每个样本选择最优的专家组合。实验表明，该方法能显著提升LMM在复杂下游任务上的性能，且计算开销低。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1551, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1764, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1771, \"height\": 906, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1768, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1765, \"height\": 737, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1775, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1583, \"height\": 802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1766, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1770, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1763, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oqpcomafof/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1760, \"height\": 385, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 904, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1615, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1782, \"height\": 1086, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 757, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 565, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 763, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 547, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 712, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 707, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 720, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 883, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 800, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 715, \"height\": 161, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 794, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1588, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1603, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1587, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1585, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oqpcomafof/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1413, \"height\": 267, \"label\": \"Table\"}]"
motivation: 端到端训练的路由器在测试时不能总是给出最优专家权重组合，限制了多模态任务性能。
method: 提出测试时重新路由机制，通过轻量级优化调整MoE路由权重，以适应具体测试样本。
result: 在多个多模态基准上显著提升性能，且仅需少量测试时计算。
conclusion: 测试时路由调整是一种有效的多模态模型自适应方法。
---

## Abstract
In large multimodal models (LMMs), the perception of non-language modalities (e.g., visual representations) is usually not on par with the large language models (LLMs)' powerful reasoning capabilities, deterring LMMs' performance on challenging downstream tasks. 
This weakness has been recently mitigated by replacing the vision encoder with a mixture-of-experts (MoE), which provides rich, multi-granularity, and diverse representations required by different downstream tasks. The performance of multimodal MoE largely depends on its router, which reweights and mixes the representations of different experts for each input. However, we find that the end-to-end trained router does not always produce the optimal routing weights for every test sample. To bridge the gap, we propose a novel and efficient method ''**R**e-**R**outing in **T**est-**T**ime (R2-T2)'' that locally optimizes the vector of routing weights in test-time by moving it toward those vectors of the correctly predicted samples in a neighborhood of the test sample. We propose three R2-T2 strategies with different optimization objectives and neighbor-search spaces. R2-T2 consistently and significantly improves state-of-the-art LMMs' performance on challenging multimodal benchmarks of diverse tasks, without training any parameters in the base model. Our code can be accessed here.

---

## 论文详细总结（自动生成）

# 论文总结：R2-T2: Re-Routing in Test-Time for Multimodal Mixture-of-Experts

## 1. 核心问题与研究动机
- **背景**：大型多模态模型（LMMs）普遍存在“模态不平衡”问题——视觉编码器的感知能力远落后于大语言模型（LLM）的推理能力，且对齐模块（如投影层）造成信息瓶颈，限制了复杂下游任务的表现。
- **现有缓解方法**：用混合专家（Mixture-of-Experts, MoE）替换单一视觉编码器，通过多个专家（如对象检测、OCR、空间关系等）提供多粒度、多样化的视觉特征，并由一个端到端训练的路由器为每个输入动态分配专家权重。
- **核心问题**：端到端训练的**路由器在测试时并不总能给出最优权重**，尤其是面对未见过的、多样化的下游任务时，次优路由严重制约了MoE的泛化能力和最终性能。作者通过实验证明，若使用“最优（Oracle）路由权重”，性能可提升≥10%。
- **目标**：在不重训练模型参数的前提下，**在测试时（test-time）局部优化路由权重**，使其更适应每个测试样本，从而释放MoE的潜力。

## 2. 方法论——测试时重新路由（R2-T2）
- **核心思想**：假设相似任务/样本所需的知识和技能是可迁移的。利用一个**参考集**（模型能正确预测的样本及其路由权重），对每个测试样本x，在其邻域内寻找“成功”的参考样本，并基于这些样本的信息来调整x的路由权重向量r。
- **关键技术**：无需训练模型参数，仅优化MoE的路由权重向量。
- **三种具体策略**（如图3所示）：
    1. **邻域梯度下降（Neighborhood Gradient Descent, NGD）**：
        - 不直接使用测试样本的标签（不可得），而是构造一个**代理损失**：测试样本邻域内参考样本损失的加权平均（权重由核函数K(·,·)度量样本间相似度）。
        - 公式：\( L(r) = \frac{\sum_{i \in N(x)} K(x_i, x) \cdot \ell[f(x_i, r), y_i]}{\sum_{i \in N(x)} K(x_i, x)} \)
        - 通过多次梯度下降更新r：\( r \leftarrow r - \lambda \nabla_r L(r) \)
        - 还定义了**Oracle上界**（使用真实标签的梯度下降）作为性能上限。
    2. **核回归（Kernel Regression）**：
        - 直接预测r为邻域参考样本路由权重的加权平均：\( \hat{r} = \frac{\sum_{i \in N(x)} K(x_i, x) r_i}{\sum_{i \in N(x)} K(x_i, x)} \)
        - 然后通过二分搜索在初始r和\(\hat{r}\)之间插值：\( r \leftarrow \alpha r + (1-\alpha)\hat{r} \)，寻找最小化代理损失的α。
    3. **模式寻找/均值漂移（Mode Finding/Meanshift）**：
        - 将r向路由权重空间中密度最高的区域移动（而非输入空间）。迭代更新：\( r \leftarrow \alpha r + (1-\alpha)\bar{r} \)，其中\(\bar{r}\)是邻域在路由权重空间中的加权平均（核函数作用于r而非x）。
- **邻域与嵌入空间**：使用kNN或ε-球；相似度在**任务嵌入空间**中计算（用预训练嵌入模型如NV-Embed-V2将样本的任务描述映射为向量）。
- **算法流程**（以NGD为例）：
    1. 构建参考集（模型正确预测的样本及其路由权重）。
    2. 对测试样本x，在任务嵌入空间中找到k个最近邻（kNN）。
    3. 计算邻域样本的加权损失作为代理目标。
    4. 对当前路由权重r进行多步梯度下降（如10步，余弦退火学习率）。
    5. 使用更新后的r进行模型推理。

## 3. 实验设计
- **模型**：两个最新多模态MoE模型——**MoAI-7B**（6个专家）和**MoVA-7B**（7个专家），均基于LLaMA等LLM。
- **参考数据集**（构建参考集）：
    - 通用视觉理解：VQA-V2, Visual7W, CLEVR, COCO-QA（各5k样本）
    - 知识推理：A-OKVQA, TQA, MathVista（各5k）
    - OCR：ST-VQA, DocVQA（各5k）
- **评估基准**（8个challenging benchmark）：
    - 通用视觉理解：MMBench, MME-P, CVBench 2D/3D, GQA
    - 知识推理：SQA-IMG, AI2D
    - OCR：TextVQA
- **对比方法**：
    - 基类（Base Model）：MoAI/MoVA原始路由
    - R2-T2三种变体：Mode Finding, Kernel Regression, NGD
    - Oracle上界（使用真实标签优化路由）
    - 其他SOTA VLM（7B~34B）：InstructBLIP, Qwen-VL, ShareGPT4V, Mini-Gemini, LLaVA-NeXT, Cambrian1, BLIP2等
- **评估指标**：Accuracy（MME-P为Accuracy+Accuracy+之和，最高2000），其余为准确率，最终计算跨基准平均分。
- **超参数**：固定设置（无需per-task调优）：k=5, 10步NGD, 余弦退火学习率(1e-2→1e-5), 高斯核, NV-Embed-V2嵌入。

## 4. 资源与算力
- 论文**未明确给出**训练时长、GPU型号与数量等详细信息。
- 但提供了**计算成本分析**（表4）：基于FLOPs（而非时间）比较。在MoAI-7B上，基模型单次推理约9.9T FLOPs；NGD（10步）需67.5T FLOPs（约6.8倍），Kernel Regression需61.9T，Mode Finding仅需10.7T。
- **内存使用**：附录表15给出不同嵌入模型下GPU内存（如+NV-Embed-V2需27GB，基模型18GB）。
- **延迟**：附录表16给出RTX A6000上平均每例运行时间：基模型7.8s，R2-T2 (NGD) 25.6s（约3.3倍）。
- 总体而言，R2-T2以可接受的计算开销（尤其相比微调模型参数）换取显著性能提升。

## 5. 实验数量与充分性
- **主实验**：在8个基准上分别测试MoVA和MoAI，对比多种基线。共16组实验（模型×基准）。
- **与SOTA对比**：表3列出10+个其他VLM（7B~34B）的分数。
- **消融实验**（针对MoAI）：系统考察了：
    - 邻域选择（kNN vs ε-ball，不同k/ε）
    - 核函数（线性、多项式、Matern、高斯）
    - 嵌入模型（5种不同规模）
    - NGD步数（5、7、10、20、50）
    - 学习率调度（固定、步衰减、余弦）
- **额外验证**：附录包含MMMU、ChartQA测试；对比集成方法、RAG/ICL；分析鲁棒性（参考集大小、任务覆盖不足、参考集不匹配）；自动化任务分类；数据污染检查。
- **充分性评价**：实验设计全面，消融覆盖关键超参数和设计选择，并与多种强基线公平比较。但可能存在**过度依赖特定嵌入模型**的风险（消融中最佳为NV-Embed-V2，其他模型表现略低但依旧显著优于基模型）。总体客观公平。

## 6. 主要结论与发现
- **R2-T2（特别是NGD）** 在几乎所有基准上显著提升两个MoE模型的性能。例如MoAI-7B在MMBench上+5.9%（79.3→85.2），MME-P +71.5分，TextVQA +5.7%。MoVA类似。
- **NGD是最优策略**，接近Oracle上界（捕获了70-80%的潜在提升空间），且优于Mode Finding和Kernel Regression。
- 与更大模型（13B、34B）相比，7B的MoAI/MoVA+R2-T2在多数基准上超越或持平更大模型，展示出测试时路由优化的巨大价值。
- **专家转移模式分析**：初始路由器过度依赖ILANG专家（语言对齐），R2-T2能将其切换至更适合任务的专家（如IAUX用于空间推理、LAUX用于目标识别、LIMG用于细粒度感知），且大部分转移将错误预测修正为正确。
- 消融证实：k=5、高斯核、NV-Embed-V2嵌入、10步NGD为最佳参数组合。

## 7. 优点
- **新颖性问题**：首次提出“测试时重新路由”这一概念，填补了MoE测试时自适应研究的空白。
- **训练免费**：仅优化路由权重（向量），无需更新模型参数，计算开销远低于微调或重训练。
- **方法简洁高效**：三种策略基于经典技术（梯度下降、核回归、均值漂移），易于实现和扩展。
- **鲁棒性分析全面**：测试了参考集大小、不匹配参考集、有限覆盖任务、自动化分类等场景，验证了实际可用性。
- **实验充分且公平**：固定超参数避免过拟合，消融覆盖主要设计维度，与SOTA对比包括不同规模模型。
- **性能提升显著**：在8个挑战性基准上一致改进，并能超越参数2-4倍的大模型。

## 8. 不足与局限
- **依赖参考集**：需要预先收集一个“正确预测”的参考集，且其质量直接影响性能。若参考集与测试样本分布差异大或存在噪声，可能限制提升（附录显示不匹配参考集仅微弱提升）。实际部署中构建这样的参考集可能成本较高。
- **计算开销**：NGD和Kernel Regression尽管无需训练，但每次测试需要多次前向推理（如10步，每一步需计算邻域样本损失），导致推理延迟增加约3.3倍，FLOPs增加约6-7倍。对实时性要求高的应用可能有挑战。
- **超参数敏感度**：虽然固定超参数在多任务上表现良好，但消融显示不同选择（如核函数、邻域大小、嵌入模型）会带来差异，说明实际应用中可能需要根据数据分布微调。
- **理论分析不足**：论文未提供关于优化收敛性或泛化误差的理论保证，仅凭实验验证。
- **模态泛化性**：仅验证了视觉-语言模型（VLM），未涉及其他模态（如音频、视频）。MoE架构在非视觉任务中的适用性未知。
- **安全性/偏见**：论文未讨论方法可能引入的偏见（如参考集中的偏差被放大）或鲁棒性攻击（如对抗样本下路由调整失效）。

（完）
