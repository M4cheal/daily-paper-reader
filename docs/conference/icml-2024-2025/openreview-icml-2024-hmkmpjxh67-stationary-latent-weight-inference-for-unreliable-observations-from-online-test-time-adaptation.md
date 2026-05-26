---
title: Stationary Latent Weight Inference for Unreliable Observations from Online Test-Time Adaptation
title_zh: 来自在线测试时自适应不可靠观测的静态潜变量权重推断
authors: "Jae-Hong Lee, Joon-Hyuk Chang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=HmKMpJXH67"
tags: ["query:tta"]
score: 9.0
evidence: 在线TTA结合贝叶斯滤波
tldr: 在线TTA易出现灾难性遗忘和适应性不足。本文提出SLWI，采用贝叶斯滤波持续跟踪目标模型权重和源模型权重，在动态环境中保持响应性。实验证明该方法有效克服了信息集成不足的问题，在多个OTTA基准上提升了性能。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-hmkmpjxh67/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1687, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hmkmpjxh67/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 882, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hmkmpjxh67/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 880, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hmkmpjxh67/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 895, \"height\": 348, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 859, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1765, \"height\": 613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 853, \"height\": 571, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 166, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 685, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 859, \"height\": 150, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1767, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1088, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 566, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hmkmpjxh67/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1412, \"height\": 355, \"label\": \"Table\"}]"
motivation: 现有OTTA方法目标域信息集成不足，导致遗忘和适应性差。
method: 利用贝叶斯滤波在线跟踪和更新模型权重。
result: 在多个OTTA基准上优于现有方法。
conclusion: SLWI成功解决了OTTA中的信息集成问题。
---

## Abstract
In the rapidly evolving field of online test-time adaptation (OTTA), effectively managing distribution shifts is a pivotal concern. State-of-the-art OTTA methodologies often face limitations such as an inadequate target domain information integration, leading to significant issues like catastrophic forgetting and a lack of adaptability in dynamically changing environments. In this paper, we introduce a stationary latent weight inference (SLWI) framework, a novel approach to overcome these challenges. The proposed SLWI uniquely incorporates Bayesian filtering to continually track and update the target model weights along with the source model weight in online settings, thereby ensuring that the adapted model remains responsive to ongoing changes in the target domain. The proposed framework has the peculiar property to identify and backtrack nonlinear weights that exhibit local non-stationarity, thereby mitigating error propagation, a common pitfall of previous approaches. By integrating and refining information from both source and target domains, SLWI presents a robust solution to the persistent issue of domain adaptation in OTTA, significantly improving existing methodologies. The efficacy of SLWI is demonstrated through various experimental setups, showcasing its superior performance in diverse distribution shift scenarios.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）

*   **核心问题**：在线测试时自适应（OTTA）面临的主要挑战是**灾难性遗忘**和**适应性不足**。现有方法过度依赖源模型信息，未能有效集成和利用来自目标域的信息，导致在动态变化的分布漂移环境中性能下降。
*   **整体含义**：本文旨在解决OTTA中目标域信息集成不足的问题，通过提出**静态潜变量权重推断（SLWI）框架**，持续融合源域和目标域信息，增强模型在持续漂移环境下的鲁棒性和适应能力。

### 2. 方法论

*   **核心思想**：引入一个**潜变量权重** \(\phi_t\)，它通过**贝叶斯滤波**（卡尔曼滤波的线性高斯模型）不断融合来自源模型权重 \(\phi_0\)（即 \(\theta_0\)）和当前目标域观测权重 \(\theta_t\) 的信息，从而获得更可靠的模型状态用于下一时刻的OTTA过程。
*   **关键技术细节**：
    *   **状态空间模型**：
        *   **转移模型**：\(p(\phi_t | \phi_{t-1}, \phi_0) = \mathcal{N}(\phi_t | a\phi_{t-1} + (1-a)\phi_0, q)\)，控制潜变量向源权重的恢复程度。
        *   **发射模型**：\(p(\theta_t | \phi_t, g_t) = \mathcal{N}(\theta_t | \phi_t - (1-c_t)g_t, 1-q)\)，其中 \(g_t\) 是由SGD计算的梯度，\(c_t\) 用于回溯非线性权重。
    *   **贝叶斯滤波更新**：递归计算潜变量的后验分布 \(\mathcal{N}(\mu_{t|t}, \sigma^2_{t|t})\)，类似标准卡尔曼滤波更新步骤（式8-10）。关键变量 \(\hat{\theta}_t = \theta_t - c_t g_t\) 为回溯后的观测值。
    *   **非平稳性检测与回溯**：定义**平稳性分数** \(S(t, \Delta t, \Delta^2_{0:t-1})\)，基于后验预测概率的对数差异和运行方差。若分数超出阈值 \(\zeta\)（通常设为2，对应95%置信区间），则判定当前权重为非线性，将回溯系数 \(c_t\) 设为 \(1/\alpha\)（\(\alpha>1\)），从而降低观测值的变化幅度，使其符合模型假设。
    *   **信息传递**：通过**插件近似**（plug-in approximation），使用一个简化的传递模型求得点估计 \(\hat{\phi}_t = \mu_{t|t-1} + b(\hat{\theta}_t - \mu_{t|t-1})\)，其中 \(b\) 为直接设定的卡尔曼增益（接近1），确保后验方差足够小，从而高效地将潜变量信息注入下一时刻的OTTA SGD优化中。

### 3. 实验设计

*   **数据集与场景**：
    *   **ImageNet-C**：包含15种腐败类型、5个严重级别，选最高严重级别Level 5，用于评估**协变量漂移**。
    *   **D109**：基于DomainNet的5个自然域（clipart, infograph, painting, real, sketch），用于评估**自然分布漂移**。
    *   **标签漂移**：通过调整狄利克雷分布参数 \(\gamma\)（\(\gamma=0.0\) 和 \(\gamma=0.1\)）模拟类别分布的时变。
*   **Benchmark与对比方法**：严格遵循现有公开基准（Marsden & Döbler, 2022）。对比方法包括 **TENT**、**LAME**、**RoTTA**、**SAR**、**EATA**、**ROID**，均使用官方实现和推荐超参数。
*   **骨干网络**：默认使用 **data2vec (D2V)**（ViT的自监督版本），额外测试了基础ViT和SwinTransformer。

### 4. 资源与算力

*   论文明确说明：所有实验使用**单个NVIDIA GeForce RTX 3090 GPU**。
*   未提供完整训练时长，但在效率对比中给出了单次运行时间：ROID约257.5秒，SLWI约263.8秒（相对增加2.4%）。

### 5. 实验数量与充分性

*   **实验数量**：论文进行了大量实验，总计约**10组以上**，包括：
    *   主实验：协变量漂移（Table 1、2）、标签漂移（Table 3、4）。
    *   模型泛化实验：不同架构（ViT、Swin、D2V，Table 5）。
    *   集成实验：将SLWI应用于TENT、EATA、ROID（Table 6）。
    *   消融实验：回溯超参数 \(\zeta\) 和 \(\alpha\) 的影响（Figure 4）、贝叶斯滤波参数（a, b, q）的影响（Appendix Table 11）。
    *   额外场景：单epoch适应场景（Appendix Table 8-10）。
*   **充分性与公正性**：实验覆盖了主流OTTA基准、多种分布漂移类型、多种网络架构，且遵循统一基准实现对比，使用了5个随机种子报告均值和标准差，结果客观可靠。

### 6. 主要结论与发现

*   **SLWI显著优于现有方法**：在协变量漂移（ImageNet-C上比最好方法ROID降低2.3%错误率）和标签漂移（γ=0.0时降低3.8%）下均取得最佳性能。
*   **缓解灾难性遗忘**：SLWI在目标域性能大幅提升的同时，源域平均错误率仅增加不到1%，表明成功保留源知识。
*   **计算开销极小**：平均仅增加约2.4%的计算时间，可无缝集成到现有OTTA方法中。
*   **回溯机制有效**：消融实验表明，不使用回溯（ζ=∞或α=1）时性能退化严重，证明检测和调整非线性权重是提升稳定性的关键。

### 7. 优点

*   **方法创新**：首次将贝叶斯滤波（卡尔曼滤波）应用于OTTA的权重空间，实现了源域与目标域信息的持续、自适应融合。
*   **理论严谨**：基于线性高斯模型和状态空间理论设计，推导出可计算的后验分布和自然导出的非平稳性检测指标。
*   **实用性强**：无需存储任何原始数据，保护隐私；计算量小，可直接集成到现有方法中提升性能。
*   **实验全面**：在多种分布漂移类型、多种架构、多种集成方式下均验证了有效性，充分展示了泛化能力。

### 8. 不足与局限

*   **超参数依赖**：需要手动设定贝叶斯滤波参数（a, q, b）和回溯超参数（ζ, α）。虽然论文显示固定参数在不同场景下仍有效，但最优值可能随任务变化，缺乏自适应调整机制。
*   **场景覆盖有限**：仅在图像分类任务（ImageNet-C、DomainNet系列）上验证，未涉足语义分割、目标检测等更复杂视觉任务或其他模态（如NLP、语音）。
*   **标签漂移设定较简化**：标签漂移通过狄利克雷分布模拟，与实际开放世界中的复杂标签分布偏移（如类别增量、域内长尾）仍有差距。
*   **未讨论故障情况**：当源模型本身质量很差或目标域与源域完全不相关时，SLWI的恢复机制可能失效，论文未对此进行深入分析。

（完）
