---
title: "ReservoirTTA: Prolonged Test-time Adaptation for Evolving and Recurring Domains"
title_zh: ReservoirTTA：面向演变和重复领域的延长测试时间自适应
authors: "Guillaume Vray, Devavrat Tomar, Xufeng Gao, Jean-Philippe Thiran, Evan Shelhamer, Behzad Bozorgtabar"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=XewZ4rJYKZ"
tags: ["query:tta"]
score: 9.0
evidence: 面向流数据的在线测试时间自适应，处理领域演变
tldr: 针对测试阶段数据分布持续演变甚至周期性重复的场景，现有的单模型测试时间自适应方法会遭受灾难性遗忘和域间干扰。ReservoirTTA提出维护一个领域专家模型池，通过在线聚类检测新领域，并将样本路由到对应的专用模型。该多模型策略在多种连续域漂移场景下显著提升了长期自适应的鲁棒性和稳定性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 611, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1423, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 999, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1296, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1301, \"height\": 1208, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1444, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1437, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1440, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1160, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 717, \"height\": 857, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1154, \"height\": 713, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1454, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1426, \"height\": 742, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1451, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1309, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1290, \"height\": 1262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xewz4rjykz/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1423, \"height\": 1460, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1170, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1465, \"height\": 727, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 799, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 723, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1454, \"height\": 745, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1490, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 396, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1412, \"height\": 555, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1443, \"height\": 614, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1452, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1444, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1447, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1445, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1445, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1447, \"height\": 493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1445, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1446, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1446, \"height\": 531, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1447, \"height\": 531, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1446, \"height\": 699, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1447, \"height\": 748, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1450, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1450, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1453, \"height\": 454, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xewz4rjykz/table-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1560, \"height\": 522, \"label\": \"Table\"}]"
motivation: 解决单一模型在长期测试时间自适应中面临灾难性遗忘和域间干扰的问题。
method: 维护一个域专家模型池，通过在线聚类检测新域并路由样本到对应模型。
result: 在多个连续域漂移数据集上显著优于单模型基线，性能稳定。
conclusion: 多模型集成有效克服了单一模型在非平稳环境中的局限性。
---

## Abstract
This paper introduces **ReservoirTTA**, a novel plug–in framework designed for prolonged test–time adaptation (TTA) in scenarios where the test domain continuously shifts over time, including cases where domains recur or evolve gradually.
At its core, ReservoirTTA maintains a reservoir of domain-specialized models—an adaptive test-time model ensemble—that both detects new domains via online clustering over style features of incoming samples and routes each sample to the appropriate specialized model, and thereby enables domain-specific adaptation.
This multi-model strategy overcomes key limitations of single model adaptation, such as catastrophic forgetting, inter-domain interference, and error accumulation, ensuring robust and stable performance on sustained non-stationary test distributions.
Our theoretical analysis reveals key components that bound parameter variance and prevent model collapse, while our plug–in TTA module mitigates catastrophic forgetting of previously encountered domains. Extensive experiments on scene-level corruption benchmarks (ImageNet-C, CIFAR-10/100-C), object-level style shifts (DomainNet-126, PACS), and semantic segmentation (Cityscapes→ACDC) — covering recurring and continuously evolving domain shifts — show that ReservoirTTA substantially improves adaptation accuracy and maintains stable performance across prolonged, recurring shifts, outperforming state-of-the-art methods. Our code is publicly available at https://github.com/LTS5/ReservoirTTA.

---

## 论文详细总结（自动生成）

# ReservoirTTA：面向演化和循环领域的长时间测试时自适应——论文总结

## 1. 论文的核心问题与整体含义

**研究动机**：深度神经网络在测试数据分布偏移时性能严重下降。现实场景（如自动驾驶、监控）中，分布偏移往往是**长期动态变化**的，包括**循环出现**（如白天/黑夜）和**逐渐演化**（如天气渐变）。现有的测试时自适应（TTA）方法大多假设每个目标域只出现一次，当域多次重复出现时，单模型容易发生**灾难性遗忘**、**域间干扰**和**错误累积**，最终导致模型崩溃。

**核心挑战**：如何让预训练模型在长时间、非平稳的测试流中稳定适应，既能快速适应新域，又能在旧域重现时保留知识，避免遗忘和负迁移。

## 2. 论文提出的方法论

### 核心思想
- **多模型解耦适应**：维护一个**领域专家模型池**（Model Reservoir），每个模型对应一个检测到的视觉域。
- **风格驱动的在线聚类**：利用预训练VGG-19的早期层**通道方差（logvar）**作为风格特征，通过**在线DP-Means聚类**动态发现新域或识别重复域。
- **领域感知路由**：根据测试批次的风格向量，软分配（soft assignment）到最相关的专家模型，仅更新该模型。
- **参数集成预测**：最终预测通过**加权平均**所有专家模型的参数（权重为风格软分配系数）获得，确保所有模型贡献但不互相覆盖。

### 关键技术细节
1. **风格表征**：从冻结的VGG-19前L层提取特征图，计算每层log-方差，拼接成风格向量 s_t。
2. **在线聚类**：维护风格质心 C_t。若当前 s_t 与所有质心最小欧氏距离 > 阈值 τ（基于源域样本对距离的q分位数），则创建新簇。质心通过**互信息损失** L_MI 在风格存储池（Style Reservoir，含最近M个风格向量）上梯度更新，保证分配置信度和多样性。
3. **模型存储池**：最大容量 K_max。新域触发时，从已有模型中选择在当前批次上**互信息最大**的模型作为初始化（避免从头开始）。
4. **模型更新**：仅更新被选中的专家模型参数 θ^{k^*}，使用基线的TTA损失（如熵最小化、冯·诺依曼熵等）。
5. **集成预测**：加权平均参数。
6. **理论分析**：提供了参数方差增长界（Lemma 1, Theorem 1）和源加权集成/ Fisher正则化等价性（Proposition 1-4），证明单模型在循环域下会漂移，而模型池解耦可避免。

### 算法流程（文字说明）
1. 初始化风格质心、模型存储池（含源模型）、Style Reservoir。
2. 对于每个测试批次 B_t：
   - 计算风格向量 s_t，更新Style Reservoir（蓄水池采样）。
   - 计算 s_t 与各质心距离，决定是否创建新域（若距离>τ且 K_t < K_max）。
   - 若为新域：增加新模型，初始化；增加新质心。
   - 更新质心：对Style Reservoir中的向量计算软分配矩阵，通过梯度下降优化 L_MI。
   - 计算软分配向量 q_t，选出最匹配模型 k*。
   - 仅更新模型 θ^{k^*} 一次。
   - 通过加权集成参数计算最终预测。

## 3. 实验设计

### 数据集与场景
- **场景级腐蚀**：CIFAR-10→CIFAR-10-C, CIFAR-100→CIFAR-100-C, ImageNet→ImageNet-C（severity 5），评估**循环结构变化（CSC）**、**循环动态变化（CDC）**、**连续变化腐蚀（CCC）**三种协议。
- **对象级风格偏移**：DomainNet-126（126类，4域：真实、绘画、剪贴画、素描），PACS（7类，4域：照片、艺术画、卡通、素描）。
- **语义分割**：Cityscapes→ACDC（4个天气条件：雾、夜、雨、雪），循环10次。

### 对比方法
- **单目标TTA**：TENT
- **持续TTA**：CoTTA*（仅更新仿射参数）、RoTTA、ETA、SAR
- **持久TTA**：RDumb、PeTTA、EATA、ROID*（不包含增强一致性损失）
- **域解耦/提示TTA**：CoLA、DPCore、BECoTTA（ViT和分割任务）
- **ReservoirTTA插件版本**：应用于EATA、ROID*、ETA、SAR、TENT、CoTTA*、BECoTTA等。

### 评估指标
- 分类：**错误率（%）**，报告第1、20次访问及变化Δ。
- 分割：**mIoU（%）**，报告每次访问。

## 4. 资源与算力

论文在方法部分未明确列出总的GPU训练时长，但在附录H提到**所有实验在单张NVIDIA A100（80GB VRAM）上运行**。实际中，每个CNN骨干实验（如CIFAR-100-C用ResNeXt-29）包含20轮循环、5个种子，每轮需遍历整个数据集多次，总计算量较大。分割实验使用Segformer-B5在Cityscapes→ACDC上循环10次。论文未给出精确小时数，但指出**ReservoirTTA额外开销为基线1.3倍的可比时间**。

## 5. 实验数量与充分性

### 实验数量
- **分类主实验**：3个腐蚀数据集 × 2种协议( CSC, CDC ) × 3个CNN骨干 + ViT-B/16 × 2协议 + CCC设置 × 2骨干 ≈ 约20个独立表格。
- **分割实验**：1个数据集，3种基线 + 3种ReservoirTTA插件，循环10次。
- **消融实验**：风格表征、聚类策略、距离度量、存储池容量K_max、风格存储池大小M、初始化策略、采样策略、批大小、阈值参数、正则权值敏感性等至少10组以上。
- **额外实验**：渐进偏移、时间相关流等。

### 充分性与公平性
- **充分**：覆盖了多种架构（CNN、ViT）、多种场景（腐蚀、风格、分割）、多种协议（CSC/CDC/CCC）、多种基线，包括与最前沿方法（CoLA、DPCore等）对比。
- **客观公平**：所有方法在统一代码库中实现，超参数按论文或常见设置；ReservoirTTA作为插件叠加，不改变基线核心优化。多次随机种子平均结果。但存在一定偏差：部分基线（如RoTTA、PeTTA）因内存限制未作为插件集成，仅与原始版本比较。另外，在ViT上对基线算法（如DPCore）可能未充分调参。

## 6. 论文的主要结论与发现

1. **单模型适应在循环场景下必然失败**：理论上参数方差随时间线性增长，导致漂移出稳定区域。
2. **ReservoirTTA通过解耦多模型显著提升长期稳定性**：在各数据集和协议上，将EATA、ROID*、ETA等方法的第20次访问错误率降低1-7个百分点，且性能几乎不随循环次数恶化。
3. **风格驱动的聚类比ViT特征更鲁棒**：VGG-19的logvar特征产生更稳定的聚类，且对批次顺序不敏感，不会过度碎片化（与DPCore、CoLA对比）。
4. **组件消融**：Model Reservoir贡献最大（尤其是CSC/CDC），Style Reservoir在渐变（CCC）中更重要；集成预测在CCC中有效。
5. **即插即用有效**：与不同TTA基线结合均能提升性能，鲁棒性提升，且降低了对Fisher正则化权重或动量系数的敏感性。

## 7. 优点

### 方法亮点
- **可扩展的即插即用设计**：适用于多种架构（BN/GN/LoRA/prompt）和多种TTA损失，不要求源码数据。
- **完全在线**：不需要离线预聚类，自动发现新域并重用旧域模型，无遗忘记忆。
- **理论支撑**：提供了参数方差界和漂移概率界的分析，解释了单模型失败原因及存储池优势。
- **低内存开销**：仅复制可训练参数（如仿射层），不存储完整模型。

### 实验亮点
- 评估协议全面：循环、动态、渐进、时间相关流均有覆盖。
- 与近期域解耦方法（CoLA、DPCore）直接对比，展现更优的域检测精度和性能。
- 在语义分割上也有验证，展示通用性。

## 8. 不足与局限

### 计算开销
- 插件增加约30%耗时（基于轻量方法如EATA），主要来自风格存储池聚类和模型存储池维护。虽然内存开销低，但对于实时性敏感的应用仍有挑战。

### 实验覆盖
- 未在**更大尺度（如ImageNet-R, ImageNet-Sketch）**或**视频流**上验证。
- **分割任务**仅测试了Cityscapes→ACDC，未覆盖更多场景（如城市→野外）。
- **未探讨域数量上限K_max的有效设定策略**：论文选16，但理论上需根据数据复杂度调整，实际部署需人工预估或引入终止条件。
- **部分基线未作为插件测试**（如RoTTA、PeTTA），可能造成比较不公平（尤其是对持久TTA方法）。

### 潜在偏差
- 风格特征依赖于VGG-19，虽然效果好，但**引入额外模型**，且其局限性（无法捕获高级语义）在细粒度域区分上可能不足。
- 方法**要求有少量源域样本**计算阈值τ，虽可接受，但在极端场景（源域完全不可用）下受限。
- 对**批次顺序和批次大小敏感**（小批次下风格估计方差大，影响聚类准确性）。

### 其他局限
- **自适应更新触发**缺失：当前每批都更新，可能造成不必要的开销；论文提出可加入触发机制，但未实现。
- 在**CCC（渐变）设置下**增益相对较小（约1.5%），说明存储池在渐进变化中的优势有限，需结合更精细的时序建模。

（完）
