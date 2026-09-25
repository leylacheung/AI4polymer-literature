# AI 与聚合物：模型方法文献调研

调研截止：2026-09-25。主要时间范围：2023-09-25—2026-09-25。

本报告整理本次对话中的文献检索和用户补充清单，聚焦聚合物专用表示、性质预测、逆向设计、主动学习及原子模拟。属于代表性文献整理，不是系统综述或穷尽检索。方法归纳以出版社摘要、论文页面、预印本及作者仓库为依据，未逐篇复现。预印本的结论需与同行评审论文区别使用。

## 1. 分类框架

建议同时记录“研究任务”和“主要贡献”，避免将数据集、综述、模型架构及材料应用混为一类。

| 维度 | 分类 |
|---|---|
| 研究任务 | 性质预测、结构/构象生成、逆向设计、主动实验设计、模拟加速、合成规划 |
| 主要贡献 | 表示方法、模型架构、预训练/学习策略、优化流程、数据库/基准、材料发现、综述/观点 |
| 验证层级 | 数据集预测、代理模型打分、独立物理模拟、实验合成、器件验证 |

结构合法、预测性质达标、模拟验证通过和实验可合成是不同证据层级。不同论文的误差或生成率只有在数据、划分和评价协议一致时才能直接比较。

## 2. 代表性方法论文

### 2.1 表征学习与性质预测

| ID | 论文 | 年份/渠道 | 方法贡献 |
|---|---|---|---|
| R01 | [Self-supervised graph neural networks for polymer property prediction](https://doi.org/10.1039/D4ME00088A) | 2024，Molecular Systems Design & Engineering | 面向包含组成和随机链结构的聚合物图，比较节点、边和图级自监督预训练，缓解标签稀缺。 |
| R02 | [MMPolymer: A Multimodal Multitask Pretraining Framework for Polymer Property Prediction](https://arxiv.org/abs/2406.04727) | 2024，CIKM | 联合一维序列与三维结构，采用掩码预测、坐标去噪和跨模态对齐；提出 Star Substitution。 |
| R03 | [PolyCL: contrastive learning for polymer representation learning via explicit and implicit augmentations](https://doi.org/10.1039/D4DD00236A) | Digital Discovery，2025 卷期；2024 年已有预印本 | 显式与隐式增强相结合的对比学习，可作为冻结特征提取器。 |
| R04 | [Unified multimodal multidomain polymer representation for property prediction](https://www.nature.com/articles/s41524-025-01652-z) | 2025，npj Computational Materials | Uni-Poly 融合 SMILES、二维图、三维几何、指纹及文本，构建 Poly-Caption。 |
| R05 | [Learning Repetition-Invariant Representations for Polymer Informatics](https://proceedings.nips.cc/paper_files/paper/2025/hash/7fe3921147c968d0b57a224c0d07e21d-Abstract-Conference.html) | 2025，NeurIPS | GRIN 通过图对齐与重复单元增强学习重复表示不变性，并提供理论分析。此不变性不意味着真实分子量不会影响性质。 |
| R06 | [Joint embedding predictive architecture for self-supervised pretraining on polymer molecular graphs](https://doi.org/10.1039/D5DD00308C) | 2026，Digital Discovery | polymer-JEPA 用于小样本性质预测及跨化学空间迁移，包括电子亲和能和共聚物相行为。 |

### 2.2 生成、逆向设计与合成规划

| ID | 论文 | 年份/渠道 | 方法贡献 |
|---|---|---|---|
| R07 | [On-demand reverse design of polymers with PolyTAO](https://www.nature.com/articles/s41524-024-01466-5) | 2024，npj Computational Materials | 条件 Transformer 从属性生成聚合物，支持半模板和无模板生成及下游微调。 |
| R08 | [De novo design of polymer electrolytes using GPT-based and diffusion-based generative models](https://www.nature.com/articles/s41524-024-01470-9) | 2024，npj Computational Materials；预印本始于 2023-12 | 比较 GPT 与扩散生成，结合预训练/微调，通过全原子 MD 评价候选电导率。 |
| R09 | [Inverse design of copolymers including stoichiometry and chain architecture](https://doi.org/10.1039/D4SC05900J) | Chemical Science，2025 卷期；2024 在线发表 | 半监督图到字符串 VAE，同时生成单体组合、比例和链结构，通过潜在空间优化设计。 |
| R10 | [polyBART: A Chemical Linguist for Polymer Property Prediction and Generative Design](https://aclanthology.org/2025.findings-emnlp.647/) | 2025，Findings of EMNLP | PSELFIES 支持分子语言模型向聚合物迁移，联合性质预测与生成，包含实验合成验证。 |
| R11 | [POLYT5: an encoder-decoder foundation chemical language model for generative polymer design](https://www.nature.com/articles/s44387-026-00087-1) | 2026-03，npj Artificial Intelligence | 基于 T5 和超过一亿条聚合物结构预训练，支持性质预测、条件生成及介电聚合物实验验证。论文注明相关数据因知识产权考虑未公开。 |
| R12 | [PolyRL: reinforcement learning-guided polymer generation for multi-objective polymer discovery](https://doi.org/10.1039/D5DD00272A) | Digital Discovery，2026 卷期；2025-11 在线发表 | 结合生成预训练、性质奖励、多目标强化学习及分子模拟，用于气体分离聚合物。 |
| R13 | [polyRETRO: a language model approach to predict polymerization class and monomers for a target polymer](https://www.nature.com/articles/s44387-026-00113-2) | 2026-05，npj Artificial Intelligence | 从聚合物结构预测聚合类别、反应模板和单体；当前验证主要针对均聚物，不能视为完整实验条件规划。 |

### 2.3 三维构象与模拟

| ID | 论文 | 年份/渠道 | 方法贡献 |
|---|---|---|---|
| R14 | [PolyConf: Unlocking Polymer Conformation Generation through Hierarchical Generative Models](https://proceedings.mlr.press/v267/wang25ah.html) | 2025，ICML | 分层生成重复单元局部构象，再通过扩散模型生成位姿并组装整链，提供 MD 构象基准。 |
| R15 | [polyGen: A Learning Framework for Atomic-level Polymer Structure Generation](https://arxiv.org/abs/2504.17656) | 2025，预印本 | 图编码与潜在扩散 Transformer 生成原子级聚合物结构，利用小分子数据联合训练。 |
| R16 | [SimPoly: Simulation of Polymers with Machine Learning Force Fields Derived from First Principles](https://arxiv.org/abs/2510.13696) | 2025，预印本 | 量子化学数据驱动的机器学习力场，用于密度和玻璃化转变等模拟，提供 130 种聚合物实验体相性质基准。 |

### 2.4 新近预印本与基准

| ID | 论文 | 时间/状态 | 方法贡献 |
|---|---|---|---|
| R17 | [A Conformation-Centric Generative Foundation Model for Linear Polymer Modeling and Design](https://arxiv.org/abs/2510.16023) | 2025-10 首发，2026-06 更新；预印本 | PolyConFM 以局部构象重建和位姿生成为预训练任务，面向线性聚合物。早期标题为 Unifying Polymer Modeling and Design via a Conformation-Centric Generative Foundation Model。 |
| R18 | [PolyFusionAgent: A Multimodal Foundation Model and Autonomous AI Assistant for Polymer Property Prediction and Inverse Design](https://arxiv.org/abs/2605.26543) | 2026-05-26；预印本 | 多模态表征与文献检索、工具调用结合，连接预测、逆向设计和证据检索；不能据此推定已完成实验闭环。 |
| R19 | [Uni-Macro-FRPN: Full-Resolution and Cross-Scale Learning for Polymers](https://arxiv.org/abs/2609.23611) | 2026-09-20；预印本 | 双 Transformer 联合原子级化学、单体序列和链拓扑，面向跨尺度与复杂架构表征。 |
| R20 | [Benchmarking study of deep generative models for inverse polymer design](https://doi.org/10.1039/D4DD00395K) | 2025，Digital Discovery | 比较 VAE、AAE、ORGAN、CharRNN、REINVENT、GraphINVENT，并研究强化学习定向生成。 |

## 3. 用户补充文献分类

保留用户原编号，便于对照。分类不意味着每项均满足严格时间窗口。

| 原编号 | 文献 | 主类别 | 判定与备注 |
|---|---|---|---|
| 1 | Mitigating systematic bias in polymer Tg prediction via role-decoupled graph readout | 性质预测 / GNN 架构 | 根据题名暂归为通过图读出改进 Tg 预测偏差的方法。本次未取得出版社正文；检索到的 DOI 为 [10.1016/j.commatsci.2026.115032](https://doi.org/10.1016/j.commatsci.2026.115032)，书目及模型细节需进一步核对。 |
| 2 | G2RINS: A Generative String-and-Graph Polymer Representation to Assist Computational Materials Discovery | 表示方法 / 基础工具 | [作者仓库](https://github.com/depablolab/g2rins)支持字符串、生成图和链集合，表达组成、连接及分子量分布。“生成”不直接等同于深度生成模型；论文正式出版信息待确认。 |
| 3 | [Mechanical property prediction of random copolymers using uncertainty-based active learning](https://doi.org/10.1016/j.commatsci.2024.113489) | 主动学习 / 力学性质预测 | 不确定性驱动选择 MD 标注样本，提高小数据预测效率。[作者机构摘要](https://scholars.lib.ntu.edu.tw/entities/publication/54898519-bb26-4bc3-af20-e91b6c003f94)。 |
| 4 | [Active Learning for Data-Scarce Multi-Objective Polymer Design: Robust Strategies with Experimental Validation](https://doi.org/10.1016/j.rineng.2026.111974) | 多目标主动学习 / 实验设计 | 比较高斯过程框架中的初始化与采集策略，以实验验证刚度与松弛的权衡。网页卷期为 2026-12，首次在线日期尚未核实，暂不纳入严格截止日期内的已确认论文统计。 |
| 5、11 | [Rapid Neural Network Prediction of Linear Block Copolymer Free Energies](https://arxiv.org/abs/2603.17391) | 物理引导代理模型 / 热力学预测 | 以模拟能量统计量训练前馈网络预测自由能，加速 BAR 相关计算；不是原子间势模型。两项重复。 |
| 6 | [Data-Driven and Physics-Guided Design of Viscosity-Modifying Polymers](https://doi.org/10.26434/chemrxiv-2025-td5v6) | 生成设计 / 贝叶斯优化 / 物理指导 | 拓扑生成、高斯过程和流体动力学模拟结合，并用标度关系指导外推。作者和框架与第 10 项对应，疑似同一工作的预印本，版本关联待核实。 |
| 7、12 | [Foundation Models for Atomistic Simulation of Chemistry and Materials](https://arxiv.org/abs/2503.10538) | 观点 / 综述；原子模拟基础模型 | 讨论机器学习原子间势、预训练、扩展规律和评估，并非新聚合物专用模型。两项重复；正式 DOI：[10.1038/s41570-025-00793-5](https://doi.org/10.1038/s41570-025-00793-5)。 |
| 8 | Benchmarking Study of Deep Generative Models for Inverse Polymer Design | 基准评测 / 生成式逆向设计 | 即 R20，比较现有生成模型并研究定向优化。 |
| 9 | [Graph Neural Networks for Polymer Characterization and Property Prediction: Opportunities and Challenges](https://doi.org/10.1021/acs.jcim.5c02421) | 综述 / GNN 与聚合物 | 梳理图表示、预测、数据资源与挑战，适合研究背景和问题定位。 |
| 10 | [Generative active learning across polymer architectures and solvophobicities for targeted rheological behavior](https://www.nature.com/articles/s41524-025-01900-2) | 生成式主动学习 / 流变逆向设计 | 调整架构和溶剂疏避性以匹配剪切黏度曲线；2025-12 在线发表，2026 卷期。与第 6 项按同一文献族暂存，避免直接重复计数。 |
| 13 | [OpenPoly: A Polymer Database Empowering Benchmarking and Multi-property Predictions](https://doi.org/10.1007/s10118-025-3402-y) | 数据库 / 多性质预测基准 | 3985 条聚合物—性质数据点、26 种性质；比较多种编码和模型。数据点数不等于独立聚合物数。 |
| 14 | [BRICS-Based Generation and AI-Assisted Screening of Ionic Liquids with Mechanistic Insights into Lithium Transport in Electrolytes](https://doi.org/10.1021/acs.jcim.5c01824) | 规则式分子生成 / 筛选 / 输运机理 | BRICS 片段重组、ML 打分及 MD 验证。直接对象是离子液体；BRICS 本身不是深度生成网络。 |
| 15 | [Machine learning-guided discovery of ionic polymer electrolytes for lithium metal batteries](https://www.nature.com/articles/s41467-023-38493-7) | 材料发现流程 / 实验及器件验证 | 筛选离子液体后与聚合物和锂盐组装电解质。发表于 2023-05-15，在严格三年窗口之外，保留作背景。 |
| 16 | VAE、AAE、ORGAN、CharRNN、REINVENT、GraphINVENT | 模型清单 | 不是独立论文，为第 8 项中的比较对象。 |
| 17 | VAE/AAE 与强化学习微调结果描述 | 基准结果 / 强化学习定向生成 | 不是独立论文；结论应限定于第 8 项的数据和评估条件。真实聚合物数据训练不代表生成候选已经实验合成。 |

## 4. 六类生成模型的区别

| 模型 | 方法类别 | 生成机制 |
|---|---|---|
| VAE | 变分自编码 | 学习潜在分布后采样、解码 |
| AAE | 对抗自编码 | 通过对抗训练约束潜在分布，再解码 |
| ORGAN | 对抗生成与目标奖励优化 | 联合判别器反馈和性质奖励 |
| CharRNN | 字符级自回归序列生成 | 逐字符生成结构字符串 |
| REINVENT | 序列生成与强化学习 | 利用奖励优化生成策略 |
| GraphINVENT | 图自回归生成 | 通过逐步图操作构造结构 |

来源：[R20 基准论文](https://doi.org/10.1039/D4DD00395K)。模型家族、训练策略和目标任务是不同维度；采用强化学习微调后，基础生成架构并不会因此变成另一种网络家族。

## 5. 建议阅读路线与选题

- 表征与预测：MMPolymer → PolyCL → GRIN → polymer-JEPA → Uni-Macro-FRPN。
- 逆向设计：PolyTAO → 共聚物图到字符串 VAE → polyBART → POLYT5 → PolyRL。
- 三维与模拟：PolyConf → polyGen → PolyConFM → SimPoly。
- 主动学习与物理指导：用户第 3、4、5、6/10 项。
- 数据与评估：OpenPoly、生成模型基准 R20；用户第 7/12、9 项用于建立领域背景。

以下是基于上述文献的研究建议，而非已证实的研究空白：

1. 将共聚比例、序列、链拓扑、分子量分布纳入统一表示，并检验每个信息层的贡献。
2. 区分重复单元“表示方式不变性”与真实链长引起的物理性质变化。
3. 加强跨化学骨架、跨链长、跨架构及跨实验条件的泛化测试。
4. 将三维构象分布、物理先验及不确定性引入预测与优化。
5. 在生成中结合聚合反应、单体可获得性与独立模拟/实验验证。

阅读或复现时，重点核查数据来源、实验与模拟标签混用、结构去重、训练测试泄漏、基线强度、数据/代码开放程度和计算成本。主动学习应比较随机采样、空间填充和多样性采样；生成应比较有效性、独特性、新颖性、性质达标与独立验证，避免仅依赖同一个代理模型自评。

## 6. 窗口外基础文献

- [TransPolymer: a Transformer-based language model for polymer property predictions](https://www.nature.com/articles/s41524-023-01016-5)，2023-04-22。
- [polyBERT: a chemical language model to enable fully machine-driven ultrafast polymer informatics](https://www.nature.com/articles/s41467-023-39868-6)，2023-07-11。

以上两篇可作基础背景，但不计入 2023-09-25 起的严格三年统计。

## 7. 书目维护说明

- 预印本与期刊版按同一研究去重；年份须区分预印本首发、在线发表与卷期年份。
- 用户第 1 项的出版社正文、第 2 项的正式出版状态、第 4 项的首次在线日期，以及第 6/10 项的版本关联仍需补核。
- 本报告为中文概括及原文链接，不包含论文全文或付费附件。
