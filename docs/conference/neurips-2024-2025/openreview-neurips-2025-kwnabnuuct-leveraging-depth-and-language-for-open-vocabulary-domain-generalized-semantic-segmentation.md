---
title: Leveraging Depth and Language for Open-Vocabulary Domain-Generalized Semantic Segmentation
title_zh: 利用深度和语言进行开放词汇域泛化语义分割
authors: "Siyu Chen, Ting Han, Chengzheng Fu, Changshe Zhang, Chaolei Wang, Jinhe Su, Guorong Cai, Meiliu Wu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=KWNabnuuct"
tags: ["query:ris"]
score: 7.0
evidence: 利用深度和语言实现语义分割域泛化，可迁移至指代分割的域迁移场景
tldr: 本文针对开放词汇语义分割与域泛化未统一的问题，提出Vireo，首个单阶段开放词汇域泛化语义分割框架，通过冻结视觉基础模型并引入深度VFM提取域不变结构特征，结合语言实现未见类别和未见域的鲁棒分割，为通用分割提供新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwnabnuuct/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwnabnuuct/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 1067, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwnabnuuct/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwnabnuuct/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1426, \"height\": 808, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwnabnuuct/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwnabnuuct/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 372, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwnabnuuct/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 705, \"height\": 407, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwnabnuuct/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 524, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwnabnuuct/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwnabnuuct/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwnabnuuct/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 717, \"height\": 626, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwnabnuuct/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 719, \"height\": 627, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwnabnuuct/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 704, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwnabnuuct/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 703, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwnabnuuct/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 698, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwnabnuuct/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 705, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwnabnuuct/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 704, \"height\": 303, \"label\": \"Table\"}]"
motivation: 开放词汇语义分割和域泛化互补但尚未统一，实际应用需同时处理未见类别和域变化。
method: 冻结视觉基础模型，通过深度VFM提取域不变结构特征，并结合语言实现开放词汇预测。
result: 在多个域泛化基准上达到领先性能。
conclusion: 首次统一开放词汇与域泛化，为通用分割提供新方向。
---

## Abstract
Open-Vocabulary semantic segmentation (OVSS) and domain generalization in semantic segmentation (DGSS) highlight a subtle complementarity that motivates Open-Vocabulary Domain-Generalized Semantic Segmentation (OV-DGSS). OV-DGSS aims to generate pixel-level masks for unseen categories while maintaining robustness across unseen domains, a critical capability for real-world scenarios such as autonomous driving in adverse conditions. We introduce Vireo, a novel single-stage framework for OV-DGSS that unifies the strengths of OVSS and DGSS for the first time. Vireo builds upon the frozen Visual Foundation Models (VFMs) and incorporates scene geometry via Depth VFMs to extract domain-invariant structural features. To bridge the gap between visual and textual modalities under domain shift, we propose three key components: (1) GeoText Query, which align geometric features with language cues and progressively refine VFM encoder representations; (2) Coarse Mask Prior Embedding (CMPE) for enhancing gradient flow for faster convergence and stronger textual influence; and (3) the Domain-Open-Vocabulary Vector Embedding Head (DOV-VEH), which fuses refined structural and semantic features for robust prediction. Comprehensive evaluation on these components demonstrates the effectiveness of our designs. Our proposed Vireo achieves the state-of-the-art performance and surpasses existing methods by a large margin in both domain generalization and open-vocabulary recognition, offering a unified and scalable solution for robust visual understanding in diverse and dynamic environments. Code is available at https://github.com/SY-Ch/Vireo.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

*   **研究问题**：开放词汇语义分割（OVSS，能分割任意文本描述的类别）和域泛化语义分割（DGSS，在未见过的环境/域中保持鲁棒）是两项互补但尚未统一的任务。实际场景（如自动驾驶在恶劣天气中）需要模型同时满足这两点：识别未见类别并适应域变化。
*   **现有挑战**：① 文本-视觉对齐模块在域偏移下性能骤降；② 域不变策略可能抑制细粒度语义，影响精确响应文本查询。
*   **论文目标**：首次提出单阶段统一框架 Vireo，同时实现开放词汇识别和域泛化分割，为通用视觉理解提供可扩展方案。

## 2. 论文提出的方法论

### 核心思想
*   冻结视觉基础模型（VFM）和深度基础模型（DepthAnything V2），保留其强大的跨域泛化能力；通过可训练的轻量模块注入几何与文本线索，在编码器内部渐进式优化特征，实现语义与结构的深度融合。

### 关键技术细节（三个组件）
1.  **GeoText Query（几何文本查询）**
    *   在VFM的多个中间层插入可学习的查询向量，该向量先与预计算的CLIP文本嵌入融合，再通过交叉注意力机制同时关注RGB视觉特征和深度特征（来自DepthAnything）。
    *   输出通过残差连接逐步精炼原始VFM特征，使语义和几何信息跨层传递。
2.  **Coarse Mask Prior Embedding（CMPE，粗掩码先验嵌入）**
    *   选取VFM多个中间层（第8、12、16、24层）的精炼特征，上采样后经自适应注意力门控（AAG）融合，得到全局粗特征。
    *   该粗特征与文本嵌入点乘生成粗语义概率图，通过分割损失提供密集梯度信号，加速训练收敛并增强文本先验的影响力。
3.  **Domain-Open-Vocabulary Vector Embedding Head（DOV-VEH，域开放词汇向量嵌入头）**
    *   像素解码器处理多尺度精炼特征，得到空间增强特征。
    *   变换解码器以GeoText Query作为可学习查询，与像素特征交叉注意力，输出掩码嵌入和分类嵌入。
    *   最终预测通过Einstein求和（点乘）组合掩码嵌入与分类嵌入生成。

### 算法流程（文字描述）
1.  输入RGB图像 I 和文本标签 C，分别送入冻结的CLIP视觉编码器、DepthAnything编码器和CLIP文本编码器。
2.  文本编码器预计算文本嵌入 tk。
3.  在VFM的多个层中，GeoText Query与 tk 融合，再通过交叉注意力同时关注视觉和深度特征，输出精炼视觉特征。
4.  CMPE模块从编码器多个层取精炼特征，融合后生成粗掩码，并从中聚合得到类别级先验，添加到GeoText Query中。
5.  DOV-VEH接收多尺度精炼特征和更新后的查询，经像素解码器和变换解码器得到最终分割掩码。

## 3. 实验设计

*   **数据集**：
    *   训练源域：Cityscapes（真实城市场景）、GTA5（合成数据）。
    *   测试目标域：ACDC（夜间、雾、雨、雪）、BDD100K、Mapillary、DELIVER（五种天气）、ADE20K子集（ADE150/ADE847）。
*   **基准设置**：采用标准DGSS协议（Cityscapes→ACDC等）和额外开放词汇设置（Cityscapes→DELIVER+ADE等）。
*   **对比方法**：
    *   OVSS方法：FC-CLIP、EBSeg、CAT-Seg、SED。
    *   DGSS方法：IBN、RobustNet、WildNet、HGFormer、CMFormer、REIN、FADA等，覆盖ResNet、Transformer、VFM基础。
*   **评估指标**：平均交并比（mIoU）。

## 4. 资源与算力

*   **GPU**：单张 NVIDIA RTX A6000（文中未写明显卡数量，但从batch size=8推断为单卡）。
*   **训练时长**：约14小时。
*   **峰值显存**：约45 GB。
*   **可训练参数**：仅约3.78M（Vireo模型本身），远低于全微调。

## 5. 实验数量与充分性

*   **实验组数**：表格共6个主要表（表1-6），包含跨域泛化、开放词汇、组件消融、不同backbone对比；图3-7提供定性可视化、注意力图、t-SNE、损失曲线。
*   **充分性**：实验非常充分——覆盖两个训练源域、多个目标域（至少8个不同数据集/子集），对比了超过10种SOTA方法；消融研究（表5）逐一验证每个组件贡献；跨backbone实验（表6）证明方法通用性（CLIP-L、SAM-H、EVA02-L、DINOv2-L）；还进行了参数效率对比（表4）。
*   **公平性**：所有实验采用相同迭代次数（40k）、统一优化器设置，保证比较客观。

## 6. 论文的主要结论与发现

1.  Vireo在域泛化和开放词汇两个维度均达到SOTA，大幅超越现有DGSS和OVSS方法（如在Cityscapes→ACDC上mIoU达60.6%以上，比最强基线提升3-5个百分点）。
2.  深度几何信息（DepthAnything V2）为域不变性提供关键支撑，GeoText Query是性能提升的最大贡献者（约+4.4% mIoU）。
3.  CMPE有效加速收敛并增强文本先验，DOV-VEH融合多模态特征实现鲁棒预测。
4.  方法参数高效（仅3.78M可训练参数），且能无缝迁移至不同VFM骨干，通用性强。

## 7. 优点

*   **问题新颖性**：首次提出并解决OV-DGSS统一框架，填补领域空白。
*   **设计巧妙**：冻结VFM并利用深度几何提供域不变结构特征，避免全微调的高成本；三个组件形成端到端闭环，各司其职。
*   **参数高效**：仅需极少量可训练参数（约3.8M），远低于其他微调方案（如FADA需11.65M）。
*   **全面验证**：在多个真实/合成域、开放词汇场景下进行系统性评估，消融实验充分证明每个模块必要性。
*   **可复现性**：代码已开源，实验设置详细。

## 8. 不足与局限

*   **依赖RGB相机**：假定可靠的RGB输入，但遇到遮挡、强光或硬件故障时，感知能力可能严重下降。
*   **未考虑多模态切换**：未探索在RGB失效时自动切换到激光雷达、雷达或事件相机等替代传感器，未来工作将朝此方向。
*   **计算资源限制**：峰值显存45GB，对低端GPU不友好；训练时间14h虽可接受但并非最优。
*   **极端域评估覆盖**：ACDC和DELIVER虽然包含多种恶劣天气，但缺少如雪地反光、高动态范围等更极端场景，泛化边界未完全测试。
*   **开放词汇性能**：对完全未见类别的mIoU仍偏低（约10-12%），说明开放词汇识别仍是难点，几何深度辅助有限。

（完）
