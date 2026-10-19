# 反驳性查新：来源分组部分不可见的共形校准

检索日期：2026-10-17 至 2026-10-18（Asia/Shanghai）。范围：固定预测模型、训练与校准来源无重叠、来源独立或交换、来源内部任意依赖、新来源均匀抽取一个记录；考察来源标识缺失或部分同源关系。本文是反驳视角工作记录，不是完整综述。

## 结论与最强反驳

本轮未检索到直接以“未知/部分可见来源分组 + 任意组内依赖 + 新来源均匀抽样”为完整对象的已核验定理。但这只能支持“本轮未找到”，不能支持首创声明。基础有效性并不构成足够贡献：已知分组时的 HCP，加上所有兼容分组的预测集合并集，已给直接保守解。

令真实分组为 Π，候选集合为 P(D)，且 Pr{Π∈P(D)}≥1−δ。若真实分组的 oracle 方法 C_Π 有无条件误覆盖≤α，则 C_rob=∪_{π∈P(D)} C_π 满足

Pr{Y不在C_rob}≤Pr{Y不在C_Π}+Pr{Π不在P(D)}≤α+δ。

不需要按候选分组数做 Bonferroni；也不需要每个错误候选在真实数据分布下有效。随机化 oracle 方法须使用同一可测构造/恰当耦合。这是集合包含和概率并集界，不能包装为主要新定理。若 P 由结果驱动构造，必须另证真实分组包含概率，不能默认其条件有效。

两篇原文进一步削弱“鲁棒并集 + 最坏分位数”的原创性：2024 年 Robust Yet Efficient Conformal Prediction Sets 已对兼容的被污染校准记录优化最保守分位数并用 MILP；2026 年 CS-WCP 明确对所有兼容权重取共形集合并集，并证明覆盖与精确端点计算。两者都不直接解决未知依赖分组，但方法论壳已存在。

若兼容类允许 K=1 个校准来源，而使用新来源 HCP 的测试来源 +∞ 质量 1/(K+1)，则 α<1/2 时该候选阈值为 +∞，并集为全空间。要给有信息的保证，必须由已知来源数下界、可靠异源关系、锚点或其他明确结构排除此类候选。此处是所述 HCP 并集的退化，不是“一切有效方法都必须全空间”的普遍不可能性定理。

## 6 篇核心相邻文献与覆盖边界

| 文献与可核验元数据 | 已读原文定位 | 对课题的反驳力度与边界 |
|---|---|---|
| Rina Foygel Barber, Emmanuel J. Candès, Aaditya Ramdas, Ryan J. Tibshirani. **Conformal prediction beyond exchangeability**. Annals of Statistics 51(2), 816–845, 2023. DOI 10.1214/23-AOS2276. [arXiv:2202.13415](https://arxiv.org/abs/2202.13415), [原文](https://arxiv.org/html/2202.13415v5#S4.SS1) | §4.1 Theorem 2；§4.3；§4.5 data-dependent weights。原文 HTML 354–360 行：覆盖≥1−α−Σ_i w̃_i TV(R(Z),R(Z^i))；原文 454–459 行强调随机权重须改为条件 TV。 | 一般联合依赖已在形式上覆盖，不能声称“首个允许任意依赖的覆盖界”。但未知来源分组不能自动给可计算的小 TV；完美同源重复时点交换可令 TV=1。可有真实剩余空间：以可观测部分来源结构推出更锐、可估计、可用的界。 |
| Maxime Cauchois, Suyash Gupta, Alnur Ali, John C. Duchi. **Robust Validation: Confident Predictions Even When Distributions Shift**. JASA 119(548), 3033–3044, 2024. DOI 10.1080/01621459.2023.2298037. [arXiv:2008.04267](https://arxiv.org/abs/2008.04267) | 题名、作者、摘要及正式出版元数据已交叉核验；PDF 23.7 MB 超出本轮 web 读取限制，未完成定理级审查。 | 分布不确定集合内最坏分布预测是既有主题；但摘要要求校准/训练数据交换，不能据此声称其有限样本定理直接解决未知校准依赖。此文在本报告只作摘要级相邻背景，不引用定理号。 |
| Jason Clarkson（arXiv v1 显示 Jase Clarkson）, Wenkai Xu, Mihai Cucuringu, Gesine Reinert. **Split Conformal Prediction under Data Contamination**. COPA 2024, PMLR 230:5–27. [正式页](https://proceedings.mlr.press/v230/clarkson24a.html), [arXiv:2407.07700](https://arxiv.org/abs/2407.07700), [原文](https://arxiv.org/html/2407.07700v1#S3) | §3 Eq (4) 明确独立同分布 Huber 混合；§3.1 Lemma 1 给 KS 距离乘污染率的覆盖偏差界，证明利用测试分数独立于校准分位数；§4 CRCP。 | 来源关系错误并非 iid 分数污染。不能直接把“缺失来源标签比例”代成污染比例：一个错误合并/拆分可改变整来源权重和依赖结构。若最后理论只是“坏事件概率 ε 则覆盖损失≤ε”，创新很弱。 |
| Soroush H. Zargarbashi, Mohammad Sadegh Akhondzadeh, Aleksandar Bojchevski. **Robust Yet Efficient Conformal Prediction Sets**. ICML 2024, PMLR 235. [arXiv:2407.09165](https://arxiv.org/abs/2407.09165), [原文](https://arxiv.org/html/2407.09165v1#S3.SS2) | §3.2 Proposition 3.2 与 Eq (3)–(4)：最保守分位数优化；§3.3 Eq (5)：至多 k 个校准标签被翻转的最坏优化；§G MILP。HTML 115–129 行。原文使用高分表示 conforming，故优化方向与残差分数相反。 | 对兼容结构优化一个保守分位数 + 集合包含 + 有限样本覆盖的逻辑已明确发表。未知分组不同于特征/响应标签污染，因此不是直接覆盖，但必须解释专用算法/锐界比通用鲁棒框架多出了什么。 |
| Ibne Farabi Shihab, Fariya Afrin. **CS-WCP: Robust Conformal Sets for LLM-Judge Traffic Shifts with Uncertain Group Proportions**. 2026 预印本. [arXiv:2609.27955](https://arxiv.org/abs/2609.27955), [原文](https://arxiv.org/html/2609.27955v1) | Eq (8) 明确 Γ_CS=∪_{v∈W}Γ_v；Theorem 2：≥1−α−δ_w−τ_A−κ；Appendix A.1 通过置信事件、集合包含、WCP、TV 推出；Proposition 3/Appendix A.2 将线性分式 admission 化为各坐标端点规则，O(G|Y|)。HTML 122–132、229–251 行。 | 与候选分组不相同：这里固定或独立学习分区，校准数据 iid，未知的是群体比例。但“所有兼容参数的共形集合并集 + 置信预算 + 精确优化”已是明确邻近方案。**元数据异常**：ID 为 2609 而 abs submission 显示 2026-08-23；只记作 2026 预印本，不断言九月首发。 |
| Adam Noonan. **The Exceedance Design Effect: Effective Sample Size for Thresholds under Clustering**. 2026 预印本. [arXiv:2608.21262](https://arxiv.org/abs/2608.21262), [原文](https://arxiv.org/html/2608.21262v1#S2) | §2.1 (A1)–(A3)；§2.2 Theorem 1；§2.4 ragged sizes；§10 明确局限。Theorem 1 为固定 m、来源数 b→∞ 的 coverage CLT，其有效样本量使用阈值指示变量 ICC；Beta 是矩匹配近似。 | “按组内相关算有效样本量再修正”并非空白；但它没有有限样本精确分组不确定性保证，也没有解决未知来源标签。不得把近似 Beta law 作为有限样本定理。若课题只提出常见 design effect 修正，会很弱。 |

起点单独核验：[arXiv:2608.15500](https://arxiv.org/abs/2608.15500) 确为 **Generalized Hierarchical Conformal Prediction**，作者 Soham Mallick、Eric Tchetgen Tchetgen、Edgar Dobriban、Yonghoon Lee。abs 显示 v1 2026-08-16。详细 HCP/GHCP 假设与结果交由主线文献代理，本轮未重复深读。

## 未命中方向及排除的伪邻居

以 record linkage / entity resolution / missing cluster labels / partially observed partition / dependency graph / unknown dependence structure 为关键词，未找到经原文核实、直接为本课题提供现成定理的文献。检索命中多为：临床文本数据整理中的 record linkage；LLM 推理步骤的 computational dependency graph；图节点/网络链接预测；学习 demographic 或 feature-space 分组的 group-conditional coverage。这些分组不是“随机抽到的同一来源产生相关记录”，不能因名称相似就视为覆盖本题。

Chernozhukov–Wüthrich–Zhu (COLT 2018) 的块排列与近似随机化检验可作背景，原文摘要已核验，但没有证据表明它解决未知的潜在来源分组；不放入核心六篇以免稀释。

## 实际剩余空间与建议的硬门槛

较可信的最小题目是：已知至少若干互异来源锚点，一部分记录来源标识缺失；清楚限定未知记录能否属于全新来源、来源总数是否已知、何种缺失机制。先把所有兼容分组的 HCP 阈值最大值作为**必须超越或精确求解的基线**。

可被审稿人视为实质理论的候选产物：

1. 对这种特殊兼容分组类，推导最坏分位数的精确结构与高效算法，给可验证的复杂度和达到等式的分组构造；不能只枚举 Bell 数或照搬 MILP。
2. 分清“在 oracle HCP 阈值的逐点上包络中最小”与“所有满足无条件覆盖方法中的 minimax 最优”；前者由定义直接成立，后者需要独立统计下界。不要混淆。
3. 刻画可观测来源信息达到多少时，并集从全空间转为有限阈值，何时更多同源/异源信息严格改善阈值，并给反例说明来源数或缺失率本身不足够。
4. 若要更小集合，须说明采用何种比并集更弱的保证或新增可验证假设；不可无理由删除“看起来不合理”的分组。

这些是可能方向，不是本轮已经证明的新定理，也不构成可发表保证。固定模型与分数级模拟可在笔记本完成；最先应证明的是特殊分组优化问题，随后用小 N 穷举检验候选公式。若几周内只能得到 union lemma，应将项目定位为课程/本科研究练习或重新选择问题。

## 2026-10-18 定向补查：统一框架与最优性

以下仅补查主代理指定的两篇，不扩展为新一轮宽检索。

### Tibshirani–Barber–Ramdas 2026

Ryan J. Tibshirani, Rina Foygel Barber, Aaditya Ramdas. **Conformal Prediction Through the Lens of Hypothesis Testing: Universality, Impossibility, and Optimality**. [arXiv:2608.27310](https://arxiv.org/abs/2608.27310)。v1 2026-08-27，当前 v2 2026-09-23；以下依据 [v2 原文](https://arxiv.org/html/2608.27310v2)。

- §3 Theorem 3 的 universality 对所有**观测单位交换分布**下有效的方法成立；本题来源交换不能自动换成记录交换，故不直接解决未知分组。
- §5 Theorem 5 / Corollary 1 是对非原子 x 的完全分布无关**条件覆盖**所导致的大集合/无限期望长度。当前题目仅要求新来源抽样的边际覆盖，不能把它当成未知来源标签的不可能性证明。
- §6 Theorem 7 在目标评价分布 P=P_XY^(n+1) 下，比较所有对交换分布有效的方法，oracle 逆条件密度分数达到期望集合测度最优。评价分布、有效性分布类和允许使用的信息都与本题不同；它不证明某个分组上包络是 minimax 最优。
- 可借用的工具是 §2 Proposition 1 的任意分布类预测—检验对偶与 §5 Theorem 4 的凸包 TV 检验下界；仍须自己构造未知来源下的观察分布类。**版本警告**：v1 Theorem 4 将左侧写为 sup，v2 已改为 inf；应使用 v2，不能复制 v1 的公式。

结论：没有直接吞掉完整课题，但“首次用检验证明不可能性/共形最优性”这类宽泛贡献已经不可声称。未知来源模型中特定的观察等价性与锐下界仍需新证明。

### Barber–Tibshirani 2026

Rina Foygel Barber, Ryan J. Tibshirani. **Unifying Different Theories of Conformal Prediction**. Electronic Journal of Statistics 20(1):1428–1474, 2026；出版信息经[作者主页](https://www.stat.berkeley.edu/~ryantibs/research.html)核验。[arXiv:2504.02292](https://arxiv.org/abs/2504.02292)，v1 2025-04-03、v2 2025-12-21；以下依据 [v2 原文](https://arxiv.org/html/2504.02292v2)。

- §3 Eq (6)、Theorem 2 为任意联合 (Z,U) 与指定参考条件分布 Q_(Z|U) 给 p 值有效性加上 (S,T) 联合分布的 TV 误差；原文 HTML 285–314 行。将 U 称为“部分信息”并不等于已经解决来源标签缺失：还要构造可计算且正确的 Q，或给出有用 TV 上界。
- §4.6 Theorem 7（引 Prinster et al. 2024）处理一般非交换联合分布，但要求所有排列的联合似然比 f(z_σ)/f(z) **已知可计算**；HTML 739–790 行。仅知道部分同源关系和组内任意依赖时，该条件通常没有得到满足。
- §7 明确把未知/难算排列似然比的稳健扩展列为后续问题；HTML 1203 行。框架无意提供本题的来源可识别性或最坏兼容分组专用计算定理。

结论：它在抽象层覆盖几乎所有校准论证，因而“任意依赖 + 部分信息 + TV 损失”的泛化定理很可能只是实例化。可保留的贡献必须落实到本题的可观测信息、可计算界、特殊分组优化或独立下界。

## 最终新颖性结论审计（2026-10-18，不新增检索）

参考本轮两份同项目工作笔记 agent_literature.md、agent_theory.md 进行交叉审查；SymmPI / C-SymmPI 的细节来自文献代理已核验原文，未再独立重复检索。

| 威胁 | 可以吸收的层面 | 不能未经新增论证直接吸收的层面 |
|---|---|---|
| HCP + oracle 支配/并集 | 当前模型的基本覆盖存在性，已知来源组等权校准；再对可信完成取最大阈值 | MCAR 下信息效率、与所有边际有效方法比较的统计最优性 |
| SymmPI（JRSSB2025，Thm4.2，原文版本须注明） | 完整对象群不变性、任意观测算子、枚举相容完成后的预测区域：一般基础有效性框架已有 | 潜在分组须嵌入固定已知群作用并证明不变性；不能仅凭“obs任意”断言任意来源大小/身份缺失的具体计算公式已经发表 |
| C-SymmPI（arXiv2605.17934v1，Thm3.1/Alg1） | 带部分观测和相容完成的结构化条件推断框架 | Thm3.1是加权覆盖误差加 penalty/interpolation 项，并非本题自动精确 marginal 1−α；未知来源机制的群作用与可算性仍需证 |
| Unified framework（arXiv2504.02292v2，Thm2；Thm7） | 任意(Z,U)参考条件核+TV误差，已知排列似然比的一般非交换覆盖 | 参考核/似然比未知时的小可计算误差，来源信息量—效率定理 |
| Robust Yet Efficient（arXiv2407.09165v1，Prop3.2/§3.3） | 对兼容污染数据最坏分位数优化与覆盖证明，含MILP | 污染记录与未知分组是不同模型；其定理不能直接作为未知相关分组覆盖结论 |
| CS-WCP（arXiv2609.27955v1，Thm2/Prop3） | 参数置信集合上的共形集合并集及精确优化是明确先例 | 未知混合比例不等于未知依赖分组；日期元数据异常已说明 |
| 2026 universality（arXiv2608.27310v2，Thm3/5/7） | 记录交换类的普遍性/最优性和完全条件覆盖的经典不可能性；检验对偶工具 | 不直接给来源交换、部分来源身份、边际覆盖模型的下界；v1 Thm4的sup已在v2改为inf |

**推荐结论措辞**：“基础覆盖可由现有 HCP 与保守完成/并集原理直接获得；union 加标准 DP 本身不足以支持实质理论新颖性。尚可研究 MCAR 来源信息下的效率损失或匹配上下界，但本轮未证其原创性或可行性。”

将“union+DP不新”理解成“已经检索到完全相同的部分来源 DP 发表”则过强：目前没有这一证据，具体 DP 归约是本项目理论笔记中的标准工具设计。将“可能空间在MCAR效率/下界”理解成“已经确认的空白或能按期限发表”也过强。反过来，若仍把基本覆盖当待发现主定理，则过弱地估计了已有框架的威胁。

MCAR 有额外风险：当前稳健覆盖只用真实分组包含，连MCAR都不需要；p主要影响信息效率。组大小完全相等时标签根本不影响oracle，而无分布/尾部正则性时不宜直接求数值宽度一致收敛率，先考虑分位水平、秩差、截断或归一化损失。若只有概率1−(1−p)^m的可见性计算加通用浓缩，其新意也未必足够。2027年6月获得正式录用或上线的要求应被视为独立排期约束，现有查新不能对该未完成的强理论方向作成功承诺。
