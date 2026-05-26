---
title: "DAA: Amplifying Unknown Discrepancy for Test-Time Discovery"
title_zh: DAA：通过放大未知差异实现测试时发现
authors: "Tianle Liu, Fan Lyu, Chenggong Ni, Zhang Zhang, Fuyuan Hu, Liang Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=gVKxz6M1ov"
tags: ["query:tta"]
score: 4.0
evidence: 通过差异放大实现测试时发现，与自适应技术相关
tldr: 测试时发现任务要求在推理时识别新类别并保持已知类性能。DAA提出差异放大适配器，在线放大了已知与未知类的特征差异，并通过模拟未知样本训练。在多个数据集上提升了发现性能，但更偏向开集发现而非传统TTA。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 743, \"height\": 257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 703, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 698, \"height\": 247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 699, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1409, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1432, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1431, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1414, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gvkxz6m1ov/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1401, \"height\": 444, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gvkxz6m1ov/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gvkxz6m1ov/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 672, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gvkxz6m1ov/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 781, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gvkxz6m1ov/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 584, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gvkxz6m1ov/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gvkxz6m1ov/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1448, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gvkxz6m1ov/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 667, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gvkxz6m1ov/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1152, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gvkxz6m1ov/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1153, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gvkxz6m1ov/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1150, \"height\": 349, \"label\": \"Table\"}]"
motivation: 测试时发现需要实时适应新类别，现有方法泛化差。
method: 提出可训练差异放大适配器，在线放大已知与未知类差异。
result: 在测试时发现基准上优于现有静态方法。
conclusion: 差异放大适配器有效支持实时测试时新类发现。
---

## Abstract
Test-Time Discovery (TTD) addresses the critical challenge of identifying and adapting to novel classes during inference while maintaining performance on known classes, which is a capability essential for dynamic real-world environments such as healthcare and autonomous driving. Recent TTD methods adopt training-free, memory-based strategies but rely on frozen models and static representations, resulting in poor generalization. In this paper, we propose a Discrepancy-Amplifying Adapter (DAA), a trainable module that enables real-time adaptation by amplifying feature-level discrepancies between known and unknown classes. During training, DAA is optimized using simulated unknowns and a novel warm-up strategy to enhance its discriminative capacity. To ensure continual adaptation at test time, we introduce a Short-Term Memory Renewal (STMR) mechanism, which maintains a queue-based memory for unknown classes and selectively refreshes prototypes using recent, reliable samples. DAA is further updated through self-supervised learning, promoting knowledge retention for known classes while improving discrimination of emerging categories. Extensive experiments show that our method maintains high adaptability and stability, and significantly improves novel class discovery performance. Our code will be available.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
**研究动机与背景**  
- 测试时发现（Test-Time Discovery, TTD）要求在推理阶段同时识别已知类别并动态发现、适应未知类别，对医疗、自动驾驶等动态场景至关重要。  
- 现有TTD方法（如HM）采用**无训练的内存策略**，依赖冻结的骨干网络和静态特征表示，导致未知类与已知类的特征分布重叠，泛化能力差。  
- 论文旨在克服静态表示的局限，引入**可训练模块**，实现实时的特征差异放大，从而提升新类发现性能。

### 2. 论文提出的方法论
**核心思想**  
- 通过训练一个轻量适配器 DAA（Discrepancy-Amplifying Adapter），在保持已知类特征的同时，放大已知类与未知类之间的**特征级差异**，使决策边界更清晰。  

**关键技术细节**  
- **预热阶段（Warm‑up）**  
  - 利用模拟未知类（通过 Mixup + 高斯噪声生成合成特征）训练 DAA。  
  - 损失函数包含两部分：  
    - MSE 损失（保持已知类特征不变）；  
    - 对比损失（使模拟未知类特征与已知类特征分离）。  
- **测试时自适应**  
  - **短期记忆更新（STMR）**：为每个类维护样本队列和特征队列，已知类队列固定，未知类队列采用先进先出（FIFO）策略，并定期对队列中的样本**重评估**，丢弃误判为已知类的样本，用可靠特征更新适配器。  
  - **预测与学习**：基于余弦相似度和阈值γ判断样本属于已知类、已发现类还是全新类。测试时损失包括自监督损失（基于伪标签）和记忆重放/更新的对比损失，综合优化 DAA。  

**算法流程（文字说明）**  
1. 用训练集（仅已知类）预热 DAA：合成未知特征，最小化 MSE 和对比损失。  
2. 测试阶段，对每批数据：  
   - 提取特征并通过 DAA 得到增强表示。  
   - 与所有已知/已发现类的原型计算相似度，根据阈值判定类别。  
   - 若被判定为全新类，则创建新原型。  
   - 定期执行 STMR：刷新未知队列中的特征，移除噪声样本。  
   - 综合损失更新 DAA。

### 3. 实验设计
**数据集与场景**  
- 使用三个基准数据集：**CIFAR-100D、CUB-200D、Tiny-ImageNetD**。  
- 按已知:未知类 = 7:3 划分，测试集同时包含两类样本，要求实时识别。  

**Benchmark 与对比方法**  
- 对比方法包括：  
  - **训练‑free 方法**：阈值法（Threshold）、HM（最先进 TTD 方法）。  
  - **训练型方法**：L2P、DP、GMP（基于 prompt 的 TTA/CL 方法）、PHE（在线类别发现方法）。  

**评估指标**  
- 已知类：已知准确率（KA）、知识遗忘率（KF）。  
- 未知类：真标签一致性（TA）、簇一致性（CA）、聚类指标（HCA、ARI、NMI、V‑Measure）。  
- 评估模式：**实时评估**（逐批累计）和**事后评估**（测试结束后重新评估所有样本）。

### 4. 资源与算力
论文**未明确**说明使用的 GPU 型号、数量或训练时长。仅在实现细节中提及采用了 ViT‑B/16 骨干和 SGD 优化器，未提供具体算力信息。

### 5. 实验数量与充分性
- **主要对比实验**：在三个数据集上报告了多次运行的均值和标准差，结果稳定。  
- **消融实验**验证了 DAA、测试时训练（TTT）和 STMR 各组件的贡献（Table 3）。  
- **超参数分析**：记忆队列大小、STMR 更新频率、回放样本数、损失权重 λ₁/λ₂、置信度阈值 γ（表/图 6–13）。  
- **可视化**：t‑SNE 投影、原型间距离直方图、未知类预测与真实标签匹配矩阵。  
- **不同可发现类数的影响**（Table 8）。  
- **结论**：实验覆盖全面，对比公平（代码已开源），统计差异显著优于 SOTA。

### 6. 论文的主要结论与发现
- DAA 能有效放大未知类与已知类的特征差异，在三个数据集上取得 **HCA、ARI、NMI、V‑Measure 最优**；TA 和 CA 也达到最高或次高。  
- 训练‑free 方法（如 HM）因无法更新模型，在复杂重叠分布下性能受限；而 DAA 的动态更新提升了新类识别且遗忘率低。  
- STMR 通过选择性刷新记忆，抑制噪声干扰，显著提升稳定性，降低知识遗忘。

### 7. 优点
- **创新性**：首次在 TTD 中引入可训练适配器，突破静态特征限制。  
- **方法简洁且有效**：DAA 仅为一个 2 层线性适配器，参数量小，但效果显著。  
- **记忆管理巧妙**：STMR 结合 FIFO 与重评估，避免误差累积，支持在线学习。  
- **实验充分**：涵盖多数据集、多指标、消融和大量超参数分析，验证了各模块必要性。  
- **代码开源**，可复现性强。

### 8. 不足与局限
- **计算开销**：虽然适配器轻量，但预热和测试时更新仍引入额外计算；STMR 频繁触发会增大延迟。  
- **启发式更新**：STMR 基于阈值和 FIFO 的更新策略可能在高噪声或极度不平衡场景下效果下降。  
- **仅验证图像分类**：未在更多模态（如文本、语音）或更复杂任务（如检测、分割）上测试。  
- **算力未报告**：难以评估资源需求，对实际部署的参考价值有限。  
- **假设已知类数量固定**：真实场景中已知类也可能动态增加，论文未考虑增量已知类的情况。

（完）
