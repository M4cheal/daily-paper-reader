---
title: Self-Bootstrapping for Versatile Test-Time Adaptation
title_zh: 自引导通用测试时自适应
authors: "Shuaicheng Niu, Guohao Chen, Peilin Zhao, Tianyi Wang, Pengcheng Wu, Zhiqi Shen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Li4rieeClO"
tags: ["query:tta"]
score: 8.0
evidence: 直接提出适用于像素级预测的通用测试时自适应方法
tldr: 该文针对测试时自适应（TTA）提出一个自引导框架，通过优化测试图像与其退化视图的预测一致性来适应分布偏移。核心在于设计既能保留几何信息（如目标大小和位置）又提供足够学习信号的劣化增强。在频域分析中揭示分布偏移对低频信息的影响，从而在像素级任务（如语义分割）中保持空间准确性。该方法在多种任务（分类、回归、像素级）上验证了有效性，尤其为需要精确空间预测的Referring Image Segmentation提供了直接的TTA解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-li4rieeclo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-li4rieeclo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1772, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-li4rieeclo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 876, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-li4rieeclo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 846, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-li4rieeclo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1586, \"height\": 1270, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1770, \"height\": 547, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 781, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1502, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1683, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 853, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1771, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 858, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 862, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 857, \"height\": 96, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 858, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1771, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 856, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 855, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-li4rieeclo/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 608, \"height\": 345, \"label\": \"Table\"}]"
motivation: 现有TTA方法多针对特定任务，缺乏统一框架，且对于像素级任务（如分割）需保留几何信息。
method: 提出自引导方案，通过优化测试图像与其频域感知退化视图的一致性来实现TTA，并设计保留几何信息的低频增强。
result: 在图像分类、目标检测和语义分割等多个任务上超越现有TTA方法，尤其保持了像素级预测的空间准确性。
conclusion: 所提通用TTA框架可有效处理多种分布偏移，并为像素级任务提供稳健的适应策略，具有广泛适用性。
---

## Abstract
In this paper, we seek to develop a versatile test-time adaptation (TTA) objective for a variety of tasks — classification and regression across image-, object-, and pixel-level predictions. We achieve this through a self-bootstrapping scheme that optimizes prediction consistency between the test image (as target) and its deteriorated view. The key challenge lies in devising effective augmentations/deteriorations that: i) preserve the image’s geometric information, e.g., object sizes and locations, which is crucial for TTA on object/pixel-level tasks, and ii) provide sufficient learning signals for TTA. To this end, we analyze how common distribution shifts affect the image's information power across spatial frequencies in the Fourier domain, and reveal that low-frequency components carry high power and masking these components supplies more learning signals, while masking high-frequency components can not. In light of this, we randomly mask the low-frequency amplitude of an image in its Fourier domain for augmentation. Meanwhile, we also augment the image with noise injection to compensate for missing learning signals at high frequencies, by enhancing the information power there. Experiments show that, either independently or as a plug-and-play module, our method achieves superior results across classification, segmentation, and 3D monocular detection tasks with both transformer and CNN models.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有测试时自适应（Test-Time Adaptation, TTA）方法大多局限于特定任务（如图像分类），无法直接应用于回归任务（如目标检测、分割）。传统的基于熵最小化的方法只能用于分类，而基于一致性的方法（如MEMO）依赖强数据增强（如随机裁剪），会破坏图像几何结构（物体位置、大小），导致在细粒度任务上失效。此外，许多方法需要访问源数据（如对齐源统计量）或修改原始训练流程，限制了通用性和隐私保护。
- **核心目标**：提出一种**通用的、任务无关的、架构无关的完全TTA方法**，能同时支持分类和回归任务（图像级、目标级、像素级预测），且不依赖源数据、不改变原始训练过程。
- **整体含义**：通过自举（self-bootstrapping）学习，在保持几何结构的前提下，从测试图像的弱增强视图预测原图，从而提供丰富的学习信号，实现跨任务的统一TTA。

## 2. 论文提出的方法论

### 2.1 核心思想：主动自举学习（Active Self-Bootstrapping）
- **框架**：对测试图像 \(x\)，生成一个几何结构保持的弱增强视图 \(v = t(x)\)。将原图 \(x\) 作为强目标（stop gradient），将弱视图 \(v\) 的预测与 \(x\) 的预测进行一致性最大化。
- **损失函数**：
  \[
  \min_{\tilde{\theta}} S(v, x) \mathcal{L}_s\big(f(v;\theta), f(x;\theta)\big), \quad v = t(x),\; t\sim \mathcal{T}
  \]
  - \(\mathcal{L}_s\)：分类头用KL散度，回归头用L1损失。
  - \(S(v, x)\)：置信度感知的选择函数（仅当强视图的预测置信度高于弱视图时才进行优化），用于过滤不可靠的监督信号。
- **可学习投影头**：在最终预测头前插入可学习投影头（初始化为恒等映射），防止模型收敛到平凡解。

### 2.2 关键技术：保持几何结构的增强策略
- **动机**：常见的几何破坏增强（如随机裁剪）不适合目标级/像素级任务。需要设计既能提供足够学习信号又不破坏几何信息的增强。
- **基于傅里叶域的分析**：
  - 通过径向平均功率谱密度（RAPSD）分析常见分布偏移（噪声、模糊、天气等）在频域的表现。
  - **发现**：低频分量携带高信息量（RAPSD高），屏蔽低频能产生大的学习信号；高频分量RAPSD低（尤其模糊下更低），屏蔽高频提供信号有限甚至有害。
- **提出的两种增强**：
  1. **低频幅度掩码**（Low-frequency Amplitude Mask）：
     - 对图像做FFT，将低频区域移至中心，随机将中心 \(\alpha h \times \alpha w\) 区域的一部分（掩码比率 \(m\)）置零，其余保持，再逆FFT得到弱视图。
     - 参数：\(\alpha=0.2\)，\(m=0.2\)。
  2. **高频噪声注入**（High-frequency Noise Injection）：
     - 直接向原图添加高斯噪声：\(v_h = (1-\gamma)x + \gamma\epsilon\)，\(\epsilon\sim\mathcal{N}(0,1)\)。
     - 参数：分类 \(\gamma=0.4\)，检测/分割 \(\gamma=0.1\)。
- **组合使用**：对同一图像分别生成两个弱视图（低频掩码图、噪声注入图），分别与强视图做一致性学习。

## 3. 实验设计

### 3.1 数据集与场景
- **分类**：
  - ImageNet-C（15种 corruption，severity level 5）
  - ImageNet-R（艺术渲染）
  - ImageNet-A（自然对抗样本）
  - ImageNet-Sketch（素描）
- **3D单目目标检测**：
  - KITTI-C（13种 corruption，severity level 1），使用MonoFlex作为源模型。
- **分割**：
  - 源模型：Cityscapes上训练的Segformer-B5；目标域：ACDC（Fog, Night, Rain, Snow），按序循环3轮进行连续TTA。
- **其他**：
  - CLIP模型跨数据集泛化（DTD, UCF101, Aircraft）
  - CLIP模型OOD鲁棒性（ImageNet-R）

### 3.2 对比方法
- **分类**：TENT, EATA, SAR, DeYO, ActMAD, CoTTA, ROID, CMF；以及与TTT-MAE、Diffusion-TTA等非完全TTA方法比较。
- **3D检测**：BN Adapt, TENT, EATA, ActMAD, MonoTTA。
- **分割**：TENT, CoTTA, DePT, VDP。
- **CLIP场景**：TPT, C-TPT, Tent, ETA, SAR, DeYO。

### 3.3 模型架构
- 分类：ViT-Base（timm预训练）
- 3D检测：MonoFlex（CNN）
- 分割：Segformer-B5（Transformer）
- 另在ResNet-50上验证分类任务。

## 4. 资源与算力

论文未明确说明训练整个实验的总算力，只在附录C提到了**推理速度**：
- 在单个A100 GPU上，ViT-Base处理ImageNet-C，SPA达到79 FPS（相比CoTTA的36 FPS），效率较高。同时，SPA-I（将两种增强合并为一张图）达到125 FPS。
- 未提及模型训练/适应过程中的GPU总时间或具体配置细节。

## 5. 实验数量与充分性

- **实验组数**：非常充分，涵盖：
  - 分类：4个benchmark（共5个数据集，35种分布偏移），与10+种SOTA方法对比。
  - 3D检测：KITTI-C（13种corruption），与5种基线对比。
  - 分割：ACDC连续TTA（4个条件×3轮），与5种方法对比。
  - 消融实验：组件消融（弱到强学习、主动选择、两种增强）、不同增强策略对比、参数敏感性、与常规增强对比、在多种模型架构上的验证等（约10+组表格）。
  - CLIP适应性实验。
- **公平性**：对比方法均采用公开代码和推荐超参，结果可复现。论文提供了详细实现细节（附录B）。
- **充分性**：实验覆盖了常见视觉任务和多种模型，同时验证了作为独立方法和作为插件模块的效果，消融实验完整，结论可信。

## 6. 论文的主要结论与发现

1. **通用性**：提出的SPA方法在分类、3D检测、分割三个完全不同类型任务上均取得最优或接近最优的结果，表明其作为通用TTA目标的潜力。
2. **有效性**：
   - 在ImageNet-C上比最佳熵方法（EATA）提升2.3%（70.1% vs 67.8%）。
   - 在KITTI-C上汽车AP³D|R40比MonoTTA提升1.4%（33.8% vs 32.4%），尤其对少类别（行人、骑车人）提升显著。
   - 在ACDC分割上，单独优于CoTTA，与CoTTA结合后平均mIoU提高2.2%（60.7% vs 58.5%）。
3. **增强策略的关键性**：基于傅里叶域分析设计的低频掩码+噪声注入，优于传统几何保持增强（灰度、对比度等），且对参数不敏感。
4. **弱到强学习的重要性**：单向弱→强学习比双向一致性（如BYOL）更适用于TTA，避免了不稳定的学习信号。
5. **可集成性**：SPA可作为插件与其他TTA方法（如ActMAD、TENT、CoTTA、MonoTTA）结合，进一步提升性能。

## 7. 优点

- **方法创新**：
  - 首次提出任务无关、架构无关的通用TTA目标，覆盖分类和回归。
  - 基于傅里叶理论分析分布偏移的频域特性，并据此设计几何保持增强，具有理论依据。
  - 主动选择机制（置信度门控）有效过滤不可靠监督，提高稳定性。
- **实验全面**：
  - 跨三个不同任务（分类、检测、分割）、多种模型（ViT, CNN, Segformer）、多种分布偏移（合成、自然、连续域）验证。
  - 消融实验充分，详细比较了不同增强策略、不同组件的影响。
  - 同时验证了独立方法和作为插件模块的灵活性。
- **效率高**：仅需两种弱增强，相比CoTTA（29种）或MEMO（64种）更高效，适合实时应用。
- **实用性强**：不依赖源数据，不修改原始训练，可直接应用于预训练模型。

## 8. 不足与局限

- **实验覆盖有限**：
  - 仅验证了视觉任务，未涉及NLP、语音等其他模态。尽管方法本身通用，但需要进一步验证。
  - 回归任务仅测试了3D检测中的坐标、尺寸、深度回归，未尝试其他回归任务（如深度估计、关键点回归）。
- **对CLIP模型跨数据集泛化效果不突出**：
  - 在CLIP的OOD任务上表现好，但在跨数据集（如DTD、UCF101）上增益有限（+0.7%），因为性能瓶颈主要在文本分支，而SPA仅适配图像编码器。
- **参数依赖**：
  - 低频掩码比例 \(\alpha\) 固定为0.2，噪声比例 \(\gamma\) 在不同任务需手动调整（分类0.4，检测/分割0.1），缺乏自适应机制。
- **潜在偏差风险**：
  - 主动选择机制依赖强视图置信度高于弱视图，当强视图本身不可靠时（如极端分布偏移），可能过滤过多样本，导致适应不足。论文未分析这种情况。
- **未考虑标签偏移**：
  - 方法假设仅存在协变量偏移，未讨论标签分布变化（如分类不平衡）下的表现。
- **资源未明确**：
  - 论文未报告完整训练阶段的算力消耗，不利于衡量可复现性。

（完）
