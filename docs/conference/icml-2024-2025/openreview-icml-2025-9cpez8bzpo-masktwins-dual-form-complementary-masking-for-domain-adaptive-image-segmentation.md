---
title: "MaskTwins: Dual-form Complementary Masking for Domain-Adaptive Image Segmentation"
title_zh: "MaskTwins: 用于域自适应图像分割的双重互补掩码"
authors: "Jiawen Wang, Yinda Chen, Xiaoyu Liu, Che Liu, Dong Liu, Jianqing Gao, Zhiwei Xiong"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=9CpeZ8BzPO"
tags: ["query:ris"]
score: 7.0
evidence: 领域自适应图像分割，涉及理论分析和域不变特征提取
tldr: 本文针对无监督域自适应分割任务，提出MaskTwins方法。通过将掩码重建重新表述为稀疏信号重建问题，理论上证明互补掩码的双重形式具有提取域不变图像特征的优越能力。该方法有效解决了域偏移问题，对提升分割模型在目标域的性能有重要意义。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-9cpez8bzpo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9cpez8bzpo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1728, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9cpez8bzpo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1676, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9cpez8bzpo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1728, \"height\": 757, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9cpez8bzpo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1094, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9cpez8bzpo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1038, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9cpez8bzpo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1717, \"height\": 2075, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-9cpez8bzpo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1780, \"height\": 962, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9cpez8bzpo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1754, \"height\": 566, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9cpez8bzpo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 785, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9cpez8bzpo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 802, \"height\": 538, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9cpez8bzpo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 804, \"height\": 390, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9cpez8bzpo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1630, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9cpez8bzpo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1628, \"height\": 275, \"label\": \"Table\"}]"
motivation: 现有掩码图像建模与一致性正则化结合缺乏理论分析，未能充分利用掩码重建的潜力。
method: 将掩码重建视为稀疏信号重建，提出双重互补掩码形式，理论上证明其提取域不变特征的能力。
result: 在无监督域自适应分割任务上验证了方法的有效性。
conclusion: 提出了一种简单有效的域自适应分割框架。
---

## Abstract
Recent works have correlated Masked Image Modeling (MIM) with consistency regularization in Unsupervised Domain Adaptation (UDA). However, they merely treat masking as a special form of deformation on the input images and neglect the theoretical analysis, which leads to a superficial understanding of masked reconstruction and insufficient exploitation of its potential in enhancing feature extraction and representation learning. In this paper, we reframe masked reconstruction as a sparse signal reconstruction problem and theoretically prove that the dual form of complementary masks possesses superior capabilities in extracting domain-agnostic image features. Based on this compelling insight, we propose MaskTwins, a simple yet effective UDA framework that integrates masked reconstruction directly into the main training pipeline. MaskTwins uncovers intrinsic structural patterns that persist across disparate domains by enforcing consistency between predictions of images masked in complementary ways, enabling domain generalization in an end-to-end manner. Extensive experiments verify the superiority of MaskTwins over baseline methods in natural and biological image segmentation.
These results demonstrate the significant advantages of MaskTwins in extracting domain-invariant features without the need for separate pre-training, offering a new paradigm for domain-adaptive segmentation. The source code is available at https://github.com/jwwang0421/masktwins.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：无监督域自适应（UDA）图像分割中，现有方法将掩码图像建模（MIM）与一致性正则化结合，但仅将掩码视为一种特殊的输入变形，缺乏理论分析，导致对掩码重建的作用理解肤浅，未能充分挖掘其在特征提取和表示学习中的潜力。
- **整体含义**：本文从稀疏信号重建视角重新审视掩码重建，理论上证明互补掩码的双重形式在提取域无关图像特征方面具有优越性。在此基础上提出 **MaskTwins** 框架，将互补掩码一致性直接集成到UDA训练中，无需额外预训练，实现端到端的域泛化。

#### 2. 方法论
- **核心思想**：将掩码重建建模为稀疏信号重建问题，通过理论分析（信息保存、泛化界、特征一致性）证明互补掩码优于随机掩码。利用互补掩码产生的不同视图，强制模型预测一致性，从而学习域不变的结构模式。
- **关键技术细节**：
  - **互补掩码生成**：对于目标域图像 \( x_T \)，从伯努利分布采样二值掩码 \( D \)（元素独立服从 \( \text{Bernoulli}(0.5) \)），得到互补对 \( D \odot x_T \) 和 \( (1-D) \odot x_T \)。
  - **损失函数**：总损失 \( L_{\text{total}} = L_{\text{sup}}^S + L_{\text{cl}}^T + \lambda_{\text{cm}} L_{\text{cm}}^T \)。
    - 源域监督损失 \( L_{\text{sup}}^S \)：标准交叉熵。
    - 目标域掩码一致性学习损失 \( L_{\text{cl}}^T \)：对互补掩码图像分别与伪标签计算交叉熵后加权平均。
    - 互补掩码损失 \( L_{\text{cm}}^T \)：约束两个互补掩码预测之间的 \( L2 \) 距离。
  - **教师模型**：通过指数移动平均（EMA）更新教师参数，为未掩码目标图像生成伪标签。
  - **架构**：共享编码器和分割头，浅层使用自适应实例归一化（AdaIN）对齐特征分布。
- **理论公式**（文字说明）：论文给出了三个定理：
  - **信息保存定理**：互补掩码的期望信息保存量优于随机掩码，且方差更小。
  - **泛化界定定理**：互补掩码的泛化误差界更紧，不依赖于输入维度。
  - **特征一致性定理**：互补掩码的特征一致性误差更小，受环境因素影响更弱。

#### 3. 实验设计
- **数据集与场景**：
  - **自然图像语义分割**：SYNTHIA（合成→实景）→ Cityscapes。
  - **生物图像线粒体分割**：VNC III → Lucchi（两个子集），MitoEM-R → MitoEM-H 及反向。
  - **3D 突触检测**：WASPSYN 数据集（内含 14 个图像块，5 个有点标注）。
- **Benchmark**：与 20+ 种 UDA 方法对比，包括 DAFormer、HRDA、MIC、DAMT-Net、DA-VSN、DA-ISC、CAFA、SSNS-Net、AdaSyn 等。
- **对比方法**：针对不同任务，对比了对应领域内最新的 UDA 方法，覆盖对抗学习、自训练、一致性正则化等策略。

#### 4. 资源与算力
- **硬件**：实验使用 **8 张 RTX 3090 GPU**。
- **训练时长**：论文未明确给出每次实验的训练时长或总耗时，仅说明了迭代次数（如 40k、200k），但无具体时间统计。

#### 5. 实验数量与充分性
- **实验组数**：共进行了 **6 个数据集**、**3 类任务**（2D 自然/生物分割、3D 检测）的评估，以及：
  - **消融实验**：组件消融（CL、CMask、EMA、AdaIN）、掩码策略对比（互补 vs 随机）、超参数（patch size、mask ratio）分析。
  - **扩展实验**：在 VisDA-2017 分类任务上验证，覆盖 ViT-B/16 和 ResNet-101。
- **充分性与公平性**：
  - 实验覆盖了多种域偏移场景（合成→真实、大鼠→人类、不同切片），对比方法按原论文设置复现或引用已有结果。
  - 指标全面（IoU、F1、MCC、mAP），并可视化定性结果。
  - 消融实验逐一分离每个组件的贡献，结论清晰。
  - 总体上实验设计合理，对比公平，充分验证了方法的鲁棒性和泛化性。

#### 6. 主要结论与发现
- **理论贡献**：首次从稀疏信号重建角度为互补掩码提供了理论支撑，证明其在线性保留、泛化界和特征一致性方面均优于随机掩码。
- **实验结果**：
  - SYNTHIA→Cityscapes：mIoU 达 **76.7%**，较 SOTA 方法 MIC 提升 **2.7%**，尤其对“人行道”提升 19.6 IoU。
  - 线粒体分割：在 V2L1、V2L2、R2H、H2R 四个组别中均达到 SOTA，IoU 提升 2.1%–3.2%。
  - 3D 突触检测：F1-score 达 **0.5913**，较基线 AdaSyn 提升 4.2%，后突触检测提升显著。
  - 分类任务：VisDA-2017 上 ViT 和 ResNet 均提升约 0.3–0.4 百分点。
- **关键发现**：互补掩码策略贡献最大（消融显示 +3.9 mIoU），而 EMA 教师和 AdaIN 模块增益相对较小。

#### 7. 优点
- **理论创新**：将 MIM 关联到压缩感知，提供严格的数学证明，为互补掩码的有效性奠定理论基础。
- **方法简洁性**：仅通过改变掩码生成方式（互补而非随机）即可显著提升性能，无需额外可学习参数或复杂模块。
- **跨域泛化强**：在自然图像、生物图像、2D/3D 多种场景下均取得 SOTA，验证了方法的通用性。
- **可扩展性**：可作为即插即用技术与现有 UDA 方法结合，灵活性强。
- **实验充分**：涵盖多数据集、多任务、丰富消融，结果可靠。

#### 8. 不足与局限
- **理论假设的局限性**：理论证明基于视觉数据服从稀疏信号模型这一假设，实际图像可能不完全符合，理论通用性有待进一步验证。
- **超参数敏感性**：性能对 patch size 和 mask ratio 敏感，需要针对不同任务调优（如突触检测使用 patch size=6）。
- **小目标适应问题**：文中提到对极小类别（如 traffic light）提升不明显甚至略有下降，可能由于互补掩码导致小目标信息丢失。
- **实验覆盖有限**：未在更多实际大规模 UDA 基准（如 GTA→Cityscapes）上评估，且未报告训练时间、显存占用等资源消耗细节。
- **缺失统计显著性分析**：实验中未给出多次运行的标准差或置信区间，结论的稳定性未充分量化。

（完）
