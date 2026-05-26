---
title: "TinyTTA: Efficient Test-time Adaptation via Early-exit Ensembles on Edge Devices"
title_zh: TinyTTA：基于早期退出集成的边缘设备高效测试时自适应
authors: "Hong Jia, Young D. Kwon, Alessio Orsino, Ting Dang, Domenico Talia, Cecilia Mascolo"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=XIcBCBe6C3"
tags: ["query:tta"]
score: 8.0
evidence: 针对边缘设备流式数据的高效测试时自适应
tldr: TinyTTA针对物联网设备在资源受限环境下模型难以持续适应数据分布漂移的问题，提出了一种基于早期退出集成的测试时自适应方法。该方法通过轻量级分类器在边缘设备上实现高效推理和快速自适应，在保持低延迟的同时显著提升了模型的鲁棒性，为资源约束下的实时自适应提供了可行方案。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1466, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 584, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1434, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1448, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1457, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 575, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 507, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1446, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1416, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xicbcbe6c3/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1420, \"height\": 336, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-xicbcbe6c3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 659, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xicbcbe6c3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 880, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xicbcbe6c3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 550, \"label\": \"Table\"}]"
motivation: 物联网设备面临数据分布漂移，但现有测试时自适应方法未在资源受限硬件上验证。
method: 提出早期退出集成策略，在推理过程中动态选择退出点，结合轻量分类器实现高效自适应。
result: 在边缘设备上实验表明，该方法在保持低能耗的同时显著提升了模型在分布漂移下的准确率。
conclusion: TinyTTA证明了测试时自适应在资源受限边缘设备上的可行性和有效性。
---

## Abstract
The increased adoption of Internet of Things (IoT) devices has led to the generation of large data streams with applications in healthcare, sustainability, and robotics. In some cases, deep neural networks have been deployed directly on these resource-constrained units to limit communication overhead, increase efficiency and privacy, and enable real-time applications. However, a common challenge in this setting is the continuous adaptation of models necessary to accommodate changing environments, i.e., data distribution shifts. Test-time adaptation (TTA) has emerged as one potential solution, but its validity has yet to be explored in resource-constrained hardware settings, such as those involving microcontroller units (MCUs). TTA on constrained devices generally suffers from i) memory overhead due to the full backpropagation of a large pre-trained network, ii) lack of support for normalization layers on MCUs, and iii) either memory exhaustion with large batch sizes required for updating or poor performance with small batch sizes. In this paper, we propose TinyTTA, to enable, for the first time, efficient TTA on constrained devices with limited memory. To address the limited memory constraints, we introduce a novel self-ensemble and batch-agnostic early-exit strategy for TTA, which enables continuous adaptation with small batch sizes for reduced memory usage, handles distribution shifts, and improves latency efficiency. Moreover, we develop the TinyTTA Engine, a first-of-its-kind MCU library that enables on-device TTA. We validate TinyTTA on a Raspberry Pi Zero 2W and an STM32H747 MCU. Experimental results demonstrate that TinyTTA improves TTA accuracy by up to 57.6\%, reduces memory usage by up to six times, and achieves faster and more energy-efficient TTA. Notably, TinyTTA is the only framework able to run TTA on MCU STM32H747 with a 512 KB memory constraint while maintaining high performance.

---

## 论文详细总结（自动生成）

# 中文总结：TinyTTA: Efficient Test-time Adaptation via Early-exit Ensembles on Edge Devices

## 1. 论文的核心问题与整体含义（研究动机和背景）
物联网（IoT）设备（如微控制器 MCU）上部署深度神经网络时，面临数据分布漂移（如传感器噪声、天气变化等）导致的性能下降问题。传统测试时自适应（TTA）方法通常需要全模型反向传播或依赖归一化层，这在资源受限的 MCU（如 512 KB SRAM）上不可行，主要因为：① 存储激活值带来的内存开销；② MCU 缺乏归一化层支持；③ 大 batch 导致内存耗尽，小 batch 又导致性能崩溃。论文首次提出 **TinyTTA**，旨在在内存极有限的边缘设备上实现高效、准确的 TTA。

## 2. 论文提出的方法论：核心思想、关键技术细节
**核心思想**：通过自集成（self-ensemble）与早退（early-exit）策略，将预训练网络划分为多个子模块，每个子模块附加轻量分类器（exit heads），并根据预测置信度动态选择退出点，仅对退出前的子模块进行更新，从而大幅减少内存占用并适应不同强度的分布漂移。

**关键技术细节**：
- **自集成网络**：根据逐层激活内存相似性，将网络划分为若干子模块（如 ResNet50 分为 4 组），每个子模块近似全模型能力，但训练时冻结子模块参数，只更新退出分类器。
- **早退机制**：对每个样本，依次通过子模块并计算熵（置信度）。若熵低于阈值 γ，则提前退出，仅更新前序子模块的退出头；否则继续向后传递。这适配了混合分布漂移（轻度漂移早退，重度漂移深处理）。
- **权重标准化（WS）**：替代传统批归一化、组归一化，运用于每个退出头的 CNN 层。WS 仅基于权重计算均值/标准差，与 batch 无关，避免了 MCU 上归一化层不支持的问题，且对小 batch 稳定。
- **TinyTTA Engine**：基于 TensorFlow Lite Micro（TFLM）扩展了反向传播算子（Conv、ReLU、Softmax 等），实现了 MCU 上的 on-device TTA，采用层级更新与动态内存分配进一步减少 SRAM 占用。

**训练阶段**（离线）：使用源数据同时训练子模块与退出头，损失包含交叉熵 L1 和特征对齐 L2（让子模块输出接近原始网络对应层输出）。λ 平衡两项。

**推理/自适应阶段**：在线单样本依次通过子模块，基于熵决策是否早退，更新对应退出头（WS 层 + 线性层），其余网络冻结。

## 3. 实验设计
- **数据集**：四个分布漂移数据集：CIFAR10-C、CIFAR100-C（15 种 corruption，5 级严重度）、OfficeHome（4 个域）、PACS（4 个域）。另附加音频实验（Musan Keywords Spotting）。
- **边缘设备**：MPU 类：Raspberry Pi Zero 2W（512 MB DRAM）；MCU 类：STM32H747（512 KB SRAM）。
- **模型**：MCUNet、EfficientNet-b1、MobileNetV2_×05、RegNet-200m（均为移动端轻量模型）。
- **对比基线**：TENT（调制/微调）、CoTTA、EATA、EcoTTA，以及非 TTA 方法（TTT，仅微调偏置）。
- **评测指标**：准确率、内存（SRAM/Flash）、延迟、能耗。

## 4. 资源与算力
论文未明确说明完整训练所需的 GPU 型号、数量及训练时长。仅提及自集成训练在 “Linux server with Intel Xeon Gold 5218 CPU @ 2.30GHz and NVIDIA Quadro RTX 6000 GPU” 上完成。部署测试则在 Raspberry Pi Zero 2W 和 STM32H747 MCU 上进行。因此，算力细节不完整。

## 5. 实验数量与充分性
- 主要实验：在 4 个数据集 × 4 种模型 × 8 种方法（含基线）上进行对比，覆盖了 MPU 和 MCU 场景。
- 消融实验：分别移除 WS、早退、自集成，验证各组件贡献；比较 WS vs GN；比较早退 vs 全模型微调；比较不同熵阈值；比较不同分布漂移严重度（L1~L5）。
- 额外实验：音频数据（MicroNets + Musan 噪声）验证模态泛化；MCU 上对比 TinyTTA vs 推理-only；与 TinyEngine（现有 MCU 训练框架）对比。
- **充分性评估**：实验覆盖充分，对比了当前主流 TTA 方法，且考虑了不同 batch size（重点 batch=1 场景）。消融实验清晰证明了各组件必要性。但缺少统计显著性检验（如误差条、置信区间）的详细报告，仅部分提及“三个独立随机种子均值”。

## 6. 论文的主要结论与发现
- TinyTTA 在 MCU（STM32H747，512 KB SRAM）上**首次实现 TTA**，精度比不适应提升约 4%，且延迟更低（50.7 ms vs 55.8 ms）。
- 在 MPU 上，TinyTTA 相比其他 TTA 方法：准确率最高提升 **57.6%**，内存减少 **6 倍**，延迟和能耗最低。
- 早退机制有效应对混合分布漂移：轻度漂移早退节省计算，重度漂移深处理避免模型崩溃。
- WS 替代归一化层使得小 batch（batch=1）下自适应稳定，优于 GN、BN。
- TinyTTA Engine 使 MCU 上 TTA 可行，额外存储开销仅 40.2 KB SRAM + 85.1 KB Flash。

## 7. 优点
- **创新性**：首次将早退集成用于边缘 TTA，巧妙结合自集成、早退、WS，克服 MCU 内存与归一化限制。
- **实用性**：提供完整 MCU 库 TinyTTA Engine，基于 TFLM 扩展反向传播，代码开源，可直接部署。
- **效率优异**：在极低内存（512 KB）下仍能运行，且延迟、能耗均优于现有方法。
- **泛化性**：不仅验证图像数据，还在音频数据上表现良好；支持多种轻量网络结构。
- **设计合理**：自集成利用相邻层内存相似性分组，早退基于熵阈值动态决策，WS 保证 batch-agnostic，三者协同。

## 8. 不足与局限
- **实验覆盖局限**：仅测试了单一 MCU（STM32H747）和单一 MPU（Raspberry Pi Zero 2W），未在其他常见 MCU（如 Arduino、ESP32）上验证。
- **数据模态单一**：除附录中的音频实验外，主要基于图像数据，未涉及时序（如 IMU）或多模态数据。
- **需要重新训练**：自集成训练需离线使用源数据重新训练模型，无法直接应用到任意预训练模型（需微调）。
- **熵阈值选择**：早退阈值 γ 需针对模型和数据集调优（附录给出网格搜索结果），可能存在泛化开销。
- **统计严谨性不足**：未报告误差条、置信区间，多个实验仅展示均值，缺乏对随机波动影响的量化分析。
- **与 TinyEngine 对比不完全公平**：TinyEngine 原本针对有标签训练，论文将其与 TENT 结合作为对比，而非其原生 TTA 能力。

（完）
