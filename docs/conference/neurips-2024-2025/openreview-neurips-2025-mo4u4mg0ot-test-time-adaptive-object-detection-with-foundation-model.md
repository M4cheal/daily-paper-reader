---
title: Test-Time Adaptive Object Detection with Foundation Model
title_zh: 基于基础模型的测试时自适应目标检测
authors: "Yingjie Gao, Yanan Zhang, Zhi Cai, Di Huang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=MO4U4mg0oT"
tags: ["query:tta"]
score: 8.0
evidence: 使用多模态基础模型提示的测试时自适应目标检测
tldr: 现有测试时自适应目标检测依赖源数据并假设类别空间相同。本文提出首个基于基础模型的测试时自适应方法，通过多模态提示均值教师框架，利用视觉语言检测器实现无需源数据的自适应，突破了封闭集限制。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1410, \"height\": 614, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1413, \"height\": 918, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1427, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 711, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 583, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1432, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 558, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1409, \"height\": 223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1397, \"height\": 1064, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 999, \"height\": 936, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 998, \"height\": 1096, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mo4u4mg0ot/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 999, \"height\": 1097, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mo4u4mg0ot/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mo4u4mg0ot/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mo4u4mg0ot/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 797, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mo4u4mg0ot/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1011, \"height\": 123, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mo4u4mg0ot/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mo4u4mg0ot/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 871, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mo4u4mg0ot/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 503, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mo4u4mg0ot/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 586, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mo4u4mg0ot/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1301, \"height\": 415, \"label\": \"Table\"}]"
motivation: 克服现有测试时自适应目标检测对源数据依赖和封闭集假设的局限性。
method: 设计多模态提示均值教师框架，结合文本和视觉线索进行测试时自适应。
result: 实现了无需源数据的开放集自适应目标检测，提升了在线自适应能力。
conclusion: 为基础模型驱动的测试时自适应提供了新范式，适用于动态环境。
---

## Abstract
In recent years, test-time adaptive object detection has attracted increasing attention due to its unique advantages in online domain adaptation, which aligns more closely with real-world application scenarios. However, existing approaches heavily rely on source-derived statistical characteristics while making the strong assumption that the source and target domains share an identical category space. In this paper, we propose the first foundation model-powered test-time adaptive object detection method that eliminates the need for source data entirely and overcomes traditional closed-set limitations. Specifically, we design a Multi-modal Prompt-based Mean-Teacher framework for vision-language detector-driven test-time adaptation, which incorporates text and visual prompt tuning to adapt both language and vision representation spaces on the test data in a parameter-efficient manner. Correspondingly, we propose a Test-time Warm-start strategy tailored for the visual prompts to effectively preserve the representation capability of the vision branch. Furthermore, to guarantee high-quality pseudo-labels in every test batch, we maintain an Instance Dynamic Memory (IDM) module that stores high-quality pseudo-labels from previous test samples, and propose two novel strategies-Memory Enhancement and Memory Hallucination-to leverage IDM's high-quality instances for enhancing original predictions and hallucinating images without available pseudo-labels, respectively. Extensive experiments on cross-corruption and cross-dataset benchmarks demonstrate that our method consistently outperforms previous state-of-the-art methods, and can adapt to arbitrary cross-domain and cross-category target data. Code is available at https://github.com/gaoyingjay/ttaod_foundation.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 一、论文的核心问题与整体含义

- **研究动机**：现有测试时自适应目标检测（TTAOD）方法严重依赖源域数据的统计特征（如特征图的均值与方差），并且默认源域与目标域共享完全相同的类别空间。这些假设在实际应用中难以满足，例如自动驾驶中实时适应未知环境或遇到新类别时，源数据不可用、类别集变化。
- **本文目标**：首次将视觉语言基础模型（如 Grounding DINO）引入 TTAOD，提出一种无需任何源数据、能处理开放集（任意类别）的测试时自适应方法，同时保持参数高效性，避免灾难性遗忘预训练知识。

## 二、方法论

- **核心思想**：利用视觉语言检测器的零样本能力，通过参数高效的提示调优（prompt tuning）在测试时在线适应目标域，并设计专用模块保证伪标签质量和表示稳定性。
- **关键技术细节**：
  1. **多模态提示均值教师框架（MPMT）**：
     - 学生模型：仅优化文本提示（\( P_T \)）和视觉提示（\( P_I \)），其余预训练参数冻结。
     - 文本提示调优：在文本编码器输出上添加可学习向量 \( \tilde{E}_T = E_T + P_T \)。
     - 视觉提示调优：在图像编码器的每个 Transformer 层前插入 \( m \) 个可学习令牌 \( P_{I,i} \)，与图像令牌拼接输入。
     - 教师模型：通过指数移动平均（EMA）更新教师提示 \( P^* = \gamma P^* + (1-\gamma)P \)。
     - 损失函数：沿用 Grounding DINO 的对比分类损失 \( L_{cls} \) 和定位损失 \( L_{loc} \)，伪标签由教师模型在弱增强图像上生成并通过阈值 \( th_{pl} \) 过滤。
  2. **测试时暖启动（TTWS）**：
     - 用第一张测试图像的第 \( i \) 层图像令牌的平均池化结果初始化视觉提示 \( P_{I,i} = \text{AvgPool}(E_{I,i}) \)，避免零初始化导致检测失败。
  3. **实例动态记忆模块（IDM）**：
     - 为每个类别维护一个动态队列 \( Q_c \)，存储来自先前测试样本的高质量伪标签三元组（裁剪图像、DINOv2 特征、分类分数）。当队列满时替换最低分实例。
  4. **记忆增强（ME）**：
     - 对当前图像中高置信度预测（分数 > \( th_{me} \)），计算裁剪图像 DINOv2 特征与类别原型 \( v_c \)（队列内平均）的相似度，增强分类分数：\( s''_j = s_j + \alpha \exp(-\beta(1 - \cos)) \)。
  5. **记忆幻觉（MH）**：
     - 对当前批次中无可用伪标签的“负样本”图像，从 IDM 随机采样高质量实例，以随机位置和缩放混合生成幻觉正样本，最多 3 个实例，并设置 IoU 阈值防止重叠。

## 三、实验设计

- **数据集与评测**：
  - **跨腐蚀基准**：Pascal-C（36760 图像，20 类）、COCO-C（5000 图像，80 类），均包含 15 种腐蚀（噪声、模糊、天气、数字等），评测指标为 AP50 或 mAP。
  - **跨数据集基准**：ODinW-13 数据集（13 个子集，覆盖不同领域和类别，如航空、水族馆、蘑菇等），评测指标为 mAP。
- **对比方法**：
  - 传统 TTAOD：BN、TENT、T3A、SHOT、Mean-Teacher、STFAR、CTTAOD 等（基于 Faster R-CNN 或 Swin-T 骨干）。
  - 基于 Grounding DINO 的强基线：Direct Test、Mean-Teacher。
- **实现细节**：模型基于 Grounding DINO (Swin-T)，使用 DINOv2 (ViT-L) 提取实例特征。超参数包括学习率（文本 0.02、视觉 0.2）、阈值（\( th_{pl}=0.3 \)、\( th_{me}=0.3 \)、\( th_{IoU}=0.2 \)）、视觉提示数 \( m=10 \)（腐蚀基准）/ \( m=5 \)（跨数据集基准）、IDM 最大容量 \( |Q_c|_{\max}=20 \)（腐蚀）/ 3（跨数据集）。

## 四、资源与算力

- 文中明确说明：所有实验在 **单个 RTX 3090 GPU** 上运行（见 Sec.4.2 “All experiments are conducted on a single RTX 3090 GPU”）。
- 附录 Table 7 报告了推理延迟（如 MPMT 约 582.9 ms/img）和峰值内存（约 18.0 GB），但未提供总训练/适应时长。由于是测试时自适应，每个 batch 的适应时间已包含在延迟数据中。

## 五、实验数量与充分性

- **主要实验**：
  - 跨腐蚀：两个数据集（Pascal-C、COCO-C），各 15 种腐蚀，对比 4-9 种基线方法。
  - 跨数据集：13 个子数据集，对比 Direct Test 和 Mean-Teacher。
- **消融实验**：
  - Table 3：分解 MPMT、TTWS、ME、MH 等 5 个组件，在 Pascal-C 平均 AP50 上显示贡献。
  - Table 4：视觉提示数量从 2 到 50 的敏感性。
  - Fig. 5：IDM 最大容量的影响。
  - Fig. 6/7：记忆增强阈值及 α、β 敏感性。
  - Table 7：参数量、延迟、内存对比。
- **充分性评估**：实验覆盖多种域偏移（腐蚀、领域迁移、开放类别），消融全面，敏感性分析覆盖关键超参数。公平性方面：承认不同检测器间难完全公平，但提供了基于相同 Grounding DINO 的强基线（Mean-Teacher）进行同基比较。结论客观。

## 六、论文的主要结论与发现

1. 提出的方法在 Pascal-C 上平均 AP50 达 56.2%，超过此前 SOTA 的 STFAR（45.2%）**11 个百分点**；在 COCO-C 上平均 mAP 26.0%，超越所有传统方法且无需源数据。
2. 在跨数据集（ODinW-13）上平均 mAP 54.2%，比直接测试提升 1.4%，而基线 Mean-Teacher 仅提升 0.3%，表明方法对开放类别场景有效。
3. 消融验证了每一组件的必要性，尤其 TTWS 解决了视觉提示初始化引起的性能崩塌，ME 和 MH 在“无伪标签”困难样本上带来额外提升。
4. 参数效率极高：仅可学习 0.079M 参数（占全模型的 0.05%），显著降低存储和通信开销。

## 七、优点

- **创新性**：首次将基础模型（Grounding DINO）引入 TTAOD，彻底摆脱源数据依赖和封闭类别限制，为开放世界实时自适应检测铺平道路。
- **方法设计巧妙**：多模态提示 + 均值教师 + 暖启动策略有效平衡了适应性与知识保留；IDM 配合记忆增强/幻觉机制缓解了伪标签匮乏问题。
- **实验充分且公平**：覆盖多种腐蚀、领域、类别变化的评测，对比了多种传统方法，并提供了基于相同骨干的强基线，消融实验设计完整。
- **实用性**：参数高效（0.05% 可学习）意味着可轻松部署到多域场景；附录中展示了与 Skip 策略结合可进一步降低延迟，具有工程落地潜力。

## 八、不足与局限

1. **极低样本场景适应性有限**：在跨数据集的 Mu（5 张）和 Pa（4 张）上性能退化，说明当测试样本极少时，IDM 无法积累足够原型，提示调优易过拟合。
2. **依赖额外特征提取器**：IDM 需要 DINOv2 提取实例特征，引入额外的计算开销和模型依赖（约 300M 参数），可能限制在资源受限设备上的应用。
3. **超参数敏感**：IDM 容量、阈值 \( th_{me} \)、混合系数 α/β 等在不同数据集上需手动调整（如 α 在 Pascal-C 设为 5.0，COCO-C 设为 1.0），缺少自动调节机制。
4. **仅验证小型骨干**：所有实验基于 Swin-T 骨干，未探索更大模型（如 Swin-L 或 ViT-L）上的扩展性与性能增益。
5. **未讨论失败案例或鲁棒性边界**：论文仅给出平均性能，未分析特定腐蚀类型（如极低亮度、极端模糊）下的失败模式；对对抗扰动等未见分布的鲁棒性未知。
6. **实时性仍需优化**：尽管参数少，但整体延迟约 693.8 ms/img（COCO-C），高于传统方法（如 Mean-Teacher 296 ms），不满足严格实时需求。作者虽提及可与 Skip 策略结合，但未系统评估视频流场景下的性能。

（完）
