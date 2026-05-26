---
title: Test-Time Canonicalization by Foundation Models for Robust Perception
title_zh: 基于基础模型的测试时规范化实现鲁棒感知
authors: "Utkarsh Singhal, Ryan Feng, Stella X. Yu, Atul Prakash"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JMZ7mr19AK"
tags: ["query:tta"]
score: 7.0
evidence: 利用基础模型进行测试时规范化以实现鲁棒感知
tldr: 现实世界感知面临多样化视角挑战，现有方法依赖数据增强或专用架构。本文提出FoCaL，在测试时通过基础模型（如CLIP）的先验，将输入图像规范化为最典型视角，从而提升鲁棒性。无需训练或架构更改，在2D/3D旋转等变换下显著提升CLIP和SAM等模型的性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 807, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1746, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 820, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1742, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 839, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 863, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 872, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 850, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1764, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1711, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 885, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1706, \"height\": 678, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1633, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1618, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 556, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmz7mr19ak/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1110, \"height\": 413, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jmz7mr19ak/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmz7mr19ak/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 903, \"height\": 384, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmz7mr19ak/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1743, \"height\": 840, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmz7mr19ak/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1316, \"height\": 358, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmz7mr19ak/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1609, \"height\": 454, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmz7mr19ak/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 931, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmz7mr19ak/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 893, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmz7mr19ak/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1775, \"height\": 491, \"label\": \"Table\"}]"
motivation: 模型在测试时面对未知视角变化，现有鲁棒性方法适应性不足。
method: 利用预训练基础模型的似然作为先验，在测试时搜索最佳变换，选择最可能的规范化视图。
result: 在多种图像变换下，CLIP和SAM的鲁棒性得到显著增强。
conclusion: 测试时规范化是一种轻量且通用的鲁棒性增强方法。
---

## Abstract
Perception in the real world requires robustness to diverse viewing conditions. Existing approaches often rely on specialized architectures or training with predefined data augmentations, limiting adaptability.  Taking inspiration from mental rotation in human vision, we propose FoCal, a test-time robustness framework that transforms the input into the most typical view. At inference time, FoCal explores a set of transformed images and chooses the one with the highest likelihood under foundation model priors. This test-time optimization boosts robustness while requiring no retraining or architectural changes.
Applied to models like CLIP and SAM, it significantly boosts robustness across a wide range of transformations, including 2D and 3D rotations, contrast and lighting shifts, and day-night changes. We also explore potential applications in active vision. By reframing invariance as a test-time optimization problem, FoCal offers a general and scalable approach to robustness. Our code is available at: https://github.com/sutkarsh/focal .

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
现实世界感知系统在应对多样化视角、光照等变化时存在脆弱性。现有方法（如数据增强、等变网络）在训练时硬编码不变性，适应性有限，难以泛化到未知变换。受人类心理旋转的启发，本文提出 **FoCal**，将鲁棒性问题重新定义为测试时优化问题：利用预训练基础模型（CLIP、Stable Diffusion）的先验知识，在推理时将输入图像变换到“最视觉典型”的规范视图，从而近似实现不变性，且无需重新训练或修改架构。

## 2. 方法论
### 核心思想
- **规范化的数学框架**：基于 Kaba et al. (2022) 的理论，通过能量最小化定义规范器：\( h(x) = \arg\min_{t \in T} E(t(x)) \)，其中 \( T \) 为变换集合，\( E \) 为能量函数。规范化后的图像 \( t^*(x) \) 可保证下游模型输出不变。
- **关键洞察**：一张图像及其所有变换版本构成了自然图像分布的一个切片，能量最小化等价于寻找该切片中最可能的版本（即视觉典型版本）。

### 技术细节
- **能量函数构建**：
  - **CLIP 能量**：基于分类 logits 的均值与最大值组合，反映语义典型性。
  - **扩散能量**：基于 Stable Diffusion 的噪声预测损失，反映图像外观的似然。
  - **总能量**：\( E_{\text{FoCal}} = \gamma_1 E_{\text{CLIP}} + \gamma_2 E_{\text{diff}} \)，通过超参数平衡两类先验。
- **“变体与排序”流程**：
  1. **Vary**：生成输入图像的一组候选变换版本（如通过 3D 渲染器、2D 旋转、颜色/对比度调整等）。
  2. **Rank**：使用联合能量函数对每个候选进行评分，选择能量最低的版本作为规范图像。
- **贝叶斯优化**：对于连续/高维变换空间（如颜色、相机位姿），使用高斯过程与期望改进获取函数进行高效搜索，通常 50–100 次评估即可找到最优解。

## 3. 实验设计
### 数据集与场景
| 变换类型 | 数据集 | 下游模型 |
|---------|--------|----------|
| 3D 视角 | Objaverse-LVIS（46K 3D 资产）、CO3D（19K 真实多视角视频） | OV-Seg（微调 CLIP）、CLIP |
| 光照（颜色/对比度） | CIFAR-100、ImageNet-1K | CLIP、DINOv2 |
| 2D 旋转 | CIFAR-10/100、STL-10、ImageNet-1K；COCO（分割） | ResNet-50、ViT、CLIP、SAM |
| 昼夜变换 | KITTI（通过 UrbanIR 生成 2000 对日/夜图像） | CLIP |
| 主动视觉 | 8 个虚拟 3D 场景（3D 高斯泼溅） | CLIP + 贝叶斯优化 6-DoF 相机位姿 |

### 对比基准
- **PRLC** (Mondal et al., 2023)：针对特定数据集和变换训练的规范化器。
- **Test-Time Augmentation (TTA)**：简单多视图平均。
- **无规范**：直接使用原始模型推理。
- **随机旋转/预设视角**：作为基线。

## 4. 资源与算力
论文未给出完整的训练算力（因方法本身无需训练），但附录 A.10 提供了各实验的 FLOPs 与运行时间：
- 2D 旋转：8 个变换，0 步扩散，每次迭代约 0.47 秒（单张 RTX 2080Ti）。
- 3D 视角：61 个变换，5 步扩散，每次迭代约 13.3 秒（RTX 6000 Ada）。
- 颜色/对比度：使用贝叶斯优化（35–60 次评估），无扩散时每次约 5.2 秒。
- 昼夜变换：2 个候选，约 0.16 秒。
- 主动视觉：500 次评估，无扩散，约 238 秒（单次运行）。
所有实验可在单 GPU 上完成，未使用分布式训练。

## 5. 实验数量与充分性
- **实验数量**：覆盖 7 种不同变换类型、5 个以上数据集、3 种下游任务（分类、分割、位姿估计）、多种骨干网络（ResNet、ViT、CLIP、SAM、DINOv2）。同时包含消融实验（能量函数组件、与 TTA 对比）、跨数据集泛化测试、与 PRLC 的公平对比（使用相同超参）。
- **充分性**：实验设计较为全面，既包括受控合成数据（2D/3D 渲染）也包括真实世界数据（CO3D、KITTI），且包含最坏情况分析（按难度分桶）。但部分场景（如昼夜、主动视觉）仅作为探索性实验，未与强 baseline 详细比较。

## 6. 主要结论与发现
- FoCal **无需任何训练**即可在多种变换下显著提升 CLIP、SAM 等模型的鲁棒性，且**匹配甚至超越**专门训练的 PRLC 方法（如 2D 旋转上 +2.1% 位姿准确率，分割 mAP 相同）。
- 在 3D 视角困难样本上，FoCal 将分类准确率从 12.0% 提升至 62.0%（+50%）。
- 光照变换：颜色偏移提升 9.9%，对比度变化提升 4.1%，极端变换下可达 15% 和 12%。
- 昼夜变换：FoCal 偏好日间图像（91% 准确率）。
- 主动视觉：优化相机位姿后能自动聚焦显著物体并保持正立姿态。
- 验证了测试时计算可作为通用鲁棒性策略，突破了“必须训练时硬编码不变性”的假设。

## 7. 优点
- **训练无关**：无需修改模型或重新训练，可直接应用于任意预训练模型。
- **通用性强**：可处理 2D/3D 旋转、光照、昼夜、位姿等不同变换。
- **理论基础扎实**：基于能量最小化框架，具有不变量保证。
- **实用创新**：结合 CLIP 语义先验和扩散模型外观先验，通过贝叶斯优化高效搜索。
- **开源实现**：代码已公开，可复现。

## 8. 不足与局限
- **计算开销大**：每次推理需多次评估能量函数（尤其扩散模型），附录表8显示 FLOPs 约为标准推理的 50 倍以上，不适合实时场景。
- **变换生成依赖**：需要事先为每类变换指定生成器（如 3D 渲染器、颜色调参范围），如何自动选择变换仍有待解决。
- **近似不变性**：对于非可逆变换（如 3D 视角），仅能实现近似不变，无法严格保证。
- **光照校正弱于专用方法**：在 RCC 数据集上颜色校正精度远低于 Barron & Tsai (2017)（中值角度误差 6.4° vs 1.3°），表明通用框架在特定任务上不如专门算法。
- **超参数敏感**：能量函数权重（α, β, γ₁, γ₂）需通过额外调优（文中使用贝叶斯优化搜索），增加了部署难度。
- **主动视觉实验初步**：仅 8 个场景，优化成功率未详细量化，存在失败案例。
- **实验偏差风险**：Objaverse 数据标签存在歧义（如多个相似类别），虽经过滤但仍可能影响评估客观性。部分实验未与更多最新方法（如 ViewFool、3D 鲁棒性方法）对比。

（完）
