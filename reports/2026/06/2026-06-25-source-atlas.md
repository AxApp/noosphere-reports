---
report_id: noosphere-source-atlas-2026-06-25
generated_at: 2026-06-25
visibility: public
source: noosphere-private-plus-public-official-docs
report_type: source_atlas
primary_category: source_operations
category_status: working_taxonomy
categories:
  - source_operations
  - global_foresight
  - public_intelligence
candidate_theme_hints:
  - oss_pain
  - developer_ecosystem
  - public_events
  - markets
  - security
  - research
  - climate
  - public_health
  - geopolitics
  - supply_chain
owning_team: agent-team:source-operations
truth_proven: false
opportunity_validated: false
production_active: false
agent_approved: false
self_approved: false
financial_advice: false
medical_advice: false
legal_advice: false
---

# Noosphere Source Atlas 2026-06-25

这是一份 Noosphere 数据源地图。产品方向已经从早期“需求发现”扩大为“全球洞察未来”：给 Intelligence Loop 提供尽可能广的公开 Observation 输入，先采集、去重、保存、标注来源，再进入 Evidence / Claim / Signal / Forecast / Scenario / Counter-Evidence / Calibration。NeedEmbryo / NeedCard 只是其中一种下游，不再是唯一终点。

信源分类的主轴也随之改变：不再按“API/RSS/JSON”这种传输方式分类，而按它对未来洞察的职能分类。

## 评分规则

总分 100：

- 信号价值 35：是否能暴露真实痛点、事件变化、需求、风险或趋势。
- 可接入性 25：是否有公开、后端友好、低摩擦 API/RSS/JSON/XML/CSV。
- 新鲜度 15：是否足够实时，适合 daily intelligence cycle。
- 稳定身份 15：是否有稳定 id / URL / timestamp，方便去重和 evidence ref。
- 合规与成本 10：是否无 key、无登录态、无反爬绕过、低成本。

## 全球洞察信源分类

| 职能分类 | 作用 | 代表源 | 评分权重倾向 | 使用方式 |
| --- | --- | --- | --- | --- |
| Primary Event Sensors / 一手事件传感器 | 捕捉已经发生或正在发生的世界变化 | GDELT、USGS、CISA KEV、NVD、SEC、Federal Register、WHO、ReliefWeb | 新鲜度、稳定 ID、可复查性 | 生成 Observation、Claim、ChangeEvent。 |
| Structural Context / 结构背景源 | 解释事件背后的制度、行业、地理、组织和历史结构 | World Bank、BIS、ECB、IMF、OpenAlex、Wikidata、RFC、MDN | 稳定性、覆盖面、实体解析 | 给事件和 forecast 补上下文，不直接触发结论。 |
| Leading Indicators / 领先指标 | 比新闻更早暴露变化方向 | GitHub activity、package downloads、Hugging Face trends、job posts、StackExchange unanswered、market/commodity movements | 领先性、时间序列、可量化性 | 进入 Signal Mining 和 Forecast Pipeline。 |
| Weak-Signal Communities / 弱信号社区 | 捕捉尚未制度化的新问题、新需求、新叙事 | HN、Reddit、V2EX、Nowcoder、Bluesky、Mastodon、Substack、Medium | 噪音控制、反证、聚类价值 | 只能做 weak signal，必须等待交叉证据。 |
| Expert / Research Evidence / 专家与研究证据 | 给趋势和假设提供专业支撑或反驳 | arXiv、OpenReview、PubMed、DBLP、OpenAlex、LessWrong | 专业性、可引用性、滞后性 | 支撑/反驳 claim，不作为实时事件源。 |
| Market / Capital / Adoption / 市场采用证据 | 观察资金、采用率、商业化和生态扩散 | CoinGecko、Binance、DefiLlama、Product Hunt、YC、Crunchbase News、npm、PyPI | 采用信号、操纵风险、时间序列 | 作为 adoption evidence，不输出投资建议。 |
| Counter-Evidence / 反证源 | 专门寻找相反证据、失败案例和过热风险 | 安全公告、issue 关闭/回滚、forecast miss、negative reviews、监管处罚、failed product launches | 反证强度、可追踪性 | 每个高分 signal 必须绑定反证检查。 |
| Calibration / Outcome Sources / 校准与结果源 | 检查 forecast 之后是否命中、错过或需要废弃 | 后续新闻、官方统计、release outcome、CVE exploit state、market settlement、SEC outcome | 回看能力、时间戳、不可抵赖性 | Forecast Scoreboard 和模型校准。 |
| Enrichment Directories / 实体补全目录 | 补全公司、国家、协议、包、论文、人物、地理实体 | Wikidata、REST Countries、OpenAlex、MDN、RFC、package metadata | 实体稳定性、去重帮助 | 只做 enrichment，不当作事实裁判。 |

## 数据源评分表

| 优先级 | 信源域 | 代表信源 | 分数 | 接入形态 | 中文说明 |
| --- | --- | --- | ---: | --- | --- |
| P0 | OSS 与技术生态领先指标 | GitHub Issues、Discussions、Search、Releases、Public Events | 96 | 官方 REST / 搜索 / 事件流 | 真实 bug、feature request、维护者疲劳、生态迁移和 adoption shift 都在这里。它不只是需求矿脉，也是技术未来变化的领先指标。官方入口：[GitHub REST API](https://docs.github.com/en/rest)。 |
| P0 | 技术问答与阻塞问题 | Stack Overflow / Stack Exchange search、unanswered、bounty、tag | 94 | 官方 API | unanswered 和 bounty 是强痛点；tag 维度适合做趋势和技术迁移。官方入口：[Stack Exchange API](https://api.stackexchange.com/docs)。 |
| P0 | Hacker / 创业社区 | Hacker News、Show HN、Ask HN、HN Algolia | 92 | 官方 Firebase API / RSS / Algolia | 早期产品、工具发布、开发者抱怨、新技术扩散都很密集。官方 API 有稳定 item id：[Hacker News API](https://github.com/HackerNews/API)。 |
| P0 | 中文开发者与泛社区 | V2EX、掘金、知乎、微博、百度热搜、36Kr、少数派、Nowcoder | 88 | hotlist / RSS / 公开 API | 补中文世界的需求、舆论和产品信号。热榜不能当真相，但很适合做 attention weather。 |
| P0 | Reddit / 垂直社区 | r/AppIdeas、r/SaaS、r/selfhosted、r/programming、r/sysadmin、RSS search | 86 | RSS 优先，JSON 暂缓 | 用户需求表达直接，但 JSON endpoint 反爬/403 风险高；先用 RSS 和 old web 兼容路径，避免默认引入登录态。 |
| P1 | 包生态趋势 | npm、PyPI、crates、Maven、NuGet、RubyGems、Packagist、Go proxy | 90 | 官方 registry API | 下载量、版本、依赖增长能发现工具迁移和生态机会；适合与 GitHub issue 交叉验证。 |
| P1 | AI / 模型生态 | Hugging Face models/datasets/spaces、arXiv、OpenReview、OpenAlex | 89 | 官方 API / Atom / JSON | AI 方向变化快，适合 forecast 和 source-quality scoring。arXiv API：[arXiv API](https://info.arxiv.org/help/api/index.html)，OpenAlex：[OpenAlex Docs](https://docs.openalex.org/)。 |
| P1 | 安全风险 | CISA KEV、NVD CVE、OSV、GitHub Advisories、security advisory RSS | 87 | 官方 JSON / API / RSS | 结构化、稳定 ID、强事件性，适合事件 trajectory 和 security opportunity radar。CISA KEV：[CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog)，NVD：[NVD Developers](https://nvd.nist.gov/developers/start-here)。 |
| P1 | 产品发布与采用雷达 | Product Hunt、YC、TechCrunch、Crunchbase News、Indie Hackers RSS | 84 | RSS / 部分 API | 用来观察“有人正在做什么”和资本/创业叙事如何移动，但不能证明趋势成立；需要和一手事件、包生态、社区反证交叉。 |
| P1 | 技术新闻 / 通用 RSS | Techmeme、The Verge、Ars、MIT TR、VentureBeat、BBC、Bloomberg RSS | 82 | RSS / Atom | 覆盖叙事变化和背景事件。适合统一 RSS-to-raw_items，不要每个 feed 单独手写 parser。 |
| P1 | 全球事件 | GDELT、ReliefWeb、USGS、WHO outbreak、Federal Register | 80 | API / JSON / RSS | 这是“天下消息”的事件底盘。GDELT 可作为全球新闻事件源：[GDELT Project](https://www.gdeltproject.org/)。 |
| P1 | 金融与市场 | CoinGecko、Binance、DefiLlama、Eastmoney、Sina Finance、ECB、BIS、World Bank | 79 | API / JSON / CSV | 市场变化能触发创业机会，但噪音高；只能做辅助 Evidence 和 forecast indicator，不能输出投资建议。 |
| P2 | 学术与知识图谱 | PubMed、DBLP、OpenAlex、Wikipedia trending、OEIS | 78 | API / RSS / JSON | 适合验证研究热度和术语扩散，不适合单独判断产品机会。 |
| P2 | 政府 / 监管 / 公司披露 | SEC EDGAR、OFAC、openFDA、USASpending、Federal Register | 77 | 官方 API / XML / JSON | 适合合规、行业变化、供应链风险。SEC 有官方 API 页面：[SEC EDGAR APIs](https://www.sec.gov/search-filings/edgar-application-programming-interfaces)。 |
| P2 | 社交新协议与创作者网络 | Bluesky public API、Mastodon feeds、Medium tag RSS、Substack public feeds | 74 | 公开 API / RSS | 趋势早，但身份归一和噪音治理难；作为 weak signal，不能作为主证据。 |
| P2 | 公共目录与实体补全 | MDN、RFC、Wikidata、REST Countries、Steam、TVMaze、Lichess | 70 | API / JSON | 主要做 enrichment、实体解析、背景补全，不是强需求源。 |
| P3 | 浏览器/登录/反爬源 | Bloomberg 正文、Reuters、Amazon ranking、Baidu Scholar、登录社区 | 45 | 暂缓 | 除非用户明确批准 browser/cookie 能力，否则只保留 RSS/摘要/公开 API。禁止把绕过反爬当默认采集能力。 |
| P3 | 大文件 / 流式源 | Ember CSV、JODI oil、RadNet、FIRMS、UCDP keyed datasets | 40 | 暂缓到离线/流式管道 | 有价值但不适合同步 collector。需要 key 管理、断点续传、限流、存储预算和回放 fixture。 |

## Wave 2 全球信源候选池

这批源补的是“全球洞察未来”的广度：冲突、宏观、公共卫生、气候灾害、交通供应链、科研专利、企业与开放数据。它们不替代 P0 开发者/安全/事件源，而是给 forecast 和 scenario 提供结构背景、领先指标、反证和校准结果。

| 职能分类 | 候选源 | 分数 | 接入状态 | 处理建议 |
| --- | --- | ---: | --- | --- |
| 一手事件传感器 | [UCDP conflict data](https://ucdp.uu.se/apidocs/) | 84 | 官方 docs 可访问；部分数据/API 可能需要 token | 高价值地缘冲突源；先登记为 gated source，等 token 策略明确后接。 |
| 一手事件传感器 | [ACLED](https://developer.acleddata.com/) | 82 | 官方 docs 简单探测 403 | 高价值但授权/账号边界明确；暂缓到 approved-key lane。 |
| 结构背景源 | [World Bank Indicators API](https://api.worldbank.org/v2/) | 88 | live JSON 成功 | 宏观、国家、发展指标底盘；适合长期结构变量和 forecast context。 |
| 结构背景源 | [Eurostat dissemination API](https://ec.europa.eu/eurostat/api/dissemination/statistics/1.0/data/tps00001?format=JSON&lang=en) | 86 | live JSON 成功 | 欧洲人口、经济、产业、价格、能源等结构背景源。 |
| 结构背景源 | [FRED API](https://fred.stlouisfed.org/docs/api/fred/) | 76 | docs 可访问；通常需要 API key | 高价值宏观时间序列；暂缓到 key lane，或只记录人工批准源。 |
| 结构背景源 | [Our World in Data Grapher](https://ourworldindata.org/grapher/annual-co2-emissions-per-country.csv) | 85 | live CSV 成功 | 气候、健康、能源、人口、教育等长期结构变量；适合 calibration 和背景补全。 |
| 公共卫生事件 | [WHO Disease Outbreak News](https://www.who.int/emergencies/disease-outbreak-news) | 82 | 页面可访问；RSS 旧路径失效 | 重要公共卫生事件源；先做 page/RSS discovery，不硬编码旧 RSS。 |
| 公共卫生事件 | [ClinicalTrials.gov API](https://clinicaltrials.gov/data-api/about-api) | 83 | live JSON 成功 | 医疗/药物/AI 临床研究趋势；适合研究证据和产业前置信号。 |
| 公共卫生事件 | [openFDA](https://open.fda.gov/apis/) | 82 | docs 可访问 | 药品、食品、设备、召回和不良事件；适合监管风险和反证源。 |
| 气候/灾害事件 | [NOAA CDO API](https://www.ncdc.noaa.gov/cdo-web/webservices/v2) | 78 | docs 可访问；通常需要 token | 气候历史数据强，但接入要处理 token 和限流。 |
| 气候/灾害事件 | [USGS Earthquake GeoJSON](https://earthquake.usgs.gov/earthquakes/feed/v1.0/geojson.php) | 87 | live JSON 成功 | 强一手事件传感器，稳定 ID/时间/地理字段好。 |
| 气候/灾害事件 | [NASA FIRMS](https://firms.modaps.eosdis.nasa.gov/api/area/) | 74 | docs 可访问；通常需要 map key | 火点/野火/环境冲击有价值；暂缓到 approved-key 或小样本 lane。 |
| 交通/供应链 | [OpenSky Network API](https://openskynetwork.github.io/opensky-api/rest.html) | 80 | docs 可访问 | 航空状态、拥堵、异常流量；适合供应链和区域事件交叉验证。 |
| 交通/供应链 | [IMF PortWatch](https://portwatch.imf.org/pages/data) | 83 | 页面可访问 | 港口、航运、贸易 chokepoint；适合地缘和供应链 scenario。 |
| 人口/迁移 | [UNHCR API](https://api.unhcr.org/docs/) | 84 | docs 可访问 | 难民、流离失所、迁移压力；地缘风险和人道事件背景。 |
| 专家/研究证据 | [Semantic Scholar API](https://api.semanticscholar.org/api-docs/) | 85 | docs 可访问 | 论文、引用、作者网络；补 arXiv/OpenAlex 的研究证据。 |
| 专家/研究证据 | [Crossref Works API](https://api.crossref.org/works) | 83 | live JSON 成功 | DOI、出版物、引用元数据；适合学术/产业证据索引。 |
| 专利/技术迁移 | [PatentsView API](https://patentsview.org/apis/api-endpoints) | 79 | docs 可访问 | 专利主题、申请人、技术扩散；偏慢但适合长期技术趋势。 |
| 企业/法人实体 | [Companies House API](https://developer.company-information.service.gov.uk/) | 78 | docs 可访问 | 英国公司注册、解散、财报事件；适合企业实体和结果校准。 |
| 企业/法人实体 | [OpenCorporates API](https://api.opencorporates.com/documentation/API-Reference) | 74 | docs 可访问；配额/授权需确认 | 全球公司实体补全；作为 enrichment，不当事实裁判。 |
| 开放网页底盘 | [Common Crawl Index](https://index.commoncrawl.org/) | 77 | docs 页面可访问 | Web-scale 历史抓取索引；适合离线研究，不适合同步 collector。 |
| 实体补全目录 | [Wikidata SPARQL](https://query.wikidata.org/) | 82 | live JSON 成功 | 实体关系、国家/公司/人物/机构补全；注意限流和查询复杂度。 |
| 天气/短期环境 | [Open-Meteo API](https://open-meteo.com/) | 81 | live JSON 成功 | 无 key 天气/气象源；适合事件解释和环境上下文。 |
| 弱信号/叙事变化 | [Google News RSS](https://news.google.com/rss/search?q=artificial%20intelligence%20when:1d&hl=en-US&gl=US&ceid=US:en) | 78 | live RSS 成功 | 适合主题级新闻发现和叙事变化；必须去重并回源到原始媒体 URL。 |
| 叙事/媒体监测 | [GDELT Television API](https://blog.gdeltproject.org/gdelt-2-0-television-api-debuts/) | 76 | 官方说明可访问 | 电视媒体叙事源；更适合批处理和专题研究，不放入默认同步 collector。 |
| 注意力/校准源 | [Wikimedia Pageviews API](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews) | 80 | 官方 docs 可访问 | 页面访问量可作为公众注意力 proxy；只能辅助判断关注度，不能证明现实变化。 |
| 反证/事实核查 | [IFCN / Poynter fact-check network](https://www.poynter.org/ifcn/) | 66 | 页面可访问；机器接口需继续确认 | 作为反证目录候选；除非找到稳定 feed/API，否则先做人工/半自动源登记。 |

## Wave 3 Subagent 并行补源与主控裁决

本轮由 3 个 subagents 并行调研：地缘宏观、科技研究、风险校准。主控裁决只合并对 Global Foresight Intelligence 有直接价值、且边界清晰的源。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 安全领先指标 | [FIRST EPSS](https://www.first.org/epss/api) | 88 | REST API / CSV | 接入。给 CVE forecast 加“被利用概率”领先指标；不能当 exploitation truth。 |
| OSS 安全反证 | [OSV API](https://google.github.io/osv.dev/api/) | 87 | POST JSON API | 接入。和 package registries / GitHub repos 交叉做供应链风险反证。 |
| OSS 安全反证 | [GitHub Global Security Advisories](https://docs.github.com/en/rest/security-advisories/global-advisories) | 85 | REST API | 接入。未认证限流低；后续可走 approved token lane。 |
| 安全上下文 | [CISA Vulnrichment](https://github.com/cisagov/vulnrichment) | 86 | GitHub repo / CSAF JSON | 接入。增强 NVD/CISA KEV 的 CVE 语义、SSVC、CWE/CVSS。 |
| 天气灾害事件 | [NOAA National Weather Service Alerts](https://www.weather.gov/documentation/services-web-api) | 88 | REST JSON/GeoJSON | 接入。美国短期高新鲜度灾害 alert，适合 event trajectory。 |
| 全球自然事件 | [NASA EONET](https://eonet.gsfc.nasa.gov/docs/v3) | 86 | REST JSON | 接入。全球自然事件传感器，和 GDACS/ReliefWeb 去重。 |
| 全球灾害预警 | [GDACS RSS](https://www.gdacs.org/xml/rss.xml) | 85 | RSS/XML | 接入。全球灾害 alert；详细事件 API 后续验证。 |
| 人道灾害事件 | [IFRC GO API](https://goadmin.ifrc.org/api/v2/) | 82 | REST JSON | 接入。补红十字灾害和人道行动事件。 |
| 制裁实体 | [UN Security Council Consolidated Sanctions XML](https://scsanctions.un.org/resources/xml/en/consolidated.xml) | 88 | 官方 XML | 接入。稳定实体和更新时间，补全球制裁事件/实体图谱。 |
| 开源生态领先指标 | [GitLab REST API](https://docs.gitlab.com/api/rest/) | 88 | REST JSON | 接入 gitlab.com lane。补 GitHub 之外的 OSS/企业开源迁移信号。 |
| 包生态采用 | [npm Downloads API](https://api.npmjs.org/downloads/point/last-week/react) | 88 | REST JSON | 接入。JS 生态 adoption 指标；需标注 CI/镜像污染风险。 |
| 跨生态依赖图 | [deps.dev API](https://deps.dev/api/v3/) | 85 | REST JSON | 接入。依赖关系、包版本、跨生态 enrichment。 |
| 生物医学研究 | [Europe PMC REST](https://www.ebi.ac.uk/europepmc/webservices/rest/) | 82 | REST JSON | 接入。补 PubMed/科研趋势；只做 evidence，不给医疗建议。 |
| 学术纠错/撤稿 | [NCBI E-utilities](https://www.ncbi.nlm.nih.gov/books/NBK25501/) | 82 | REST XML/JSON | 接入 retraction/correction lane。医学/论文 claim 必查反证。 |
| 标准化进展 | [RFC Editor Index](https://www.rfc-editor.org/rfc-index.xml) / [IETF drafts](https://www.ietf.org/archive/id/) | 83 | XML / index | 接入。协议成熟度和技术方向校准；draft 不是标准。 |
| 产品发布弱信号 | [Product Hunt Atom feed](https://www.producthunt.com/feed) | 76 | Atom feed | 接入低优先级。只做 launch signal，不碰 GraphQL 403/key lane。 |
| 劳动力技能迁移 | [LMI for All API](https://api.lmiforall.org.uk/) / [O*NET database](https://www.onetcenter.org/database.html) | 84 | JSON / downloadable DB | 接入。招聘/技能迁移作为领先指标；广告偏差必须标注。 |
| 预测校准 | [Manifold Markets API](https://docs.manifold.markets/api) | 80 | REST API | 接入 calibration/watch lane。社区预测偏差大，不能当真相。 |

### Key-gated / Approved-key lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| 监管政策事件 | [Regulations.gov API](https://open.gsa.gov/api/regulationsgov/) | 84 | 需要 API key；美国域。 |
| 贸易结构 | [UN Comtrade API](https://comtradedeveloper.un.org/) | 86 | subscription key；大查询要分页/缓存。 |
| 能源领先指标 | [EIA API](https://www.eia.gov/opendata/) | 80 | key/配额；不输出投资建议。 |
| 宏观结构 | [FRED API](https://fred.stlouisfed.org/docs/api/fred/) | 76 | 通常需要 API key；适合作为 approved-key macro lane。 |
| 气候历史 | [NOAA CDO API](https://www.ncdc.noaa.gov/cdo-web/webservices/v2) | 78 | token/限流；适合离线/结构背景。 |
| 火点/野火 | [NASA FIRMS](https://firms.modaps.eosdis.nasa.gov/api/area/) | 74 | map key；高价值但不进默认无 key collector。 |
| 空气质量 | [OpenAQ API](https://docs.openaq.org/) | 76 | 多 endpoint key-gated；先登记。 |
| 气候再分析 | [Copernicus CDS API](https://cds.climate.copernicus.eu/how-to-api) | 73 | account/key + 大文件 job；只进离线 lane。 |
| 专利族 | [EPO OPS](https://www.epo.org/en/searching-for-patents/data/web-services/ops) | 77 | 注册/key；专利语义复杂。 |
| 招聘商业源 | [Adzuna Developer API](https://developer.adzuna.com/overview) | 72 | key-gated；招聘广告偏差大。 |
| 事实核查 | [Google Fact Check Tools API](https://developers.google.com/fact-check/tools/api) | 77 | API key；覆盖依赖 fact-check publisher，不是真相裁判。 |

### Offline / Watch lane

| 职能分类 | 信源 | 分数 | 主控裁决 |
| --- | --- | ---: | --- |
| 灾害结果校准 | [NOAA Storm Events CSV](https://www.ncei.noaa.gov/pub/data/swdi/stormevents/csvfiles/) | 81 | 离线接入。文件较大，适合 forecast 事后校准。 |
| 全球灾害历史 | [EM-DAT](https://public.emdat.be/) | 79 | 注册/许可；先放 approved-data lane。 |
| 网络安全事件历史 | [VERIS Community Database](https://github.com/vz-risk/VCDB) | 72 | 非实时历史数据；做 taxonomy/calibration。 |
| 开放网页历史 | [Common Crawl Index](https://index.commoncrawl.org/) | 77 | Web-scale 离线研究，不进同步 collector。 |
| 预测市场 | [Polymarket Docs](https://docs.polymarket.com/) / [Kalshi Docs](https://docs.kalshi.com/) | 76 | 合规敏感；只做公开 observation，不做投资建议。 |
| 美国灾害声明 | [OpenFEMA API](https://www.fema.gov/about/openfema/api) | 78 | 美国域；需 live endpoint 小样本确认。 |
| ReliefWeb | [ReliefWeb API](https://api.reliefweb.int/) | watch | 旧 v1 返回 410；后续必须验证 v2 endpoint，禁止硬编码旧路径。 |

## Wave 4 Subagent 并行补源与主控裁决

本轮实际执行：2 个 subagents 并行调研媒体注意力、法律采购；主控本地补地球观测/交通基础设施，因为线程上限阻止第三个 subagent 启动。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 百科动态/争议信号 | [MediaWiki RecentChanges API](https://www.mediawiki.org/wiki/API:RecentChanges) | 88 | REST JSON | 接入。监控高价值实体页编辑、新页面、回滚；编辑不是事实，只是注意力/争议信号。 |
| 百科 feed lane | [MediaWiki feedrecentchanges](https://www.mediawiki.org/wiki/API:Feedrecentchanges) | 82 | RSS/Atom | 接入懒路径。先按语言/主题小样本跑，再回查 page/revision metadata。 |
| 实时百科事件流 | [Wikimedia EventStreams](https://wikitech.wikimedia.org/wiki/Event_Platform/EventStreams) | 86 | SSE stream | 接入 watch/stream lane。需要断点、重连和背压，不替代 REST polling。 |
| 实体发现 | [MediaWiki OpenSearch](https://www.mediawiki.org/wiki/API:Opensearch) | 78 | REST JSON | 接入 enrichment。用于 query/entity discovery，不代表搜索量。 |
| 新闻叙事 | [GDELT DOC 2.0 API](https://blog.gdeltproject.org/gdelt-doc-2-0-api-debuts/) | 84 | REST JSON/CSV | 接入。补文章级新闻搜索、主题时间线；必须回源、去重、语言归一。 |
| RSS 发现 | [RSS autodiscovery](https://www.rssboard.org/rss-autodiscovery) / [Atom RFC 4287](https://www.rfc-editor.org/rfc/rfc4287) | 83 | HTML link discovery + feed fetch | 接入通用媒体 collector 的发现层；按站点 robots/限流/去重。 |
| Podcast/媒体元数据 | [Apple iTunes Search API](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/) | 81 | REST JSON | 接入。发现 podcast/news show metadata；不采节目全文。 |
| 法院/诉讼事件 | [CourtListener REST / RECAP](https://www.courtlistener.com/api/rest/v4/) | 90 | REST JSON | 接入。诉讼、判例、docket、RECAP 元数据；非政府官方，全量性有限。 |
| 欧盟公共采购 | [TED Open Data Service](https://docs.ted.europa.eu/ODS/latest/) | 89 | REST / bulk docs | 接入。EU tender/award notices；eForms schema 必须版本化。 |
| 英国公共采购 | [Find a Tender API](https://www.find-tender.service.gov.uk/apidocumentation) | 86 | REST JSON/XML | 接入。UK 高价值招标/award notice。 |
| 英国合同机会 | [Contracts Finder API](https://www.contractsfinder.service.gov.uk/apidocumentation) | 84 | REST API | 接入。补中低金额合同机会，和 Find a Tender 分层去重。 |
| 美国财政支出细粒度 | [USAspending endpoint docs](https://api.usaspending.gov/docs/endpoints) | 87 | REST JSON / download | 接入。transactions、awards、recipient、agency spending；保留来源差异。 |
| 美国企业披露细节 | [SEC submissions / companyfacts](https://www.sec.gov/search-filings/edgar-application-programming-interfaces) | 88 | data.sec.gov JSON | 接入。需合规 User-Agent、fair access、限流；不输出投资建议。 |
| 美国现行法规文本 | [eCFR API](https://www.ecfr.gov/developers/documentation/api/v1) | 85 | REST JSON/XML | 接入。补 Federal Register 之外的当前有效 CFR 文本。 |
| 制裁/PEP 聚合 | [OpenSanctions datasets](https://www.opensanctions.org/datasets/) | 86 | Bulk JSON/CSV | 接入 enrichment。非官方聚合，必须保留原始官方源 provenance。 |
| 全球法人身份 | [GLEIF LEI API](https://www.gleif.org/en/lei-data/gleif-api) | 84 | REST JSON:API | 接入实体补全。只覆盖有 LEI 的实体。 |
| 美国金融机构 | [FDIC BankFind Suite API](https://banks.data.fdic.gov/docs/) | 82 | REST JSON | 接入。银行机构、分支、失败银行、历史变更。 |
| 地球观测目录 | [NASA CMR collections API](https://cmr.earthdata.nasa.gov/search/collections.json?page_size=1) | 86 | REST JSON | 接入 discovery/enrichment。用于定位 NASA Earthdata 数据集，不直接批量下载。 |
| 遥感 STAC | [USGS Landsat STAC](https://landsatlook.usgs.gov/stac-server) | 84 | STAC JSON | 接入地球观测目录。适合遥感事件背景，不进同步大下载。 |
| 遥感 STAC | [Microsoft Planetary Computer STAC](https://planetarycomputer.microsoft.com/api/stac/v1) | 82 | STAC JSON | 接入候选。高价值目录，但非官方政府源；保留 provider provenance。 |
| 气候/环境数据目录 | [NOAA NCEI Access API](https://www.ncei.noaa.gov/access/services/search/v1/datasets) | 84 | REST JSON | 接入数据集发现层。具体 dataset 再单独 source spec。 |
| 机场运行状态 | [FAA airport status XML](https://nasstatus.faa.gov/api/airport-status-information) | 80 | XML | 接入交通事件源。美国机场状态，适合 disruption signals。 |

### Key-gated / Approved-key lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| 事实核查 | [Google Fact Check Tools API](https://developers.google.com/fact-check/tools/api/reference/rest) | 80 | API key；覆盖依赖 ClaimReview 发布者，不是真相裁判。 |
| 社交公开搜索 | [Bluesky app.bsky.feed.searchPosts](https://docs.bsky.app/docs/api/app-bsky-feed-search-posts) | 79 | 公共 API/限流/删除语义需验证；只做公开 observation。 |
| 美国采购/实体/排除 | [SAM.gov Public APIs](https://open.gsa.gov/api/) | 88 | 多 API key-gated；SAM 与 USASpending 语义不能混。 |
| 美国国会立法 | [Congress.gov API](https://api.congress.gov/) | 83 | API key；法案不等于法律，需结果校准。 |
| 美国官方出版归档 | [GovInfo API](https://api.govinfo.gov/docs/) | 84 | API key；大包下载需缓存/去重。 |
| 欧盟法律 RDF | [EU Publications Office SPARQL](https://publications.europa.eu/webapi/rdf/sparql) | 82 | SPARQL 复杂且限流；先做 enrichment/offline。 |
| 欧盟遥感/地球观测 | [Copernicus Data Space APIs](https://documentation.dataspace.copernicus.eu/APIs.html) | 80 | 官方 docs 可访问；下载/配额/身份边界需分层。 |
| 欧洲电网透明度 | [ENTSO-E Transparency API](https://transparency.entsoe.eu/content/static_content/Static%20content/web%20api/Guide.html) | 78 | API guide 返回 400/需要正确参数和 token；放 key lane。 |

### Watch / Protocol / Discovery lane

| 职能分类 | 信源 | 分数 | 主控裁决 |
| --- | --- | ---: | --- |
| 事实核查结构化数据 | [ClaimReview](https://schema.org/ClaimReview) | 74 | 作为 crawled-page enrichment schema，不作为独立 collector。 |
| 联邦社交 | [Mastodon public timelines](https://docs.joinmastodon.org/methods/timelines/) / [ActivityPub](https://www.w3.org/TR/activitypub/) | 76 | 先选少量实例；实例偏差极大，不能代表全网。 |
| 美国公共交通 | [Transit.land API](https://www.transit.land/documentation/datastore/api-endpoints.html) | 76 | 官方/社区目录可确认；GTFS feed 质量差异大，先做目录发现。 |
| GTFS 标准 | [MobilityData GTFS](https://mobilitydata.org/gtfs-schedule/) | 72 | 标准/生态入口，具体 feed 需逐城市确认。 |
| 开放能源系统 | [Open Power System Data](https://open-power-system-data.org/) | 75 | 页面可确认；更像离线结构背景源。 |
| 海洋活动 | [Global Fishing Watch APIs](https://globalfishingwatch.org/our-apis/documentation) | 74 | 文档可访问；授权/配额边界待确认。 |

## Wave 5 Subagent 并行补源与主控裁决

本轮复用 3 个已完成 subagents 并行调研：消费文化/应用采用、人口粮食教育劳动力结构、数字基础设施/互联网测量。主控保留接口可验证性、合规边界和 source function 分类。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| App 采用榜单 | [Apple RSS / App Store Charts](https://rss.applemarketingtools.com/) | 88 | JSON feed | 接入。top-free/top-paid/top-grossing/apps，按国家/类型采样；排名不是下载量。 |
| App 评价/负反馈 | [App Store Customer Reviews RSS](https://itunes.apple.com/us/rss/customerreviews/id=284882215/sortBy=mostRecent/json) | 82 | JSON/RSS | 接入 review delta。版本后差评、评分变化和痛点关键词是 adoption 反证。 |
| 游戏实时采用 | [Steam current players](https://partner.steamgames.com/doc/webapi/ISteamUserStats#GetNumberOfCurrentPlayers) | 87 | REST JSON | 接入重点 appid 在线人数时间序列；免费周末/活动需标注。 |
| 游戏口碑/需求痛点 | [Steam Store Reviews](https://partner.steamgames.com/doc/store/getreviews) | 84 | REST JSON | 接入。评论可做痛点和负反馈，但要识别 review bombing。 |
| 电视/内容元数据 | [TVmaze API](https://www.tvmaze.com/api) | 76 | REST JSON | 接入 enrichment/watch。覆盖播出节奏和节目实体，不代表观看量。 |
| 开放音乐趋势 | [ListenBrainz API](https://listenbrainz.readthedocs.io/en/latest/users/api/) | 78 | REST JSON | 接入开放音乐趋势样本；用户群偏自愿上传。 |
| 国际结构指标 | [UN SDG Global Database API](https://unstats.un.org/sdgapi/swagger/) | 90 | REST JSON | 接入。跨贫困、教育、粮食、卫生、就业、气候；低频结构背景和校准。 |
| 联合国统计总线 | [UN Data API](http://data.un.org/Host.aspx?Content=API) | 84 | API / dataset download | 接入白名单 dataset，不全量扫；老系统编码差异大。 |
| 人口结构 | [UN DESA World Population Prospects](https://population.un.org/wpp/) | 88 | Bulk CSV/XLSX | 接入离线结构背景；预测版本必须记录 revision。 |
| 粮食/农业结构 | [FAOSTAT](https://www.fao.org/faostat/en/#data) | 88 | REST/Bulk | 接入 watch+cache。API 探测出现 521，先按 domain 白名单重试并缓存。 |
| 粮价/粮食安全 | [WFP Food Prices via HDX](https://data.humdata.org/dataset/wfp-food-prices) | 86 | HDX CKAN / CSV | 接入。补 FAOSTAT 低频数据；价格不能直接推断饥荒。 |
| 人道数据目录 | [Humanitarian Data Exchange API](https://data.humdata.org/api/3/action/package_search) | 84 | CKAN JSON | 接入 discovery/enrichment。HDX 是聚合目录，必须保留 source org。 |
| 高分辨率人口 | [WorldPop](https://hub.worldpop.org/rest/data) | 87 | REST + raster downloads | 接入离线 lane。用于灾害/冲突暴露估计，不进轻量同步 collector。 |
| 劳动力结构 | [ILOSTAT bulk](https://ilostat.ilo.org/data/bulk/) | 86 | Bulk CSV / SDMX | 接入。就业、失业、工资、劳动参与、行业结构；保留版本与口径。 |
| 互联网主动测量 | [RIPE Atlas API](https://atlas.ripe.net/docs/apis/rest-api-reference/) | 90 | REST JSON | 接入。public measurements/probes 做延迟、DNS、traceroute observation。 |
| 路由/ASN 背景 | [RIPEstat Data API](https://stat.ripe.net/docs/data_api) | 88 | REST JSON | 接入。IP/ASN/prefix 背景、BGP 状态、归属补全。 |
| 云服务状态 | [AWS RSS](https://status.aws.amazon.com/rss/all.rss) / [Azure RSS](https://status.azure.com/en-us/status/feed/) / [GCP incidents JSON](https://status.cloud.google.com/incidents.json) | 87 | RSS / JSON | 接入 unified status_feed collector；厂商披露可能滞后。 |
| SaaS 状态 | [Cloudflare Status](https://www.cloudflarestatus.com/api) / [GitHub Status](https://www.githubstatus.com/api) | 84 | Statuspage JSON | 接入。components/incidents 可复用 Statuspage parser。 |
| 证书透明度目录 | [Chrome CT Log List](https://www.gstatic.com/ct/log_list/v3/log_list.json) | 79 | JSON | 接入 enrichment。它是 log list，不是证书搜索 API。 |

### Key-gated / Approved-key lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| 音乐采用/流行度 | [Spotify Web API](https://developer.spotify.com/documentation/web-api) | 82 | OAuth/key；popularity 是 Spotify 内部指标，不是播放量。 |
| 视频注意力 | [YouTube Data API](https://developers.google.com/youtube/v3) | 86 | API key/quota；地区和推荐算法影响强。 |
| 直播/游戏热度 | [Twitch Helix API](https://dev.twitch.tv/docs/api/) | 85 | OAuth app token；viewer_count 波动快。 |
| Reddit 排名/社区采用 | [Reddit Data API](https://www.reddit.com/dev/api/) | 78 | API 政策/限流敏感；不用私有登录态。 |
| 影视文化元数据 | [TMDb API](https://developer.themoviedb.org/docs) | 80 | API key；评分不是票房或观看量。 |
| 游戏元数据 | [IGDB API](https://api-docs.igdb.com/) | 79 | Twitch OAuth；偏 metadata，不是实时采用。 |
| Podcast 目录 | [Podcast Index API](https://podcastindex-org.github.io/docs-api/) | 76 | key-gated；目录去重需要处理。 |
| 国际贸易结构 | [WTO API portal](https://apiportal.wto.org/) | 84 | 可能注册/key；低频统计，不是实时贸易流。 |
| ICT / 数字鸿沟 | [ITU DataHub](https://datahub.itu.int/) | 80 | API/下载稳定性待确认；部分许可可能受限。 |
| 互联网状态 | [Cloudflare Radar](https://developers.cloudflare.com/radar/) | 86 | 可能需要 token/参数；Radar 统计不是故障裁判。 |
| Web 体验 | [Chrome UX Report API](https://developer.chrome.com/docs/crux/api/) | 78 | API key/BigQuery；只覆盖足够 Chrome 用户样本的 origin。 |

### Offline / Watch lane

| 职能分类 | 信源 | 分数 | 主控裁决 |
| --- | --- | ---: | --- |
| 游戏消费榜单 | [Steam Charts](https://store.steampowered.com/charts/) | 74 | 官方页面无稳定 JSON；低频 watch，不作为默认 collector。 |
| 图书/阅读趋势 | [Open Library APIs](https://openlibrary.org/developers/api) | 75 | 官方 API 可确认但本机超时；先 watch。 |
| Google Books | [Google Books API](https://developers.google.com/books/docs/v1/using) | watch | 本机 429；需限流/key 策略。 |
| 教育结构 | [UNESCO UIS Data Browser](https://databrowser.uis.unesco.org/) | 82 | 机器接口待确认；结构背景源。 |
| 迁移人口 | [UN DESA International Migrant Stock](https://www.un.org/development/desa/pd/content/international-migrant-stock) | 78 | 页面 403/下载路径需人工确认；低频背景。 |
| BGP live | [RIPE RIS Live](https://ris-live.ripe.net/) | 86 | WebSocket 流式源；需断点、重连、回放 fixture。 |
| BGP 历史 | [RouteViews Archive](https://archive.routeviews.org/) | 84 | MRT 大文件；离线校准 lane。 |
| ASN 拓扑 | [CAIDA ASRank](https://asrank.caida.org/) / [AS Relationships](https://www.caida.org/catalog/datasets/as-relationships/) | 84 | enrichment/offline；注意许可和缓存。 |
| 网络质量 | [M-Lab data](https://www.measurementlab.net/data/docs/) | 83 | BigQuery 成本；NDT 样本有选择偏差。 |
| DNS 测量 | [OpenINTEL](https://www.openintel.nl/data/) | 75 | 许可/访问需确认；不进实时 collector。 |
| Web 生态 | [HTTP Archive](https://httparchive.org/reports/state-of-the-web) | 77 | 月度/历史源，适合长期趋势，不是实时事件源。 |

## Wave 6 Subagent 并行补源与主控裁决

本轮按区域补全球覆盖盲点：亚太/中国、欧洲/非洲、拉美/中东。原则：区域官方源优先，目录源只做 discovery/enrichment，不把目录当事实源。

### 优先接入 / Accepted

| 区域 | 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | --- | ---: | --- | --- |
| 香港 | 统计/开放数据 | [DATA.GOV.HK CKAN](https://data.gov.hk/en-data/api/3/action/package_search?rows=1) / [C&SD API](https://www.censtatd.gov.hk/en/scode470.html) | 82 | CKAN / API | 接入。香港人口、价格、贸易、运输、地产结构变量；逐 dataset 建 schema。 |
| 台湾 | 市场/交易所 | [TWSE OpenAPI](https://openapi.twse.com.tw/) | 86 | REST JSON | 接入。台湾市场官方校准源；不输出投资建议。 |
| 日本 | 灾害/气象 | [Japan Meteorological Agency](https://www.jma.go.jp/jma/indexe.html) | 87 | JSON/HTML feeds | 接入 watch。地震、海啸、气象告警；部分 JSON 非正式文档化，需 schema watch。 |
| 新加坡 | 政府开放数据/统计 | [data.gov.sg API](https://guide.data.gov.sg/developer-guide/api-overview) / [SingStat](https://tablebuilder.singstat.gov.sg/) | 88 | REST JSON | 接入。实时环境 + GDP/CPI/人口/行业统计；小国源不外推东南亚。 |
| 澳洲 | 官方统计 | [ABS Data API](https://www.abs.gov.au/about/data-services/application-programming-interfaces-apis/data-api-user-guide) | 86 | SDMX REST/XML/JSON | 接入。人口、就业、CPI、国民经济；先少量 dataflow。 |
| EU | 开放数据目录 | [data.europa.eu SPARQL](https://data.europa.eu/sparql) | 86 | SPARQL / DCAT | 接入 discovery/enrichment。必须回链 publisher/resource。 |
| EU | 环境/气候监管 | [European Environment Agency datasets](https://www.eea.europa.eu/data-and-maps/data/) | 82 | dataset portal / CSV / geo | 接入候选。排放、空气、水、土地等欧洲结构变量。 |
| France | 国家开放数据 | [data.gouv.fr API](https://www.data.gouv.fr/api/1/datasets/) | 86 | REST JSON | 接入。法国部门数据更新监控；目录源需回到 producer。 |
| Germany | 国家开放数据 | [GovData CKAN](https://www.govdata.de/ckan/api/3/action/package_search) | 85 | CKAN JSON | 接入。德国联邦/州开放数据索引；license 差异需保留。 |
| UK | 官方统计 | [ONS API](https://api.beta.ons.gov.uk/v1/datasets) | 87 | REST JSON | 接入。英国人口、经济、劳动力、价格；保留 edition/version。 |
| UK | 法律文本 | [legislation.gov.uk developer API](https://www.legislation.gov.uk/developer) | 84 | XML/JSON/RDF | 接入 watch。法律文本和修订版本；法律解释不能自动化过度。 |
| Italy | 国家开放数据 | [dati.gov.it CKAN](https://www.dati.gov.it/opendata/api/3/action/package_search) | 80 | CKAN JSON | 接入 discovery。 |
| Spain | 国家开放数据 | [datos.gob.es API](https://datos.gob.es/apidata/catalog/dataset) | 80 | DCAT/REST JSON | 接入 discovery；多语言字段需处理。 |
| South Africa | 国家统计 | [Statistics South Africa](https://www.statssa.gov.za/) | 81 | web tables / downloads | 接入 watch/download lane。南非人口、价格、劳动力、GDP、普查。 |
| Brazil | 宏观统计 | [IBGE SIDRA / serviços](https://apisidra.ibge.gov.br/) | 90 | REST JSON | 接入。巴西结构底盘；葡语字段和表号/变量号需映射。 |
| Brazil | 宏观金融 | [Banco Central do Brasil SGS](https://dadosabertos.bcb.gov.br/) | 88 | REST JSON/CSV | 接入。利率、汇率、金融时间序列；不输出投资建议。 |
| Chile | 开放数据目录 | [datos.gob.cl CKAN](https://datos.gob.cl/api/3/action/package_search?rows=1) | 80 | CKAN JSON | 接入 discovery。 |
| Argentina | 宏观时间序列 | [Datos Argentina Series API](https://datos.gob.ar/series/api) / [INDEC APIs](https://www.indec.gob.ar/indec/web/Institucional-Indec-APIs) | 82 | REST JSON | 接入。通胀、产业、宏观指标；区分 datos.gob.ar 与 INDEC 权威性。 |
| Colombia | 开放数据目录 | [datos.gov.co](https://www.datos.gov.co/) | 80 | Socrata JSON | 接入 discovery；dataset id 需逐个验证。 |
| MENA/Conflict | 人道数据目录 | [HDX country datasets](https://data.humdata.org/api/3/action/package_search) | 84 | CKAN JSON | 接入区域 discovery。Yemen/Syria/Gaza 等人道/冲突数据必须回到原始组织评分。 |

### Approved-key / Watch lane

| 区域 | 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | --- | ---: | --- |
| 中国大陆 | 宏观统计 | [国家统计局国家数据](https://data.stats.gov.cn/) | 84 | 高价值但本机 API 403；先人工确认稳定参数，不承诺强 SLA。 |
| 中国大陆 | 贸易/海关 | [海关总署统计](http://stats.customs.gov.cn/) | 82 | 官方网页/表格；更适合离线下载。 |
| 中国大陆 | 金融/货币 | [中国人民银行统计](http://www.pbc.gov.cn/diaochatongjisi/116219/index.html) | 80 | HTML/Excel；表格结构需监控。 |
| 中国大陆 | 政策/产业 | [gov.cn 政策](https://www.gov.cn/zhengce/) / [MIIT 统计分析](https://www.miit.gov.cn/gxsj/tjfx/) | 78 | 公告文本源；需 NLP 抽取，不是结构化事实源。 |
| 中国大陆 | 气象/地震 | [中国气象数据网](https://data.cma.cn/) / [中国地震台网](https://news.ceic.ac.cn/) | 77 | CMA 多需注册；CEIC 机器接口需人工复核。 |
| 日本 | 官方统计 | [e-Stat API](https://www.e-stat.go.jp/api/) | 84 | appId/key-gated；表结构复杂。 |
| 韩国 | 官方统计 | [KOSIS OpenAPI](https://kosis.kr/openapi/) | 82 | key-gated；韩文元数据成本。 |
| 印度 | 政府开放数据 | [data.gov.in APIs](https://data.gov.in/apis) | 79 | 多 endpoint 需 API key；质量差异大。 |
| Africa | 区域发展统计 | [African Development Bank Data Portal](https://dataportal.opendataforafrica.org/) | 84 | 本机 403；API/下载方式需人工确认。 |
| Africa | 公共卫生 | [Africa CDC Download Centre](https://africacdc.org/download-centre/) | 82 | 本机 403；多为 PDF/report，非实时 collector。 |
| Nigeria | 国家统计 | [Nigeria NBS](https://www.nigerianstat.gov.ng/) | 78 | 本轮超时；站点稳定性风险。 |
| Mexico | 官方统计 | [INEGI API](https://www.inegi.org.mx/servicios/api_indicadores.html) | 85 | 通常 token；本机 timeout，key lane。 |
| Mexico | 央行金融 | [Banxico SIE API](https://www.banxico.org.mx/SieAPIRest/service/v1/) | 84 | 多请求需 token；宏观 evidence only。 |
| Latin America | 区域统计 | [CEPAL statistics](https://www.cepal.org/en/statistics) | 78 | API 路径未确认；先人工确认下载/API 契约。 |
| Latin America | 发展金融 | [IDB data](https://data.iadb.org/) | 77 | 本机 API 探测 403；watch。 |
| Israel | 官方统计/开放数据 | [data.gov.il](https://data.gov.il/api/3/action/package_search?rows=1) / [Israel CBS](https://www.cbs.gov.il/en/) | 80 | data.gov.il 可接；CBS API 需单独验证。 |
| Gulf | 区域统计 | [Saudi Open Data](https://open.data.gov.sa/) / [GASTAT](https://database.stats.gov.sa/) / [UAE data](https://uae.data.gov.ae/) / [GCC-Stat](https://www.gccstat.org/) | 75 | API 契约不明；先手工确认下载格式。 |

## Wave 7 Subagent 并行补源与主控裁决

本轮补政治制度/人权、空间天气/太空/链上、农业/水资源/能源商品。原则：评分/指数/NGO 报告只能做结构背景或反证，不当事实裁判；链上/商品/市场源不输出投资建议。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 民主制度结构 | [V-Dem Dataset](https://www.v-dem.net/data/the-v-dem-dataset/) | 91 | CSV/R/data package | 接入离线结构源。年度制度指标，必须记录版本和引用许可。 |
| 选举参与 | [International IDEA Voter Turnout Database](https://www.idea.int/data-tools/data/voter-turnout-database) | 82 | data download | 接入。投票率、登记选民、有效票；结果发布滞后。 |
| 选举日历/结果 | [IFES ElectionGuide](https://www.electionguide.org/) | 84 | structured web | 接入 watch。全球选举日历/结果入口，最终结果回各国 EMB。 |
| 政党/议会 | [ParlGov](https://www.parlgov.org/data-info/) | 83 | CSV/SQLite | 接入欧洲/OECD 政治结构背景。 |
| 政体历史 | [Center for Systemic Peace / Polity](https://www.systemicpeace.org/inscrdata.html) | 80 | Excel/CSV | 接入长期背景；口径有争议，和 V-Dem 并列而非替代。 |
| 法治指标 | [World Justice Project Rule of Law Index](https://worldjusticeproject.org/rule-of-law-index/downloads/) | 83 | CSV/Excel | 接入结构背景；专家/民调混合评分，不是事件事实。 |
| 空间天气告警 | [NOAA SWPC alerts](https://services.swpc.noaa.gov/products/alerts.json) | 91 | JSON | 接入。太阳风暴、无线电 blackout、地磁暴告警；保留原文。 |
| 空间天气指标 | [NOAA SWPC JSON services](https://services.swpc.noaa.gov/json/) | 90 | JSON | 接入 Kp、太阳风、X-ray flux 等领先指标；限频去重。 |
| 太阳活动事件 | [NASA DONKI](https://api.nasa.gov/) | 88 | REST JSON | 接入。CME、solar flare、SEP、GST 等；DEMO_KEY/限流要处理。 |
| 近地天体 | [NASA/JPL CAD API](https://ssd-api.jpl.nasa.gov/doc/cad.html) | 89 | REST JSON | 接入 NEO close approach；保留距离和不确定性。 |
| 小行星风险 | [NASA/JPL Sentry API](https://ssd-api.jpl.nasa.gov/doc/sentry.html) | 85 | REST JSON | 接入风险列表；极低概率事件不能夸大。 |
| 卫星轨道 | [CelesTrak GP](https://celestrak.org/NORAD/elements/gp.php?GROUP=active&FORMAT=json) | 88 | JSON/TLE | 接入轨道对象底盘；TLE 误差随时间增长。 |
| 地磁观测 | [USGS Geomagnetism Web Services](https://geomag.usgs.gov/ws/docs/) | 84 | REST JSON | 接入地磁台站变化，校准 SWPC 影响。 |
| Bitcoin 链上状态 | [mempool.space API](https://mempool.space/docs/api/rest) | 86 | REST JSON | 接入 Bitcoin fees/block/mempool congestion；第三方公共节点，需交叉。 |
| 官方链上制裁 | [OFAC SDN Advanced XML](https://sanctionslistservice.ofac.treas.gov/api/PublicationPreview/exports/SDN_ADVANCED.XML) | 90 | XML | 接入 crypto address sanctions truth；只说明制裁名单，不说明犯罪事实。 |
| 粮食供需 | [USDA WASDE](https://www.usda.gov/oce/commodity/wasde) / [FAS PSD](https://apps.fas.usda.gov/psdonline/app/index.html#/app/downloads) | 90 | report/download | 接入。全球作物供需、库存、产量、贸易预期；先 PSD 下载，后 WASDE 解析。 |
| 干旱事件 | [US Drought Monitor GIS Data](https://droughtmonitor.unl.edu/DmData/GISData.aspx) | 88 | GIS/CSV/shapefile | 接入农业/水资源 forecast 必要源；美国覆盖。 |
| 水文实时 | [USGS Water Services](https://waterservices.usgs.gov/) | 86 | REST JSON | 接入流量/水位等水资源事件源。 |
| 水资源结构 | [FAO AQUASTAT](https://www.fao.org/aquastat/en/databases/) | 82 | database/download | 接入结构背景；API 契约需再确认。 |
| 能源结构 | [IEA Stats API](https://api.iea.org/stats/indicators?countries=WORLD) | 82 | REST JSON | 接入能源供需/燃料结构背景；授权边界需确认。 |
| 油气校准 | [JODI Oil/Gas](https://www.jodidata.org/oil/database/data-downloads.aspx) | 84 | CSV/XLS downloads | 接入油气产量、库存、需求校准；国家报送滞后需标注。 |
| 关键矿产 | [USGS Mineral Commodity Summaries](https://www.usgs.gov/centers/national-minerals-information-center/mineral-commodity-summaries) / [MRDS](https://mrdata.usgs.gov/mrds/) | 86 | reports/database | 接入关键矿产长期结构源；年度更新，不是实时源。 |

### Approved-key / Offline / Watch lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| 政治自由 | [Freedom House datasets](https://freedomhouse.org/reports/publication-archives) | 86 | 专家评分；本机超时，需下载路径确认。 |
| 民主指标 | [IDEA GSoD](https://www.idea.int/gsod-indices/dataset-resources) | 85 | 本机 403；与 V-Dem/FH 交叉。 |
| 政党纲领 | [Manifesto Project API](https://manifesto-project.wzb.eu/information/documents/api) | 82 | 账号/key/许可；离线 approved lane。 |
| 腐败感知 | [Transparency CPI](https://www.transparency.org/en/cpi/2024) | 81 | 感知指数，年度滞后。 |
| 公民空间 | [CIVICUS Monitor](https://monitor.civicus.org/) | 78 | API/下载未确认；watch。 |
| NGO 人权报告 | [HRW RSS](https://www.hrw.org/rss/news) / [Amnesty RSS](https://www.amnesty.org/en/latest/rss/) | 76 | NGO 叙事源；避免单源定性。 |
| UN 人权声明 | [OHCHR](https://www.ohchr.org/) | 82 | 官方声明但页面防护需稳妥处理。 |
| 官方轨道目录 | [Space-Track](https://www.space-track.org/documentation) | 86 | 注册登录/再分发限制；approved-key lane。 |
| 欧洲空间天气 | [ESA Space Weather Service Network](https://swe.ssa.esa.int/) | 78 | portal-first，机器产品需确认。 |
| Minor Planet Center NEOCP | [MPC NEOCP](https://minorplanetcenter.net/iau/NEO/toconfirm_tabular.html) | 76 | HTML/table 脆；候选不等于确认对象。 |
| Ethereum Beacon | [Beaconcha.in API](https://beaconcha.in/api/v1/docs/index.html) | 78 | key-gated/第三方；不代表官方状态。 |
| Solana public RPC | [Solana RPC](https://solana.com/docs/rpc/http) | 79 | 公共 RPC 严格限流；需 fallback。 |
| 多链统计 | [Blockchair API](https://blockchair.com/api/docs) | 76 | 商业限制/非官方；敏感地址分析需谨慎。 |
| Scam reports | [Chainabuse](https://www.chainabuse.com/) | 70 | 页面 403；举报库可能误报，不当事实裁判。 |
| USDA QuickStats | [QuickStats API](https://quickstats.nass.usda.gov/api) | 86 | 通常需要 key；美国覆盖。 |
| USDA AMS Market News | [AMS Market News](https://www.ams.usda.gov/market-news) | 82 | 类别多，先 grain/livestock 小样本。 |
| FEWS NET | [FEWS NET Data Warehouse](https://fdw.fews.net/) | 84 | 当前 403；授权确认后接。 |
| NASA GRACE groundwater | [GRACE data](https://nasagrace.unl.edu/data/) | 84 | 大文件/栅格；离线 lane。 |
| JRC MARS / Agri4Cast | [MARS Data Portal](https://agri4cast.jrc.ec.europa.eu/DataPortal/Index.aspx) | 82 | 下载型，字段复杂；离线样本。 |
| Copernicus Agromet | [CDS agrometeorological indicators](https://cds.climate.copernicus.eu/datasets/sis-agrometeorological-indicators) | 79 | CDS key-gated + 大文件任务。 |
| IMF commodity prices | [IMF commodity prices](https://www.imf.org/en/Research/commodity-prices) | 78 | 本机 403；接口需确认。 |
| Freightos/Baltic shipping | [Freightos FBX](https://fbx.freightos.com/) / [Baltic Exchange](https://www.balticexchange.com/en/data-services/market-information0.html) | 72 | 多为商业授权，低频 watch。 |

## Wave 8 Subagent 并行补源与主控裁决

本轮补未来产业和社会压力：AI/算力/模型经济、创业公司与产品采用、住房/消费/信用压力。原则：价格、榜单、投诉、融资和房价都只是 proxy signal，不直接等于真实需求、投资价值或社会结论。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 模型经济/价格 | [OpenRouter Models API](https://openrouter.ai/api/v1/models) | 90 | REST JSON | 接入。模型列表、上下文长度、token pricing、provider route；只代表 OpenRouter 市场。 |
| 云/GPU 价格 | [AWS Price List API](https://pricing.us-east-1.amazonaws.com/offers/v1.0/aws/AmazonEC2/current/index.json) | 89 | JSON offer files | 接入但需过滤 region/instanceType，避免下载全量巨 JSON。 |
| 云/GPU 价格 | [Azure Retail Prices API](https://learn.microsoft.com/en-us/rest/api/cost-management/retail-prices/azure-retail-prices) | 89 | REST JSON | 接入 GPU VM/SKU retail price；不含企业折扣、spot、capacity reservation。 |
| Benchmark 标准 | [MLCommons / MLPerf](https://mlcommons.org/benchmarks/) | 88 | results files/repos | 接入。硬件/系统性能基准；厂商提交强优化，不能外推真实业务。 |
| 模型评测 | [Stanford HELM](https://crfm.stanford.edu/helm/latest/) | 84 | static results | 接入 watch。模型质量矩阵，更新频率低。 |
| AI 历史/算力趋势 | [Epoch AI data](https://epoch.ai/data) | 82 | data/download | 接入。notable models、training compute、cost、parameter trend；保留版本和引用。 |
| 创业公司目录 | [YC Company Directory](https://www.ycombinator.com/companies) | 82 | HTML/site data | 接入低频 discovery。无稳定 API，尊重 ToS。 |
| 产品发布细节 | [Product Hunt GraphQL API](https://api.producthunt.com/v2/docs) | 80 | GraphQL/OAuth | 接入 approved-key lane，补 maker/votes/topics/comments；votes 是注意力信号。 |
| 裁员事件 | [layoffs.fyi](https://layoffs.fyi/) | 76 | HTML/public tracker | 接入 watch。非官方 curated 数据，必须和 WARN/news 交叉。 |
| 官方裁员通知 | [New York WARN Notices](https://dol.ny.gov/warn-notices) | 82 | web/download | 接入 WARN 垂直切片；美国州级碎片化。 |
| 公司法律公告 | [The Gazette Data](https://www.thegazette.co.uk/data) | 85 | API/RSS/data services | 接入 UK insolvency/winding-up/legal notices；谨慎解释法律公告。 |
| 专利生命周期 | [USPTO PEDS API](https://developer.uspto.gov/api-catalog/patent-examination-data-system-api) | 84 | REST API | 接入 patent application/assignee/status，补技术/公司创新信号。 |
| 商标/品牌信号 | [USPTO Trademark Case Files API](https://developer.uspto.gov/api-catalog/trademark-case-files-dataset-api) | 84 | REST/Bulk | 接入 trademark filings/status，作为新产品/品牌弱信号。 |
| 住房底盘 | [US Census APIs](https://www.census.gov/data/developers/data-sets.html) | 90 | REST JSON | 接入 ACS/HVS/Building Permits；变量码需维护字典。 |
| 房价 | [FHFA HPI](https://www.fhfa.gov/data/hpi/datasets) | 88 | CSV/download | 接入美国房价指数；指数而非交易明细。 |
| 英国房价 | [UK Land Registry HPI](https://landregistry.data.gov.uk/app/ukhpi/download) | 87 | CSV/linked data | 接入英国房价指数。 |
| 英国房产交易 | [UK Land Registry Price Paid Data](https://landregistry.data.gov.uk/data/ppi/transaction-record.json?_pageSize=1) | 86 | Linked Data JSON | 接入离线增量。数据量大，不进同步全量采集。 |
| 家庭债务/信用 | [NY Fed Household Debt and Credit](https://www.newyorkfed.org/microeconomics/hhdc) | 84 | report/Excel/CSV | 接入季度家庭压力源。 |
| 消费信用 | [Federal Reserve G.19](https://www.federalreserve.gov/releases/g19/current/default.htm) | 83 | HTML/CSV | 接入循环信贷/消费信贷压力；宏观汇总。 |
| 驱逐纠纷 | [NYC Marshal Evictions](https://data.cityofnewyork.us/resource/6z8x-wfk4.json?$limit=1) | 78 | Socrata JSON | 接入地方样本；敏感数据聚合使用。 |

### Approved-key / Watch lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| GCP 云价 | [GCP Cloud Billing Catalog](https://cloud.google.com/billing/docs/how-to/catalog-api) | 84 | 需要 key/identity；SKU 解析复杂。 |
| LMArena / Chatbot Arena | [leaderboard](https://lmarena.ai/leaderboard) | 83 | 无稳定官方 API；人类偏好样本偏差大。 |
| Papers with Code API | [API docs](https://paperswithcode.com/api/v1/docs/) | 77 | 本机返回 HTML，需复核 API 稳定性。 |
| HF Open LLM Leaderboard dataset | [dataset API](https://huggingface.co/api/datasets/open-llm-leaderboard/results) | 80 | 具体 leaderboard lane；评测污染/榜单过时风险。 |
| WSTS / SEMI / TSMC | [WSTS](https://www.wsts.org/) / [SEMI](https://www.semi.org/en/market-data) / [TSMC monthly revenue](https://investor.tsmc.com/english/monthly-revenue) | 79 | 多为 gated/WAF；半导体供给 proxy，低频 watch。 |
| Crunchbase / Dealroom | [Crunchbase API](https://data.crunchbase.com/docs/using-the-api) / [Dealroom API](https://dealroom.co/api) | 84 | 商业授权；融资数据覆盖偏差。 |
| USAJOBS | [USAJOBS Developer](https://developer.usajobs.gov/) | 78 | API key/header；公共部门 hiring signal。 |
| WIPO / EUIPO trademarks | [WIPO Brand DB](https://branddb.wipo.int/) / [EUIPO eSearch](https://euipo.europa.eu/eSearch/) | 76 | API 不明确；先 watch。 |
| BEA API | [BEA API](https://apps.bea.gov/API/signup/) | 82 | 免费 UserID；个人收入/消费支出背景。 |
| CFPB Consumer Complaints | [CFPB API](https://www.consumerfinance.gov/data-research/consumer-complaints/search/api/v1/) | 87 | 当前 403/WAF；投诉是 allegation，不是裁决事实。 |
| HUD USPS Vacancy | [HUD USPS vacancy](https://www.huduser.gov/portal/datasets/usps.html) | 80 | 下载型；季度空置压力。 |
| OECD housing-specific SDMX | [OECD Data Explorer housing](https://data-explorer.oecd.org/vis?tm=housing&pg=0&snb=6) | 82 | SDMX 复杂；固定少量 dataflow。 |
| Consumer sentiment | [University of Michigan Surveys](https://www.sca.isr.umich.edu/) | 76 | 非政府源；完整历史/细分可能授权。 |
| Fannie Mae NHS | [National Housing Survey](https://www.fanniemae.com/research-and-insights/surveys-indices/national-housing-survey) | 75 | 当前 403；房贷情绪 proxy。 |

## Wave 9 Subagent 并行补源与主控裁决

Wave 9 补三类此前覆盖不足的未来洞察信源：生态/生物多样性，犯罪/公共安全/非法经济，公共意见/价值观/社会调查。主控 live probe 已确认 GBIF、iNaturalist、OBIS、UK Police API 可公开返回 JSON；FBI CDE 本轮旧 agencies 路径返回 Not Found，按新版文档进入复核后接入。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 生物多样性 | [GBIF Occurrence API](https://api.gbif.org/v1/occurrence/search?limit=1) | 92 | REST JSON | 接入。全球物种出现记录、dataset provenance、taxonomy；观测记录不等于真实丰度。 |
| 海洋生态 | [OBIS API](https://api.obis.org/v3/occurrence?size=1) | 88 | REST JSON | 接入。海洋生物出现记录，适合海洋生态、渔业、气候迁移信号；保留采样偏差。 |
| Citizen science | [iNaturalist API](https://api.inaturalist.org/v1/observations?per_page=1) | 83 | REST JSON | 接入 weak-signal lane。适合异常物种、城市生态、公众观察热点；不作为丰度事实。 |
| 森林变化 | [Global Forest Watch Data API](https://data-api.globalforestwatch.org/docs) | 88 | API / dataset query | 接入。森林砍伐、树冠损失、火灾、供应链生态风险；大栅格走离线。 |
| 遥感/土地变化 | [Copernicus Data Space STAC](https://catalogue.dataspace.copernicus.eu/stac/collections) | 86 | STAC API | 接入。Sentinel/Copernicus 遥感底座；同步 collector 只抓 metadata，不抓大资产。 |
| 土地覆盖 | [ESA WorldCover](https://esa-worldcover.org/en/data-access) / [STAC](https://planetarycomputer.microsoft.com/api/stac/v1/collections/esa-worldcover) | 84 | GeoTIFF / STAC | 接入离线 lane。全球 10m 土地覆盖；必须记录 product/version/class legend。 |
| 拉美土地覆盖 | [MapBiomas](https://brasil.mapbiomas.org/en/downloads/) | 82 | download / Earth Engine | 接入离线 lane。亚马逊、农业扩张、牧场、森林变化关键源；区域和版本分开。 |
| 官方犯罪统计 | [UNODC Data Portal](https://dataunodc.un.org/) | 90 | portal / download | 接入。全球 homicide、drug、criminal justice、trafficking、prison baseline；国家上报滞后和质量差异需显式标注。 |
| 城市公共安全 | [UK Police API](https://data.police.uk/docs/) | 88 | REST JSON | 接入聚合 lane。街区级公开犯罪与结果数据；默认只聚合到月/地区/类别，避免个人或街区标签化。 |
| 美国犯罪统计 | [FBI Crime Data API / CDE](https://cde.ucr.cjis.gov/LATEST/webapp/#/pages/docApi) | 86 | REST API | 接入前复核新版路径和 key。用于美国 UCR/NIBRS 长期趋势；迁移断点需记录。 |
| 欧洲犯罪统计 | [Eurostat crime datasets](https://ec.europa.eu/eurostat/api/dissemination/statistics/1.0/data/crim_off_cat?format=JSON) | 84 | Eurostat API | 接入 dataset 白名单。补欧盟犯罪、警务、法院、监狱统计。 |
| 受害调查 | [ONS Crime and Justice](https://www.ons.gov.uk/peoplepopulationandcommunity/crimeandjustice) | 82 | download / ONS dataset | 接入。Crime Survey 可反证 police-recorded crime 偏差；低频。 |
| 非法经济结构 | [GI-TOC Global Organized Crime Index](https://ocindex.net/) | 82 | index / report | 接入背景指标。用于 organized crime markets、criminal actors、resilience；指数不是事件事实。 |
| 社会价值观 | [World Values Survey](https://www.worldvaluessurvey.org/WVSContents.jsp) | 91 | offline dataset | 接入离线 lane。全球价值观、信任、宗教、政治态度长期基线；按 wave 版本化。 |
| 欧洲社会调查 | [European Social Survey](https://www.europeansocialsurvey.org/data/) | 89 | portal / API / download | 接入。高方法质量社会信任、移民、幸福感、政治态度；具体 API 路径单独固定。 |
| 欧盟民意 | [Eurobarometer](https://europa.eu/eurobarometer/screen/home) | 87 | report / dataset | 接入离线/报告 lane。欧盟政策、经济信心、战争、气候、科技态度。 |
| 非洲民意 | [Afrobarometer](https://www.afrobarometer.org/data/) | 86 | dataset download | 接入。补全球南方治理、民主、生活条件、信任基线。 |
| MENA 民意 | [Arab Barometer](https://www.arabbarometer.org/survey-data/data-downloads/) | 84 | dataset download | 接入。中东/北非政治、经济、宗教、青年态度；可能需表单/许可。 |
| 拉美民意 | [Latinobarómetro](https://www.latinobarometro.org/lat.jsp) | 83 | data / report portal | 接入离线 lane。拉美民主、经济、制度信任长期序列；机器接口弱。 |
| 美国社会态度 | [GSS / NORC](https://gss.norc.org/get-the-data) | 82 | dataset / explorer | 接入。美国价值观与制度信任长期序列；变量字典和权重必须保留。 |
| 民调专题 | [Pew Research Center Datasets](https://www.pewresearch.org/datasets/) | 82 | dataset download | 接入 watch/offline。AI、媒体、政治极化、宗教与代际态度；遵守下载条款。 |

### Approved-key / Offline / Watch lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| 保护等级 | [IUCN Red List API](https://www.iucnredlist.org/resources/api) | 88 | key-gated；保护等级极高价值，但不能绕过 token。 |
| 保护地 | [Protected Planet / WDPA API](https://api.protectedplanet.net/documentation) | 86 | token / download approval；边界数据再分发和许可需确认。 |
| 鸟类观测 | [eBird API](https://documenter.getpostman.com/view/664302/S1ENwy59) | 84 | key-gated；近实时鸟类观测强，但请求需 token，采样偏差大。 |
| 鱼类性状 | [FishBase](https://www.fishbase.se/) / [SeaLifeBase](https://www.sealifebase.ca/) | 76 | watch/offline；需确认稳定合法机器入口。 |
| 犯罪受害调查 | [BJS / NCVS](https://bjs.ojp.gov/data-collection/ncvs) | 80 | offline/download；先接公开汇总表，微数据默认不接。 |
| 政治暴力 | [ACLED API](https://developer.acleddata.com/) | 84 | key-gated；事件标签不等于刑事犯罪统计。 |
| 恐怖主义历史 | [Global Terrorism Database](https://www.start.umd.edu/gtd/) | 80 | offline/terms；适合 terrorism historical baseline。 |
| 跨国执法报告 | [Europol reports](https://www.europol.europa.eu/publications-events/main-reports) | 76 | PDF/report；适合 taxonomy/scenario，不做 event feed。 |
| 商业全球民调 | [Gallup World Poll](https://www.gallup.com/analytics/318875/global-research.aspx) | 84 | commercial/gated；只登记公开报告和元数据，不默认接原始数据。 |
| 信任报告 | [Edelman Trust Barometer](https://www.edelman.com/trust/trust-barometer) | 72 | watch；年度报告/营销材料，机器可读性弱。 |
| 商业民调 | [YouGov](https://yougov.co.uk/) / [Ipsos Global Advisor](https://www.ipsos.com/en/global-advisor) | 76 | watch/gated；公开报告可参考，原始数据/API 通常受限。 |
| 国家选举研究 | [ANES](https://electionstudies.org/) / [BES](https://www.britishelectionstudy.com/) | 78 | offline；国家级深度强，跨国可比弱，按专题接。 |

### Wave 9 风险裁决

- 生态观测源必须区分 occurrence、abundance、range、taxonomy 和 conservation status；不允许把观测热度当物种真实变化。
- 遥感/土地覆盖源必须记录 product、version、resolution、legend 和 collected_at；不同产品类别不能直接相加。
- 犯罪源只接官方聚合统计、受害调查、公开报告和名单事实；默认排除个人级执法数据、精确地址标签化、嫌疑人/受害者详情。
- Police-recorded crime、victimization survey、sanctions/watchlist、organized-crime index 是不同证据类型；不能混成同一事实。
- 民调源必须保留 wave、权重、样本、问题文本、语言版本和调查模式；民意不是事实真相，只是带抽样和措辞偏差的社会观察。
- Gallup、YouGov、Ipsos、IUCN、eBird、WDPA、ACLED 等受限源不得进入默认 collector，除非单独批准 key、许可和使用边界。

## Wave 10 Subagent 并行补源与主控裁决

Wave 10 补三类高解释力结构源：金融系统风险、贸易/供应链/制裁合规、教育/人才/技能供给。主控 live probe 已确认 IMF DataMapper、ECB Data API、SEC companyfacts、College Scorecard demo 可返回公开数据；O*NET Web Services 需要认证；US Census trade 本轮超时，暂不判死。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 全球金融系统 | [BIS Statistics](https://stats.bis.org/api-doc/v2/) | 91 | SDMX/API | 接入。跨境银行、信贷、债务、房地产、衍生品核心源；具体 dataflow 固定后再进 collector。 |
| 市场/宏观基线 | [FRED CSV](https://fred.stlouisfed.org/graph/fredgraph.csv?id=VIXCLS) | 90 | CSV / API-key lane | 接入 CSV baseline。正式 API key 用于 metadata/批量 series；不输出投资建议。 |
| 数据修订审计 | [ALFRED vintage data](https://alfred.stlouisfed.org/graph/alfredgraph.csv?id=GDP) | 89 | CSV / API-key lane | 接入 forecast 回测。保存 vintage，避免 hindsight bias。 |
| 全球宏观 | [IMF DataMapper API](https://www.imf.org/external/datamapper/api/v1/NGDP_RPCH) | 88 | REST JSON | 接入。增长、通胀、财政、外部部门背景；指标目录需白名单。 |
| 金融压力 | [OFR Financial Stress Index](https://www.financialresearch.gov/financial-stress-index/data/fsi.csv) | 87 | CSV | 接入。美国金融压力分项，适合 alert/calibration；只作压力 proxy。 |
| 欧元区金融 | [ECB Data API](https://data-api.ecb.europa.eu/service/data/EXR/D.USD.EUR.SP00.A?lastNObservations=1) | 86 | SDMX REST | 接入。欧元区汇率、利率、货币、银行与金融市场；SDMX key 复杂。 |
| 公司披露 | [SEC EDGAR submissions/companyfacts](https://data.sec.gov/api/xbrl/companyfacts/CIK0000320193.json) | 86 | JSON API | 接入。上市公司 filings、XBRL 基本面、风险披露；遵守 SEC fair access/User-Agent。 |
| 全球贸易 | [UN Comtrade](https://unstats.un.org/wiki/display/comtrade/New+Comtrade+User+Guide) | 91 | API / download | 接入 approved-key lane。全球商品流动底盘；大查询分页、缓存、HS 白名单。 |
| 制裁事实 | [OFAC SDN Advanced XML](https://sanctionslistservice.ofac.treas.gov/api/PublicationPreview/exports/SDN_ADVANCED.XML) | 90 | XML | 接入。名单事实源；只能记录某日期某名单包含某实体，不能输出违法结论。 |
| 贸易政策 | [WTO Data API](https://apiportal.wto.org/) | 88 | API portal | 接入。贸易、关税、服务贸易、政策指标；可能需 key。 |
| 港口/ chokepoint | [IMF PortWatch](https://portwatch.imf.org/pages/data) | 87 | download / portal | 接入具体港口 chokepoint collector。此前已有总源，本轮补接入职责。 |
| 贸易/关税聚合 | [WITS / World Bank Trade API](https://wits.worldbank.org/API/V1/SDMX/V21/rest/data) | 86 | SDMX REST | 接入。贸易、关税、Comtrade/TRAINS 派生指标；保留原始来源。 |
| 贸易发展 | [UNCTADstat](https://unctadstat.unctad.org/) | 84 | portal / download | 接入。贸易、航运、FDI、产业结构长期变量；低频。 |
| 欧盟制裁 | [EU Consolidated Financial Sanctions List](https://data.europa.eu/data/datasets/consolidated-list-of-persons-groups-and-entities-subject-to-eu-financial-sanctions) | 88 | dataset | 接入。EU 制裁事实；下载资源和字段版本化。 |
| 英国制裁 | [UK OFSI Consolidated List](https://www.gov.uk/government/publications/financial-sanctions-consolidated-list-of-targets) | 87 | download page | 接入。UK 制裁事实；跟踪文件链接变化。 |
| 教育结构 | [World Bank EdStats](https://api.worldbank.org/v2/) | 88 | REST JSON/XML | 接入指标白名单。全球教育入学率、完成率、教育投入。 |
| 欧洲教育/劳动力 | [Eurostat education/labor datasets](https://ec.europa.eu/eurostat/api/dissemination/statistics/1.0/data/educ_uoe_enrt01?format=JSON) | 87 | REST JSON | 接入 dataset 白名单。欧盟教育、就业、技能、人口结构。 |
| 劳动力结构 | [ILOSTAT bulk](https://ilostat.ilo.org/data/bulk/) | 86 | Bulk CSV / SDMX | 接入 skills/labor slice。职业、工资、失业、行业结构；此前已有总源。 |
| 教育系统 | [UNESCO UIS Data Browser](https://databrowser.uis.unesco.org/) | 84 | portal / download | 接入 offline lane。学生、教师、教育投入、性别差距；API/批量路径待固定。 |
| 技能 taxonomy | [O*NET Database](https://www.onetcenter.org/database.html) | 82 | Bulk DB / CSV | 接入 ontology lane。职业、技能、任务、能力字典；不是趋势事实。 |
| 欧洲技能 taxonomy | [ESCO API](https://ec.europa.eu/esco/portal/api) | 81 | REST API / RDF | 接入。职业、技能、资格标准化；需固定正确查询参数。 |
| 美国高教结果 | [College Scorecard API](https://collegescorecard.ed.gov/data/api-documentation/) | 79 | REST API / key | 接入 approved-key lane。高校成本、毕业、收入、专业；demo 可返回数据。 |
| 全球南方调查 | [DHS Program API](https://api.dhsprogram.com/) | 78 | REST JSON / survey | 接入 metadata/aggregate lane。教育、健康、人口、家庭调查；微观数据需许可。 |

### Approved-key / Offline / Watch lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| FRED / ALFRED API | [FRED API docs](https://fred.stlouisfed.org/docs/api/fred/) | 86 | key lane；CSV 可先用，API key 用于 metadata 和批量 series。 |
| 金融市场授权数据 | [Nasdaq Data Link](https://docs.data.nasdaq.com/) / [CBOE DataShop](https://datashop.cboe.com/) | 72 | paid/watch；实时、微观、期权链、订单簿默认排除。 |
| 美国贸易 | [US Census International Trade API](https://api.census.gov/data/timeseries/intltrade/) | 85 | 本轮超时；参数严格，复测后按 commodity 白名单接。 |
| 商业贸易数据 | [ITC Trade Map](https://www.trademap.org/) / Panjiva / ImportGenius | 76 | 登录/商业授权；默认不接。 |
| AIS/船舶商业数据 | MarineTraffic / VesselFinder | 70 | 商业授权和合规限制；默认排除。 |
| EU TARIC 自动化 | [EU TARIC DDS](https://ec.europa.eu/taxation_customs/dds2/taric/taric_consultation.jsp) | 76 | portal-first；确认合法稳定接口前只 watch。 |
| 高教统计 | [IPEDS / NCES](https://nces.ed.gov/ipeds/use-the-data) | 80 | offline；美国高校招生、毕业、学费、专业，官方但偏下载。 |
| OECD 教育/PISA | [OECD PISA data](https://www.oecd.org/en/about/programmes/pisa/pisa-data.html) | 78 | offline/low-frequency；大文件、低频，适合教育质量基线。 |
| 迁移数据 | [UN DESA International Migrant Stock](https://www.un.org/development/desa/pd/content/international-migrant-stock) / [IOM Migration Data Portal](https://www.migrationdataportal.org/) | 77 | offline/watch；迁移统计滞后，IOM 更像索引解释层。 |
| 儿童/家庭调查 | [UNICEF MICS](https://mics.unicef.org/) | 76 | offline/watch；微观数据需许可和伦理边界。 |
| 英国高教 | [HESA](https://www.hesa.ac.uk/data-and-analysis) | 75 | offline/watch；开放表格多，稳定 API 不明确。 |

### Wave 10 风险裁决

- 金融源只能生成 Observation/Evidence/Signal，不输出投资建议；市场微观数据、实时行情、订单簿和付费数据默认排除。
- 宏观金融数据必须保留 release date、revision/vintage、methodology；forecast 回测优先用 ALFRED/vintage。
- 贸易源必须记录 reporter、partner、flow、HS/SITC/BEC 版本、period、release date；镜像统计差异不是错误，必须作为不确定性保存。
- 制裁名单不是犯罪裁判；OpenSanctions 只能做 entity resolution/enrichment，法律事实回到 OFAC/EU/UK/UN 原始名单。
- 教育和人才源默认只接聚合统计、技能 taxonomy、学校/专业公开统计；个人级简历、学生记录、移民个案不接。
- O*NET/ESCO 是 ontology，不是供需事实；必须和 ILOSTAT、岗位、毕业、迁移等趋势源交叉。

## Wave 11 Subagent 并行补源与主控裁决

Wave 11 补三类领先信号：科研资金/项目、监管与标准管线、公共卫生监测。主控 live probe 已确认 Federal Register、NIH RePORTER、NSF Award、UKRI GtR、WHO GHO、openFDA FAERS 可返回公开数据；WHO 旧 DON RSS 404，CDC 旧 dataset id 不存在，均不硬编码。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 美国监管管线 | [Federal Register API](https://www.federalregister.gov/developers/documentation/api/v1) | 90 | REST JSON | 接入。拟议规则、最终规则、通知、总统文件；区分 draft/proposed/final。 |
| 公共咨询 | [Regulations.gov API](https://open.gsa.gov/api/regulationsgov/) | 88 | REST API / key | approved-key lane。docket、comments、supporting docs；评论量大，需分页与个人信息最小化。 |
| 欧盟法规元数据 | [EUR-Lex / Cellar SPARQL](https://publications.europa.eu/webapi/rdf/sparql) | 88 | SPARQL/RDF | 接入固定 query 模板。EU 法规、指令、官方出版物元数据。 |
| 英国政策咨询 | [GOV.UK Content API](https://www.gov.uk/api/content/search/all.json?filter_content_store_document_type=open_consultations&count=1) | 86 | REST JSON | 接入。英国公开咨询、政策文件、部门发布；参数白名单。 |
| 技术标准管线 | [IETF Datatracker API](https://datatracker.ietf.org/api/) | 87 | REST JSON | 接入。drafts、RFC 进度、WG 状态；draft 不是标准。 |
| Web 标准管线 | [W3C API](https://api.w3.org/doc) | 84 | REST JSON | 接入。specifications、groups、versions、status。 |
| 美国技术治理 | [NIST CSRC Publications](https://csrc.nist.gov/publications) | 82 | page / RSS/API 待固定 | 接入 watch。AI RMF、网络安全、密码、隐私指南。 |
| NIH 资助 | [NIH RePORTER API](https://api.reporter.nih.gov/) | 92 | REST POST JSON | 接入。生物医学、AI 医疗、公共卫生科研资金领先指标；PI 个人字段最小化。 |
| NSF 资助 | [NSF Award API](https://www.research.gov/awardapi-service/v1/awards.json) | 89 | REST JSON | 接入。基础科学、AI、量子、材料、教育早期方向；award 到成果有长滞后。 |
| EU 科研项目 | [EU CORDIS](https://cordis.europa.eu/projects) | 87 | project search / download 待固定 | 接入 offline/watch。Horizon/FP 项目、参与方、结果；项目描述常偏宣传。 |
| UK 科研项目 | [UKRI Gateway to Research API](https://gtr.ukri.org/gtr/api/projects?term=quantum) | 86 | XML/API | 接入。英国科研资金、产业合作、技术转移图谱；字段清洗。 |
| 资助-成果聚合 | [OpenAIRE Projects API](https://api.openaire.eu/search/projects?keywords=quantum&format=json) | 85 | REST XML/JSON | 接入 enrichment。连接 grant、论文、机构、成果；事实回原 funder。 |
| DOE 成果 | [DOE OSTI API](https://www.osti.gov/api/v1/records?search=quantum&rows=1) | 84 | REST JSON | 接入。能源、核、材料、AI for science 研究成果。 |
| NASA 技术项目 | [NASA TechPort API](https://techport.nasa.gov/api) | 87 | REST API | 接入。航天、机器人、材料、推进、遥感技术项目；保存项目状态/TRL。 |
| 机构归一 | [ROR API](https://api.ror.org/organizations?query=mit) | 78 | REST JSON | 接入 entity-resolution lane。连接 NIH/NSF/UKRI/OpenAIRE/CORDIS。 |
| 全球健康指标 | [WHO Global Health Observatory API](https://ghoapi.azureedge.net/api/Indicator) | 86 | OData/JSON | 接入。全球健康指标、卫生系统、疾病负担基线；维护指标目录。 |
| 美国公共卫生数据 | [CDC Open Data / Socrata](https://data.cdc.gov/api/views.json?limit=1) | 87 | Socrata JSON | 接入 dataset discovery。具体 dataset id、字段、更新频率单独锁定。 |
| 药品/器械/食品安全 | [openFDA event APIs](https://api.fda.gov/drug/event.json?limit=1) | 88 | REST JSON | 接入。FAERS/device/food events；不良事件不是因果证明。 |
| 病毒基因组 | [NCBI Virus / Datasets API](https://api.ncbi.nlm.nih.gov/datasets/v2/virus/taxon/sars-cov-2/genome?limit=1) | 84 | REST JSON | 接入。病原体演化、序列 metadata；测序采样偏差必须标注。 |
| 病原体进化 | [Nextstrain public data](https://data.nextstrain.org/ncov_open_global_all-time.json) | 82 | Public JSON | 接入。变异株传播和谱系替代弱信号；保存 build/version。 |
| 欧洲疾病监测 | [ECDC Surveillance Atlas](https://atlas.ecdc.europa.eu/public/index.aspx) | 82 | portal / bulk 待固定 | 接入 watch。欧洲传染病趋势和 outbreak context。 |

### Approved-key / Offline / Watch lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| EU 公共咨询 | [EU Have Your Say](https://ec.europa.eu/info/law/better-regulation/have-your-say/initiatives_en) | 84 | HTML/watch；机器接口需确认。 |
| AI 政策 | [OECD AI Policy Observatory](https://oecd.ai/en/dashboards/policy-initiatives) | 78 | watch；高价值但 API/稳定性需确认。 |
| 标准目录 | ISO / IEC / IEEE | 76 | 只接 metadata/watch；标准正文版权/付费，默认排除。 |
| 美国 grant opportunities | [Grants.gov S2S](https://www.grants.gov/system-to-system) | 82 | 机会不等于拨款；偏申请系统。 |
| SBIR/STTR awards | [SBIR API](https://api.www.sbir.gov/public/api/awards) | 84 | 本轮 403；确认合法调用方式后再接。 |
| NIH bulk | [NIH ExPORTER](https://reporter.nih.gov/exporter) | 86 | offline bulk；适合批量，不适合同步 collector。 |
| 商业科研库 | Dimensions / AUTM STATT | 75 | 商业/会员授权；默认不接。 |
| WHO outbreak | [WHO Disease Outbreak News](https://www.who.int/emergencies/disease-outbreak-news) | 82 | 页面可用，旧 RSS 404；新版 feed/列表需复核。 |
| 疫苗不良事件 | [VAERS public data](https://vaers.hhs.gov/data/datasets.html) | 80 | CSV/ZIP；强非因果，离线接入。 |
| 序列库 | [GISAID](https://www.gisaid.org/) | 88 | login/license；不进默认 collector。 |
| 早期疫情信号 | ProMED / HealthMap | 78 | watch/manual；机器授权不明确。 |
| Wastewater | CDC NWSS / WastewaterSCAN | 75-83 | 高价值，但具体 dataset id、归一化方法、接口稳定性需固定。 |

### Wave 11 风险裁决

- 政策草案、consultation、draft、working paper 不是最终法规；Noosphere 只记录管线事实，不输出法律意见。
- 标准正文常有版权/付费限制；默认只采 metadata、状态、编号、发布日期。
- 资助项目标题和摘要常夸大愿景；grant/award 是资金方向信号，不等于技术已实现或市场采用。
- PI、co-PI、评论者、患者等个人字段默认不建画像；公开数据也要做最小化。
- 公共卫生源只生成 Observation/Evidence/Signal，不提供医疗建议；FAERS/VAERS 不良事件不是因果证明。
- 病例定义、上报制度、检测率、基因组测序能力、水样归一化方法都会造成假趋势；必须保存 source metadata 和 collection window。

## Wave 12 Subagent 并行补源与主控裁决

Wave 12 补三类资源与权力流动信号：企业所有权/政治影响、能源电力/碳排、消费价格/零售需求。主控 live probe 已确认 OpenFEC、US Senate LDA、NESO CKAN、EPA GHGRP、Open Food Facts 可返回公开数据；EIA 需要 API key；BLS 本轮超时。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 法人实体归一 | [GLEIF LEI API](https://www.gleif.org/en/lei-data/gleif-api) | 88 | REST JSON:API | 接入。连接 SEC、采购、制裁、游说、融资数据；只覆盖有 LEI 的实体。 |
| 英国法人控制权 | [Companies House PSC API](https://developer-specs.company-information.service.gov.uk/companies-house-public-data-api/reference/persons-with-significant-control) | 87 | REST API / key | 接入 approved-key lane。公司登记、officers、重大控制人；保留 filing/effective/retrieved date。 |
| SEC 所有权披露 | [SEC EDGAR ownership forms](https://www.sec.gov/search-filings/edgar-application-programming-interfaces) | 86 | JSON / filing data | 接入 slice。13D/13G、13F、Forms 3/4/5；滞后和披露口径需标注。 |
| 美国政治资金 | [FEC / OpenFEC API](https://api.open.fec.gov/developers/) | 84 | REST API / key | 接入聚合 lane。候选人、委员会、PAC、支出；不做个人捐赠画像。 |
| 美国游说 | [US Senate LDA API](https://lda.senate.gov/api/v1/filings/?filing_year=2024&page=1) | 88 | REST JSON | 接入。游说登记、filings、clients、registrants、issues；必须带过滤参数。 |
| EU 游说 | [EU Transparency Register](https://transparency-register.europa.eu/index_en) | 82 | portal/download 待确认 | 接入 watch。利益代表登记；自报数据质量参差。 |
| 美国能源 | [EIA Open Data API](https://www.eia.gov/opendata/) | 89 | REST JSON / key | approved-key lane。能源、电力、燃料、价格、库存、发电；EIA 明确要求 API key。 |
| 英国电网 | [UK NESO Data Portal](https://api.neso.energy/api/3/action/package_search?rows=1) | 84 | CKAN JSON/API | 接入。电网需求、发电、系统运行；需挑 dataset 固定 schema。 |
| 英国碳强度 | [UK Carbon Intensity API](https://api.carbonintensity.org.uk/intensity) | 82 | REST JSON | 接入。电力碳强度、发电结构；英国范围。 |
| 欧洲电力数据 | [Open Power System Data](https://data.open-power-system-data.org/) | 82 | CSV/data packages | 接入 offline lane。欧洲电力、装机、负荷、价格、天气。 |
| 设施排放 | [EPA GHGRP / Envirofacts](https://data.epa.gov/efservice/PUB_DIM_FACILITY/ROWS/0:1/JSON) | 86 | REST JSON/download | 接入。美国设施级温室气体排放；年度/滞后。 |
| 全球排放 | [EDGAR Emissions Database](https://edgar.jrc.ec.europa.eu/dataset_ghg80) | 84 | download/dataset | 接入 offline lane。国家/部门 GHG 排放；核算口径必须保存。 |
| CO₂/能源基线 | [OWID CO₂/Energy CSV](https://raw.githubusercontent.com/owid/co2-data/master/owid-co2-data.csv) | 83 | CSV | 接入。全球 CO₂/energy baseline；二次整理源，保留 provenance。 |
| 能源资产 | [Global Energy Monitor](https://globalenergymonitor.org/projects/global-coal-plant-tracker/download-data/) | 83 | download | 接入 offline lane。电厂、煤电、油气、钢铁等资产 tracker；逐包确认许可。 |
| 美国价格 | [BLS Public Data API](https://www.bls.gov/developers/) | 90 | REST JSON / key-free limits | 接入 watch/key lane。CPI/PPI/工资等；本轮超时，官方 API 需复测。 |
| 欧洲价格 | [Eurostat HICP](https://ec.europa.eu/eurostat/api/dissemination/statistics/1.0/data/prc_hicp_midx?format=JSON) | 89 | REST JSON | 接入 prices dataset 白名单。欧盟跨国可比通胀与家庭成本压力。 |
| 英国价格 | [ONS prices datasets](https://api.beta.ons.gov.uk/v1/datasets) | 87 | REST JSON | 接入。CPIH/CPI/RPI、生活成本、消费结构；固定 edition/version。 |
| 商品价格 | [World Bank Commodity Markets](https://www.worldbank.org/en/research/commodity-markets) | 85 | Excel/CSV | 接入 offline lane。能源、食品、金属价格；月度。 |
| 食品价格 | [FAO Food Price Index / FAOSTAT CP](https://www.fao.org/faostat/en/#data/CP) | 84 | portal/API/download | 接入。食品成本、粮食安全、社会稳定背景。 |
| 商品目录 | [Open Food Facts API](https://world.openfoodfacts.org/data) | 82 | REST JSON/bulk | 接入 enrichment。食品条码、品牌、品类、营养；不是价格源。 |
| 美国零售 | [US Census Monthly Retail Trade](https://api.census.gov/data/timeseries/eits/marts.html) | 79 | REST API | 接入 watch。零售销售和行业需求；参数严格，需固定 series。 |

### Approved-key / Offline / Watch lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| 公司注册聚合 | [OpenCorporates API](https://api.opencorporates.com/documentation/API-Reference) | 80 | key/watch；只做 entity enrichment，不当事实裁判。 |
| 政治资金聚合 | [OpenSecrets API](https://www.opensecrets.org/api/) | 78 | 403/授权变化；FEC/LDA 官方源优先。 |
| 受益所有权 | FinCEN BOI / EU member BO registers | 70 | 非公开或需 legitimate interest；默认排除。 |
| 商业所有权数据 | Orbis / D&B / PitchBook | 70 | 商业授权；默认排除。 |
| 欧洲电力 | [ENTSO-E Transparency Platform](https://transparency.entsoe.eu/) | 86 | key-gated；token/最新文档确认后再接。 |
| 电力碳强度 | [Electricity Maps API](https://portal.electricitymaps.com/developer-hub/api/getting-started) | 80 | key/commercial watch；默认不接付费 plan。 |
| 电力市场微观 | Elexon BMRS / 实时电价/dispatch | 75 | 授权和市场数据边界敏感；逐项确认。 |
| 商业零售/POS | NielsenIQ / IRI / Circana / Similarweb | 72 | 商业授权；默认不接。 |
| 搜索趋势 | Google Trends | 70 | 无稳定官方公开 API；只作低信任人工参考。 |
| 电商价格 | Amazon/淘宝/京东等页面 | 65 | ToS、反爬、地域/会员/动态价格；默认排除。 |

### Wave 12 风险裁决

- 所有权、政治资金、游说、制裁、PSC、SEC 披露只说明公开登记/披露事实，不代表违法或不当影响。
- 个人捐赠、officer、PI、消费者等个人级数据只保留公开最小字段；默认不建画像。
- 电力、碳排、能源价格只能生成 Observation/Evidence/Signal，不做投资、交易或合规建议。
- 排放数据必须区分 territorial、consumption-based、facility-level、CO₂-only、GHG CO₂e、估算与核证。
- CPI/HICP/PCE/商品价格都有 release date、revision 和地域/品类口径；forecast 回测要保存 vintage。
- Open Food Facts 是商品目录和 enrichment，不是价格事实；电商价格、POS、流量和商业面板默认排除。

## Wave 13 Subagent 并行补源与主控裁决

Wave 13 补硬安全与实体工业底盘：国防/军贸/出口管制、关键矿产/工业材料、核安全/危险设施/工业事故。主控 live probe 已确认 USAspending 防务合同切片、BIS/Trade.gov CSL 页面、USGS MRDS、IAEA PRIS、US CSB 页面可达；NRC 事件页本轮超时，DSCA DNS 失败，均进 watch 复测。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 全球军费 | [SIPRI Military Expenditure Database](https://www.sipri.org/databases/milex) | 90 | download/table | 接入 offline lane。全球军费、GDP 占比、历史序列；年度/低频。 |
| 军贸结构 | [SIPRI Arms Transfers Database](https://www.sipri.org/databases/armstransfers) | 88 | database/download | 接入。常规武器转让、TIV、供应/接收国；TIV 不是金额。 |
| NATO 军费 | [NATO Defence Expenditures](https://www.nato.int/cps/en/natohq/topics_49198.htm) | 84 | report/table | 接入。成员国军费、装备支出、GDP 占比；版本化报告。 |
| 美国防务合同 | [USAspending defense slice](https://api.usaspending.gov/docs/endpoints) | 87 | REST JSON | 接入 DoD/R&D/PSC/NAICS 过滤切片；保留 action date、recipient、award type。 |
| 美国军售公告 | [DSCA Major Arms Sales](https://www.dsca.mil/press-media/major-arms-sales) | 86 | official notices | watch/低频复测。公告是 proposed sale，不等于签约/交付。 |
| 出口管制 | [BIS Entity List](https://www.bis.doc.gov/index.php/policy-guidance/lists-of-parties-of-concern/entity-list) | 88 | official page/list | 接入 watch。名单事实不是违法裁判；字段和更新时间版本化。 |
| 多名单筛查 | [Trade.gov Consolidated Screening List](https://api.trade.gov/consolidated_screening_list/v1/search?size=1) | 86 | REST API | 接入 enrichment。BIS/OFAC/DDTC 等聚合；法律事实回原 agency。 |
| 常规武器登记 | [UN Register of Conventional Arms](https://www.unroca.org/) | 82 | official register | 接入 offline/watch。自愿申报、不完整、滞后。 |
| 安全援助 | [ForeignAssistance.gov](https://foreignassistance.gov/) | 80 | portal/download | 接入。美国对外援助中安全相关账户；分类谨慎。 |
| 矿产基线 | [USGS Mineral Commodity Summaries](https://www.usgs.gov/centers/national-minerals-information-center/mineral-commodity-summaries) | 90 | annual report/tables | 接入 offline lane。关键矿产储量、产量、贸易、美国依赖。 |
| 矿床/矿点 | [USGS MRDS](https://mrdata.usgs.gov/mrds/) | 82 | database/download | 接入。矿床位置、commodity、历史资源记录；下载/API 入口需固定。 |
| 欧盟原材料 | [JRC RMIS](https://rmis.jrc.ec.europa.eu/) | 84 | portal/profiles | 接入 watch。关键原材料、供应风险、回收、贸易。 |
| 全球矿产统计 | [BGS World Mineral Statistics](https://www.bgs.ac.uk/mineralsuk/statistics/world-mineral-statistics/) | 83 | download/report | 接入 offline lane。与 USGS 交叉校准产量和贸易。 |
| 钢铁产能 | [Global Energy Monitor Steel Plant Tracker](https://globalenergymonitor.org/projects/global-steel-plant-tracker/download-data/) | 85 | download | 接入 offline lane。钢厂、产能、状态、项目；逐包确认许可。 |
| 钢铁统计 | [World Steel Association Statistics](https://worldsteel.org/steel-topics/statistics/) | 80 | table/download | 接入 watch。工业周期、基建和制造活动强指标。 |
| 铝产量 | [International Aluminium Institute](https://international-aluminium.org/statistics/primary-aluminium-production/) | 79 | statistics/download | 接入 watch。原铝产量、电力成本、工业需求信号。 |
| 工业合规 | [EPA ECHO Web Services](https://echo.epa.gov/tools/web-services) | 90 | REST/API docs | 接入小白名单。设施合规、许可、检查、违规；合规记录不是违法裁判。 |
| 有毒物质排放 | [EPA Envirofacts TRI](https://data.epa.gov/efservice/TRI_FACILITY/ROWS/0:1/JSON) | 88 | REST JSON/bulk | 接入。美国有毒物质排放设施、TRI 报告；年度/滞后。 |
| 设施实体解析 | [EPA Facility Registry Service](https://www.epa.gov/frs) | 86 | API/download | 接入 entity-resolution lane。连接 ECHO/TRI/GHGRP；地址字段最小化。 |
| 工业事故 | [US Chemical Safety Board Investigations](https://www.csb.gov/investigations/) | 85 | official reports/pages | 接入 offline/watch。重大化学/工业事故调查和事故模式。 |
| 核电设施 | [IAEA PRIS](https://pris.iaea.org/PRIS/home.aspx) | 81 | official tables/pages | 接入 watch。全球核电站、机组状态、容量、运行信息；API 未确认。 |
| 欧洲工业排放 | [EEA Industrial Emissions Portal](https://industry.eea.europa.eu/) | 81 | portal/GIS data | 接入 watch。EU 工业设施、排放、污染物；数据接口需固定。 |

### Approved-key / Offline / Watch lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| 美国合同机会 | [SAM.gov APIs](https://open.gsa.gov/api/) | 84 | key lane；opportunity 不等于 award。 |
| UN Peacekeeping data | [UN Peacekeeping data](https://peacekeeping.un.org/en/data) | 76 | 本轮 403；公开统计/报告可 watch。 |
| EU dual-use | [EU Dual-use Export Controls](https://policy.trade.ec.europa.eu/help-exporters-and-importers/exporting-dual-use-items_en) | 76 | 政策/法规文件；不自动法律判断。 |
| 关键矿产情景 | [IEA Critical Minerals Data Explorer](https://www.iea.org/data-and-statistics/data-tools/critical-minerals-data-explorer) | 83 | 当前 403；人工确认下载/API 后接。 |
| 金属价格/库存 | LME / CME / S&P / Benchmark Minerals | 70 | 商业授权或付费；默认排除。 |
| 详细核安保 | [IAEA ITDB](https://www.iaea.org/resources/databases/itdb) | 70 | 详细库可能受限；只用公开事实表。 |
| NRC 事件/ADAMS | [NRC event status](https://www.nrc.gov/reading-rm/doc-collections/event-status/event/) / [ADAMS](https://www.nrc.gov/reading-rm/adams.html) | 82 | 事件页本轮超时；按 docket/license 白名单低频接。 |
| EPA RMP | EPA RMP data | 72 | 危险化学品设施安全敏感；接入前需人工审批边界。 |
| EU eMARS | [eMARS](https://emars.jrc.ec.europa.eu/) | 74 | 访问不稳定；重大工业事故库 watch。 |
| Copernicus EMS assets | [Copernicus EMS Mapping](https://mapping.emergency.copernicus.eu/activations) | 77 | 只抓 activation metadata；遥感大资产离线处理。 |

### Wave 13 风险裁决

- 涉军源只接公开预算、合同、公告、名单、报告；不采集部署细节、行动信息、非公开采购文件或商业军情。
- 军贸公告、预算、合同、交付、实际能力是不同事件；SIPRI TIV 不是金额。
- 制裁、出口管制、合同、合规、检查、PSC/NAICS 等都是披露事实，不是违法裁判。
- 矿产 resources、reserves、mine production、refinery production、capacity 是不同概念；不得混用。
- 核、RMP、危险化学品、设施地址存在公共安全敏感性；默认最小化字段并优先聚合。
- 事故早期通报和最终调查结论分层保存；工业合规/许可/检查记录只作为 Evidence/Signal。

## Wave 14 Subagent 并行补源与主控裁决

Wave 14 补三类社会脉冲源：冲突/抗议/社会动员，旅游/跨境流动/大型活动，城市民生/311。主控 live probe 已确认 NYC 311、Chicago 311、Eurostat tourism 可直接返回 JSON，TSA 为页面型，UCDP API 本轮提示 token required，Boston CKAN 被边缘层拦截。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 冲突事件 | [UCDP GED / UCDP API](https://ucdp.uu.se/apidocs/) | 91 | API / CSV download | 接入 offline/API lane。全球冲突事件权威源；本轮 API 样例需 token，GED CSV 可先接。 |
| 高频冲突弱信号 | [GDELT conflict/protest slice](https://www.gdeltproject.org/) | 85 | Events/DOC API | 接入白名单查询。已有关联总源，本轮限定 protest/conflict/violence 主题。 |
| 社会动员历史 | [Mass Mobilization Data](https://dataverse.harvard.edu/dataverse/MMdata) | 84 | Dataverse download | 接入 offline lane。长期抗议/大规模动员 baseline；需 codebook。 |
| 非暴力/暴力运动 | [NAVCO Data Project](https://dataverse.harvard.edu/dataverse/navco) | 82 | Dataverse download | 接入 offline lane。运动级结构源，不是实时事件源。 |
| 冲突背景网格 | [PRIO-GRID](https://grid.prio.org/) | 83 | dataset/download | 接入背景源。人口、地理、资源、治理变量用于空间 join。 |
| 战争历史 | [Correlates of War](https://correlatesofwar.org/) | 81 | dataset download | 接入长期 baseline。编码体系与 UCDP/ACLED 分开。 |
| 流离失所 | [UNHCR Operational Data Portal](https://data.unhcr.org/) | 84 | portal/API/CSV | 接入 outcome source。难民、流离失所、人道响应；不是冲突发生源。 |
| 欧洲旅游 | [Eurostat Tourism API](https://ec.europa.eu/eurostat/api/dissemination/statistics/1.0/data/tour_occ_ninat?format=JSON&lang=en&time=2023&geo=EU27_2020) | 86 | REST JSON | 接入 tourism dataset 白名单。住宿、过夜、来源地；欧洲消费/流动脉冲。 |
| 美国航空流量 | [TSA Checkpoint Travel Numbers](https://www.tsa.gov/travel/passenger-volumes) | 84 | official page/table | 接入 watch。安检人数高频 proxy，不等于总航空客流。 |
| 美国交通数据 | [data.transportation.gov](https://data.transportation.gov/api/views.json?search=Airline&limit=1) | 84 | Socrata API | 接入 discovery lane。航空/机场/交通 dataset 需逐个锁定。 |
| 美国航空统计 | [BTS TranStats](https://www.transtats.bts.gov/) | 82 | database/download | 接入 offline/watch。航班、机场、承运人统计；下载接口需固定。 |
| 英国机场 | [UK CAA Airport Data](https://www.caa.co.uk/data-and-analysis/uk-aviation-market/airports/uk-airport-data/) | 80 | download/table | 接入 offline lane。旅客、货邮、航班。 |
| 欧洲航空变化 | [Eurocontrol Daily Traffic Variation](https://www.eurocontrol.int/Economics/DailyTrafficVariation-Airports.html) | 83 | HTML/data page | 接入 watch。机场/国家日度航班变化；机器下载接口需确认。 |
| 边境拥堵 | [US CBP Border Wait Times API](https://bwt.cbp.gov/api/waittimes) | 76 | REST JSON | 接入。等待时间是拥堵 proxy，不是过境人数。 |
| 311 标准 | [Open311 Standard](https://www.open311.org/) | 88 | standard docs | 接入 schema 参考。统一 service_code、status、datetime 等字段。 |
| 纽约 311 | [NYC 311 Service Requests](https://data.cityofnewyork.us/resource/erm2-nwe9.json?$limit=1) | 90 | Socrata REST JSON | 接入聚合 lane。默认聚合到 ZIP/社区/月，不保留精确住址。 |
| 芝加哥 311 | [Chicago 311 Service Requests](https://data.cityofchicago.org/resource/v6vf-nfxy.json?$limit=1) | 86 | Socrata REST JSON | 接入。与 NYC 对照，需类型映射和重复请求处理。 |
| 旧金山 311 | [SF 311 Cases](https://data.sfgov.org/resource/vw6y-z8j6.json?$limit=1) | 82 | Socrata REST JSON | 接入 watch。确认最新 dataset 后接。 |
| 多伦多 311 | [Toronto 311](https://open.toronto.ca/dataset/311-service-requests-customer-initiated/) | 80 | open data assets | 接入 watch。下载/API 资产需定位。 |
| 英国社区问题 | [FixMyStreet Open311](https://www.fixmystreet.com/open311/v2/) | 79 | Open311 API | watch/低频。当前可能限流；尊重 429。 |

### Approved-key / Offline / Watch lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| 冲突事件 | [ACLED API](https://developer.acleddata.com/) | 86 | key/授权；高价值但不进默认无 key collector。 |
| 恐怖主义 | [Global Terrorism Database](https://www.start.umd.edu/gtd/) | 78 | offline/terms；定义敏感且争议大。 |
| 人权/危机报告 | OHCHR / ICG / CrisisWatch | 75 | 报告型/403；适合背景摘要，不做实时事件源。 |
| 美国抗议 | Crowd Counting Consortium | 76 | 本轮站点不可达；找到稳定 CSV/GitHub 后再接。 |
| 全球旅游 | [UN Tourism data](https://www.unwto.org/tourism-statistics/tourism-statistics-database) | 84 | 当前 403；人工确认公开下载/API。 |
| 机场统计 | ACI / IATA / ForwardKeys / FlightAware | 70 | 商业授权或 key/paid；默认排除。 |
| 活动票务 | Ticketmaster / Eventbrite | 72 | API key/平台偏差；票务数据授权敏感。 |
| 酒店/短租 | STR / AirDNA | 70 | 商业授权；默认排除。 |
| 地方 311 | Boston / LA / SeeClickFix / Local CKAN | 72-78 | 地方碎片化；按城市白名单和 dataset id 接。 |
| OSM changesets | [OSM replication](https://planet.openstreetmap.org/replication/) | 70 | 基础设施弱信号；编辑者偏差，不与 311 混用。 |

### Wave 14 风险裁决

- 冲突、抗议、社会动员源不得输出组织、规避、现场行动建议；不抓参与者身份、社媒账号、实时聚集路径。
- UCDP、ACLED、GTD、GDELT、NAVCO、CoW 编码体系不同；actor、event type、fatalities 不可直接合并。
- 旅游与交通源只接聚合流量、官方统计和公开日历；不抓 PNR、票务订单、个人定位或登录态。
- TSA、CBP wait time、航班量、过夜数、游客数不是同一指标；必须保留 source function。
- 311 投诉量不是真实问题量；受报修习惯、数字鸿沟、语言、App 推广影响。
- 311/地方开放数据默认聚合到街区/邮编/类型/月；精确地址、投诉人信息、重复/垃圾请求必须降权或剔除。

## Wave 15 Subagent 并行补源与主控裁决

Wave 15 补三类安全与韧性信号：产品安全/召回/监管执行，灾害损失/保险风险/韧性，劳工行动/工作停摆/劳资关系。主控 live probe 已确认 NHTSA、openFDA enforcement、CPSC recalls 可直接返回 JSON；OpenFEMA/NOAA 是页面型；BLS Work Stoppages 和 USDA FSIS 本轮被边缘层拒绝；Cornell Labor Action Tracker、EU Safety Gate 页面可达。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 车辆召回 | [NHTSA Recalls API](https://api.nhtsa.gov/recalls/recallsByVehicle?make=Honda&model=Accord&modelYear=2020) | 90 | REST JSON | 接入。车辆召回、缺陷、车型风险；车型/VIN/制造商需标准化。 |
| 车辆安全图谱 | [NHTSA vehicle safety APIs](https://vpic.nhtsa.dot.gov/api/) | 85 | REST JSON | 接入 enrichment。车型、VIN、制造商、投诉、召回相关数据。 |
| 消费品召回 | [CPSC Recalls API](https://www.cpsc.gov/Recalls/CPSC-Recalls-Application-Program-Interface-API-Information) | 89 | REST JSON/XML | 接入。消费品召回、品牌/品类质量风险；文本实体抽取。 |
| FDA 执行/召回 | [openFDA Enforcement Reports](https://api.fda.gov/food/enforcement.json?limit=1) | 91 | REST JSON | 接入。食品、药品、器械 enforcement/recall；不输出医疗建议。 |
| 欧盟产品安全 | [EU Safety Gate / RAPEX](https://ec.europa.eu/safety-gate-alerts/screen/webReport) | 86 | portal/API 待确认 | 接入 watch。欧洲非食品消费品安全警报；下载/API 需确认。 |
| 欧盟食品预警 | [EU RASFF](https://webgate.ec.europa.eu/rasff-window/screen/search) | 84 | portal | 接入 watch。食品和饲料快速预警。 |
| 跨国召回聚合 | [OECD GlobalRecalls](https://globalrecalls.oecd.org/) | 80 | portal | 接入 enrichment。回链原监管机构，不作事实裁判。 |
| 金融消费者投诉 | [CFPB Consumer Complaint API](https://www.consumerfinance.gov/data-research/consumer-complaints/search/api/v1/?size=1) | 86 | REST JSON | 接入聚合 lane。投诉非事实裁判；按公司/产品/时间聚合。 |
| 灾害经济损失 | [NOAA Billion-Dollar Disasters](https://www.ncei.noaa.gov/access/billions/) | 88 | CSV/page | 接入。美国重大天气/气候灾害损失；记录 nominal/real、基准年。 |
| 风暴事件损失 | [NOAA Storm Events](https://www.ncei.noaa.gov/pub/data/swdi/stormevents/csvfiles/) | 84 | annual CSV | 接入离线 lane。事件级损失、伤亡、天气类型。 |
| 热带气旋 | [IBTrACS](https://www.ncei.noaa.gov/products/international-best-track-archive) | 83 | CSV/NetCDF | 接入。全球气旋路径和强度；大文件离线。 |
| 地震影响 | [USGS PAGER / Earthquake Feeds](https://earthquake.usgs.gov/data/pager/) | 85 | GeoJSON/API | 接入。地震快速影响和损失估算；PAGER 是估算。 |
| 全球灾害预警 | [GDACS RSS](https://www.gdacs.org/xml/rss.xml) | 82 | RSS/XML | 接入。全球灾害事件发现，不是最终损失源。 |
| FEMA 灾害响应 | [OpenFEMA](https://www.fema.gov/openfema-data-hub) | 86 | API/CSV 待复测 | watch/retry。灾害声明、公共援助、NFIP；本轮 endpoint 不稳定。 |
| 灾害风险背景 | [FEMA National Risk Index](https://hazards.fema.gov/nri/data-resources) | 82 | CSV/download | 接入 offline/watch。美国县/tract 风险、脆弱性、韧性。 |
| 全球灾害损失 | [EM-DAT Public Portal](https://public.emdat.be/) | 80 | portal/download | 接入 offline/registration。全球灾害事件、伤亡、经济损失。 |
| 美国停工 | [BLS Work Stoppages](https://www.bls.gov/wsp/) | 88 | official tables/download | watch/offline。本轮 403；美国重大工作停摆权威源。 |
| 劳工行动 | [Cornell ILR Labor Action Tracker](https://striketracker.ilr.cornell.edu/) | 87 | site/data asset 待确认 | 接入 watch。补 BLS 只记录大型停摆的缺口。 |
| 英国劳资纠纷 | [UK ONS Labour Disputes](https://www.ons.gov.uk/employmentandlabourmarket/peopleinwork/workplacedisputesandworkingconditions) | 84 | ONS pages/API | 接入 watch。工作日损失、劳资纠纷；dataset id 需锁定。 |
| 工业争议统计 | [ILOSTAT industrial disputes slice](https://ilostat.ilo.org/data/bulk/) | 83 | Bulk CSV / SDMX | 接入指标白名单。跨国 strikes/lockouts/working days lost 背景。 |
| 工会组织 | [NLRB reports & data](https://www.nlrb.gov/reports/graphs-data) | 82 | official data/download | watch。美国工会选举、petitions、案件活动。 |

### Approved-key / Offline / Watch lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| USDA 食品召回 | [USDA FSIS Recalls](https://www.fsis.usda.gov/recalls) | 78 | 本轮 403；找 RSS/CSV 后接。 |
| 加拿大/澳洲召回 | Canada Recalls / Australia Product Safety | 76-77 | 本轮 403；复测官方 API/feeds。 |
| FTC 执法 | [FTC Cases](https://www.ftc.gov/legal-library/browse/cases-proceedings) | 75 | 页面/403；低频监管执行摘要。 |
| 商业灾害损失 | Munich Re / Swiss Re / Aon / Verisk | 70 | 商业授权；默认排除。 |
| DesInventar / UNDRR | [DesInventar](https://www.desinventar.net/) | 78 | 多国质量不均；适合全球南方历史背景。 |
| ReliefWeb disaster impact | [ReliefWeb API](https://api.reliefweb.int/) | 76 | API 版本需复测；人道影响叙事。 |
| ACLED/GDELT labor slice | ACLED / GDELT | 73-74 | key/media bias；只作弱信号，不作劳工事件真相。 |
| DOL OLMS / FMCS / Eurofound | DOL / FMCS / Eurofound | 75-78 | 组织/报告敏感或接口不明；只做组织级/聚合。 |

### Wave 15 风险裁决

- 召回、投诉、enforcement、safety alert 是公开监管/企业事实，不等于最终责任、违法裁判或医疗建议。
- 消费者投诉、NHTSA/CPSC/CFPB 用户报告只作为未核实观察；默认聚合并去个人化。
- 灾害损失要区分 insured loss、economic loss、public assistance、NFIP claim、crop/property loss、nominal/real。
- 早期灾害估算、PAGER、GDACS、Copernicus 等不是最终损失；后续修订必须保留。
- 劳工行动不抓个人工人、组织者、投诉人身份；罢工、停工、抗议、请愿、纠察定义分开。
- 官方劳工统计低频但权威；媒体/NGO tracker 高频但偏差大，需交叉验证。

## Wave 16 Subagent 并行补源与主控裁决

Wave 16 补三类制度性信号：立法/议会/投票，发展援助/NGO资金/项目融资，竞争/反垄断/市场监管。主控 live probe 已确认 Congress.gov、UK Parliament Bills、World Bank Projects、ProPublica Nonprofit Explorer 可返回公开数据；IATI 新 API 端点需要 subscription key，旧/搜索端点需单独固定；OpenStates 需要 key；EU competition cases、UK CMA 是页面型。

### 优先接入 / Accepted

| 职能分类 | 信源 | 分数 | 接入形态 | 主控裁决 |
| --- | --- | ---: | --- | --- |
| 美国立法 | [Congress.gov API](https://api.congress.gov/) | 91 | REST API / key | 接入 approved-key lane。法案、修正案、成员、委员会、行动进度；版本化。 |
| 美国官方文本 | [GovInfo API](https://api.govinfo.gov/docs/) | 89 | REST API / key | 接入 approved-key/offline。公法、法案文本、CFR、Congressional Record。 |
| 行政监管 | [Federal Register legislative/regulatory slice](https://www.federalregister.gov/developers/documentation/api/v1) | 86 | REST JSON | 接入 slice。行政规章、公报、拟议规则；已有总源。 |
| 英国法案 | [UK Parliament Bills API](https://bills-api.parliament.uk/index.html) | 86 | REST JSON | 接入。bill、stage、publications；程序阶段需映射。 |
| 英国辩论 | [UK Hansard API](https://hansard-api.parliament.uk/) | 82 | REST API | 接入 watch。议题热度和政策叙事；不做个人政治画像。 |
| 英国投票 | [UK Commons Votes API](https://commonsvotes-api.parliament.uk/) | 83 | REST API | 接入。division/votes；投票解释需上下文。 |
| 美国州级立法 | [OpenStates API](https://docs.openstates.org/api-v3/) | 85 | API / key | approved-key lane。州级 bills、votes、people；州程序差异大。 |
| 欧盟立法流程 | [EU Parliament OEIL](https://oeil.secure.europarl.europa.eu/oeil/home/home.do) | 82 | portal | watch/低频。EU legislative procedures、dossiers、stages。 |
| 欧盟议会开放数据 | [European Parliament Open Data](https://data.europarl.europa.eu/) | 84 | RDF/linked data | 接入 watch。MEPs、votes、documents、procedures。 |
| 欧盟法律文本 | [EUR-Lex / Publications Office SPARQL](https://publications.europa.eu/webapi/rdf/sparql) | 88 | SPARQL/RDF | 接入固定 query。CELEX、legal acts、authority tables。 |
| 联合国文件 | [UN Digital Library](https://digitallibrary.un.org/) | 80 | library/search | watch/offline。决议、会议记录、报告；API/批量接口需确认。 |
| 援助活动 | [IATI Datastore](https://iatidatastore.iatistandard.org/search/activity?q=*:*&rows=1) | 92 | Solr-like JSON/API | 接入。援助活动、发布方、受援方、sector、资金流；新 API 401，固定可用入口。 |
| 官方援助 | [OECD CRS / ODA SDMX](https://sdmx.oecd.org/public/rest/v1/dataflow/OECD.DCD.FSD) | 88 | SDMX REST | 接入。ODA 承诺/支出、捐助国、受援国、部门；SDMX key 复杂。 |
| 开发项目 | [World Bank Projects API](https://search.worldbank.org/api/v2/projects?format=json&rows=1) | 86 | REST JSON | 接入。项目、贷款、国家、sector、状态；项目文本有宣传偏差。 |
| 美国 nonprofit | [ProPublica Nonprofit Explorer](https://projects.propublica.org/nonprofits/api/v2/search.json?q=red%20cross) | 84 | REST JSON | 接入。501(c) nonprofit、IRS 990 摘要；美国范围。 |
| IRS 990 | [IRS Form 990 downloads](https://www.irs.gov/charities-non-profits/form-990-series-downloads) | 86 | bulk XML/download | 接入 offline/watch。原始申报；当前 S3 年度索引需确认。 |
| 英国慈善 | [UK Charity Commission Register](https://register-of-charities.charitycommission.gov.uk/register/full-register-download) | 82 | register/bulk | 接入 offline。慈善组织注册、财务、状态。 |
| 人道资金 | [OCHA Financial Tracking Service](https://fts.unocha.org/) | 82 | portal/API docs | 接入 watch。appeals、donors、crises、funding flows；endpoint 按 docs 固定。 |
| 欧盟竞争案件 | [EU Competition Cases](https://competition-cases.ec.europa.eu/search) | 89 | official case search | 接入 watch。antitrust、cartel、merger、state aid；机器接口需确认。 |
| 英国竞争案件 | [UK CMA cases](https://www.gov.uk/cma-cases) | 87 | GOV.UK pages/search | 接入。竞争、并购、市场研究、消费者保护案件。 |
| 美国反垄断 | [DOJ Antitrust Division](https://www.justice.gov/atr/case-filings) | 86 | official pages/filings | watch/offline。诉讼、和解、cartel、并购挑战；本轮超时。 |
| FTC 执法 | [FTC cases / press](https://www.ftc.gov/legal-library/browse/cases-proceedings) | 85 | official pages | watch。消费者保护、反垄断、隐私、并购；本机曾 403。 |
| 澳洲竞争 | [ACCC Public Registers](https://www.accc.gov.au/public-registers) | 81 | official registers | watch。并购、授权、承诺、消费者执法；机器接口需确认。 |

### Approved-key / Offline / Watch lane

| 职能分类 | 信源 | 分数 | 边界 |
| --- | --- | ---: | --- |
| Congress/GovInfo/OpenStates | 官方 API | 85-91 | key lane；先 bills/actions/votes 小切片。 |
| LegiScan / TheyWorkForYou | third-party civic APIs | 72 | key/第三方；官方源优先。 |
| IATI 新 API | [api.iatistandard.org](https://api.iatistandard.org/datastore/activity/select?q=*:*&rows=1) | 82 | 当前 401；确认 subscription key 后再接。 |
| AidData / Open990 / USAID DEC | research/portal | 74-80 | offline/watch；接口和许可需确认。 |
| Candid / Foundation Directory | commercial | 70 | 商业授权；默认排除。 |
| Competition reports | OECD / state AG / Canada / ACCC | 72-78 | 报告/页面/碎片化；按法域白名单扩展。 |
| FTC/DOJ pages | official pages | 85-86 | 页面防护/超时；低频复测和 RSS/press route 优先。 |

### Wave 16 风险裁决

- 法案、辩论、投票、行政规章、公报、法律文本必须按 introduced/passed/enacted/effective/amended/repealed 分状态。
- 投票、发言、committee action 不等于个人动机或政策结果；不做法律意见。
- 援助 commitment、disbursement、expenditure、budget、pledge 是不同金额；币种、财政年度、现价/不变价必须保存。
- 项目文本和慈善报告常有宣传偏差与滞后；组织/项目事实需和支出、评估、审计交叉。
- 竞争/反垄断 investigation、allegation、settlement、decision、fine、appeal 是不同阶段；调查不等于违法。
- 个人捐赠者、慈善受益人、议员个人画像、消费者投诉文本默认最小化或排除。

## 接入批次

1. 第一批：Primary Event Sensors + Leading Indicators。GDELT、CISA KEV、NVD、GitHub、StackExchange、HN、npm/PyPI/Hugging Face。
2. 第二批：Structural Context + Expert Evidence。World Bank、ECB/BIS、OpenAlex、arXiv、OpenReview、Wikidata。
3. 第三批：Weak-Signal Communities + Counter-Evidence。Reddit RSS、V2EX/Nowcoder、Bluesky/Mastodon、negative reviews、issue rollback、监管处罚。
4. 第四批：Global Foresight Wave 2。World Bank、Eurostat、OWID、USGS、ClinicalTrials、openFDA、UNHCR、PortWatch、Semantic Scholar、Crossref、PatentsView、Wikidata、Open-Meteo。
5. 第五批：RSS/hotlist 泛化层。把已有 raw_news/raw_hotlists 尽量统一成 raw_items，减少重复管道。
6. 暂缓批：登录态、反爬、key-only、大文件、慢源。除非单独批准，不进入默认 backend collector。

## Noosphere 当前底盘

- 已有内置 hotlist：65 个。
- 已有 RSS：59 个。
- 已有 structured item APIs：约 297 个。
- 2026-06-24 manual world run 尝试 61 个 live sources，48 个成功产出，生成 2029 条 RawItem / Evidence。

这些数字证明 source coverage 已经很宽，但不证明 truth、opportunity validation 或 project decision。

## 操作边界

- 可以：公开 API、RSS/Atom、JSON/XML/CSV、小文件、稳定 ID、可复放 payload、source health、freshness scoring。
- 暂缓：登录态、私有 session、验证码、支付链路、绕过反爬、无授权大规模抓取、key-only API。
- 必须保留：原始 payload 摘要、source id、source_id、URL、published_at、collection window、failure reason、SourceHealth。

## 下一步

最小有效路线：

1. 建一个 P0 Source Runbook：GitHub + StackExchange + HN + Reddit/V2EX。
2. 把每个源挂到 Source Function Taxonomy，而不是只挂接口类型。
3. 做 generic RSS-to-raw_items，优先复用成熟 feed parser。
4. 给所有源加 source reliability / freshness / duplication / foresight-role score。
5. 用 cross-source evidence merge 把同一事件的多源观察合成 Observation Event Group。
6. 每日输出 Creator Daily Brief / Forecast Due Review / DecisionInbox，不让 agent 自行判定未来已被证明。

## 非声明

这份报告不证明任何 source 的内容为真，不证明产品机会有效，不授权生产采集，不授权 agent 自主批准，不构成金融、医疗或法律建议。
