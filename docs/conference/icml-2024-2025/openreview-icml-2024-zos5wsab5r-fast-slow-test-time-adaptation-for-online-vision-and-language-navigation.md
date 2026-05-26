---
title: Fast-Slow Test-Time Adaptation for Online Vision-and-Language Navigation
title_zh: 在线视觉语言导航的快慢测试时自适应
authors: "Junyu Gao, Xuan Yao, Changsheng Xu"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=Zos5wsaB5r"
tags: ["query:tta"]
score: 9.0
evidence: 多模态视觉语言导航的TTA
tldr: 在线视觉语言导航需要同时处理样本间指令执行和样本内多步决策，现有TTA方法更新频率难以平衡。本文提出快慢双速TTA，结合快速和慢速更新策略，在在线VLN中实现了高效且稳定的自适应。实验表明该方法显著提升了导航成功率。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-zos5wsab5r/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 843, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-zos5wsab5r/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1779, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-zos5wsab5r/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 832, \"height\": 1004, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-zos5wsab5r/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1432, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-zos5wsab5r/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1247, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-zos5wsab5r/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1246, \"height\": 649, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 546, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 848, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1738, \"height\": 672, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 854, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 853, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1772, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1242, \"height\": 754, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1243, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1765, \"height\": 682, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1153, \"height\": 689, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1739, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-zos5wsab5r/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1150, \"height\": 307, \"label\": \"Table\"}]"
motivation: 在线VLN中快更新导致参数剧变，慢更新则动态适应不足。
method: 提出快慢双速TTA，融合频繁更新与稀疏更新的优势。
result: 在多个VLN基准上取得了最优导航成功率。
conclusion: 快慢双速TTA有效平衡了在线VLN中的适应速度与稳定性。
---

## Abstract
The ability to accurately comprehend natural language instructions and navigate to the target location is essential for an embodied agent. Such agents are typically required to execute user instructions in an online manner, leading us to explore the use of unlabeled test samples for effective online model adaptation. However, for online Vision-and-Language Navigation (VLN), due to the intrinsic nature of inter-sample online instruction execution and intra-sample multi-step action decision, frequent updates can result in drastic changes in model parameters, while occasional updates can make the model ill-equipped to handle dynamically changing environments. Therefore, we propose a Fast-Slow Test-Time Adaptation (FSTTA) approach for online VLN by performing joint decomposition-accumulation analysis for both gradients and parameters in a unified framework. Extensive experiments show that our method obtains impressive performance gains on four popular benchmarks. Code is available at https://github.com/Feliciaxyao/ICML2024-FSTTA.

---

## 论文详细总结（自动生成）

# 论文详细总结：Fast-Slow Test-Time Adaptation for Online Vision-and-Language Navigation

## 1. 核心问题与整体含义（研究动机和背景）

- **研究问题**：在线视觉语言导航（Online VLN）中，智能体需要实时执行自然语言指令并在动态环境中导航，同时利用无标签的测试样本进行模型自适应。然而，现有的测试时自适应（TTA）方法在应对 VLN 的**样本间连续指令执行**和**样本内多步动作决策**时，面临**适应性-稳定性困境**：
  - **频繁更新**（每步或少量步更新）虽能快速适应环境变化，但容易导致模型参数剧烈变化、累积误差和灾难性遗忘。
  - **稀疏更新**（每个样本只更新一次）则可能使模型无法充分适应动态变化的环境。
- **研究意义**：探索一种适用于在线 VLN 的高效 TTA 方法，使智能体在测试过程中能积累经验并提升导航能力，同时避免过拟合和遗忘问题。

## 2. 方法论

### 核心思想
提出**快慢双速测试时自适应（Fast-Slow Test-Time Adaptation, FSTTA）**，在统一的梯度-参数分解-累积框架下，交替执行快速更新和慢速更新，以平衡模型的适应性和稳定性。

### 关键技术细节

- **基础模型**：采用已有的 VLN 模型（如 DUET、HM3D），仅对最后的 LayerNorm 层进行更新（其余参数冻结）。
- **测试时训练目标**：使用熵最小化（Entropy Minimization）损失，降低当前可导航节点概率分布的熵。
- **快速更新阶段（Fast Update）**：
  - 每 \( M \) 个动作步收集 \( M \) 个梯度向量 \(\{g_{j,m}\}\)。
  - 通过主成分分析（PCA）对梯度矩阵进行**分解**，得到局部坐标基 \(\{u_{j,d}\}\) 和对应的特征值 \(\lambda_{j,d}\)。
  - 采用 **梯度分解-累积** 策略：根据特征值大小（方差）自适应地聚合梯度分量，抑制发散方向、增强一致方向，得到亲和谐方向 \(\nabla^{(fast)}_j\)。
  - 引入**动态学习率缩放**：利用梯度协方差矩阵的迹（方差和）来动态调整学习率，当方差偏离历史均值较大时减小更新步长。
- **慢速更新阶段（Slow Update）**：
  - 每 \( N \) 个测试样本执行一次，记录历史模型参数状态。
  - 对参数矩阵进行类似的**分解-累积**分析，计算参数变化的主方向（大特征值对应的轴）。
  - 利用历史参数偏差的加权和作为参考方向，组合主方向得到优化路径 \(\nabla^{(slow)}_l\)，直接调制模型参数。
  - 采用固定学习率，不进行动态缩放，以保证稳定性。
- **交替执行**：在测试过程中，快速更新在样本内部的多个动作步间进行，慢速更新在样本间定期触发，两者交替进行。

### 算法流程（文字描述）
1. 初始化模型参数。
2. 对于每个测试样本，遍历每个动作步：
   - 计算熵损失并得到梯度。
   - 每 \( M \) 步执行一次快速更新：收集最近 \( M \) 个梯度，进行PCA分解，得到亲和谐梯度，并按动态学习率更新参数。
3. 每处理完 \( N \) 个样本，执行一次慢速更新：收集最近 \( N \) 个模型状态，进行PCA分解，得到参数变化主方向，结合参考方向直接调整参数。
4. 重复直到所有测试样本处理完毕。

## 3. 实验设计

### 数据集与Benchmark
- **REVERIE**：远程目标指代表达导航，含 10,567 张全景图、21,702 条高层指令。
- **R2R**：逐步指令导航，含 10,800 全景视图、7,189 条轨迹。
- **SOON**：场景导向目标导航，含 3,848 条指令、超 3 万条长距离轨迹。
- **R2R-CE**：连续环境版本，约 16,000 条指令-轨迹对。

### 评估指标
- TL（轨迹长度）、NE（导航误差）、SR（成功率）、SPL（成功率加权路径长度）、OSR（Oracle 成功率）、RGS（远程接地成功率）、RGSPL（RGS 加权路径长度）。

### 对比方法
- **TTA 方法**：Tent、EATA、CoTTA、NOTE、SAR、ViDA，以及基于 Tent 的不同更新间隔策略（INT-1 至 INT-4）和稳定更新策略。
- **VLN 基线模型**：DUET、HM3D、WS-MGMap、BEVBert 等。
- **消融实验**：逐步添加快速更新、动态学习率、慢速更新的效果。

### 实验设置
- 在线 VLN 模拟：打乱测试样本顺序，批量大小为 1，每个样本/动作步只前向一次。
- 更新层数：仅更新最后 4 个 LayerNorm 层。
- 超参数：快速更新间隔 \(M=3\)，慢速更新间隔 \(N=4\)；动态学习率阈值 \(\tau=0.7\)，动量 \(\rho=0.95\)；基数学习率 \(\hat{\gamma}^{(fast)}=6\times10^{-4}\)，\(\gamma^{(slow)}=1\times10^{-3}\)（REVERIE 上）。

## 4. 资源与算力

- **GPU 型号**：单张 RTX 3090（24GB 显存）。
- **训练时长**：论文未明确说明训练时长或 GPU 数量，仅提及所有实验在 RTX 3090 上进行。
- **代码**：开源在 GitHub（https://github.com/Feliciaxyao/ICML2024-FSTTA）。

## 5. 实验数量与充分性

- **实验数量**：
  - 在 **4 个 VLN 基准**（REVERIE、R2R、SOON、R2R-CE）的验证集和测试集上进行了全面评估。
  - 对比了 **6 种主流 TTA 方法**及其变体（如不同更新间隔）。
  - 进行了 **消融实验**（逐步添加快速更新、动态学习率、慢速更新）。
  - 进行了 **参数分析**（对快速/慢速更新的步长和学习率进行敏感性实验）。
  - 额外验证了 **灾难性遗忘**（在验证 seen 集上重新测试）、**混合场景泛化**（seen+unseen 组合）以及 **跨域迁移**（离散→连续环境）。
- **充分性评估**：实验设计较为全面，覆盖了多个数据集、多种评估指标、多个对比方法，并进行了详细的消融和参数分析。实验设置合理，结果统计上报告了多次运行的平均值和标准差（通常 5 次），具有统计可靠性。因此，实验是充分且客观的。

## 6. 主要结论与发现

- **FSTTA 显著提升 VLN 性能**：在 REVERIE 验证 unseen 集上，与基线 DUET 相比，SR 提升 7.2%（46.98%→54.15%），SPL 提升 2.7%（33.73%→36.41%）。
- **优于现有 TTA 方法**：在 REVERIE 上，FSTTA 的 SR 达到 54.15%，远超 SAR（48.00%）和 Tent（46.87%），且时间开销适中。
- **平衡适应性与稳定性**：快速更新应对短期环境变化，慢速更新防止长期遗忘，两者结合有效缓解了频繁/稀疏更新的不足。
- **不引起灾难性遗忘**：在验证 seen 集上重新测试时，FSTTA 性能与基线相当，说明模型未遗忘先前知识。
- **在连续环境中同样有效**：在 R2R-CE 上，FSTTA 提升 DUET 的 SR 约 2%；在跨域（离散→连续）迁移任务中也表现出鲁棒性。

## 7. 优点

- **方法创新**：首次将快慢双速更新框架引入 VLN 的测试时自适应，统一了梯度和参数两个层面的分解-累积分析，思路新颖。
- **平衡性设计**：通过快速更新保持适应性，慢速更新维持稳定性，解决了 TTA 在序列决策任务中的关键矛盾。
- **高效性**：仅更新少量归一化层（4 个 LN），计算开销较低；动态学习率缩放进一步提升了收敛效率。
- **实验充分**：在多个标准 VLN 基准上进行了广泛验证，与多种 SOTA TTA 方法对比，消融实验和参数分析完善。
- **泛化性强**：不仅在离散环境中表现优异，在连续环境和跨域场景中也有良好迁移能力。
- **开源代码**：促进可复现性和后续研究。

## 8. 不足与局限

- **更新范围受限**：仅更新归一化层，对于不包含 LN 层的模型需要额外引入并重新训练，适用性有限。
- **模拟在线环境**：实验通过打乱测试样本顺序模拟在线 VLN，但未在真实在线部署场景中验证，存在一定偏差风险。
- **计算开销**：尽管 TTA 方法增加了一定时间（约 30ms/指令），但相比于基线仍有额外成本；快速更新中的 SVD 分解可能成为瓶颈。
- **固定更新频率**：快速和慢速的更新间隔（M、N）是固定的，未实现自适应触发，可能无法最优适应不同难度的任务。
- **未考虑其他层类型**：未来工作可探索更新更多层（如全连接层）以提升性能，但需注意过拟合风险。
- **稳定性与泛化的权衡**：尽管整体表现好，但在某些指标（如 RGSPL 在连续环境中）提升不显著，甚至略有下降，说明仍有改进空间。

（完）
