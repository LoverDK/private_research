# 综合检索记录与复核边界

检索日期：2026-10-17—18，时区Asia/Shanghai；最终判断截止2026-10-18。任务为立项前查新，不是穷尽型系统综述。未来投稿窗口原定至2027-10-18，现优先满足2027年6月正式录用或正式出版。

## 分工与来源

- 文献子代理：GPT-6.1-sol，medium；直接层级/来源相关文献，GHCP向后引文和2026扩展。
- 反驳子代理：GPT-6.1-sol，medium；一般依赖、部分分区、记录链接、污染、稳健完成、有效样本量和统一框架。
- 理论子代理：GPT-6.1-sol，medium；独立检查抽样模型、oracle/并集证明、退化反例和计算归约。
- 主代理：核验GHCP/HCP关键正文、SymmPI期刊元数据、关键一般框架边界，综合裁决，查官方投稿日程。三者一致不作为证明。
- 访问范围：公开web检索；arXiv abs/HTML/PDF、PMLR、CVF、出版社页面、作者出版页、会议和期刊官方站。第三方搜索片段只用于发现。
- 子代理实际检索词和逐篇阅读位置保留于 [直接文献日志](./search_literature.md) 和 [反驳日志](./search_adversarial.md)；以下保留主代理实际搜索组，不把计划搜索混入执行记录。

## 冻结研究问题

1. 部分可见来源分组下的新来源边际预测是否已被直接研究或已有定理简单覆盖？
2. 对所有可行分区的oracle集合取并集解决了什么；哪部分仍有统计/计算内容？
3. 对本科生和有限算力是否可行；2027年6月录用/出版硬节点下应如何取舍？

## 主代理实际搜索词

### 主代理检索组 1（2026-10-17）

- `COPA 2027 conformal probabilistic prediction applications conference submission`
- `COLT 2027 call for papers deadline`
- `AISTATS 2027 call for papers important dates`
- `ICML 2027 dates call for papers`

### 主代理检索组 2（2026-10-17）

- `site.learningtheory.org colt2027 call papers`
- `site.learningtheory.org colt2026 call papers submission deadline`
- `site.icml.cc 2027 conference dates`
- `site.neurips.cc 2027 dates`

### 主代理检索组 3（2026-10-17）

- `site.imstat.org electronic journal statistics submission scope`
- `site.bernoullisociety.org Bernoulli journal submission instructions scope`
- `site.jmlr.org author guide submissions`

### 主代理检索组 4（2026-10-17）

- `"conformal prediction" "unknown" "clusters"`
- `"conformal" "partial" "partition"`
- `"conformal" "record linkage"`
- `"conformal" "missing group"`

### 主代理检索组 5（2026-10-17）

- `"conformal prediction" "unknown groups"`
- `"conformal prediction" "group membership" "missing"`
- `"conformal prediction" "record linkage"`
- `"conformal prediction" "provenance"`

### 主代理检索组 6（2026-10-17）

- `"SymmPI" Dobriban Yu`
- `"Distribution-free prediction sets with random effects" Dunn Wasserman`
- `"Conformal prediction with hierarchical data" Lee Barber Willett`
- `"CS-WCP"`

### 主代理检索组 7（2026-10-18）

- `site.auai.org uai2027 call for papers dates`
- `site.auai.org uai2026 important dates deadline`
- `site.jmlr.org tmlr rolling submission review timeline`
- `site.imstat.org "Electronic Journal of Statistics" "Manuscript"`

### 主代理检索组 8（2026-10-18）

- `"Test-time Augmentation Improves Efficiency in Conformal Prediction" CVPR 2025`
- `"Robust Yet Efficient Conformal Prediction Sets" site.proceedings.mlr.press`
- `"Distribution-Free Prediction Sets for Two-Layer Hierarchical Models"`
- `"Distribution-free inference with hierarchical data" "3786352"`

### 主代理检索组 9（2026-10-18）

- `site.dl.acm.org/doi/10.1145/3786352`
- `site.rinafb.github.io "Distribution-free inference with hierarchical data"`
- `site.academic.oup.com "SymmPI" "2025"`
- `site.tandfonline.com "Distribution-Free Prediction Sets for Two-Layer"`

### 主代理检索组 10（2026-10-18）

- `"SymmPI" "qkaf022"`
- `"3786352" "Journal"`
- `"Conformal Prediction Through the Lens of Hypothesis Testing" universality impossibility optimality`

### 主代理检索组 11（2026-10-18）

- `site.copa-conference.com "2027" "June 15"`
- `site.learningtheory.org "COLT 2027"`
- `site.icml.cc "2027" "Submission"`
- `site.auai.org "2027"`
## 定向全文访问和核验

- 先打开arXiv:2608.15500元数据，再读v1正文A1–A3、Theorem2.1及相关证明定位。确认GHCP不是未知来源身份专用方法。
- HCP:2306.06342v4读取Definition1、Theorem1及Appendix E.1；SymmPI:2312.16160v3检查Thm4.2的一般观测映射；C-SymmPI:2605.17934v1检查带误差的加权条件结果，避免误写精确条件覆盖。
- 追踪Dunn、HCP、SymmPI基础链；最新定向补查到2026统一框架2504.02292v2、检验视角2608.27310v2、聚类阈值2608.21262v2（10月1日版本）。
- 独立核验ICML2024稳健共形、CVPR2025增强论文正式页面；增强论文§4明确先聚合增强结果再对原输入形成score。
- 官方会议/期刊范围与日期：COPA2027、COLT2027、ICML FutureMeetings，UAI/ICML/COLT/NeurIPS2026周期参照，AISTATS2027已截止，TMLR FAQ和作者说明、EJS、Bernoulli。2026-10-18最后再次访问COPA、COLT、TMLR及ICML官方页。
- 读取UCI Parkinsons Telemonitoring官方元数据，没有下载或运行数据实验。

## 已处理的分歧

1. GHCP起点真实，但“最接近”按设定判断，HCP与一般对称框架更关键。
2. 群对称性论文的层级例知道分支，不等于其一般obs定理不能表示来源缺失；保留框架覆盖风险。
3. HCP公开作者页列ACM JDS，但无法直接读正式页，正式发表年不填；预印本版本可核验。
4. 数学基线不代表新颖性：union覆盖是直接推论；特定DP未查到相同发表，不能写成“已经完全发表过”，也不能把常规归约当论文级贡献。
5. K未知但B已知时有ceil(N/B)下界，不能一律说K=1导致全空间。
6. 原始score无限制时数值阈值差可被缩放放大；主目标须用尺度不变损失或明确增加正则条件。
7. 六月“见稿”已明确为正式录用或上线，不用投稿/preprint替代。

## 尚未解决的检索限制

- 未做付费数据库和所有被引文献的全量遍历；无法保证收齐检索日所有公开预印本。
- record linkage、entity resolution、partially observed partition、unknown dependency graph的检索未产生经原文确认的直接解，**不等于这些领域无人研究此事**。
- Cauchois等Robust Validation全文PDF读取失败，只作元数据/摘要级背景。
- ACM HCP页面访问受限；UAI2027本轮未获得可读CFP。标为待核而不臆测。
- CS-WCP编号月份与submission日期显示不一致，污染论文HTML渲染日期异常；使用可信正式年份或仅标预印本年份，记录异常不据此推断精确首发时间。
- Noonan与检验视角论文使用最新已核验v2；工作日志里的旧版本节号不直接进入最终结论。
- 没有确认具体2027 workshop的适配CFP及六月前正式出版时间，不以未核验workshop凑渠道数量。

## 后续更新规则

新增论文须同时记录检索词/日期、元数据来源、读到的假设/定理/证明、与本题抽样单位及覆盖目标的差别。若只有标题/摘要证据，单列待精读，不能推翻或支持精确理论判断。只有官方CFP发布后才能把推测日期升级为确认日期。主报告及文献清单优先于代理工作笔记。

