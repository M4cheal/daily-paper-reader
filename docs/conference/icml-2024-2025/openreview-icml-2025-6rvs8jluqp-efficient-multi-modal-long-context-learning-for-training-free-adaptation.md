---
title: Efficient Multi-modal Long Context Learning for Training-free Adaptation
title_zh: 高效多模态长上下文学习用于无训练自适应
authors: "Zehong Ma, Shiliang Zhang, Longhui Wei, Qi Tian"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6Rvs8jluQP"
tags: ["query:tta"]
score: 5.0
evidence: 面向多模态大语言模型的无训练自适应方法
tldr: 针对多模态大语言模型微调成本高的问题，本文提出EMLoC，一种无训练自适应方法。它将示范样本直接嵌入输入，并通过分块压缩和逐层自适应剪枝来管理长上下文。在无需梯度更新的情况下实现任务自适应，实验显示该方法在多个多模态任务上达到与微调相当的性能，且效率更高。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6rvs8jluqp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 762, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6rvs8jluqp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1725, \"height\": 763, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6rvs8jluqp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 778, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6rvs8jluqp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 796, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6rvs8jluqp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 629, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6rvs8jluqp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1605, \"height\": 624, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1665, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 747, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 748, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 868, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 716, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 866, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 723, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 780, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1509, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 881, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 713, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 926, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1423, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1127, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 496, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6rvs8jluqp/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 497, \"height\": 356, \"label\": \"Table\"}]"
motivation: 多模态大语言模型微调成本高昂，亟需无训练的高效自适应方案。
method: 将示范样本嵌入输入，结合分块压缩和逐层自适应剪枝处理长上下文。
result: 在多个多模态任务上达到与微调相当的性能，且大幅降低计算开销。
conclusion: 无训练自适应方法可有效替代微调，实现多模态模型的高效部署。
---

## Abstract
Traditional approaches to adapting multi-modal large language models (MLLMs) to new tasks have relied heavily on fine-tuning. This paper introduces Efficient Multi-Modal Long Context Learning (EMLoC), a novel training-free alternative that embeds demonstration examples directly into the model input. EMLoC offers a more efficient, flexible, and scalable solution for task adaptation. Because extremely lengthy inputs introduce prohibitive computational and memory overhead, EMLoC contributes a chunk-wise compression mechanism combined with layer-wise adaptive pruning. It condenses long-context multimodal inputs into compact, task-specific memory representations. By adaptively pruning tokens at each layer under a Jensen-Shannon divergence constraint, our method achieves a dramatic reduction in inference complexity without sacrificing performance. This approach is the first to seamlessly integrate compression and pruning techniques for multi-modal long-context learning, offering a scalable and efficient solution for real-world applications. Extensive experiments on diverse vision-language benchmarks demonstrate that EMLoC achieves performance on par with or superior to naive long-context approaches. Our results highlight the potential of EMLoC as a groundbreaking framework for efficient and flexible adaptation of multi-modal models in resource-constrained environments. Codes are publicly available at https://github.com/Zehong-Ma/EMLoC.

---

## 论文详细总结（自动生成）

# 论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：多模态大语言模型（MLLMs）在迁移至下游任务时通常依赖微调（全微调或参数高效微调），但微调需要更新模型参数，计算与存储成本高昂。
- **背景**：MLLMs 已支持多图像、视频和长上下文输入，实验发现将多个任务特定示范示例直接作为输入（即多模态长上下文学习，MLoC）可显著提升模型性能。然而，长上下文带来巨大的推理计算和内存开销。
- **目标**：提出一种无训练（training-free）的自适应方法，高效利用长上下文信息，同时降低计算负担，实现灵活、可扩展的任务适配。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 核心思想
- **EMLoC**（Efficient Multi-Modal Long Context Learning）将示范示例直接嵌入模型输入，不更新任何参数。
- 通过**分块压缩**和**逐层自适应剪枝**，将长多模态上下文压缩为紧凑的任务特定记忆表示，大幅降低推理复杂度。

### 关键技术细节
1. **分块压缩（Chunk-wise Compression）**  
   - 将长上下文划分为多个小chunk，每个chunk包含固定数量（例如20个）的示范示例。  
   - 逐chunk处理：先处理第一个chunk，将修剪后的KV缓存保留，再与后续chunk合并重复处理。

2. **逐层自适应剪枝（Layer-wise Adaptive Pruning）**  
   - 从顶层到底层逐层进行剪枝。  
   - **重要性评分**：利用当前chunk中的答案token对上下文token的注意力权重累加，作为重要性指标。  
   - **剪枝-检查步骤**：对每一层，从一组保留比率（例如 [0.1, 0.2, 0.5, 1.0]）中贪心选择最小比率，仅保留top-k token。  
   - **JS散度约束**：每次剪枝后，计算原始输出分布与剪枝后输出分布之间的Jensen-Shannon散度。若散度低于预设阈值δ（默认0.005），则接受该剪枝比率；否则增大比率直至满足约束或达到1.0。  
   - 逐层推进，最终得到压缩后的全局记忆。

### 算法流程（文字说明）
- **输入**：第k个chunk的上下文C_k，该chunk的示范示例D_k，前k-1个chunk的压缩记忆M_{k-1}。
- **步骤**：
  1. 提取M_k：基于M_{k-1}和C_k得到完整KV缓存。
  2. **前向示范**：将M_{k-1}⊕M_k与D_k一起输入模型，获取原始输出概率p_ori、注意力权重α、隐藏状态H。
  3. **逐层剪枝**（从顶层L到底层1）：
     - 计算当前层token重要性β^l。
     - 按保留比率集R从小到大的顺序尝试剪枝：仅保留Top-(r×S)个token。
     - 用修剪后的记忆和隐藏状态H^l做前向，得到p_iter。
     - 若JS(p_ori, p_iter) ≤ δ，则接受该r，否则继续尝试更大r，直至达到1.0。
  4. 将所有层的修剪结果合并，得到当前chunk的压缩记忆�̂�_k。
  5. 拼接M_{k-1}和�̂�_k，得到M_k，作为最终记忆输入下一chunk。

### 理论分析
- 对信息损失建立了线性上界：全局JS距离√Δ ≤ (K-1)√δ + ε，其中K是chunk数，δ是局部约束。实际观察中Δ几乎与K无关，使δ成为唯一需要调参的变量。

## 3. 实验设计

### 数据集和场景（6个基准）
| 数据集 | 领域 | 样本/任务 |
|--------|------|-----------|
| ImageNet100（ImageNet-1k子集，100类） | 图像分类 | 5000张测试图 |
| ScreenSpot | 跨平台GUI定位 | -- |
| MME-RW | 真实世界多模态（OCR、遥感、驾驶等） | 100个测试样本 |
| IllusionVQA | 光学错觉理解 | 100个测试样本 |
| OK-VQA | 开放知识问答 | 100个测试样本 |
| YouCook2 | 视频理解（烹饪视频） | 100个测试样本 |

### 对比方法
- **基础长上下文基线**：MLoC（直接喂入全部示范示例，无压缩）
- **其他多模态ICL方法**：RICES（检索相似样本）、MTV（任务向量）
- **微调方法**：全微调、LoRA、VPT、E²PT、M²PT
- **剪枝策略**：SnapKV、H2O、PyramidKV、FastGen、PyramidInfer

## 4. 资源与算力

- **GPU**：NVIDIA L20，显存48GB，batch size=1。
- **适应时间**（即压缩阶段的额外前向）：EMLoC在ImageNet100上需144秒（10个chunk），相比LoRA微调234秒、全微调820秒。
- **推理时间**：与MLoC相比，EMLoC大幅减少（如ImageNet100从1866s降至1107s）。
- **峰值内存**：EMLoC在适应阶段约38G（对应1.6k chunk），但可通过增加chunk数降低内存（如0.8k chunk仅24G）。
- **未明确说明**：使用了多少张GPU，以及总训练/适应耗时；论文仅报告单卡测量值。

## 5. 实验数量与充分性

- **实验组数**：超过15组对比，涵盖：
  - 主表（Table 1）在6个任务上的性能与上下文长度对比。
  - 不同示范数量（Table 2）ImageNet100上5/50/200/300示例。
  - 与其他ICL方法比较（Table 3）。
  - 与微调方法比较（Table 4）。
  - 消融实验：不同剪枝策略（Table 5）、不同δ（Figure 3）、不同chunk长度（Table 6）、不同保留比率（Table 7）、观察窗口（Table 8）。
  - 可视化分析：各层剩余token数及JS散度分布（Figure 4）、剪枝token类型分布（Figure 5）。
  - 附加实验：长视频基准（Table 10）、超参鲁棒性（Table 11-12）、任务差异影响（Table 13-14）。
- **充分性**：实验覆盖了多个任务类型（分类、VQA、定位、视频理解），对比了多种当前主流基线，且进行了理论分析，整体比较充分。
- **公平性**：所有方法使用相同的示范样本和模型基座Qwen2-VL，推理设置保持一致（如分辨率、batch size等）。

## 6. 主要结论与发现

- **EMLoC可在无训练前提下显著降低上下文长度**，平均压缩77%（从11338 token降至2600），而性能与原始MLoC相当甚至更好。
- **动态剪枝优于静态固定剪枝**：在同样压缩率（如22.4%）下，EMLoC保持63.7%准确率，而SnapKV/H2O仅47.6%、PyramidKV仅49.3%。
- **JS散度阈值δ可有效控制压缩与精度权衡**；默认δ=0.005在多数任务上表现良好。
- **分块压缩使大模型可以在消费级GPU（如24G显存）上处理长上下文**，且不影响最终性能。
- **任务自适应性**：EMLoC在低任务差异（与预训练数据相似）的任务上表现突出；在高度差异的任务（如医疗QA）上所有方法均困难，符合预期。

## 7. 优点

1. **无需微调**：模型参数不变，即插即用，适配成本极低（仅需少量前向传播）。
2. **动态剪枝策略**：基于JS散度约束自适应决定每层保留多少token，优于固定比率/金字塔启发式方法。
3. **理论保证**：证明局部JS约束可控制全局信息损失，提供可调参数δ。
4. **高效实现**：分块机制支持在有限显存设备上运行，且推理时间大幅缩短。
5. **广泛实验**：在6个不同领域任务上验证，并与多种ICL、微调、剪枝方法对比，结果具有说服力。
6. **可复现性**：代码已开源。

## 8. 不足与局限

1. **模型泛化性**：实验仅基于Qwen2-VL进行，未在其他MLLM（如LLaVA、InternVL）上验证，方法对模型架构的依赖性未知。
2. **额外适应开销**：虽然无需训练，但压缩阶段需要额外的前向传播（适应时间约144秒），对于大规模部署仍需考虑。
3. **阈值选择敏感性**：虽然δ默认0.005在多数任务稳定，但在极端压缩场景（δ=0.02）性能下降明显，需手动调节。
4. **示范示例选择**：论文采用均匀采样，未探究示例质量或排序对压缩效果的影响，这在实际应用中可能重要。
5. **长视频场景验证有限**：虽然在YouCook2和VideoMME上测试，但仅使用8帧或384帧，未在更长（如数千帧）视频上验证。
6. **上下文长度上限**：论文在200示例时表现良好，但当示例数继续增加（如300示例）时，EMLoC精度略有波动（62.6 vs 63.7），可能受压缩极限影响。

（完）
