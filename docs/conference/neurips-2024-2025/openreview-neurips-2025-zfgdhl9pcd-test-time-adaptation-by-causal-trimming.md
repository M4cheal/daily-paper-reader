---
title: Test-Time Adaptation by Causal Trimming
title_zh: 通过因果修剪进行测试时自适应
authors: "Yingnan Liu, Rui Qiao, Mong-Li Lee, Wynne Hsu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=zFGdHL9pcD"
tags: ["query:tta"]
score: 8.0
evidence: 测试时自适应的因果修剪理论
tldr: 测试时自适应旨在提升分布偏移下的鲁棒性。性能下降的主因是模型依赖非因果特征。本文提出因果修剪（TACT）方法，通过数据增强保留因果特征并变化非因果特征，利用主成分分析识别高方差方向并去除。基于因果视角提供了理论分析。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfgdhl9pcd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 423, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfgdhl9pcd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 356, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfgdhl9pcd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 1199, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfgdhl9pcd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfgdhl9pcd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 647, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfgdhl9pcd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 602, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfgdhl9pcd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfgdhl9pcd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1274, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfgdhl9pcd/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1375, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfgdhl9pcd/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfgdhl9pcd/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1360, \"height\": 131, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfgdhl9pcd/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 962, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfgdhl9pcd/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 687, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfgdhl9pcd/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1148, \"height\": 137, \"label\": \"Table\"}]"
motivation: 分布偏移下模型依赖非因果特征导致性能下降，需要识别并去除这些特征。
method: 通过数据增强保持因果特征、改变非因果特征，利用PCA识别高方差方向并修剪表征。
result: 在多个域偏移数据集上显著提升模型鲁棒性，并具有理论保证。
conclusion: TACT为测试时自适应提供了因果驱动的有效方法，揭示了特征选择的重要性。
---

## Abstract
Test-time adaptation aims to improve model robustness under distribution shifts by adapting models with access to unlabeled target samples. A primary cause of performance degradation under such shifts is the model’s reliance on features that lack a direct causal relationship with the prediction target. We introduce Test-time Adaptation by Causal Trimming (TACT), a method that identifies and removes non-causal components from representations for test distributions. TACT applies data augmentations that preserve causal features while varying non-causal ones. By analyzing the changes in the representations using Principal Component Analysis, TACT identifies the highest variance directions associated with non-causal features. It trims the representations by removing their projections on the identified directions, and uses the trimmed representations for the predictions. During adaptation, TACT continuously tracks and refines these directions to get a better estimate of non-causal features. We theoretically analyze the effectiveness of this approach and empirically validate TACT on real-world out-of-distribution benchmarks. TACT consistently outperforms state-of-the-art methods by a significant margin.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**：测试时自适应（Test-Time Adaptation, TTA）旨在利用未标注的目标样本来提升模型在分布偏移下的鲁棒性。已有 TTA 方法严重依赖模型自身的预测标签来指导适配过程，但预测标签可能受 **非因果特征**（即与预测目标没有直接因果关系的特征）影响而不可靠，导致次优适配结果。
- **整体含义**：本文提出 **因果修剪（Causal Trimming, TACT）**，通过识别并去除表征中的非因果成分，使模型在测试时能更依赖因果特征，从而提升分布偏移下的预测性能。理论分析与大量实验表明该方法有效且优于现有方法。

## 2. 论文提出的方法论

- **核心思想**：模型在训练中学到的表征同时包含因果和非因果特征。通过施加保持因果特征、改变非因果特征的数据增强，生成多个共享因果语义但非因果属性不同的样本，利用 PCA 分析这些表征的方差变化，识别出与 **非因果特征** 对齐的最大方差方向。
- **关键技术细节**：
  - **非因果特征识别**：对测试样本 \(x\) 生成 \(n\) 个增强样本，收集原始与增强样本的表征矩阵，计算协方差矩阵并做谱分解，得到主成分 \(\{e_i\}\)。认为方差最大的方向对应非因果特征的变化。
  - **因果修剪**：将测试样本表征 \(z\) 和各类原型 \(q_j\) 投影到前 \(m\) 个主成分上，然后减去这些投影分量，得到去除非因果成分的 \(\hat{z}\) 和 \(\hat{q}_j\)，即：
    \[
    \hat{z} = z - \sum_{i=1}^m (z \cdot e_i) e_i,\quad \hat{q}_j = q_j - \sum_{i=1}^m (q_j \cdot e_i) e_i.
    \]
  - **模型适配**：在测试过程中，对每批样本计算修剪后的原型并维护其移动平均，作为更鲁棒的类模板。预测时采用修剪后的表征 \(\hat{z}\) 与移动平均的修剪原型 \(\bar{\hat{q}}_j\) 的点积作为 logits。
- **理论分析**：提供了三个命题，分别给出 TACT 能纠正错误预测、保持正确预测以及不破坏已有正确预测的充分条件，揭示了修剪的主成分须主要包含非因果信息且因果信息保留足够的条件。

## 3. 实验设计

- **数据集**：五个真实世界分布偏移数据集，涵盖图像、音频、文本等多模态：
  - Birdcalls（音频，鸟类分类，宏 F1）
  - Camelyon17（医学图像，肿瘤分类，准确率）
  - CivilComments（文本，毒性分类，最差组准确率）
  - ImageNet-R（图像，200类，准确率）
  - ImageNet-V2（图像，1000类，准确率）
- **基准/对比方法**：
  - 无反向传播法：T3A、LAME、FOA
  - 基于反向传播法：SHOT、Tent、SAR、DeYO、TAST、TSD、PASLE
  - 本文还提出 TACT-adapt（以 TACT 预测为伪标签，结合交叉熵与信息最大化的梯度更新）。
- **实验设置**：
  - 骨干网络：ViT-B/32（图像），DistilBERT（文本）；验证了更大模型（ViT-B/16、BERT）。
  - 测试批次大小 64；超参数（增强数量 \(n\)、修剪主成分数 \(m\)）经网格搜索并通过 oracle 选择。
  - 全部实验均使用公开预训练模型或按标准流程训练，确保公平。

## 4. 资源与算力

- 论文在 Appendix D.3 明确说明：使用 NVIDIA V100 GPU（32GB 内存），批次大小为 64 时单 GPU 足够运行 TACT 及所有基线方法。未披露训练总工时，但指出 TACT 因需要计算增强样本的 PCA，在 Birdcalls 上的单次耗时约 112–323 秒（随增强数不同），内存占用约 1.8–5.4 GB，相比其他无反向传播方法（<1 GB，<17 秒）更高，但性能增益显著。

## 5. 实验数量与充分性

- **主要实验**：表 1 给出了五个数据集上的完整对比（10 次重复，其余 3 次重复），展示了均值与标准差。
- **消融实验**：表 2 分离了表征修剪、原型移动平均的影响，共 4 种配置；附录还包含增强策略对比（表 3）、更大模型实验（表 4）、与训练时增强的协同（表 5）、不同批次大小（表 6）、计算开销（表 7）、ICA 变体（表 8）、阈值修剪变体（表 9）。
- **可视化分析**：图 3、图 5 展示了 GradCAM 热力图，定性说明 TACT 减少对背景等非因果因素的关注。
- **充分性与公平性**：实验覆盖多模态、多类型偏移；所有基线按原文超参数空间搜索并采用 oracle 选择；统计误差报告完整。论文也讨论了分布偏移假设可能不成立时的局限性（如增强可能改变因果特征），因此实验设计较为全面客观。

## 6. 论文的主要结论与发现

- TACT 在所有五个数据集上均明显优于所有无反向传播基准方法，例如在 CivilComments 上提升 15% 最差组准确率，在 Birdcalls 上提升约 4% 宏 F1。
- TACT-adapt（结合梯度更新）进一步超越基于反向传播的 SOTA，说明 TACT 可作为更可靠的伪标签来源。
- 理论分析（命题 1–3）揭示了 TACT 能纠正错误预测并保持正确预测的条件，确认去除非因果信息是有效的。
- 消融研究证实，同时修剪表征和原型并保持原型移动平均可获得最佳性能。

## 7. 优点

- **创新性**：首次在 TTA 中明确基于因果视角主动去除非因果特征，而非仅依赖逐步弱化（如 DeYO）。
- **简洁高效**：核心操作（PCA+修剪）无需反向传播，计算成本虽略高但显著优于其他无反向传播方法。
- **理论扎实**：给出了清晰的假设与充分条件分析，为方法有效性提供了理论支撑。
- **广泛验证**：涵盖图像、音频、文本三种模态，并使用多种骨干网络（ViT、BERT），证明方法通用性。

## 8. 不足与局限

- **对先验知识的依赖**：需要领域知识来设计“保留因果、变化非因果”的数据增强，若增强不当（如改变因果特征）可能损害性能。论文建议可将增强作为超参数搜索。
- **PCA 的正交性限制**：假设非因果特征沿正交方向变化，但真实场景中因果与非因果可能非正交。论文在附录 F.1 尝试 ICA 但效果逊于 PCA。
- **计算开销**：对比其他无反向传播方法，TACT 因计算增强样本的 PCA 而需要更多 GPU 内存和时间，在资源极端受限场景下可能不适用。
- **仅评估了单一模型**：虽然使用了多种架构，但骨干网络均为 ViT 或 BERT，未涉及 CNN 等更传统结构（但推测通用性良好）。
- **未讨论持续适应场景**：论文仅在 i.i.d. 测试流上评估，未考虑测试分布随时间动态变化（如在线流数据）的情况。

（完）
