# 来源分组部分缺失的共形预测：独立查新证据

检索日期：2026-10-17；C-SymmPI 定向补核：2026-10-18。读者：统计本科生；目标：固定预测模型、训练与校准无来源重叠、来源间 iid 或交换、来源内任意依赖；预测一个新来源内均匀抽取的观测。以下“来源”是产生依赖的单位，如病人、原始图像、文档、用户；不是分类标签，也不是为公平覆盖而定义的人口子群。

## 查新结论与边界

最直接的基础工作是 Lee–Barber–Willett 的 HCP，而非 GHCP。已知分组时，组等权、组内均分权重加测试组 infinity mass 的构造已有有限样本理论。仅把该构造应用于重复数据或增强视图，不能作为充分新意。本次未检出以“依赖来源分组部分缺失/分组集合不确定”为主问题、同时覆盖上述完整设定的论文；这只是公开检索范围内的未检出，不是不存在的证明。SymmPI 已提供一般观测算子与对称性推断框架，因此“对缺失结构做完成再反演”的思想必须说明相对该框架的额外内容。

关键设定差别：HCP 原定理要求组内交换性，并非字面上的任意有序依赖。但用户预测的是组内独立均匀抽中的观测。对每个完整来源独立施加均匀随机排列可把任意来源向量转为组内交换向量，且保持组内经验分布；这为使用 HCP 提供直接扩展论证。该结论是本报告的推论，不是文献声称的新定理。它要求完整来源向量及大小共同交换，抽样与分组缺失机制仍需单独处理。

## 已核验的核心文献

### 1. Distribution-free inference with hierarchical data

Yonghoon Lee, Rina Foygel Barber, Rebecca Willett。arXiv 首版 2023，读取 v4（2025-08-02）。2026-10-18 补核：[作者 publication 页面](https://yhoon31.github.io/publications.html) 明确列 ACM Journal of Data Science 并提供 Publication 链接，故期刊归属有作者一手支持；但作者按首版年份归于 2023，未标期刊年份，ACM DOI 页面本次打不开。具体“2026 正式出版日期”不算独立核实；2026 年及 DOI 10.1145/3786352 有 GHCP 引用与第三方元数据支持。正式报告宜采用 arXiv 2023 / v4 2025 为无争议主版本，期刊状态注明作者页面列于 ACM JDS。

- 元数据及正文：[arXiv](https://arxiv.org/abs/2306.06342)、[全文](https://arxiv.org/html/2306.06342v4)、[期刊 DOI](https://doi.org/10.1145/3786352)。
- 定位：Definition 1；§2.1 Theorem 1；§2.3 Proposition 1；Appendix E.1。
- 原假设：可变长来源向量整体交换，各来源内部条件于长度后交换；校准与训练按来源分开。无须组内独立。
- 主结果：K1 个校准来源时，权重为 1/((K1+1)Nk)，余下 1/(K1+1) 放在 +infinity；对新来源首点覆盖至少 1−alpha。上界的额外条件是跨来源不出现相同分数，允许同来源重复；上界为 1−alpha+2/(K1+1)。
- 证明核查：E.1 在固定训练数据后构造包含完整测试来源的组等权经验分位数；用两层交换性把目标事件概率改写为所有组内指标的等权平均；将测试来源总质量移到 +infinity 使阈值增大。
- 与课题关系：oracle baseline 和最直接证明模板；全文未把校准来源身份缺失作为问题。不要把已有组等权校准宣称为新方法。

### 2. Generalized Hierarchical Conformal Prediction

Soham Mallick, Eric Tchetgen Tchetgen, Edgar Dobriban, Yonghoon Lee。2026-08-16 提交，arXiv:2608.15500v1，44 页、13 图；当前记录只核验到预印本，未见期刊发表声明。

- [元数据](https://arxiv.org/abs/2608.15500)、[正文](https://arxiv.org/html/2608.15500v1)。此 URL 与题名及作者相符，真实存在。
- 定位：§1.1 Assumptions A1–A3；§2.2 Theorem 2.1；Appendix A.2、E.1 Lemmas E.1–E.2。
- 问题：测试来源已经有固定 o 个观测，参考来源大小随机；通过随机“捐赠”一个参考来源大小恢复对称性。
- 假设：潜在来源 law 与来源协变量交换；参考来源大小交换且独立于来源 law/协变量；给定来源 law，来源内 iid，来源间条件独立。A3 强于仅组内交换。
- 定理：A1–A3 下有限样本覆盖至少 1−alpha；无 ties 的 A4 用于额外上界。E.1 先证明捐赠后层级交换，再用部分观测来源的 coverage lemma E.2。
- 与课题关系：不是来源身份缺失；没有处理未知校准分组。用户的新来源无先验观测，GHCP 的核心困难并不出现。其 size ignorability 不能暗中加入用户更弱设定。

### 3. Distribution-Free Prediction Sets for Two-Layer Hierarchical Models

Robin Dunn, Larry Wasserman, Aaditya Ramdas。arXiv 首版 2018；Journal of the American Statistical Association 118(544), 2491–2502，2023。

- [arXiv](https://arxiv.org/abs/1809.07441)、[正文](https://arxiv.org/html/1809.07441)。期刊信息亦见 GHCP References。
- 定位：§4.1 Theorem 7；§4.2 Theorem 9；§4.3 Theorem 10；无监督类似结果为 §3。
- 设定：来源分布 iid 抽自一个分布上的分布，每个来源内部条件 iid，来源身份已知。
- 定理区分：平均组内经验 CDF 的 pooling 主要给随来源数增长的渐近覆盖；每来源取一个观测得到 iid 代表，Theorem 9 给有限样本 1−alpha；重复 subsampling 的平均 p 值直接以 alpha 为阈值，Theorem 10 只保证 1−2alpha（欲保 1−alpha 应作校正）。
- 证明核查：Theorem 9 归约标准 conformal；Theorem 10 使用两倍平均 p 值的有效性，不把相关重复子样本当独立。
- 与课题关系：来源代表抽样基线；不能把 repeated subsampling 的经验 1−alpha 误写成其原定理保证。未知来源分组仍未解决。

### 4. SymmPI: Predictive Inference for Data with Group Symmetries

Edgar Dobriban, Mengxin Yu。arXiv 首版 2023；JRSS Series B 87(5), 1353–1381，2025，DOI 10.1093/jrsssb/qkaf022。

- [arXiv](https://arxiv.org/abs/2312.16160)、[正文](https://arxiv.org/html/2312.16160)、[期刊](https://doi.org/10.1093/jrsssb/qkaf022)。
- 定位：Theorem 4.2、§4.4.4、§5、Theorem 5.3；证明 §9.1。
- 原理论：完整数据分布对群作用不变，score 变换分布等变，观测为任意已指定算子 obs(Z)；构造与观测相容的完整数据区域。
- 定理：确定性区域至少 1−alpha；边界随机化区域精确 1−alpha。§9.1 用轨道上的随机群变换与不变阈值证明，不依赖普通逐点交换。
- 与课题关系：最强相邻理论框架，允许部分观测；“未知分组视为 latent full data”可能落入其一般理论。但必须指定真实分组上的不变性及观测机制，不能从任意 obs 自动推出一个可计算、有限阈值的来源校准方案。文章的 hierarchical examples 使用已给定树/分支关系。

### 5. Conformal Prediction Beyond Exchangeability

Rina Foygel Barber, Emmanuel J. Candès, Aaditya Ramdas, Ryan J. Tibshirani。Annals of Statistics 51(2), 816–845，2023；DOI 10.1214/23-AOS2276。

- [期刊 PDF](https://projecteuclid.org/journals/annals-of-statistics/volume-51/issue-2/Conformal-prediction-beyond-exchangeability/10.1214/23-AOS2276.pdf)、[正文](https://arxiv.org/html/2202.13415)。
- 定位：§4 Theorem 2；§6.2 proof；附录一般 score 扩展。
- 结果：非交换 full/split conformal 的覆盖缺口由数据/残差与 calibration-test 交换后的分布之间 total variation 的加权和控制。固定独立训练模型符合 split 版本。
- 与课题关系：可为错分组的稳健性提供比较背景；TV 项在任意来源内依赖下可能很大或未知，因此不能直接宣称恢复 1−alpha，也不能用“相关系数小”替代其 TV 假设。本课题更有价值的目标是利用来源结构不确定集合得到可核查的显式界。

### 6. The Exceedance Design Effect: Effective Sample Size for Thresholds under Clustering

Adam Noonan。arXiv:2608.21262；v1 2026-08-21，v2 2026-10-01；已核验预印本，未核验到同行评审发表。

- [元数据](https://arxiv.org/abs/2608.21262)、[正文](https://arxiv.org/html/2608.21262)。
- 定位：§2.1–2.2 Theorem 1 与其紧随证明；§2.4；§4.3 Proposition 2；Appendix B.1。
- 假设：等大小 iid 来源，组内交换；score 连续边际，测试 score 独立同边际。来源数增长而组大小固定。
- 主结果：pooled score 分位数的 calibration-conditional coverage 一阶波动有设计效应 D(p)=1+(m−1)rho_I(p)，其中 rho_I 是阈值指标相关而非 score 相关；证明由独立来源 count CLT 与次序统计量事件反演组成。
- 限制：这是渐近方差结果，n/D 不能直接作为 conformal 的“有效样本数”换取有限样本秩覆盖。§2.4 明确指标相关也不决定二阶平均覆盖偏差，并给重复项反例。任意依赖、未知分组、可变且信息性大小均需额外分析。
- 与课题关系：2026 年最新直接相关的反驳/对照文献；不能笼统声称此前无人研究依赖校准或 duplicates。

### 7. Conditional Predictive Inference for General Structured Data with Group Symmetries（C-SymmPI）

Yichen Shen, Mengxin Yu。arXiv:2605.17934v1，2026-05-18。核验到预印本；元数据未声明期刊/会议录用。

- [元数据](https://arxiv.org/abs/2605.17934)、[正文](https://arxiv.org/html/2605.17934v1)。
- 定位：Algorithm 1；Theorem 3.1；§4.2.1 Assumptions 4.1–4.3；§4.2.2；Appendix G.2。
- 核验结论：不能简单称它“只允许已知来源结构”。一般定理允许任意预先指定 obs(Z)，Algorithm 1 枚举所有与观测相容的 complete-data completion；理论上可把某些结构隐去。但必须先构造固定已知的群及其对完整对象的作用，使完整数据 law 不变，且 score 变换确定性等变。论文未给部分来源身份缺失时如何构造该作用、保证相容分组集合或高效计算的具体方案。
- 覆盖含义：Theorem 3.1 是函数 f 加权的覆盖误差，界为 penalty error 加 interpolation error；并非无需误差项的逐个分支条件 1−alpha 覆盖。G.2 使用轨道 pinball-loss 凸优化的一阶次梯度条件，再以群不变性把轨道平均换为总体期望。
- 具体层级例子：§4.2.1 给定来源向量与大小，要求大小机制独立数据 law、组内与组间交换；§4.2.2 的 obs 明确保留分支结构、仅隐去最后来源最后观测的响应。这与用户的未知 calibration 来源身份不同。
- 新意约束：若研究仅声称“允许隐变量/部分结构观测”，已有 SymmPI / C-SymmPI 的一般 obs 框架会构成重要先例；应突出有限样本 marginal 来源覆盖、可计算的 worst-case partition 阈值、sharpness/非平凡性，且避免不必要地转向更难的 near-conditional 目标。

## 十二项紧凑阅读表

前七项为本报告实质相关主清单；后三至五项是边界核验，不能计作解决同一问题的理论工作。总表十二项避免无限扩展。

| 优先级 | 文献 | 状态/年份 | 用途与原文读取层级 |
|---|---|---|---|
| 核心 | Lee–Barber–Willett, Distribution-free inference with hierarchical data | 作者页面列 ACM JDS，正式年份待直接核实；arXiv 2023 / v4 2025 | Definition 1、Theorem 1、E.1 精读 |
| 核心 | Dunn–Wasserman–Ramdas, Distribution-Free Prediction Sets for Two-Layer Hierarchical Models | JASA 2023；预印本始于2018 | Theorems 7、9、10 及证明理由精读 |
| 核心 | Dobriban–Yu, SymmPI | JRSSB 2025 | Theorem 4.2、§9.1 精读 |
| 核心 | Mallick et al., GHCP | arXiv 2026 | A1–A3、Theorem 2.1、E.1 精读 |
| 核心 | Shen–Yu, C-SymmPI | arXiv 2026 | Theorem 3.1、Algorithm 1、§4.2、G.2 精读 |
| 对照 | Barber et al., Beyond Exchangeability | Annals of Statistics 2023 | Theorem 2、split 适用范围核验 |
| 对照 | Noonan, Exceedance Design Effect | arXiv v2 2026-10 | Theorem 1、证明、duplicates 反例精读 |
| 增强边界 | [Shanmugam–Lu–Sankaranarayanan–Guttag, Test-time Augmentation Improves Efficiency in Conformal Prediction](https://arxiv.org/abs/2505.22764) | CVPR 2025 | 官方论文与作者元数据核验；未用摘要推断理论 |
| 术语排除 | [Ding et al., Class-Conditional Conformal Prediction with Many Classes](https://arxiv.org/abs/2306.09335) | NeurIPS 2023 | 类别聚合，不是依赖来源 |
| 术语排除 | [Principato et al., Conformal Prediction for Hierarchical Data](https://arxiv.org/abs/2411.13479) | TMLR 2026 | 线性加总层级，不是来源层级 |
| 术语排除 | [Javanmardi–Sale–Hofman–Hüllermeier, Conformal Prediction with Partially Labeled Data](https://proceedings.mlr.press/v204/javanmardi23a.html) | COPA 2023 | partial label 是响应集合 |
| 相邻缺失性 | [Yi–Wang 等, Hierarchical Conformal Prediction for Clustered Data with Missing Responses](https://ww2.amstat.org/meetings/jsm/2025/onlineprogram/abstract.cfm?sid=2860&tid=3495) | JSM 2025 摘要；软件2026 | 响应缺失；未获得正式定理全文 |

## 需排除的同词异义

- Ding 等 Class-Conditional Conformal Prediction with Many Classes（NeurIPS 2023，arXiv:2306.09335）：cluster 是合并类别进行条件覆盖，不是引起数据相关的来源组。
- Principato 等 Conformal Prediction for Hierarchical Data（arXiv:2411.13479，2026 TMLR）：hierarchy 指多变量分量满足线性加总约束与 forecast reconciliation，并非来源内相关的层级样本。
- Javanmardi 等 Conformal Prediction with Partially Labeled Data（COPA 2023，PMLR 204:251–266）：partial label 指响应类别集合，不是来源身份缺失。
- Yi、Wang 等 Hierarchical Conformal Prediction for Clustered Data with Missing Responses（JSM 2025 abstract，HCPclust 软件 2026）：missing responses 是响应缺失。只核验到会议摘要和官方软件文档，不能将摘要里关于局部/渐近条件覆盖的话写成已经读到的正式定理。
- augmentation 文献如 Shanmugam 等 CVPR 2025 Test-time Augmentation Improves Efficiency in Conformal Prediction（arXiv:2505.22764），与增强有关。2026-10-18 已补读正文 §4 Proposal / Preserving exchangeability：每个原始输入的多个增强 logits 经学习权重聚合为单个概率向量，再为该原始输入计算一个 conformal score；独立 D_TTA 学聚合权重，D_cal 用于阈值。它没有把增强视图当作多个独立 calibration 观测，也不解决来源身份缺失；应作为 score 效率的背景，不作为未知来源依赖校准的直接先例。

## 对理论选题的约束

1. 应把假设写在“完整来源随机向量（含大小）+分组信息观测机制”层面，避免只写来源 law iid 而忽略大小是否信息性。
2. 部分来源标签缺失不等于缺失观测；完整分组是否仍在相容集合中，必须有确定性保证或至少 1−delta 的同时概率保证。
3. 最坏分组取 supremum 阈值是可证明的稳健构造，但要有非平凡效率/可计算性定理，才有超过 oracle HCP 加 union containment 的学术价值。
4. 若不用分组，直接把未知点当各自新来源，通常不能保住来源交换性。根据样本值进行恢复/聚类还可能产生选择偏差。
5. 对手审查应比较 HCP oracle、single subsampling、pooled baseline、保守只用完整已知来源（须证明其保留机制可忽略），以及最坏相容分组方案。

## 检索完整性说明

已沿 GHCP 的参考文献回溯 HCP、Dunn、SymmPI，并独立搜索 unknown grouping、missing group labels、provenance、duplicates、augmentation 和最新 cluster effective-size 工作。尚不能证实“来源标签部分缺失的共形预测”为无人做过；应以明确的观测机制、非平凡保证与算法贡献限定查新主张。
