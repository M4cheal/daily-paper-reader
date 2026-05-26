---
title: "Rethinking Entropy in Test-Time Adaptation: The Missing Piece from Energy Duality"
title_zh: 重新审视测试时间自适应中的熵：来自能量对偶性的缺失部分
authors: "Mincheol Park, Heeji Won, Won Woo Ro, Suhyun Kim"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=BKYFAutCDZ"
tags: ["query:tta"]
score: 9.0
evidence: TTA中熵最小化的理论分析
tldr: 现有TTA方法依赖熵最小化，但本文通过能量对偶性发现熵最小化不能保证能量降低和可靠似然估计。核心方法分析熵与能量的二元关系，证明两者需同时优化。实验表明同时减少熵和能量提升自适应效果。为TTA理论基础提供重要修正。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkyfautcdz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkyfautcdz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkyfautcdz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 515, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkyfautcdz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 332, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkyfautcdz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkyfautcdz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkyfautcdz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkyfautcdz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkyfautcdz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1455, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkyfautcdz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1456, \"height\": 170, \"label\": \"Table\"}]"
motivation: 熵最小化在TTA中虽常用但不足以确保可靠预测，缺乏理论解释。
method: 揭示熵与能量的对偶关系，提出同时优化二者的方法。
result: 理论证明和实验验证表明联合优化熵和能量优于单独熵最小化。
conclusion: 为TTA提供了更坚实的理论基础，指导设计更有效的目标函数。
---

## Abstract
Test-time adaptation (TTA) aims to preserve model performance under distribution shifts. Yet, most existing methods rely on entropy minimization for confident predictions. This paper re-examines the sufficiency of entropy minimization by analyzing its dual relationship with energy. We view energy as a proxy for likelihood, where lower energy indicates higher observability under the learned distribution. We uncover that entropy and energy are tightly associated, controlled by the model’s confidence or ambiguity, and show that simultaneous reduction of both is essential. Importantly, we reveal that entropy minimization alone neither ensures energy reduction nor supports reliable likelihood estimation, and it requires explicit discriminative guidance to reach zero entropy. To combat these problems, we propose a twofold solution. First, we introduce a likelihood-based objective grounded in energy-based models, which reshape the energy landscape to favor test samples. For stable and scalable training, we adopt sliced score matching—a sampling-free, Hessian-insensitive approximation of Fisher divergence. Second, we enhance entropy minimization with a cross-entropy that treats the predicted class as a target to promote discriminability. By counterbalancing entropy and energy through the solution of multi-objective optimization, our unified TTA, ReTTA, outperforms existing entropy- or energy-based approaches across diverse distribution shifts.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：测试时自适应（TTA）旨在应对测试数据分布偏移（如光照变化、传感器噪声等）导致的模型性能下降。现有主流TTA方法几乎都依赖于熵最小化（Entropy Minimization, EM）来促使模型输出自信预测。然而，本文质疑“仅靠熵最小化是否足以实现有效的TTA”。
- **核心问题**：作者通过分析熵与其对偶量——能量（Energy，反映数据在模型分布下的似然）的二元关系，发现熵最小化并不保证能量降低，也无法确保可靠的似然估计。单独优化熵会导致模型无法充分利用测试数据分布信息，且难以达到真正的零熵状态（即完全自信预测）。
- **整体含义**：TTA需要同时最小化熵和能量，并辅以显式的判别性引导，才能应对多样化的分布偏移。本文提出的ReTTA统一框架将能量优化与判别性引导结合，显著优于纯熵或纯能量方法。

## 2. 论文提出的方法论

### 2.1 核心思想
- 利用能量与熵的共轭对偶关系（Fenchel对偶），证明两者紧密耦合：熵最小化仅能增加模型对最可能类的置信度，但无法降低整体能量（即无法提高测试数据在模型分布下的似然）。
- 通过能量-熵分布带分析（Theorem 1），发现数据点分布在多个离散的“带”上，仅靠熵最小化难以从多主逻辑带的区域（k≥2）跃迁到零熵带（k=1），需要额外目标引导。

### 2.2 关键技术细节
- **目标1：基于能量的似然最大化（SSM损失）**  
  采用能量基础模型（EBM）建模边际分布 \( p_\theta(\mathbf{x}_t) \)，通过最大化对数似然降低测试样本能量、提升生成样本能量。为避免MCMC采样不稳定，采用**切片分数匹配（Sliced Score Matching, SSM）**——一种无采样、对Hessian不敏感的Fisher散度近似。损失函数形式（公式15）基于随机投影方向的分数匹配，可高效计算。
- **目标2：目标类别收敛损失（TCC）**  
  将Softmax最可能的类作为伪标签，使用交叉熵损失（公式16）引导模型向单一类收敛，促使熵降至零，弥补EM在低置信度样本上的不足。
- **统一损失**：\( \ell_{\text{ReTTA}} = \ell_{\text{EM}} + \lambda_1(\alpha) \cdot \ell_{\text{SSM}} + \lambda_2 \cdot \ell_{\text{TCC}} \)
  - \( \lambda_1(\alpha) \) 通过多目标优化自适应调整：基于梯度方向求解二次规划，使EM与SSM的平衡自动适应不同分布偏移（公式18）。
  - 默认 \( \lambda_2 = 1 \)。
- **算法流程**：每次测试样本仅观测并更新一次（one-shot TTA），仅更新归一化层的仿射参数（BN/GN/LN），使用SGD优化器。

## 3. 实验设计

### 3.1 数据集与场景
- **主数据集**：ImageNet-C（15种 corruption，分为Noise、Blur、Weather、Digital四组，每种5个严重等级）。
- **附加数据集**：
  - ImageNet-R（渲染物体，大域偏移）
  - ImageNetV2（重新采样的验证集，近域偏移）
  - ImageNet-S（草图，灰度图）
- **场景**：
  - **轻度偏移**：标准corruption（severity 5）
  - **在线标签偏移**：设定标签不平衡比=8（SAR设置）
  - **终身自适应**：连续应对多种corruption（遵循EATA协议）

### 3.2 对比方法
- **熵基方法**：MEMO、Tent、EATA、SAR、DeYO
- **能量基方法**：TEA、AEA
- 所有对比方法在相同设置下运行，结果取自原文或复现。

### 3.3 模型与超参数
- 模型架构：ResNet-50（BN/GN）、ViT-Base（LN）
- 优化器：SGD（momentum 0.9），batch size 64，学习率 ResNet 0.00025 / ViT 0.001
- 实现细节：采用DeYO的数据采样和损失重加权策略，更新归一化层仿射参数

## 4. 资源与算力

- **论文未明确提及使用的GPU型号、数量及训练时长**。仅在附录中提到实验在数据中心共享资源上运行，未提供具体算力统计。因此无法评估计算开销总量，但可推断：由于TTA仅更新少量仿射参数且为one-shot，单次实验计算量相对较小（每个样本前向+一次反向）。

## 5. 实验数量与充分性

### 实验数量
- 主要结果：Table 1（轻度偏移，ResNet-50 BN，15种corruption+平均）、Table 2（在线标签偏移，两类架构+15种corruption）
- 消融实验（Ablation Study）：
  - Figure 4(a)：λ2参数敏感性
  - Figure 4(b)：SSM替代方案（SM、SSM-VR）
  - Figure 4(c)：投影分布选择（Rademacher、Sphere、Normal）
  - Table 3：组件消融（SSM、TCC分别及组合）
  - Table 4：ReTTA在三种SOTA EM方法（EATA、SAR、DeYO）上的适配增益
- 额外数据集验证：Table 5（ImageNet-R、ImageNetV2、ImageNet-S）
- 终身自适应验证：Table 6

### 充分性评价
- **充分**：涵盖了多种分布偏移类型（噪声、模糊、天气、数字）、不同严重等级、不同架构、不同场景（轻度、标签偏移、终身）。
- **客观公平**：与多个代表性基线在同一设置下对比，使用标准ImageNet-C benchmark，并报告了标准差（三次随机运行）。
- 消融实验系统验证了每个组件的必要性，且对超参数λ2和投影分布进行了敏感性分析。

## 6. 论文的主要结论与发现

- **理论贡献**：证明了熵与能量的对偶关系，揭示了仅最小化熵的三个缺陷：①无法保证能量降低；②不能可靠估计似然；③难以达到零熵状态（尤其在低置信度样本）。
- **方法贡献**：提出ReTTA——统一熵、能量和判别性引导的TTA框架，其中SSM实现无采样能量降低，TCC实现零熵收敛，自适应平衡系数应对不可预测的分布偏移。
- **实验结论**：
  - 在ImageNet-C轻度偏移下，ReTTA平均准确率49.2%，超越所有对比方法（DeYO 48.6%）；
  - 在在线标签偏移下，ResNet-50 GN平均提升3.6%（47.5% vs 43.9%），ViT-Base平均提升2.5%（64.8% vs 62.3%）；
  - 在ImageNet-R、ImageNetV2、ImageNet-S上同样表现优异或持平；
  - 在终身自适应设置中，ReTTA在保持源域性能的同时提升自适应效果（+0.3%）。

## 7. 优点

1. **理论深度**：从能量-熵的对偶性出发，给出了熵最小化不足的严格数学分析（Fenchel对偶、能量-熵分布带定理），为TTA提供了坚实的理论基础。
2. **方法创新**：引入切片分数匹配（SSM）作为无采样、高效的似然最大化目标，避免了能量基础模型训练中的MCMC不稳定性；TCC损失巧妙利用交叉熵引导零熵收敛。
3. **自适应机制**：自调整系数λ1(α)利用多目标优化自动平衡熵与能量，无需手动调节，对不同corruption有鲁棒性。
4. **实验全面性**：涵盖多种分布偏移、多种架构、多种场景（轻度、标签偏移、终身），且通过消融实验验证每个组件的贡献。
5. **实用性**：one-shot更新，仅修改归一化层参数，计算开销小，易于部署。

## 8. 不足与局限

1. **算力资源未披露**：未提供GPU型号、数量、训练时长，其他研究者难以复现和比较计算开销。
2. **实验覆盖范围有限**：仅使用ImageNet系数据集（高分辨率、1K类），未在医学图像、遥感、语音等非视觉领域验证，泛化性待检验。
3. **对特定corruption提升有限**：在Defocus、Glass blur等某些corruption上，ReTTA相比基线提升较小甚至持平，可能由于SSM对平滑型corruption不敏感。
4. **TCC可能引入伪标签噪声**：在极端分布偏移下，模型预测可能严重错误，用其作为目标进行交叉熵训练可能放大错误，论文未讨论该风险。
5. **终身自适应性能尚待提升**：虽然ReTTA在终身场景有提升，但绝对增益仍较小（+0.3%），可能受限于仅更新仿射参数。
6. **超参数λ2固定**：尽管λ2在实验中设为1，但未说明该值是否在不同场景下最优，缺乏类似λ1的自适应机制。

（完）
