---
title: Open-Vocabulary Part Segmentation via Progressive and Boundary-Aware Strategy
title_zh: 渐进式边界感知的开放词汇部件分割
authors: "Xinlong Li, Di Lin, Shaoyiyi Gao, Jiaxin Li, Ruonan Liu, Qing Guo"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=gwT1GOKiaO"
tags: ["query:ris"]
score: 7.0
evidence: 利用语言提示进行开放词汇部件分割，与指代分割定位语义实体相关
tldr: 开放词汇部件分割面临边界模糊和分类离散化冲突。本文提出PBAPS框架，无需额外训练，利用物体-部件结构知识逐步从物体分割到部件，并引入边界感知精化模块通过不确定性量化增强模糊区域特征。在多个数据集上达到先进性能，其语言引导分割思想与指代分割高度一致。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gwt1gokiao/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1430, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gwt1gokiao/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 716, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gwt1gokiao/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gwt1gokiao/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gwt1gokiao/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1418, \"height\": 1318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gwt1gokiao/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 713, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gwt1gokiao/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1433, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gwt1gokiao/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1429, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gwt1gokiao/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1419, \"height\": 1186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gwt1gokiao/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1425, \"height\": 1239, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gwt1gokiao/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1411, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gwt1gokiao/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1457, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gwt1gokiao/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gwt1gokiao/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 588, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gwt1gokiao/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 845, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gwt1gokiao/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 664, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gwt1gokiao/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 636, \"height\": 245, \"label\": \"Table\"}]"
motivation: 开放词汇部件分割中边界的结构连接性与离散分类机制冲突导致精度不足。
method: 利用结构知识引导渐进式分割，并设计边界感知模块基于不确定性自适应细化。
result: 在多个部件分割基准上取得最优结果，无需训练即可高效分割。
conclusion: 该方法证明了语言引导下的精细分割潜力，对指代分割具有直接参考价值。
---

## Abstract
Open-vocabulary part segmentation (OVPS) struggles with structurally connected boundaries due to the inherent conflict between continuous image features and discrete classification mechanism. To address this, we propose PBAPS, a novel training-free framework specifically designed for OVPS. PBAPS leverages structural knowledge of object-part relationships to guide a progressive segmentation from objects to fine-grained parts. To further improve accuracy at challenging boundaries, we introduce a Boundary-Aware Refinement (BAR) module that identifies ambiguous boundary regions by quantifying classification uncertainty, enhances the discriminative features of these ambiguous regions using high-confidence context, and adaptively refines part prototypes to better align with the specific image. Experiments on Pascal-Part-116, ADE20K-Part-234, PartImageNet demonstrate that PBAPS significantly outperforms state-of-the-art methods, achieving 46.35\% mIoU and 34.46\% bIoU on Pascal-Part-116. Our code is available at https://github.com/TJU-IDVLab/PBAPS.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：开放词汇部件分割（Open-Vocabulary Part Segmentation, OVPS）在分割**结构连接部件边界**（如猫头与猫脖、躯干与脖颈）时精度严重不足。
- **根本原因**：图像特征是**连续的、平滑过渡的**，而分类机制是**离散的、互斥的**，导致边界像素同时混合相邻部件特征，难以被可靠分类；传统基于高梯度假设的边界检测在此失效。
- **意义**：突破现有方法对物体‑部件结构建模的忽视，提升细粒度部件分割的鲁棒性和泛化性。

### 2. 方法论
#### 核心思想
- **渐进式分割**：利用物体‑部件层级关系（Hierarchical Part Connected Graph, HPCGraph）引导从物体到细粒度部件的逐层分割。
- **边界感知精化（Boundary‑Aware Refinement, BAR）**：通过不确定性量化定位模糊区域，再利用高置信度上下文增强特征并自适应更新部件原型。

#### 关键技术细节
1. **跨模型原型诱导**：使用 Stable Diffusion（文本提示生成合成图像）+ SAM（获取掩码）+ DINOv2（提取掩码内特征）为每个部件类生成视觉原型（并做 K‑means 子类聚类，K=4）。
2. **HPCGraph 构建**：节点包括物体层和部件层（多层粒度），边分为**层级边**（父子“组成”关系）和**邻接边**（结构连接关系）。
3. **渐进式分割流程**：
   - 物体级分割：利用跨层级匹配代价（公式 2）对像素分配物体标签。
   - 部件级分割：在父物体掩码内对子部件进行局部匹配，得到原始部件掩码。
   - 每层分割后由 BAR 模块优化结构连接边界。
4. **BAR 模块（四步）**：
   - **定位模糊区域**：计算两结构连接部件的匹配代价图之差的绝对值（代价散度图），归一化后阈值化（λ=0.3）得到模糊区域 U；
   - **像素特征优化**（公式 4‑5）：对 U 内每个像素，用注意力机制聚合确定性区域（A_det, B_det）的上下文特征，与原始特征融合（γ=0.8）得到增强特征；
   - **原型自适应更新**（公式 6）：对确定性区域特征聚类得到局部原型，与全局原型融合（α=0.7）得到自适应原型；
   - **重分类**：用增强特征与自适应原型再次分类。

### 3. 实验设计
- **数据集**：Pascal‑Part‑116（17 物体类，116 部件类，850 验证图）、ADE20K‑Part‑234（44 物体类，234 部件类，1016 验证图）、PartImageNet（11 超类，40 常见物体类，2957 验证图）。
- **评估指标**：mIoU（整体分割质量）、bIoU（边界分割精度）。
- **对比方法**：
  - **监督微调类**：ZSSeg+、VLPart、CLIPSeg、CAT‑Seg、PartCATSeg、PartCLIPSeg。
  - **无训练类**：OVDiff、RIM（使用相同视觉原型集确保公平）。
- **消融实验**：分解 HPCGraph（层级分割 + 跨层级匹配）、BAR（边界定位、特征优化、原型自适应）各组件；不同边界类型优化效果；不同特征提取器（MAE, DINO, CLIP, SD, DINOv2）；不同掩码生成器（MaskFormer, SAM, 无）；超参数敏感性（γ, α, K, λ）。

### 4. 资源与算力
- **硬件**：单张 NVIDIA A6000 GPU。
- **推理时间**：每张图像平均 1.81s（含滑动窗口特征提取与 BAR 处理）。
- **原型生成**：生成 128 张合成图像约需 443s，每个部件原型占 0.45 MB。
- **训练需求**：本框架是**无需训练**的，仅使用预训练模型推理，未涉及模型微调或训练时长。

### 5. 实验数量与充分性
- **主实验**：在三个数据集上对比 8 种方法（表 2），均取得最佳 mIoU/bIoU。
- **消融实验**：表 3 逐项消融 HPCGraph 和 BAR 所有子模块；表 4 边界召回率与 λ 关系；表 5 对比仅优化结构连接边界 vs. 所有边界 vs. 非结构连接边界；表 6‑7 消融特征提取器和掩码生成器；图 8 超参数敏感性。
- **公平性**：与无训练方法使用完全相同的视觉原型集；与微调方法在同一基准下比较；评估指标标准化（mIoU, bIoU）。
- **充分性**：实验覆盖主要组件、边界类型、特征来源、阈值影响，充分验证了各设计的必要性。

### 6. 主要结论与发现
- PBAPS 在 **Pascal‑Part‑116** 上达到 46.35% mIoU / 34.46% bIoU，超越所有现有方法，包括全监督 PartCLIPSeg（+10.39% mIoU）和无训练 OVDiff（+4.80% mIoU）。
- **BAR 模块**对结构连接边界提升最为显著（+2.27% mIoU, +1.47% bIoU），而对非结构连接边界无效甚至下降，说明选择性优化的必要性。
- **无训练范式**（利用基础模型生成原型+匹配）整体优于微调范式，表明预训练模型在 OVPS 中的巨大潜力。

### 7. 优点
- **无需训练**，直接利用 Stable Diffusion、SAM、DINOv2 等基础模型，零样本泛化强。
- **创新性设计**：明确区分结构连接边界与非结构连接边界，并针对性设计 BAR 模块（代价散度定位、特征增强、原型自适应），理论动机清晰（梯度分析支持）。
- **渐进式层级结构**（HPCGraph）充分利用物体‑部件先验，避免全局匹配歧义。
- **实验全面、对比公平**：覆盖多个数据集、多种基线，并严格控制变量（如使用相同原型集）。

### 8. 不足与局限
- **无法实例区分**：仅做语义部件分割，不能分离不同个体（如多只猫的各部件混在一起）。
- **依赖先验图**：HPCGraph 需手动定义或外部知识库，对复杂/不规则物体（如模块化家具）可能无法捕获正确拓扑。
- **计算开销**：BAR 仅在结构连接边界执行时增加 0.34s/图；若对所有边界执行则增加 48% 推理时间，效率仍有提升空间。
- **超参数敏感**：λ（阈值）、γ（融合权重）、α（原型自适应系数）需针对数据集调优，缺乏自适应机制。
- **实验局限**：未报告误差棒（标准偏差），也未在更多开放式场景（如医学图像）验证泛化性。

（完）
