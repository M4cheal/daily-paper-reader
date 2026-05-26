---
title: Backpropagation-Free Test-Time Adaptation via Probabilistic Gaussian Alignment
title_zh: 基于概率高斯对齐的无反向传播测试时自适应
authors: "Youjia Zhang, Youngeun Kim, Young-Geun Choi, Hongyeob Kim, Huiling Liu, Sungeun Hong"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=rYv42fDKQi"
tags: ["query:tta"]
score: 9.0
evidence: 提出无反向传播的TTA方法，利用概率高斯对齐
tldr: 现有测试时自适应（TTA）方法依赖反向传播，限制了实时部署且缺乏对类别条件特征分布的建模。本文提出ADAPT，一种无需反向传播的TTA方法，通过对齐概率高斯分布来显式建模类别条件分布，从而生成可靠的决策边界和校准的预测。在多种分布偏移场景下，ADAPT不仅显著降低计算开销，还提升了鲁棒性和模型校准能力。该方法为高效、可部署的TTA提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ryv42fdkqi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ryv42fdkqi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ryv42fdkqi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ryv42fdkqi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ryv42fdkqi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 1427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ryv42fdkqi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 433, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1370, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 840, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 822, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 580, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 845, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 724, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 577, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 686, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 778, \"height\": 574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 872, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 590, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1439, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1441, \"height\": 571, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 796, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 795, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ryv42fdkqi/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 796, \"height\": 445, \"label\": \"Table\"}]"
motivation: 现有TTA方法依赖反向传播导致推理速度慢，且忽略类别条件特征分布建模。
method: ADAPT通过概率高斯对齐建模类别条件分布，无需反向传播，实现高效自适应。
result: 在多种分布偏移数据集上，ADAPT在降低计算开销的同时提升了准确率和模型校准度。
conclusion: 提出了一种无需反向传播的TTA方法，兼顾效率与鲁棒性，适合实时部署。
---

## Abstract
Test-time adaptation (TTA) enhances the zero-shot robustness under distribution shifts by leveraging unlabeled test data during inference. Despite notable advances, several challenges still limit its broader applicability. First, most methods rely on backpropagation or iterative optimization, which limits scalability and hinders real-time deployment. Second, they lack explicit modeling of class-conditional feature distributions. This modeling is crucial for producing reliable decision boundaries and calibrated predictions, but it remains underexplored due to the lack of both source data and supervision at test time. In this paper, we propose ADAPT, an Advanced Distribution-Aware and backPropagation-free Test-time adaptation method. We reframe TTA as a probabilistic inference task by modeling class-conditional likelihoods using gradually updated class means and a shared covariance matrix. This enables closed-form, training-free inference. To correct potential likelihood bias, we introduce lightweight regularization guided by CLIP priors and a historical knowledge bank. ADAPT requires no source data, no gradient updates, and no full access to target data, supporting both online and transductive settings. Extensive experiments across diverse benchmarks demonstrate that our method achieves state-of-the-art performance under a wide range of distribution shifts with superior scalability and robustness.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：测试时间自适应（TTA）旨在利用无标签测试数据增强视觉-语言模型（如CLIP）在分布偏移下的零样本鲁棒性。现有TTA方法大多依赖反向传播或迭代优化，导致计算成本高、实时部署困难；同时缺乏对类条件特征分布的显式建模，这使得决策边界不稳定、预测校准性差。
- **背景**：早期方法如提示微调、适配器微调需要反向传播；近期无训练方法基于记忆库或相似度评分，但仍需调整超参数且未捕捉分布结构。作者提出ADAPT方法，将TTA重新定义为概率高斯对齐任务，实现免反向传播、无迭代优化的自适应。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：假设类条件特征服从高斯分布，并共享协方差矩阵，利用CLIP原型初始化类均值，通过高置信度样本构建的知识库逐步更新均值和协方差，得到闭式解，无需训练或迭代。
- **关键技术细节**：
  - 维护每个类别的固定大小知识库，存储高置信度样本的伪标签和特征。
  - 在线设置下，利用负对数似然、CLIP先验正则化和知识库一致性正则化构造损失函数，推导出闭式标签估计公式（式8）和类均值更新公式（式9），协方差采用贝叶斯脊估计（式10）。
  - 转导设置下，利用整个测试集和知识库，用类似闭式解实现全局优化（式12）。
  - 整个流程无反向传播，支持在线流式处理和转导批处理两种模式。
- **算法流程**（文字说明）：
  - 在线：每来一个样本，计算置信度，更新知识库；用知识库样本更新均值和协方差；利用闭式公式预测当前样本标签。
  - 转导：先对整个测试集计算置信度，构建知识库；利用所有样本和知识库一次更新均值和协方差；为所有样本计算闭式标签。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：三类任务。
  - 自然分布偏移：ImageNet、ImageNet-A、ImageNet-V、ImageNet-R、ImageNet-Sketch。
  - 腐败鲁棒性：ImageNet-C（15种合成腐败，5个严重级别）。
  - 细粒度分类：Aircraft、Caltech101、Cars、DTD、EuroSAT、Flower102、Food101、Pets、SUN397、UCF101。
- **基准**：CLIP零样本作为基线；对比方法包括基于反向传播的（TPT、DiffTPT、C-TPT、DMN、DPE、TPS、DynaPrompt、B2TPT）和免反向传播的（MTA、TDA、ZERO、AWT、RA-TTA、BCA、TCA、Dota等），以及转导方法（GDA-CLIP、TransCLIP、Frolic、TIMO、ZLaP、StatA等）。
- **实验设置**：在线（batch_size=1）和转导两种协议；基于CLIP ViT-B/16，部分实验使用CLIP-RN50。

### 4. 资源与算力
- 论文明确说明所有实验在一块NVIDIA RTX A6000 GPU上运行。
- 在线设置下，ADAPT在ImageNet上耗时1h 11min，GPU显存0.93GB；转导设置下耗时0.73min，显存3.37GB（见表6）。
- 对比方法如TPT耗时9h 45min，显存4.29GB；DiffTPT >20h。

### 5. 实验数量与充分性
- **数量**：在三大类任务（自然偏移、腐败、细粒度）共约27个数据集上进行了全面评估，涵盖在线和转导两种设置。此外还进行了消融实验（表5）、超参数分析（图2）、效率对比（表6）、均值初始化实验（表7）、闭式与迭代对比（表8）、输入顺序影响（表9）、少样本实验（图5）、不同骨干网络实验（图6）等，总计超过30组实验。
- **充分性**：实验覆盖了多种分布偏移场景和模型架构，对比了多个SOTA方法，消融验证了各组件的必要性。实验设计客观公平，采用与基线一致的评估协议。但仅使用了CLIP和少量其他VLM（BLIP、ALBEF），未在更多基础模型上验证。

### 6. 论文的主要结论与发现
- ADAPT在自然分布偏移、腐败鲁棒性、细粒度分类三个任务上，在线和转导设置均达到或超过了现有最好方法，且无需反向传播。
- 在效率方面，ADAPT比基于反向传播的方法快数倍甚至百倍，显存消耗低。
- 闭式解的性能与迭代优化的方法相当，但速度更快（4×加速）。
- 知识库和分布建模对稳定自适应至关重要，早期排除当前样本可避免误差累积。
- 方法对知识库大小、均值初始化等超参数鲁棒，适用于在线和转导场景。

### 7. 优点
- 方法创新：将TTA转化为概率高斯对齐，实现了真正免反向传播、免迭代优化的闭式解，逻辑清晰且理论上可靠。
- 高效性：极低的计算和内存开销，适合实时/流式部署。
- 灵活性：同时支持在线和转导两种设置，无需修改核心算法。
- 理论支撑：提供了完整的推导和证明，并对高斯假设进行了实证检验（投影法正态性检验、协方差共享性验证）。
- 实验充分且结果显著：在多个主流基准上超越现有方法，消融实验和超参数分析全面。

### 8. 不足与局限
- 高斯假设可能无法捕捉真实数据中复杂的多模态分布；作者也承认这是局限性，但提供了实证表明该假设在CLIP特征上近似成立。
- 在在线设置中，若初始大量低置信度样本，知识库填充慢可能延迟自适应；作者通过排除当前样本缓解了早期过拟合。
- 实验主要基于CLIP ViT-B/16和RN50，仅在少量VLM上验证，泛化性有待在更多架构上测试。
- 对极端低置信度场景（表中N=2时在线性能下降较多）有一定敏感性，但转导模式鲁棒。
- 未讨论公平性、隐私等社会影响。

（完）
