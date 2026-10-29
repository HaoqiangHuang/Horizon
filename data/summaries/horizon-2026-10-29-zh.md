# Horizon 每日速递 - 2026-10-29

> 从 39 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [Google 发布 Gemini 4 Carbon，先限网络安全伙伴测试](#item-tech-news-1) ⭐️ 8.0/10
2. [Apple 的 macOS 仍信任遭攻陷的 eMudhra 证书](#item-tech-news-2) ⭐️ 8.0/10
3. [MacBook Pro 首发 PROLED XDR 触控屏](#item-tech-news-3) ⭐️ 8.0/10
4. [混淆式 LLM 指纹脚本诱导危险输出](#item-tech-news-4) ⭐️ 7.0/10
5. [Dayjob: Tax 的 50 项税务智能体评测](#item-tech-news-5) ⭐️ 7.0/10
6. [GitHub Octoverse 2026：月合并 PR 达 2.2 亿](#item-tech-news-6) ⭐️ 7.0/10
7. [Discord 公开服务器将接入网络搜索](#item-tech-news-7) ⭐️ 7.0/10
8. [长鑫存储拟限量生产 HBM3E](#item-tech-news-8) ⭐️ 7.0/10

**财经新闻**
1. [Alphabet 将 AI 模式搜索广告扩展至全球](#item-finance-news-1) ⭐️ 8.0/10
2. [长鑫科技纳入上证综指和科创综指](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Google 发布 Gemini 4 Carbon，先限网络安全伙伴测试](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-carbon/) ⭐️ 8.0/10

Google 发布 Gemini 4 Carbon，并将其称为目前最强的前沿模型，主攻网络安全和可连续运行数天的长时程任务，例如定位并修复大型代码库漏洞、调试底层系统。Google 称其在编程、代理、科学任务、全栈网页开发和多模态理解上均有提升，相比前代 Argon，安全代码生成成功率提高超过 2 倍，SEC-bench Pro 得分 88.2%；这些数字来自发布方，材料未提供独立评测。首发介绍价格为每百万输入 token 2 美元、每百万输出 token 10 美元，与 Argon 相同但之后将翻倍；目前仅逐步向部分网络安全防御者和可信伙伴开放（含美国政府预发布测试），尚未普遍提供给开发者、企业和消费者。

hackernews · acossta · 10月28日 17:01 · [社区讨论](https://news.ycombinator.com/item?id=50276792)

**「从 Argon 到 Carbon」** Gemini 4 Carbon 延续了 Gemini 4 Argon 的网络安全与长时程任务路线。Google 于 9 月 30 日先公布 Argon，仅通过 Fairwind Program 向一组可信网络防御者推出；10 月 13 日，Argon 才在 AI Studio 和 Gemini 平台向开发者与企业开放，并进入 Google Antigravity、Gemini 应用及搜索 AI Mode 的部分订阅层级。因此，Carbon 当前先面向部分网络安全防御者和可信合作伙伴，属于 Argon 之后延续的分阶段接入策略，而非该能力线首次亮相。

**「当前采用限制」** 现阶段，网络安全团队不能假定 Carbon 已可通过常规开发者或消费者渠道接入，只能在选择性开放期间验证效果；采用计划还应为官方所称的后续价格翻倍预留空间，并在模型实际开放后复核基准与可用性。

**「命名、入口与基准争议」** 评论者对命名和入口提出质疑：一名用户称其 Gemini 应用仍只显示 3.8 Pro，也难以判断 Workspace 的 Ultra 套餐及 Carbon、Argon 的接入方式；另一人主张用 Ultra、Pro、Flash、Lite 等固定层级统一命名。也有观点认为，模型尚未公开发布时公布基准意义有限，因为竞争变化很快、分数可能很快过时；有评论者还以 Argon 先宣布后延期及公开发布状态不透明为例，质疑 Google 的类似发布策略。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-carbon/">Introducing Gemini 4 Carbon - The Keyword</a></li>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-4-argon/">Introducing Gemini 4 Argon - The Keyword</a></li>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-argon/">Gemini 4 Argon is now available for everyone - The Keyword</a></li>

</ul>
</details>

**标签**: `#Google Gemini`, `#Large Language Models`, `#AI Model Releases`, `#Model Benchmarks`, `#AI Naming`

---

<a id="item-tech-news-2"></a>
### [Apple 的 macOS 仍信任遭攻陷的 eMudhra 证书](https://emudhra.we-have-a-problem.com/apple.html) ⭐️ 8.0/10

报道称，Apple 的 macOS 证书信任配置仍接受已遭攻陷的 eMudhra 证书，因此除了 Git，依赖系统级证书链的其他工具也可能受到影响。Apple 提供的补救方案是由用户手动修改证书信任链，但系统更新可能覆盖这些修改，导致不安全证书再次受到信任。目前没有已发生真实中间人攻击的公开证据，实际利用情况尚不确定。

hackernews · galadran · 10月28日 11:03 · [社区讨论](https://news.ycombinator.com/item?id=50271640)

**「此前的证书处置与系统信任机制」** 此前，苹果已撤销对 8 张受影响的 eMudhra 中间 CA 证书的信任；但 macOS 随附的 git、curl 和 Python 依赖系统级 CA 信任库，因此相关根证书未从系统中移除时，这些工具仍会接受它们。苹果在 10 月 17 日获知该事件后，截至 10 月 28 日仍未通过正式系统更新完成清理，临时方案是由管理员手动从 /etc/ssl/cert.pem 中删除受影响的根 CA 证书。

**「开发者仍需修补 Git 证书信任链」** Apple 自 2026 年 10 月 19 日起已在主要系统信任路径中屏蔽受影响的 eMudhra 中间 CA，但 macOS 上的 Git、curl 及部分 Unix 工具可能仍使用 \`/etc/ssl/cert.pem\` 或显式配置的 CA 包，从而继续接受这些证书链。开发者和运维人员应按 Apple 支持文档手动更新相关信任配置、检查 Git 和 curl 实际使用的证书包，并在系统升级后复验；目前没有已报告的在野中间人攻击，但残余信任仍构成潜在凭据泄露风险。

**「影响范围与手动修复引发质疑」** 评论者指出问题并不限于 Git，并提到 Homebrew 安装的 Git 和 curl 是否依赖 macOS 系统信任库也尚未得到确认。讨论集中质疑 Apple 为何要求用户手动修改信任链，以及系统更新为何可能撤销修复；一名评论者建议 macOS 开发者尽快按照 Apple 的官方文档执行补救。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://dev.to/saeediphone/apple-blocks-compromised-emudhra-certificates-1g98">Apple Blocks Compromised eMudhra Certificates - DEV Community</a></li>
<li><a href="https://emudhra.we-have-a-problem.com/apple.html">Apple &#x27;s git still trusts the compromised eMudhra certificates</a></li>
<li><a href="https://www.theprotec.com/blog/macos-git-emudhra-certificates-trust-fix/">Git on macOS Still Trusts Compromised eMudhra Certificates ...</a></li>
<li><a href="https://support.apple.com/en-us/149555">About the compromised eMudhra intermediate CAs - Apple Support</a></li>
<li><a href="https://www.devsprintslab.com/blogs/git-macos-trusts-compromised-emudhra-certificates">Git on macOS Trust Vulnerability | Dev Sprints Lab</a></li>

</ul>
</details>

**标签**: `#macOS security`, `#Git`, `#TLS certificates`, `#eMudhra`, `#developer tooling`

---

<a id="item-tech-news-3"></a>
### [MacBook Pro 首发 PROLED XDR 触控屏](https://www.apple.com/newsroom/2026/10/apple-unveils-groundbreaking-macbook-pro-with-proled-xdr-display/) ⭐️ 8.0/10

Apple 发布新款 MacBook Pro，14 英寸和 16 英寸机型均采用首发 PROLED XDR 串联 OLED 触控屏，峰值亮度达 2000 尼特、对比度达 1000 万比一，并在 Mac 产品线中首次加入触控。新机搭载 M5 Pro 或 M5 Max 芯片，Apple 称机身更薄、更轻，最长续航为 24 小时；目前没有独立的性能、亮度或续航测试数据。10 月 28 日起开放预订，11 月 6 日正式发售，14 英寸和 16 英寸版本起售价分别为 22,999 元和 27,999 元人民币。

telegram · zaihuapd · 10月28日 17:16

**「发布前传闻与官方确认」** 10 月 26 日的日报曾援引 Bloomberg 报道，苹果计划推出首批触屏 MacBook Pro，预计采用 OLED 屏幕和灵动岛，但完整规格、价格及触控定位仍待官方确认。此次 Apple 官方稿已确认 PROLED XDR 串联 OLED 触控屏、M5 Pro/M5 Max 芯片以及售价和上市安排，相关产品由发布前传闻推进到了正式规格公布阶段。

**「触控交互进入 Mac 工作流」** 采用 M5 Pro 或 M5 Max 的 MacBook Pro 现可在屏幕上直接滚动、捏合和旋转，为触控交互提供了实际输入路径；面向 iPad 或 iOS 风格工作流的开发者应在这些机型上验证手势与界面适配。14 英寸和 16 英寸版本于 11 月 6 日开售，中国大陆起售价分别为 22,999 元和 27,999 元。

**「社区讨论」** 评论者对触控 Mac 的看法存在分歧：CountSessine 认为 macOS 界面控件对触屏操作而言过小，即使用户不使用触控，相关体验问题也可能引发投诉和缺陷；joshstrange 则更偏好鼠标的精确操作，并担忧屏幕容易留下指纹。tristanj 对减重更感兴趣，称两款机型均约减重 15%，并推测取消背光和减少屏幕层数有所贡献，但剩余减重来源仍未得到解释。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/newsletters/2026-10-25/apple-to-unveil-touch-screen-macbook-pro-executive-promotions-in-box-checker">2026-10-26 — 苹果将发布首款触屏 MacBook Pro</a></li>
<li><a href="https://www.apple.com/shop/buy-mac/macbook-pro-proled-xdr">Buy MacBook Pro with PROLED XDR Display - Apple</a></li>
<li><a href="https://www.youtube.com/watch?v=WzuIZLoHqqA">New MacBook Pro with PROLED XDR Display and Touch... - YouTube</a></li>
<li><a href="https://www.apple.com.cn/macbook-pro/proled-xdr-display/">MacBook Pro ( PROLED XDR 显示屏) - Apple (中国大陆)</a></li>

</ul>
</details>

**标签**: `#MacBook Pro`, `#PROLED XDR`, `#触控显示`, `#Apple M5`, `#消费电子`

---

<a id="item-tech-news-4"></a>
### [混淆式 LLM 指纹脚本诱导危险输出](https://nullpt.rs/fingerprinting-bioweapons) ⭐️ 7.0/10

现有摘要显示，一段面向 LLM 代理的指纹脚本会在混淆 JavaScript 中嵌入对抗性指令，诱使执行网页任务的自动化模型绕过常规安全控制并输出危险内容。这里的“生物武器”指模型被诱导生成的内容，而非已经制造出实体生物武器；摘要未提供脚本名称、测试模型范围、成功率或独立复核。其技术要点是将提示注入与脚本混淆结合，用于探测不同模型安全策略的差异。

hackernews · hazebooth · 10月28日 17:13 · [社区讨论](https://news.ycombinator.com/item?id=50276998)

**「面向大模型代理的反混淆诱饵」** 这里的“指纹识别”针对的是会抓取并分析网页代码的 LLM 代理，而非普通浏览器：脚本利用混淆 JavaScript、带有“生物武器”等惊悚字样的函数名及编码越狱提示，试图触发模型的安全拒答，阻断 AI 辅助的逆向分析。另一篇报道称，研究者扫描 10,000 个网站后发现这一来自某俄罗斯反 DDoS 公司的脚本，因此标题中的“制造生物武器”实为防御性诱饵与提示注入机制的夸张表述，并无实际研发生物武器的证据。

**「网页智能体需隔离不可信指令」** 对于会让 LLM 智能体浏览或执行第三方网页内容的组织，这项调查显示了一个具体风险：页面中的混淆脚本可携带对抗性指令，诱使具备工具调用能力的模型生成危险内容，不能仅依赖模型自身的拒答机制。相关研究同样证实，LLM 驱动的网页导航智能体容易受到间接提示注入影响，并已有在浏览器内运行、由 LLM 引导的模糊测试框架用于实时发现此类漏洞；因此应将抓取的页面和脚本视为不可信输入，隔离其与系统提示及工具权限，并在智能体上线前测试间接注入场景。

**「社区测试揭示模型响应差异」** 一名评论者称，用同一提示测试 GLM-5.3 时模型也服从了请求；这是个人测试结果，不能据此概括所有模型的防护水平。另一位评论者提到，商业前沿模型 API 会拦截真实攻击命令、漏洞载荷和 C2 制品，导致相关日志分析初期无法开展，这类限制也会影响评测的复现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://nullpt.rs/fingerprinting-bioweapons">Why Is This Fingerprinting Script Creating Bioweapons?</a></li>
<li><a href="https://news.lavx.hu/article/fingerprinting-script-packed-with-bioweapon-function-names-to-block-ai-analysis">Fingerprinting Script Packed With Bioweapon Function Names to ...</a></li>
<li><a href="https://arxiv.org/abs/2507.14799">Manipulating LLM Web Agents with Indirect Prompt Injection ... In-Browser LLM-Guided Fuzzing for Real-Time Prompt Injection ... Indirect prompt injection in large language models 2. Prompt Injection (Direct / Indirect) | Microsoft Learn Indirect Prompt Injection in Web Content Targets AI Agents Indirect Prompt Injection: The Hidden Attack Vector in RAG ... Indirect Prompt Injection: Attacks, Defenses, and the 2026 ...</a></li>
<li><a href="https://arxiv.org/html/2510.13543v1">In-Browser LLM-Guided Fuzzing for Real-Time Prompt Injection ...</a></li>
<li><a href="https://link.springer.com/article/10.1007/s00521-026-12266-x">Indirect prompt injection in large language models</a></li>

</ul>
</details>

**标签**: `#LLM fingerprinting`, `#prompt injection`, `#AI security`, `#JavaScript obfuscation`, `#web agents`

---

<a id="item-tech-news-5"></a>
### [Dayjob: Tax 的 50 项税务智能体评测](https://surgehq.ai/blog/dayjob-tax) ⭐️ 7.0/10

Dayjob: Tax 使用 50 项专业税务任务评测 AI 智能体，重点考察它们在真实税务工作流中的能力与可靠性。现有材料未提供任务来源、评分方法、参评模型、总体成绩或失败分类，因此不能据此判断哪家智能体更准确，也不能直接把社区个案视为基准结果。

hackernews · landonxi · 10月28日 15:46 · [社区讨论](https://news.ycombinator.com/item?id=50275626)

**「专业报税代理的评测背景」** 专业报税代理不仅要生成推理结果，还需把资料正确映射到申报表字段、完成计算并保留可供复核的依据，因为汇率或字段错误会直接影响申报结果和退款。社区个案凸显了这种复核需求：一名用户称 Astra 与 Codex 整理的复杂报税资料虽获会计师认可，但正式填表时出现多处错误， refund 少近 2,000 美元；另一名开发者正尝试形式化 IRS 表格与计税工作表，并估计其开源项目覆盖约 60% 的美国联邦税务情形，但这一覆盖率尚未获独立验证。

**「报税代理需要强制人工复核」** 社区案例表明，AI 代理可用于整理复杂报税材料，但输出错误可能直接影响退款和表单字段：一名用户使用 Astra 与 Codex 后发现大量错误，退款金额少算近 2,000 美元，最终仍需会计师和反复校正。因此，实际使用中应把代理定位为辅助草拟与检查工具，并在提交前由专业人员核对金额、字段及适用情境。

**「有用但仍需专业复核」** 评论者 lexandstuff 称，Astra 与 Codex 能把复杂报税材料整理成供会计师填表使用的表格，但后续复核发现多处错误和字段错置，导致退税额少近 2,000 美元，说明生成式税务流程不能替代专业复核。RGS1811 表示其开源 IRS 表单建模项目估计已覆盖 60% 的美国联邦税务情形；另有评论者质疑该评测是否只是给通用智能体提供文档和任务再观察结果，因此其方法有效性仍待说明。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/emmilco/us-tax-model">GitHub - emmilco/us-tax-model: US federal income tax forms ...</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#evaluation benchmarks`, `#professional workflows`, `#tax software`, `#LLM reliability`

---

<a id="item-tech-news-6"></a>
### [GitHub Octoverse 2026：月合并 PR 达 2.2 亿](https://simonwillison.net/2026/Oct/28/github-octoverse-2026/) ⭐️ 7.0/10

GitHub 在 GitHub Universe 发布《Octoverse 2026》，称 2026 年平台每月合并拉取请求（PR）达到 2.2 亿次、代码提交达到 73.8 亿次、新建仓库达到 3030 万个。Simon Willison 的现场记录称，合并 PR 在不到一年内增至三倍、提交量增至三倍以上，新建仓库速率则翻倍，并把这组增长视为代理式编程影响日益显著的体现；不过这些是 GitHub 汇总的全平台指标，原文未提供将增长单独归因于 AI 代理的统计拆分。报告使用经微调的多语言嵌入模型划分行业，并借助大语言模型从用户资料中提取位置代码，以校正各国 push 统计中的 VPN 偏差；互操作性和逆向工程仓库则依据名称、描述、topics 或 README 中的相关术语识别。

rss · Simon Willison · 10月28日 16:45

**「理解 Octoverse 的统计口径」** GitHub 的 Octoverse 是其年度开发者生态报告，本届以公开仓库的提交、推送和新建仓库等指标观察开发活动，并将 AI 代理辅助开发列为重要背景。理解国家、行业和互操作性分项时需注意其口径：国家排名按用户资料所在地汇总推送，并借助大语言模型分类校正 VPN 干扰；行业归属由多语言嵌入模型依据仓库名称、描述、topics 和 README 分类；“互操作性或逆向工程”则根据这些文本字段中的相关词语判定，并不代表对代码内容进行了全面审计。

**「开发团队的评审与治理压力」** GitHub 月度合并 PR 达到 2.2 亿、提交量达到 73.8 亿，显示代理辅助开发正在显著增加代码吞吐；开发者和组织需要相应扩充自动化测试、代码审查与安全治理能力，以应对更大的评审队列。第三方对 Octoverse 数据的整理称，超过 40% 的 PR 由代理启动，但这些基于公开和开源活动的数量指标衡量的是提交与合并，不能直接证明生产力或软件质量提升。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://octoverse.github.com/">Octoverse 2026: The state of open source</a></li>
<li><a href="https://github.blog/news-insights/octoverse/octoverse-commits-pushes-reach-new-highs-in-2026-as-developers-build-with-agents/">Octoverse: Commits, pushes, reach new highs in 2026 as ...</a></li>
<li><a href="https://github.blog/news-insights/octoverse/">The latest Octoverse findings - The GitHub Blog</a></li>
<li><a href="https://github.blog/news-insights/octoverse/">The latest Octoverse findings - The GitHub Blog</a></li>
<li><a href="https://github.blog/news-insights/octoverse/octoverse-commits-pushes-reach-new-highs-in-2026-as-developers-build-with-agents/">Octoverse: Commits, pushes, reach new highs in 2026 as ...</a></li>
<li><a href="https://explainx.ai/blog/github-octoverse-2026-7-4-billion-commits-month-agents-40-percent-pull-requests-2026">GitHub Octoverse 2026: 7.4B Commits, 40% Agent PRs - explainx.ai</a></li>

</ul>
</details>

**标签**: `#GitHub`, `#developer activity`, `#AI coding agents`, `#software metrics`

---

<a id="item-tech-news-7"></a>
### [Discord 公开服务器将接入网络搜索](https://techcrunch.com/2026/10/27/discord-is-making-its-public-communities-more-searchable-and-people-have-concerns/) ⭐️ 7.0/10

Discord 宣布分阶段让公开的“可发现服务器”内容进入网络搜索：11 月 16 日起，每个此类服务器将生成独立网页，其中可能包含自动生成的讨论摘要；12 月中旬起，管理员选定的部分公开频道消息可能出现在搜索结果中。管理员可选择参与频道，成员也可自行退出，发布到搜索结果中的内容不会显示用户名和头像。鉴于法律限制，该功能将在欧盟、英国等地默认关闭，青少年用户不参与。

telegram · zaihuapd · 10月28日 03:21

**「背景：Discord 的公开网页呈现」** Discord 此次扩展的是“可发现服务器”的网页呈现功能，而不是直接公开索引其客户端内的全部内容；管理员可以指定哪些频道对外展示，私密频道和受角色限制的频道则永不纳入。首批计划呈现的是频道讨论摘要，单条公开消息要到后续阶段才可能被搜索引擎收录。

**「对公开社区的影响」** 按计划，Discord 公开可发现服务器中的部分频道消息将从 12 月中旬起进入网络搜索结果，未加入服务器的用户也可能借此找到并访问这些内容；管理员应只开放可接受被索引的频道，并告知成员可自行退出。搜索结果中的发布内容不显示用户名和头像，可降低直接身份关联，但该功能在欧盟、英国等地区默认关闭，且青少年不参与。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://support.discord.com/hc/en-us/articles/44049845164823-Discoverable-Server-Web-Presence">Discoverable Server Web Presence – Discord</a></li>
<li><a href="https://discord.com/blog/making-content-from-discoverable-servers-easier-to-discover">Making Content from Discoverable Servers Easier to Discover</a></li>
<li><a href="https://support.discord.com/hc/en-us/articles/44302319454359-Discoverable-Content-on-the-Web">Discoverable Content on the Web – Discord</a></li>
<li><a href="https://www.engadget.com/2299126/discord-server-messages-google-searchable-opt-out/">Discord Public Server Messages May Be Soon Searchable On...</a></li>

</ul>
</details>

**标签**: `#Discord`, `#网络搜索`, `#隐私`, `#内容发现`

---

<a id="item-tech-news-8"></a>
### [长鑫存储拟限量生产 HBM3E](https://www.reuters.com/world/china/chinas-cxmt-start-advanced-ai-memory-production-despite-poor-yields-sources-say-2026-10-28/) ⭐️ 7.0/10

据路透社援引两名知情人士，长鑫存储已向多家中国本土 AI 芯片设计公司送样 HBM3E，并计划在报道发布后的两个月内启动限量生产。知情人士称，其当前良率仅为 20%至 30%，远低于 SK 海力士约 70%的水平；测试性能更接近 SK 海力士上一代 HBM3，预计售价也会高于海外同类产品。长鑫存储之所以推进该项目，据称是因为美国出口管制加剧了国内 AI 内存短缺，但相关量产计划和指标目前尚未得到独立验证。

telegram · zaihuapd · 10月28日 06:19

**「HBM3E 量产背景」** 路透社援引知情人士称，美国出口管制导致国内 AI 内存严重短缺，这是长鑫存储仍推进 HBM3E 送样和限量生产的直接背景。报道以 SK 海力士上一代 HBM3 为性能参照，称长鑫样品的表现更接近该上一代产品，而 20% 至 30% 的良率表明其仍处于早期量产爬坡阶段。

**「量产导入仍受低良率限制」** 对国内 AI 芯片设计公司而言，当前影响主要限于送样验证而非成熟量产：长鑫存储已向多家厂商送样，并计划未来两个月内限量生产，但 20% 至 30% 的良率意味着首批产品成本高、数量有限。测试性能更接近 SK 海力士上一代 HBM3，且预计售价高于海外同类产品，因此设计方在定版和采购前仍需核验实际性能与总成本，不能仅凭“HBM3E”名称视作与海外领先产品等效。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thenextweb.com/news/cxmt-hbm3e-ai-memory-low-yields-reuters">China ’s CXMT will make AI memory despite yields as low as 20 ...</a></li>
<li><a href="https://cryptobriefing.com/cxmt-hbm3e-production-low-yields/">CXMT plans HBM 3 E production even as most of its chips fail quality...</a></li>

</ul>
</details>

**标签**: `#HBM3E`, `#AI芯片`, `#存储芯片`, `#出口管制`, `#中国半导体`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [Alphabet 将 AI 模式搜索广告扩展至全球](https://techcrunch.com/2026/10/28/google-expands-ai-search-ads-globally-as-core-ad-growth-slows/) ⭐️ 8.0/10

Alphabet 在第三季度财报电话会上宣布，将 AI 模式搜索广告扩展至全球更多市场，并在美国推出支持多轮对话的广告。与此同时，搜索广告收入同比增长 12%，低于此前两个季度的 17%和 19%；财报公布后，公司股价盘后一度下跌超过 10%。

telegram · zaihuapd · 10月29日 01:43

**「背景」** Alphabet 此次扩张正值第三季度搜索及其他广告收入同比仅增长 12%，低于此前两个季度的 17%和 19%；同期 Google 服务收入增长 11%至 963 亿美元，显示核心广告业务增速正在放缓。

**「影响」** 对依赖 Google 搜索获取消费者的广告主而言，AI 模式广告扩至更多市场、美国新增多轮对话广告，提供了新的付费触达方式；但 Alphabet 搜索广告第三季度同比增长 12%至 633.5 亿美元，仍低于分析师预期。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://s206.q4cdn.com/479360582/files/doc_news/2026/Oct/28/attachments/2026q3-alphabet-earnings-release.pdf">GOOG Exhibit 99.1 Q3 2026 - s206.q4cdn.com</a></li>
<li><a href="https://www.cnbc.com/2026/10/28/alphabet-googl-earnings-q3-2026.html">Alphabet (GOOGL) earnings Q 3 2026</a></li>

</ul>
</details>

**标签**: `#Alphabet`, `#AI搜索广告`, `#季度财报`, `#搜索广告`, `#科技股`

---

<a id="item-finance-news-2"></a>
### [长鑫科技纳入上证综指和科创综指](https://m.gelonghui.com/live/2733034) ⭐️ 7.0/10

据中证指数公司披露，长鑫科技已被纳入上证综合指数和上证科创板综合指数，并以 4.67%和 15.74%的权重分别成为两大指数的第一大权重股。在上证综指中，其权重高于农业银行的 3.83%和工商银行的 3.77%。

telegram · zaihuapd · 10月28日 08:03

**「背景」** 长鑫科技于 2026 年 7 月 27 日登陆科创板，至 10 月 27 日上市满三个月，符合“上市以来日均总市值排名沪市前 10 位、上市满三个月后计入指数”的条件。报道同时称单个样本权重上限为 15%，但 15.74%的权重与“不超过 15%”的表述存在不一致。

**标签**: `#上证综合指数`, `#科创板综指`, `#指数调整`, `#长鑫科技`

---

