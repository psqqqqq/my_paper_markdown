# 文章翻译

Abstract Translation and Comparison

[English Original]
Survival analysis is a cornerstone of clinical research by modeling time-to-event outcomes such as metastasis, disease relapse, or patient death. Unlike standard tabular data, survival data often come with incomplete event information due to dropout, or loss to follow-up. This poses unique challenges for synthetic data generation, where it is crucial for clinical research to faithfully reproduce both the event-time distribution and the censoring mechanism. In this paper, we propose SURVDIFF, an end-to-end diffusion model specifically designed for generating synthetic data in survival analysis. SURVDIFF is tailored to capture the data-generating mechanism by jointly generating mixed-type covariates, event times, and right-censoring, guided by a survival-tailored loss function. The loss encodes the time-to-event structure and directly optimizes for downstream survival tasks, which ensures that SURVDIFF (i) reproduces realistic event-time distributions and (ii) preserves the censoring mechanism. Across multiple datasets, we show that SURVDIFF consistently outperforms state-of-the-art generative baselines in both distributional fidelity and survival model evaluation metrics across multiple medical datasets. To the best of our knowledge, SURVDIFF is the first end-to-end diffusion model explicitly designed for generating synthetic survival data.

[中文精准翻译]
生存分析通过对诸如癌细胞转移、疾病复发或患者死亡等事件发生时间结果进行建模，成为了临床研究的基石。与标准的表格数据不同，由于患者中途退出或失联随访，生存数据通常伴随着不完整的事件信息。这给合成数据生成带来了独特的挑战，而在临床研究中，忠实地再现事件时间分布和删失机制都至关重要。在本文中，我们提出了 SURVDIFF，这是一种专门为生存分析中生成合成数据而设计的端到端扩散模型。SURVDIFF 通过在生存定制损失函数的指导下，联合生成混合类型的协变量、事件时间和右删失状态，从而专门用于捕捉这种数据生成机制。该损失函数对事件发生时间结构进行了编码，并直接针对下游生存任务进行了优化，从而确保了 SURVDIFF 能够做到两点：第一是再现真实的事件时间分布，第二是保留删失机制。在多个医疗数据集上的实验表明，SURVDIFF 在分布保真度和生存模型评估指标上，均持续优于目前最先进的生成基线模型。据我们所知，SURVDIFF 是第一个显式设计用于生成合成生存数据的端到端扩散模型。

# 摘要核心概念与生存分析原理拆解

Core Concepts and Methodological Framework of Survival Analysis

[Methodological Framework and Domain Logic]
本篇论文的核心研究对象是生存分析中的多维联合分布生成问题。在临床医学统计中，传统的机器学习生成模型通常只能处理常规的二维表格数据矩阵，而生存数据的独特之处在于其因变量并非离散的分类标签或连续的常规数值，而是由生存时间和删失指示符共同构成的双变量复合结构。当研究人员试图利用深度神经网络合成虚拟患者微观数据集时，面临的最大技术瓶颈在于如何完美还原真实的删失机制。由于患者个体的异质性，失联或退出随访这一行为本身就与患者的临床协变量（如年龄、病理分期等）存在潜在的统计依赖关系。如果生成模型仅仅独立地模拟患者特征和生存时间，而忽略了删失机制的内在概率分布，那么合成出来的数据在投入下游生存任务（如 Cox 比例风险模型拟合或随机生存森林预测）时，就会因为选择性偏差而导致极大的偏误。

针对这一痛点，该研究利用生成式 AI 领域的扩散模型架构，创新性地提出了多变量联合生成的数学解法。其核心贡献在于设计了一个量身定制的生存损失函数，该函数不再像传统扩散模型那样盲目去最小化每个像素或数值的均方误差，而是直接将生存分析中的偏似然函数或累积风险函数项嵌入到神经网络的反向传播梯度流中。通过这种数学建模，扩散模型在进行一步步的去噪生成时，能够被迫在数学逻辑上遵循生存 horizon 的边界约束。这使得模型最终不仅能够忠实地输出高度保真、包含了连续与离散变量的混合类型协变量，还能确保每个虚拟样本的事件发生时间与右删失标签在概率空间上具有与真实临床医学数据完全一致的联合分布规律，从而在不泄露患者隐私的前提下，为医学研究提供高质量的仿真沙盒数据。

Advanced Hidden Concepts and Technical Subtleties in SURVDIFF

[Hidden Methodological Concepts and Mathematical Subtleties]
在这篇论文的工程实现与数学建模底层，实际上还纠缠着三个至关重要却未在摘要中展开的隐藏概念。首先是时间尺度的对齐与非负性约束问题。扩散模型在本质上是一个连续或离散步数的加噪与去噪过程，其生成的数值通常在全实数域内波动。然而，生存分析中的事件时间在物理和数学意义上必须是严格非负的（T >= C >= 0）。为了解决扩散模型可能生成负数时间这一致命缺陷，模型在底层必然引入了某种时间轴的对齐变换，例如在对数时间尺度（Log-time scale）上进行前向扩散，或者在损失函数中施加极其严厉的边界惩罚，从而确保生成的生命周期数据符合常识。

其次是多模态条件生成中的无分类器指导机制（Classifier-Free Guidance, CFG）。摘要中提到模型在生存定制损失函数的指导下联合生成协变量、时间和右删失状态。由于患者的临床特征（协变量）与最终的生存时间之间存在高度复杂的非线性相关性，普通的扩散模型很容易迷失方向，生成出“明明极度健康却瞬间死亡”的不合逻辑的样本。因此，算法在底层必须采用条件控制技术，将混合类型的临床协变量作为强烈的语义特征条件（Conditioning），去约束和引导时间与右删失状态的去噪轨迹，使得生存时间的生成不是盲目的随机抽样，而是严格基于患者基线特征的条件条件概率分布。

最后是生存数据的离散与连续混合采样的不连续性退化。扩散模型原本最擅长处理图像这种连续的像素数据，但临床协变量中充满了大量的离散分类变量，例如性别、是否吸烟或治疗分组，同时右删失指示变量 delta 也是一个绝对离散的 0 或 1 标签。在同一个扩散网络中，如何让连续的时间数值与离散的分类标签在加噪去噪过程中保持梯度的平滑传递，是该架构最硬核的工程含金量所在。这通常需要模型在底层引入类似 VQ-VAE 的文本离散化嵌入技术，或者采用特殊的连续化松弛策略（如 Gumbel-Softmax 重新参数化技巧），将离散的删失标签映射到高维连续空间进行扩散，最后在输出端进行硬阈值切分，从而完美攻克了生存分析数据“半连续、半离散”的世纪难题。
