---
layout: default
title: "Horizon Summary: 2026-11-19 (ZH)"
date: 2026-11-19
lang: zh
---

> 从 37 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [谷歌发布 Gemini 4 Neon，支持 100 万 token 上下文](#item-tech-news-1) ⭐️ 8.0/10
2. [Nginx HTTP/2 未认证远程代码执行漏洞与修复](#item-tech-news-2) ⭐️ 8.0/10
3. [OpenAI 推进模型辅助芯片设计，开放范围待确认](#item-tech-news-3) ⭐️ 8.0/10
4. [Genie 4 向符合条件的 Google AI Ultra 订阅者开放](#item-tech-news-4) ⭐️ 7.0/10
5. [Voyager 1 交互式拆解：从核电池到单比特存储](#item-tech-news-5) ⭐️ 7.0/10
6. [Quad9 退出法国与 DNS 反盗版争议](#item-tech-news-6) ⭐️ 7.0/10
7. [微软宣布七款模型，主打规模化性价比](#item-tech-news-7) ⭐️ 7.0/10
8. [能量模型推理：宣称效率提升 385 倍](#item-tech-news-8) ⭐️ 7.0/10
9. [微信 AI 助手小微扩大测试，日活达 3000 万](#item-tech-news-9) ⭐️ 7.0/10

**财经新闻**
1. [腾讯三季报：资本开支高于预期，自由现金流转负](#item-finance-news-1) ⭐️ 7.0/10
2. [中韩结束自贸协定服务与投资后续谈判](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [谷歌发布 Gemini 4 Neon，支持 100 万 token 上下文](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 8.0/10

谷歌发布 Gemini 4 Neon，主打复杂软件工程、知识工作和科研工作流的快速端到端执行，现已向开发者、企业及 Google AI Pro/Ultra 订阅用户开放。其 API 定价为每百万输入 token 3 美元（缓存输入 0.15 美元）、输出 15 美元，支持 100 万 token 上下文；所引 Artificial Analysis 数据显示，其编程智能体指数为 58.6、排名第一，智能指数 xhigh 档为 61、排名第三，Terminal-Bench 4.1 成绩为 65.2%。谷歌称默认 high 档的单任务成本较 Carbon 低 32%；与此同时，讨论材料显示 Neon 的 AA 综合分高于 Carbon，但 CritPt 研究级推理评分更低，因此它并非对 Carbon 长时程科研定位的全面替代。现有来源未披露模型规格和完整评测方法，不能据此推断其在所有工作负载中均更优。

hackernews · yigitdemirag · 11月18日 21:34 · [社区讨论](https://news.ycombinator.com/item?id=50552424)

**「Gemini 4 的工作流分工」** Gemini 4 Neon 延续了 Google 将同一代模型按工作流拆分的思路。Google 的 Neon 模型卡将 Carbon 定位为最困难的长时程项目、Hydrogen 定位为快速日常执行，而 Neon 侧重兼顾深度与效率；Horizon 10 月 29 日的日报还显示，Carbon 首发时主攻可持续数天的网络安全与大型代码库漏洞修复，这构成了理解 Neon 差异分工的直接背景。

**「选型与成本影响」** 对需要在编码、智能体和复杂分析工作流中选型的开发者与企业，Gemini 4 Neon 提供了直接的成本优势：官方称默认 high 档单任务成本比 Carbon 低 32%，API 定价为每百万输入 token 3 美元、缓存输入 0.15 美元、输出 15 美元，并支持 100 万 token 上下文。OpenRouter 已列出该模型并显示两家提供商，Artificial Analysis 则将 Neon（Xhigh）以 61 分列为 Google 模型中智能分最高者；实际迁移时仍应使用自身编码和长上下文任务进行对照测试，因为现有材料未说明它与 Carbon 的接口兼容性。

**「开发者讨论」** 多位评论者对 Neon、Carbon、Astra、Sol 等持续增加且用途难辨的模型名称感到疲劳；也有人基于个人体验认为 Gemini 仍不及 Anthropic Opus 5.5，但未提供可复现实验。declanjackson 指出模型能力正变得“锯齿化”：Neon 的 AA 综合分更高，但 CritPt 等研究推理指标低于偏向长时程任务的 Carbon；另有用户在 OpenRouter 当时的路由上观察到 Neon 约 127 token/s、Carbon 约 46 token/s，这属于时点性实测，并非官方性能结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-carbon/">2026-10-29 — Google 发布 Gemini 4 Carbon，先限网络安全伙伴测试</a></li>
<li><a href="https://deepmind.google/models/model-cards/gemini-4-neon/">Gemini 4 Neon - Model Card — Google DeepMind</a></li>
<li><a href="https://openrouter.ai/google/gemini-4-neon">Gemini 4 Neon - API Pricing &amp; Benchmarks | OpenRouter</a></li>
<li><a href="https://deepmind.google/blog/introducing-gemini-4-neon/">Introducing Gemini 4 Neon - deepmind.google</a></li>
<li><a href="https://artificialanalysis.ai/models/creators/google">Google Models: Intelligence, Performance &amp; Price</a></li>

</ul>
</details>

**标签**: `#Gemini 4`, `#Google AI`, `#large language models`, `#AI model evaluation`, `#model naming`

---

<a id="item-tech-news-2"></a>
### [Nginx HTTP/2 未认证远程代码执行漏洞与修复](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 8.0/10

报道称，Xint 公开了 NGINX2Root 链，将 5 个 Nginx 漏洞与一个 Linux 内核缺陷串联后，可由 Nginx 访客一路利用至主机 root；其中 CVE-2026-123007 是 HTTP/2 流控内存破坏漏洞，未认证攻击者可在 worker 中执行命令，报道还列出 CVE-2026-123633，但未说明后者的具体机制。Nginx 1.30.7 和 1.31.9 已于 11 月 18 日发布，修复共 10 个 CVE；Rapid7 已发布 PoC，但报道时未发现在野利用，无法立即升级的部署应关闭对外 HTTP/2。现有材料未列出受影响版本范围，也未提供完整利用细节。

hackernews · speedping · 11月18日 15:19 · [社区讨论](https://news.ycombinator.com/item?id=50547374)

**「HTTP/2 流控与内存破坏」** HTTP/2 使用流控窗口限制单个流可占用的数据量；在启用 HTTP/2 的 Nginx 配置中，恶意构造的请求可令流控窗口超过允许上限，触发基于堆的缓冲区溢出（CVE-2026-123007），使未经认证的攻击者可能执行任意代码或造成拒绝服务。F5 的公告将 CVE-2026-123007 和 CVE-2026-123633 的适用范围限定为启用 HTTP/2 的配置，因此是否启用该协议是判断暴露面的关键条件。

**「HTTP/2 暴露面需要立即处置」** 对外启用 HTTP/2 的 NGINX 部署面临未认证远程代码执行风险，攻击者可能在 worker 进程内执行命令；这两个漏洞位于 NGINX 本身，CVSS 4.0 评分均为 9.2，即使网站或 API 的应用代码安全也无法消除风险。管理员应优先升级至 1.30.7 或 1.31.9；暂时无法升级时，应在受影响的 server 块中设置 \`http2 off\`，并从相关 \`listen\` 指令中移除 \`http2\`，以阻断 CVE-2026-123007 和 CVE-2026-123633 的利用路径。需要注意，关闭 HTTP/2 并不覆盖 NGINX2Root 中另外三个漏洞；针对这些漏洞还需分别关闭 HTTP/3、避免在请求阶段动态解析上游地址，并限制或停止公开邮件代理。

**「评论者对披露与风险的判断」** black3r 认为开源仓库的修复已提前约一周公开，熟悉漏洞监控的攻击者可能已据此开发利用，并批评 F5、Nginx 及报告方未先发布安全公告，即使关闭 HTTP/2 是直接缓解措施。fduran 援引 W3Techs 称 HTTP/2 并非 Nginx 默认配置且约有 12% 的服务器启用；userbinator 将问题归因于 HTTP/2 的实现复杂度，testtestmetest 则声称利用需要 128GB 流量和特定 CPU 指令以淡化风险，这些均属评论者观点，未获独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.sophos.com/en-us/security-advisories/sophos-sa-20261118-nginx2root">Advisory: NGINX Vulnerabilities - nginx2root (CVE-2026-123007 ...</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-123007">CVE-2026-123007 - Red Hat Customer Portal</a></li>
<li><a href="https://www.ox.security/blog/nginx2root-five-critical-nginx-flaws-expose-web-servers-to-remote-code-execution/">NGINX 2 Root: 5 Critical NGINX RCE Vulnerabilities &amp; CVE Fixes</a></li>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>
<li><a href="https://thehackernews.com/2026/11/10-year-old-nginx-http2-flaw-lets.html">10-Year-Old NGINX HTTP / 2 Flaw Lets Unauthenticated Attackers...</a></li>

</ul>
</details>

**标签**: `#nginx`, `#remote-code-execution`, `#http/2`, `#cybersecurity`, `#cve`

---

<a id="item-tech-news-3"></a>
### [OpenAI 推进模型辅助芯片设计，开放范围待确认](https://openai.com/index/advancing-chip-design-with-our-models/) ⭐️ 8.0/10

OpenAI 在官方文章中介绍其模型用于芯片设计的进展，讨论范围包括 EDA 自动化、模拟电路与 RTL 流程，并涉及 RISC-V 设计。现有材料未提供模型版本、基准测试、任务规模或前后对比，因此无法量化设计效率与正确性的提升。文章是否开放相关 RISC-V 设计也未在可用材料中明确。

hackernews · vighneshiyer · 11月18日 17:45 · [社区讨论](https://news.ycombinator.com/item?id=50549493)

**「AI 辅助芯片设计的流程」** 芯片设计通常借助电子设计自动化（EDA）工具完成 RTL 描述、电路综合、仿真验证以及模拟电路建模等环节，AI 模型的作用主要是辅助或优化这些既有流程。OpenAI 官方材料称，其模型已用于优化 Jalapeño 芯片采用的电路并改进 RISC‑V 核设计，示例涉及 GPT‑6 Astra；现有信息未提供公开设计文件、量化基准或独立验证结果。

**「对芯片设计团队的影响」** OpenAI 称，GPT‑6 Astra 已优化 Jalapeño 芯片所用电路并改进 RISC‑V 核设计，但这尚不能视为可复现、可投产的芯片设计能力：现有信息未提供端到端基准、完整方法或相关设计文件的发布状态。芯片团队在接入现有 EDA 与仿真流程时，应分别验证 Verilog 生成、调试和参考模型生成能力，并确认模型访问条件及设计资产是否可用。

**「实践与开放性争议」** skyberrys 分享其个人做法：把芯片设计当作软件问题，让智能体生成电路、自动化 EDA 流程并监控多小时的仿真，同时让 RTL 仅占设计的一小部分、保留大部分模拟设计；这是单个使用者的经验，并非独立验证。jacquesm 认为闭源模型企业在服务客户的同时参与其业务，可能形成竞争与信息优势，zardo 则质疑相关 RISC-V 设计为何尚未公开。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/advancing-chip-design-with-our-models/">Advancing chip design with OpenAI models</a></li>
<li><a href="https://openai.com/index/advancing-chip-design-with-our-models/">Advancing chip design with OpenAI models</a></li>
<li><a href="https://arxiv.org/html/2601.21448v1">ChipBench: A Next-Step Benchmark for Evaluating LLM ...</a></li>

</ul>
</details>

**标签**: `#AI for chip design`, `#Electronic Design Automation`, `#RISC-V`, `#OpenAI`, `#Semiconductors`

---

<a id="item-tech-news-4"></a>
### [Genie 4 向符合条件的 Google AI Ultra 订阅者开放](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 7.0/10

Google DeepMind 宣布，Genie 4 已面向符合资格的 Google AI Ultra 订阅者开放，用于生成可交互的虚拟环境。现有材料强调，新版本在保持生成环境一致性方面有所改进，社区尤其关注观察视角旋转 360° 时细节能否保持稳定；但材料未提供基准成绩、模型规模、生成延迟或 API 与兼容性数据。评论者提出的“像游戏引擎一样工作”仍属于潜在应用设想，而非已经发布或经独立验证的能力。

hackernews · leumon · 11月18日 18:49 · [社区讨论](https://news.ycombinator.com/item?id=50550415)

**「从 Genie 3 到 Genie 4」** Project Genie 最初仅面向美国 Google AI Ultra 订阅者，由 Genie 3 驱动，用于创建、探索和重混互动世界，这构成了 Genie 4 的直接产品前序。Horizon 的 10 月 28 日日报记载，Genie 4 当时仍处于面向可信测试者的研究预览阶段，并计划扩展至 Ultra 订阅者以及 Gemini API、AI Studio 合作伙伴；此次更新则标志着它从有限测试转向订阅用户开放。

**「实际影响」** 当前使用门槛仍是 Google AI Ultra 订阅资格。一名评论者称其 Workspace 账户无法使用 Ultra，而英国的个人 Gmail 账户仍只显示 Genie 3；这虽不能确认官方规则，却说明使用者需要核对账户、地区和版本资格。材料也未公布 API、企业版或工作流兼容性，开发者暂时无法确认能否将其接入现有游戏引擎工具链。

**「社区讨论」** kingrolo 对“Eligible Google AI Ultra subscribers”的资格说明不清晰表示不满，并报告其英国个人账户仍只显示 Genie 3。giancarlostoro 认为这类世界模型有朝一日可能成为游戏引擎的工作方式，也有评论者担忧这类技术的潜在负面后果；这些均为社区观点，不是已确认的产品能力或影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/google-deepmind/project-genie/">Google AI Ultra subscribers in the U.S. can now try out Project Genie .</a></li>
<li><a href="https://deepmind.google/blog/genie-4-a-new-generation-of-world-simulation/">2026-10-28 — Google DeepMind 发布 Genie 4 世界模型</a></li>

</ul>
</details>

**标签**: `#world models`, `#generative AI`, `#Google DeepMind`, `#game engines`, `#product launch`

---

<a id="item-tech-news-5"></a>
### [Voyager 1 交互式拆解：从核电池到单比特存储](https://rshekhar.com/voyager/) ⭐️ 7.0/10

开发者 Raj Shekhar 发布了一个交互式 Voyager 项目，面向希望从系统层级深入了解旅行者号硬件和运行状态的读者。页面可显示两艘 Voyager 的当前位置，并逐层展开 Voyager 1 的放射性同位素热电机（核电池，内含 24 个钚球）、数据计算机、单颗存储芯片乃至单个比特，同时介绍《金唱片》封面、无线电修复过程和正在接收信号的地球天线。项目呈现的是既有航天器系统与工程历史，而非新的航天研究；作者在发布说明中称，Voyager 1 当时距离地球约一个光日。

hackernews · raj-shekhar · 11月18日 16:18 · [社区讨论](https://news.ycombinator.com/item?id=50548161)

**「背景」** 要理解项目中的无线电修复演示，需了解旅行者号在关键部件失效后依赖备用系统和地面试验的历史。1978 年，旅行者 2 号的主无线电接收机失效后，其余任务改用备用接收机；后来向旅行者 1 号的计算机上传软件更新前，NASA 会先在距离地球更近的旅行者 2 号上试验同一流程。

**「实际用途」** 工程师、学生和航天爱好者可以通过页面及作者提供的直达链接，集中查看核电源、计算存储器、深空通信链路和金唱片等部件的具体细节，也可配合配套的四分钟影片理解同一套交互模型；该项目本身不代表新的在轨操作或研究突破。

**「社区讨论」** 评论者对项目表示赞赏，但有人指出内容仍有缺失，并追问 CMOS 存储芯片持续读错数据的具体物理机制，包括晶体管栅极与线路、热循环及封装互连故障。另有评论者询问项目是否主要由 AI 生成、是否包含原创研究，以及相关复原是否经过权威资料核验；所提供的评论中没有出现对这些问题的回答。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Voyager_2">Voyager 2 - Wikipedia</a></li>

</ul>
</details>

**标签**: `#computer systems`, `#space hardware`, `#interactive visualization`, `#digital archaeology`

---

<a id="item-tech-news-6"></a>
### [Quad9 退出法国与 DNS 反盗版争议](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

Quad9 在法国法院命令涉及域名解析阻断的背景下退出法国，相关变化主要影响法国用户及依赖其本地 DNS 服务的网络管理员。文章认为，在递归 DNS 解析器层面执行反盗版措施，会把版权执法转化为更广泛的访问干预，并引发审查风险及法律边界争议。现有材料属于观点分析，未交代具体封锁域名、命令全文、实际执行方式或独立效果数据，因此无法据此判断措施的覆盖范围和行业影响。

hackernews · ritzaco · 11月18日 13:18 · [社区讨论](https://news.ycombinator.com/item?id=50545958)

**「Quad9 法国退出的背景」** 这件事的直接背景是，Quad9 作为递归 DNS 解析器收到法国法院的命令，必须对法国境内用户屏蔽若干域名的递归解析；Quad9 在 10 月 22 日的公告称，法院将每日罚款从 58 万欧元降至 1,000 欧元，但公司仍决定停止向法国用户提供服务，停止日期为 11 月 24 日。EFF 将其描述为法国法院针对涉嫌侵犯版权网站的屏蔽命令迫使一家保护用户隐私的非营利 DNS 服务退出法国，说明争议涉及司法命令对公共递归 DNS 基础设施的直接约束。

**「法国用户与解析器运营方的合规压力」** Quad9 计划于 2026 年 11 月 24 日停止在法国提供免费公共 DNS 解析服务，而不接受针对 beIN Sports 所指版权侵权域名的封锁命令；依赖该服务的法国用户届时需改用其他递归解析器，并检查终端及网络配置。法国法院此前因 Quad9 未屏蔽相关域名而判其每日缴纳罚款，因此运营商在可用性与执行域名级封锁之间面临直接取舍。

**「评论者质疑执法路径与替代方案」** 评论者 trentnix 认为，以 DNS 封锁打击盗版会演变为政府压制言论的后门；bemtevi 则主张通过价格合理且不含 DRM 的合法下载服务改善付费体验。skrebbel 提出，责任究竟应归于作出判决的法院，还是制定相关法律并迫使其执行的立法者，仍需进一步区分。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://quad9.net/news/blog/au-revoir-france/">Farewell, France | Quad9</a></li>
<li><a href="https://torrentfreak.com/dns-resolver-quad9-will-leave-france-after-court-orders-piracy-blocking-penalty/">DNS Resolver Quad9 Will Leave France After Court Orders ...</a></li>
<li><a href="https://www.eff.org/deeplinks/2026/10/french-courts-site-blocking-orders-drive-quad9-out-france">French Court’s Site-Blocking Orders Drive Quad9 Out Of France</a></li>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad9’s withdrawal from France: A canary in the coal mine</a></li>
<li><a href="https://techstackups.com/articles/quad9-leaves-france-dns-blocking/">Quad9 Is Leaving France: Why DNS Resolvers Are the Wrong ...</a></li>
<li><a href="https://www.heise.de/en/news/Censorship-ruling-prompts-DNS-service-Quad9-to-leave-France-11497631.html">Censorship ruling prompts DNS service Quad9 to leave France</a></li>

</ul>
</details>

**标签**: `#DNS`, `#network infrastructure`, `#internet policy`, `#digital rights`

---

<a id="item-tech-news-7"></a>
### [微软宣布七款模型，主打规模化性价比](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 7.0/10

微软在 Ignite 2026 宣布七款新 AI 模型，主打可扩展的价格与性能表现，其中社区讨论尤其关注编码模型 MAI Code 2。当前材料未提供七款模型的完整名单、具体定价、兼容性、开放方式或基准测试方法，因此其实际性价比优势仍无法独立验证。

hackernews · gmays · 11月18日 16:08 · [社区讨论](https://news.ycombinator.com/item?id=50548021)

**「企业 AI 栈与评测背景」** 此次发布是微软 Ignite 2026 企业 AI 全栈战略的一部分：除七款 MAI 模型外，微软还把 Agent 365、业务上下文、智能体治理、安全与 Azure 硬件纳入同一框架，其中 MAI Code 2 面向智能体编程，Cyber 2 Flash 面向安全任务。理解其性价比主张时需注意基准口径：微软称 MAI Code 2 可达到 GPT-6.1 Sol 约 98% 的编码质量、价格约为其 40%，但第三方整理仍将实际价格和未解决问题列为需要进一步核验的项目。

**「选型应转向每任务成本」** 对准备试用的开发团队，微软新增七款模型并不会自动带来成本下降；外部评测称，OpenAI GPT‑6.2 Astra 在 Artificial Analysis Intelligence Index 排名第二并处于多数“成本/任务”帕累托前沿，标价每百万 token 为 8/40 美元，缓存输入为 0.40 美元。现有发布材料未提供微软各型号的价格和可复现基准，因此应将外部资料记录于 11 月 17 日发布的 MAI Code 2 和 MAI Code 2 Flash 与现用模型进行同任务测试，比较成功率、延迟和每任务成本后再决定是否采用。

**「社区评价与分歧」** 一名实际测试者称 MAI Code 2 在其日常编码中表现良好，并认为它可以与评论中提到的 Opus 或 Sol 相比，但这只是个人体验，未附可复现的测试数据。另有评论者认为微软若想扩大市场份额，应提供开源或开放权重模型，也有人质疑微软的产品执行和 Ignite 发布的内容，显示社区对性价比、开放性及市场竞争力存在明显分歧。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world-class models at scalable price-performance ...</a></li>
<li><a href="https://windowsforum.com/news/microsoft-ignite-2026-mai-code-2-models-agent-365-governance-and-enterprise-ai-stack.453003/">Microsoft Ignite 2026: MAI Code 2 Models, Agent 365 ...</a></li>
<li><a href="https://thediaryofai.com/models-releases/microsoft-mai-code-2-seven-models/">Microsoft MAI Code 2: Prices, Benchmarks, Ignite Models</a></li>
<li><a href="https://artificialanalysis.ai/articles/openai-has-the-2-model-in-the-intelligence-index-with-the-release-of-gpt-6-2-astra-and-gpt-6-2-sol">OpenAI has the # 2 model in the Intelligence Index... | Artificial Analysis</a></li>
<li><a href="https://benchlm.ai/models/gpt-6-2-astra">GPT-6. 2 Astra Benchmarks &amp; Pricing (November 2026)</a></li>

</ul>
</details>

**标签**: `#Microsoft AI`, `#large language models`, `#model pricing`, `#coding models`

---

<a id="item-tech-news-8"></a>
### [能量模型推理：宣称效率提升 385 倍](https://energy-based-reasoners.github.io/) ⭐️ 7.0/10

Energy-Based Reasoners 项目提出用能量模型处理约束密集型推理任务，并宣称可将推理效率提升 385 倍；这一数字目前属于项目方主张，所给材料未提供独立验证。项目及讨论涉及的示例包括数独、计数、数学和 Lean 证明，显示这种方法可用于评估或验证候选解，但尚不能据此认定其具备通用任务所需的扩展能力。

hackernews · frenchmajesty · 11月18日 09:29 · [社区讨论](https://news.ycombinator.com/item?id=50543989)

**「能量函数与迭代推理」** 项目页面将能量基推理器（EBR）定义为：在潜在推理状态上学习一个能量函数，并把循环更新表示为对该能量的梯度下降；能量用于比较候选状态，梯度用于引导状态修正，也可作为停止迭代的信号。这里的“能量”是推理搜索中的标量评分，而非物理能量；项目声称的 385 倍推理效率提升应结合其约束推理基准理解，不能据此推断训练成本、所有任务准确率或可扩展性都会同步改善。

**「对约束型推理工作负载的影响」** 如果项目结果能在目标工作负载上复现，采用循环式模型处理数独等约束型推理的团队可能显著降低每次决策的推理算力：报道汇总称，EBR 在四个算法推理基准上达到或超过既有循环推理模型，并在 Sudoku-Extreme 上将推理计算量减少 345 倍，同时取得 99.9% 的准确率；另一报道给出的上限是相对项目所列基线最高 385 倍的效率提升。现有证据集中于特定算法基准，社区评论者还认为 EBM 训练困难且数独求解方案扩展性有限，因此开发者应先验证自身任务上的准确率、端到端延迟及训练与扩展成本，不能直接将这组结果外推为通用 LLM 推理的替代方案。

**「社区讨论」** 有参与者建议结合 Yann LeCun 等人参与的 Logical Intelligence 项目理解 EBM，并认为这类方法可能更适合 LLM 较弱的小学数学和计数问题；另一位自称研究一年以上的评论者则认为 EBM 虽适合作为验证器，却训练困难、应用狭窄，数独求解能否扩展到任意规模仍有疑问。另有评论者指出，论文仅说明模型会为候选预测分配一个标量“能量”，但没有清楚解释其取值域及该术语的具体含义。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://energy-based-reasoners.github.io/">Energy - Based Reasoners : Your Recurrent Reasoner Should Be an...</a></li>
<li><a href="https://apexneuralnews.com/news/energy-based-reasoners-385x-more-efficient-inference">Energy-Based Reasoners: 385x more efficient inference</a></li>
<li><a href="https://todayforai.com/en/story/story-a37d7264-d1b">Energy-Based Reasoners Achieve 385x Inference Efficiency Gain</a></li>

</ul>
</details>

**标签**: `#energy-based models`, `#AI reasoning`, `#inference efficiency`, `#constraint solving`, `#machine learning`

---

<a id="item-tech-news-9"></a>
### [微信 AI 助手小微扩大测试，日活达 3000 万](https://mp.weixin.qq.com/s/r3NthxJZQJgztyLADwNV4A) ⭐️ 7.0/10

腾讯在 2026 年第三季度财报中表示，微信 AI 助手“小微”的测试范围已扩大，日活跃用户达到 3000 万，并正逐步接入聊天、朋友圈、公众号和视频号等微信主要场景。小微采用针对推理成本效率优化的 WeLM 定制模型；腾讯称其推理成本较低且仍在下降，并预计未来让部分推理任务在用户设备端运行。现有披露尚未说明具体模型能力、各场景功能、端侧覆盖范围或第三方验证结果，3000 万日活及成本表现均来自腾讯口径。

telegram · zaihuapd · 11月18日 11:35

**「“小微”的微信原生形态」** “小微”的产品定位不是独立 AI App，而是嵌入微信首页的原生助手；一篇公开报道将其描述为以腾讯自研 WeLM 为主模型、部分场景联动 DeepSeek，但这并非本次腾讯财报披露的细节。理解此次测试扩围的关键，是它发生在微信既有的聊天、朋友圈、公众号和视频号场景内。

**「测试用户需确认功能入口」** 被纳入扩大测试的微信用户将逐步在聊天、朋友圈、公众号和视频号等原生场景中遇到“小微”，使用前应确认所在账号是否开放及具体功能范围，不能将 3000 万日活视为全量用户均已可用。部分任务转移到设备端运行目前仍是腾讯的未来计划，现阶段不应据此依赖离线推理能力或确定的相关隐私、成本收益。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://post.smzdm.com/p/a03633d9/">不扎堆做独立AI App...</a></li>

</ul>
</details>

**标签**: `#微信`, `#AI助手`, `#WeLM`, `#端侧推理`, `#产品部署`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [腾讯三季报：资本开支高于预期，自由现金流转负](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

腾讯公布的 2026 年第三季度财报显示，营收 2073 亿元，同比增长 8%，低于市场预期；归母净利润 636 亿元，同比仅增 0.8%。单季资本开支 814.33 亿元，高于市场预估的 554 亿元，自由现金流为负 691 亿元；腾讯称，按其披露口径，WorkBuddy 日均 Token 消耗量超过 100 万亿，为国内大语言模型产品最高。

telegram · zaihuapd · 11月18日 09:20

**「背景」** 此前在 2026 年 4 月 23 日发布并开源 Hy3 preview 的是腾讯重组后的混元团队；第三季度公司资本开支（购置长期资产等项目的现金支出）达到 814.33 亿元，高于市场预估的 554 亿元。

**「AI 投入加剧现金流压力」** 腾讯的 AI 投入正在明显加剧现金流压力：第三季度资本开支达 814.33 亿元、自由现金流降至负 691 亿元，较第二季度的 527.84 亿元和负 138 亿元进一步恶化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://m.guancha.cn/GongSi/2026_05_14_817078.shtml">腾 讯 半 年 跌去 三 成多，马化 腾 给出怎样的答案-观察者网</a></li>
<li><a href="https://post.smzdm.com/p/axkzngg3/">放弃元宝押注 WorkBuddy ， 腾 讯 AI 这 场 转型算成功吗_IT... | 什么值得买</a></li>

</ul>
</details>

**标签**: `#腾讯`, `#季度财报`, `#资本开支`, `#自由现金流`, `#中国AI`

---

<a id="item-finance-news-2"></a>
### [中韩结束自贸协定服务与投资后续谈判](https://x.com/Jaemyung_Lee/status/2122988472994791476) ⭐️ 7.0/10

中韩于 11 月 18 日宣布，自贸协定服务与投资后续谈判实质性结束；中方承诺在电影、游戏等领域给予韩国最惠国待遇，并扩大旅游、法律、建筑和金融领域开放，视听节目共同制作范围将由电影扩至电视剧、动画、综艺和纪录片，但部分技术事项仍待协商。

telegram · zaihuapd · 11月18日 10:02

**「背景」** 这轮后续谈判是中韩自贸协定第二阶段的一部分，始于 2018 年 3 月；主要谈判至此实质性结束，但部分技术事项仍由工作层面继续处理。

**「行业影响」** 韩国影视、游戏、旅游、法律、建筑和金融企业是主要潜在受益方，因为协议扩大了市场准入并承诺最惠国待遇，视听合拍范围也扩至电视剧、动画、综艺和纪录片；具体实施仍待部分技术事项敲定。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gov.cn/yaowen/liebiao/202611/content_7086520.htm">习近平会见 韩 国总统 李 在 明 __ 中 国政府网</a></li>

</ul>
</details>

**标签**: `#中韩自贸协定`, `#服务与投资`, `#影视与游戏`, `#市场准入`

---