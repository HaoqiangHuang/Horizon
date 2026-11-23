# Horizon 每日速递 - 2026-11-23

> 从 27 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [OpenAI 探讨困惑度与模型智能的关系](#item-tech-news-1) ⭐️ 8.0/10
2. [太子集团关联人员被指涉嫌走私英伟达芯片](#item-tech-news-2) ⭐️ 7.0/10
3. [谷歌用 Mirror Dimension 测试 Chrome AI 代理](#item-tech-news-3) ⭐️ 7.0/10

**科技博客**
1. [不确定时，以多路试探换取反馈](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [美股科技股遭血洗，亚洲股市严阵以待](#item-finance-news-1) ⭐️ 8.0/10
2. [创纪录厄尔尼诺加剧全球粮食援助压力](#item-finance-news-2) ⭐️ 8.0/10
3. [蚂蚁集团领投 Simplexity Robotics 1 亿美元融资](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenAI 探讨困惑度与模型智能的关系](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 8.0/10

OpenAI 发布《Perplexity and Intelligence》，考察语言模型的困惑度能否作为衡量智能强弱的实用代理指标，并指出模型能力增强与困惑度下降之间存在明显趋势。对模型开发者和评估者而言，这提供了一种比综合能力基准更简单的预训练评测视角。现有材料未给出完整图表、相关系数或因果检验，因此文章证明的是相关性与潜在用途，而非困惑度可以完整定义智能。

hackernews · acossta · 11月22日 17:06 · [社区讨论](https://news.ycombinator.com/item?id=50601525)

**「困惑度的含义」** 困惑度（perplexity）衡量语言模型根据已有文本预测下一个词元的平均表现，可理解为预测时的平均不确定性；分数越低，通常意味着模型对文本的预测更有把握。OpenAI 的文章以这一预训练指标讨论模型能力，因此其结论需要与“更准确地预测文本”和“具备完整智能”明确区分。

**「比较模型时需统一评测口径」** 开发者可以用同一留出评测集上的困惑度作为补充指标，追踪基础模型的预测进展；但比较时必须明确使用的是普通困惑度还是 log-perplexity，并保持词表、数据和评测协议一致。现有证据也不支持用它取代任务能力基准。

**「评论者认可简单指标但强调其边界」** 评论者将困惑度解释为模型预测下一个 token 时的平均“意外程度”：理想情况下为 1，随机均匀预测时等于词表大小；有人认为它可能比不断复杂的基准更简洁地反映智能进步。另有一名评论者转述称，微软在获准使用 OpenAI 的留出评测集后，报告 MAI-2 Base 的 log-perplexity 为 0.819，并承诺共享预训练进展；这一外部说法在当前材料中未经独立核验。

<details><summary>参考链接</summary>
<ul>
<li>Perplexity and Intelligence | OpenAI</li>
<li>How LLM perplexity scores are calculated and interpreted - Facebook</li>

</ul>
</details>

**标签**: `#language-model evaluation`, `#perplexity`, `#AI benchmarks`, `#machine intelligence`

---

<a id="item-tech-news-2"></a>
### [太子集团关联人员被指涉嫌走私英伟达芯片](https://www.ft.com/content/f3ad8a81-3890-4a8a-8853-ff0a94b08ba9?syn-25a6b1a6=1) ⭐️ 7.0/10

据 Telegram 消息转述的《金融时报》调查报道，被美国财政部称为柬埔寨太子集团“二号人物”的胡小伟，涉嫌参与将英伟达芯片运入中国；报道还指称相关网络利用空壳公司、地下融资渠道和私人飞机走私货物。贸易数据显示，马来西亚 Megaspeed 子公司在 2024 年 12 月至 2025 年 12 月间申报进口约 46 亿美元货物，部分芯片据称流入中国黑市。太子集团否认胡小伟曾为其工作，并称相关指控缺乏事实依据；目前公开内容是二手概述，具体证据及技术细节尚未披露。

telegram · zaihuapd · 11月22日 04:34

**「东南亚芯片转运通道受关注」** 英伟达先进 AI 芯片对华出口受美国出口管制约束，东南亚贸易实体因而被视为需要审查的潜在转运环节。Horizon 11 月 18 日的日报曾报道，英伟达在美国方面调查其新加坡子公司是否可能牵涉对华转运芯片期间，停止披露该子公司的销售数据；11 月 13 日的日报则称，美国商务部拟把包括马来西亚、新加坡和泰国在内的七国纳入远程用芯限制，但规则与实施时间表当时尚未公布。此次报道把关注点进一步延伸至 Megaspeed 马来西亚子公司的进口申报和太子集团关联网络，但这些背景本身不能证明相关芯片最终进入中国或交易违法。

**「芯片采购需加强溯源」** 对中国市场中的 AI 芯片采购方和算力用户而言，这起遭否认的走私指控意味着审查范围应扩展至东南亚分销商、空壳公司、最终用户和芯片实际所在地，而不能只核对发票。美国近期收紧了涉及东南亚 AI 芯片及海外算力的出口规则，而既有管制也曾推高中国部分芯片类型的价格，因此采购与部署团队应重新评估供应可得性和合规成本。报道所称约 46 亿美元是进口申报价值，并非已经查实的走私金额，相关指控仍待核实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ft.com/content/dbde7a30-548c-4f9d-a4be-7898a0c24dcf">2026-11-18 — 英伟达停止披露新加坡子公司销售数据</a></li>
<li><a href="https://www.theinformation.com/articles/commerce-department-finalizing-long-awaited-ai-remote-access-rule">2026-11-13 — 美商务部据报拟封堵中国 AI 远程用芯</a></li>
<li>The Limits of Chip Export Controls in Meeting the China Challenge - CSIS</li>
<li>US Closes AI Chip Export Loophole, Imposes New Rules On Southeast ...</li>

</ul>
</details>

**标签**: `#英伟达`, `#AI芯片`, `#出口管制`, `#芯片走私`, `#供应链风险`

---

<a id="item-tech-news-3"></a>
### [谷歌用 Mirror Dimension 测试 Chrome AI 代理](https://www.landian.news/archives/128701.html) ⭐️ 7.0/10

据蓝点网的简短二手报道，谷歌搭建了名为 Mirror Dimension 的隔离模拟互联网，用于测试 Chrome AI 代理打开网页、搜索浏览、登录、加购和完成任务等操作。测试环境包含数千个模拟网站；每名工程师单独隔离测试，团队每天运行超过 1000 个测试案例，重点防范恶意网页中的提示词注入等攻击。当前材料未提供谷歌的一手说明、具体测试方法或项目开放范围，因此尚无法确认 Mirror Dimension 是否公开，以及相关 Chrome AI 代理功能何时向用户发布。

telegram · zaihuapd · 11月23日 01:30

**「浏览器代理的提示注入风险」** Horizon 10 月 29 日的日报曾记录一种针对 LLM 代理的混淆式 JavaScript 指纹脚本：它将对抗性指令嵌入网页脚本，可诱导执行网页任务的模型绕过常规安全控制。该案例具体展示了浏览器自动化代理面临的提示注入风险，为理解此次恶意网页测试提供了威胁背景，但不能证明 Chrome 的具体防护方案或效果。

**「对 Chrome 代理测试的影响」** 对 Chrome AI 代理团队而言，Mirror Dimension 可在数千个合成站点上反复测试打开网页、搜索、登录和加购等操作，并集中植入提示词注入场景，而无需让代理在真实网站上执行这些动作；每天超过 1000 个测试用例也支持高频回归验证。外部资料将其描述为用于安全训练和评估浏览器代理的沙盒，可降低测试阶段误操作真实网站或受恶意网页影响的风险。不过现有报道没有提供攻击检出率、误报率或面向 Chrome 用户的上线时间，因此不能据此认定该防护已经部署或已被证明有效。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://nullpt.rs/fingerprinting-bioweapons">2026-10-29 — 混淆式 LLM 指纹脚本诱导危险输出</a></li>
<li>Mirror Dimension for Agents: Evaluating Browser-Use Agents ...</li>
<li>Google Mirror Dimension: Fake Web for Chrome AI Agents - explainx.ai</li>

</ul>
</details>

**标签**: `#AI代理`, `#浏览器安全`, `#提示词注入`, `#模拟互联网`, `#Chrome`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [不确定时，以多路试探换取反馈](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** 面对方向不清、无法判断何者有用的技术问题时，作者主张不要把时间耗在等待完整认识上；若“乱试”失控，也会损害职业信誉，因此关键不是蛮干，而是通过密集且可放弃的实验换取反馈，再迅速收敛。

**「方案」** 他给出的框架是：同时尝试许多不同方案，认真听取同行和现实结果的反馈，并立即放弃没有积极信号的方案；多路尝试既能接触更多真实约束、避免把希望压在单一计划上，也提高至少一个方案奏效的概率。在产品层面，作者以已退役的 GitHub Models 为例：许多功能和集成并不成功，但允许 AI 推理通过 GitHub Actions token 运行这一做法获得持续吸引力，并成为 Continuous AI 的起点；一旦找到牵引力，再集中投入。在工程层面，面对庞大、纠缠且快速变化的系统，他建议先做多项推测性改动，表现没有改善便丢弃，有改善则追查原因；AI agent 可帮助并发生成多种重构方案供比较。在组织层面，跨团队失联或团队不满时，可以尝试自动化工作、主动接管任务或提出长期计划，但必须对反馈尤其敏感，迅速撤掉无效行动，否则持续施压会把原本的怨气转向行动者。他还将过程中的不适解释为在信息不足下反复失败的心理感受；预先知道这种感觉，有助于把它视为有效探索的信号，而非必须停止的警报。

**「启示」** 作者的核心结论是：面对产品、工程和组织不确定性，保持多个尝试并行、紧盯反馈并迅速淘汰失败项，比仓促押注单一方案更有效；找到牵引力后再重注。

**标签**: `#experimentation`, `#feedback loops`, `#technical decision-making`, `#product development`, `#engineering leadership`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美股科技股遭血洗，亚洲股市严阵以待](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 8.0/10

美股 AI 科技股大跌后，中国大陆、韩国和中国台湾地区推出或推进多项交易及卖空限制，以应对亚洲市场波动风险。

telegram · zaihuapd · 11月22日 13:24

**标签**: `#美股科技股`, `#AI板块抛售`, `#亚洲股市`, `#保证金调整`, `#卖空限制`

---

<a id="item-finance-news-2"></a>
### [创纪录厄尔尼诺加剧全球粮食援助压力](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 8.0/10

据伯克利地球气候学家 Zeke Hausfather，截至 10 月，中热带太平洋升温已达 3.5℃，超过此前约 2.75℃的纪录；世界粮食计划署警告，本轮厄尔尼诺可能令额外 4900 万人到 2027 年底陷入急性粮食不安全，总人数达到 2.74 亿。报道称，全球援助资金 2025 年较 2022 年峰值下降 30%，世界粮食计划署在索马里类似旱情下可覆盖的人数也已由 1000 万降至不足 100 万。

telegram · zaihuapd · 11月22日 14:09

**「背景」** 本轮厄尔尼诺 7 月已被评估为有望成为 150 年来最强事件；世界粮食计划署 8 月警告其可能加剧粮食不安全，而全球援助资金到 2025 年已较 2022 年峰值下降 30%，压缩了救援能力。

**「粮食援助压力」** 世界粮食计划署预计，本轮厄尔尼诺将在 2027 年底前使全球急性粮食不安全人口增加 4900 万、达到 2.74 亿；全球援助资金较 2022 年峰值已下降 30%，依赖国际援助的受灾家庭和地区将更难获得足够的粮食支持。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.wired.com/story/2026-el-nino-the-strongest-in-150-years/">The 2026 El Niño Is on Track to Be the Strongest on Record</a></li>
<li><a href="https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/">How This Year’s Super El Niño Will Worsen Global ... - WIRED</a></li>
<li><a href="https://news.un.org/en/story/2026/08/1168079">Strengthening El Niño to push 49 million more people into acute hunger</a></li>
<li><a href="https://www.usnews.com/news/world/articles/2026-08-05/strong-el-nino-could-push-49-million-more-people-into-acute-hunger-un-agency-says">Strong El Niño Could Push 49 Million More People Into Acute Hunger...</a></li>

</ul>
</details>

**标签**: `#厄尔尼诺`, `#粮食安全`, `#气候风险`, `#人道主义援助`, `#全球粮食危机`

---

<a id="item-finance-news-3"></a>
### [蚂蚁集团领投 Simplexity Robotics 1 亿美元融资](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 7.0/10

据彭博报道，蚂蚁集团领投中国具身智能公司 Simplexity Robotics 的 1 亿美元 Pre-A 轮融资，使其投后估值达到 16 亿美元；公司董事长兼联合创始人王凯确认了这一消息，资金将用于争夺人形机器人市场。

telegram · zaihuapd · 11月23日 02:02

**「背景」** Simplexity Robotics 于 2025 年 7 月在杭州成立，核心团队来自理想汽车；据公司 2026 年 3 月披露，成立半年内已完成五轮融资、累计融资 20 亿元人民币，当时投后估值已超过 10 亿美元。

**「影响」** 这 1 亿美元将增加 Simplexity Robotics 的可用资金，用于其与宇树、优必选等成熟厂商争夺人形机器人市场。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race">Ant Group Bets on Simplexity to Thrive in China’s Humanoid ...</a></li>
<li><a href="https://aiweekly.co/alerts/ant-group-leads-100m-pre-a-for-simplexity-at-16b-valuation">Ant Group Leads $100M Pre-A for Simplexity at $1.6B Valuation</a></li>

</ul>
</details>

**标签**: `#具身智能`, `#融资`, `#人形机器人`, `#蚂蚁集团`

---

