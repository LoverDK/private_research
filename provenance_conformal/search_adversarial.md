# 反驳视角检索日志

日期：2026-10-17 至 2026-10-18，Asia/Shanghai。读取 deep-research/SKILL.md 及 references/citation-protocol.md。使用 web 搜索和 arXiv/作者/正式 proceedings 原文核验；搜索引擎的第三方摘要仅用于发现，结论以 primary source 为准。未覆盖所有数据库、未做付费数据库引用网络穷尽。

## 冻结问题

RQ-A：未知或部分可见来源分组是否被已存在依赖共形、污染稳健共形或 record linkage 定理直接覆盖？

RQ-B：所有兼容分组的共形集合并集是否已经提供基本有效解，且该思路是否有发表先例？

RQ-C：在统计本科与笔记本资源下，什么比简单并集更可能构成真正理论贡献？

## 宽检索关键词（均已实际检索）

- conformal prediction partially observed groups unknown dependence partition
- conformal prediction record linkage errors latent groups robust unknown dependence
- conformal prediction unknown dependency graph exchangeability robust partition
- conformal prediction uncertain partition clustering dependence hierarchical
- conformal prediction record linkage errors duplicate contamination
- "conformal" "unknown dependence"
- "conformal" "record linkage"
- "conformal" "dependency graph"
- "conformal" "uncertain" "partition" robustness
- "conformal prediction" "Beyond Exchangeability" Barber 2023
- "conformal" "effective sample size" dependence
- "conformal" "unknown" "dependence structure"
- "conformal" "partially observed partition"
- "conformal prediction" "poisoning" "calibration" guarantees
- "conformal prediction" "unknown groups" dependence
- "conformal prediction" "missing" "cluster labels"
- "conformal prediction" "dependence graph"
- "conformal prediction" "unknown partition"
- "conformal prediction" "uncertain grouping"
- "conformal prediction" "group labels" "missing" dependence
- "conformal" "record linkage" -site:researchgate.net -maintenance
- "conformal prediction" "partition uncertainty"
- "conformal prediction" "latent groups" calibration dependence

## 收窄检索及原文核验

- 直接打开 https://arxiv.org/abs/2608.15500 与 https://arxiv.org/html/2608.15500v1 ：确认 GHCP 题名、四位作者及 v1 日期。
- https://arxiv.org/html/2202.13415v5 ：搜索 Theorem 1、total variation；细读 §4.1 Theorem 2、§4.3、§4.5，确认不是未知分组的可计算小误差现成结论。
- "Split Conformal Prediction under Data Contamination" arxiv；正式 PMLR 与 https://arxiv.org/html/2407.07700v1 ：细读 §3 iid 混合模型、Lemma 1 及证明，区别来源信息缺失与独立污染。HTML 页显示日期异常为 2026-08-24，而文首 arXiv v1 日期是 2024-07-10，出版年份使用 COPA/PMLR 2024。
- "Robust Yet Efficient Conformal Prediction Sets" ICML 2024 PMLR；https://arxiv.org/html/2407.09165v1 ：细读 §3.2 Prop 3.2、§3.3 Eq (5)，最坏分位数与 MILP。
- https://arxiv.org/abs/2609.27955 与 https://arxiv.org/html/2609.27955v1 ：细读 Eq (8)、Theorem 2、Appendix A.1/A.2，确认兼容权重并集、覆盖和 O(G|Y|) 精确优化。ID 月份与 abs submission 日期不一致，记录为 2026 预印本，不推断九月首次公开。
- https://arxiv.org/abs/2608.21262 与 https://arxiv.org/html/2608.21262v1 ：细读 (A1)–(A3)、Theorem 1、ragged family、§10，确认有效样本量结果为渐近，Beta 是近似。
- Cauchois Gupta Ali Duchi 2024 robust validation conformal prediction；https://arxiv.org/abs/2008.04267 ：核验题名作者、摘要。https://arxiv.org/html/2008.04267v5 返回404；PDF读取失败，因 23.7 MB 超出工具内容大小。因此本轮仅摘要级使用，不给定理级解释。
- "conformal prediction" "record linkage errors"；"conformal prediction" "dependency graph" statistics calibration；"conformal prediction" "unknown dependence structure" ：未发现直接来源分组不确定性定理。命中 computational dependency graph / LLM filtering 等，概念不相同，排除。

## 检索结论的边界

未检索到 ≠ 不存在；本轮没有逐篇追踪所有 HCP 引用和被引文章，也没有覆盖截至 2026-10-18 当天每份新预印本。CS-WCP 与 ESS 新预印本宜在正式报告中标明未经同行评议，且核对版本元数据异常。已检验的邻近定理没有直接吞掉完整来源不确定问题，但足以吞掉基本“并集保证”“最坏兼容分位数保证”“泛化 TV 覆盖缺口保证”的空泛创新宣称。

## 2026-10-18 主代理指定的有界补查

- 打开 https://arxiv.org/abs/2608.27310 ，确认三作者、v2 日期2026-09-23；阅读 https://arxiv.org/html/2608.27310v2 的 §2 Proposition1、§3 Theorem3、§5 Theorems4/5及Corollary1、§6 Theorem7。版本交叉发现 v1 Theorem4 的 sup 在 v2 改为 inf，报告以 v2 为准。记录交换、条件覆盖与本题来源交换/边际覆盖的区别。
- 打开 https://arxiv.org/abs/2504.02292 ，确认两作者与 v2 日期2025-12-21；阅读 https://arxiv.org/html/2504.02292v2 的 §3 Theorem2、§4.6 Theorem7、§7。核查其“partial information”只是任意 U 的框架，而非未知来源关系的专用解；generalized WCP明确要求排列似然比已知。
- 实际搜索："Unifying Different Theories of Conformal Prediction" "1428"；以 https://www.stat.berkeley.edu/~ryantibs/research.html 与 https://rinafb.github.io/research/ 核验 EJS20(1):1428–1474,2026。没有再向外追引文。
