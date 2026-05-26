---
title: Test-Time Selective Adaptation for Uni-Modal Distribution Shift in Multi-Modal Data
title_zh: 多模态数据中单模态分布偏移的测试时选择性自适应
authors: "MingCai Chen, Baoming Zhang, Zongbo Han, Wenyu Jiang, Yanmeng Wang, Shuai Feng, Yuntao Du., Bingkun BAO"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6EZMWeV5sH"
tags: ["query:tta"]
score: 9.0
evidence: 多模态测试时自适应，含理论分析
tldr: 该论文聚焦于多模态数据中的单模态分布偏移这一实际场景，指出现有测试时自适应方法未考虑该问题。提出选择性测试时自适应方法，利用理论分析证明单模态偏移会阻碍多模态对齐，并通过实验验证方法在多种多模态任务上的有效性。贡献在于揭示了多模态TTA中一个被忽视的问题并给出解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6ezmwev5sh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 838, \"height\": 229, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ezmwev5sh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 839, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ezmwev5sh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 721, \"height\": 849, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ezmwev5sh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1670, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ezmwev5sh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 834, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ezmwev5sh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 893, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ezmwev5sh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1208, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ezmwev5sh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 702, \"height\": 389, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6ezmwev5sh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1626, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ezmwev5sh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1623, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ezmwev5sh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1622, \"height\": 579, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ezmwev5sh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 855, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ezmwev5sh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 852, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ezmwev5sh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 976, \"height\": 191, \"label\": \"Table\"}]"
motivation: 多模态测试时自适应中，不同模态偏移程度不同，现有方法未考虑单模态偏移场景。
method: 提出选择性自适应机制，仅对受偏移影响的模态进行适配，同时利用未偏移模态提供稳定信号。
result: 在视觉-语言等多模态任务上，该方法显著优于统一适配所有模态的基线。
conclusion: 单模态偏移是实际中常见的挑战，选择性适配是高效且鲁棒的多模态TTA策略。
---

## Abstract
Modern machine learning applications are characterized by the increasing size of deep models and the growing diversity of data modalities.  This trend underscores the importance of efficiently adapting pre-trained multi-modal models to the test distribution in real time, i.e., multi-modal test-time adaptation.  In practice, the magnitudes of multi-modal shifts vary because multiple data sources interact with the impact factor in diverse manners.  In this research, we investigate the the under-explored practical scenario *uni-modal distribution shift*, where the distribution shift influences only one modality, leaving the others unchanged. Through theoretical and empirical analyses, we demonstrate that the presence of such shift impedes multi-modal fusion and leads to the negative transfer phenomenon in existing test-time adaptation techniques.  To flexibly combat this unique shift, we propose a selective adaptation schema that incorporates multiple modality-specific adapters to accommodate potential shifts and a ``router'' module that determines which modality requires adaptation. Finally, we validate the effectiveness of our proposed method through extensive experimental evaluations.
Code available at https://github.com/chenmc1996/Uni-Modal-Distribution-Shift.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与研究动机
**背景**：实际多模态应用中，分布偏移常仅影响单一模态（如摄像头受光照影响而LiDAR不变），而现有测试时自适应（TTA）方法默认假设全局偏移，对所有模态统一调整，导致未偏移模态产生负迁移（negative transfer），性能反而下降。

**核心问题**：如何在未知哪一模态发生偏移的情况下，对多模态模型进行灵活、安全的测试时自适应，避免伤害未偏移模态的融合效果。

## 2. 方法论
**核心思想**：选择性自适应——仅对受偏移模态进行适配，保持未偏移模态不变。引入轻量级“路由器”自动判断偏移模态，并激活对应适配器。

**关键技术细节**：
- 为每个模态配备一个可学习适配器矩阵 Φ(v)、Φ(a)，以残差形式作用于特征：ˆz = z(Φ + I)。
- 路由器输出模态偏移信号量 S = [s(v), s(a)]，经Gumbel-Softmax得到选择权重 w，对原始特征与适配后特征做凸组合：˜z = w·z + (1−w)·ˆz。
- 遍历推理：测试时通过集成多个前向（分别激活不同适配器）选取最高置信度预测。
- 自训练目标：伪标签交叉熵损失（带置信度阈值）+ 平衡损失（负熵正则化）。

**流程**：
1. 编码器提取特征 → 2. 适配器与路由器生成选择后特征 → 3. 跨模态融合（自注意力） → 4. 分类 → 5. 自训练更新适配器与路由器。

## 3. 实验设计
**数据集**：Kinetics50（50类动作视频，29204个视频）和 VGGSound（309类音频事件，14046个视频）。两者均包含15种视频偏移（高斯噪声、散焦模糊等）和6种音频偏移（交通噪声、风声等）。

**基准**：对比方法包括单模态TTA方法（Tent、ETA、SAR）及多模态TTA方法（MM-TTA、READ），均使用CAV-MAE作为预训练骨干。

**对比方式**：报告在晚融合（LF）与注意力融合（AF）两种融合方式下的结果；所有方法使用相同骨干与预训练参数。

**实验覆盖**：共4个主要场景（Kinetics50视频偏移、Kinetics50音频偏移、VGGSound视频偏移、VGGSound音频偏移），每种场景包含多种具体偏移类型。此外包含消融实验、注意力图可视化、计算效率对比、超参数敏感性分析。

## 4. 资源与算力
论文明确说明：网络实现基于单张 GeForce RTX 3090 GPU，CPU为Intel Core i9-10900K @ 3.70GHz。**未报告训练总时长或GPU数量**。参数数量：我们的方法约1.18M可训练参数，少于READ（1.772M）但多于Tent（0.226M，但Tent在VGGSound上出现OOM）。时间成本：每epoch约36秒（Kinetics50）、192秒（VGGSound）。

## 5. 实验数量与充分性
**数量**：主实验表3张（每表涵盖约11-15种偏移） + 消融实验表1张 + 计算对比表1张 + 路由分布表1张 + 敏感性图3张 + 注意力热图1组。总计覆盖21种偏移类型、4个数据集-偏移组合。

**充分性**：实验设计相对充分，涵盖了多种偏移类型、两种融合架构、多个SOTA对比。消融验证了Gumbel-Softmax、遍历推理、选择性适配三组件的有效性。敏感性分析覆盖了批大小、温度、置信度阈值、损失系数。

**公平性**：所有方法使用相同骨干和预训练权重，超参数分开调优（但未说明调优方式是否一致）。报告5次随机种子均值。注意力图对比直观。

## 6. 主要结论
- 单模态偏移会导致跨模态注意力方差增大、融合效果下降，理论证明了该现象（Proposition 3.2）。
- 现有TTA方法（Tent、ETA、SAR）在未偏移模态上出现负迁移，性能低于预训练模型。
- 我们的选择性自适应方法在所有对比场景中均取得最佳平均精度（例如Kinetics50视频偏移平均64.5 vs READ 62.5；音频偏移平均71.5 vs READ 71.1）。
- 参数效率高，无OOM问题，注意力图显示模型更有效地重新分配跨模态关注。

## 7. 优点
- **问题新颖**：首次系统定义单模态分布偏移，并指出其与全局偏移的本质区别。
- **理论支撑**：提供注意力方差的分析证明，解释了偏移如何破坏跨模态融合。
- **方法简洁有效**：路由器+适配器设计轻量，端到端自训练，不需修改主干。
- **鲁棒性**：无需提前知道哪一模态偏移，路由器可自动学习。
- **计算友好**：参数少于READ，避免OOM（相较Tent）。

## 8. 不足与局限
- **实验覆盖**：仅使用两个数据集（Kinetics50和VGGSound），且均为视频-音频模态，未验证视频-文本、图像-文本等其他多模态组合。
- **应用限制**：假设仅单模态偏移，实际可能多模态同时受不同程度影响（该方法未直接处理）。
- **依赖假设**：理论分析假设加性噪声，实际偏移可能更复杂（如非线性扭曲）。
- **超参数敏感性**：批大小对性能影响较大（图5），实际部署需根据数据流调节。
- **测试效率**：遍历推理需多次前向，虽仅用于推理但增加延迟。
- **未讨论开放环境**：如出现未见类或概念偏移（open-world shift）时的表现。

（完）
