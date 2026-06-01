---
title: "Better to Teach than to Give: Domain Generalized Semantic Segmentation via Agent Queries with Diffusion Model Guidance"
title_zh: 教优于给：基于扩散模型引导的Agent查询实现域广义语义分割
authors: "Fan Li, Xuan Wang, Min Qi, Zhaoxiang Zhang, Yuelei Xu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=jvP1wbD0xh"
tags: ["query:ris"]
score: 8.0
evidence: 域广义语义分割，旨在泛化到未见数据集
tldr: 本文针对域广义语义分割任务，提出基于扩散模型引导的Agent查询学习框架。利用扩散模型生成场景分布的丰富先验，帮助模型在源域训练后泛化到未见目标域。实验表明该方法在多个跨域场景下有效，对指代分割的域泛化具有潜在价值。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jvp1wbd0xh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 808, \"height\": 1031, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jvp1wbd0xh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1509, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jvp1wbd0xh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 868, \"height\": 185, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jvp1wbd0xh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jvp1wbd0xh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 867, \"height\": 424, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1777, \"height\": 686, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 863, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 563, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 649, \"height\": 91, \"label\": \"Table\"}]"
motivation: 现有域广义分割方法难以捕捉场景分布，导致语义信息丢失。
method: 提出Agent查询驱动框架，利用扩散模型先验知识指导学习。
result: 在多个域泛化分割基准上取得先进性能。
conclusion: 展示了扩散模型在先验知识利用方面的优势。
---

## Abstract
Domain Generalized Semantic Segmentation (DGSS) trains a model on a labeled source domain to generalize to unseen target domains with consistent contextual distribution and varying visual appearance.
Most existing methods rely on domain randomization or data generation but struggle to capture the underlying scene distribution, resulting in the loss of useful semantic information. 
Inspired by the diffusion model's capability to generate diverse variations within a given scene context, we consider harnessing its rich prior knowledge of scene distribution to tackle the challenging DGSS task.
In this paper, we propose a novel agent \textbf{Query}-driven learning framework based on \textbf{Diff}usion model guidance for DGSS, named QueryDiff. 
Our recipe comprises three key ingredients: (1) generating agent queries from segmentation features to aggregate semantic information about instances within the scene; 
(2) learning the inherent semantic distribution of the scene through agent queries guided by diffusion features; 
(3) refining segmentation features using optimized agent queries for robust mask predictions.
Extensive experiments across various settings demonstrate that our method significantly outperforms previous state-of-the-art methods. 
Notably, it enhances the model's ability to generalize effectively to extreme domains, such as cubist art styles. Code is available at https://github.com/FanLiHub/QueryDiff.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义
- **研究动机**：Domain Generalized Semantic Segmentation (DGSS) 旨在利用带标注的源域训练模型，泛化到未见过的目标域（场景分布一致但视觉外观不同）。现有方法多依赖域随机化或数据生成，但难以捕捉底层场景分布（如实例间的空间关系和语义依赖），导致语义信息丢失，泛化能力有限。
- **核心问题**：扩散模型虽能生成高质量多样化样本，但直接将扩散特征用于分割任务面临两大挑战：(1) 迭代采样过程计算昂贵，不适于感知任务；(2) 扩散特征包含不必要的视觉细节（颜色、纹理），干扰分割。如何高效利用扩散模型中的场景分布先验来增强分割泛化成为关键。
- **整体含义**：提出“授人以渔”的思想——不直接使用扩散模型生成数据（give），而是通过 agent queries 作为接口，学习扩散特征中的场景分布知识（teach），从而提升分割模型的鲁棒性。

## 2. 方法论
### 核心思想
- 提出 **QueryDiff** 框架，基于 agent queries 与扩散模型引导，将高维场景分布知识注入分割模型。**三个关键步骤**：
  1. **生成 Agent Queries**：从分割骨干网络的多层特征中聚合实例级语义，通过渐进式合并形成统一的 agent queries。
  2. **扩散引导优化**：利用扩散特征的强弱噪声差异，通过扩散一致性损失（DCL）剥离视觉细节，使 agent queries 专注学习场景的语义分布。
  3. **特征细化与掩码预测**：用优化后的 agent queries 通过交叉注意力细化分割解码器特征，输出鲁棒预测。

### 关键技术细节
- **Agent Queries 生成**：
  - 对每一层特征 \( f^l_{seg} \)，通过可学习查询 \( q^l_{init} \) 与特征交互得到层查询 \( q^l_{layer} \)。
  - 采用渐进合并策略：通过交叉注意力（\( Q, K, V \)）将上一阶段输出逐步聚合成更少的查询，最终平均得到全局 agent queries \( q_{agent} \in \mathbb{R}^{r \times c} \)。
- **扩散特征提取**：
  - 使用预训练 Stable Diffusion 编码器得到潜变量 \( z_0 \)，加噪得 \( z_t \)。
  - 分别取弱噪声时间步 \( t_w \) 和强噪声时间步 \( t_s \)，通过噪声预测器得到两种扩散特征 \( f^{(t_w,j)}_d \) 和 \( f^{(t_s,j)}_d \)。弱噪声特征含细粒度视觉细节，强噪声特征保留粗粒度语义。
- **扩散一致性损失 (DCL)**：
  - 由两部分组成：
    - **\( \mathcal{L}_{sup} \)**：通过相似性图 \( S^{t_w}_j \) 将 agent queries 与弱噪声特征关联，再与强噪声特征重组得到 \( q_{opt} \)，用 Huber 损失监督 agent queries。
    - **\( \mathcal{L}_{dist} \)**：用重组后的特征 \( \hat{f}^j_d \) 与强噪声特征 \( f^{(t_s,j)}_d \) 计算 KL 散度，强制消除视觉细节。
  - 总损失 \( \mathcal{L}_{diff} = \mathcal{L}_{sup} + \mathcal{L}_{dist} \)。
- **特征细化**：优化后的 agent queries 与像素解码器的多尺度特征通过交叉注意力融合，再用深度可分离卷积和1×1卷积得到细化特征，输入 Transformer 解码器与掩码解码器，生成类概率与掩码。
- **完整目标**：\( \mathcal{L}_{total} = \mathcal{L}_{seg} + \alpha \mathcal{L}_{diff} \)，其中 \( \mathcal{L}_{seg} \) 包括二值交叉熵、Dice 损失和分类损失。

## 3. 实验设计
- **数据集与场景**：
  - **合成→真实**：GTA5 → Cityscapes, BDD100K, Mapillary。
  - **真实→真实**：Cityscapes → BDD100K, Mapillary。
  - **正常→恶劣**：Cityscapes → ACDC（Night, Snow, Rain, Fog）。
  - 所有数据集均为驾驶场景，共享19或20类。
- **基准与对比方法**：
  - 对比方法涵盖三类骨干：ResNet-based（WildNet, SHADE, SAW, DIDEX, BlindNet, FAMix）、Transformer-based（HRDA, HGFormer, DGInStyle）、VFM-based（CLOUDS, Rein）。共12种以上。
  - 使用同一骨干（ResNet50, MiT-B5, DINOv2-L）进行公平比较。
- **实现细节**：
  - 分割解码器基于 Mask2Former；优化器 AdamW；迭代60,000步；batch size 4；图像裁剪512×512；扩散模型为冻结的 Stable Diffusion v2-1。

## 4. 资源与算力
- **文中未明确说明使用的 GPU 型号、数量、训练时长等具体算力信息**。仅提到使用 AdamW 优化器，学习率设置（骨干1e-5，解码器和可学习查询1e-4），以及60,000次迭代（batch size 4）。训练效率未与基线比较。

## 5. 实验数量与充分性
- **实验组数**：共开展了大量实验，包括：
  - 主对比实验（表1, 2）：覆盖三种泛化设置×多种骨干。
  - 消融实验（表3）：组件消融（agent queries, \( \mathcal{L}_{sup}, \mathcal{L}_{dist} \)）。
  - 不同 VFM 测试（表4）：CLIP, SAM, DINOv2 在全微调、冻结、轻量微调下的对比。
  - 超参数分析：agent queries 长度 r（图5）、时间步 \( t_w, t_s \) 选择（表5）、不同 Stable Diffusion 版本（表6）。
  - 定性对比（图3, 4）：类 IoU 热力图、可视化结果。
- **充分性与公平性**：
  - 实验覆盖了三种主流骨干（ResNet, Transformer, VFM），三种泛化设置，多种数据集。
  - 消融实验系统，验证了每个组件的贡献。
  - 对比方法均来自近年顶级会议，复现条件一致，结果取3次平均，统计可靠。
  - 未发现明显不公平比较（如未采用更强骨干或额外数据）。

## 6. 主要结论与发现
- 提出的 QueryDiff 在几乎所有设置下显著超越现有 SOTA。
  - 在 G→C, B, M 上以 DINOv2-L 为骨干达到 **66.7% mIoU**，比 Rein 高 **2.4%**。
  - 在 Normal-to-adverse 上以 DINOv2-L 达到 **79.9% mIoU**，比 Rein 高 **2.3%**。
- 在极端域（如立体主义艺术风格）上展现优异泛化能力（图1a）。
- 组件消融表明 agent queries、\( \mathcal{L}_{sup} \)、\( \mathcal{L}_{dist} \) 均对性能有正向贡献，联合使用最佳。
- 方法对扩散模型版本不敏感（SD 1.4/1.5/2.1 性能接近），且在不同 VFM 上一致提升。

## 7. 优点
- **方法简洁高效**：推理时无需扩散模型，只依赖分割网络和 agent queries，无额外计算开销。
- **创新性强**：首次将 agent queries 作为接口来蒸馏扩散模型中的场景分布先验，而非直接使用扩散模型生成数据，符合“授人以渔”理念。
- **DCL 损失设计巧妙**：利用强弱噪声特征的差异消除视觉细节，使 agent queries 聚焦语义分布，提升泛化。
- **通用性好**：兼容多种骨干（ResNet, Transformer, VFM）和多种泛化场景（合成→真实、真实→真实、正常→恶劣）。
- **实验充分**：横跨三大设置、多个数据集、多种骨干，消融细致，结果可靠。
- **开源代码**：便于复现与后续研究。

## 8. 不足与局限
- **算力信息缺失**：未报告训练所需的 GPU 型号、数量、时长，难以评估资源开销。
- **场景覆盖有限**：仅评估了驾驶场景数据集（Cityscapes, GTA5, BDD, Mapillary, ACDC），未涉及室内、遥感、医学图像等其他领域，泛化性需进一步验证。
- **未见类或开放世界**：论文未讨论对未见类别或开放世界语义分割的泛化能力。
- **依赖预训练扩散模型**：虽然扩散模型在训练时被冻结，但仍需额外加载并提取特征，可能导致训练内存和速度开销。
- **效率指标缺失**：未报告模型参数量、推理速度（FPS）等，难以评估实际部署可行性。
- **极端域欠定量**：仅给出定性示例（立方体艺术风格），缺少定量对比，说服力稍弱。

（完）
