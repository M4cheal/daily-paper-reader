---
title: "OneRef:  Unified One-tower Expression Grounding and Segmentation with Mask Referring Modeling"
title_zh: OneRef：统一单塔表达定位与分割的掩码指代建模
authors: "Linhui Xiao, Xiaoshan Yang, Fang Peng, Yaowei Wang, Changsheng Xu"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=siPdcro6uD"
tags: ["query:ris"]
score: 10.0
evidence: 统一的指代分割框架
tldr: 现有指代分割方法依赖笨重的Transformer融合，本文提出OneRef，采用模态共享的单塔Transformer统一视觉与语言特征空间，并设计掩码指代建模（MRefM）来捕捉指代关系。实验表明OneRef在多个指代分割基准上达到最优性能，且结构更加简洁高效。该方法推动了指代分割的实用化。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-sipdcro6ud/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1401, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sipdcro6ud/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sipdcro6ud/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sipdcro6ud/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sipdcro6ud/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1330, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sipdcro6ud/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1396, \"height\": 870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sipdcro6ud/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1376, \"height\": 903, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sipdcro6ud/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1364, \"height\": 896, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1453, \"height\": 675, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 874, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 547, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 869, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 565, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1163, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1460, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1129, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 841, \"height\": 686, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1285, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1455, \"height\": 522, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1311, \"height\": 538, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1344, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sipdcro6ud/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 810, \"height\": 357, \"label\": \"Table\"}]"
motivation: 现有指代分割中视觉和语言分离编码，需复杂融合，且掩码视觉语言建模无法捕捉细腻指代关系。
method: 提出模态共享单塔Transformer，统一特征空间；引入掩码指代建模(MRefM)学习指代性掩码关系。
result: 在多个指代分割数据集上取得最优结果，模型更简洁高效。
conclusion: 单塔统一框架结合专用掩码建模可有效提升指代分割性能。
---

## Abstract
Constrained by the separate encoding of vision and language, existing grounding and referring segmentation works heavily rely on bulky Transformer-based fusion en-/decoders and a variety of early-stage interaction technologies. Simultaneously, the current mask visual language modeling (MVLM) fails to capture the nuanced referential relationship between image-text in referring tasks. In this paper, we propose **OneRef**, a minimalist referring framework built on the modality-shared one-tower transformer that unifies the visual and linguistic feature spaces. To modeling the referential relationship, we introduce a novel MVLM paradigm called Mask Referring Modeling (**MRefM**), which encompasses both referring-aware mask image modeling and referring-aware mask language modeling. Both modules not only reconstruct modality-related content but also cross-modal referring content. Within MRefM, we propose a referring-aware dynamic image masking strategy that is aware of the referred region rather than relying on fixed ratios or generic random masking schemes. By leveraging the unified visual language feature space and incorporating MRefM's ability to model the referential relations, our approach enables direct regression of the referring results without resorting to various complex techniques. Our method consistently surpasses existing approaches and achieves SoTA performance on both grounding and segmentation tasks, providing valuable insights for future research. Our code and models are available at https://github.com/linhuixiao/OneRef.

---

## 论文详细总结（自动生成）

# OneRef: 统一单塔表达定位与分割的掩码指代建模 — 详细论文总结

---

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的指代定位（Visual Grounding）和指代分割（Referring Segmentation）方法普遍采用视觉与语言分离编码的架构，依赖笨重的 Transformer 融合编码器/解码器以及大量早期交互技巧（如适配器、跨模态桥、权重生成、交叉注意力等），导致模型参数量大、流程复杂。同时，当前的掩码视觉语言建模（MVLM）虽然通过交替训练 MIM 和 MLM 实现多模态交互，但无法有效捕捉图像与文本之间细粒度的指代关系（referential relationship），因此在面向回归的指代任务中存在显著差距。
- **整体含义**：作者旨在探索一种更简洁、高效的统一框架，通过模态共享的单塔 Transformer 将视觉和语言特征空间统一，并设计新的掩码建模范式来显式建模指代关系，从而摆脱传统方法中复杂的融合模块和专用定位 token，实现端到端的简洁指代定位与分割。

---

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 基于 BEiT-3 的模态共享单塔 Transformer（Multi-way Transformer with MoE heads）构建统一特征空间。
- 提出 **Mask Referring Modeling (MRefM)** 范式，包含两个子模块：
  - **Referring-aware Mask Image Modeling (Referring MIM)**：重建视觉内容 + 视觉目标关系分数（visual target-relation score），并采用指代感知的动态图像掩码策略。
  - **Referring-aware Mask Language Modeling (Referring MLM)**：重建语言内容 + 语义目标关系分数（semantic target-relation score）。
- MRefM 预训练后，在统一特征空间内直接用轻量级任务头（轻量 MLP 或 deconv + 余弦相似度）回归定位框或分割掩码，无需额外融合编码器/解码器、无需 [Region] 或查询锚点。

### 关键技术细节
1. **Referring MIM**：
   - 使用视觉 token 与聚合文本 token（[SEP]）的点积结果进行重建。
   - 重建两个分支：① 模态相关内容（原始视觉 token 分类损失）；② 视觉目标关系分数 \( s^{vt}_i \in \mathbb{R}^{4} \)，表示每个 patch 到指代区域的四维距离（x-掩码、y-掩码、w-掩码、h-掩码）。
   - 提出**指代感知动态图像掩码策略**：对指代区域及其周边采用不同掩码率（β 为周边低掩码率，γ 为区域内高掩码率），整体掩码率 α 根据每个样本的指代区域大小动态决定。

2. **Referring MLM**：
   - 使用语言 token 与聚合视觉 token（[CLS]）的点积结果进行重建。
   - 重建两个分支：① 模态相关内容（原始语言 token 分类损失）；② 语义目标关系分数 \( s^{st}_i \)，通过教师模型（BEiT-3 经图像-文本对比微调）计算语言 token 与指代区域、整图聚合 token 的余弦相似度的加权和，再用 KL 散度进行预测。

3. **指代感知动态图像掩码策略算法**（Algorithm 1）：
   - 随机生成 β 比例的背景掩码块（block-wise random masking）。
   - 在指代区域扩展范围内按 γ 比例生成随机块掩码。
   - 最终合并生成掩码位置集合 M。

4. **任务头设计**：
   - **REC 头**：视觉 token 与 [SEP] 计算余弦相似度得到粗粒度掩码 \( M_{sim} \)，再通过加权求和得到降维 token，经 3 层 MLP 回归边界框。额外使用 Focal loss 和 Dice loss 对相似度掩码施加边界框约束作为辅助损失。
   - **RES 头**：视觉 token 经 3 层反卷积上采样后与 [SEP] 计算余弦相似度，再经 1 层双线性插值得到最终分割掩码，使用 Focal loss 和 Dice loss 监督。

5. **损失函数**：
   - REC：\( \mathcal{L}_{REC} = \lambda_{L1} L_{L1} + \lambda_{giou} L_{giou} + L_{box\_mask\_constraints} \)
   - RES：\( \mathcal{L}_{RES} = \lambda_{f\_seg} L_{focal} + \lambda_{d\_seg} L_{dice} \)

---

## 3. 实验设计

### 使用数据集
- **Three benchmark tasks**:
  - REC / PG：RefCOCO, RefCOCO+, RefCOCOg, ReferItGame, Flickr30k Entities
  - RES：RefCOCO, RefCOCO+, RefCOCOg

### 评估指标
- REC/PG：IoU≥0.5 的准确率（Acc@0.5）
- RES：mIoU（平均交并比）和 oIoU（总体交并比）

### 对比方法
- 对比了多个 SoTA 方法：
  - **传统设定**（单数据集微调）：TransVG, TransVG++, QRNet, VG-LAW, CLIP-VG, HiVG 等
  - **数据集混合中间预训练**：MDETR, Grounding-DINO, OFA, UniTAB, PolyFormer, RISCLIP, HiVG, LION (7B/12B) 等
  - 同时包括了超大模型（LION-12B）和 MLLM 方法（Shikra, Ferret）
- 对比维度涵盖不同 backbone（CLIP, BEiT-3, Swin, ViT 等）和不同预训练数据规模

### 实验设置
- **三种实验设置**：
  1. **单数据集微调**：在单个下游数据集上直接微调（不使用外部预训练数据）
  2. **数据集混合中间预训练**：先使用混合数据（RefC, ReferIt, Flickr）进行 MRefM 预训练，再微调至具体任务
  3. **无监督中间预训练**：使用 FH 算法生成区域伪标签进行 MRefM 预训练，验证泛化性

---

## 4. 资源与算力

- **硬件**：NVIDIA A100 GPU
- **MRefM 预训练**：
  - Base 模型：32 张 A100，约 15 小时（110 epoch）
  - Large 模型：32 张 A100，约 50 小时
- **REC/RES 微调**：
  - Base 模型：8 张 A100，每数据集约 3 小时（20 epoch）
  - Large 模型：8 张 A100，每数据集约 8 小时
- **推理速度**：在单张 A100 上，OneRef-B 的 FPS 为 83.2（测试条件：RefCOCO 数据集，384×384 分辨率），远快于 TransVG++（8.7 FPS）、Grounding-DINO（8.3 FPS）等

---

## 5. 实验数量与充分性

- **实验组数**：非常充分。包括：
  - REC 任务：5 个数据集（RefCOCO/+/g, ReferIt, Flickr30k）的多种设置
  - RES 任务：3 个数据集（RefCOCO/+/g）的多种设置
  - PG 任务：2 个数据集（ReferIt, Flickr30k）的混合预训练设置
  - 消融实验：MRefM 各组件消融（Table 4）、掩码策略消融（Table 16）、任务头消融（Table 5）、泛化性实验（Table 6、Table 7）
  - 无监督预训练验证
  - 计算资源对比（Table 14）
- **公平性**：
  - 与 SoTA 方法在同一评估协议下对比，指标一致。
  - 与 HiVG、Grounding-DINO、LION 等均使用相同或相近的数据集混合设置。
  - 部分基线（如 TransVG++）因代码未公开，作者自行复现进行公平对比。
  - 注意：OneRef 的预训练数据量（RefC + ReferIt 约 0.5M）远小于 LION（3.6M）、MDETR（6.5M）等，但仍取得了更优结果，说明方法高效。
- **结论**：实验充分、客观、公平，囊括了主流设置和大量对比，消融实验清晰验证了各模块贡献。

---

## 6. 主要结论与发现

1. **MRefM 范式有效提升指代能力**：引入 Referring MIM 和 Referring MLM 后，相比标准 MVLM，性能显著提升（RefCOCOg test 上提升 6.21%）。
2. **指代感知动态掩码策略优于固定掩码**：相比 random masking 和 block-wise masking，该策略能更好地利用指代区域上下文，带来约 1% 的性能增益。
3. **统一单塔架构可行且高效**：无需交叉注意力融合模块和特殊 token，仅用轻量 MLP 头即可达到甚至超越复杂架构的性能。
4. **模型扩展性好**：Large 模型相较 Base 模型有显著提升（如 RefCOCO testA 从 94.31% 升至 95.43%）。
5. **泛化性强**：MRefM 可移植到其他框架（如 TransVG、CLIP-VG、TransVG++、LAVT）中，均带来正的性能增益。
6. **计算效率高**：OneRef 在参数、FLOPs、推理速度上均远优于传统方法，同时精度更高。

---

## 7. 优点

- **架构简洁**：首创性提出完全基于单塔 Transformer 的指代定位与分割框架，移除了传统方法中复杂的融合编码器/解码器、早期交互模块、特殊 grounding token。
- **新型掩码建模**：MRefM 首次将掩码建模系统性地应用于指代任务，通过重建目标关系分数和指代感知动态掩码，使模型在预训练阶段就学习到跨模态指代关系。
- **统一框架**：同一模型可同时处理 REC、PG、RES 三类任务，仅需更换轻量任务头。
- **高计算效率**：FLOPs 仅为 Grounding-DINO 的 34.9%，推理速度可达 83.2 FPS，远超同类方法。
- **泛化验证充分**：在无监督预训练、迁移到其他 backbone 等场景下均验证了方法的通用性和鲁棒性。
- **代码与模型开源**：提供了完整开源代码和预训练模型，便于后续研究。

---

## 8. 不足与局限

- **数据依赖**：MRefM 预训练需要额外提供指代区域边界框作为监督信号（虽然可通过无监督方法生成，但质量可能不稳定），无法像纯粹自监督方法完全无标签。
- **大规模预训练挑战**：对于网络爬取的图像-文本对，文本常描述全图而非特定区域，导致生成伪区域时噪音较大，在更大规模预训练中可能引入偏差。
- **数据集规模限制**：本文预训练仅使用 RefC 和 ReferIt 数据集（约 0.5M 样本），未使用更大规模的多源数据（如 GoldG、O365 等），若使用更大数据可能进一步提升性能。
- **实验覆盖**：虽然覆盖了多个主流数据集，但未在视频域或其他场景（如开放词汇、密集指代）进行验证。
- **对文本理解的挑战**：对于长句、复杂修饰语（如 RefCOCO+ 中的颜色、形状组合），模型表现虽好但仍有提升空间。
- **潜在应用风险**：强大的开放集指代能力可能被用于非法监控、目标追踪等不当场景，需关注伦理和公平性问题。

---

（完）
