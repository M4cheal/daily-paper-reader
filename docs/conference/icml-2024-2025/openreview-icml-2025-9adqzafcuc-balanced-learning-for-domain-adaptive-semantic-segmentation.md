---
title: Balanced Learning for Domain Adaptive  Semantic Segmentation
title_zh: 域自适应语义分割的平衡学习
authors: "Wangkai Li, Rui Sun, Bohao Liao, Zhaoyang Li, Tianzhu Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=9ADQZAfcUC"
tags: ["query:ris"]
score: 5.0
evidence: 语义分割的无监督域适应方法处理域偏移
tldr: 无监督域适应语义分割中的类不平衡和分布偏移问题。BLDA通过分析预测logits分布识别过预测和欠预测类，并引入后处理对齐方法，无需先验知识即可缓解类别偏差。在多个域适应基准上取得显著提升，证明了平衡学习的重要性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-9adqzafcuc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9adqzafcuc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 851, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9adqzafcuc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 848, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9adqzafcuc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1736, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9adqzafcuc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9adqzafcuc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 836, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9adqzafcuc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1755, \"height\": 1709, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9adqzafcuc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1753, \"height\": 1706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9adqzafcuc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1692, \"height\": 2053, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9adqzafcuc/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1734, \"height\": 1747, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1758, \"height\": 644, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1681, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1758, \"height\": 417, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 742, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 288, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 332, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1642, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 289, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 313, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1635, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1601, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1631, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1315, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1745, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1740, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1824, \"height\": 1242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1652, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9adqzafcuc/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1426, \"height\": 532, \"label\": \"Table\"}]"
motivation: 现有自训练方法在域适应中因数据分布和标签空间的类不平衡导致类别学习不均衡。
method: 通过分析预测logits分布识别偏差类别，并采用后处理对齐logits分布。
result: 在多个域适应数据集上有效缓解类偏差，提升分割精度。
conclusion: 平衡学习策略无需先验知识即可提升域适应分割的公平性和性能。
---

## Abstract
Unsupervised domain adaptation (UDA) for semantic segmentation aims to transfer knowledge from a labeled source domain to an unlabeled target domain.
Despite the effectiveness of self-training techniques in UDA, they struggle to learn each class in a balanced manner due to inherent class imbalance and distribution shift in both data and label space between domains.
To address this issue, we propose Balanced Learning for Domain Adaptation (BLDA), a novel approach to directly assess and alleviate class bias without requiring prior knowledge about the distribution shift.
First, we identify over-predicted and under-predicted classes by analyzing the distribution of predicted logits.
Subsequently, we introduce a post-hoc approach to align the  logits distributions across different classes using shared anchor distributions.
To further consider the network's need to generate unbiased pseudo-labels during self-training, we estimate logits distributions online and incorporate logits correction terms into the loss function.
Moreover, we leverage the resulting cumulative density as domain-shared structural knowledge to connect the source and target domains.
Extensive experiments on two standard UDA semantic segmentation benchmarks demonstrate that BLDA consistently improves performance, especially for under-predicted classes, when integrated into various existing methods.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **研究问题**：无监督域适应（UDA）语义分割中，模型在目标域上存在严重的**类别不平衡学习**问题。即使采用自训练（self-training）范式，网络仍倾向于对部分类别（head classes）过度预测（over-prediction），而对另一些类别（tail/hard-to-transfer classes）欠预测（under-prediction），导致整体分割性能不均。
- **背景**：
  - 语义分割数据集固有类别分布不均衡（如Cityscapes中“道路”像素远多于“自行车”）。
  - 跨域场景下，源域与目标域的数据分布和标签分布均存在偏移，部分类别迁移难度大，进一步加剧预测偏差。
  - 现有重加权（re-weighting）和重采样（re-sampling）方法依赖“测试与训练数据同分布”的假设，在UDA中失效，且需要先验知识（如目标域类别先验），无法直接评估和缓解类别偏差。
- **动机**：直接从网络预测的**logits分布**出发，无需域分布先验，设计一种能在线感知模型学习状态、自适应的类别平衡学习策略。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 通过分析每个类别的**正logits分布**（该类像素被正确预测的logits）和**负logits分布**（该类像素被误判为其他类的logits）来评估类别偏差。
- 将各类的logits分布与一个**共享锚点分布**（anchor distribution）对齐，实现预测的类间平衡。
- 在训练过程中**在线估计logits分布**，并将校正项直接嵌入损失函数，实现自适应边界（adaptive margin）学习。
- 利用累积密度函数（CDF）作为**域共享的结构知识**，桥接源域和目标域，增强域适应。

### 关键技术细节

#### (1) 偏差评估（§3.3.2）
- 定义**logits集合矩阵** M：M_cl = {fθ(x)[l] | y=c}，对角线为某类正logits，非对角线为负logits。
- 偏差度量 Bias(l) = 平均预测概率偏离均匀分布1/C的程度。正偏差→过预测，负偏差→欠预测。
- 理论分析表明：各类正/负logits分布的差异导致预测偏差。

#### (2) 后处理类平衡（§3.3.3）
- 设定全局锚点分布：正锚点分布 P_p（全局所有正logits）、负锚点分布 P_n（全局所有负logits），从源域统计得到。
- 通过**累积分布函数（CDF）映射**将对数几率对齐：z' = F_p^{-1}(F_cl(z))（正类）或 F_n^{-1}(F_cl(z))（负类）。
- 为保留序结构，采用点对点映射。引入缩放因子 τ 控制平衡程度，以适配mIoU或mAcc指标。

#### (3) 在线logits调整（§3.3.4）
- 在训练过程中，分别对源域和目标域维护两组**高斯混合模型（GMM）**，各含C×C×K个高斯分量，模拟各类logits分布。
- 采用**动量式EM更新**：每个迭代利用当前批次logits初始化GMM参数，经T次EM循环后，以动量τ̃更新。
- 根据在线GMM计算logits校正偏移 Δ_cl(z)，将其引入交叉熵损失：
  - 源域监督损失、目标域自训练损失中的logit项减去 τ·Δ，等价于带有自适应边界的损失。
  - 效果：过预测类别的惩罚降低，欠预测类别的惩罚增大，实现类平衡学习。

#### (4) 累积密度桥接域（§3.3.5）
- 对每个像素，根据其真实/伪标签查询对应的**正累积密度值** d_ij = F_{c,c}(fθ(x)[c])，该值∈[0,1]，反映样本对该类的判别难度，且与图像风格无关（域不变）。
- 添加回归头 h_ϕ 预测该密度值，使用L2损失在源域和目标域上进行监督（目标域引入质量权重q(p_ij)）。
- 该辅助任务将两域连接，进一步促进域适应。

### 算法流程
- 每迭代：
  1. 前向计算源域和目标域logits，生成伪标签。
  2. 收集logits集合 M_S、M_T，采样N_sample个样本（≥N_min）。
  3. 动量EM更新源域GMM、目标域GMM、锚点GMM。
  4. 计算累积分布函数F及其逆，得到校正偏移Δ。
  5. 计算调整后的监督损失和自训练损失。
  6. 计算累积密度回归损失。
  7. 反向传播更新主网络参数。

## 3. 实验设计

### 数据集与Benchmark
- **源域**：GTA5（合成，24966张，1914×1052）、SYNTHIA（合成，9400张，1280×960）。
- **目标域**：Cityscapes（真实，2975/500训练/验证，1024×2048）。
- **标准UDA协议**：GTA5→Cityscapes 和 SYNTHIA→Cityscapes。

### 对比方法
- **Baseline方法**（4种自训练框架）：DAFormer、CDAC、HRDA、MIC（均以MiT-B5为骨干）；另验证CNN骨干：DACS、DAFormer(C)。
- **SOTA对比**：AdaptSegNet、CRST、PLCA、ProDA、CPSL、TransDA、ADFormer、DIGA、CoPT 等。

### 评估指标
- **mIoU**（主流指标，受类别分布影响）
- **mAcc**（平均准确率，类平衡指标）
- 同时报告各类别IoU/Acc的标准差，反映类别间均衡程度。

### 实验设置
- 训练迭代：40K（DACS为250K）。
- 批次大小：2。
- GPU：1或2块RTX-3090（24GB）。
- 优化器：AdamW，学习率6e-5（编码器）/6e-4（解码器），权重衰减0.01。
- 数据增强：512×512随机裁剪，线性学习率预热1.5K iter。
- EMA系数：0.999。
- 超参数：温度系数τ=0.1，累积密度损失权重λ=0.2，GMM分量数K=5，动量因子τ̃=0.99，EM循环T=3，最小样本数N_min=100。

## 4. 资源与算力

- **GPU型号**：NVIDIA RTX-3090（24GB）× 1或2张。
- **训练时间**：
  - DAFormer（40K iter）：14.5h → +BLDA后17.7h（每迭代增加约0.3s，总计多3.2h）。
  - DACS（250K iter）：35.5h → +BLDA后56.1h（增加较多，但DACS本身迭代多）。
  - CDAC（40K iter）：18.7h → +BLDA后22.3h。
- **显存开销**：
  - DAFormer：9807MB → +BLDA 12655MB（+2.8GB）。
  - DACS：11078MB → 14354MB（+3.3GB）。
  - CDAC：35443MB（不变，因重用已有缓存）。
- 论文**明确列出了GPU型号、训练时长、显存占用**，对算力分析充分。

## 5. 实验数量与充分性

### 实验组数
- **主实验**：2个标准基准（GTA5→CS、SYNTH→CS），每个基准测试了多个方法（Baseline+BLDA），覆盖CNN和Transformer骨干。
- **增加mAcc指标**：对GTA5→CS和SYNTH→CS均报告mAcc，并标注标准差。
- **消融实验**（以DAFormer为基础）：
  - 各组件贡献：Post-hoc、OLA_S（仅源域）、OLA、CDE等。
  - 超参数影响：τ、K、τ̃、T、λ 的网格搜索。
  - 锚点分布选择：源域/目标域、全局/特定类。
  - 与其他类不平衡方法对比（Focal Loss、CB Loss、重采样、Logit Adjustment等）。
- **扩展实验**：
  - 图像分类任务：VisDA-2017，以MIC+ResNet-101为基准。
  - 视频语义分割：VIPER→Cityscapes-Seq、VIPER→BDD。
- **可视化**：logits分布对比、分割结果定性对比。

### 充分性与公平性
- 实验覆盖了主流UDA框架（4个自训练方法）和两类骨干，结果一致提升。
- 对比方法均为近年SOTA，且BLDA作为插件无缝集成，保证了公平性。
- 消融实验设计全面，验证了每个模块的必要性。
- 在图像分类和视频分割上的拓展实验增加了泛化性证据。
- 论文公开了代码，可重复性高。

## 6. 主要结论与发现

1. **类别偏差在UDA中普遍存在**，且与源域类分布不完全相关，迁移难度差异是重要原因。
2. **通过logits分布可直接评估类别偏差**，无需域先验。
3. **BLDA嵌入任意自训练方法均可显著改善欠预测类别的性能**，降低类间标准差。
   - 在GTA5→CS上，MIC+BLDA的mIoU从75.9%提升至77.1%，mAcc从83.2%提升至86.3%，标准差从14.8降至13.5。
   - 在SYNTH→CS上，HRDA+BLDA mIoU从65.8%提升至67.9%。
4. **在线logits调整比后处理更有效**，因为它能在训练过程中持续平衡梯度信号。
5. **累积密度估计作为辅助任务**，提供域不变的结构信息，进一步缩小域间隙。

## 7. 优点

### 方法亮点
- **创新性**：首次从logits分布（正/负）角度系统分析UDA中的类别偏差，并提出无需域先验的解决方案。
- **通用性**：BLDA作为即插即用模块，可集成到多种自训练框架（Transformer/CNN），且在不同任务（分割、分类、视频）上均有效。
- **理论支撑**：从混淆矩阵扩展到logits集合矩阵，给出偏差的数学定义并与logits分布差异建立联系。
- **实现高效**：利用GMM并行更新、CDF多项式近似，额外计算成本合理（每迭代+0.3s，显存+~3GB）。

### 实验设计优点
- **双指标评估**（mIoU和mAcc）充分揭示类平衡性改善。
- **大量消融**：组件、超参数、锚点选择、与现有类不平衡方法对比，佐证方法优势。
- **跨任务验证**：扩展至图像分类和视频分割，增加结论可信度。

## 8. 不足与局限

1. **独立性假设**：在公式推导中假设各logits分布独立（P_cl独立），未建模类别间相关性（如易混淆的“摩托车”与“自行车”）。未来可引入相关性建模。
2. **对超参数τ敏感**：虽给出默认值0.1，但mIoU最优τ与mAcc最优τ不一致（mAcc需τ=1），需根据目标指标调参。
3. **仅考虑合成→真实场景**：未测试真实→真实（如Cityscapes→BDD）或白天→夜晚等更复杂域偏移。
4. **额外计算开销**：虽效率尚可，但对资源受限设备（如嵌入式）的部署可能仍有压力（特别是GMM的在线EM更新）。
5. **锚点分布依赖源域**：当源域与目标域分布差异极大时，源域全局锚点可能不完全合适（如目标域出现新风格），论文虽通过消融表明影响有限，但极端情况下可能欠佳。
6. **不适用于无伪标签的对抗训练范式**：方法依赖于自训练中的伪标签生成，与纯对抗训练方法不兼容。
7. **实验仅覆盖两个基准**，虽扩展至视频和分类，但对更多真实场景的普适性有待验证。

（完）
