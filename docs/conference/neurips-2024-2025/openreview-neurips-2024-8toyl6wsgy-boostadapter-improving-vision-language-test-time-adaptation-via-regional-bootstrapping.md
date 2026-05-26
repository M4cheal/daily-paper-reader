---
title: "BoostAdapter: Improving Vision-Language Test-Time Adaptation via Regional Bootstrapping"
title_zh: BoostAdapter：通过区域引导提升视觉语言测试时自适应
authors: "Taolin Zhang, Jinpeng Wang, Hang Guo, Tao Dai, Bin Chen, Shu-Tao Xia"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=8tOYl6WsGY"
tags: ["query:tta"]
score: 9.0
evidence: 通过区域引导提升视觉语言模型的测试时自适应
tldr: 现有测试时自适应方法要么需要大量计算，要么忽略样本内信息。BoostAdapter 通过区域引导机制，结合轻量级记忆库，在无需额外标注的情况下，有效提升了视觉语言模型在下游任务上的泛化能力，在多个基准上取得领先结果。该方法为高效测试时自适应提供了新思路。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-8toyl6wsgy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1305, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8toyl6wsgy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 939, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8toyl6wsgy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1288, \"height\": 767, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8toyl6wsgy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8toyl6wsgy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 695, \"height\": 223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8toyl6wsgy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1426, \"height\": 373, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1311, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1374, \"height\": 555, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 725, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 676, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1376, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 702, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1119, \"height\": 789, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1439, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1448, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1439, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1437, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1440, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1446, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1447, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8toyl6wsgy/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1439, \"height\": 419, \"label\": \"Table\"}]"
motivation: 现有测试时自适应方法计算开销大或信息挖掘不足，需平衡效率与效果。
method: 提出区域引导引导框架，维护轻量级记忆库，结合训练需要和无训练方法的优势。
result: 在多个视觉语言下游任务上超越现有方法，同时降低计算开销。
conclusion: 区域引导机制有效桥接了不同测试时自适应范式，提升了视觉语言模型的泛化性能。
---

## Abstract
Adaptation of 
pretrained vision-language models such as CLIP to various downstream tasks have raised great interest in recent researches. 
Previous works have proposed a variety of test-time adaptation (TTA) methods to achieve strong generalization without any knowledge of the target domain. 
However, existing training-required TTA approaches like TPT necessitate entropy minimization that involves large computational overhead, while training-free methods like TDA overlook the potential for information mining from the test samples themselves.
In this paper, we break down the design of existing popular training-required and training-free TTA methods and bridge the gap between them within our framework.
Specifically, we maintain a light-weight key-value memory for feature retrieval from  instance-agnostic historical samples and instance-aware boosting samples. 
The historical samples are filtered from the testing data stream and serve to extract useful information from the target distribution, while the boosting samples are drawn from regional bootstrapping and capture the knowledge of the test sample itself.
We theoretically justify the rationality behind our method and empirically verify its effectiveness on both the out-of-distribution and the cross-domain datasets, showcasing its applicability in  real-world situations.

---

## 论文详细总结（自动生成）

# BoostAdapter：通过区域引导提升视觉语言测试时自适应

## 1. 核心问题与整体含义（研究动机和背景）

视觉语言模型（如CLIP）在零样本任务中表现出色，但在测试时面临域偏移问题。现有的测试时自适应方法分为两类：

- **需要训练的方法**（如TPT）：通过熵最小化等自监督目标优化模型参数或可学习提示，但计算开销大（需梯度下降）。
- **免训练的方法**（如TDA）：利用记忆网络或缓存存储历史样本，通过特征检索调整预测，但忽略了测试样本自身的细粒度信息。

两类方法各有优劣且缺乏统一理解。本文旨在弥合这一鸿沟，结合两者的优势，提出一种既高效又能挖掘测试样本自身信息的新型自适应框架。

## 2. 方法论

### 核心思想
- 将测试样本的增强视图视为一种“区域引导分布”（boosting distribution）。通过互信息过滤低熵的高质量增强样本，得到“引导样本”。
- 理论证明：对引导样本进行熵最小化等价于从包含这些样本的缓存中进行特征检索（Proposition 1）。
- 基于此，提出 **BoostAdapter**：维护一个轻量级键值记忆库（cache），其中包含：
  - **实例无关的历史样本**：从测试数据流中按熵阈值过滤得到的可靠样本。
  - **实例相关的引导样本**：对当前测试样本进行随机裁剪和水平翻转并过滤得到。
- 采用类似Tip-Adapter的特征检索公式进行预测：
  \[
  p_{\text{boost}}(x) = A\left( g(x) \tilde{G}_{\text{cache}}^\top \right) \tilde{Y}
  \]
  其中 \(A\) 为缩放函数，\(\tilde{G}_{\text{cache}}\) 为历史样本和引导样本的特征组合，\(\tilde{Y}\) 为对应的伪标签。

### 关键技术细节
- 伪标签通过argmax生成，并用熵阈值过滤不可靠样本。
- 动态调整每个样本的熵阈值（固定百分位数 \(p=0.1\)）。
- 缓存容量按类别设置最大shot数（如3），低熵样本可替换旧样本。
- 理论分析（Proposition 2, 3）表明：引入引导样本可进一步降低经验误差，当引导分布更接近测试样本时效果更明显。

## 3. 实验设计

### 数据集与场景
- **OOD基准**：4个ImageNet变体（ImageNet-V2、Sketch、A、R），测试对自然分布偏移的鲁棒性。
- **跨域基准**：11个数据集（Caltech101、Pets、Cars、Flowers、Food101、Aircraft、SUN397、DTD、EuroSAT、UCF101），测试迁移能力。
- **附加基准**：ImageNet-C（15种常见损坏，最高严重等级5）。

### 对比方法
- 需要训练的方法：CLIP+TPT、CoOp、CoOp+TPT、CoCoOp、CoCoOp+TPT、MaPLe、MaPLe+TPT、PromptAlign、DiffTPT。
- 免训练的方法：TDA。
- 另外对比了与TSD、DEYO等方法的融合。

### 评估指标
- 报告Top-1准确率及误差界（±0.12～±0.17）。

## 4. 资源与算力

- **GPU**：单张Nvidia 3090 24GB GPU。
- **推理速度**：BoostAdapter为11.23 fps（TDA为11.89 fps），内存占用1.2 GB（与TDA相同）。
- 训练需要的方法（如TPT）则慢得多（0.29 fps，内存4.5 GB）。文中未报告具体训练时长。

## 5. 实验数量与充分性

- **主实验**：OOD 4个数据集 + 跨域11个数据集（结果在表1、2）。
- **附加实验**：
  - ImageNet-C（15种损坏，表6）。
  - 不同backbone（RN-50，表4、5）。
  - 消融实验：历史样本 vs 引导样本、增强视图数量、shot容量、不同增强方法、独立缓存（表3、10、11、12、13、14、15、16、17、18）。
  - 与训练需要方法融合（TSD、DEYO）（表8）。
  - 定性结果（图5、6）。
- **充分性**：实验覆盖了主流benchmark，消融完整，公平性良好（报告误差界并与现有方法复现结果对比）。

## 6. 主要结论与发现

- BoostAdapter在OOD基准上平均准确率65.57%，比最强基线TDA（63.89%）高1.68%；在跨域基准上平均68.68%，比TDA（67.53%）高1.15%。
- 在ImageNet-A上提升最显著（+4.42%），说明引导样本在缺乏可靠历史样本时特别有效。
- 理论分析证实历史缓存和引导样本均能降低经验风险。
- 消融实验表明：结合历史样本和引导样本优于单独使用任何一种；随机水平翻转是最佳增强；shot容量3左右最佳。

## 7. 优点

- **方法创新**：首次在理论上连接了需要训练和免训练TTA方法，并据此提出统一框架。
- **效率优异**：免训练，推理速度接近TDA，远快于TPT等需要梯度下降的方法。
- **理论保障**：提供了详细的误差界分析（附录C）。
- **实验全面**：覆盖多种基准、消融、不同backbone、与其他方法融合。
- **代码开源**（将在接受后公开）。

## 8. 不足与局限

- 需要生成多个增强视图（64个）并过滤，增加了计算开销（对比TDA fps稍低）。
- 对增强策略的依赖：实验仅测试了随机裁剪+水平翻转，其他增强（如亮度、旋转）效果较差。
- backbone种类有限：仅测试ViT-B/16和RN-50，未扩展到更大模型（如ViT-L）或视觉语言模型的其他变体。
- 仅关注分类任务，未验证在检测、分割等任务上的有效性。
- 伪标签噪声：尽管引入熵过滤，但在高难度域（如ImageNet-A）仍有噪声影响。
- 缓存容量假设固定shot数，实际最优容量可能随数据分布变化，需要调参。

（完）
