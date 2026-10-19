# 检索日志

日期：2026-10-17；范围：公开英文网络检索、arXiv 元数据与 HTML 正文、出版社 DOI/官方会议论文/作者页面；检索按主流层级数据理论、未知来源机制、相邻群对称性与稳健性、增强/重复数据四个视角串行进行。没有付费数据库或系统引文图全量索引。

2026-10-18 增量补核：直接访问 arXiv:2605.17934 的 abs 与 HTML，核验作者为 Yichen Shen、Mengxin Yu，v1 日期 2026-05-18；读取 Theorem 3.1、Algorithm 1、§4.2.1–4.2.2、G.2 proof，并定向查找 unknown。结果：一般 obs 框架允许 completion，但具体层级例子给定分支关系，未提出来源分组缺失算法；near-conditional guarantee 是函数加权误差界而非精确逐分支条件覆盖。未重新开展广泛搜索。

2026-10-18 元数据补核：作者 https://yhoon31.github.io/publications.html 明确将 HCP 列为 ACM Journal of Data Science，Publication 链接指向 ACM；作者页面年份按预印本始发年份分组，不能据 2023 标题推断正式期刊年。ACM DOI 页面不可读，2026 发表日期单独降级为待直接核实。另直接读取 UCI Parkinsons Telemonitoring 官方页面，未下载：42 subjects、5875 recordings、subject# 为 ID、约890KB数据文件、目标 UPDRS 为线性插值值、无原生缺失、CC BY 4.0。

2026-10-18 最后引用边界复核：补读 TTA 论文 https://arxiv.org/html/2505.22764 的 §4，确认多增强预测先聚合为一个原始输入的概率向量，独立D_TTA学习权重、D_cal校准。不是把增强视图当独立校准观测。用户要求2027年6月前正式录用或上线；预印本或已投稿不满足其约束，不能把本文核验的预印本状态当已发表替代品。

## 一个轻量真实数据候选

[UCI Parkinsons Telemonitoring](https://archive.ics.uci.edu/dataset/189/parkinsons+telemonitoring)，DOI 10.24432/C5ZS3N。官方页面确认 42 位早期 Parkinson 患者在六个月内的 5875 次声音记录；subject# 唯一标识来源，16个声音指标，motor_UPDRS / total_UPDRS 为响应。数据文件约889.9KB；无需图像/原始音频。42个来源可作教学级 source split，但来源级有效样本数较小：例如12训练、20校准、10测试，alpha=.1时可给有限阈值；若只剩少数完整已知来源，保守方案很容易退化。每次测试应先均匀选保留患者再在其记录内均匀选一个，或逐患者均分权重汇总覆盖，不按5875行等权。数据不自带来源缺失，必须明确人工遮蔽 subject#；来源 iid 是实验模型假设，非元数据证明。响应为临床分数线性插值，不能当独立即时临床真值。官方页面的约200条/患者与5875/42平均约140条并不相符，避免照抄近似数量；实际组大小待下载后核验。本步骤没有下载数据。

## 研究问题

RQ1：已知依赖来源分组时，有哪些有限样本方法可适配新来源内均匀观测？
RQ2：未知或部分缺失来源身份是否已有直接方法？一般 group symmetries / partial observation 框架是否覆盖？
RQ3：重复/增强、组大小差异、有效样本数与来源标签缺失的贡献边界在哪里？

## 实际关键词

- hierarchical conformal prediction clustered data Lee Barber Willett 2026
- conformal prediction partial unknown group labels clustered provenance duplicates augmentation
- conformal unknown clusters calibration
- conformal prediction duplicate data augmentation
- conformal partially observed group dependence
- conformal clustered data Dunn Wasserman
- Distribution-free prediction sets for two-layer hierarchical models arxiv
- conformal prediction data augmentation dependence
- conformal unknown grouping
- conformal provenance calibration
- Conformal Prediction for Hierarchical Data Principato
- conformal missing group labels
- conformal partially known groups
- conformal unknown group membership dependence
- SymmPI 2025 JRSSB
- The Exceedance Design Effect arxiv
- Test-time Augmentation Improves Efficiency in Conformal Prediction authors

## 顺序与范围

1. 首先直接访问 https://arxiv.org/abs/2608.15500，元数据为 GHCP、四位作者、2026-08-16；随即读 v1 HTML 正文 A1–A4、Theorem 2.1、Appendix A.2 与 E.1。
2. 经 GHCP References 反查 HCP、Dunn、SymmPI；分别打开 arXiv 元数据及全文，读取定理与证明位置，详见 agent_literature.md。
3. 直接查 unknown grouping / partially known groups / missing group labels / provenance，主要返回类别、部分响应、人口子群或不相关物理共形文献；未检出直接“依赖来源标签部分缺失”论文。
4. augmentation / duplicate 搜索发现 CVPR 2025 TTA 及多篇增强论文；未据摘要归纳其理论。
5. 发现 2026-10 更新的 Noonan 2608.21262，查元数据、Theorem 1、原假设、证明和重复反例；纳入最新直接对照。
6. 查 Barber 等 Beyond Exchangeability 原定理与官方 PDF，作为错分组稳健性相邻方法。

## 核验标准

每条主要引用做“作者/题名/年份存在性 + 正文结论相符”两步核验。六篇主要文献均有原始正文链接；HCP、GHCP、Dunn、SymmPI、Noonan 已读相关定理和证明段落。发表状态以 arXiv/官方期刊/作者声明核验；仅软件与 JSM 摘要的 missing-response 工作不提升为正式定理证据。检索未命中仅记为本范围未检出。

技能依据：C:/Users/Qiutian/.codex/skills/deep-research/SKILL.md 与 references/citation-protocol.md。未让生成式二手论文解读充当定理证据。
