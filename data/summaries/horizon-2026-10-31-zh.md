# Horizon 每日速递 - 2026-10-31

> 从 35 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [Azure&\#x27;s Weakest Link – Five Full Cross-Tenant Compromises](#item-tech-news-1) ⭐️ 8.0/10
2. [Cursor Marketplace 的 Claude Code 扩展后门事件](#item-tech-news-2) ⭐️ 8.0/10
3. [Tangled 发布联邦式自托管代码协作平台](#item-tech-news-3) ⭐️ 7.0/10
4. [Binance 被指遭 20 分钟执行的 63 亿美元攻击](#item-tech-news-4) ⭐️ 7.0/10
5. [AI 代理是否让 SRE 岗位去技能化](#item-tech-news-5) ⭐️ 7.0/10
6. [FCC 拟限制中国运营商获取美国号码资源](#item-tech-news-6) ⭐️ 7.0/10
7. [苹果将在华测试首批 Apple 智能功能](#item-tech-news-7) ⭐️ 7.0/10

**财经新闻**
1. [SpaceX 最大 AI 算力客户或为 Anthropic](#item-finance-news-1) ⭐️ 8.0/10
2. [苹果将中国台湾地区 App Store 佣金降至 26%](#item-finance-news-2) ⭐️ 7.0/10
3. [DeepSeek 据报完成 1055 亿元融资，估值超 6155 亿元](#item-finance-news-3) ⭐️ 7.0/10
4. [四家日系车企在华产量降至 2020 年同期峰值四成以下](#item-finance-news-4) ⭐️ 7.0/10
5. [美股半导体板块重挫，英特尔跌超 26%](#item-finance-news-5) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Azure&\#x27;s Weakest Link – Five Full Cross-Tenant Compromises](https://www.binarysecurity.no/posts/2026/10/one-root-case) ⭐️ 8.0/10

A security research article claims five Azure vulnerabilities can produce complete cross-tenant compromises and discusses weaknesses involving OAuth redirects, tenant validation, IDOR, and path traversal.

hackernews · swq115 · 10月30日 10:06 · [社区讨论](https://news.ycombinator.com/item?id=50301854)

**标签**: `#azure`, `#cloud-security`, `#cross-tenant-vulnerability`, `#oauth`, `#idor`

---

<a id="item-tech-news-2"></a>
### [Cursor Marketplace 的 Claude Code 扩展后门事件](https://phorion.io/blog/offical-claude-code-vsx-compromise/) ⭐️ 8.0/10

Cursor 安全公告称，Cursor Marketplace 于 10 月 29 日出现一个并非 Anthropic 开发的篡改版 \`Anthropic.claude-code\` 2.1.313；该版本收集主机信息，并尝试向用户的 SSH \`authorized\_keys\` 写入攻击者公钥以维持长期访问，Cursor 估计最多 5000 名用户受影响。Cursor 已下架该版本、暂时关闭整个市场，在轮换密钥后恢复上线，攻击者服务器也已下线。Anthropic 表示其官方渠道、系统及员工设备均未受影响；用户应检查 \`authorized\_keys\` 中标为 \`svc-telemetry\` 的密钥，若存在则予以移除。

hackernews · \_chall · 10月30日 07:09 · [社区讨论](https://news.ycombinator.com/item?id=50300683)

**「官方渠道与第三方市场」** 理解这起事件的关键是区分“官方渠道被攻破”和“第三方市场供应链被篡改”：Cursor 与 Anthropic 均称，受影响的 Anthropic.claude-code 2.1.313 并非 Anthropic 构建或发布，Anthropic 的系统、员工设备及官方渠道版本未受影响。恶意副本利用 SSH 公钥认证机制，将标为“svc-telemetry”的攻击者公钥追加到 ~/.ssh/authorized\_keys；该文件保存允许通过 SSH 登录的公钥，因此这种改动旨在建立持久的远程访问。

**「检查并清除持久 SSH 后门」** 安装 Cursor 市场中遭篡改 Claude Code 扩展的用户，其主机可能被写入攻击者公钥，从而留下持久 SSH 登录入口。用户应立即检查 \`~/.ssh/authorized\_keys\` 中是否存在标记为 \`svc-telemetry\` 的公钥；一旦发现，即应按 Cursor 公告运行对应平台的修复脚本并移除该恶意密钥。

**「社区讨论」** Anthropic 员工 Felix Rieseberg 表示，攻击者利用其对 Cursor 市场的访问权限发布了篡改扩展，该扩展并非 Anthropic 构建或发布。社区对 Microsoft 官方 VS Code 或 Open VSX 注册表是否同样受影响仍有疑问，现有讨论未明确确认，因此 Cursor Marketplace 的影响范围不宜直接外推到其他注册表。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cursor.com/blog/claude-code-extension-security-notice">Security notice — malicious version of Anthropic.claude-code ...</a></li>
<li><a href="https://www.microsoft.com/en-us/security/blog/2026/10/30/inside-malicious-claude-code-branded-cursor-extension-persistent-ssh-backdoor/">Inside a malicious Claude Code-branded extension and its ...</a></li>

</ul>
</details>

**标签**: `#supply-chain security`, `#Claude Code`, `#VS Code extensions`, `#developer tools`, `#SSH key persistence`

---

<a id="item-tech-news-3"></a>
### [Tangled 发布联邦式自托管代码协作平台](https://tangled.org/blog/forge/) ⭐️ 7.0/10

Tangled 发布了一个以 AT Protocol 为核心的联邦式、可自托管代码协作平台，面向希望自行托管代码与协作服务、并以联邦方式组织仓库的开发者。其联合创始人称，本次发布已稳定 AT Protocol lexicons，全面重构了架构和 UI，并支持自托管完整技术栈或其中部分组件；组织功能也已上线。私有仓库尚未交付，团队计划在未来几周开始逐步推出。

hackernews · zlliang · 10月30日 15:44 · [社区讨论](https://news.ycombinator.com/item?id=50305573)

**「联邦式代码托管的技术前提」** “联邦式代码托管”的技术前提，是让多个可独立托管的实例基于开放协议互操作，而不是要求所有代码集中在一家服务商；Tangled 以 AT Protocol 为协议层，并将议题、拉取请求和评论等协作对象纳入仓库数据模型。外部报道将此次版本描述为从单一瑞典服务器转向边缘索引器的架构重建，因此“自托管仍可跨站协作”并非单纯更换界面，而是此次发布所依托的基础设施与数据模型变化。

**「迁移前需确认的能力」** 对已有 Gitea 或 GitHub 工作流的团队，Tangled 这次发布提供了一条可试验的联邦式协作路径。联合创始人称 AT Protocol 词法已经稳定，全部或部分服务栈均可自托管，组织支持也已上线；但私有仓库仍只是在未来数周推出的计划，涉及私有代码的团队应等待其正式可用后再迁移。Tangled 于 3 月 2 日宣布获得 380 万欧元种子轮，为继续扩张提供资金，但目前尚无广泛采用的证据。

**「社区反馈」** 一名使用自托管 Gitea 的开发者希望迁移代码、发布及可能的 CI，同时保留 GitHub 用于发现和备份，因此认为 git-bug 增加 Tangled 桥接及完善自托管文档会降低迁移门槛；另一位正在开发 juju.bi 的开发者则追问 issue、PR 和评论记录是否会从用户作用域改为仓库作用域，以实现与 Tangled 的互操作。另有用户认为首页信息过密、个人主页活动图过于复杂，偏好 GitHub 或 GitLab 风格的方格活动图。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://tangled.org/blog/forge/">The federated code forge · The Tangled Blog</a></li>
<li><a href="https://news.lavx.hu/article/tangled-rebuilds-federated-forge-on-at-protocol-with-edge-indexer-and-organization-accounts">Tangled rebuilds federated forge on AT Protocol with edge ...</a></li>
<li><a href="https://blog.tangled.org/seed/">Announcing our €3,8M seed round — Tangled&#x27;s Blog</a></li>
<li><a href="https://www.eu-startups.com/2026/03/finlands-tangled-raises-e3-8-million-backed-by-githubs-former-ceo-to-build-a-european-alternative-to-the-us-based-platform/">Finland’s Tangled raises €3.8 million, backed by GitHub’s ...</a></li>

</ul>
</details>

**标签**: `#federated code hosting`, `#AT Protocol`, `#developer tools`, `#self-hosting`, `#code collaboration`

---

<a id="item-tech-news-4"></a>
### [Binance 被指遭 20 分钟执行的 63 亿美元攻击](https://www.wired.com/story/the-dollar63-billion-binance-hack-was-pulled-off-in-just-20-minutes/) ⭐️ 7.0/10

据 Wired 2026 年 10 月 30 日的报道标题及所附摘要，一宗针对 Binance 的攻击据称仅用 20 分钟便完成，涉及 63 亿美元。现有材料没有披露初始入侵、私钥或签名密钥获取、提款路径及损失确认，也没有独立佐证；因此不能把这一数字视为已确认损失，也无法断定攻击是否涉及软件供应链。

hackernews · domhudson · 10月30日 12:50 · [社区讨论](https://news.ycombinator.com/item?id=50303172)

**「事件背景与调查状态」** 报道所称的“20 分钟”是攻击者完成核心操作的时间窗口，而非从侦察、准备到入侵的全过程；多家加密资产追踪公司认为，朝鲜黑客组织 TraderTraitor 可能牵涉其中，但这一归因仍属调查中的判断。Binance 起初称攻击者似乎入侵了一名工程师的笔记本电脑，随后表示调查又发现了“额外的入侵点”；约 63 亿美元的损失规模仍是估算，具体攻击链与最终责任归属当时尚未查清。

**「客户资产与运营响应」** 此次入侵直接波及 Binance 客户资产：Binance 称约 63 亿美元的客户端资产受影响，其中约 30 亿美元已在区块链网络冻结并开始追回部分资金，因此不能仅凭冻结或“资金安全”的通知认定损失已经结清（tool-3-1、tool-3-2）。报道称安全入侵涉及一名工程师的笔记本，受影响用户应依据官方追回进度核验账户状态，交易所运营方则需复核员工端点、签名权限与提币流程的隔离措施（tool-3-2、tool-3-3）。

**「评论聚焦准备时间与平台责任」** 多名评论者认为，20 分钟更可能只是漏洞利用或转账执行阶段，发现目标、设计攻击及准备凭据可能已耗时很久；这是评论者提出的解释，并非报道确认的攻击时间线。另有用户质疑 Binance 转述的“被攻陷的笔记本”与 63 亿美元规模之间的技术联系，认为承诺承担全部损失反而凸显了安全疏忽和监管问题，并将事件时间与 Claude Code 供应链攻击联系起来；这些责任归因和关联均未得到现有材料证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.wired.com/story/the-dollar63-billion-binance-hack-was-pulled-off-in-just-20-minutes/">The $6.3 Billion Binance Hack Was Pulled Off in Just ... - WIRED</a></li>
<li><a href="https://gizmodo.com/how-hackers-stole-6-3-billion-from-binance-in-minutes-2000833158">How Hackers Stole $6.3 Billion From Binance in Minutes - Gizmodo</a></li>
<li><a href="https://www.nytimes.com/2026/10/30/technology/binance-hack-ai-north-korea.html">Binance’s $6.3 Billion Hack Is Just the Start of a Risky New Era</a></li>
<li><a href="https://www.cnbc.com/make-it/2026/10/30/binance-crypto-hack-customer-funds.html">Binance crypto hack : What happens to customer funds on exchanges</a></li>
<li><a href="https://www.ft.com/content/c7f5e395-c3a9-430e-b757-5014527b4d49?syn-25a6b1a6=1">Binance rushes to recover customer money after $ 6 . 3 bn heist</a></li>
<li><a href="https://finance.yahoo.com/personal-finance/investing/article/what-binance-users-should-do-right-now-following-63-billion-hack-152239989.html">What Binance users should do right now following $ 6 . 3 billion hack</a></li>

</ul>
</details>

**标签**: `#cybersecurity`, `#Binance`, `#cryptocurrency exchanges`, `#software supply chain`, `#incident response`

---

<a id="item-tech-news-5"></a>
### [AI 代理是否让 SRE 岗位去技能化](https://newsletter.signoz.io/p/ai-isnt-replacing-sres-its-deskilling) ⭐️ 7.0/10

文章的核心判断是，AI 代理对站点可靠性工程师（SRE）的首要风险不是直接取代岗位，而是让自动化跑在人的学习速度之前：调试和基础设施操作等任务被更快委派出去，工程师却可能因此减少亲手理解复杂系统的机会。文章据此指出，即时生产力提升与长期技能积累之间可能发生冲突；不过现有材料属于观点分析，未提供岗位替代率、性能提升幅度或技能退化的量化结果。讨论的关键因此是自动化效率与保留人类独立排障、动手学习能力之间的取舍。

hackernews · dorianniemiec · 10月30日 15:52 · [社区讨论](https://news.ycombinator.com/item?id=50305693)

**「自动化与实战能力」** 站点可靠性工程（SRE）不仅要求用工具恢复服务，也要求工程师理解数据流、系统瓶颈、日志、架构以及缓解和恢复策略。文章提出的核心问题是：如果 AI 代理承担了 95% 的日常事故响应，工程师是否会因缺少实战练习而更难处理剩余的 5% 关键事故。

**「为 SRE 保留人工演练环节」** 当 AI 代理承担告警分流、事故调查、根因分析和部分修复时，SRE 团队获得更高处理效率的同时，也应保留通过亲手排查形成系统理解的环节，否则遇到代理无法处理的复杂故障时，团队可能面临实践能力不足。HN 评论者以航空业保留手动飞行时长类比，建议即使代理能够处理，也指定部分事件用于人工演练；这是社区提出的实践建议，并非已验证效果。团队可据此将轮岗、模拟演练和事后复盘纳入运维流程，在采用自动化的同时控制技能流失风险。

**「社区争论」** andix 以航空业要求保留手动飞行时间类比，主张即使 AI 有能力处理故障，团队也应指定部分事件作为人类练习机会；jedberg 则认为 Terraform 等自动化并未让 SRE 去技能化，反而能加快检测与修复，并支持更高的“五个九”可靠性。sloob 自述让 Claude 以只读方式访问 AWS 环境、日志、路由表和数据库后，排障可达到手工处理约 10 倍速度；pluc 反驳称 SRE 的核心是理解数据流、瓶颈、SLI、SLO 和故障缓解，而 AI 生成的应用会破坏这种理解，这些均是评论者的经验与立场。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://newsletter.signoz.io/p/ai-isnt-replacing-sres-its-deskilling">AI Isn &#x27; t Replacing SREs . It &#x27; s Deskilling Them .</a></li>
<li><a href="https://www.augmentcode.com/guides/ai-sre-ai-powered-site-reliability-engineering">AI SRE: The 2026 Guide to AI-Powered Site Reliability Engineering</a></li>
<li><a href="https://dev.to/siddharth_singh_409bd5267/ai-sre-the-complete-guide-for-engineering-teams-in-2026-51ba">AI SRE: The Complete Guide for Engineering Teams in 2026</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Site Reliability Engineering`, `#AI-assisted operations`, `#infrastructure automation`, `#engineering skill erosion`

---

<a id="item-tech-news-6"></a>
### [FCC 拟限制中国运营商获取美国号码资源](https://fccid.io/news/fcc-draft-national-security-voip-direct-access-numbering-rules) ⭐️ 7.0/10

美国联邦通信委员会（FCC）10 月 29 日表示，将于 11 月 19 日表决一项国家安全提案，禁止中国移动、中国电信、中国联通及相关 VoIP 服务商直接获取美国电话号码资源，并禁止使用华为、中兴等风险清单设备的服务商获得同类权限。该提案仍待表决，若获通过，限制范围将主要是号码资源直接准入，现有普通国际电话的拨打与接听暂不受影响。三家运营商的相关在美实体此前已被拒绝或撤销美国国际电信业务授权。

telegram · zaihuapd · 10月30日 08:01

**「背景：号码资源准入与既有授权」** 在 FCC 的提案语境中，“直接获取美国电话号码资源”是指运营商或 VoIP 服务商取得直接分配美国号码的资格，并不等同于拨打或接听普通国际电话的权限，因此该措施并非全面切断跨境通话。相关在美实体此前已被拒绝或撤销美国国际电信业务授权；11 月 19 日拟表决的提案是在既有许可审查基础上，进一步以国家安全及防范诈骗骚扰电话为由限制号码资源准入，目前尚未表决通过。

**「直接配号企业须调整号码供应」** 若该提案于 11 月 19 日获 FCC 通过，中国移动、中国电信、中国联通及相关 VoIP 服务商将无法直接从北美号码计划管理员（NANPA）取得美国号码资源，使用华为、中兴等风险清单设备的服务商也将失去直接配号资格。依赖直接配号的 VoIP 运营商需重新安排号码供应路径，并审查多级转售链条的合规责任；现有普通国际电话的拨打和接听暂不受影响，因此受影响的是美国号码资源准入，而非全部中美通话。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/world/asia-pacific/us-plans-ban-chinese-telecom-firms-direct-access-us-phone-numbers-2026-10-30/">US plans to ban Chinese telecom firms from direct access to ...</a></li>
<li><a href="https://www.firstpost.com/world/us-moves-to-block-chinese-telecom-firms-from-direct-access-to-american-phone-numbers-14056577.html">US moves to block Chinese telecom firms from direct access to ...</a></li>
<li><a href="https://www.reuters.com/world/asia-pacific/us-plans-ban-chinese-telecom-firms-direct-access-us-phone-numbers-2026-10-30/">US plans to ban Chinese telecom firms from direct access to ...</a></li>
<li><a href="https://docs.fcc.gov/public/attachments/DOC-416496A1.pdf">FCC Combats Robocallers’ Abuse of Phone Numbering Resources</a></li>
<li><a href="https://docs.fcc.gov/public/attachments/FCC-26-17A1.pdf">Federal Communications Commission FCC 26-17 Before the ...</a></li>

</ul>
</details>

**标签**: `#FCC监管`, `#通信安全`, `#VoIP`, `#中美科技竞争`, `#电信设备`

---

<a id="item-tech-news-7"></a>
### [苹果将在华测试首批 Apple 智能功能](https://www.apple.com.cn/newsroom/2026/10/apple-intelligence-features-are-coming-to-users-in-china/) ⭐️ 7.0/10

苹果宣布，最新 iOS 开发者 Beta 版将于 11 月 4 日起向符合条件的中国用户开放首批 Apple 智能功能测试，包括实时翻译、照片消除和写作工具；这些功能计划随 12 月发布的 iOS 27.3 正式推出。首批功能将接入阿里巴巴千问，覆盖 Siri、写作工具和视觉智能，适用对象包括在中国购买支持 Apple 智能的 iPhone 的用户，以及设备位置和 Apple Account 国家或地区均设置为中国的用户。测试仍处于分阶段开放阶段，其他平台的推出需获得必要审批，此次更新也暂不包含下一代 Siri。

telegram · zaihuapd · 10月30日 21:44

**「分阶段开放背景」** Apple Intelligence 在中国按“开发者 Beta 测试—随 iOS 27.3 正式发布—审批后扩展至其他平台”的节奏分阶段落地，首批范围包括实时翻译、照片消除和写作工具，并接入阿里巴巴千问。此次开放不含下一代 Siri，因此并非 Apple 智能功能的完整上线；可用设备、所在地区及 Apple 账户国家或地区也须符合中国区资格条件。

**「对中国用户的影响」** 中国用户将从 11 月 4 日起通过最新版 iOS 开发者 Beta 版测试实时翻译、照片消除和写作工具，首批功能随后于 12 月随 iOS 27.3 正式推出。功能资格受设备和账户地区条件限制，且仍需等待部分平台审批；本次更新不含下一代 Siri，因此尚不是 Apple 智能功能在中国的完整落地。

**标签**: `#Apple Intelligence`, `#iOS`, `#AI in China`, `#Alibaba Qwen`, `#machine translation`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [SpaceX 最大 AI 算力客户或为 Anthropic](https://www.cls.cn/detail/2519914) ⭐️ 8.0/10

SpaceX 申报文件显示，上季度约 34.5%的营收来自 AI 算力部门的一名单一客户；知情人士称该客户是 Anthropic，但尚未获官方确认。Anthropic 披露的合同显示，其截至 2029 年最多向 SpaceX 支出 1205 亿美元，财联社据此估算自 2026 年 12 月起相当于每月约 31 亿美元；合同上限并非已实现收入。

telegram · zaihuapd · 10月30日 06:20

**「背景」** Anthropic 早前已与 SpaceX 签约使用其孟菲斯数据中心的算力；公司 IPO 申报文件披露，相关算力安排在截至 2029 年的合同期内最高支出 1205 亿美元。

**「影响」** 若“客户 B”确为 Anthropic，SpaceX 上季度已有 34.5%的营收依赖单一 AI 算力客户，而 Anthropic 截至 2029 年的潜在算力采购承诺最高达 1205 亿美元，双方分别面临客户集中和采购成本敞口。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://c.m.163.com/news/a/LA6S4ONO05198NMR.html">史 上 最大IPO来了！ Anthropic 正式提交IPO 申 请， 上 半年净亏损807...</a></li>
<li><a href="https://www.youtube.com/watch?v=EZ25jGlssOI">收 入暴涨14倍、现金流转正！ Anthropic 招股书把 AI ... - YouTube</a></li>
<li><a href="https://www.donews.com/news/detail/1/6756473.html">Anthropic 招股书引发热 议 ：增长不保证，百 亿 亏空有玄机- DoNews</a></li>
<li><a href="https://www.163.com/tech/article/LA82822E00097U7T.html">Anthropic 最 硬气招股书，先把丑话说在前头</a></li>

</ul>
</details>

**标签**: `#Anthropic`, `#SpaceX`, `#AI算力`, `#数据中心`, `#重大商业协议`

---

<a id="item-finance-news-2"></a>
### [苹果将中国台湾地区 App Store 佣金降至 26%](https://developer.apple.com/news/?id=w9mxlhek) ⭐️ 7.0/10

苹果宣布，自 2026 年 10 月 31 日起，中国台湾地区 App Store 的标准 App 内购买及付费 App 交易佣金费率由 30%降至 26%，降幅为 4 个百分点。

telegram · zaihuapd · 10月30日 09:25

**「背景」** 苹果称此次降费是在与当地公平交易委员会讨论后作出，并将自动适用，开发者无需在生效日前签署更新条款。

**标签**: `#Apple`, `#App Store`, `#Taiwan`, `#commission rates`, `#app developers`

---

<a id="item-finance-news-3"></a>
### [DeepSeek 据报完成 1055 亿元融资，估值超 6155 亿元](https://www.theinformation.com/articles/behind-deepseeks-16-billion-funding-chinese-tech-titans-state-players) ⭐️ 7.0/10

据 The Information 报道，DeepSeek 第二轮融资规模达 1055 亿元，估值超过 6155 亿元，腾讯、宁德时代等近 30 家投资方参与。本轮国资背景投资者出资占比约为 27%，明显高于今年 6 月完成的首轮融资中的 2%，但具体估值依据和交易条款尚未披露。

telegram · zaihuapd · 10月30日 12:37

**「融资背景」** 这是 DeepSeek 继今年 6 月完成约 510 亿元首轮融资后的第二轮交易；据 The Information 报道，国资背景投资者在本轮出资占比约为 27%，高于首轮的 2%。

**「融资结构变化」** 据 The Information 披露，DeepSeek 本轮融资中国资背景投资者出资占比约为 27%，明显高于首轮约 500 亿元融资时的 2%；但报道未披露持股和投票权安排，无法判断控制权是否发生变化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theinformation.com/articles/behind-deepseeks-16-billion-funding-chinese-tech-titans-state-players">Behind DeepSeek’s $16 Billion Funding: Chinese Tech Titans ...</a></li>
<li><a href="https://panews.io/articles/01a18bb5-6a9a-7684-979c-d78026298ba4">Details of DeepSeek&#x27;s 105.5 Billion Yuan Funding Round ...</a></li>
<li><a href="https://www.caixinglobal.com/2026-07-17/deepseek-reaches-52-billion-valuation-in-round-backed-by-tencent-catl-102465358.html">DeepSeek Reaches $52 Billion Valuation in Round ... - Caixin Global</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#人工智能融资`, `#战略投资`, `#国资资本`, `#中国科技业`

---

<a id="item-finance-news-4"></a>
### [四家日系车企在华产量降至 2020 年同期峰值四成以下](https://weibo.com/1642634100/Rp6qUwLKa) ⭐️ 7.0/10

据新浪科技报道，2026 年 4 月至 9 月，丰田、本田、日产和马自达在华合计产量约 102 万辆，同比下降 32%，不足 2020 年同期峰期的四成；本田同期产量约 13.2 万辆，同比下降 60%，并计划将在华燃油车年产能从 149 万辆降至 100 万辆。

telegram · zaihuapd · 10月30日 13:38

**「背景」** 报道以 2020 年 4—9 月四家车企在华合计产量为峰值基准；此前丰田 8 月在华销量为 11.84 万辆、同比下降 23%，本田销量已连续 31 个月下滑。

**「产能影响」** 据报道，本田拟把在华燃油车年产能从 149 万辆降至 100 万辆，直接影响是其中国燃油车生产规模将进一步缩减，并可能促使经销与零部件采购安排相应调整。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://post.smzdm.com/p/aggqz776/">思域 月 销1337台、“限 量 版”谣言还在传： 本 田 连跌31...</a></li>

</ul>
</details>

**标签**: `#中国汽车市场`, `#日系车企`, `#汽车产量`, `#产能削减`, `#本田`

---

<a id="item-finance-news-5"></a>
### [美股半导体板块重挫，英特尔跌超 26%](https://www.cls.cn/detail/2521210) ⭐️ 7.0/10

10 月 30 日，美股半导体板块重挫，费城半导体指数单日下跌 5.67%，英特尔跌超 26%，AMD、英伟达及三倍做多半导体 ETF SOXL 也同步大跌；报道未说明下跌原因。

telegram · zaihuapd · 10月30日 13:48

**「背景」** 10 月 26 日，费城半导体指数盘初曾涨超 1.5%，美光科技和闪迪等芯片股涨超 3%，数日后板块转为大幅下跌。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://hk.stockstar.com/IG2026102600038474.shtml">特 斯拉市值飙升5700亿元 美股 半 导 体 、光通信股上涨 Lumentum...</a></li>

</ul>
</details>

**标签**: `#美股`, `#半导体板块`, `#英特尔`, `#市场大跌`

---

