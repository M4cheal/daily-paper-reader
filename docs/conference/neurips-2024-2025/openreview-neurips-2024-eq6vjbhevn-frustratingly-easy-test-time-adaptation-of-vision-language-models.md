---
title: Frustratingly Easy Test-Time Adaptation of Vision-Language Models
title_zh: 极其简单的视觉语言模型测试时自适应
authors: "Matteo Farina, Gianni Franchi, Giovanni Iacca, Massimiliano Mancini, Elisa Ricci"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=eQ6VjBhevn"
tags: ["query:tta"]
score: 9.0
evidence: 视觉语言模型的测试时自适应
tldr: 本文理论分析了基于边际熵最小化的TTA方法，发现其中潜伏着一种强力的TTA变体，命名为ZERO（零温度）。ZERO无需在线反向传播，通过简单地调节温度参数即可达到甚至超越现有方法。实验在多个VLM基准上验证了其有效性和效率。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-eq6vjbhevn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1400, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-eq6vjbhevn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 933, \"height\": 687, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-eq6vjbhevn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 671, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-eq6vjbhevn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1242, \"height\": 1939, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-eq6vjbhevn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1122, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-eq6vjbhevn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-eq6vjbhevn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1386, \"height\": 1132, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-eq6vjbhevn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eq6vjbhevn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1306, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eq6vjbhevn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 752, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eq6vjbhevn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1432, \"height\": 125, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eq6vjbhevn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1449, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eq6vjbhevn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eq6vjbhevn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eq6vjbhevn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eq6vjbhevn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1451, \"height\": 749, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eq6vjbhevn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1454, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-eq6vjbhevn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1449, \"height\": 384, \"label\": \"Table\"}]"
motivation: 现有基于熵最小化的TTA方法计算开销大，且存在隐藏的有效方法未被发掘。
method: 理论推导并提出了ZERO方法，通过零温度参数实现高效TTA。
result: 在多个VLM任务上，ZERO以极小计算开销达到SOTA性能。
conclusion: ZERO揭示了TTA中一个简单但强大的方法，具有理论洞见。
---

## Abstract
Vision-Language Models seamlessly discriminate among arbitrary semantic categories, yet they still suffer from poor generalization when presented with challenging examples. For this reason, Episodic Test-Time Adaptation (TTA) strategies have recently emerged as powerful techniques to adapt VLMs in the presence of a single unlabeled image. The recent literature on TTA is dominated by the paradigm of prompt tuning by Marginal Entropy Minimization, which, relying on online backpropagation, inevitably slows down inference while increasing memory. In this work, we theoretically investigate the properties of this approach and unveil that a surprisingly strong TTA method lies dormant and hidden within it. We term this approach ZERO (TTA with “zero” temperature), whose design is both incredibly effective and frustratingly simple: augment N times, predict, retain the most confident predictions, and marginalize after setting the Softmax temperature to zero. Remarkably, ZERO requires a single batched forward pass through the vision encoder only and no backward passes. We thoroughly evaluate our approach following the experimental protocol established in the literature and show that ZERO largely surpasses or compares favorably w.r.t. the state-of-the-art while being almost 10× faster and 13× more memory friendly than standard Test-Time Prompt Tuning. Thanks to its simplicity and comparatively negligible computation, ZERO can serve as a strong baseline for future work in this field. Code will be available.

---

## 论文详细总结（自动生成）

# 论文总结：Frustratingly Easy Test-Time Adaptation of Vision-Language Models

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：视觉语言模型（VLM）在零样本分类中表现出色，但在面对分布偏移或困难样本时泛化能力不足。测试时自适应（Test-Time Adaptation, TTA）作为一种单样本在线学习方法，通过最小化边际熵（Marginal Entropy Minimization, MEM）对模型参数（如提示词）进行在线微调，已成为主流范式。然而，该范式依赖在线反向传播，导致推理速度慢、内存占用高。
- **核心问题**：MEM 是否真正有效？能否在无需优化的情况下获得同样甚至更好的性能？
- **整体含义**：论文通过理论和实验揭示，MEM 对边际概率分布的预测影响极小，而边际概率分布本身（即多次增强后平均的Softmax输出）已经比原始单次预测更鲁棒。进一步发现，增强视图会导致模型过度自信（overconfidence），从而破坏边际概率的可靠性。通过简单地将Softmax温度设为0（即“投票”机制），可以在无需任何梯度更新下获得与MEM相当甚至更好的结果，且计算开销极低。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：MEM 实际上对模型预测的改变很小，而边际概率分布 `p(·|x)`（对N个增强视图的输出取平均）本身就是一个强分类器。但增强视图会引入过置信度，降低可靠性。通过将Softmax温度设为0（极限情况），使每个视图的输出变为 one-hot 向量，然后取平均（即多数投票），可以消除过置信度的影响，同时保留集成的优势。
- **关键技术细节**：
    - **步骤**：① 对测试图像进行N次随机增强（裁剪、翻转）；② 通过视觉编码器得到每个视图的logits；③ 根据熵筛选出最自信的视图（保留概率较低的10%~30%）；④ 将温度设为接近于0的极小值（如 `torch.finfo(dtype).eps`）；⑤ 计算筛选后视图的Softmax（此时几乎为one-hot）并求和（或平均），取argmax作为最终预测。
    - **公式**：  
      `ZERO(x, t_ctx, C) = argmax_{c} sum_{i} 1(x_i in X_filt) * lim_{τ→0+} p(y=c|x_i, t_ctx, τ)`  
      等价于对自信视图进行多数投票。
- **算法流程**（PyTorch风格代码已在文中给出）：
    - 输入图像、文本嵌入、视图数N、过滤比例γ、原始温度temp。
    - 生成N个增强视图；通过image_encoder得到logits；根据熵过滤；将温度设为eps；计算softmax并求和；返回argmax。
- **无需反向传播**：仅需一次前向传播，无需优化器或梯度计算。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **基准数据集**：
    - **自然分布偏移（Natural Distribution Shifts）**：ImageNet验证集、ImageNet-A（对抗性）、ImageNet-R（渲染）、ImageNet-v2、ImageNet-Sketch。
    - **细粒度分类（Fine-grained Classification）**：10个数据集：Flowers102、DTD、Oxford-Pets、Stanford Cars、UCF101、Caltech101、Food101、SUN397、FGVC-Aircraft、EuroSAT。
- **Benchmark**：遵循TPT、PromptAlign、RLCF等工作的标准实验协议。
- **对比方法**：
    - **TPT**（Test-Time Prompt Tuning）：基于MEM的提示词优化。
    - **PromptAlign**：在MaPLe初始化基础上，结合MEM和分布对齐损失。
    - **RLCF**（Reinforcement Learning from CLIP Feedback）：使用更强的CLIP模型作为奖励，优化小模型。
    - **Baseline**：零样本CLIP、集成（Ensemble）等。
- **模型分组**：
    - Group 1: CLIP-ViT-B-16（与TPT对比）
    - Group 2: MaPLe初始化（与PromptAlign对比）
    - Group 3: CLIP-ViT-B-16 + CLIP-ViT-L-14（与RLCF对比）

## 4. 资源与算力

- 论文明确说明：所有实验使用 **1张 NVIDIA A100 GPU**，采用 **FP16自动混合精度**。
- 运行时间测量在 **1张 NVIDIA RTX 4090** 上进行（用于计算资源对比）。
- 未提及具体训练总时长，但给出了每张图像的推理时间（如ZERO在CLIP-ViT-B-16上每图像约0.06秒，TPT约0.57秒）。
- 未说明预训练或超参数搜索的算力消耗。

## 5. 实验数量与充分性

- **实验数量**：
    - 自然分布偏移：5个数据集 × 3个模型分组 → 每组详细报告准确率（含均值）。
    - 细粒度分类：10个数据集 × 3个模型分组。
    - 额外实验：LAION-2B预训练模型、CoOp初始化、不同过滤百分比的消融（0.1 vs 0.3）。
    - 计算资源对比：时间、内存。
    - 理论验证：证明命题的统计（95%以上样本预测不变）、可靠性图、校准误差等。
- **充分性**：实验覆盖了主流基准和多种模型初始化，并进行了消融（过滤阈值）、公平性（相同硬件跑所有基线）、统计性（3个随机种子）。但未涵盖更多VLM架构（如EVA-CLIP、SigLIP等），也未在完全无过滤或不同增强策略下测试。对EuroSAT这种极端分布偏移的失败案例进行了专门分析。
- **客观性**：作者明确公开了代码，复现了基线方法，并且指出ZERO在细粒度分类上平均不如TPT（但+Ensemble可超越），表明分析坦诚。

## 6. 论文的主要结论与发现

- **关键发现1**：MEM对边际概率分布的预测影响极小，在95%以上的样本上argmax不变（理论证明+实验验证）。
- **关键发现2**：边际概率分布 `p(·|x)` 的误差率是原始模型误差率的下界（基于集成理论推导和实证）。
- **关键发现3**：数据增强会导致VLM严重过度自信（校准误差增大），从而降低 `p` 的可靠性。通过将温度设为0可以消除该问题。
- **核心贡献**：提出ZERO——无需优化、仅需一次前向传播的TTA方法，在自然分布偏移上大幅超越TPT、PromptAlign、RLCF等，在细粒度分类上与它们相当或略低，但计算效率提升10倍以上（速度）、13倍内存减少。
- **局限性**：对于卫星图像（EuroSAT）等极端OOD场景，所有TTA方法均失效（包括ZERO），原因在于增强视图严重损害原始模型性能。

## 7. 优点：方法或实验设计上的亮点

- **理论深度**：首次从理论上论证MEM对预测影响甚微，并给出p的误差下界条件。
- **极简高效**：方法仅需调节一个超参数（温度），无需任何训练，计算开销极低，易于继承和扩展。
- **实验严谨**：严格控制硬件环境复现基线，报告多次运行标准差；对EuroSAT失败案例进行了详细分析（过置信、增强误差增加）。
- **开源友好**：提供PyTorch代码片段，并承诺开源完整代码。
- **公平比较**：在分组内对比，考虑不同初始化（零样本、MaPLe、CoOp、LAION预训练）。

## 8. 不足与局限

- **理论假设的局限性**：命题2.1假设熵全局最小化且变化小，实际中高不确定性样本可能不满足，尽管实验显示仍很少（>82%）。
- **独立同分布假设**：视图间独立假设在实践中难以成立（增强视图共享源图像信息），论文附录H对此进行了讨论但未给出缓解方案。
- **数据增强依赖**：方法性能高度依赖于合适的增强策略。EuroSAT案例显示简单增强（裁剪翻转）对某些领域有害，且增强数量线性增加视觉编码器计算量。
- **细粒度分类提升有限**：在细粒度基准上，ZERO仅略优于零样本，且不如TPT（除非加上文本集成）。这表明在需要细微特征区分的场景，多数投票可能不如学习到的提示词有效。
- **场景覆盖**：仅测试了CLIP系列模型（ViT-B-16和ViT-L-14），未实验其他VLM（如SigLIP、BLIP等）或更大规模模型。
- **超参数敏感性**：置信过滤阈值（0.3）仅在ImageNet上验证后固定，不同数据集可能存在次优选择（附录B显示0.1在某些OOD数据集上更好）。
- **卫星图像失败**：EuroSAT上所有TTA方法（包括ZERO）均下降，表明当前TTA范式对极端分布偏移存在系统性局限。

（完）
