---
title: Monitoring Risks in Test-Time Adaptation
title_zh: 监控测试时间适应中的风险
authors: "Mona Schirmer, Metod Jazbec, Christian A. Naesseth, Eric Nalisnick"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=TzHX2RWUdE"
tags: ["query:tta"]
score: 8.0
evidence: 测试时间适应中的风险监控
tldr: 现有测试时间自适应（TTA）方法能处理分布偏移，但模型性能仍可能严重下降而未被察觉。本文提出将TTA与风险监控框架结合，基于序贯测试和置信序列来追踪预测性能并报警。此方法扩展了现有监控工具以适配TTA场景。实验表明能有效检测需要离线重训的失败情况。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-tzhx2rwude/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 344, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tzhx2rwude/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 627, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tzhx2rwude/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1407, \"height\": 1303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tzhx2rwude/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 542, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tzhx2rwude/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 609, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tzhx2rwude/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1407, \"height\": 1303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tzhx2rwude/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1359, \"height\": 1002, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tzhx2rwude/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1420, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tzhx2rwude/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1418, \"height\": 1225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tzhx2rwude/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1007, \"height\": 1264, \"label\": \"Figure\"}]"
motivation: TTA虽能适应分布偏移，但性能下降仍可能严重到需要离线重训，当前缺乏监控手段。
method: 将TTA与基于置信序列的序贯测试框架配对，实时追踪预测性能并触发警报。
result: 在多种分布偏移场景下有效检测到性能显著下降，及时发出告警。
conclusion: 提出一种实用的TTA风险监控方案，提升部署可靠性。
---

## Abstract
Encountering shifted data at test time is a ubiquitous challenge when deploying predictive machine learning models. Test-time adaptation (TTA) methods aim to address this issue by continuously adapting a deployed model using only unlabeled test data. While TTA can help extend the model's deployment lifespan, there are scenarios where, despite adaptation, the drop in the model's performance remains significant enough to warrant taking the model offline and retraining. To detect such failure cases, we propose pairing TTA with risk monitoring frameworks that track predictive performance and raise alerts when predefined performance criteria are violated. Specifically, we extend existing monitoring tools based on sequential testing with confidence sequences to accommodate scenarios where the model is updated at test time and no test labels are available to estimate the performance metrics of interest. Our extensions unlock the application of rigorous statistical risk monitoring in TTA and we demonstrate applicability of our proposed TTA monitoring framework across a representative set of TTA methods, datasets and distribution shift types.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

测试时间适应（Test-Time Adaptation, TTA）方法通过仅使用无标签测试数据持续更新模型参数，以应对部署时遇到的分布偏移，从而延长模型的有效生命周期。然而，TTA并非万能：在严重偏移或长时间适应后，模型性能可能急剧下降甚至完全崩溃（如预测坍塌），并且这种失败往往是“无声”的，难以被及时发现。现有风险监控方法要么需要测试标签（如Podkopaev & Ramdas的序贯测试），要么假设模型固定不变（如Amoukou等人的无监督监控），无法直接应用于模型持续更新的TTA场景。因此，**核心问题**是：如何在无测试标签的条件下，对持续自适应模型进行严格的统计风险监控，及时发出需要离线重训的警报，同时控制误警率。

### 2. 论文提出的方法论：核心思想、关键技术细节

**核心思想**：将序贯假设检验框架扩展到TTA场景，利用置信序列（Confidence Sequences）构建源风险的上界和测试运行风险的下界，当测试下界超过源上界加容忍阈值时触发警报。关键创新在于：  
- **模型适应**：定义针对模型序列 \(p_{1:t}\) 的假设检验，警报函数 \(\Phi_t^a\) 使用适应后模型的损失序列构建下界。  
- **无监督下界**：引入损失代理（loss proxy）\(u = g(x, p)\)，例如模型不确定性（\(1 - \max_c p_c(x)\)），并基于**假设1**（代理需能分离高/低损失样本且跨分布稳健），推导出无监督运行测试风险下界 \(B_t\)（命题1）：  
  \[
  \bar{R}_t(p_{1:t}) \ge \tau \left( \frac{1}{t} \sum_{k=1}^t P_{P_k}(u_k > \lambda_k) - P_{P_0}(u_0 > \lambda_0, z_0 \le \tau) \right)
  \]  
  其中 \(\tau\) 为损失阈值，\(\lambda\) 为代理阈值。  
- **在线阈值校准**：使用源校准集通过最大化F1分数同时选择 \(\tau\) 和 \(\lambda_0\)，并在每个适应步骤后基于当前模型重新校准 \(\lambda_k\)，以保证假设1成立。  
- **提升检测功率**：对于0-1损失，可省略 \(\tau\)（推论1）；对于连续损失（如Brier），可改为检验“高损失概率”而非期望风险（式8），以收紧界。

**算法流程**：  
1. 从源分布获取校准集，计算源模型损失和代理值，选出初始阈值。  
2. 对每个测试批次：  
   - 执行TTA更新获得模型 \(p_k\)；  
   - 用校准集评估 \(p_k\) 并更新代理阈值 \(\lambda_k\)；  
   - 在测试批次上计算代理值，构建下界置信序列；  
   - 若下界超过源上界+容忍度，触发警报并停止适应；否则继续预测。

### 3. 实验设计

- **数据集**：  
  - ImageNet-C（合成损坏，高斯噪声，5个严重等级）  
  - Yearbook（真实时间漂移，人像性别分类）  
  - FMoW-Time（卫星图像土地利用分类，跨年份漂移）  
- **TTA方法**：TENT、CoTTA、SAR、SHOT、T3A、STAD（共6种）  
- **基准对比**：  
  - 监督下界 \(\hat{L}_t^a\)（oracle，使用测试标签）  
  - 朴素代理 \(\hat{L}_t^c\)（直接用代理代替损失，无理论保证）  
  - 静态模型无监督下界 \(\hat{L}_t^d\)（Amoukou等人方法）  
- **评估指标**：能否及时检测风险违反（当运行风险超过源风险+容忍度）、是否有误警、下界与真实运行风险的接近程度。

### 4. 资源与算力

论文提及使用 **NVIDIA RTX 6000 Ada 48GB GPU** 进行计算，但未说明具体用量（如GPU数量或总时长）。实验运行了20个随机种子（部分实验10个种子），每个实验均基于公开预训练模型，计算开销主要来自在线校准（每次适应步需在Ncal=1000的校准集上评估模型）。

### 5. 实验数量与充分性

- **核心实验**（图2-3）：在3个数据集×6种TTA方法下，展示了 \(\hat{L}_t^b\) 能紧密跟踪真实风险，正确触发/不触发警报。  
- **检测模型坍塌**（图4）：在故意引发TENT坍塌的高学习率设置下验证了有效性。  
- **替代代理消融**（图5、A.2）：对比了不确定性、能量得分、熵、距离原型等代理，结果表明不确定性通用性强，但对last-layer方法需改用距离。  
- **阈值敏感性**（A.3）：缩减校准集大小（100 vs 1000）和降低校准频率（每1~20步一次），发现影响较小。  
- **标签偏移**（A.5）：在Yearbook上引入标签偏移测试，仍能检测。  
- **假设验证**：全程跟踪 \(\Delta_t^b\) 以确保假设1成立。  

实验覆盖了合成/真实漂移、严重/渐进偏移、各种TTA范式和代理选择，**充分性较高**，且通过多次随机种子控制变异性，**公平客观**。

### 6. 论文的主要结论与发现

1. 提出的无监督下界 \(\hat{L}_t^b\) 能紧密逼近监督oracle下界，检测延迟小。  
2. 在合成损坏（ImageNet-C严重5）、真实漂移（Yearbook）下均能可靠报警，而在无风险违反的FMoW和ID数据上保持沉默。  
3. 对于极端失败（模型坍塌）也能有效检测，尽管此时模型自身输出已不可靠。  
4. 代理选择至关重要：模型不确定性对多数TTA有效；距离原型更适合last-layer方法；能量得分和熵效果相似或更差。  
5. 假设1在实践中基本满足（仅静态模型在严重偏移下偶有违反）。  
6. 校准集大小可缩减至100，校准频率可降低至每20步一次，仍保持合理性能。

### 7. 优点

- **理论保证**：基于置信序列的序贯测试提供时间一致的误警率控制。  
- **无监督性**：完全无需测试标签，仅需少量源校准集。  
- **通用性**：不假设漂移类型、TTA方法或模型结构，代理可选多样。  
- **实用性**：在线校准策略适应模型变化，计算开销可控。  
- **全面实验**：覆盖多种漂移、TTA方法和代理，并验证了稳健性边界。

### 8. 不足与局限

- **假设验证依赖标签**：假设1的验证仍需要测试标签，尽管经验上成立，但无诊断工具提前检测违反。  
- **检测延迟**：相比监督方法，无监督下界可能延迟报警，对延迟高敏感场景可能不够。  
- **需要源校准集**：依赖少量标记源数据，极端场景下可能受限。  
- **静态模型失效**：当模型不更新时，默认的阈值校准方法可能导致假设违反（ImageNet-C实例），未来需改进。  
- **代理选择需匹配TTA类型**：对last-layer方法默认不确定性松动，需设计更鲁棒的代理。  
- **高学习率坍塌仅实验一类**：未系统评估其他失效模式（如对抗攻击）或更大规模模型。

（完）
