# Horizon 每日速递 - 2026-11-28

> 从 29 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [OpenSec 披露 Linux nfsd 预认证高危漏洞](#item-tech-news-1) ⭐️ 8.0/10
2. [DeepCrossAttention：Transformer 残差连接最高提速 3 倍](#item-tech-news-2) ⭐️ 7.0/10
3. [热门购物站点报告 WebRTC 盗卡脚本](#item-tech-news-3) ⭐️ 7.0/10
4. [多州起诉 SpaceX，指 Grok 生成儿童性影像及非自愿私密影像](#item-tech-news-4) ⭐️ 7.0/10
5. [错误证明如何通过计算机检验](#item-tech-news-5) ⭐️ 7.0/10
6. [SemiAnalysis 深度拆解 Trainium3 推理架构](#item-tech-news-6) ⭐️ 7.0/10
7. [《我的世界》基岩版资源包漏洞已修复](#item-tech-news-7) ⭐️ 7.0/10

**财经新闻**
1. [蜜雪冰城据报出资 5 亿元参与 DeepSeek 融资](#item-finance-news-1) ⭐️ 7.0/10
2. [央行公布大额存单新规](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenSec 披露 Linux nfsd 预认证高危漏洞](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec 称，Linux 内核 nfsd 的预认证堆溢出漏洞 CVE-2026-99362 获 CVSS 9.8 评分；攻击者无需登录，仅需连接 tcp/2049 即可越界写入内核堆并取得 root shell。该漏洞据称自 Linux 3.16 起存在，影响启用 NFSv4.1 或 4.2 的文件服务器、NAS 和集群存储节点，CVE 于 2026 年 11 月 20 日公开。OpenSec 称修复已发布至 Linux 6.12.117、6.18.61、7.3.2 和 7.4-rc1，运维人员应升级内核并重启；无法立即升级时，可通过防火墙限制 tcp/2049 访问。目前材料仅为 Telegram 对 OpenSec 披露的转述，尚无公告原文或独立技术验证。

telegram · zaihuapd · 11月27日 12:57

**「nfsd 预认证漏洞的技术背景」** 理解该漏洞的技术前提是：Linux 的 nfsd 提供 NFS 文件共享服务，受影响部署启用了 NFSv4.1 或 NFSv4.2，客户端通过 TCP/2049 访问文件服务器、NAS 和 Kubernetes 存储节点，因此攻击路径可在 NFS 客户端认证完成前抵达内核。公开漏洞条目还描述了 nfsd4 编码过程中 operation\(\) 提前返回、未继续执行 encode sequence\(\) 的行为；这是公告所述堆溢出的代码层背景，并非对该漏洞可利用性的独立验证。

**「受影响主机需修补并限制 NFS 端口」** OpenSec 称，CVE-2026-99362 可被能够访问 tcp/2049 的远程攻击者用于对启用了 NFSv4.1 或 4.2 的 Linux 主机实施预认证越界写并获取 root；漏洞数据库将其定位在 NFSv4 SEQUENCE 应答处理路径。相关文件服务器、NAS 和集群存储节点应尽快升级至 6.12.117、6.18.61、7.3.2 或 7.4-rc1 并重启内核；暂时无法升级时，应通过防火墙限制 tcp/2049 的访问范围。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS 2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://dbu.gs/vulnerability/PT-2026-151543">CVE - 2026 - 99362 — Vulnerability in Linux Kernel | dbugs</a></li>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://dbu.gs/vulnerability/PT-2026-151543">CVE - 2026 - 99362 — Vulnerability in Linux Kernel | dbugs</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/new-nfs2root-linux-flaw-can-let-attackers-gain-root-privileges/">New NFS2ROOT Linux flaw can let attackers gain root privileges</a></li>

</ul>
</details>

**标签**: `#Linux 内核`, `#NFS`, `#CVE-2026-99362`, `#漏洞修复`, `#网络安全`

---

<a id="item-tech-news-2"></a>
### [DeepCrossAttention：Transformer 残差连接最高提速 3 倍](https://research.google/blog/supercharging-transformer-residual-connections/) ⭐️ 7.0/10

Google Research 介绍了 DeepCrossAttention，一种用于改进 Transformer 残差连接的新方法，并宣称其在保持可比模型质量的同时最高可实现 3 倍速度提升。现有材料未提供测试模型、硬件、基准任务或具体质量指标，也缺少独立验证，因此“3 倍”应视为该方法在特定条件下公布的结果，而非普遍适用的性能结论。

hackernews · ComputedCamp995 · 11月27日 23:06 · [社区讨论](https://news.ycombinator.com/item?id=50672565)

**「DeepCrossAttention 的研究背景」** 传统 Transformer 通过残差连接将子层输出与原表示相加；Google Research 的 ICML 2025 论文《DeepCrossAttention: Supercharging Transformer Residual Connections》专门研究了这种连接机制的局限，并提出 DeepCrossAttention 方案。论文摘要称，该方法在保持模型质量的同时最高可实现 3 倍速度，并称新增开销可忽略；因此这一数字属于论文作者报告的实验结果，而非本条材料提供的独立验证。

**「对模型训练与推理的潜在影响」** 对需要训练或运行 Transformer 的团队，DeepCrossAttention 提供了一条降低计算时间的候选路径：Google Research 称，该方法在保持可比模型质量的同时最高可快 3 倍。因此，实施团队应在自身任务上复测吞吐、延迟和资源消耗，不能将“最高 3 倍”视为所有模型的保证；现有资料也未说明它是否能直接替换现有架构，实施前还需确认集成与评测要求。

<details><summary>参考链接</summary>
<ul>
<li>Supercharging transformer residual connections - Google Research</li>
<li>[PDF] DeepCrossAttention: Supercharging Transformer Residual Connections - arXiv</li>
<li><a href="https://arxiv.org/abs/2502.06785">[2502.06785] DeepCrossAttention: Supercharging Transformer ...</a></li>
<li><a href="https://research.google/blog/supercharging-transformer-residual-connections/">Supercharging transformer residual connections - Google Research</a></li>

</ul>
</details>

**标签**: `#transformers`, `#model-efficiency`, `#deep-learning`, `#google-research`, `#architecture`

---

<a id="item-tech-news-3"></a>
### [热门购物站点报告 WebRTC 盗卡脚本](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

InfoHawk 报道称，热门购物网站上的信用卡盗卡脚本利用了 WebRTC，使网站访客的支付信息面临通过该通道被窃取的风险。现有材料未列出受影响站点、脚本实现、具体 WebRTC 调用、受害者数量或独立验证结果，因此影响范围尚无法确认，也不能据此认定 WebRTC 本身存在新漏洞。事件反映出的主要安全问题更可能是第三方 JavaScript 权限、脚本隔离和支付数据处理不足。

hackernews · scanr · 11月27日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50668145)

**「技术背景」** 2026 年 3 月公开的“WebRTC Skimmer”报告曾描述一种支付盗卡脚本：它利用 WebRTC 数据通道接收载荷并外传数据，以绕过 CSP 等网页安全控制。此次在购物网站中发现使用 WebRTC 的盗卡脚本，延续的是这一类以浏览器通信通道作为外传路径的技术思路，而非 WebRTC 协议本身被攻破。

**「结账页需要隔离第三方脚本」** 对电商、浏览器和支付风控团队，实际后果是第三方脚本一旦进入结账页，就可能监听支付请求中的卡号、有效期和 CVV；Ars Technica 对另一起 Optimizely 第三方脚本事件的报道也记录了这种数据窃取方式。运营方应隔离支付表单与第三方代码、审计结账阶段的异常 WebRTC 和网络外连，并回归测试可能被隔离机制影响的广告、分析及反欺诈脚本；但现有报道未列出受影响站点或规模，无法据此量化波及范围。

**「社区讨论」** 评论者认为，问题并非 WebRTC 独有能力，而是它较少受到安全工具监控；同样的攻击也可能通过普通 HTTP 请求实施，因此根本风险在于网站允许第三方脚本在访客浏览器中运行。另有人主张让浏览器隔离或禁止执行第三方内容中的 JavaScript，但这属于对现有 Web 架构和广告模式的长期改进观点，并非该报道已经验证的解决方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer">Credit card skimming scripts using WebRTC found on popular ...</a></li>
<li><a href="https://thehackernews.com/2026/03/webrtc-skimmer-bypasses-csp-to-steal.html">WebRTC Skimmer Bypasses CSP to Steal Payment Data from E ...</a></li>
<li><a href="https://arstechnica.com/security/2026/11/malicious-code-delivered-through-optimizely-hits-visitors-to-hundreds-of-sites/">Hundreds of websites deliver potent malware cocktail... - Ars Technica</a></li>

</ul>
</details>

**标签**: `#web-security`, `#WebRTC`, `#payment-fraud`, `#third-party-javascript`

---

<a id="item-tech-news-4"></a>
### [多州起诉 SpaceX，指 Grok 生成儿童性影像及非自愿私密影像](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

2026 年 11 月 27 日，多名美国州总检察长对 SpaceX 提起诉讼，要求阻止 Grok 生成和推广儿童性虐待材料及非自愿私密影像。诉状指控 SpaceX 作为 X、xAI 和 Grok 的母公司，未能采取充分措施防止其生成式 AI 服务产出相关违法内容。现有材料未提供案号、具体州数量、受理法院或具体救济请求；相关行为属于原告指控，尚不能视为已经司法确认的事实。

hackernews · DeepLogin · 11月27日 19:42 · [社区讨论](https://news.ycombinator.com/item?id=50670855)

**「诉讼背景」** 弗吉尼亚州总检察长杰伊·琼斯（Jay Jones）与俄勒冈州总检察长丹·雷菲尔德（Dan Rayfield）分别提起了内容相似但彼此独立的诉讼。两地总检察长办公室称，诉状指称 SpaceX 允许 Grok 和 X 平台生成、托管及分享儿童性虐待材料（CSAM）和非自愿私密影像（NCII），且产品缺少必要防护；这些目前仍属诉讼指控，尚未经法院认定。

**「州级诉讼与平台责任风险」** 对 SpaceX、xAI 和 Grok 平台而言，州总检察长起诉意味着风险已具体落到模型生成、平台推广以及 CSAM 法下的平台责任和潜在处罚，而不只是常规内容下架；现有材料只证明诉讼及指控，尚不能确认 Grok 已被裁定违法、收到禁令或完成整改（tool-3-2）。由于 xAI 已在 2026 年 7 月就明尼苏达州禁止“脱衣”技术的法律起诉州政府，平台还需考虑同步采取加强防护以合规和挑战相关州规合宪性两条路径（tool-3-1）。

**「社区讨论」** 一名评论者质疑此类内容为何未被普遍禁止，以及用户是否需要通过特定提示词“绕过”限制；另一名评论者主张应追究实际制作者而非平台。第三名评论者声称美国最高法院已认定个人使用 AI 制作儿童性虐待材料属于受保护言论，但排除涉及真实儿童等情形，并认为这一区分可能适用于涉及真实人物的报复色情内容；该法律主张在现有材料中未经核实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.doj.state.or.us/media-home/news-media-releases/ag-rayfield-takes-legal-action-against-grok-for-failing-to-block-child-exploitation/">Oregon Attorney General Rayfield and Virginia Attorney ...</a></li>
<li><a href="https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform">Attorneys General Jones and Rayfield File Suit Against SpaceX ...</a></li>
<li><a href="https://www.theguardian.com/technology/2026/jul/29/xai-sues-minnesota-nudification-technology">Elon Musk’s xAI sues Minnesota over law banning... | The Guardian</a></li>
<li><a href="https://factually.co/fact-checks/technology/grok-csam-investigations-b0a6c9">grok csam investigations</a></li>

</ul>
</details>

**标签**: `#AI safety`, `#Grok`, `#generative AI`, `#content moderation`, `#AI regulation`

---

<a id="item-tech-news-5"></a>
### [错误证明如何通过计算机检验](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

该页面分析证明检查器的健全性漏洞如何导致错误的形式化证明被计算机接受，并讨论由多个独立实现的验证器交叉检验以降低风险。讨论涉及 Lean、Metamath 等系统，但现有材料未列出具体漏洞编号、触发条件或可复现实例，因此不能据此认定这些检查器普遍不可靠。

hackernews · \_tk\_ · 11月27日 15:26 · [社区讨论](https://news.ycombinator.com/item?id=50667989)

**「背景」** 计算机检验证明依赖证明检查器逐步重放形式化推导：只有每个推导步骤都符合系统的公理和规则，所声称的结论才会被接受。所谓“健全性漏洞”是检查器错误接受无效步骤的缺陷；据该页面汇总，此类漏洞已有报告，并可能使错误陈述通过检查。

**「对形式化验证与高保证软件的影响」** CVE-2026-72844 暴露出 Lean 4 内核的健全性漏洞：检查器一旦接受不成立的证明，其上构建的形式化验证保证就会受损。因此，采用 Lean 的组织应核对受影响版本并采用修复版本，其中包括 AWS 使用 Lean 验证 Cedar 授权策略语言的项目。关键证明可由实现独立的检查器交叉验证，但 nanoda 在 Lean Kernel Bug \#14576 中也曾因独立的投影节点验证漏洞漏过无效证明，说明多检查器流程还必须分别审计每个实现及其版本，不能把第二个检查器视为无条件可靠的安全网。

**「单一漏洞是否足以造成误导」** dwheeler 认为文章若让人以为一个 Metamath 检查器的漏洞就足以污染主证明库，会造成误导；他称 set.mm 和 iset.mm 的收录流程要求五种语言中五个独立实现的验证器全部通过。twotwotwo 进一步指出，要真正误导数学家往往需要多个检查器同时存在漏洞，且证明表面上看不出异常；gr\_norm 认为此类漏洞总体稀少，而 andai 提醒检查器之外的规格理解错误也可能导致“正确证明了错误目标”。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer - checked proofs (djb)</a></li>
<li><a href="https://www.openwall.com/lists/oss-security/2026/10/26/2">oss-security - CVE-2026-72844: Lean 4 kernel soundness bug...</a></li>
<li><a href="https://lean-lang.org/">Lean Programming Language</a></li>
<li><a href="https://aitoolly.com/ai-news/article/2026-08-02-lean-kernel-soundness-bug-14576-postmortem-of-the-ai-assisted-collatz-conjecture-disproof-and-fix">Lean Kernel Bug #14576: Postmortem and Technical Analysis | AIToolly</a></li>

</ul>
</details>

**标签**: `#formal verification`, `#proof assistants`, `#software correctness`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-6"></a>
### [SemiAnalysis 深度拆解 Trainium3 推理架构](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis 发布针对 AI 推理团队的技术拆解与测试：AWS Trainium3 以 tile 为核心计算单元，其 Descriptor Generation Engines（DGE）被作者视为英伟达 TMA 和 AMD MI455X TDM 的对应机制；其微基准称，Trainium3 能在较小消息尺寸下达到峰值 HBM 带宽利用率，而英伟达 GPU 无法做到。UBenchX/InferenceX 覆盖了 SRAM scratchpad 的周期级延迟与带宽、机架级带宽与延迟、注意力指数测试，以及不同模型形状和 head\_dim 对 roofline 达成率的影响，但这些结果来自 SemiAnalysis 自身测试及 AWS 架构团队协助验证的环境，并非独立认证。文章还称，Trainium3 PDS 配合 vLLM 在真实编码代理会话回放中，除 Vera Rubin 外，在“总拥有成本与 p90 交互延迟”曲线上优于其他加速器；Trainium3 和 TPU 在单 token 生成成本上也可与英伟达 GB300 竞争或胜出，但实际迁移效果仍取决于模型与工作负载。

rss · Semianalysis · 11月27日 15:54

**「背景」** Trainium 早期面临的主要障碍之一是软件适配与成熟度；本文作者认为，随着 Trainium3 配合 PDS 和 vLLM，这一问题已明显缓解。Horizon 10 月 24 日的摘要曾报道，AWS Neuron 正将训练栈迁至原生 PyTorch，并支持 eager mode、torch.compile 和标准 API，但当时其成熟度仍远不及 CUDA，这构成了理解本文软件进展的直接前序背景。

**「部署影响」** 对需要降低推理总拥有成本的团队，Trainium3 已可作为英伟达 GPU 之外的实际部署候选：AWS Trainium3 UltraServers 已宣布可用，而 SemiAnalysis 的 AgentX 通过回放真实编码代理会话测试了 Trainium3 PDS + vLLM 组合，报告称除 Vera Rubin 外，该组合在所测 TCO 与 p90 交互延迟曲线上优于其他加速器。迁移前仍应以自身模型、上下文长度和延迟 SLO 复测，因为这一结论限于 InferenceX/AgentX 工作负载，且测试采用了 PDS + vLLM 软件路径。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://newsletter.semianalysis.com/p/amazons-trainium-takes-a-strike-at">2026-10-24 — Trainium 转向原生 PyTorch 训练</a></li>
<li><a href="https://www.linkedin.com/posts/apiyer_trainium3-ultraservers-now-available-enabling-activity-7401674243283025920-_sef">Trainium 3 Delivers 4x Faster AI Training and 50% Cost ... | LinkedIn</a></li>

</ul>
</details>

**标签**: `#AWS Trainium3`, `#AI inference`, `#microarchitecture`, `#AI accelerators`, `#machine learning hardware`

---

<a id="item-tech-news-7"></a>
### [《我的世界》基岩版资源包漏洞已修复](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

据报道，《我的世界》基岩版存在资源包安全漏洞：包含 content.zipe 的资源包可篡改游戏界面框架 Ore UI 的文件并执行隐藏脚本。附加组件开发者 8Crafter 于 11 月 15 日在 Reddit 披露称，已确认该问题影响 26.52 至 26.63 版本，更早版本也可能受影响；漏洞覆盖 PC、手机和主机，但 Java 版不受影响。当玩家加入服务器或 Realm 并启用资源包自动下载时，无需手动安装也可能收到相关文件；报告列出的后果包括删除全部存档、收集玩家 IP，以及在 Windows 的特定条件下无提示调用任意 URI，并通过资源包内的批处理文件下载恶意软件。Mojang 据称已在 26.65 版修复该问题；AxmBro 另发布了 Windows 只读检测工具，可查找 content.zipe，但不能判断资源包是否恶意。

telegram · zaihuapd · 11月27日 18:04

**「背景：与此前 Java 版资源包漏洞是两条不同攻击链」** Horizon 2026 年 11 月 26 日的日报曾报道过另一条独立的资源包攻击链：minecraft2shell 项目指出，恶意服务器资源包中的特制 TrueType 字体可触发 FreeType 2.14.3 及更早版本的原生越界写，从而在 Windows 客户端实现任意代码执行，当时列出的受影响范围为 Java 版 1.20.5 至 1.21.10 及 26.1 至 26.4 快照，并称 1.20.4 及更早版本和基岩版均不受影响。此次基岩版问题并不依赖字体解析，而是利用资源包中的 content.zipe 改写 Ore UI 界面框架文件并执行隐藏脚本，属于与前述漏洞不同的另一条攻击链。外部检索结果亦印证，附加组件开发者 8Crafter 于 11 月 15 日公开该问题后，Mojang 才以 26.65 热修复的形式修补。

**「影响与应对」** 基岩版 26.52–26.63 的 PC、手机和主机用户若在加入服务器或 Realm 时开启资源包自动下载，无需手动安装也可能下载并加载恶意资源包；已报告的后果包括删除全部存档和收集玩家 IP，Windows 在特定条件下还可无提示打开任意 URI，并通过资源包内的批处理文件下载恶意软件。用户应升级至已修复该问题的 26.65；更早版本可能受影响但范围尚未完全确认，Java 版则不受影响。AxmBro 的 Windows 只读工具可查找 content.zipe，却不能判断资源包是否恶意，因此只能辅助排查，不能代替升级和安全处置。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/bikini/minecraft2shell">2026-11-26 — minecraft2shell 披露 Minecraft Java 版资源包 RCE 风险</a></li>
<li>Minecraft Bedrock: Mojang patches resource pack security hole</li>
<li>Resource packs can contain malware now : r/ibxtoycat - Reddit</li>
<li>Minecraft Bedrock had a serious security flaw that could allow malware to spread through ... - X</li>
<li>Mojang Patches Bedrock After Community Discovers Resource Packs Could Execute Malicious Code - Tech Times</li>

</ul>
</details>

**标签**: `#Minecraft`, `#security vulnerability`, `#resource packs`, `#malware`, `#cross-platform security`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [蜜雪冰城据报出资 5 亿元参与 DeepSeek 融资](https://m.sohu.com/a/1107027659_115479) ⭐️ 7.0/10

据搜狐报道，DeepSeek 完成新一轮融资，规模为 1000 亿至 1055 亿元、投后估值约 6155 亿元；蜜雪冰城通过天津砺思星深基金认缴 5 亿元，本轮新增 31 名出资人。

telegram · zaihuapd · 11月27日 06:33

**「背景」** 据此前报道，DeepSeek 首轮融资于 4 月启动、6 月完成交割，以超 3500 亿元估值募集 500 亿元；受首轮额度限制，大量意向投资方转而参与后续轮次。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.php.cn/faq/2947867.html">消息称 DeepSeek 重启 第 二 轮 500 亿 元 融 资 投前估值升 至 5000...</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#人工智能`, `#股权融资`, `#蜜雪冰城`, `#风险投资`

---

<a id="item-finance-news-2"></a>
### [央行公布大额存单新规](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

中国人民银行 11 月 27 日公布新规，个人认购大额存单的起点金额由 20 万元降至 10 万元，机构由 1000 万元降至 500 万元，新规将于 2027 年 3 月 21 日起施行。

telegram · zaihuapd · 11月27日 11:36

**「监管背景」** 新办法将废止 2015 年的《大额存单管理暂行办法》和 2016 年第 13 号公告，并要求金融机构自主确定存贷款利率，不得通过高息揽储等不正当手段吸收存款。

**「影响范围」** 个人和机构参与大额存单所需的资金门槛均减半，银行自主定价空间扩大，但高息揽储行为将受到明确限制。

**标签**: `#中国人民银行`, `#大额存单`, `#存款利率`, `#银行监管`

---

