---
title: "ReferSplat: Referring Segmentation in 3D Gaussian Splatting"
title_zh: "ReferSplat: 3D高斯泼溅中的指代分割"
authors: "Shuting He, Guangquan Jie, Changshuo Wang, Yun Zhou, Shuming Hu, Guanbin Li, Henghui Ding"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=reuShgiHdg"
tags: ["query:ris"]
score: 9.0
evidence: 提出在3D高斯场景中基于自然语言描述的分割任务，直接涉及指代分割
tldr: 本文首次提出3D高斯泼溅场景中的指代分割任务R3DGS，要求模型根据自然语言描述（如空间关系）分割目标物体。为此构建了Ref-LERF数据集，并提出了ReferSplat框架，显式建模空间关系和多模态理解。该工作对于推动具身AI中3D多模态理解具有重要价值。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-reushgihdg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-reushgihdg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 838, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-reushgihdg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1766, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-reushgihdg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 818, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-reushgihdg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1741, \"height\": 1025, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 847, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 824, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 796, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 852, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 858, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 860, \"height\": 288, \"label\": \"Table\"}]"
motivation: 现有3D场景理解缺乏基于语言描述的分割能力，且处理遮挡和空间关系困难。
method: 提出ReferSplat框架，显式建模3D多模态理解和空间关系。
result: 在构建的Ref-LERF数据集上进行了评估，验证了方法的有效性。
conclusion: 开创了3D指代分割任务并提供了基准。
---

## Abstract
We introduce Referring 3D Gaussian Splatting Segmentation (R3DGS), a new task that aims to segment target objects in a 3D Gaussian scene based on natural language descriptions, which often contain spatial relationships or object attributes. This task requires the model to identify newly described objects that may be occluded or not directly visible in a novel view, posing a significant challenge for 3D multi-modal understanding. Developing this capability is crucial for advancing embodied AI. To support research in this area, we construct the first R3DGS dataset, Ref-LERF. Our analysis reveals that 3D multi-modal understanding and spatial relationship modeling are key challenges for R3DGS. To address these challenges, we propose ReferSplat, a framework that explicitly models 3D Gaussian points with natural language expressions in a spatially aware paradigm. ReferSplat achieves state-of-the-art performance on both the newly proposed R3DGS task and 3D open-vocabulary segmentation benchmarks. Dataset and code are available at https://github.com/heshuting555/ReferSplat.

---

## 论文详细总结（自动生成）

# ReferSplat: 3D高斯泼溅中的指代分割 —— 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：3D Gaussian Splatting (3DGS) 作为一种高效的神经渲染技术，在3D场景理解中取得了显著进展。然而，现有3DGS场景理解方法主要依赖固定类别的标签（如“椅子”、“桌子”）进行分割，缺乏对自由形式自然语言描述的理解能力。特别是当描述包含空间关系（如“左边的红色物体”）或物体属性（如“带浮圈装饰的黄色物体”）时，模型需要同时具备语义和空间推理能力。这种能力对于具身AI、自动驾驶、VR/AR等实际应用至关重要。
- **新任务提出**：本文首次提出**Referring 3D Gaussian Splatting Segmentation (R3DGS)** 任务——在3D高斯场景中，根据自然语言描述分割目标物体。任务挑战性在于：测试时给定的新视角中，目标物体可能被遮挡甚至不可见，模型需利用多视图训练中学到的3D场景知识进行推理。
- **数据集构建**：为支撑研究，构建了第一个R3DGS数据集 **Ref-LERF**，基于Lerf场景（4个真实复杂场景），包含295条语言描述（236训练/59测试），平均句子长度超过13.6词，强调空间关系与细粒度属性。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将自然语言表达与3D高斯点进行显式、空间感知的建模，实现端到端的指代分割。
- **整体框架（ReferSplat）**：包含三个核心组件：
  1. **3D Gaussian Referring Fields（3D高斯指代场）**：
     - 为每个高斯点扩展一个**指代特征向量** \( f_{r,i} \in \mathbb{R}^{d_r} \)。
     - 使用文本编码器（BERT）提取句子嵌入 \( f_e \) 和词特征 \( f_w \)。
     - 计算高斯指代特征与词特征的相似度 \( m_i = \sum_j f_{r,i} \times f_{w,j} \)（逐元素乘积），得到每个高斯的文本响应。
     - 通过光栅化（类似RGB渲染）将 \( m_i \) 渲染到2D图像平面，得到分割掩码 \( M(v) \)。
     - 使用BCE损失监督，伪掩码由**置信度加权IoU策略**生成：对Grounded SAM生成的K个候选掩码，计算加权重叠分数 \( p_k = \frac{\sum_j (\gamma_k \hat{M}_k \cap \gamma_j \hat{M}_j)}{\sum_j (\gamma_k \hat{M}_k \cup \gamma_j \hat{M}_j)} \)，选择分数最高的作为伪GT。
  2. **Position-aware Cross-Modal Interaction（位置感知跨模态交互）**：
     - **位置特征提取**：高斯中心坐标通过MLP得到位置嵌入 \( f_{p,i} \)；文本位置特征通过软注意力从高斯位置特征推断：\( f_{p,w,i} = \text{softmax}(f_w f_{r,i}^T / \sqrt{D}) f_{p,i} \)。
     - **位置引导注意力**：融合位置信息更新指代特征：\( f'_{r,i} = f_{r,i} + \text{softmax}\left( \frac{(f_{r,i}+f_{p,i})(f_w+f_{p,w,i})^T}{\sqrt{D}} \right) f_w \)。
     - 增强后的 \( f'_{r,i} \) 替代原 \( f_{r,i} \) 计算相似度，提升空间推理能力。
  3. **Gaussian-Text Contrastive Learning（高斯-文本对比学习）**：
     - 选取相似度 \( m_i \) 的前τ%高斯点（正样本），平均得到高斯嵌入 \( f_g \)。
     - 采用物体级对比损失：\( \mathcal{L}_{con} = -\frac{1}{|P|} \sum_{f_e^+ \in P} \log \frac{\exp(f_g \cdot f_e^+)}{\sum_{f_e' \in P,N} \exp(f_g \cdot f_e')} \)。
     - 增强区分语义相似但目标不同的描述的能力。
- **总损失**：\( \mathcal{L}_{total} = \mathcal{L}_{bce} + \lambda \mathcal{L}_{con} \)，其中λ=0.02。
- **两阶段优化**：先用伪掩码训练ReferSplat，再用第一阶段输出的渲染掩码作为新的伪掩码训练第二阶段，进一步细化分割。

## 3. 实验设计

- **数据集与Benchmark**：
  - **Ref-LERF**（R3DGS任务）：4个场景（ramen, figurines, teatime, kitchen），295条描述（236训练/59测试），平均长度>13.6词。
  - **LERF-OVS**（3D开放词汇分割）：4个场景。
  - **3D-OVS**（3D开放词汇分割）：5个场景（bed, bench, room, sofa, lawn）。
- **评估指标**：平均交并比（mIoU）。
- **对比方法**：
  - 2D方法：Grounded SAM（直接应用于单视图）。
  - 3D方法：LangSplat、SPIn-NeRF、GS-Grouping、GOI。
  - 消融基线：Cosine Similarity、仅乘法（Baseline）。
- **实验设置**：训练45,000次迭代，学习率0.0025（高斯特征）/0.0001（MLP），Adam优化器，NVIDIA RTX A6000 GPU。

## 4. 资源与算力

- **明确信息**：训练使用**NVIDIA RTX A6000 GPU**（未提及数量，通常单卡）。
- 训练时长：约**58分钟**（ramen场景），相比LangSplat（176分钟）更短。
- 存储占用：约**3.3 MB**（高斯特征），低于LangSplat（46 MB）但高于GS-Grouping（2.3 MB）。
- 推理FPS：**26.8 FPS**，介于LangSplat（12.4）和GS-Grouping（54.2）之间。
- **未明确说明**：是否使用多卡、显存占用、具体CPU/内存配置等。

## 5. 实验数量与充分性

- **实验组数**：
  - **消融实验**（Tab.1-7）：8组多场景实验，覆盖组件有效性、基线配置、伪掩码生成策略、跨模态交互设计、特征维度、语言编码器选择、计算开销。
  - **主实验结果**：R3DGS（Tab.8）、开放词汇分割（Tab.9-10），共3个表格。
  - **定性可视化**：图5展示4个场景下的分割结果对比。
- **充分性评估**：
  - **优点**：消融全面，覆盖核心组件、超参数、伪掩码质量、不同基线对比；在多个benchmark上验证泛化能力；定量与定性结合。
  - **不足**：
    - 仅4个场景的Ref-LERF数据集规模小，可能影响统计显著性。
    - 未在新场景（如室内/室外）进行zero-shot迁移实验，泛化性验证有限。
    - 无统计显著性检验（如置信区间或p值）。
    - 未与更多近期OCC/NeRF-based指代分割方法对比（因任务新，可对比方法有限）。
  - **公平性**：与基线方法采用相同训练/测试划分，评估指标一致；作者公开代码和数据集，可复现。

## 6. 论文的主要结论与发现

- **R3DGS任务可行且挑战性高**：模型需理解空间关系、处理遮挡，3D多模态理解是关键瓶颈。
- **ReferSplat显著优于现有方法**：在Ref-LERF上mIoU达到29.2%，远超LangSplat（13.9%）、GS-Grouping（14.4%）等。
- **各组件均有效**：位置感知跨模态交互（PCMI）提升4.3%~5.1% mIoU，高斯-文本对比学习（GTCL）提升3.4%~4.4%。
- **两阶段优化进一步增益**：在ramen场景从35.2%提升至36.9%。
- **在开放词汇分割任务上也达到SOTA**：在LERF-OVS上平均55.4% mIoU，在3D-OVS上94.1% mIoU。
- **BERT优于CLIP**作为语言编码器，因为指代表达更依赖细粒度语义和空间描述。

## 7. 优点

- **任务创新**：首次定义并基准化3D高斯指代分割任务，填补空白。
- **方法论亮点**：
  - **3D高斯指代场**：直接在高斯特征上建模语言响应，避免2D投影的信息损失。
  - **位置感知跨模态交互**：将空间位置信息显式注入注意力机制，解决“语义强但空间弱”的问题。
  - **高斯-文本对比学习**：通过正负样本分离提升区分度。
  - **置信度加权IoU伪掩码生成**：比简单top-1更可靠，提升训练质量。
- **高效实用**：训练和推理速度快，存储占用小，适合实际部署。
- **开源贡献**：代码和数据集公开，促进后续研究。

## 8. 不足与局限

- **尺度限制**：
  - 数据集仅4个室内场景，缺乏室外、动态、大规模场景，领域泛化性未知。
  - 语言描述数量有限（295条），可能无法覆盖真实世界的多样性。
- **假设限制**：
  - 假设场景是静态的（无动态物体），不适用于时变环境。
  - 未涉及3D视觉定位（如物体框或尺寸估计），仅支持分割。
- **技术局限**：
  - 依赖Grounded SAM生成伪掩码，伪掩码质量直接影响上游训练；若场景复杂或文本模糊，伪掩码可能不准确。
  - 两阶段训练增加计算复杂度（虽已较低）。
- **评估局限**：
  - 无零样本场景测试，无法评估模型对未见房间布局或新物体类别的适应能力。
  - 未在真实机器人/VR应用场景中验证实用性。
  - 对比方法多为开放词汇分割的改编，缺少专门针对R3DGS的其他方法（因任务新）。
- **作者自述局限**：
  - 未整合4D高斯泼溅处理动态场景；未扩展至物体大小估计；未来需构建大规模数据集。

（完）
