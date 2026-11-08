# Horizon 每日速递 - 2026-11-08

> 从 37 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [MaxxBench 检验 DeepSWE 成绩的泛化性](#item-tech-news-1) ⭐️ 8.0/10
2. [GitHub Rubicon 支持高并发智能体协作](#item-tech-news-2) ⭐️ 8.0/10
3. [macOS 被曝存在未公开的亲属分类与个人知识图谱组件](#item-tech-news-3) ⭐️ 7.0/10
4. [Claude Code 权限设置致公开仓库凭据泄露](#item-tech-news-4) ⭐️ 7.0/10
5. [Asahi Linux Progress Linux 7.3](#item-tech-news-5) ⭐️ 7.0/10
6. [实地探访内蒙古 Galaxy 数据中心](#item-tech-news-6) ⭐️ 7.0/10
7. [Claude Code 被指在网页搜索请求中泄露登录邮箱](#item-tech-news-7) ⭐️ 7.0/10
8. [苹果披露 HALO 人形机器人分层控制架构](#item-tech-news-8) ⭐️ 7.0/10

**财经新闻**
1. [软银与 ABB 拟分拆中国机器人业务](#item-finance-news-1) ⭐️ 7.0/10
2. [全国 3.35 万座寺院启动财务大检查](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [MaxxBench 检验 DeepSWE 成绩的泛化性](https://maxxbench.unlap.ai/research/why-maxxbench/) ⭐️ 8.0/10

MaxxBench 通过改变任务规格并观察模型得分与失败模式的变化，检验 DeepSWE 所报告的性能能否在条件变化后保持。该方法重点考察软件工程代理是真正具备解决任务的能力，还是只适应了基准原有的表述方式。现有材料未提供完整实验方法、具体分数或误差范围，因此不足以据此断言 DeepSWE 的结果无效；评论中关于基准存在缺陷的说法也尚未得到独立验证。

hackernews · antiuniverse · 11月7日 17:19 · [社区讨论](https://news.ycombinator.com/item?id=50406222)

**「背景」** MaxxBench 沿用 DeepSWE 的 89 个编码任务，但改写任务说明或起始代码，并将补丁规模变化控制在中位数 17 行（3.5%），以小幅扰动测试代理是否会调整原有策略。其设计考虑是，基准一旦进入模型或代理的研发流程，得分就可能同时反映实际能力与对原任务形态的适应，因此评测还需排查基准缺陷这一替代解释。

**「不要只看单一基准得分」** 对评估 DeepSWE 编码代理的团队，不宜再把一次基准得分直接当作代理能够适应不同需求表述的证据。DeepSWE 包含 113 个原创的长周期软件工程任务，而 MaxxBench 通过改写任务规格并比较得分与失败模式来检验其稳健性；因此，在模型选型或上线前，应使用多种规格变体复测，并审查任务及验证器实现中可能存在的缺陷。

**「评论者讨论扰动方式与训练过拟合」** 评论者 kqr 认为改变任务规格是检验基准分数泛化性的合理默认方法，但指出模型可能因不同原因失败，扰动变量的选择仍会影响结论。其他人从图中认为小型及“-flash”模型退化更明显，并推测这可能源于强化学习环境过度贴近基准任务；这些解读和预测属于评论者观点，现有摘录不足以验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://daily.dev/posts/maxxbench-nice-deepswe-score-but-is-it-true--ue9ulip60">MaxxBench – &quot;Nice DeepSWE score. But is it true?&quot;</a></li>
<li><a href="https://maxxbench.unlap.ai/research/why-maxxbench/">Introducing MaxxBench: Benchmarking Task Adaptation and ...</a></li>
<li><a href="https://deepswe.datacurve.ai/">DeepSWE measures frontier coding agents on original, long-horizon...</a></li>
<li><a href="https://arxiv.org/html/2607.07946">DeepSWE : Measuring Frontier Coding Agents on Original...</a></li>

</ul>
</details>

**标签**: `#LLM evaluation`, `#DeepSWE`, `#software engineering agents`, `#benchmark robustness`, `#AI benchmarks`

---

<a id="item-tech-news-2"></a>
### [GitHub Rubicon 支持高并发智能体协作](https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/) ⭐️ 8.0/10

GitHub 开始以有限私有预览方式提供代号为 Rubicon 的新 Git 存储架构，主要面向大量 AI 智能体并发操作同一代码仓库的场景。其内部测试显示，5000 个智能体同时协作时每秒可处理 7200 次推送，并保持较低读取延迟。该架构将 Git 对象存入 Azure Blob Storage，以 Ref-CAS 管理引用状态，通过虚拟副本处理读写，并由后台节点压缩数据包；不过，上述性能来自 GitHub 内部测试，尚未代表公开上线后的普遍表现。

telegram · zaihuapd · 11月7日 14:12

**「Rubicon 的存储分层」** Git 仓库并不只保存工作区文件：Git 对象记录内容与仓库结构，ref 则维护分支、标签等指向提交的可变引用。Rubicon 在这一分层上将 Git 对象存入 Azure Blob Storage，以 Ref-CAS 管理引用状态，并通过虚拟副本和后台压缩处理并发读写与数据整理；相关架构当时仍处于有限私有预览阶段。

**「适用场景与当前限制」** 对需要在同一仓库中并发运行数千个 AI 智能体的团队，获准参与 Rubicon 私有预览后，可重点验证批量推送时的写入吞吐和读取延迟；GitHub 内部测试称，5000 个智能体可实现每秒 7200 次推送。该能力目前仅处于有限私有预览，普通组织不能据此认定已经可用，而且性能数字来自厂商内部测试，尚不能视为独立基准。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://dzen.ru/a/au6qec3gh2vpaVUH">GitHub описала Rubicon , новое хранилище Git для... | Дзен</a></li>

</ul>
</details>

**标签**: `#GitHub`, `#Git 存储架构`, `#AI 智能体并发`, `#Azure Blob Storage`, `#Ref-CAS`

---

<a id="item-tech-news-3"></a>
### [macOS 被曝存在未公开的亲属分类与个人知识图谱组件](https://8rank.ai/game/apple-intelligence-personal-knowledge-graph) ⭐️ 7.0/10

一项针对 macOS 与 Apple Intelligence 内部机制的调查声称，Mac 上存在未公开的“家庭成员”分类器及个人知识图谱守护进程，可能用于整理用户身份、熟人关系和互动信息。此次发布的是调查结论而非 Apple 宣布的版本更新；现有材料也未提供正式组件名、具体版本、数据是否上传、触发条件或关闭方式。因此，标题中的“每台 Mac 都自带这些能力”应视为研究者的概括性主张，而不是已由系统日志、代码或独立测试证实的官方规格。

hackernews · infwhispers · 11月7日 09:46 · [社区讨论](https://news.ycombinator.com/item?id=50403097)

**「个人知识图谱与关系消歧」** 这里的“个人知识图谱”是指将联系人、亲属、地点和沟通对象等实体及其关系整理为可检索的上下文，使系统中的语言模型能够理解“给 James 发消息”之类存在歧义的指令。转述 8rank.ai 研究的报道称，这一机制是在检查 macOS 26 的 Apple Intelligence 组件时发现的，涉及 knowledgeconstructiond 和 intelligenceplatformd 两个后台守护进程，用于构建供语言模型查询的关系信息。不过，“自 2022 年起每台 Mac 都具备完整的关系推断能力”仍是研究的概括性主张，现有背景材料不足以独立验证其实际覆盖范围。

**「开发者需明确应用数据的个性化用途」** 准备接入 Apple Intelligence 的开发者需要明确设计应用操作和数据的披露与授权，因为 Apple 官方文档确认 Siri、聚焦搜索和快捷指令可结合个人上下文增强功能；但这些文档并未验证调查所称的“家庭成员分类器”存在于每一台 Mac。

**「社区讨论：用途与知情同意」** 讨论者对这类关系图谱的用途与风险存在分歧：有人认为它可为 Siri 等本地模型区分同名联系人，另有评论者称 Photos 已能识别亲友的人脸和名字，因此并不意外。隐私方面的主要反对意见是默认收集与他人同意问题：Thomascountz 表示若能选择加入会觉得有趣，但如今感到疲惫，并认为聊天参与者并未同意被归纳；这些均是评论者观点，不能证明组件实际如何运行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techbytes.app/posts/every-mac-comes-with-an-undocumented-family-member-classifier/">Every Mac comes with an (undocumented) family member classifier</a></li>
<li><a href="https://techplanet.today/post/apples-hidden-personal-knowledge-graph-understanding-macoss-undocumented-family-classifier">Apple&#x27;s Hidden Personal Knowledge Graph: Understanding macOS ...</a></li>
<li><a href="https://developer.apple.com/documentation/technologyoverviews/apple-intelligence/">Apple Intelligence | Apple Developer Documentation</a></li>

</ul>
</details>

**标签**: `#macOS internals`, `#personal knowledge graphs`, `#on-device AI`, `#privacy`

---

<a id="item-tech-news-4"></a>
### [Claude Code 权限设置致公开仓库凭据泄露](https://apiiro.com/blog/coding-agents-leaking-secrets-github-dont-ask-again) ⭐️ 7.0/10

一项第三方扫描称，GitHub 上有 1,122 个公开文件包含与 Claude Code 权限设置相关的暴露凭据。社区澄清，按下“Don’t Ask Again”本身并不会自动公开密码；典型情形是开发者把含密钥或密码命令的本地 \`.claude/settings.local.json\` 手动提交并发布。Anthropic 团队成员 Boris 表示，Claude Code 历来没有内置密钥清理能力，正在研究预防措施；该文件本应只保留在本地，Claude 自动创建时会将其加入 \`.gitignore\`。

hackernews · shmulc · 11月7日 20:45 · [社区讨论](https://news.ycombinator.com/item?id=50407882)

**「暴露前提」** Claude Code 的“Don’t Ask Again”会将获准执行的命令保存到本地 \`.claude/settings.local.json\`；该文件按设计不应提交到版本控制，Claude Code 创建它时也会自动将其加入 \`.gitignore\`。因此，泄露通常发生于开发者手工创建并提交了含明文密码或密钥的本地设置文件，随后又公开仓库，而不是仅仅点击“Don’t Ask Again”便会自动暴露凭据。

**「开发者需检查本地配置」** 在 Claude Code 权限命令中使用真实密钥的开发者，应确认 \`.claude/settings.local.json\` 未被 Git 跟踪并检查提交历史；若相关凭据曾进入公开仓库，需要轮换可能已暴露的密钥或密码。

**「评论者补充风险边界」** 评论者认为标题把“Don’t Ask Again”与提交本地配置混为一谈；实际暴露还需要开发者把含秘密的批准命令写入配置并公开发布仓库。另有用户采用一次性隔离虚拟机、限制外部服务的 API 代理，以及由 1Password 的 op CLI 在指纹确认后临时取用凭据，以减少代理长期接触秘密；这些属于个人工作流建议，而非扫描结论。

**标签**: `#AI coding agents`, `#secret leakage`, `#GitHub security`, `#Claude Code`, `#developer tooling`

---

<a id="item-tech-news-5"></a>
### [Asahi Linux Progress Linux 7.3](https://asahilinux.org/2026/11/progress-report-7-3/) ⭐️ 7.0/10

Asahi Linux&\#x27;s Linux 7.3 progress report details continued Apple Silicon enablement work and a same-day Fedora Asahi Remix release, prompting discussion about display support and project licensing.

hackernews · ackyshake · 11月7日 05:20 · [社区讨论](https://news.ycombinator.com/item?id=50401867)

**标签**: `#Asahi Linux`, `#Apple Silicon`, `#Linux kernel`, `#hardware enablement`, `#Fedora Asahi`

---

<a id="item-tech-news-6"></a>
### [实地探访内蒙古 Galaxy 数据中心](https://newsletter.semianalysis.com/p/we-visited-chinas-stargate-in-inner) ⭐️ 7.0/10

SemiAnalysis 在 9 月实地探访了位于内蒙古乌兰察布的 Galaxy AI 数据中心，并称该园区规划最高 800MW 的 IT 容量，首期 120MW 在一年内交付，成本约为美国同类项目的五分之一。园区业主远景集团（Envision Group）为两家互联网巨头定制建设全部四个阶段，同时运营自有风电场和专用输电线，并集成低压电力模块、800V 系统、电池储能及预制变电站；到访时园区其余部分仍在施工，周边 22 个数据中心项目据当地报道合计约 3 万名工人在岗。成本仅为美国项目五分之一及“超低成本”属于报道方说法，现有内容未说明成本口径、核算方法或独立验证依据。

rss · Semianalysis · 11月7日 19:01

**「中美人规模数据中心建设对照」** 作为比较基准，Stargate Abilene 是美国得州平原上为 OpenAI 建设的吉瓦级 AI 数据中心园区。SemiAnalysis 在 11 月 2 日的日报中曾报道，其模型预计得州约占美国 2028 年新增数据中心容量的 30%，而许可暂停、州长选举及候选人对扩建的立场可能延后建设；这为此次将内蒙古称作“中国得州”并与 Abilene 进行规模对照提供了此前的政策背景。

**「影响」** 对中国 AI 与云服务企业，Galaxy 的 120MW 首期在一年内交付，SemiAnalysis 称其成本约为美国同类项目的五分之一，提供了更快扩建本土算力的具体案例；公开资料称该园区已于 2026 年 8 月开始运行，并非仅有规划。不过，四期均按两家互联网巨头定制，不能视为面向其他客户公开供应的通用容量；报道未披露成本核算方法或提供独立验证，企业据此调整预算前应另行核实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://newsletter.semianalysis.com/p/the-datacenter-backlash-goes-bipartisan">2026-11-02 — 中期选举影响美国 2028 年数据中心建设</a></li>
<li><a href="https://interestingengineering.com/energy/worlds-first-800v-dc-power-system">China debuts world&#x27;s first 800V DC power system for smart data centers</a></li>

</ul>
</details>

**标签**: `#AI infrastructure`, `#data centers`, `#China`, `#power capacity`, `#infrastructure economics`

---

<a id="item-tech-news-7"></a>
### [Claude Code 被指在网页搜索请求中泄露登录邮箱](https://github.com/anthropics/claude-code/issues/107757) ⭐️ 7.0/10

一名开发者在 Claude Code 的 GitHub issue 中称，其登录邮箱可能被填入联网请求并发送给外部网站，导致每天收到大量诈骗邮件；目前这属于问题报告，尚非已被独立证实的系统性漏洞。Anthropic 工程师解释，早期为避免 Claude 误填作者名，团队曾将登录邮箱放入模型上下文；据称 7 月已有用户报告邮箱被发送给维基百科、美国证券交易委员会等站点。维护方已在 2.1.317 版加入拦截，但该措施可被 Python 脚本绕过，并计划在下一版本中从模型上下文移除登录邮箱。

telegram · zaihuapd · 11月7日 08:09

**「问题的技术背景」** 据 Anthropic 工程师在 GitHub issue 中解释，Claude Code 最初为避免模型猜测 Git 提交作者姓名，将账户登录邮箱放入模型上下文；模型调用联网工具时，邮箱因而可能随请求一并发送。该问题早在 7 月就已被报告，曾涉及向 Wikipedia、美国证券交易委员会等站点发送邮箱；Claude Code 2.1.317 随后加入拦截，但报道指出 Python 脚本仍可绕过，因此公司计划在下一版本中从模型上下文里移除登录邮箱。

**「开发者需防范邮箱暴露与钓鱼风险」** 据 GitHub 问题报告，Claude Code 在网页搜索时曾将用户的登录邮箱放入 User-Agent 请求头并发送给第三方，报告者因此每天收到数十封诈骗邮件，意味着使用联网搜索的开发者可能暴露账户标识并遭遇定向钓鱼。Claude Code 2.1.317 已加入拦截，但报道称 Python 脚本仍可绕过，因此用户应检查相关升级版本，并等待后续版本从模型上下文中移除邮箱，而不应仅依赖现有拦截。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/anthropics/claude-code/issues/107757">Bug Report: Privacy violation in User-Agent header · Issue #107757...</a></li>

</ul>
</details>

**标签**: `#Claude Code`, `#隐私泄露`, `#网络安全`, `#AI 编程工具`

---

<a id="item-tech-news-8"></a>
### [苹果披露 HALO 人形机器人分层控制架构](https://weibo.com/1642634100/RqjjGllvw) ⭐️ 7.0/10

据转述新浪科技的简讯，苹果研究团队于 11 月 4 日在 arXiv 提交论文，披露人形机器人自主控制架构 HALO，并在宇树 G1 上将仿真环境中学到的动作迁移至陌生真实房间执行。HALO 分为三层：Qwen3.6-35B-A3B 负责任务编排，Qwen3.5-2B 生成动作，底层为通过强化学习训练的动作跟踪器；研究团队称已公开数据生成、模型训练与部署代码。当前内容未附论文或代码链接，也未提供量化结果和消融实验，因此该方案及其代码的实际可用性仍无法独立核验。

telegram · zaihuapd · 11月7日 13:35

**「技术背景」** HALO 采用了分层具身控制架构：上层模型编排任务，中层模型生成动作，底层强化学习动作跟踪器负责真实执行；这里的“仿真到现实”是指把模拟环境中学到的动作迁移到陌生真实房间。作为验证平台，宇树 G1 已有 LeRobot 适配项目，支持使用其双臂灵巧手采集的数据进行训练和测试，但现有简讯未说明 HALO 是否直接采用该工具链。

**「开放代码与适用范围」** 数据生成、模型训练和部署代码的公开，使开发者能够检查并复现 HALO 的两级千问模型与强化学习动作跟踪器方案。现阶段该方案仅在宇树 G1 上得到验证，因此其他机器人平台能否兼容，以及迁移到陌生真实房间的可靠性和量化表现仍需结合论文结果评估。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/unitreerobotics/unitree_lerobot">GitHub - unitreerobotics/ unitree _lerobot: The unitree _il_lerobot...</a></li>

</ul>
</details>

**标签**: `#人形机器人`, `#Qwen`, `#强化学习`, `#仿真到现实`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [软银与 ABB 拟分拆中国机器人业务](https://www.bloomberg.com/news/articles/2026-11-07/softbank-abb-weigh-china-carve-out-to-salvage-robotics-deal) ⭐️ 7.0/10

据彭博援引匿名知情人士，软银与 ABB 正考虑将 ABB 机器人业务的中国部分分拆为由软银主导、股权独立的新实体，以推进已被中国叫停的 54 亿美元收购；方案能否继续尚不确定，ABB 也在评估另寻买家。

telegram · zaihuapd · 11月7日 11:24

**「背景」** 此前，中国外商投资安全审查工作机制办公室已叫停软银以 54 亿美元收购 ABB 机器人业务的交易；ABB 随后确认，禁令针对其中国机器人业务。

**「潜在影响」** 若分拆方案获批，原 54 亿美元收购将不再涵盖中国业务，使软银和 ABB 有机会在剔除受审查部分后继续交易，但该方案能否获批仍不确定。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/business/media-telecom/china-blocks-softbanks-54-billion-takeover-abbs-robotics-division-ft-reports-2026-11-05/">China blocks SoftBank’s $5.4 billion takeover of ABB’s ...</a></li>
<li><a href="https://www.swissinfo.ch/eng/workplace/china-blocks-softbanks-5-4bn-takeover-of-abbs-robotics-division/92331403">China blocks SoftBank’s $5.4bn takeover of ABB’s robotics ...</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-07/softbank-abb-weigh-china-carve-out-to-salvage-robotics-deal">SoftBank, ABB Consider China Carve-Out to Salvage Robotics ...</a></li>
<li><a href="https://www.abb.com/global/en/news/140154/update-on-divestment-of-abb-robotics">Update on divestment of ABB Robotics</a></li>

</ul>
</details>

**标签**: `#软银`, `#ABB`, `#机器人并购`, `#中国外资安全审查`

---

<a id="item-finance-news-2"></a>
### [全国 3.35 万座寺院启动财务大检查](https://www.163.com/dy/article/LB2VSRQD0556HNS1.html) ⭐️ 7.0/10

覆盖全国寺院和道观的财务检查将加强审计和关联交易监管，并限制宗教场所的商业化经营及融资。

telegram · zaihuapd · 11月7日 15:02

**标签**: `#宗教财务监管`, `#寺院与道观`, `#第三方审计`, `#商业化整顿`

---

