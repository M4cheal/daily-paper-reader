---
title: Connectivity-Driven Pseudo-Labeling Makes Stronger Cross-Domain Segmenters
title_zh: 连通性驱动伪标签：更强的跨域分割器
authors: "Dong Zhao, Qi Zang, Shuang Wang, Nicu Sebe, Zhun Zhong"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=VIqQSFNjyP"
tags: ["query:ris"]
score: 6.0
evidence: 通过伪标签处理语义分割中的域偏移，与指代分割域适应相关
tldr: 跨域语义分割中伪标签方法受域偏移影响产生散布噪声，且开放类别像素可能被误标。本文提出连通性驱动的伪标签方法，通过像素连通性约束筛选可靠标签，避免误差累积。在多个合成到真实域迁移任务上验证了有效性，其思想可直接应用于指代分割的域偏移场景。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-viqqsfnjyp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1383, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-viqqsfnjyp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1365, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-viqqsfnjyp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-viqqsfnjyp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-viqqsfnjyp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1296, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-viqqsfnjyp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-viqqsfnjyp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1422, \"height\": 788, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-viqqsfnjyp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-viqqsfnjyp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1450, \"height\": 821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-viqqsfnjyp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1089, \"height\": 2180, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-viqqsfnjyp/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1405, \"height\": 2292, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-viqqsfnjyp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 712, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-viqqsfnjyp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-viqqsfnjyp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1166, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-viqqsfnjyp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1089, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-viqqsfnjyp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1387, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-viqqsfnjyp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 545, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-viqqsfnjyp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1382, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-viqqsfnjyp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1382, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-viqqsfnjyp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1376, \"height\": 251, \"label\": \"Table\"}]"
motivation: 跨域语义分割中像素级伪标签存在散布噪声和开放类误标，导致自训练错误累积。
method: 引入连通性约束筛选结构化的可靠伪标签，替代传统像素级独立筛选。
result: 在多个域适应基准上超过现有伪标签方法，尤其在大域偏移下鲁棒性显著提升。
conclusion: 连通性先验有效提升了伪标签质量，为指代分割的跨域泛化提供了可借鉴思路。
---

## Abstract
Presently, pseudo-labeling stands as a prevailing approach in cross-domain semantic segmentation, enhancing model efficacy by training with pixels assigned with reliable pseudo-labels.  However, we identify two key limitations within this paradigm: (1) under relatively severe domain shifts, most selected reliable pixels appear speckled and remain noisy. (2) when dealing with wild data, some pixels belonging to the open-set class may exhibit high confidence and also appear speckled. These two points make it difficult for the pixel-level selection mechanism to identify and correct these speckled close- and open-set noises. As a result, error accumulation is continuously introduced into subsequent self-training, leading to inefficiencies in pseudo-labeling. To address these limitations, we propose a novel method called Semantic Connectivity-driven Pseudo-labeling (SeCo).  SeCo formulates pseudo-labels at the connectivity level, which makes it easier to locate and correct closed and open set noise. Specifically, SeCo comprises two key components: Pixel Semantic Aggregation (PSA) and Semantic Connectivity Correction (SCC). Initially, PSA categorizes semantics into ``stuff'' and ``things'' categories and aggregates speckled pseudo-labels into semantic connectivity through efficient interaction with the Segment Anything Model (SAM).  This enables us not only to obtain accurate boundaries but also simplifies noise localization. Subsequently, SCC introduces a simple connectivity classification task, which enables us to locate and correct connectivity noise with the guidance of loss distribution. Extensive experiments demonstrate that SeCo can be flexibly applied to various cross-domain semantic segmentation tasks, \textit{i.e.} domain generalization and domain adaptation,  even including source-free, and black-box domain adaptation, significantly improving the performance of existing state-of-the-art methods. The code is provided in the appendix and will be open-source.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在跨域语义分割中，伪标签（pseudo-labeling）技术是主流方法，但存在两个关键缺陷：  
  - 在严重域偏移下，被选为“可靠”的像素实际上仍呈散点状且包含大量噪声（闭集噪声）。  
  - 在处理开放集（wild）数据时，属于未知类的像素可能被误判为高置信度可靠像素，同样呈现散点状（开集噪声）。  
  - 像素级的筛选机制难以识别和纠正这些噪点，导致自训练过程中误差累积，最终影响模型性能。
- **研究背景**：域适应（UDA、SF-UDA、BB-UDA）与域泛化（DG）中，伪标签的质量直接决定最终适应效果；现有像素级去噪方法（如多分类器投票、一致性正则化）在强域偏移下依然不足。
- **整体目标**：提出**语义连通性驱动的伪标签（SeCo）**，将伪标签从像素级提升到连通性（connectivity）级，从而更结构化和低噪声地引导后续训练。

### 2. 论文提出的方法论

- **核心思想**：利用**分割一切模型（SAM）**将散点伪标签聚合为语义连通区域，然后对每个连通区域进行噪声识别与纠正，而非对孤立像素独立处理。
- **关键技术细节**（两步法）：  
  1. **像素语义聚合（PSA）**：  
     - 将类别分为“stuff”（大尺度、高像素占比）和“things”（小尺度、密集相邻）。  
     - 对“stuff”采用语义对齐（alignment）方式聚合：用SAM生成无类别掩码，根据伪标签在掩码内的最大比例赋值。  
     - 对“things”采用框+点提示（box + point prompts）引导SAM精确分割。  
     - 最终输出**连通性级别的伪标签**（connectivity-level pseudo-label），既保留精确边界又简化噪声定位。  
  2. **语义连通性纠正（SCC）**：  
     - 构建一个连通性分类器（特征提取器+线性层），对每个连通区域进行K-way分类。  
     - 利用**早期学习现象**（early learning）与**高斯混合模型**（GMM）对损失分布建模：以小损失对应的分布为干净样本，大损失对应噪声。  
     - 设定噪声阈值（τ_ns）滤除噪声连通性，并设置纠正阈值（τ_cr）将部分噪声连通性按照分类器高置信度输出重新分配标签。  
     - 最终得到干净/纠正后的伪标签集合 D_all，用于后续自训练。
- **公式或算法流程**（文字说明）：  
  - PSA过程：见Algorithm 1（提取连通性 → 对things用框+点提示 → 对stuff用语义对齐 → 合并去重）。  
  - SCC损失函数：L_scc = ∑ -ŷ^k log(MLP(Pool[F_scc(x), m]))。  
  - 噪声概率 η = p(c | L_scc(x,m))，通过EM拟合双高斯得到。  
  - 最终伪标签集 D_clean = {η < τ_ns}，D_corr = {p_scc > τ_cr, η > τ_ns}，取并集用于训练。

### 3. 实验设计

- **数据集**：  
  - 合成源域：GTA5、SYNTHIA。  
  - 真实目标域：Cityscapes、BDD-100k。  
  - 额外场景：室内ADE20K（半监督）、医学Endovis17→18、遥感Potsdom→Vaihingen。
- **Benchmark**：涵盖多种跨域任务：  
  - **无监督域适应（UDA）**：GTA5→Cityscapes、SYNTHIA→Cityscapes、GTA5→BDD-100k（开放复合域）。  
  - **源自由域适应（SF-UDA）**：GTA5→Cityscapes、SYNTHIA→Cityscapes、GTA5→BDD-100k。  
  - **黑盒域适应（BB-UDA）**：GTA5→Cityscapes、SYNTHIA→Cityscapes。  
  - **域泛化（DG）**：GTA5→Cityscapes/BDD-100k/Mapillary（使用Stable Diffusion合成数据）。
- **对比方法**：  
  - UDA：AdvEnt、ProDA、DAFormer、HRDA、PyCDA等。  
  - SF-UDA：HCL、DTST、SFOCDA等。  
  - BB-UDA：DINE、BiMem。  
  - DG：SHADE、TLDR、MoDify、CLOUDS（也使用SAM）等。
- **评估指标**：平均交并比（mIoU）。

### 4. 资源与算力

- 论文中**未明确说明**使用的GPU型号、数量及具体训练时长。仅提及使用SAM ViT-H作为分割模型，连通性分类器训练5000迭代。  
- 可以推测实验在标准GPU集群（如V100/A100）上运行，但未提供精确细节。

### 5. 实验数量与充分性

- **实验数量丰富**：  
  - 主要UDA实验：3个任务（GTA5→Cityscapes、SYNTHIA→Cityscapes、GTA5→BDD-100k），每个任务分别测试4-6个baseline（含集成SeCo）。  
  - SF-UDA和BB-UDA：各2个任务，每个任务2个baseline。  
  - DG：2个baseline + CLUODS。  
  - 消融实验：PSA vs. PSA(b)，SCC贡献，Prompt方式比较，与DivideMix对比等。  
  - 超参数敏感性分析（τ_ns、τ_cr）。  
  - 额外场景：室内、医学、遥感（各1个baseline）。  
  - 特征分布可视化（FID指标）。
- **公平性**：  
  - 作者主动讨论了SAM使用带来的潜在不公平，并提供了不使用SAM的对比（SCC单独应用），证明连通性去噪思想本身有优势。  
  - 对比方法均采用官方或最佳设置，并集成SeCo后统一测试。  
- **充分性**：实验覆盖主要跨域场景，消融全面，结论可靠。

### 6. 论文的主要结论与发现

- **SeCo显著提升跨域语义分割性能**：在UDA、SF-UDA、BB-UDA、DG等任务中，集成SeCo均能带来2.3%~13.4%的mIoU提升，尤其对源自由和黑盒适应提升更大（6~10%）。  
- **连通性级去噪优于像素级**：因为连通性特征空间更紧凑，噪声更易分离，且能利用图像级去噪技术（如DivideMix）。  
- **与SAM的交互方式至关重要**：区分为“stuff”和“things”分别采用对齐和提示策略，避免暴力使用SAM导致的噪声放大。  
- **SeCo可即插即用**：能够灵活集成到多种现有方法中，无需修改原算法主体。

### 7. 优点

- **创新性**：首次将伪标签从像素级提升到连通性级，结合SAM和噪声学习实现高效去噪。  
- **实用性**：适用于多种域适应范式和域泛化，包括数据保护场景（SF-UDA、BB-UDA）。  
- **即插即用**：可以无缝集成到现有SOTA方法中，不改变原始网络结构。  
- **实验充分**：覆盖多个基准、多个任务、多种baseline，消融详尽，验证了每个组件的必要性。  
- **可视化清晰**：通过图像对比直观展示了SeCo在去除闭集和开集噪声上的优势。

### 8. 不足与局限

- **缺乏类别平衡处理**：连通性噪声过滤未显式考虑类别不平衡，可能对稀有类不利（作者附录G提及）。  
- **依赖SAM的预处理**：需要额外运行SAM，带来更多计算成本，且SAM本身对大物体和小物体处理效果可能不均衡。  
- **开放集评估受限**：虽声称能处理开集噪声，但现有数据集缺乏专门的开集标注，难以定量评估。  
- **未报告具体算力资源**：无法精确复现计算开销。  
- **实验场景仍有扩展空间**：虽然涵盖了室内、医学、遥感，但每个场景仅测试一个baseline，泛化性待进一步验证。  
- **超参数依赖**：τ_ns和τ_cr需要针对不同任务微调，尽管敏感性分析表明在合理范围内稳定。

（完）
