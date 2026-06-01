---
title: Learning Frequency-Adapted Vision Foundation Model for Domain Generalized Semantic Segmentation
title_zh: 学习频率自适应视觉基础模型用于域广义语义分割
authors: "Qi Bi, Jingjun Yi, Hao Zheng, Haolan Zhan, Yawen Huang, Wei Ji, Yuexiang Li, Yefeng Zheng"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=b7hmPlOqr8"
tags: ["query:ris"]
score: 6.0
evidence: 频率适应方法处理域偏移，适用于RIS域偏移问题
tldr: 域广义语义分割面临跨域风格差异，本文提出频率自适应视觉基础模型，利用Haar小波变换解耦风格和内容信息，通过自适应频率调制提升域泛化能力。实验在多个城市场景分割数据集上证明，该方法有效缩小域间隙，为RIS中的域偏移问题提供了可迁移的解决方案。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-b7hmploqr8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1436, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-b7hmploqr8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-b7hmploqr8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 726, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-b7hmploqr8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 693, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-b7hmploqr8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 730, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-b7hmploqr8/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-b7hmploqr8/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-b7hmploqr8/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1414, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-b7hmploqr8/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1449, \"height\": 1851, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-b7hmploqr8/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 1856, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-b7hmploqr8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 653, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-b7hmploqr8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 872, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-b7hmploqr8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 756, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-b7hmploqr8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 569, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-b7hmploqr8/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 683, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-b7hmploqr8/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 683, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-b7hmploqr8/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1217, \"height\": 1169, \"label\": \"Table\"}]"
motivation: 域广义语义分割的关键瓶颈在于跨域风格差异导致域间隙。
method: 利用Haar小波变换将频率空间分解为低频内容和高频风格，自适应地调整频率成分以保持风格不变性。
result: 在多个域广义语义分割基准上取得领先性能。
conclusion: 频率自适应能有效提升视觉基础模型的跨域泛化能力。
---

## Abstract
The emerging vision foundation model (VFM) has inherited the ability to generalize to unseen images.
Nevertheless, the key challenge of domain-generalized semantic segmentation (DGSS) lies in the domain gap attributed to the cross-domain styles, i.e., the variance of urban landscape and environment dependencies.
Hence, maintaining the style-invariant property with varying domain styles becomes the key bottleneck in harnessing VFM for DGSS. 
The frequency space after Haar wavelet transformation provides a feasible way to decouple the style information from the domain-invariant content, since the content and style information are retained in the low- and high- frequency components of the space, respectively. 
To this end, we propose a novel Frequency-Adapted (FADA) learning scheme to advance the frontier.
Its overall idea is to separately tackle the content and style information by frequency tokens throughout the learning process.
Particularly, the proposed FADA consists of two branches, i.e., low- and high- frequency branches. The former one is able to stabilize the scene content, while the latter one learns the scene styles and eliminates its impact to DGSS. 
Experiments conducted on various DGSS settings show the state-of-the-art performance of our FADA and its versatility to a variety of VFMs.
Source code is available at \url{https://github.com/BiQiWHU/FADA}.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：域广义语义分割（DGSS）面临的核心挑战是训练集（源域）与未见测试集（目标域）之间因**跨域风格差异**（如城市景观、天气、光照条件等）导致的域间隙。虽然内容的语义类别（如行人、车辆）是共享的，但风格变化造成了特征分布偏移。
- **现有方法不足**：已有方法要么解耦风格（但弱化了内容表示），要么增强内容表示（但忽视风格不变性）。新兴的视觉基础模型（VFM）虽有强泛化能力，但在DGSS中**风格不变性**未被探索。
- **本文思路**：利用**Haar小波变换**将频率空间分解为低频（内容主导）和高频（风格主导）成分，分别处理以保持风格不变性，从而提出**频率自适应学习方案（FADA）**。

## 2. 方法论

### 核心思想
- 将VFM每层冻结后的特征通过**Haar小波变换**分解为四个分量：LL（低频）、LH、HL、HH（三个高频）。低频含内容信息，高频含风格信息。
- 设计**双分支结构**：
  - **低频分支**：利用可学习的低频Token捕捉稳定的场景内容。
  - **高频分支**：利用高频Token并通过**实例归一化（Instance Normalization）**抑制域特定风格，使特征对风格变化具有不变性。
- 整个过程遵循**低秩适应（LoRA）**范式，即Token矩阵由低秩分解（\(T_i = A_i B_i\)）实现参数高效微调。

### 关键技术细节（以第\(i\)层为例）
1. **频率分解**：
   \[
   f_i^{LL} = (W_i f_i) \otimes LL^T,\quad f_i^{LH}, f_i^{HL}, f_i^{HH} \text{ 类似}
   \]
   其中\(W_i f_i\)为冻结VFM输出，\(\otimes\)为小波卷积。

2. **低频适应**：
   - 计算相似度图：\(S_i^L = \text{Softmax}\left( \frac{f_i^{LL} \cdot (T_i^L)^T}{\sqrt{c}} \right)\)
   - 投影并融合：\(\tilde{f}_i^{LL} = f_i^{LL} + \left( f_i^{LL} + (S_i^L \times [T_i^L W_i^1 + b_i^1]) \right) W_i^2 + b_i^2\)

3. **高频适应**：
   - 对三个高频分量拼接后计算相似度图\(S_i^H\)
   - 对\(S_i^H\)施加**实例归一化**：\(\tilde{S}_i^H = (S_i^H - \mu)/\sigma\)
   - 投影并融合得到\(\tilde{f}_i^{LH}, \tilde{f}_i^{HL}, \tilde{f}_i^{HH}\)

4. **逆变换**：所有分量经逆Haar小波变换后输入下一层。

5. **损失函数**：直接继承Mask2Former的交叉熵、Dice和分类损失（参数\(\lambda_{ce}=5.0, \lambda_{dice}=5.0, \lambda_{cls}=2.0\)）。

## 3. 实验设计

### 数据集与场景
- **5个主流驾驶场景语义分割数据集**：CityScapes (C)、BDD-100K (B)、Mapillary (M)、SYNTHIA (S)、GTA5 (G)，共享19个语义类别。
- **三组跨域设置**：
  - GTA5 → CityScapes, BDD, Mapillary, SYNTHIA
  - SYNTHIA → CityScapes, BDD, Mapillary, GTA5
  - CityScapes → BDD, Mapillary, GTA5, SYNTHIA
- **额外测试**：ACDC数据集（含雾、夜、雨、雪四个不利条件）。
- **不同VFM泛化测试**：CLIP、SAM、EVA02、DINOv2。

### Benchmark与对比方法
- **ResNet基方法**：IBN、IW、DRPC、ISW、GTR、DIRL、SHADE、SAW、WildNet、AdvStyle、SPC等。
- **Mask2Former基方法**：HGFormer、CMFormer。
- **VFM基方法**：DIDEX、REIN（最强基线）。

### 评估指标
- **平均交并比（mIoU, %）**。

## 4. 资源与算力

- **论文未明确说明**使用的GPU型号、数量及具体训练时长。
- 仅提及：图像尺寸512×512，Adam优化器，初始学习率1e-4，训练20个epoch。默认使用DINOv2作为VFM。

## 5. 实验数量与充分性

- **大量实验**：
  - 三个主设置共12个目标域结果（表1）。
  - ACDC四个不利条件结果（表5）。
  - 四种不同VFM的泛化测试（表4）。
  - 消融实验：每个Haar分量影响（表2）、低秩维度r（表3）、Token长度m（附录图8）、频率适配器位置（附录表6）。
  - 可视化分析：特征相关性矩阵（图3）、t-SNE（图4）、实例归一化效果（图5）。
- **充分性评价**：实验设计全面，对比了多个SOTA方法（包括ResNet、Transformer、VFM三类），且消融验证了各组件有效性。采用三次独立重复取平均，结果可靠。整体实验客观、公平。

## 6. 主要结论与发现

- FADA在**所有12个跨域设置上均取得最优**，相比最强基线REIN平均提升约**1.5%~2.0% mIoU**（最高达2.9%）。
- 低频分支稳定内容表示，高频分支通过实例归一化有效抑制域特定风格，两者缺一不可。
- 方法**通用性强**：在CLIP、SAM、EVA02、DINOv2等多种VFM上均能取得一致提升。
- 在ACDC不利条件数据集上，FADA同样领先，尤其对雨、雪域提升显著（+2.5%、+2.9%）。
- 特征可视化证明FADA能缩小跨域特征分布差距，保持通道激活一致性。

## 7. 优点

1. **创新性**：首次将频率空间（Haar小波）与VFM低秩适应范式结合，为DGSS提供风格不变性新视角。
2. **通用性**：可即插即用于多种VFM，不改变其骨干结构，仅需额外小参数量（约6M可接受）。
3. **有效性**：多个大规模数据集、多种跨域设置的全面验证，且可视化分析支撑机理。
4. **简洁性**：双分支设计直观，高频分支利用实例归一化直接抑制风格，避免复杂对抗训练。
5. **开源**：代码已公开，便于复现及后续研究。

## 8. 不足与局限

1. **参数增加**：相比REIN，FADA约增加6M可训练参数（表4），虽可接受但仍有提升空间。
2. **计算资源未说明**：文中未报告GPU型号、数量、训练耗时等，不利于复现时的成本预估。
3. **依赖Haar小波**：方法有效性基于Haar小波能完美分离内容与风格的假设，但实际中高低频成分可能有重叠，极端场景（如剧烈光照变化）下分离效果可能下降。
4. **仅考虑驾驶场景**：实验仅在驾驶场景5个数据集进行，对室内、医学等其他领域泛化性未知。
5. **无消融损失函数项**：损失函数直接继承Mask2Former，未分析各损失项对泛化的贡献。
6. **理论分析较浅**：虽然附录有Haar小波理论证明，但对频率适应为何能提升泛化的理论解释不够深入。

（完）
