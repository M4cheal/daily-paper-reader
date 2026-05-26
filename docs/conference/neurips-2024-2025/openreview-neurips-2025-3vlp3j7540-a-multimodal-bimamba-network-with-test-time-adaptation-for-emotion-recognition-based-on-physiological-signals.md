---
title: A Multimodal BiMamba Network with Test-Time Adaptation for Emotion Recognition Based on Physiological Signals
title_zh: 基于生理信号的多模态BiMamba网络与测试时间自适应情感识别
authors: "Ziyu Jia, Tingyu Du, Zhengyu Tian, Hongkai Li, Yong Zhang, Chenyu Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3vLp3J7540"
tags: ["query:tta"]
score: 8.0
evidence: 面向情感识别的多模态测试时间自适应
tldr: 多模态生理信号情感识别面临长程依赖建模和缺失模态性能下降问题。本文提出BiM-TTA，包含双向Mamba网络建模模态内长程依赖和模态间相关性，以及多模态TTA策略处理缺失数据。在缺失模态场景下，TTA动态调整模型以适应可用信号。实验表明对缺失模态鲁棒，优于基线。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 878, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1309, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1200, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1218, \"height\": 873, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1088, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 998, \"height\": 1026, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1020, \"height\": 256, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 865, \"height\": 589, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1397, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1398, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1074, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 457, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1366, \"height\": 226, \"label\": \"Table\"}]"
motivation: 多模态情感识别中长程依赖建模困难且缺失模态时性能显著下降。
method: 设计双向Mamba网络捕获跨模态依赖，并引入测试时间自适应策略处理缺失模态。
result: 在多个生理信号数据集上，缺失模态时仍保持高情感识别准确率。
conclusion: 将TTA与高效序列模型结合，提升了多模态情感识别的实用性。
---

## Abstract
Emotion recognition based on physiological signals plays a vital role in psychological health and human–computer interaction, particularly with the substantial advances in multimodal emotion recognition techniques. However, two key challenges remain unresolved: 1) how to effectively model the intra-modal long-range dependencies and inter-modal correlations in multimodal physiological emotion signals, and 2) how to address the performance limitations resulting from missing multimodal data. In this paper, we propose a multimodal bidirectional Mamba (BiMamba) network with test-time adaptation (TTA) for emotion recognition named BiM-TTA. Specifically, BiM-TTA consists of a multimodal BiMamba network and a multimodal TTA. The former includes intra-modal and inter-modal BiMamba modules, which model long-range dependencies along the time dimension and capture cross-modal correlations along the channel dimension, respectively. The latter (TTA) mitigates the amplified distribution shifts caused by missing multimodal data through two-level entropy-based sample filtering and mutual information sharing across modalities. By addressing these challenges, BiM-TTA achieves state-of-the-art results on two multimodal emotion datasets.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：基于生理信号（如EEG、EOG、EMG、ECG、GSR）的情感识别在心理健康和人机交互中具有重要价值，因为它能客观反映真实情绪状态。然而，多模态生理信号情感识别面临两大核心挑战：
  - **挑战1**：如何有效建模模态内的长程时间依赖（情绪变化是渐进过程）以及模态间的复杂相关性（如不同生理信号在情绪波动时的协同变化）。传统CNN难以捕捉长程依赖，Transformer注意力缺乏显式时序滤波，且难以建模高阶跨模态关系。
  - **挑战2**：实际采集过程中，由于出汗、姿势变化或电极接触不良等因素，常导致部分模态数据缺失。这会放大训练集和测试集之间的分布偏移，严重损害模型性能。现有方法多在训练阶段处理缺失，缺乏测试时的灵活适应能力。
- **整体含义**：论文旨在提出一种既能高效建模多模态生理信号的长程依赖与跨模态交互，又能在缺失数据场景下通过测试时自适应保持稳健性能的统一框架。

### 2. 论文提出的方法论
- **核心思想**：结合**双向Mamba（BiMamba）**的状态空间模型优势（选择机制、显式全局状态变量）与**测试时自适应（TTA）**策略，分别解决两个挑战。
- **关键技术细节**：
  - **多模态BiMamba网络**：
    - **模态内BiMamba模块**：对每个模态独立处理。首先用初始化编码器提取浅层特征 \(h_i\)；然后通过BiMamba结构进行双向状态空间建模：前向和反向分别应用SSM，并采用门控机制（SiLU激活）过滤噪声；最后用线性投影和残差连接得到输出特征 \(u_i\)。
    - **模态间BiMamba模块**：将所有模态特征沿通道维度拼接，并交换时间与通道维度，得到矩阵 \(m\)；然后再次通过BiMamba沿通道维度进行双向建模，使不同模态的特征在状态传递中充分交互，捕捉跨模态相关性。
    - **辅助任务**：每个模态独立输出分类概率，计算交叉熵损失 \(L_i\)，并与主分类损失 \(L_{task}\) 加权求和形成总训练损失 \(L_{train}\)，防止单一模态过拟合。
  - **多模态TTA**：
    - **两级熵样本过滤**：保留**低多模态熵**（预测确定性强、接近源域分布）且**高单模态熵**（依赖多模态信息、信息丰富）的样本。阈值采用动态递增策略（\(\gamma_m, \gamma_u\)），使模型逐渐从弱偏移样本适应到强偏移样本。
    - **跨模态互信息共享**：计算每个模态预测概率 \(p(\hat{y}_i|x_i)\) 与互补概率（其他模态平均）及多模态预测概率的KL散度损失 \(L_{mis}\)，促使信息在模态间对齐，避免严重损坏模态误导其他模态。
    - **优化细节**：采用权重项 \(\alpha(x)\) 降低高熵样本贡献；仅微调初始编码器的第一卷积层、模态间BiMamba的第一全连接层及所有BN层（外科微调），保持稳定性并降低计算量。

### 3. 实验设计
- **数据集**：
  - **DEAP**：32名被试，EEG（32通道）+ 8个外周信号（EOG、EMG等），128Hz采样，二分类（高/低效价、高/低唤醒度）。
  - **MAHNOB-HCI**：27名被试（去除3名无效），EEG（32通道）+ ECG、GSR等，256Hz采样，同样二分类。
- **数据缺失模拟**：随机屏蔽0.2/0.4/0.6/0.8比例的数据，模拟从轻度到重度缺失。
- **基准方法**：
  - 情感识别基线：SVM、EEGNet、ACRNN、HetEmotionNet、TSception、LGGNet、EEG-Deformer、MambaFormer、SST、VSGT。
  - TTA基线：No Adapt（无适应）、Tent（熵最小化）、EATA（可靠样本选择）、READ（调整自注意力融合）、2LTTA（两级目标函数）。
- **评价指标**：分类准确率（Accuracy），采用试验级别10折交叉验证，确保同一试验不跨训练/测试集。

### 4. 资源与算力
- **硬件**：NVIDIA RTX A4000 (16GB) 单GPU。
- **训练时间**：单次训练（30 epochs）约60分钟。
- **模型规模**：仅22,431个参数，FLOPs约1.18M，GPU内存占用2.29MB，非常轻量级。

### 5. 实验数量与充分性
- **实验数量**：包含以下主要实验组：
  - 无缺失数据对比（表1）：在DEAP和MAHNOB-HCI上比较效价和唤醒度准确率。
  - 缺失数据对比（表2&3）：四种缺失比例下，BiM-TTA与TTA基线的提升率比较。
  - 粗略消融（图2）：去除BiMamba或TTA对性能的影响。
  - 精细消融（图3&4）：对比不同的模态内建模（单向Mamba/Transformer/LSTM vs. BiMamba）、模态间融合（注意力/MLP vs. BiMamba）、TTA子模块（两级过滤、互信息共享）的有效性。
  - 超参数研究（表5、图7）：对辅助任务权重 \(\alpha_i\)、\(\lambda\)、\(\mu_i\)、迭代次数 \(iter\)、平滑因子 \(\beta\) 进行敏感性分析。
  - 可视化（图5&6）：Grad-CAM显示长程依赖与跨模态生理关联；t-SNE显示TTA缓解分布偏移。
  - 效率比较（表6）：与LGGNet、EEG-Deformer对比参数、推理时间、FLOPs、GPU内存。
- **充分性与公平性**：
  - 使用10折交叉验证，避免数据泄漏。
  - 所有基线修改为多模态版本，实验设置一致。
  - 缺失数据模拟随机掩码，重复性有保障。
  - 消融实验覆盖主要模块，超参数研究展示稳健性。
  - 总体而言，实验设计系统、客观，结论可信。

### 6. 论文的主要结论与发现
- **性能优势**：BiM-TTA在无缺失数据和多种缺失比例下均达到SOTA，尤其在缺失场景下显著优于其他TTA方法（如在DEAP上平均提升1.172%效价、1.309%唤醒度）。
- **双向Mamba有效性**：模态内和模态间BiMamba均优于单向Mamba、Transformer或纯MLP/注意力融合，证明双向状态空间建模对时序依赖和跨模态交互更有效。
- **TTA策略有效性**：两级熵过滤避免了模型被强偏移样本污染；跨模态互信息共享能够从信息完整的模态中学习补充知识，缓解缺失导致的性能下降。
- **轻量与高效**：模型参数量极小，推理速度快，适合实时场景。

### 7. 优点
- **方法创新**：首次将双向Mamba与多模态测试时自适应结合，针对生理信号情感识别的特定挑战（长程依赖+缺失数据）提出系统解决方案。
- **模块化设计**：模态内/间BiMamba可独立替换，辅助任务平衡多模态训练，TTA策略可集成到任意多模态模型。
- **鲁棒性**：在缺失比例高达80%时仍能保持相对稳定，相比其他TTA方法波动更小。
- **可解释性**：Grad-CAM可视化展示了与生理常识一致的跨模态交互（如EOG干扰EEG、EEG诱发延迟的眼动），增强了方法可信度。
- **全面消融与超参分析**：验证了每个组件的贡献，并给出了阈值选择的启发式指导（基于Chebyshev不等式）。

### 8. 不足与局限
- **实时系统评估缺失**：未在真实在线场景（如可穿戴设备）中测试延迟和电池消耗，实际部署可能需要模型压缩。
- **多任务泛化性不足**：仅验证了情感分类任务，作者承认需要在睡眠分期、运动想象等任务上进一步验证。
- **阈值选择依赖经验**：两级熵过滤的阈值虽然基于统计（期望±方差），但超参数 \(\beta, iter\) 等仍需针对数据集调优，泛化到新数据集可能需要重新校准。
- **缺失模式单一**：仅模拟了随机缺失，未考虑结构性缺失（例如某个模态全部丢失）或不同缺失机制（如传感器故障模式），实际场景可能更复杂。
- **未实验更大规模数据集**：DEAP和MAHNOB-HCI样本量较小（各数百试验），在更大规模、更多模态的数据集上的表现尚不明确。
- **未与更复杂的TTA方法比较**：如SAR、TTT++等，可能影响先进性判断（但已涵盖主流多模态TTA）。

（完）
