---
title: "OOD-Barrier: Build a Middle-Barrier for Open-Set Single-Image Test Time Adaptation via Vision Language Models"
title_zh: OOD-Barrier：通过视觉语言模型为开集单图像测试时间自适应构建中间屏障
authors: "Boyang Peng, Sanqing Qu, Tianpei Zou, Fan Lu, Ya Wu, Kai Chen, Siheng Chen, Yong Wu, Guang Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=GUPx2otaKL"
tags: ["query:tta"]
score: 8.0
evidence: 面向视觉语言模型的开集单图像测试时间自适应
tldr: 现实环境中的测试样本可能是开集（包含分布外样本）且逐张到达，现有方法依赖批处理。Open-IRT提出基于中间表示的测试时间自适应框架，通过构建屏障将分布内和分布外样本分开，从而在单样本流中安全自适应。在开集TTA基准上，该方法有效兼顾了分布内性能和对分布外样本的拒绝能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupx2otakl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 982, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupx2otakl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupx2otakl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 711, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupx2otakl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 844, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupx2otakl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1490, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupx2otakl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1479, \"height\": 280, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupx2otakl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 641, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupx2otakl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1454, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupx2otakl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1465, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupx2otakl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 853, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupx2otakl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 818, \"height\": 335, \"label\": \"Table\"}]"
motivation: 解决开集单图像场景下批处理TTA无法适用的问题。
method: 构建中间表示屏障，分离分布内与分布外样本，逐图像自适应。
result: 在开集TTA基准上分布内准确率和OOD拒绝率均达最优。
conclusion: 基于中间屏障的框架为实时开集TTA提供了可行方案。
---

## Abstract
In real-world environments, a well-designed model must be capable of handling dynamically evolving distributions, where both in-distribution (ID) and out-of-distribution (OOD) samples appear unpredictably and individually, making real-time adaptation particularly challenging. While open-set test-time adaptation has demonstrated effectiveness in adjusting to distribution shifts, existing methods often rely on batch processing and struggle to manage single-sample data stream in open-set environments. To address this limitation, we propose Open-IRT, a novel open-set Intermediate-Representation-based Test-time adaptation framework tailored for single-image test-time adaptation with vision-language models. Open-IRT comprises two key modules designed for dynamic, single-sample adaptation in open-set scenarios. The first is Polarity-aware Prompt-based OOD Filter module, which fully constructs the ID-OOD distribution, considering both the absolute semantic alignment and relative semantic polarity. The second module, Intermediate Domain-based Test-time Adaptation module, constructs an intermediate domain and indirectly decomposes the ID-OOD distributional discrepancy to refine the separation boundary during the test-time. Extensive experiments on a range of domain adaptation benchmarks demonstrate the superiority of Open-IRT. Compared to previous state-of-the-art methods, it achieves significant improvements on representative benchmarks, such as CIFAR-100C and SVHN — with gains of +8.45\% in accuracy, -10.80\% in FPR95, and +11.04\% in AUROC.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

现实环境中，模型需要应对动态变化的分布，其中分布内（ID）和分布外（OOD）样本可能不可预测地、逐个地出现，这给实时自适应带来了巨大挑战。现有的开放集测试时自适应（open-set test-time adaptation）方法虽然能处理分布偏移，但大多依赖批处理方式，难以应对开放集环境下的单样本数据流（single-sample data stream）。为此，本文提出 **Open-IRT** 框架，专门面向**基于视觉语言模型（VLM）的开放集单图像测试时自适应**任务，旨在实时、逐样本地处理ID和OOD样本的混合流，提升模型在动态开放环境中的适应能力。

### 2. 论文提出的方法论：核心思想、关键技术细节

#### 核心思想
- 利用视觉语言模型（如CLIP）的**跨模态信息**，通过**极性感知提示**和**中间域构建**，间接扩大ID与OOD特征分布之间的边界。
- 提出两个假设：**语义对比假设**（Hypothesis 1）和**中间域特征刻画假设**（Hypothesis 2），并据此设计两个模块。

#### 关键技术细节

1. **极性感知提示基OOD过滤器（PPF）**
   - 为每个ID类别设计**正提示**（如“a photo of [CLS]”）和**负提示**（如“a photo of no [CLS]”）。
   - 对输入图像特征 \( f \)，计算与正提示的相似度 \( \text{sim}_{\text{pos}} \)、与负提示的相似度 \( \text{sim}_{\text{neg}} \)，以及两者的绝对差 \( \text{sim}_{\text{diff}} \)。
   - 定义得分函数：  
     \[
     S(f) = \phi\left( \sup_{c \in [C]} [\text{sim}(f, p_c) + \alpha |\text{sim}(f, p_c) - \text{sim}(f, p'_c)|] \right)
     \]
     其中 \(\phi\) 是min-max归一化，\(\alpha\) 控制对比强度。
   - 将得分存入滑动窗口银行 \( B_s \)，并用**高斯混合模型（GMM）** 对得分分布建模，从而判定样本为ID或OOD，并将对应特征存入特征银行 \( B_f \)。

2. **基于中间域的测试时自适应（IDT）**
   - 根据假设2，构建**中间域特征** \( f_m \)：通过风格迁移方式合并ID和OOD的均值和方差，使中间域位于ID和OOD之间。
   - 当样本被高置信度判定为ID时，使用对比学习损失 \( L_I \) 拉近输入与ID邻居、推远与OOD邻居及中间特征；当为OOD时，用 \( L_O \) 反向操作。
   - 设计**阈值基双向伪标签损失** \( L_{\text{psd}} \)：对高置信度样本使用标准交叉熵，对低置信度样本使用负交叉熵，以抑制噪声。
   - 总测试时损失 \( L_{\text{TTA}} = L_{\text{psd}} + L_{\text{mid}} \)，其中 \( L_{\text{mid}} \) 为前一步的对比损失。

#### 算法流程（文字说明）
- 初始化：正负提示、空特征银行和得分银行。
- 对每个测试样本：
  1. 提取视觉特征，计算PPF得分，通过GMM得到ID/OOD判别结果。
  2. 根据判别结果和置信度，构建中间域特征。
  3. 从特征银行中检索K近邻，计算对比损失和伪标签损失。
  4. 反向传播更新视觉编码器参数（文本编码器冻结）。
  5. 更新银行（滑动窗口）。

### 3. 实验设计

- **ID数据集**：CIFAR-10C/100C、ImageNet-C、VisDA。
- **OOD数据集**：MNIST、MNIST-M、SVHN、Tiny-ImageNet、CIFAR-100C（作为OOD的小偏移情况）。
- **基准（Benchmark）**：采用开放集单图像测试时自适应设定，每次仅用一个样本进行在线更新和评估。
- **对比方法**：ZS-Eval、TPT、TPT-C、ROSITA、OWTTT、TDA、UniEnt、DPE、PAlign、PAlign-C等。
- **指标**：AUROC（面积）、FPR95（95%真阳性率下的假阳性率）、Acc HM（ID准确率与OOD二元分类精度的调和平均）。

### 4. 资源与算力

- 实验平台：ImageNet-C实验使用**NVIDIA A6000 GPU**，其余实验使用**NVIDIA 3090 GPU**。
- 未明确说明GPU数量、总训练时长或具体运行时间。

### 5. 实验数量与充分性

- **主要实验**：在CIFAR、ImageNet-C、VisDA三个大类上进行了多组ID→OOD实验，涵盖不同复杂度。
- **消融实验**：验证PPF中GMM vs LDA、IDT中各损失组件（\( L_{\text{mid}} \)、\( L_{\text{psd}} \)、λ设置）的作用。
- **附加分析**：不同骨干网络（ViT-B/16、ViT-B/32、ResNet50）、不同OOD比例（0.2~1.0）的鲁棒性实验。
- **评估充分性**：实验覆盖了多种领域偏移和语义偏移场景，对比方法全面，结果清晰。但未报告多次运行的标准差或置信区间，无法评估统计显著性。

### 6. 论文的主要结论与发现

- Open-IRT在单样本数据流设定下显著优于现有SOTA方法，例如在CIFAR-100C→SVHN任务中，**Acc HM提升+8.45%，FPR95降低-10.80%，AUROC提升+11.04%**。
- PPF的极性感知得分能有效分离ID和OOD，GMM优于LDA。
- IDT的中间域构建策略能间接扩大ID-OOD边界，且双向伪标签损失有助于抑制噪声。
- 该方法对骨干网络和OOD比例变化鲁棒，适用性广。

### 7. 优点

- **创新性强**：首次将“中间域”概念引入开放集单图像测试时自适应，利用VLM的极性和对比信息。
- **设计巧妙**：PPF结合绝对对齐和相对极性，IDT通过间接分解分布差异而非直接最大化ID-OOD距离，更易优化。
- **实验全面**：在多个经典benchmark上与众多基线对比，涵盖不同复杂度、多种OOD类型。
- **实际意义重大**：面向实时、单样本流场景（如自动驾驶、安防），弥补了现有批处理方法的不足。

### 8. 不足与局限

- **内存开销**：方法依赖大小固定的特征银行和得分银行（size=128），与“单图像”自适应的严格前提存在张力，未来需在严格单图像设定下实现稳健性能。
- **应用范围**：仅在图像分类上验证，未扩展到物体检测、语义分割等更复杂的开放集任务。
- **统计可靠性**：未报告重复实验的误差条，结果可能受随机因素影响。
- **计算效率**：每样本需反向传播更新模型，实时性可能受限于模型规模和硬件；未提供时间开销数据。
- **假设验证**：假设1和2的数学形式较软，缺乏严格的理论保证，更多是经验启发。

（完）
