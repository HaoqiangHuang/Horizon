---
layout: default
title: "Horizon Summary: 2026-11-17 (ZH)"
date: 2026-11-17
lang: zh
---

> 从 41 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [vLLM v0.34.0 默认启用可扩展 KV 缓存](#item-tech-news-1) ⭐️ 8.0/10
2. [报道称 Optimizely 被入侵并向 Zoom、GitLab 投放恶意代码](#item-tech-news-2) ⭐️ 8.0/10
3. [CMU 免费发布整套计算机科学课程](#item-tech-news-3) ⭐️ 7.0/10
4. [Jiff 1.0：Rust 日期时间库稳定版](#item-tech-news-4) ⭐️ 7.0/10
5. [微软称 7 月修复引入缺陷导致邮件服务中断](#item-tech-news-5) ⭐️ 7.0/10
6. [摩根大通相关技术故障拖累多家美国银行网银](#item-tech-news-6) ⭐️ 7.0/10
7. [Marimba 以单次 Qwen3-ASR 编码统一多项语音任务](#item-tech-news-7) ⭐️ 7.0/10
8. [Artex 驱动 AI 代理窃取 API 密钥](#item-tech-news-8) ⭐️ 7.0/10
9. [美国将先进 AI 芯片管制延伸至远程访问](#item-tech-news-9) ⭐️ 7.0/10
10. [苹果中国区 App Store 新增 AIGC 合规必填项](#item-tech-news-10) ⭐️ 7.0/10

**财经新闻**
1. [英特尔及两名高管遭股东集体诉讼](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [vLLM v0.34.0 默认启用可扩展 KV 缓存](https://github.com/vllm-project/vllm/releases/tag/v0.34.0) ⭐️ 8.0/10

vLLM v0.34.0 发布，新增 Mistral Large 4、MiniMax-M3.1-Flash、Nemotron-3.5-Transcribe 等 10 种模型支持，并在 CUDA 和 ROCm 上默认启用可扩展 KV 缓存；缓存容量改为根据 CUDA Graph 捕获和预热后的实际空闲显存计算。GPU 端现仅保留 Model Runner V2，V1 已删除；项目发布说明报告了 Blackwell 和 MI355X 上最高 1.95 倍的解码提升等基准结果，但这些属于项目方数据，并非独立测量。该版本包含多项破坏性变化：默认块大小从 16 改为 64，\`gpu\_memory\_utilization\` 默认值变为 1.0，ROCm 7.2 制品停止发布，并要求 \`huggingface\_hub &gt;= 2.0.0\`。

github · khluu · 11月16日 23:22

**「升级背景」** 此前的 vLLM GPU 执行路径包含 Model Runner V1，KV 缓存按预留显存的估算值配置，默认块大小为 16。此次升级以 Model Runner V2 取代旧路径，并在预热后按真正可用的显存扩大缓存，例如发布说明称 MiniMax-M3 在 H200 上的容量可从 43.3 万增至 67.2 万 token。

**「升级影响」** 现有部署升级前需要删除会使启动失败的 \`VLLM\_USE\_V2\_MODEL\_RUNNER=0\`，迁移 V1 logits processors，并按需通过 \`--block-size 16\`、\`--gpu-memory-utilization 0.9\` 或 \`--no-enable-extensible-kv-cache\` 恢复旧行为；ROCm 用户须改用 ROCm 10.0，同时升级至 \`huggingface\_hub &gt;= 2.0.0\`、\`tokenizers &gt;= 0.23.3\` 和 \`timm &gt;= 1.0.30\`。新缓存策略并非无条件提速：发布说明称，在部分 H200 模型并发数为 128 时，TPOT 反而增加 6%–18%，因此服务方应针对自身工作负载压测后再决定是否关闭该功能。

**标签**: `#vLLM`, `#LLM inference`, `#model serving`, `#GPU acceleration`, `#release engineering`

---

<a id="item-tech-news-2"></a>
### [报道称 Optimizely 被入侵并向 Zoom、GitLab 投放恶意代码](https://blog.report-uri.com/worlds-largest-brands-infected-with-malware-via-optimizely/) ⭐️ 8.0/10

据报道，Optimizely 的客户端脚本基础设施遭入侵，攻击者得以向包括 Zoom 和 GitLab 在内的多个下游网站和服务投放恶意代码。现有材料未说明初始入侵方式及受影响客户的完整范围，也不能据此确认所有访问者均已感染；此次供应链事件的调查仍未完成。

hackernews · kristjansson · 11月16日 23:00 · [社区讨论](https://news.ycombinator.com/item?id=50524767)

**「客户端脚本供应链风险」** Optimizely Web 会把第三方 JavaScript 嵌入客户网站；此次恶意代码被写入 188 个项目片段后，又经 Optimizely 自有 CDN 使用有效证书分发至 178 家机构，因此客户服务器本身并未显示被攻陷。报道指出，这不是 CDN 缓存投毒，而是 CDN 如实交付了被篡改的项目内容；攻击者如何获得跨客户写入权限，仍无法确定是 Optimizely 系统被攻陷、凭据被盗还是其他途径。

**「下游站点需排查浏览器端风险」** 影响首先落在受影响站点的访客浏览器：多家报道显示，恶意 JavaScript 通过 Optimizely Web 在 Zoom、GitLab、BBC、CNN、HSBC 等站点运行，其中一份统计称涉及 178 家组织。站点运营方应检查 Optimizely 脚本及其加载链、审计浏览器端数据访问，并确认是否有凭据或其他敏感数据被恶意代码获取；现有发现证明的是网站脚本遭植入，不能据此认定这些组织的内部系统也已遭入侵。

**「评论者讨论第三方脚本风险」** 评论者认为，Google Tag Manager 等工具允许营销团队绕过工程团队直接修改网页脚本，在提高运营灵活性的同时放大了第三方代码风险；有人主张采用分阶段发布、权限制衡、内部冷静期和自动安全检查来降低类似事件的影响。另有评论者建议使用 NoScript 等浏览器控制工具减少执行潜在恶意内容，但这些属于防御建议，并非已证实能够完全阻断此次攻击。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://shiftdelete.net/en/optimizely-malware">Optimizely Malware Hit 178 Sites: What It Stole and What to Do</a></li>
<li><a href="https://blog.tmcnet.com/blog/rich-tehrani/msp/optimizelys-trusted-script-hit-178-companies-visitors-your-vendors-vendor-is-now-your-attack-surface.html">Optimizely’s Trusted Script Hit 178 Companies’ Visitors. Your ...</a></li>
<li><a href="https://gizmodo.com/sprawling-malware-attack-reportedly-affects-zoom-cnn-fox-news-peacock-and-170-others-2000840831">Sprawling Malware Attack Reportedly Affects Zoom, CNN, Fox ...</a></li>
<li><a href="https://shiftdelete.net/en/optimizely-malware">Optimizely Malware Hit 178 Sites: What It Stole and What to Do</a></li>
<li><a href="https://uknip.co.uk/news/uk/uk-news/optimjack-cyberattack-bbc-cnn-zoom-optimizely-178-organisations-2/">OPTIMJACK cyberattack hits BBC, CNN, Zoom and 178 organisations</a></li>

</ul>
</details>

**标签**: `#supply-chain security`, `#malware`, `#JavaScript`, `#CDN security`

---

<a id="item-tech-news-3"></a>
### [CMU 免费发布整套计算机科学课程](https://www.cs.cmu.edu/learn/) ⭐️ 7.0/10

卡内基梅隆大学推出 CS Learn，在 YouTube 免费发布该校当前计算机科学课程的整学期讲座，首周每天上线一门课程。首批内容涵盖概率与计算、机器学习系统等主题，其中 Tianqi Chen 的“机器学习系统”课程受到学习者关注；CMU 计划于 2026 年 1 月继续开放更多课程。

hackernews · pcompeau · 11月16日 20:43 · [社区讨论](https://news.ycombinator.com/item?id=50522980)

**「此前的在线教学基础」** CMU 此前已通过 CMU CS Academy 提供基于图形化环境、以 Python 教学的在线计算机科学课程，为此次向公众开放大学课程资源奠定了既有基础。此次 CS Learn 新提供的是完整学期的课程讲座；项目负责人尚未说明作业和指定阅读是否也会公开，相关问题在评论中仍未得到答复。

**「对学习者的直接影响」** 学习者可免费在 YouTube 观看卡内基梅隆大学当前课程的整学期讲座，首批课程在发布周每天上线一门，更多课程计划于 1 月推出。不过公告目前只承诺发布视频，未说明是否同时开放作业、练习或答案，因此自学者不应默认其材料完整度等同于包含大纲、讲义、作业和答案的 MIT OpenCourseWare。

**「学习者关心课程范围与作业开放」** 学习者希望后续能覆盖 15-122、15-150、15-151、15-251 和 15-451 等核心课程，并询问是否会同时公开作业和习题；一名评论者认为，掌握基础知识能让 AI 成为增效工具，但这是个人观点而非项目方承诺。多位 CMU 校友和学习者对开放“机器学习系统”和“概率与计算”课程表示欢迎，并提出分布式系统、操作系统等后续课程请求。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://academy.cs.cmu.edu/">CMU CS Academy</a></li>
<li><a href="https://www.youtube.com/@mitocw">MIT OpenCourseWare - YouTube</a></li>

</ul>
</details>

**标签**: `#computer science education`, `#open courseware`, `#online learning`, `#machine learning systems`

---

<a id="item-tech-news-4"></a>
### [Jiff 1.0：Rust 日期时间库稳定版](https://burntsushi.net/jiff/) ⭐️ 7.0/10

Jiff 1.0 已发布，成为 Rust 生态中的一个稳定日期时间库版本，重点是谨慎处理日期与时间。项目明确承认 Jiff 并不适合所有场景，部分需求仍应选择其他库；现有材料未提供具体 API、兼容性范围或性能数据。讨论集中在 API 设计、兼容性以及是否支持更专门的时间尺度。

hackernews · burntsushi · 11月16日 16:53 · [社区讨论](https://news.ycombinator.com/item?id=50519744)

**「Jiff 1.0 的设计基础」** Jiff 的核心定位是为 Rust 提供偏高层、强调“难以误用”的日期时间原语；其官方仓库和文档列出的能力包括接入时区数据库、夏令时感知的运算与舍入，以及时区感知时间的无损格式化与解析。达到 1.0 意味着这些 API 获得正式的稳定性承诺，依赖者因此可以将接口兼容性纳入长期集成评估。

**「采用与升级安排」** Rust 开发者现在可以将稳定版 Jiff 1.0 用于日期时间处理；现有 Jiff 0.2 用户仍会获得为期一年的关键错误修复，但 0.2 将停止活跃的功能开发，因此应提前规划升级。

**「社区讨论」** quodlibetor 表示，他维护 Chrono 约五年后因长期看不到 API 改进路径而倦怠退出，并认为稳定的既有 API 反而是 Chrono 更受欢迎的重要原因。Dagonfly 认可项目不试图包揽所有时间需求的做法，ddahlen 则询问 Jiff 对 TAI、UT1 以及超大时间尺度等特殊场景的支持。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/BurntSushi/jiff">GitHub - BurntSushi/jiff: A datetime library for Rust that ...</a></li>
<li><a href="https://docs.rs/jiff/latest/jiff/">jiff - Rust - Docs.rs</a></li>
<li><a href="https://elsolitario.org/en/2026/11/16/jiff-1-0-rust-datetime-library/">Rust Datetime Library: Jiff 1.0 Explained - elsolitario.org</a></li>
<li><a href="https://burntsushi.net/jiff/">A datetime library for Rust - Andrew Gallant&#x27;s Blog</a></li>
<li><a href="https://github.com/BurntSushi/jiff">GitHub - BurntSushi/ jiff : A datetime library for Rust that encourages...</a></li>

</ul>
</details>

**标签**: `#Rust`, `#datetime`, `#library-release`, `#time-handling`

---

<a id="item-tech-news-5"></a>
### [微软称 7 月修复引入缺陷导致邮件服务中断](https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026) ⭐️ 7.0/10

微软将一次大规模邮件服务中断归因于 7 月修复中引入的软件缺陷，即此前的修复操作造成了回归。报道将事件视为变更管理、回滚预案和服务韧性的案例，相关讨论集中在部署验证、容量管理及高负载下的优雅降级。现有材料未披露受影响用户范围、中断时长、具体组件或独立复现结果，因此这仍是微软提出的故障归因，而非已获独立验证的结论。

hackernews · Bender · 11月16日 13:18 · [社区讨论](https://news.ycombinator.com/item?id=50517321)

**「此前对故障原因的初步判断」** 11 月 13 日和 14 日的日报将此次 Microsoft 365 中断描述为 Exchange Online 部分服务器意外不可用、进而加重其余基础设施负担的“服务器问题”，当时尚未公布具体代码诱因。此次归因因此是同一故障的后续说明：微软把此前笼统的服务器故障具体化为由 7 月修复引入的软件缺陷。

**「生产环境容量验证成为关键」** 微软的初步事后报告称，7 月变更引入的缺陷是在流量激增且容量下降时触发，事故使全球数百万用户一度无法使用 Outlook 邮件和 Teams 会议等服务。因此，Microsoft 365 运维团队应确保发布前测试覆盖生产规模的并发负载与容量下降场景，并为类似变更保留可快速回滚的方案。

**「社区质疑测试与降级机制」** 有评论者质疑，系统为何不能通过限制连接、轮换放行部分客户端等方式主动卸载负载，并建议在恢复过程中采用渐进式接入；另一名评论者认为，较低规格的测试环境与生产环境存在差异，可能掩盖了并发缺陷。上述内容属于社区提出的设计意见，材料并未证明微软当时已经实施这些措施。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/">2026-11-14 — Microsoft 365 核心服务全球宕机超 12 小时</a></li>
<li><a href="https://www.cnbc.com/2026/11/12/microsoft-outage-outlook-aws-google.html">2026-11-13 — 微软服务器故障导致 Outlook 与 Teams 中断</a></li>
<li><a href="https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026">Microsoft blames monster email outage on software defect ...</a></li>
<li><a href="https://www.cnn.com/2026/11/12/tech/microsoft-outage-cripples-office-workers-nationwide">Massive Microsoft outage disrupts businesses, schools and ...</a></li>

</ul>
</details>

**标签**: `#Microsoft`, `#email outage`, `#software defect`, `#change management`, `#service reliability`

---

<a id="item-tech-news-6"></a>
### [摩根大通相关技术故障拖累多家美国银行网银](https://apnews.com/article/bank-outage-chase-wells-fargo-truist-50fee2693c22f597fa6ca51a97ef2cda) ⭐️ 7.0/10

一项与摩根大通（JPMorgan Chase）相关的技术问题导致美国多家银行的在线银行服务出现延迟，影响不再局限于单家银行机构。现有材料没有确认根因；云平台、数据库以及 COBOL、CICS、IMS、DB2 等传统主机技术栈均只是讨论中的候选解释，不能据此认定事故源于 AWS、Google Cloud 或银行核心系统。材料也未给出完整的受影响银行清单、恢复时间或服务恢复进度。

hackernews · samk3nny · 11月16日 18:31 · [社区讨论](https://news.ycombinator.com/item?id=50521045)

**「共享依赖导致跨行故障外溢」** 美国多家银行的在线服务可能因共享依赖而出现“故障外溢”：同一技术问题先出现在 JPMorgan Chase，随后表现为 Wells Fargo、Bank of America 等机构的客户访问困难。Chase 已向媒体确认问题并非网络攻击，但现有报道尚未确认具体根因，因此不能断定故障来自云平台、数据库或主机系统中的某一项。

**「多家银行客户无法正常访问线上服务」** 此次故障的影响不限于 Chase：TIME 报道称，数千名客户无法正常访问多家美国大型银行的线上服务；用户报告涉及 Bank of America、Chase/J.P. Morgan、U.S. Bank、Wells Fargo 和 Zelle。客户在服务恢复前应准备使用银行仍可用的替代渠道处理账户访问和支付相关操作，并避免反复提交可能重复的交易。

**「社区讨论」** 评论者对根因存在明显分歧：有人以此前持续约 12 小时、被其归因于 Google Cloud 的 Revolut 故障作类比，猜测数据库或云服务可能是诱因；也有人认为银行核心流程更可能依赖 COBOL、CICS、IMS、DB2 等老旧但可靠的主机栈。一名用户称其从西海岸测试的五项服务中有三项可正常加载，并怀疑东海岸 AWS 或自身 WireGuard 连接存在异常，但这只是个人观察，不能证明此次事故的技术原因。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.usnews.com/news/business/articles/2026-11-16/customers-at-some-of-the-nations-largest-banks-are-reporting-difficulty-accessing-accounts-online">A Technical Issue at JPMorgan Chase Triggers Online Banking ...</a></li>
<li><a href="https://www.usatoday.com/story/money/2026/11/16/bank-outage-nationwide-chase-bofa--live/92814152007/">Banking outage linked to Chase, impacted Wells Fargo and BofA</a></li>
<li><a href="https://chicago.suntimes.com/business/2026/11/16/a-technical-issue-at-jpmorgan-chase-triggers-online-banking-delays-across-major-us-banks">A technical issue at JPMorgan Chase triggers online banking ...</a></li>
<li><a href="https://www.usatoday.com/story/money/2026/11/16/bank-outage-nationwide-chase-bofa--live/92814152007/">Banking outage linked to Chase, impacted Wells Fargo and BofA</a></li>
<li><a href="https://time.com/article/2026/11/16/bank-outage-down-jpmorgan-chase-technical-issue/">What to Know About the Banking Service Outages - TIME</a></li>
<li><a href="https://www.wpri.com/money/customers-u-s-banks-difficulty-accessing-accounts-online/">Technical issue at JPMorgan Chase triggers online banking ...</a></li>

</ul>
</details>

**标签**: `#banking outage`, `#infrastructure resilience`, `#cloud systems`, `#legacy systems`, `#financial technology`

---

<a id="item-tech-news-7"></a>
### [Marimba 以单次 Qwen3-ASR 编码统一多项语音任务](https://www.reddit.com/r/MachineLearning/comments/1xxsqro/marimba_a_system_one_model_for_speech_r/) ⭐️ 7.0/10

Marimba 公开了完整论文、代码仓库、采用 Apache-2.0 许可的权重和 Hugging Face 演示，并可用“pip install marimba-audio”安装；该系统用冻结的 Qwen3-ASR-0.6B 编码器对每个 8 秒音频窗口只运行一次，再由任务专用评分返回校准概率，覆盖术语检测、语言识别、轮次结束、说话人变化和说话人数。术语检测对解码器的贪心假设和 4-beam 假设打分后进行 Platt 校准，语言识别使用 ASR 自带的语言分数，轮次结束读取第 18 层，说话人任务读取第 12 层。作者在论文中报告，Marimba 在同一组 1,000 道公开题中的 9 项测试里有 6 项达到或超过 Qwen3-Omni（30B-A3B），但在 Speech Commands 上仍弱于后者；此外，其在 300 段 FLEURS 音频上的语言识别率为 100%，在 AMI 和 VoxConverse 上的说话人变化 AUROC 为 0.966—0.980、高于 ECAPA，说话人计数也优于 pyannote 3.1。不过，轮次结束读出头使用 Smart Turn 数据训练，因此该结果属于同分布评测：Marimba 在 Smart Turn 自测集上的 AUROC 为 0.930，低于 Smart Turn v3.2 的 0.982；在 ICSI 上两者分别为 0.716 和 0.712，接近持平，而在 CochlScene 未见任务的场景分类中，各任务头均降至随机水平。

reddit · r/MachineLearning · /u/solanotodesch · 11月16日 15:47

**「技术基础」** Marimba 建立在 Qwen3-ASR-0.6B 的冻结特征之上；Qwen3-ASR 是 Qwen 团队开源的 ASR 系列，覆盖多语种语音、音乐与歌曲识别、语言检测和时间戳预测。其关键思路是复用每个 8 秒窗口的一次 ASR 编码：词汇问题对转写候选进行零样本打分并校准，其他问题使用任务特定的读出层，其中轮次结束检测单独读取第 18 层特征。

**「对语音应用开发的影响」** 对语音应用开发者，Marimba 可让同一段音频在一次冻结的 Qwen3-ASR-0.6B 编码后，同时支持术语检测、语言识别、轮次结束、说话人变化与计数，减少为不同任务部署独立模型的集成负担；其 Apache-2.0 权重和 \`pip install marimba-audio\` 安装包也便于直接复现。不过，“9 项测试中 6 项持平或优于 Qwen3-Omni”是论文方的报告结果，且轮次结束评测使用了 Smart Turn 训练数据、场景分类在 CochlScene 上处于随机水平，因此团队在采用前仍需用自身领域数据验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.18330">[2611.18330] Marimba: A System One Model for Speech - arXiv.org</a></li>
<li><a href="https://github.com/QwenLM/Qwen3-ASR">GitHub - QwenLM/Qwen3-ASR: Qwen3-ASR is an open-source series ...</a></li>

</ul>
</details>

**标签**: `#speech-language models`, `#Qwen3-ASR`, `#speaker recognition`, `#model calibration`, `#efficient inference`

---

<a id="item-tech-news-8"></a>
### [Artex 驱动 AI 代理窃取 API 密钥](https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/) ⭐️ 7.0/10

亚马逊称，攻击者利用开源渗透测试框架 Artex 驱动 AI 代理，针对公网暴露的 LiteLLM、Dify 等应用窃取 API 密钥，验证后将其汇入共享池，用于支付更多的大模型调用。相关活动自 10 月 3 日开始，11 月 5 日被亚马逊的 MadPot 诱捕网络发现并阻断。亚马逊仅以中等信心将此次行动归因于中国相关威胁组织，并表示并非所有被列目标都已失陷，已通知可能受影响的 AWS 客户；现有披露未提供具体受害规模或更详细的技术证据。

telegram · zaihuapd · 11月16日 13:00

**「“自供血”攻击链」** 这里的“自供血”是指攻击者从公网暴露的 LiteLLM、Dify 等 AI 应用中窃取并验证 API 密钥，再将其投入共享池，用于支付更多大模型调用；风险因此不仅是凭据泄露，还包括被盗密钥可持续支持 AI 代理运行。Artex 是用于驱动这一自动化攻击的开源渗透测试框架，而 MadPot 是亚马逊发现并阻断相关活动的诱捕网络。

**「暴露实例需轮换密钥并排查调用」** 公网暴露 LiteLLM、One API、Dify 等应用的运维方面临模型提供商 API 密钥被盗及后续调用计费风险，因为攻击者会验证窃得的密钥并将其投入共享池。相关组织应检查异常模型调用、轮换可能泄露的密钥并修补已知入口；亚马逊表示已通知可能受影响的 AWS 客户，但并非所有被列目标都已失陷。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html">Amazon Uncovers AI Agent Campaign Targeting LiteLLM , Dify , and...</a></li>
<li><a href="https://qz.com/amazon-ai-agents-steal-provider-keys-artex-111626">Amazon captured records of AI agents trying to steal AI keys</a></li>

</ul>
</details>

**标签**: `#AI 安全`, `#AI 代理`, `#API 密钥泄露`, `#云安全`, `#威胁情报`

---

<a id="item-tech-news-9"></a>
### [美国将先进 AI 芯片管制延伸至远程访问](https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/) ⭐️ 7.0/10

美国商务部工业与安全局（BIS）于 11 月 16 日发布临时最终规则，将先进 AI 芯片及相关服务器的出口管制延伸至远程访问，以封堵通过第三国数据中心绕开限制的路径。据报道，规则由财政部和国家安全委员会主导起草，向印度尼西亚、马来西亚、新加坡、泰国和巴西再出口 AI 芯片须申请许可。云服务商、数据中心及上述市场的芯片采购方可能因此面临新的许可审查，但现有材料未提供规则全文，具体适用对象、生效条件和执行范围仍待确认。

telegram · zaihuapd · 11月16日 14:44

**「从拟议规则到正式发布」** 此前美国主要限制先进 AI 芯片和服务器的实体跨境流动，但企业可通过租用第三国数据中心的算力远程使用受限芯片，形成所谓“远程访问”缺口。Horizon 11 月 13 日的日报曾报道，商务部正敲定一项覆盖七个国家、包括马来西亚、新加坡和泰国的拟议规则，但当时规则文本、适用企业范围及实施时间表均未公布；11 月 16 日发布的临时最终规则将远程访问正式纳入管制，路透社称海外向中国 AI 企业提供服务的数据中心有 90 天申请许可，部分国家的再出口也须申请许可。

**「云端算力纳入出口审查」** 云服务商、数据中心运营方及芯片经销商需要将“远程提供算力”纳入出口管制合规检查；向受限制的中国客户提供先进 AI 芯片或服务器远程访问，即使硬件没有出境，也可能需要申请许可。向新加坡、马来西亚、印度尼西亚、泰国和巴西再出口相关 AI 芯片也须申请许可；由于该措施仍是临时最终规则，具体许可范围和执行条件应以规则文本为准。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theinformation.com/articles/commerce-department-finalizing-long-awaited-ai-remote-access-rule">2026-11-13 — 美商务部据报拟封堵中国 AI 远程用芯</a></li>
<li><a href="https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/">US to curb China&#x27;s access to AI chips as Trump heads to Asia</a></li>
<li><a href="https://media.bis.gov/sites/default/files/documents/BIS+Issues+Rule+Addressing+Remote+Access+to+American+Super+Intelligence+Technology.pdf">BUREAU OF INDUSTRY AND SECURITY - media.bis.gov</a></li>
<li><a href="https://www.nixonpeabody.com/insights/alerts/2026/11/16/bis-targets-remote-access-to-advanced-chips-through-overseas-data-centers">BIS targets remote access to advanced chips through overseas ...</a></li>
<li><a href="https://www.zerohedge.com/markets/us-closes-cloud-loophole-days-after-jensens-exit-new-rule-puts-ai-chip-rentals-china-and">US Closes The &quot; Cloud Loophole&quot;: Days After... | ZeroHedge</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-16/us-moves-to-limit-remote-access-to-advanced-ai-chips">US Moves to Curb China ’s Remote Access to Nvidia’s AI Chips</a></li>

</ul>
</details>

**标签**: `#AI chips`, `#export controls`, `#semiconductors`, `#AI infrastructure`, `#cloud computing`

---

<a id="item-tech-news-10"></a>
### [苹果中国区 App Store 新增 AIGC 合规必填项](https://www.ithome.com/1/028/158.htm) ⭐️ 7.0/10

据报道，苹果已在中国大陆区 App Store Connect 新增两项合规必填项：AIGC 服务声明与备案信息，以及安全评估证明。现有相关应用须在 2027 年 1 月 31 日前补齐，新应用则须在提交时立即提供。适用范围包括含聊天机器人、图像或视频生成、语音或人脸编辑等 AIGC 服务的 App；采用第三方技术的应用还须上传授权协议和算法备案号，苹果 2026 年审核指南也已纳入生成式 AI 条款。

telegram · zaihuapd · 11月17日 04:29

**「AIGC 审核背景」** 背景是，苹果 2026 年审核指南已经纳入生成式 AI 条款，此次 App Store Connect 后台新增的必填项则把相关要求细化为 AIGC 服务声明与备案信息、安全评估证明。适用范围包括聊天机器人、图像或视频生成、语音及人脸编辑；使用第三方技术的应用还须上传授权协议和算法备案号。

**「开发者需尽快核验合规材料」** 对中国区提供聊天、图像或视频生成、语音或人脸编辑等 AIGC 功能的开发者，直接影响是 App Store Connect 的审核资料准备：现有应用需在 2027 年 1 月 31 日前补齐 AIGC 服务声明与备案信息、安全评估证明，新应用须立即提交；使用第三方技术时还要准备授权协议和算法备案号。苹果确认会审核 App Store Connect 提交的所有 App，并要求开发者遵循审核准则，因此应尽快核对这些材料，材料不完整可能影响提交通过。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developer.apple.com/cn/distribute/app-review/">App 审核 - 分发 - Apple 开发者</a></li>
<li><a href="https://developer.apple.com/cn/news/?id=92th7e5i">更新后的《App 审核指南》现已发布 - 最新动态 - Apple Developer</a></li>

</ul>
</details>

**标签**: `#苹果 App Store`, `#AIGC 合规`, `#应用审核`, `#算法备案`, `#中国区应用发布`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [英特尔及两名高管遭股东集体诉讼](https://www.investing.com/news/stock-market-news/intel-sued-by-shareholders-following-29-stock-plunge-5028171) ⭐️ 7.0/10

据路透社报道，英特尔及 CEO 陈立武、CFO 津斯纳遭股东集体诉讼，诉称公司隐瞒 PC 需求疲软和库存积压，拟代表 2026 年 7 月 23 日至 10 月 29 日买入股票的投资者索赔。此前公司发布不及预期的第四季度营收和利润预测后，股价单日下跌 28.6%、市值减少约 1400 亿美元；诉讼指控尚未获法院或英特尔确认。

telegram · zaihuapd · 11月16日 11:10

**「背景」** 诉讼前，英特尔于 10 月 29 日公布低于预期的第四季度营收和利润预测，并警告个人电脑（PC）市场低迷可能延长；原告在诉状中指称公司此前隐瞒了 PC 需求疲软及库存积压。

**「影响」** 这起集体诉讼使英特尔及其 CEO 陈立武、CFO 津斯纳面临投资者索赔，拟代表 2026 年 7 月 23 日至 10 月 29 日买入股票的投资者主张损失；诉状指其淡化 PC 需求疲软对业绩的影响，但相关指控尚未经法院或公司确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wccftech.com/intel-ceo-lip-bu-tan-named-defendant-class-action-lawsuit-pc-sales-slowdown/">Intel CEO Lip - Bu Tan Named As Defendant In New Class-Action...</a></li>
<li><a href="https://www.tomshardware.com/pc-components/cpus/intel-sued-by-shareholders-for-misleading-investors-after-stock-plunges-29-percent-class-action-claims-the-company-downplayed-the-severity-of-pc-market-headwinds">Intel sued by shareholders for misleading investors after stock ...</a></li>
<li><a href="https://www.oreanda-news.com/en/v_mire/shareholders-sued-intel-over-the-collapse-of-the-company-s-value/article1605275/">Shareholders sued Intel over the collapse of the... - Oreanda-News</a></li>

</ul>
</details>

**标签**: `#英特尔`, `#股东集体诉讼`, `#业绩指引`, `#PC需求`, `#股价波动`

---