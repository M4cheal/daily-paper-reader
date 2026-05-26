---
title: Semantics-aware Test-time Adaptation for 3D Human Pose Estimation
title_zh: 面向3D人体姿态估计的语义感知测试时间自适应
authors: "Qiuxia Lin, Rongyu Chen, Kerui Gu, Angela Yao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=pNZ3pioKRN"
tags: ["query:tta"]
score: 7.0
evidence: 面向3D人体姿态估计的语义感知测试时间自适应
tldr: 针对测试时间自适应中3D人体姿态预测过于平滑且缺乏语义引导的问题，本文首次将语义感知运动先验引入TTA。利用视频理解和运动-文本空间对齐，在测试时动态调整运动预测以符合视频语义。同时提出基于运动-文本相似度的缺失2D姿态补全策略。在多个基准上显著改进了遮挡和截断情况下的姿态估计精度。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-pnz3piokrn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 805, \"height\": 935, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pnz3piokrn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1741, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pnz3piokrn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 848, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pnz3piokrn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pnz3piokrn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1738, \"height\": 1182, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pnz3piokrn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 838, \"height\": 130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pnz3piokrn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 838, \"height\": 800, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pnz3piokrn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1704, \"height\": 2191, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pnz3piokrn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1654, \"height\": 2199, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pnz3piokrn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1670, \"height\": 2237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pnz3piokrn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1671, \"height\": 2114, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-pnz3piokrn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1472, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pnz3piokrn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 869, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pnz3piokrn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 842, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pnz3piokrn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1789, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pnz3piokrn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 871, \"height\": 127, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pnz3piokrn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 845, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pnz3piokrn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 532, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pnz3piokrn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 714, \"height\": 144, \"label\": \"Table\"}]"
motivation: 现有TTA方法在3D人体姿态估计中存在预测平滑、缺乏语义引导的问题。
method: 集成语义感知运动先验，利用视频理解与运动-文本空间在测试时自适应调整运动预测。
result: 在多个数据集上有效改善遮挡和截断场景的姿态估计精度。
conclusion: 语义感知先验能显著提升测试时间自适应的鲁棒性与准确性。
---

## Abstract
This work highlights a semantics misalignment in 3D human pose estimation. For the task of test-time adaptation, the misalignment manifests as overly smoothed and unguided predictions. The smoothing settles predictions towards some average pose. Furthermore, when there are occlusions or truncations, the adaptation becomes fully unguided. To this end, we pioneer the integration of a semantics-aware motion prior for the test-time adaptation of 3D pose estimation. We leverage video understanding and a well-structured motion-text space to adapt the model motion prediction to adhere to video semantics during test time. Additionally, we incorporate a missing 2D pose completion based on the motion-text similarity. The pose completion strengthens the motion prior's guidance for occlusions and truncations. Our method significantly improves state-of-the-art 3D human pose estimation TTA techniques, with more than 12% decrease in PA-MPJPE on 3DPW and 3DHP.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有测试时间自适应（TTA）方法在3D人体姿态估计中存在两个主要缺陷：一是预测结果过于平滑，趋向于某种平均姿态，忽略了动作语义；二是当存在遮挡或截断导致2D关键点缺失时，模型缺乏有效引导，预测变得不可靠。
- **研究动机**：传统TTA方法（如CycleAdapt、DynaBOA）仅依赖2D投影损失和时序平滑正则化，无法解决深度模糊性和无2D监督时的完全无引导问题。作者意识到视频片段中蕴含的语义信息（如“爬楼梯”、“行走”）可以大幅缩小3D解空间，并用于补全缺失2D关键点。
- **背景**：3D人体姿态估计在真实场景中由于训练数据（MoCap）与测试数据分布差异大，预训练模型泛化能力差。TTA是一种无需标注即可在测试时微调模型的实用方案，但现有方法缺乏语义理解。

## 2. 论文提出的方法论

### 核心思想
- 首次将**语义感知运动先验**融入TTA框架，利用运动-语言模型（MotionCLIP）对齐预测运动与视频片段的文本语义，从而引导3D预测进入正确的语义解空间。
- 对遮挡/截断导致的缺失2D关键点，利用运动-文本相似度阈值进行**2D姿态补全**，增强先验的引导能力。

### 关键技术细节
- **文本标签生成**：使用VLM（GPT-4o）对视频片段进行动作描述，并从运动词典中匹配最相关的文本标签。只保留所有帧标签一致的片段，并采用加权采样（权重=1-预测运动与文本标签的余弦相似度）。
- **运动-文本特征对齐**：将预测姿态参数（转化为6D表示）通过MotionCLIP的运动编码器得到特征，文本标签通过CLIP模型得到特征，计算余弦相似度作为对齐损失L_align = 1 - cos(f_CLIP(s), f_MOTION(p'))。运动编码器和CLIP模型均冻结，仅回传梯度更新HPE网络。
- **2D姿态更新**：
  - 初始2D估计由OpenPose提供，置信度低于0.3的关键点视为缺失。
  - 每轮模型微调后，使用指数移动平均（EMA）更新2D标签：J_bar_{k}^{e+1} = alpha * J_bar_{k}^{e} + (1-alpha) * J_hat_{k}^{e}。
  - 对于缺失关键点，若预测运动与文本特征相似度超过阈值sigma，则用当前预测的2D投影填充：J_bar_{k}^{e+1} = J_hat_{k}^{e}；否则保持缺失。
- **总体损失**：L_overall = λ1 L_2D + λ2 L_align + L_smooth。其中L_2D为可见关键点的L1投影损失，L_smooth为时序平滑损失（与CycleAdapt相同）。

## 3. 实验设计

- **数据集**：
  - **训练集**：Human3.6M（用于预训练HMR网络）。
  - **测试集**：3DPW（室外，37个视频，含遮挡）、3DHP（6个室内外视频，含未见姿态）、EgoBody（自我中心视角，严重截断）。
- **基准**：预训练HMR网络、BOA、DynaBOA、DAPA、CycleAdapt（最先进TTA方法）。
- **对比方法**：除上述外，还比较了两种替代语义整合策略（运动判别器、未配对局部姿态监督）。
- **评估指标**：MPJPE、PA-MPJPE、MPVPE（单位毫米）。

## 4. 资源与算力

- 文中未明确说明使用的GPU型号、数量及训练时长。只提到在单帧运行时，额外增加的33.5ms中85.4%来自VLM（GPT-4o），14.6%来自本文框架组件。整体运行时间远低于BOA、DynaBOA、DAPA，但比CycleAdapt略高（107.6ms vs 74.1ms）。

## 5. 实验数量与充分性

- **主要实验组**：共进行了约8组定量实验+多组定性可视化。
  - 在3DPW和3DHP上与4种SOTA方法对比（Table 1）。
  - 在EgoBody上使用更强骨干HMR2.0对比CycleAdapt（Table 2）。
  - 消融实验（Table 3）：依次添加对齐、2D EMA、2D补全，共4组。
  - 语义策略对比（Table 4）：与运动判别器、未配对局部姿态在2个特定视频片段及全部视频上对比。
  - EMA超参数α搜索（Table 8）：5组。
  - 补全阈值σ影响（Table 6）：6组+图4展示数量与质量关系。
  - VLM失败案例分析（Table 7）：3组（无适应、错误标签、正确标签）。
  - 改进分布（Fig.3）：按语义类别统计MPJPE提升。
  - 运行时分析（Table 5）：5种方法对比。
- **充分性与公平性**：
  - 对比方法均为公开代码的SOTA，采用相同骨干和预训练设置。
  - 消融实验逐步验证各组件贡献，逻辑清晰。
  - 对VLM失败情况专门分析，表明即使标签错误仍有稳健性。
  - 但对EMA阈值α和补全阈值σ的搜索只报告最优值，未提供更多细节（如5折交叉验证）。整体实验设计较为充分且客观。

## 6. 论文的主要结论与发现

- 语义感知运动先验能显著缩小2D-to-3D解空间，使用时序平滑导致的平均姿态问题得到缓解。
- 在3DPW上MPJPE从CycleAdapt的87.7mm降至76.4mm（降12.9%），PA-MPJPE从53.8mm降至47.2mm（降12.3%），在3DHP上PA-MPJPE从74.4mm降至65.1mm（降12.5%）。
- 2D补全模块对遮挡/截断场景尤为有效，通过运动-文本相似度筛选高质量预测，平衡了2D关键点的数量与质量。
- 即使VLM给出错误标签，方法仍具鲁棒性（错误标签下MPJPE为92.2mm，仍远低于无适应的213.8mm）。
- 在更强骨干HMR2.0及更挑战的EgoBody数据集上仍优于CycleAdapt。

## 7. 优点

- **创新性**：首次将高层语义信息（动作类别）引入3D人体姿态估计TTA，解决了传统方法忽略语义的问题。
- **实用性**：无需真实2D/3D标注，仅需测试视频即可在线微调；使用开源VLM和预训练运动-语言模型，易于复现。
- **鲁棒性**：对VLM的误标签、遮挡、截断等均有较好抗性；2D补全策略通过阈值控制质量，避免引入噪声。
- **全面性**：在多个数据集、多种骨干、多种TTA方法上验证，并提供详尽的消融和分析实验。
- **效率合理**：虽慢于CycleAdapt，但远快于其他复杂优化方法。

## 8. 不足与局限

- **依赖VLM质量**：文本标签的准确性依赖GPT-4o等大模型，存在3.6%的失败率（如将捡箔纸误判为打高尔夫），虽然实验表明鲁棒，但极端错误可能影响性能。
- **MotionCLIP限制**：运动-语言模型仅能对齐词典内动作，对新颖或复杂动作的描述能力有限，限制了方法向更多场景的泛化。
- **遮挡下的精细度不足**：补全的2D关键点可能与真实步频/持续时间仍有差异，未能完全捕捉实际运动模式。
- **未考虑运动模糊等常见退化**：文中提及运动模糊是未来方向，本方法未专门处理。
- **实验覆盖**：仅评估了HMR和HMR2.0两种骨干；未在更多不同类型基线上（如直接回归3D关节而非SMPL参数的方法）验证。另外，EMA和补全阈值的选择基于网格搜索，可能并非对于所有测试视频最优。
- **资源细节缺失**：未报告训练时的具体GPU型号、显存、总训练时间等，难以复现计算成本。

（完）
