---
title: "PTTA: Purifying Malicious Samples for Test-Time Model Adaptation"
title_zh: PTTA：为测试时模型自适应净化恶意样本
authors: "Jing Ma, Hanlin Li, Xiang Xiang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=SznX4yic20"
tags: ["query:tta"]
score: 8.0
evidence: 通用TTA样本净化方法
tldr: 现有测试时自适应方法通常过滤恶意样本，造成数据浪费。本文提出PTTA，通过检索与恶意样本目标函数效果相反的良性样本进行Mixup，将恶意样本转化为良性样本，从而充分利用所有测试数据。该方法即插即用，在多个基准上提升了TTA性能，避免了数据浪费。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 824, \"height\": 702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 848, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 811, \"height\": 792, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1704, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 835, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1763, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1761, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 847, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1681, \"height\": 297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1738, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1604, \"height\": 2308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1718, \"height\": 1501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sznx4yic20/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1423, \"height\": 875, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 667, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1768, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 737, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1006, \"height\": 721, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 668, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 854, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 851, \"height\": 800, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 711, \"height\": 548, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 887, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 709, \"height\": 548, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1764, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1763, \"height\": 716, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1762, \"height\": 703, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1763, \"height\": 718, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1761, \"height\": 1408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1762, \"height\": 1103, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1760, \"height\": 1419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1760, \"height\": 1418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1765, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1768, \"height\": 619, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1760, \"height\": 984, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sznx4yic20/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1769, \"height\": 306, \"label\": \"Table\"}]"
motivation: 现有TTA方法过滤恶意样本导致测试数据浪费，因此研究如何转化恶意样本为良性。
method: 提出基于显著性指标的净化策略，检索良性样本与恶意样本进行Mixup。
result: 在多个TTA基准上验证了方法有效性，实现了性能提升和数据充分利用。
conclusion: PTTA即插即用，有效解决了TTA中恶意样本的利用问题。
---

## Abstract
Test-Time Adaptation (TTA) enables deep neural networks to adapt to arbitrary distributions during inference. Existing TTA algorithms generally tend to select benign samples that help achieve robust online prediction and stable self-training. Although malicious samples that would undermine the model's optimization should be filtered out, it also leads to a waste of test data. To alleviate this issue, we focus on how to make full use of the malicious test samples for TTA by transforming them into benign ones, and propose a plug-and-play method, PTTA. The core of our solution lies in the purification strategy, which retrieves benign samples having opposite effects on the objective function to perform Mixup with malicious samples, based on a saliency indicator for encoding benign and malicious data. This strategy results in effective utilization of the information in malicious samples and an improvement of the models' online test accuracy. In this way, we can directly apply the purification loss to existing TTA algorithms without the need to carefully adjust the sample selection threshold. Extensive experiments on four types of TTA tasks as well as classification, segmentation, and adversarial defense demonstrate the effectiveness of our method. Code is available at https://github.com/HAIV-Lab/PTTA.

---

## 论文详细总结（自动生成）

# 论文总结：PTTA：为测试时模型自适应净化恶意样本

## 1. 核心问题与研究动机
- **问题**：现有测试时自适应（TTA）方法通常通过样本选择过滤掉“恶意样本”（即对模型优化有害的样本），但这导致大量测试数据被浪费，且样本选择阈值高度敏感，轻微变化即可导致性能剧烈下降（如ViT-B/16上比例从60%调到70%时准确率下降36%）。
- **目标**：提出一种转化策略，将恶意样本净化为良性样本，从而充分利用所有测试数据，同时降低对阈值的手动调参依赖。

## 2. 方法论
- **核心思想**：利用Mixup将恶意样本与检索到的、对其目标函数影响相反的良性样本融合，生成净化样本用于模型训练。
- **关键技术**：
  - **显著性指标**：基于目标函数（如熵最小化）对样本的梯度，在logit、特征、像素三个层面计算，其中logit级别效果最佳且计算开销最低。
  - **良性样本检索**：通过余弦距离衡量显著性方向的对立性，在内存队列（FIFO，最大长度1000）或当前批次内检索与恶意样本贡献最相反的良性样本。
  - **Mixup净化**：将恶意样本与检索到的良性样本按系数λ=1/(K+1)线性插值（默认K=1），得到净化样本及其伪标签。
  - **损失函数**：在原TTA损失上添加净化损失L_pur（交叉熵），总损失 L_total = L_tta + α L_pur（α为超参数，样本选择方法默认α=3，无选择方法默认α=1）。
- **流程**：接收测试批次 → 分选良性/恶意样本 → 计算显著性指标 → 检索对立方 → Mixup生成净化样本 → 联合损失优化模型。

## 3. 实验设计
- **数据集与场景**：
  - 四个TTA任务：episodic、single、continual、lifelong（10轮共150种损坏）。
  - 主要数据集：ImageNet-C、CIFAR100-C、ImageNet及其变体（-A、-V2、-R、-Sketch）。
  - 额外任务：语义分割（CarlaTTA）、对抗防御（基于DIA攻击场景）。
- **对比方法**：Tent、CoTTA、SoTTA、SAR、ETA、EATA、DeYO、CPL等8种主流TTA方法，以及TPT（prompt tuning）和CLIP模型变体。PTTA作为即插即用模块加在每种方法上。
- **实现细节**：ResNet50、ViT-B/16、WRN-40、CLIP-RN50/ViT-B/16、DeepLab-V2等骨干网络。所有实验重复3个随机种子报告均值±标准差。

## 4. 资源与算力
- 论文未明确说明训练时间和具体GPU型号。但在附录C.4的“效率分析”中：
  - 硬件：Intel Xeon Silver 4210 CPU + NVIDIA GeForce RTX 3090 (24GB) + 256GB RAM。
  - 软件：PyTorch 1.9.0，CUDA 11.1。
  - PTTA版本比基础方法增加约10%~45%的运行时间（主要来源于额外前向/反向传播）。
  - 内存队列占用：存储1000个样本需约35MB（图像）+ 28KB（logit梯度）+ 28KB（预测概率）。

## 5. 实验数量与充分性
- **实验数量**：非常丰富，涵盖8类基线的所有TTA任务、2种骨干、4种目标函数（熵、一致性等）、3种显著性指标、3种检索方式、2种净化范围、2种数据增强对比等，总计超过30组对比表和消融图。
- **充分性**：
  - 每个实验均重复3次随机种子，报告均值±标准差，统计可靠。
  - 包含了全部15种损坏类型和5种自然分布偏移，覆盖corruption和自然分布偏移。
  - 消融实验全面：α、K、内存库大小、显著性等级、检索类型、净化范围、是否使用样本选择、对抗防御等。
  - 比较了FGSM、SOAP、扩散式DDA等现有净化方法，PTTA一致更优。
- **公平性**：对比方法使用其官方超参数，PTTA作为插件仅在原始方法上增加净化损失，不改变基线的选择阈值或结构，比较公平。

## 6. 主要结论
- PTTA可有效将恶意样本转化为良性，提升测试数据利用率，在几乎所有TTA方法上带来1~37%的准确率提升（尤其在ResNet50的continual任务中）。
- PTTA显著降低了对样本选择阈值的敏感性，使模型在不同比例下更稳定。
- PTTA即插即用，适用于多种网络架构（ResNet、ViT、CLIP）、多种目标函数（熵、一致性、prompt tuning）和多种任务（分类、分割、对抗防御）。
- Logit级别显著性指标在性能与效率之间取得最佳平衡。
- 当使用所有测试样本（无需样本选择）作为候选时，PTTA仍表现良好，进一步消除了阈值依赖。

## 7. 优点
- **创新性**：首次提出对TTA中恶意样本进行“净化”而非过滤，利用Mixup和显著性指标实现数据复用。
- **即插即用**：可直接融入现有TTA方法，无需重调阈值或改变训练流程。
- **鲁棒性强**：在不同损坏类型、不同骨干、不同任务上均稳定提升，且对超参数（如α、K、内存大小）不敏感。
- **实验全面**：覆盖4种TTA范式、多个数据集、多种骨干、消融实验细致，并扩展到分割和对抗防御，验证了通用性。

## 8. 不足与局限
- **计算开销**：PTTA需额外计算每个样本的梯度（至少1次前向和1次反向），运行时间增加10~45%，在资源受限场景下可能受限。
- **对显著性指标的依赖**：当分布偏移极为剧烈或模型完全失效时，logit梯度可能无法准确指示方向，影响检索质量。
- **Mixup假设**：假设两个样本线性插值可生成有效净化样本，但某些场景（如高度纹理化或结构敏感的任务）可能破坏语义。
- **未在更多模态验证**：仅限视觉任务（分类、分割），未扩展到NLP或跨模态。
- **未讨论记忆库陈旧问题**：在持续变化环境中，旧样本可能过时，但论文仅用FIFO简单丢弃，未设计淘汰策略。
- **未与在线自适应方法比较**：未与如MEMO（基于增强）或TTT（基于自监督）等非样本选择方法进行比较（但PTTA可加在这些方法上）。

（完）
