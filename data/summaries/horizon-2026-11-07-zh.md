# Horizon 每日速递 - 2026-11-07

> 从 39 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [Libghostty 1.0 面向终端应用开发者](#item-tech-news-1) ⭐️ 8.0/10
2. [百度开源文心 5.5 Flash Base](#item-tech-news-2) ⭐️ 8.0/10
3. [长江存储武汉新厂国产设备占比最高拟达 70%](#item-tech-news-3) ⭐️ 8.0/10
4. [PwnEscape 第二部分：Firecracker 虚拟机逃逸的实际利用](#item-tech-news-4) ⭐️ 7.0/10
5. [AI 正在加速机器学习研究，但证据集中于特定环节](#item-tech-news-5) ⭐️ 7.0/10
6. [Jev 按需调用 Claude Opus 降低身份核验成本](#item-tech-news-6) ⭐️ 7.0/10
7. [月之暗面据报洽租欧洲逾 8000 颗 Blackwell GPU](#item-tech-news-7) ⭐️ 7.0/10
8. [欧盟指控 TikTok 推荐算法造成“兔子洞”效应](#item-tech-news-8) ⭐️ 7.0/10
9. [淘宝 MNN 开源 0.3B 手机端模型](#item-tech-news-9) ⭐️ 7.0/10
10. [Telegram 13.2 新增聊天内 HTML 互动消息](#item-tech-news-10) ⭐️ 7.0/10

**科技博客**
1. [与设计师协作的边界](#item-tech-blog-1) ⭐️ 6.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Libghostty 1.0 面向终端应用开发者](https://mitchellh.com/writing/libghostty-1-0) ⭐️ 8.0/10

Libghostty 1.0 已发布，面向希望复用终端模拟能力的开发者，该版本将这一库推进到可用于构建终端应用与集成的 1.0 阶段。现有材料未列出具体 API、性能数据、平台兼容范围或许可证变化，因此无法据此判断它与既有版本的技术差异。

hackernews · mfiguiere · 11月6日 23:30 · [社区讨论](https://news.ycombinator.com/item?id=50399933)

**「背景」** Libghostty 是 Ghostty 终端模拟器可供其他程序集成的库形态，使应用能够复用终端处理能力，而不必只采用完整的 Ghostty 终端。社区开发者称，在 1.0 版本发布前，他们已将该库用于自建终端项目、Emacs 的 Ghostel 集成以及一次 Android 项目尝试；其中一位开发者表示，这项能力省下了大量重复实现工作。

**「开发影响」** 对终端应用开发者，Libghostty 1.0 提供了可复用的终端模拟基础：一名评论者报告，在自建终端项目中采用该库后节省了大量工作，Ghostel 项目页面也显示其 Emacs 终端模拟器由 libghostty 驱动。Emacs 及其他终端集成因此可以减少底层终端仿真的重复开发，但现有材料未提供平台支持、语言绑定或兼容性清单，集成方仍需针对目标环境验证。

**「开发者的实际使用反馈」** 一名正在开发自有终端项目的开发者称 Libghostty 能够直接运行并节省了大量工作，另一名用户则认为它让基于 Ghostel 的 Emacs 终端体验成为可能；也有人曾尝试将其用于 Android 项目。讨论中还提出了无显示服务器环境下的 SSH 配色支持，以及为何采用 C 而非 Zig 等具体问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://modernorange.io/item/48879504">Ghostel .el: Terminal emulator powered by libghostty | Modern Orange</a></li>

</ul>
</details>

**标签**: `#libghostty`, `#terminal-emulators`, `#developer-tools`, `#open-source`

---

<a id="item-tech-news-2"></a>
### [百度开源文心 5.5 Flash Base](https://www.news.cn/info/20261105/f3bbdb6854f5441ca9fb34062f213875/c.html) ⭐️ 8.0/10

百度已正式开源基座模型“文心 5.5 Flash Base”，面向需要自行训练、微调或部署模型的开发者。该 MoE 模型总参数量为 2800 亿，每个 Token 激活 140 亿参数，使用 33.5 万亿 Token 预训练；预训练上下文最长为 128K，微调与推理最长支持 100 万 Token。百度称模型通过优化注意力机制、专家路由和训练目标提升资源利用效率，但报道未提供基准测试、许可证、代码仓库及复现细节，因此实际性能和可用性尚无法据此判断。

telegram · zaihuapd · 11月6日 05:41

**「模型规格背景」** 理解文心 5.5 Flash Base 的参数规格，需要区分 MoE 架构的总参数量与单 Token 激活参数量：2800 亿代表模型的总参数规模，而 140 亿表示每个 Token 实际激活的参数规模。该设计旨在保留较大模型容量的同时减少单次推理计算量；预训练最长 128K、微调与推理最长 100 万 Token 则分别对应训练阶段和使用阶段的不同上下文上限。

**「对模型开发与部署的影响」** 按百度披露的规格，文心 5.5 Flash Base 将 2800 亿总参数与每 Token 140 亿激活参数分开，开发者评估微调和推理成本时，应重点测量激活参数对应的显存占用、吞吐和自身任务表现，而非仅按总参数量估算。官方称其微调与推理支持最长 100 万 Token 上下文，但报道未提供许可证、代码仓库或基准测试，正式接入前仍需核验这些条件。

**标签**: `#文心5.5`, `#开源大模型`, `#MoE架构`, `#长上下文`, `#模型效率`

---

<a id="item-tech-news-3"></a>
### [长江存储武汉新厂国产设备占比最高拟达 70%](https://www.reuters.com/world/china/chinas-top-flash-memory-chipmaker-targets-more-homegrown-tools-new-factory-2026-11-06/) ⭐️ 8.0/10

长江存储计划在武汉建设第四座 NAND 工厂，预计 2027 年开工，并将国产设备采购比例从第三座工厂目前超过 50%的水平提高到至少 60%、最高达到 70%。新厂拟生产超过 300 层的先进 NAND 闪存，主要面向数据中心和人工智能存储需求，清洗、抛光和刻蚀设备预计成为国产化增量重点。项目目前仍处于规划阶段，光刻、检测等先进设备仍依赖海外供应商；报道还称，长江存储在中国的 NAND 市场份额已达 38.5%，未来三座新厂全部投产后整体产能有望翻倍。

telegram · zaihuapd · 11月6日 08:34

**「设备国产化的既有基础」** 这轮设备国产化的推力来自美国出口管制。据报道，长江存储第三座工厂目前国产设备占比已超过 50%，新增产能中的主要国产化增量预计出现在清洗、抛光和刻蚀设备，而光刻、检测等先进设备仍依赖海外供应商；公司在中国 NAND 市场的份额已升至 38.5%、超过三星，这是其继续扩建的产业基础。需要注意，第四座工厂及 60%–70%的国产设备比例、300 层以上 NAND 产能目前均属规划口径，项目预计 2027 年才开工，尚无已建成产能佐证。

**「设备国产化机会与限制」** 若武汉第四座 NAND 工厂按计划于 2027 年开工，清洗、抛光和刻蚀设备将迎来最直接的潜在采购增量，相关国产设备厂商可将其视为前瞻性订单机会，而非已确认收入。Omdia 同期数据显示，长江存储在中国 NAND 市场的份额已达 38.5%并超过三星，因此其扩产采购具有实际分量；但 60%–70%的国产设备比例仍是规划目标，且光刻、检测仍依赖海外供应商，晶圆厂不能据此认定设备供应链已完全自主。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.businesskorea.co.kr/news/articleView.html?idxno=279363">Samsung, SK hynix Upgrade China NAND Plants to Counter Rising ...</a></li>

</ul>
</details>

**标签**: `#半导体`, `#NAND闪存`, `#芯片制造`, `#供应链国产化`, `#AI基础设施`

---

<a id="item-tech-news-4"></a>
### [PwnEscape 第二部分：Firecracker 虚拟机逃逸的实际利用](https://pwn.ai/blog/firecracker-escape) ⭐️ 7.0/10

pwn.ai 发布了 PwnEscape 系列的第二篇文章，通过实际利用演示说明此前披露的 Firecracker 虚拟机逃逸漏洞可以在 Firecracker 虚拟机中被触发。文中明确交代了演示的前提条件：其配置没有启用 jailer，而 Firecracker 生产环境的隔离手段包括降权，以及通过命名空间（namespaces）和 seccomp 限制 VMM 进程；作者因此指出，启用了这些管控的部署仍需单独评估 VMM 被攻破后残留的权限与可访问资源。这不是一次新的漏洞披露，而是对数周前已公开的 PwnEscape 漏洞的实践性利用说明，属于同一漏洞的后续技术文章。

hackernews · SerCe · 11月6日 19:33 · [社区讨论](https://news.ycombinator.com/item?id=50397219)

**「背景」** PwnEscape 是此前已披露的 Firecracker 虚拟机逃逸漏洞，本文并非再次披露新漏洞，而是展示如何将其转化为针对 Firecracker microVM 的实际利用链。PoC 从恶意客户机内定位仍在运行的 VMM，并最终控制宿主机上以 root 身份运行的进程；测试配置未启用 jailer，因此生产部署中的降权、命名空间和 seccomp 隔离能否阻止这条攻击链仍需单独评估。

**「部署方需重新评估失陷后的权限边界」** 此次披露并非新增漏洞，而是证明 PwnEscape 可在特定配置下被实际用于 Firecracker 的客户机到宿主机逃逸，因此运行不可信代码的服务方不能仅依赖 Firecracker 进程本身维持隔离。Firecracker 官方设计以 seccomp、cgroups、命名空间和降权进程提供纵深防御，但启用这些控制后仍需单独核查 VMM 被攻破时剩余的宿主权限与可访问资源。

**「评论者补充真实部署经验与质疑前提」** 最有说服力的反馈来自 zX41ZdbW：他运营的 ClickBench playground 完全依赖 Firecracker 虚拟机、承载数百个存在漏洞的数据库引擎（他称 Pandas 基本等同于开放 RCE），并表示可以在该线上服务上完成 Firecracker 虚拟机逃逸的 PoC，说明在缺少额外隔离的部署中这一利用并非纯理论问题。lrvick 则主张采用 Nova 微内核（hypervisor.org）路线，让复杂内核运行在小型、经形式化验证的微内核之下；markasoftware 和 denysvitali 认为这篇文章只是数周前已披露漏洞的实践利用写法、并非新问题，后者给出了更早的 HN 讨论链接，而 scoodah 希望作者能就“演示未启用 jailer”这一前提展开更多说明。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://pwn.ai/blog/firecracker-escape">Firecracker VM Escape: PwnEscape Part 2. | PWN.AI Security ...</a></li>
<li><a href="https://github.com/firecracker-microvm/firecracker/blob/main/docs/design.md">firecracker /docs/design.md at main · firecracker -microvm/ firecracker</a></li>
<li><a href="https://news.ycombinator.com/item?id=50397219">Firecracker VM Escape : PwnEscape Part 2 | Hacker News</a></li>
<li><a href="https://pwn.ai/blog/pwnescape">PwnEscape : Guest-to-Host KVM Escape (CVE-2026-99999) | PWN .AI...</a></li>

</ul>
</details>

**标签**: `#Firecracker`, `#VM escape`, `#Vulnerability research`, `#Cloud security`

---

<a id="item-tech-news-5"></a>
### [AI 正在加速机器学习研究，但证据集中于特定环节](https://www.planned-obsolescence.org/p/ai-is-dramatically-accelerating-ai) ⭐️ 7.0/10

文章提出，AI 工具已经让机器学习研究的部分环节明显提速，受益者主要是能够在计算环境中快速试验和修改代码的 ML 研究者，尤其是模型架构、训练策略、算法与软件工作；讨论中有研究者估计个别任务可快约 10 倍，但这是轶事性说法，并非独立测量。文章的核心限制是，现有证据更多显示“针对基准的优化工作”变快，而不是所有科研活动都同步加速，也无法证明递归自我改进或更广泛的社会影响。评论者还指出，把多个基准合并成曲线会掩盖差异，且基准反馈回路和合成数据训练可能夸大看似自主的进步，因此应区分基准成绩、研究生产率与通用能力。

hackernews · yurivish · 11月6日 20:27 · [社区讨论](https://news.ycombinator.com/item?id=50397994)

**「相关研究背景」** 相关背景是，AI 对可数字化、可评测的研究环节加速最明显，而涉及物理实验的实验室工作并未同步提速。《Scientific American》提到模型生成证明等案例同时引发了“抢先完成”的争议；arXiv 论文 2609.36054 则称，相比一年前，AI 已编写 AI 公司大部分代码，并据此初步评估 AI 自动化 AI 研发是否会触发“智能爆发”，但这仍不是已经证实的结论。

**「研究团队的局部加速与工程代价」** 对研究团队而言，AI 的可兑现收益主要是模型架构、训练策略和软件实验等计算环境内环节的更快迭代；文章据此主张 AI 正在加速部分机器学习研究，但这属于局部、可测量的工作流效应，不能直接外推为整体科研速度或系统能力的跃升。外部证据也显示应谨慎解读生产力数字：METR 对 349 名技术人员的调查称，AI 工具带来的工作价值自报变化中位数为 1.4–2 倍，但报告提醒这一幅度值得怀疑；Faros 的 2026 工程报告则称吞吐量上升时，缺陷、生产事故和返工也在更快增加。实际采用时，团队应把实验吞吐量与缺陷率、事故数和返工成本放在同一指标体系中衡量，否则可能把局部提效误当成无摩擦的生产力增长。

**「社区对加速机制的质疑」** 一位自称从事 ML 研究的评论者把“研究提速”限定为模型架构、训练策略、算法和软件等计算环境内工作，并认为这种提速本身不能推出超级智能或世界变化加速。另一些评论者质疑能力提升究竟来自数据、架构、训练方法，还是资本投入与规模化扩展；他们也指出，个人产出加快并不等于宏观影响同比扩大。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/why-ai-is-speeding-up-scientific-research-but-not-lab-experiments/">Why AI is speeding up scientific research but not lab ...</a></li>
<li><a href="https://arxiv.org/abs/2609.36054">[2609.36054] What if automating AI R&amp;D triggers an ...</a></li>
<li><a href="https://metr.org/notes/2026-02-10-simpler-ai-timelines-model/">A simpler AI timelines model predicts 99% AI ... - METR</a></li>
<li><a href="https://www.faros.ai/research/ai-acceleration-whiplash">AI Impact on Engineering Productivity : 2026 Report Data</a></li>

</ul>
</details>

**标签**: `#artificial-intelligence`, `#machine-learning-research`, `#LLMs`, `#AI benchmarks`, `#research productivity`

---

<a id="item-tech-news-6"></a>
### [Jev 按需调用 Claude Opus 降低身份核验成本](https://hightouch.com/blog/llm-judges-identity-resolution) ⭐️ 7.0/10

文章介绍了一个名为 Jev 的评审模型：它在身份核验任务中仅在需要时请求 Claude Opus 协助。文章称，Jev 能以约为单独使用 Opus 四分之一的成本达到“Opus 级”的准确率；但目前可见信息未提供独立测量，而且该结果仅针对身份核验，不能外推为通用代理或编程任务的同等提升。

hackernews · theanomaly · 11月6日 19:48 · [社区讨论](https://news.ycombinator.com/item?id=50397429)

**「实验背景」** 身份解析是判断不同数据集中的多条记录是否指向同一实体的任务，也是该实验评估模型判断准确性的具体场景。Jev 与 Claude Opus 的混合方案采用选择性升级机制，由 Jev 先处理、仅在必要时请求 Opus；原文称其在每千次身份判断上可实现约 0.15 秒响应和 0.10—0.50 美元成本，但在更难的基准上准确率仍比 Opus 低约 6 个百分点。

**「身份解析的降本路径」** 对于需要判定多条记录是否属于同一实体的团队，Hightouch 报告的基准测试显示，可用 Jev 完成首轮判定，仅将低置信度案例升级给 Claude Opus，在达到前沿模型准确率的同时将成本降至原来的四分之一以下。作为对照，Jev 和 GPT-6 Luna 单独运行时虽然最高可便宜 90 倍、快 10 倍，但准确率较低，因此采用该方案时仍需保留升级路径；这些结果限于身份解析任务，不能直接外推到编码或通用智能体工作负载。

**「社区讨论」** nico 指出，这只是身份核验这一特定任务的结果，不能据此证明通用使用或编程代理也有提升；netshade 则表示自己见过类似的按需升级行为，但认为最优模型组合与经济性高度依赖任务和模型能力边界。另有评论者称已在安全工作流中采用混合方案，但需要经过初始校准；关于利用决策模型自动策展上下文的说法则属于个人判断，而非已经验证的结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://hightouch.com/blog/llm-judges-identity-resolution">LLM Judges for Identity Resolution at 4x Lower Cost | Hightouch</a></li>
<li><a href="https://hightouch.com/blog/llm-judges-identity-resolution">LLM Judges for Identity Resolution at 4x Lower Cost | Hightouch</a></li>
<li><a href="https://todayforai.com/en/items/art-6182ccb3-c82">Hybrid Jev-Opus Routing Matches Frontier Accuracy at 4x Lower ...</a></li>

</ul>
</details>

**标签**: `#LLM routing`, `#model cascades`, `#AI agents`, `#cost optimization`, `#identity resolution`

---

<a id="item-tech-news-7"></a>
### [月之暗面据报洽租欧洲逾 8000 颗 Blackwell GPU](https://www.cnbc.com/2026/11/05/moonshot-ai-nvidia-chips-europe-china.html) ⭐️ 7.0/10

据 CNBC 援引知情人士报道，月之暗面正与欧洲新兴云厂商洽谈租用 8,000 颗以上 Nvidia Blackwell GPU，算力主要用于推理，也涉及训练；交易尚未敲定，消息源也未具名。报道称，美国出口管制禁止 Blackwell 芯片进口中国，而通过海外数据中心远程调用被视为潜在的绕道途径。报道还援引白宫今年 7 月的说法，称该公司曾通过位于泰国的设施获得 Blackwell 芯片。谈判中的方案据称要求月之暗面比非中国买家多预付 30% 至 50%，但相关条件与最终部署均未得到确认。

telegram · zaihuapd · 11月6日 05:02

**「海外云算力与出口管制的边界」** 美国现行出口管制禁止 Blackwell 芯片进入中国，但据 TechTimes 对相关报道的梳理，企业租用欧洲新型云服务商（neocloud）的海外算力目前并不自动等同于非法出口，出租方是否触发受管制交易及相关合规义务仍需逐案判断。作为同一政策环境下的相关先例，2026 年 11 月 5 日的 Horizon 日报转述《金融时报》报道称，甲骨文在美国政府施压下取消了与腾讯价值约 70 亿美元、为期五年的 AI 芯片租赁协议；该报道没有提供官方原始信源或明确取消日期，因此这一事件仍属未经独立确认的报道。另据 Yahoo 转载报道，白宫方面曾于今年 7 月声称月之暗面通过泰国产能远程使用 Blackwell；这是政府方面的说法，并非已独立核实的使用记录。

**「海外算力供给仍存变数」** 若洽谈成功，月之暗面可在无需将 Blackwell 芯片运入中国的情况下，从欧洲 neocloud 获得 8,000 颗以上 GPU，用于推理并兼顾训练；但美国国会议员正考虑封堵中国 AI 企业通过海外云访问先进 Nvidia 算力的缺口，因此该方案可能面临进一步限制，不能视为稳定的长期容量来源，依赖该路径的部署仍需准备替代算力方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tradingview.com/news/seekingalpha:e51e68f4d094b:0-oracle-cancels-7b-ai-chip-lease-with-tencent-amid-us-concerns-ft/">2026-11-05 — 甲骨文取消腾讯 70 亿美元芯片租赁协议</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/china-moonshot-ai-seeks-nvidia-155140723.html?fr=sycsrp_catchall">China’s Moonshot AI seeks Nvidia Blackwell access in Europe ...</a></li>
<li><a href="https://www.techtimes.com/articles/330165/20261106/moonshot-ai-sought-nvidia-blackwell-rentals-europe-reported-51-rule-not-us-law-hits-lessors.htm">Moonshot AI Sought Nvidia Blackwell Rentals in Europe ...</a></li>
<li><a href="https://www.cnbc.com/2026/08/19/china-ai-nvidia-chips-us-export-controls.html">China AI firms tap Nvidia power overseas as U . S . weighs crackdown</a></li>

</ul>
</details>

**标签**: `#Nvidia Blackwell`, `#AI compute`, `#export controls`, `#Moonshot AI`, `#neocloud`

---

<a id="item-tech-news-8"></a>
### [欧盟指控 TikTok 推荐算法造成“兔子洞”效应](https://www.cnbc.com/2026/11/06/eu-charges-tiktok-harmful-algorithmic-rabbit-hole-effects.html) ⭐️ 7.0/10

欧盟委员会指控 TikTok 的个性化推荐可能形成有害的“兔子洞”效应，并称平台未采取有效措施应对相关风险，涉嫌违反《数字服务法》。欧盟要求其调整“For You”推荐逻辑、更多依据用户明确偏好、改进控制选项并定期测试算法，以应对持续推送相似内容可能带来的心理健康影响。如果问题未获解决，母公司字节跳动可能面临最高相当于全球年营收 6% 的罚款；目前这仍属于更广泛调查中的监管指控，而非最终违规裁定。

telegram · zaihuapd · 11月6日 14:03

**「既有监管程序」** 这并非欧盟首次审查 TikTok 的《数字服务法》合规情况。2024 年 2 月 19 日，欧盟委员会启动正式程序，评估 TikTok 是否违反该法；TikTok 随后回应称不认同欧盟的部分解读。此次指控延续了既有程序，并将监管焦点进一步具体化为推荐机制的风险测试、整改和用户控制要求。

**「整改与罚款风险」** TikTok 需要调整推荐逻辑，更多依据用户明确偏好，并改进控制选项、定期测试算法；此次指控延续了欧盟 2026 年 2 月 6 日关于“成瘾式设计”的初步认定，此前被指出的时间管理工具易被忽略、家长控制启用成本偏高，意味着整改将涉及推荐机制与用户控制界面的可用性。若问题未获解决，TikTok 母公司字节跳动 2027 年可能面临最高相当于全球年营收 6%的罚款。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://m.mp.oeeee.com/a/BAAFRD0000202505161086787.html">TikTok 回 应 欧 盟 指 其违反 数 字 服 务 法 ：部分解读不认同 | 南都N视频</a></li>
<li><a href="https://m.mp.oeeee.com/a/BAAFRD0000202602071521970.html">事关成瘾 性 设 计 ！ 欧 盟 调查 TikTok ，释放何种信号 | 南都N视频</a></li>
<li><a href="https://tech.ifeng.com/c/8qYIm39yTed">被 欧 盟 认定存在上瘾式设 计 ， TikTok 回应：调查结果完 全 错误_凤凰网</a></li>

</ul>
</details>

**标签**: `#TikTok`, `#推荐算法`, `#欧盟《数字服务法》`, `#算法监管`, `#平台安全`

---

<a id="item-tech-news-9"></a>
### [淘宝 MNN 开源 0.3B 手机端模型](https://www.ithome.com/1/023/212.htm) ⭐️ 7.0/10

淘宝 MNN 团队开源了约 3 亿参数的端侧模型 MNN-Pocket-0.3B，并分别提供预训练、后训练和端侧部署版本，供移动端 AI 开发者使用。据报道，该模型可在 iPhone 18 Pro 上完全离线运行，平均解码速度约为 350 token/s，INT4 部署文件为 173 MB。团队将峰值内存低于 300 MB、解码速度超过 200 token/s 作为目标，最终采用 28 层结构并将词表从 151K 精简至 64K；不过现有信息未提供模型质量评测、许可证或同类模型对比数据。

telegram · zaihuapd · 11月6日 15:13

**「端侧模型部署背景」** “0.3B”指约 3 亿参数，“INT4”则是以 4 位整数保存部署权重，主要影响文件体积和内存开销，并不能说明模型质量。此次项目将产物拆分为预训练、后训练和端侧部署版本，分别对应训练、后训练与手机部署流程；团队以峰值内存低于 300 MB、解码超过 200 token/s 为目标，最终采用 28 层结构，并将词表从 151K 缩减至 64K。

**「移动端可打包的离线推理」** 移动应用开发者现在可以用 Apache-2.0 许可的 MNN-Pocket-0.3B 在手机端加入离线语言模型能力：其 INT4（W4A16）部署文件为 173MB、峰值内存低于 300MB，在 iPhone 18 Pro 上平均解码约 350 token/s，并支持最高 32K 上下文。集成方应使用 MNN 构建并针对目标设备复测性能，因为公开速度来自特定硬件，且现有材料未提供足够的模型质量评测，不能仅凭吞吐量判断实际任务效果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/taobao-mnn/MNN-Pocket-0.3B-MNN">taobao-mnn/MNN-Pocket-0.3B-MNN · Hugging Face</a></li>
<li><a href="https://www.modelscope.cn/models/MNN/MNN-Pocket-0.3B">MNN-Pocket-0.3B · Models</a></li>
<li><a href="https://github.com/alibaba/MNN">GitHub - alibaba/MNN: MNN: A blazing-fast, lightweight ... Taobao MNN Team Open-Sources 0.3B Mobile Model, Achieving 350 ... MNN module - github.com/alibaba/MNN - Go Packages Taobao MNN Team Open-Sources MNN-Pocket-0.3B; Offline ... MNN-Pocket-0.3B发布：173MB手机模型实测350 token/s - OpenAI Hub</a></li>

</ul>
</details>

**标签**: `#端侧 AI`, `#小语言模型`, `#模型部署`, `#开源模型`, `#移动端推理`

---

<a id="item-tech-news-10"></a>
### [Telegram 13.2 新增聊天内 HTML 互动消息](https://play.google.com/store/apps/details?id=org.telegram.messenger&amp;amp;hl=en_US) ⭐️ 7.0/10

Telegram 的 Android、iOS 和 macOS 客户端升至 13.2，Desktop 升至 7.4；开发者可用 HTML、CSS 和 JavaScript 制作直接在聊天中运行的互动消息，无需打开 Mini App，例如支持触控和进度保存的小游戏。群组与机器人话题新增从屏幕右侧展开话题列表的“侧边栏”布局，更新说明称该布局还会在频道私聊和“收藏”中自动启用。现有说明未提供具体 API、安全机制或旧版兼容范围，互动消息的部署条件与风险边界仍不明确。

telegram · zaihuapd · 11月6日 15:56

**「背景」** Telegram 的 Mini Apps 是由机器人提供、在独立界面中打开的嵌入式网页应用。此次引入的 HTMLBubbles 则把 HTML、CSS 和 JavaScript 交互组件直接放入聊天中，并允许组件响应用户与机器人的操作。

**「开发者影响」** 开发者现在可将 HTML、CSS 和 JavaScript 交互直接嵌入私聊、群组及机器人话题，无需像 Mini App 那样先打开独立应用，从而缩短用户的交互路径。实现时应在 Android、iOS、macOS 13.2 和 Desktop 7.4 客户端中验证；TelegramMessenger 的 widget-sandbox 被描述为“无网络”沙箱，因此依赖外部网络请求的方案不能直接按普通网页方式处理，第三方客户端还须遵守 Telegram 的隐私与安全准则。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://vgtimes.com/tech-and-hardware/173701-telegram-13.2-adds-interactive-html-widgets-and-games-to-chats.html">Telegram 13.2 Adds Interactive HTML Widgets and Games to Chats</a></li>
<li><a href="https://github.com/TelegramMessenger/widget-sandbox">GitHub - TelegramMessenger/widget- sandbox · GitHub</a></li>
<li><a href="https://core.telegram.org/api/terms">Terms of Service that all third - party client apps must comply with.</a></li>

</ul>
</details>

**标签**: `#Telegram`, `#HTML 消息`, `#JavaScript`, `#Mini Apps`, `#客户端更新`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [与设计师协作的边界](https://seangoedecke.com/working-with-designers/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月7日 00:00

**「背景」** 作者以工程师视角回忆与设计师协作：设计师常能把他并不满意的占位界面，变成他无法凭技术想象出的更好版本，因此他珍视这种合作，也警惕设计工作的组织成本。他集中质疑“多名设计师”和设计系统（可复用前端组件库）的常规用法，认为真正的难点是审美分歧、全局改动与既有技术约束的冲突。

**「方案」** 在一次三人设计师团队中，两位资深设计师接替原设计师后立即重做产品，随后又互相推翻对方意见，页面往返三四轮；作者只能逐版实现，直到上线前一周才借两层管理层冻结设计，但发布前仍持续改动。据其跨团队经验，他主张同一产品只保留一名设计师，因为多设计师容易陷入以品味为核心、缺少客观尺度且牵动全局的争论，“开会达成一致”并不奏效。设计系统虽是统一大规模 UI 的少数办法，却有激励与兼容问题：维护者希望组件永远优雅，产品团队却要满足不规则需求；系统若基于新版 React，而存量应用仍是旧版 React、Angular 或纯 HTML/CSS，设计师所见与工程师可用版本便不同，迫使团队重写组件、用 CSS 覆盖，甚至直接嵌入组件。他并不否定设计系统：版本同步、需求普通时它很有效，但应区分视觉设计与 API 等技术工作；API、计费或 Markdown/PDF 渲染等团队未必需要视觉设计师，而 Netlify Analytics 难用仍有人购买、Azure 后台不美却做大生意的例子，被他用来质疑设计总是业务关键。

**「启示」** 作者的核心结论是：设计能显著提升产品，但只有收束视觉决策、让设计系统兼容存量技术并划清视觉与架构职责，设计收益才不会淹没在反复改版和工程绕行中。

**标签**: `#design-systems`, `#engineering-management`, `#frontend-engineering`, `#product-design`

---

