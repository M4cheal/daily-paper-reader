---
title: Test-Time Degradation Adaptation for Open-Set Image Restoration
title_zh: 开放集图像恢复的测试时退化适应
authors: "Yuanbiao Gou, Haiyu Zhao, Boyun Li, Xinyan Xiao, Xi Peng"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=XLlQb24X2o"
tags: ["query:tta"]
score: 7.0
evidence: 开放集图像恢复的测试时退化适应
tldr: 开放集图像恢复面临未知退化（分布偏移）。本文受TTA启发，提出包含预训练扩散模型和测试时退化适配器的框架，在推理时适应未知退化。实验证明该框架有效处理了训练时未见过的退化类型，扩展了图像恢复的适用性。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-xllqb24x2o/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xllqb24x2o/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1744, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xllqb24x2o/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1758, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xllqb24x2o/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1649, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xllqb24x2o/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1482, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xllqb24x2o/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 819, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xllqb24x2o/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 856, \"height\": 408, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-xllqb24x2o/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1585, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xllqb24x2o/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1618, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xllqb24x2o/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 868, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xllqb24x2o/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1481, \"height\": 166, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xllqb24x2o/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 811, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xllqb24x2o/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 161, \"label\": \"Table\"}]"
motivation: 开放集图像恢复需处理训练时未见的未知退化。
method: 结合预训练扩散模型与测试时退化适配器。
result: 在多个未知退化场景下恢复质量优于现有方法。
conclusion: TTA框架有效解决了开放集图像恢复中的未知退化问题。
---

## Abstract
In contrast to close-set scenarios that restore images from a predefined set of degradations, open-set image restoration aims to handle the unknown degradations that were unforeseen during the pretraining phase, which is less-touched as far as we know. This work study this challenging problem and reveal its essence as unidentified distribution shifts between the test and training data. Recently, test-time adaptation has emerged as a fundamental method to address this inherent disparities. Inspired by it, we propose a test-time degradation adaptation framework for open-set image restoration, which consists of three components, *i.e.*, i) a pre-trained and degradation-agnostic diffusion model for generating clean images, ii) a test-time degradation adapter adapts the unknown degradations based on the input image during the testing phase, and iii) the adapter-guided image restoration guides the model through the adapter to produce the corresponding clean image. Through experiments on multiple degradations, we show that our method achieves comparable even better performance than those task-specific methods. The code is available at https://github.com/XLearning-SCU/2024-ICML-TAO.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

- **研究动机**：现有图像恢复方法大多假设测试时的退化类型与训练时一致（闭集场景），这限制了它们在真实世界中处理多样且不可预见的退化时的泛化能力。作者正式定义了**开放集图像恢复（Open-Set Image Restoration, OIR）**问题，要求模型能处理预训练阶段未见过、未知的退化类型。
- **本质**：OIR的本质是测试数据与训练数据之间存在**未识别的分布偏移**。作者指出测试时适应（Test-Time Adaptation, TTA）是应对这种偏移的有效方法论。

## 2. 方法论：核心思想、关键技术细节与流程

- **核心思想**：利用预训练的退化不可知的扩散模型作为通用生成器，在测试阶段通过一个轻量级适配器将模型适应到未知退化，并通过动态引导策略逐步恢复清晰图像。
- **框架组成**（称为 **TAO**）：
  1. **预训练扩散模型（PDM）**：固定参数，用于在测试阶段逐步去噪生成图像。选用无条件扩散模型，预训练于ImageNet，对退化类型完全不可知。
  2. **测试时退化适配器（TDA）**：一个四层卷积网络，在测试阶段针对每个输入样本进行优化。通过域对齐（对抗训练+重建损失+感知损失）将生成的清晰图像翻译到退化域，从而提供监督信号。
  3. **适配器引导的图像恢复（AIR）**：利用TDA产生的梯度来更新生成图像，使其逼近真实干净图像。根据去噪过程中的时间动态，将过程分为三个阶段，采用不同策略：
     - **第一阶段**（t~999-700）：图像内容模糊，使用MSE损失学习全局信息。
     - **第二阶段**（t~700-50）：感知内容丰富，引入感知损失、对抗损失和MSE损失。
     - **第三阶段**（t~50-0）：细节修补，加入总变分正则项。
- **关键公式**：引导梯度 \( G = \nabla_{\hat{x}_0} \log p_\phi(y|\hat{x}_0) \)，其中适配器 \( \phi \) 输出翻译后的退化图像，用于与输入退化图像 \( y \) 计算损失。
- **流程**：每个去噪步骤，同时生成一个“引导图像”和一个“辅助图像”，通过TDA优化适配器，再通过AIR更新引导图像，逐步生成最终清晰图像。

## 3. 实验设计

- **数据集与场景**：
  - **图像去雾**：使用RESIDE中的HSTS测试集（10张合成+10张真实雾图）。
  - **低光图像增强**：使用LOL数据集测试集（15对低光/正常光图像）。
  - **图像去噪**：使用Kodak24数据集（24张自然图像，添加σ=30的高斯噪声）。
- **Benchmark与对比方法**：
  - 每项任务都分别对比了经典的**有监督学习方法**（如DehazeNet、MBLLEN、BM3D等）和**零样本方法**（如DCP、Zero-DCE、DIP等）。仅本方法为统一框架，未针对任务专门训练。
- **评价指标**：PSNR、SSIM。

## 4. 资源与算力

- 论文未明确说明训练时长或使用的GPU数量。仅在“Experimental Settings”中提及实验基于PyTorch，在 **Ubuntu20.04 + GeForce RTX 3090 GPU** 上运行。适配器和判别器均为四层卷积，使用Adam优化器，学习率1e-3，每一步去噪只优化一次。
- 整体算力需求：由于需要逐样本地在测试阶段迭代优化适配器（1000步去噪），计算代价较高，但未给出具体时间。

## 5. 实验数量与充分性

- **主要实验**：在3种不同退化（去雾、低光增强、去噪）上进行定量和定性比较，每种任务均与多个（9~10个）代表性方法对比。
- **消融与分析实验**：
  - 对TDA的域对齐策略进行了对比（GAN变体：VGAN-S/B、LSGAN、WGAN等）。
  - 对AIR的三阶段引导策略进行了消融（去除某阶段或使用统一MSE）。
  - 对阶段划分步数进行了敏感性分析（不同分割点）。
  - 通过可视化展示了域对齐效果和去噪过程动态。
- **充分性评价**：实验覆盖了多种常见图像退化，对比了目前最强的有监督和零样本方法，消融实验系统验证了各组件的必要性。整体设计较充分公平。但仅测试了合成退化或模拟退化，缺乏真实复杂退化场景的验证。

## 6. 主要结论与发现

- 提出的TAO框架能够在多个开放集退化任务中取得与任务特定方法相当甚至更好的性能，证明了TTA可有效应对未知退化分布偏移。
- 预训练扩散模型作为通用图像生成器具有强大能力，结合测试时适配器可以灵活适应新退化。
- 动态的三阶段引导策略比单一策略更优，符合去噪过程的时间动态。
- TDA的域对齐能力是关键，能够将生成图像翻译到目标退化域，从而提供有效监督。

## 7. 优点

- **问题新颖性**：率先明确界定开放集图像恢复问题，并揭示其与分布偏移的本质联系。
- **方法创新性**：首次将测试时适应引入图像恢复领域，利用扩散模型的通用性，无需针对每种退化训练模型。
- **设计巧妙**：采用辅助图像防止适配器退化为恒等映射；三阶段动态引导充分利用去噪过程的特性。
- **实验扎实**：在三种不同退化上验证，与大量专用方法公平对比，消融实验完整。
- **代码开源**：提供GitHub仓库，便于复现与扩展。

## 8. 不足与局限

- **泛化性局限**：不同退化类型需要手动调节损失权重和引导尺度，尚未实现完全自适应。
- **计算开销**：测试阶段需在每步去噪中优化适配器，实际应用时计算成本较高，难以满足实时需求。
- **测试场景受限**：仅测试了合成退化（雾、低光、高斯噪声），未涉及真实世界中的复杂混合退化或盲退化（如运动模糊+噪声等）。
- **恢复质量有提升空间**：部分任务（如低光增强）存在轻微色偏；PSNR/SSIM在某些任务上未达到最优，且未使用更先进的感知指标（如LPIPS、FID）。
- **依赖大型预训练模型**：扩散模型参数量大，且要求输入尺寸固定（需中心裁剪和缩放），可能丢失原始图像信息。

（完）
