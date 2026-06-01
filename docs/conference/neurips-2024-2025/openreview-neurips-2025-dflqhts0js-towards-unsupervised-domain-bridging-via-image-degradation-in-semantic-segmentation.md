---
title: Towards Unsupervised Domain Bridging via Image Degradation in Semantic Segmentation
title_zh: 通过图像退化实现无监督域桥接的语义分割方法
authors: "Wangkai Li, Rui Sun, Huayu Mai, Tianzhu Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=dFlqhts0jS"
tags: ["query:ris"]
score: 6.0
evidence: 通过图像退化构建中间域解决域偏移
tldr: 针对语义分割在目标域上性能下降的问题，提出无监督域桥接方法DiDA。该方法通过简单图像退化操作构建连续中间域，迫使网络学习域不变特征，并引入语义保持损失保留分割结构。实验证明该方法在多个域适应基准上有效提升分割精度，为域偏移问题提供了轻量级解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1425, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 423, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 977, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1387, \"height\": 1185, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1338, \"height\": 865, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1435, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1419, \"height\": 836, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1423, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1421, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1420, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dflqhts0js/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1424, \"height\": 730, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 890, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 516, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 648, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 547, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1057, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 653, \"height\": 116, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 685, \"height\": 116, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 617, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 659, \"height\": 118, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 578, \"height\": 115, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dflqhts0js/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 616, \"height\": 187, \"label\": \"Table\"}]"
motivation: 语义分割在跨域时性能显著下降，现有无监督域适应方法未显式建模域共享特征。
method: 提出DiDA，包含退化构建中间域模块和语义保持模块，在退化域上训练不变特征。
result: 在多个域适应数据集上超越现有方法，尤其在大域间隙场景下提升明显。
conclusion: 简单退化操作可有效桥接域差异，为域适应提供新思路。
---

## Abstract
Semantic segmentation suffers from significant performance degradation when the trained network is applied to a different domain. To address this issue, unsupervised domain adaptation (UDA) has been extensively studied. 
Despite the effectiveness of selftraining techniques in UDA,  they still overlook the explicit modeling
of domain-shared feature extraction.
In this paper, we propose DiDA, an unsupervised domain bridging approach for semantic segmentation.   DiDA consists of two key modules: (1) Degradation-based Intermediate Domain Construction, which creates continuous intermediate domains through simple image degradation operations to encourage learning domain-invariant features as domain differences gradually diminish; (2) Semantic Shift Compensation, which leverages a diffusion encoder to  disentangle and compensate for semantic shift information with degraded time-steps, preserving discriminative representations in the intermediate domains.
As a plug-and-play solution, DiDA supports various degradation operations and seamlessly integrates with existing UDA methods. Extensive experiments on multiple domain adaptive semantic segmentation benchmarks demonstrate that DiDA consistently achieves significant performance improvements across all settings.
Code is available at https://github.com/Woof6/DiDA.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：语义分割模型在源域（如合成数据）上训练后，直接应用于目标域（如真实场景）时，因域间分布差异（domain shift）导致性能严重下降。
- **背景**：无监督域适应（UDA）通过利用无标签目标域数据来迁移知识，其中自训练（self-training）方法虽已成为主流，但现有方法未显式建模域共享特征（domain-shared feature）的提取。作者从因果表示学习角度指出，观察特征由因果特征（域不变，如形状）和环境特征（域特定，如纹理）共同生成，域偏移导致学习真正的域不变表示变得困难。
- **核心动机**：探索图像退化操作（如加噪）作为先验，通过构建中间域来逐步消除域特定属性，迫使网络学习域不变特征，从而桥接域差异。

## 2. 方法论

### 核心思想
- 利用扩散模型的前向过程理论：随着噪声添加，域特定属性（如纹理）先丢失，域不变属性（如形状）后丢失，不同域的噪声分布重叠区域增大，该重叠区域可视为域共享分布，作为学习域不变表示的先验。
- 将图像退化正式化为扩散前向过程，构建一系列连续中间域，并设计语义偏移补偿机制来缓解退化导致的判别性信息丢失。

### 关键技术细节
- **退化驱动的中间域构建（Degradation-based Intermediate Domain Construction）**：
  - 基于扩散前向过程定义：\( x_t = \sqrt{\bar{\alpha}_t} x_0 + \sqrt{1 - \bar{\alpha}_t} \epsilon, \epsilon \sim \mathcal{N}(0, I) \)。
  - 将不同时间步 \( t \) 对应的 \( x_t \) 视为中间域，其分布与源域和目标域分布的重叠逐渐增大。
  - 在训练中，随机采样 \( t \)，对源域和目标域图像同时施加相同退化，迫使编码器 \( g \) 保持稳定特征表示。

- **语义偏移补偿（Semantic Shift Compensation）**：
  - 引入额外训练扩散编码器 \( g' \) 和重建头 \( h' \)。
  - 时间嵌入模块（Transformer 正弦位置编码）将时间 \( t \) 编码为 shift 和 bias，调制 \( g' \) 的每层特征，使其感知退化程度。
  - 通过残差连接将 \( g' \) 的特征与主编码器 \( g \) 的特征融合，用重建损失 \( L_R = \| h' \circ (g + g')(x_t, t) - \epsilon \|_2^2 \) 监督，强制补偿语义偏移。
  - 引入退化图像一致性损失（DIC loss）\( L_D \)：对退化图像 \( x_{i,t} \) 使用融合网络 \( \bar{f}_\theta = h \circ (g + g') \) 预测分割图，并用交叉熵损失监督（源域用真值，目标域用伪标签）。

- **损失函数**：
  - 总体损失：\( L = L_S + L_T + \lambda_D L_D + \lambda_R L_R \)，其中 \( L_S \) 为源域监督损失，\( L_T \) 为目标域自训练适应损失。
  - 推理时仅使用 \( f_\theta = h \circ g \)，无需额外模块，无推理开销。

- **扩展到任意退化方式**：
  - 支持将加噪替换为模糊（Gaussian blur）或掩码（cowmask），只需修改前向过程和重建目标（直接预测干净图像 \( x_0 \)）。

## 3. 实验设计

### 数据集与场景
- **源域**：合成数据集 GTA5（24,966 张图像）和 SYNTHIA（9,400 张图像）。
- **目标域**：
  - Cityscapes（2,975 训练 / 500 验证，晴好天气）。
  - ACDC（1,600 训练 / 406 验证 / 2,000 测试，恶劣天气：雨、雪、雾、夜晚）。
- **评估指标**：逐类 IoU 和平均 mIoU。

### 基准方法与架构
- **架构**：DeepLabV2 + ResNet-101（CNN）、DAFormer + MiT-B5（Transformer）。
- **对比方法**：DAFormer、HRDA、MIC 三个主流 UDA 方法（均为 DAFormer 系列）。
- **对照**：与其他即插即用方法（FST、DiGA、DTS）比较。

### 训练细节
- 基于 MMSegmentation 框架，1-2 块 RTX-3090 (24GB) GPU，40K 迭代，batch size 2。
- 优化器：AdamW，学习率 \( 6 \times 10^{-5} \)（编码器）/ \( 6 \times 10^{-4} \)（解码器），权重衰减 0.01，线性 warm-up 1.5K 迭代。
- 教师网络 EMA 系数 0.999，扩散步数 \( T = 100 \)，sigmoid 噪声调度。
- 损失权重：\( \lambda_D = 0.5 \)，\( \lambda_R = 5 \)（DAFormer）/ 1（DeepLabV2）。

## 4. 资源与算力

- **明确说明**：所有实验在 1-2 块 RTX-3090 GPU（24GB 显存）上完成。
- **训练开销**：
  - DAFormer 基线：GPU 内存 9,807 MB，每迭代 1.32 秒，总训练 14.5 小时（40K 迭代）。
  - DAFormer + DiDA（完整版）：GPU 内存 15,856 MB，每迭代 1.64 秒，总训练 18.5 小时。
  - HRDA 和 MIC 类似，开销增加约 60-70% 显存，0.3-0.5 秒/迭代。
- **轻量变体**：DiDA(\( g_{\text{time}} \)) 可节省 15-20% 显存，性能接近完整版。

## 5. 实验数量与充分性

- **总实验组数**：超过 10 组主要实验，涵盖：
  - 三个 UDA 方法 × 三个数据集场景 × 两个骨干架构（CNN/Transformer），共约 9 组对比。
  - 消融实验：组件消融（表 2）、损失权重消融（表 7-9）、时间步数消融（表 9）、时间调度策略消融（表 10）。
  - 扩展版本实验：模糊/掩码退化（表 11-12）。
  - 对比其他即插即用方法（表 3-4）。
  - 可视化分析与诊断实验（图 4、图 7-12）。
- **充分性评价**：
  - 实验覆盖多数据集、多架构、多方法，跨多种域偏移场景（合成→真实、晴天→恶劣天气）。
  - 消融实验系统，验证各组件必要性。
  - 与最先进方法公平比较（同基线、同设置），并报告改进幅度。
  - **不足**：未报告误差棒或多次运行统计显著性，仅一次运行结果；计算资源有限但方法开销较大。

## 6. 主要结论与发现

- DiDA 在所有设置下稳定提升 UDA 分割性能，改进幅度 0.8%–3.7% mIoU，在大域间隙场景（如 Cityscapes → ACDC）提升更显著（+2.3%–3.7%）。
- 简单图像退化即可有效桥接域差异，扩散过程的时间步可编码语义偏移程度。
- 语义偏移补偿模块通过时间嵌入和重建损失能有效恢复退化导致的判别性信息丢失。
- DiDA 即插即用，推理时无额外开销，可扩展到任意退化类型（高斯噪声、模糊、掩码）。
- 新 SOTA：在 MIC 基线上达到 76.8 mIoU（GTA→Cityscapes），68.6 mIoU（SYNTHIA→Cityscapes），72.1 mIoU（Cityscapes→ACDC）。

## 7. 优点

- **方法创新性**：首次将图像退化作为域桥接先验，理论依据充分（扩散模型属性损失与时步关系），区别于传统数据增强或风格迁移方法。
- **通用性与灵活性**：即插即用，兼容多种 UDA 方法、骨干网络和退化类型，推理无额外成本。
- **实验设计全面**：覆盖主流 UDA 基准、多架构、多域场景，消融实验详细，与多个同类插拔方法比较并胜出。
- **理论分析深入**：从因果表示学习和扩散模型角度提供理论支撑，并定量验证退化程度与域对齐效果的相关性（附录 H）。
- **代码开源**：提供 GitHub 仓库，可复现。

## 8. 不足与局限

- **计算开销**：训练时显存增加 60-70%，时间增加 25-30%，对资源受限环境不够友好（虽提供轻量变体但仍有开销）。
- **超参数敏感**：DIC 损失权重 \( \lambda_D \) 在 0.5 附近需仔细调优，过大或过小均导致性能下降。
- **退化类型选择**：当前手动设计，未自动化选择最优退化组合，依赖经验。
- **实验统计**：未报告多次运行的标准差或置信区间，结果可靠性可能受单次随机性影响。
- **应用限制**：仅适用于语义分割任务，未验证在其他视觉任务（目标检测、实例分割）上的通用性；在极端退化程度下性能仍下降。
- **假设局限**：理论假设基于均匀分布和特定粒度假设，实际域偏移可能更复杂，模型对退化程度匹配有依赖性（推理时 t 需匹配退化程度）。

（完）
