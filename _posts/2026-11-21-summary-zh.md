---
layout: default
title: "Horizon Summary: 2026-11-21 (ZH)"
date: 2026-11-21
lang: zh
---

> 从 35 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [陶哲轩文章公布 GRH 与非受迫纳维–斯托克斯奇性主张](#item-tech-news-1) ⭐️ 9.0/10
2. [Inkling 2 Mini：开放权重模型采用循环架构与 NVFP4 训练](#item-tech-news-2) ⭐️ 8.0/10
3. [SEC 据报调查英伟达潜在会计问题](#item-tech-news-3) ⭐️ 7.0/10
4. [Signal 推动限制移动 AI 代理读取敏感数据](#item-tech-news-4) ⭐️ 7.0/10
5. [美国收紧东南亚芯片出口，印度加码 AI 算力](#item-tech-news-5) ⭐️ 7.0/10
6. [OpenAI 公测最长 8 小时后台模式](#item-tech-news-6) ⭐️ 7.0/10
7. [KVM 漏洞可让嵌套虚拟机读取 AMD 宿主内存](#item-tech-news-7) ⭐️ 7.0/10
8. [台积电暂停中国客户 16nm 及以下制程订单](#item-tech-news-8) ⭐️ 7.0/10
9. [特朗普拟以重税推动海外 AI 数据中心回流](#item-tech-news-9) ⭐️ 7.0/10

**科技博客**
1. [为什么输出缓存难以奏效](#item-tech-blog-1) ⭐️ 7.0/10

**财经新闻**
1. [阿里巴巴遭股东集体诉讼](#item-finance-news-1) ⭐️ 7.0/10
2. [北京拟禁止以正常损耗扣减租房押金](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [陶哲轩文章公布 GRH 与非受迫纳维–斯托克斯奇性主张](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 9.0/10

陶哲轩在博客发表题为《Unforced Navier–Stokes Singularity and the Generalized Riemann Hypothesis》的文章，介绍其所称的广义黎曼猜想（GRH）以及非受迫纳维–斯托克斯方程奇性结果。转述材料称，Anthropic 数学家 Levent Alpöge 借助 Claude 证明黎曼猜想，并将证明用 Lean 形式化发布，详细文稿超过 25 万页；讨论中援引陶哲轩的话称，该证明似乎用到了朗兰兹纲领与算术几何的现代发展。一名评论者称两个独立的 Lean 内核均接受了该形式化，这降低了单一内核漏洞造成假阳性的风险，但只直接支持编码后的命题通过了内核检查。所给转述仍写有“若验证通过”，且未说明公理依赖、陈述对应关系或独立数学审查情况，因此目前更准确的状态是博客文章、Lean 形式化和双重内核检查信号已经公开，而非相关猜想已经获得公认的最终证明。

hackernews · archon1410 · 11月20日 17:21 · [社区讨论](https://news.ycombinator.com/item?id=50578358)

**「相关数学进展的前置脉络」** 广义黎曼猜想（GRH）是比黎曼猜想更一般的猜想，因此“证明黎曼猜想”的转述本身并不等于已经证明 GRH。Tao 在帖文中说明，非受迫 Euler 奇性此前已由 OpenAI 证明，并在受迫 Navier–Stokes 奇性结果的同一天公布；当前帖子把这项已有进展与新的非受迫 Navier–Stokes 奇性及 GRH 讨论并列呈现。Lean 形式化提供的是可由内核检查的证明记录，不应直接等同于数学共同体已对结论完成独立复核。

**「机器验证与复核重点」** 如果报道所称的 25 万余页 Lean 形式化确实通过独立内核检查，数学家就能用可重复的软件检查复核证明，而不必仅依赖人工逐行审阅论文；这也将成为 Claude 参与“生成证明—形式化验证”流程的大规模案例。即便如此，独立研究者仍需核对形式化陈述是否准确对应目标猜想以及证明依赖是否可信，因为现有消息只转述了验证结果，未独立确认数学结论。

**「评论中的核验与担忧」** 评论者一方面把两个独立 Lean 内核的接受结果视为较强的技术核验信号，另一方面指出这并不等同于确认形式化陈述与原始数学主张完全对应。另一部分讨论质疑现有 AI 方法是否只能重组既有抽象，并表达了对研究者职业前景和安全的个人不安；这些属于观点与疑问，不是证明正确性的证据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/">Unforced Euler singularity, unforced Navier - Stokes singularity , and...</a></li>

</ul>
</details>

**标签**: `#generalized Riemann hypothesis`, `#Navier–Stokes equations`, `#AI-assisted theorem proving`, `#Lean formalization`, `#machine-checked mathematics`

---

<a id="item-tech-news-2"></a>
### [Inkling 2 Mini：开放权重模型采用循环架构与 NVFP4 训练](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 8.0/10

Thinking Machines 推出 Inkling 2 Mini，这是一款面向本地推理的开放权重小型语言模型，采用循环式 Transformer 架构，并以 NVFP4 低精度格式进行端到端训练。现有报道将其基准表现描述为具有竞争力，但真实场景验证仍不完整；早期社区测试称，模型在 Ryzen 395 上通过 llama.cpp Vulkan 解码可达约 27 token/s，在 32GB M1 Pro 上以 q4\_xl 量化运行时约为 10 token/s。当前部分 llama.cpp Vulkan 改进仍依赖尚未合并的 PR，另有测试者称应用一个小型补丁可再提升约 30% 速度。

hackernews · jasondavies · 11月20日 20:12 · [社区讨论](https://news.ycombinator.com/item?id=50581260)

**「技术背景」** 循环式 Transformer 通过重复调用同一组网络层或参数来增加有效计算深度，目标是在不按比例扩大参数量的情况下提升模型能力，这也是 Inkling 2 Mini 与常规单次前向 Transformer 的主要结构差异。所谓“端到端 NVFP4 训练”表示训练过程本身采用 NVFP4 低精度数值格式，而不只是训练完成后再做一次 4 位权重量化，因此主要关系到训练阶段的内存和计算需求。官方将 Inkling 2 Mini 定位为总参数少于 1000 亿的开放权重模型；“开放权重”意味着开发者可以取得参数并在本地运行，但本身并不保证训练数据、训练代码或完整复现流程也已公开。

**「对本地推理用户的实际影响」** 社区早期实测显示该模型已具备可用的本地推理表现：一名用户称在 Ryzen 395 上通过 llama.cpp 的 Vulkan 后端达到约 27 token/s 的解码速度，另一名用户则在 32GB M1 Pro 上以 q4 XL 量化运行约 10 token/s。不过，这些结果依赖尚未合并的 llama.cpp PR（32694、32657、32429、32704），且报告者使用了一个非官方补丁并声称可再提速约 30%；用户当前评估性能时应同时核对后端、量化方式和补丁状态，不能直接将其视为已稳定复现的速度。

**「社区关注实际性能与循环架构风险」** 一位评论者认为，如果 Inkling 2 Mini 的基准优势能在真实任务中成立，其接近大型 Qwen 模型的循环架构表现将很有价值；其他用户则报告了成功的编程测试和本地运行速度。也有人担忧，循环式模型在广泛开放后，其安全性和可解释性是否会受到影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>

</ul>
</details>

**标签**: `#small language models`, `#looped transformers`, `#open weights`, `#local inference`, `#quantization`

---

<a id="item-tech-news-3"></a>
### [SEC 据报调查英伟达潜在会计问题](https://www.marketscreener.com/news/us-sec-s-nvidia-probe-is-examining-potential-accounting-issues-sources-say-ce785ed3dd8ff627) ⭐️ 7.0/10

据报道，美国证券交易委员会（SEC）正在调查英伟达可能存在的会计问题。现有材料未披露具体会计科目、涉及交易、调查时段或潜在违规行为，也未说明 SEC 是否已作出任何认定，因此目前只能确认调查被媒体曝出，不能视为已经发现账务违规。

hackernews · ftchd · 11月20日 20:22 · [社区讨论](https://news.ycombinator.com/item?id=50581438)

**「SEC 调查的制度背景」** 美国证券交易委员会（SEC）可针对涉嫌违反证券法规的问题提起民事诉讼或启动行政程序，但本身没有刑事执法权，必要时需将刑事案件移送检察机关。此次报道仅称 SEC 正调查 Nvidia 的潜在会计问题，尚未披露具体事项、证据或结论，因此不能视为已经认定违规。

**「调查或传导至 GPU 需求」** 目前报道未说明 SEC 调查的具体范围，也没有任何违规认定；若潜在会计问题涉及 Nvidia 对 neocloud 的融资安排，并促使公司收紧支持，相关 GPU 云厂商的融资难度可能上升，进而削弱 GPU 采购需求。这一风险源于其“循环融资”模式：Nvidia 提供资本或承诺，neocloud 用其购买 Nvidia GPU，并向 Nvidia 返还部分收入；投资者应重点关注相关资本承诺和收入确认披露是否变化。

**「社区质疑调查范围」** 部分评论者将此案与英伟达过去五年的“循环融资”、以股票换取折价芯片等安排联系起来，并质疑公司为何让长期担任 CFO 的 Colette Kress 出任临时 CEO。还有人猜测可能涉及“黑市芯片销售”，但这些均属于评论者的怀疑，现有报道并未将其确认为 SEC 的调查事项或违法结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.m.wikipedia.org/wiki/United_States_Securities_and_Exchange_Commission">United States Securities and Exchange Commission - Wikipedia</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/nvidia-financing-role-neoclouds-faces-181433179.html">Nvidia ’s financing role for neoclouds faces scrutiny after CEO exit</a></li>
<li><a href="https://www.spheron.network/blog/nvidia-neocloud-backstop-financing-circular-gpu-2026/">NVIDIA &#x27;s Neocloud Backstop Financing Explained: What Circular ...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#SEC regulation`, `#accounting`, `#AI hardware`, `#semiconductors`

---

<a id="item-tech-news-4"></a>
### [Signal 推动限制移动 AI 代理读取敏感数据](https://signal.org/blog/protecting-your-privacy/) ⭐️ 7.0/10

Signal 介绍了限制移动操作系统中 AI 代理捕获敏感数据的工作，目标是阻止代理利用过宽的系统权限读取屏幕和应用内容。Signal 表示已取得一些进展并“谨慎乐观”，但现有材料没有说明适用系统版本、具体机制、部署时间或覆盖率，因此不能视为已全面阻断此类捕获。

hackernews · dotcoma · 11月20日 09:42 · [社区讨论](https://news.ycombinator.com/item?id=50572348)

**「移动系统 AI 代理」** 移动操作系统内置的 AI 代理可能接触设备上的应用数据，这是 Signal 需要处理代理捕获和保存其消息数据风险的技术背景。Signal 官方博客称其正限制最新移动系统 AI 代理对 Signal 数据的潜在访问，但现有摘要没有说明具体限制机制、适用的操作系统版本或实际覆盖范围。

**「隐私保护与功能兼容」** 移动 AI 代理若能读取屏幕和应用数据，就可能捕获聊天等敏感内容，因此代理开发者需要限制此类权限；但现有材料只说明 Signal 正在推动相关限制，并未给出平台覆盖范围、版本要求或防护效果。另据一名社区用户反馈，相关限制也使其无法在 Windows 上截取 Signal 对话，落地时需要兼顾防泄密与功能兼容性。

**「社区讨论」** 评论者认为，即使设备未安装 AI 应用，联系人使用具备系统权限的代理也可能间接暴露 Signal 聊天，因此主张加强操作系统层面的控制、明确告知用户，并建议使用 GrapheneOS 或 Linux 等替代方案。也有开发者希望 Signal 公开取证调查结果以形成协作资料库；另有用户报告 Windows 版无法截取 Signal 聊天界面，反映出隐私限制与常用取证功能之间的取舍。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://signal.org/blog/protecting-your-privacy/">Signal &gt;&gt; Blog &gt;&gt; Signal is Serious About Protecting Your Privacy</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#mobile OS security`, `#Signal`, `#data capture`, `#digital forensics`

---

<a id="item-tech-news-5"></a>
### [美国收紧东南亚芯片出口，印度加码 AI 算力](https://www.bloomberg.com/news/articles/2026-11-20/nvidia-scandal-fallout-india-ai-yotta-ambani-adani-am-intelligence-e2e-networks) ⭐️ 7.0/10

美国已收紧对马来西亚、泰国和新加坡的先进芯片出口，印度 AI 业界认为本国可能承接由此外溢的算力需求。Yotta 称未来一年将新增约 10 万块 GPU，相当于印度现有算力再增约 10%，但这属于企业计划而非已交付能力。印度目前拥有 153 个数据中心、全球排名第 14，Reliance 承诺投入最高 1100 亿美元，Adani 计划投入 1000 亿美元建设 AI 基础设施，但算力短缺和资本受限仍是长期约束。该消息是 Telegram 对 Bloomberg 报道的简要转述，尚未提供出口管制细则及新增产能的具体落地情况。

telegram · zaihuapd · 11月20日 07:31

**「出口管制瞄准算力流向」** 理解这一机会需要先区分两类管制：2025 年 7 月，美国已计划限制向马来西亚和泰国运送 AI 芯片，以防其成为流向中国的渠道；此后公布的商务部临时规则又要求新加坡、马来西亚、泰国、印尼和巴西的数据中心运营商限制中国公司远程访问先进 AI 芯片和服务器。后者表明管制针对的不只是 GPU 在哪里安装，还包括算力最终流向，因此所谓“外溢需求”并不等同于印度可以无条件承接。

**「新增算力不能按规划量直接采购」** 对需要在印度获取先进 GPU 的云客户，Yotta 被列为 NVIDIA B200 的云供应方，企业可据此将 B200 的云端分配纳入采购询价；但信实 1100 亿美元和阿达尼 1000 亿美元的基础设施投入仍属投资承诺，并非已上线容量。签订长期算力合同前，企业应确认 B200 的交付批次、实际上线时间及美国出口限制对相关采购路径的适用性，避免把规划产能当作即时可用库存。

<details><summary>参考链接</summary>
<ul>
<li>The Trump administration moved to restrict foreign countries from giving Chinese companies remote access to advanced AI chips and servers, amid scrutiny over its semiconductor e</li>
<li>US Plans AI Chip Curbs on Malaysia, Thailand Over China Concerns - Bloomberg</li>
<li><a href="https://www.linkedin.com/posts/nextround-ai_adani-ai-techpartnership-activity-7429929884497567744-M_T1">Adani Expands Capacity with 5GW Data Centers , Partners... | LinkedIn</a></li>
<li><a href="https://worldtradescanner.com/India+AI+Summit+Spurs+Global+Declarations+and+$200B+Investments.htm">worldtradescanner.com/ India AI Summit Spurs Global Declarations...</a></li>
<li><a href="https://analyticsindiamag.com/ai-news-updates/with-34000-gpus-indiaai-mission-backs-soket-ai-gnani-ai-gan-ai-for-foundation-models/?trk=article-ssr-frontend-pulse_little-text-block">How is IndiaAI Supporting Local AI Startups? | Analytics India Magazine</a></li>

</ul>
</details>

**标签**: `#AI chips`, `#export controls`, `#AI infrastructure`, `#data centers`, `#India`

---

<a id="item-tech-news-6"></a>
### [OpenAI 公测最长 8 小时后台模式](https://developers.openai.com/api/docs/guides/background) ⭐️ 7.0/10

OpenAI 正公测 API 后台模式，开发者可设置 background: true，并选择 2 小时或 8 小时的完成窗口，以异步执行长耗时请求。对应 token 费率较标准价低 30% 和 40%；未指定窗口时使用默认的 soonest，不享受折扣。该公测目前适用于 GPT-6.2 Astra、GPT-6.2 Sol、GPT-6.1 Terra 和 GPT-6 Luna。后台模式会临时存储响应数据，即使请求设置 store: false 或启用零数据保留也不例外，因此相关 API 用法仍需经过数据合规评估。

telegram · zaihuapd · 11月20日 11:15

**「相关模型此前的 API 进展」** Horizon 11 月 18 日的日报曾报道，GPT-6.2 Astra 与 Sol 已分别以 gpt-6.2-astra 和 gpt-6.2-sol 开放 API 调用；现在两者被纳入后台模式公测，可按所选完成时限享受相对标准价 30% 或 40% 的 token 折扣。Horizon 10 月 27 日的日报还报道，GPT-6.1 Terra 当时已开放，其标准 API 定价为每百万输入、缓存输入和输出 token 分别 1、0.05 和 5 美元；此次变化是为既有模型增加后台执行方式及折扣资格，而非重新发布模型。

**「开发者影响与合规注意」** 需要执行长时间异步任务的开发者可设置 \`background: true\`，并选择 \`2h\` 或 \`8h\` 完成窗口；在参与公测的 GPT-6.2 Astra、GPT-6.2 Sol、GPT-6.1 Terra 和 GPT-6 Luna 上，Token 费率可分别比标准价低 30% 和 40%。但后台模式会临时存储响应数据，即使设置 \`store: false\` 或启用零数据保留也不例外，因此受数据驻留或零保留要求约束的组织在采用前需评估这一数据处理风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/introducing-gpt-6-2-astra-sol/">2026-11-18 — OpenAI 发布 GPT-6.2 Astra 与 Sol</a></li>
<li><a href="https://openai.com/index/introducing-gpt-6-1-terra/">2026-10-27 — OpenAI 发布 GPT-6.1 Terra，API 价格减半</a></li>

</ul>
</details>

**标签**: `#OpenAI API`, `#异步任务`, `#大模型`, `#API 定价`, `#数据保留`

---

<a id="item-tech-news-7"></a>
### [KVM 漏洞可让嵌套虚拟机读取 AMD 宿主内存](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 7.0/10

Linux 内核 KVM 的 CVE-2026-99312 据报道仅影响启用了嵌套虚拟化的 AMD 主机，攻击者可从虚拟机内读取宿主内存。研究人员在 DigitalOcean 上实际读出了约 127 GB 宿主内存，但报道未披露漏洞原理或利用细节。上游修复已于 11 月 18 日随稳定内核 7.3.5 等版本发布，Debian、Ubuntu 等发行版当时尚未更新；在补丁部署前，可通过关闭嵌套虚拟化缓解风险。

telegram · zaihuapd · 11月20日 14:23

**「背景：KVM 嵌套虚拟化缺陷」** KVM 是内置于 Linux 内核的虚拟机监控器；启用嵌套虚拟化后，客户机系统能够使用底层虚拟化能力，从而进入原本仅供宿主机使用的相关代码路径。CVE-2026-99312 的技术根源是 KVM 中的失效指针，研究人员称，该缺陷在 Linux 内核中存在近四年，源于一项安全修复。

**「受影响主机应暂停嵌套虚拟化」** 启用嵌套虚拟化的 AMD 主机管理员应在 Debian、Ubuntu 等发行版内核合入修复前关闭该功能；DigitalOcean 的测试中，攻击者已从虚拟机读取约 127 GB 宿主内存。上游稳定内核 7.3.5 的修复已于 11 月 18 日发布，发行版用户需等待并部署包含该补丁的内核后再恢复嵌套虚拟化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.digitalocean.com/blog/cve-2026-99312-kvm-patch">Virtualization , Responsible Disclosure, and CVE - 2026 - 99312</a></li>
<li><a href="https://www.terra.security/blog/kvm-guest-to-host-escape">KVM Guest-to-Host Escape | Terra Security Research</a></li>

</ul>
</details>

**标签**: `#KVM`, `#Linux 内核`, `#AMD 虚拟化`, `#CVE-2026-99312`, `#内存泄露`

---

<a id="item-tech-news-8"></a>
### [台积电暂停中国客户 16nm 及以下制程订单](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 7.0/10

据 AppleInsider 报道，台积电已通知客户暂停接受中国企业 16nm 及以下制程的芯片订单；按收紧后的美国半导体出口新规，除非事先取得美国出口许可或豁免，否则不得供货，台积电表示将遵守新规。关键变化在于审批流程：此前台积电可自行评估客户设计是否符合豁免条件，现在必须由客户提前向美国申请，而美国已获批名单中出现苹果、AMD 和英伟达，尚无中国公司。报道称，中国客户因此只能使用 28nm、40nm 等成熟制程，且无法获得 AI 数据中心所需的高带宽内存。需注意该报道为二手转述，未附新规原文或台积电官方公告全文，具体的许可口径、豁免适用条件与执行时间表仍待官方信息确认。

telegram · zaihuapd · 11月21日 02:01

**「出口管制政策背景」** 据当前报道，此前由台积电自行评估客户设计能否获得豁免的流程，已改为客户须就中国客户的 16nm 及以下订单预先申请美国许可或豁免；台积电表示将遵守新规，但报道未附规则原文或生效条款。Horizon 11 月 17 日的日报还曾报道，美国商务部工业与安全局于 11 月 16 日发布临时最终规则，将先进 AI 芯片及相关服务器的管制延伸至远程访问，并要求向印度尼西亚、马来西亚、新加坡、泰国和巴西再出口时申请许可；这提供了更广的政策背景，但不能据此确认该规则与此次 16nm 暂停令属于同一项规则。

**「对中国芯片项目的影响」** 若报道所述措施已经生效，未提前取得美国许可或豁免的中国客户将无法向台积电提交 16nm 及以下制程订单，依赖该工艺的项目必须改用 28nm、40nm 等节点，或先完成许可申请。相关芯片设计因此需要重新进行工艺适配、流片和封装验证，可能延后上市；由于报道未附美国规则原文或台积电正式通知，企业仍需核对具体订单范围和许可条件。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/">2026-11-17 — 美国将先进 AI 芯片管制延伸至远程访问</a></li>

</ul>
</details>

**标签**: `#半导体`, `#出口管制`, `#台积电`, `#中国芯片`, `#AI硬件`

---

<a id="item-tech-news-9"></a>
### [特朗普拟以重税推动海外 AI 数据中心回流](https://apnews.com/article/trump-artificial-intelligence-data-centers-f1ac03b73d13445400eeed8631d9d879) ⭐️ 7.0/10

特朗普在 11 月 20 日的白宫记者会上表示，拟对在海外建设 AI 数据中心的美国科技公司征收“巨额税款”，以促使项目留在美国，并维持美国相对中国的 AI 竞争优势。他同时敦促美国各地接纳数据中心，并建议社区与开发商谈判、由开发商向社区付款，以应对新建项目带来的用电和噪音争议。这目前只是政策表态；税种、税率、适用对象、执行范围和实施时间均未公布，也尚无已落地规则。

telegram · zaihuapd · 11月21日 03:26

**「此前的投资与选址背景」** 11 月 4 日的 Horizon 摘要曾报道，美国大型科技公司围绕 AI 基础设施的财务承诺半年内增长约 90% 至 3.2 万亿美元，涉及数据中心租赁、云与算力采购及电力供应等合同，但未说明其中多少对应海外项目。相较于此前对投资规模的披露，此次新增的是特朗普提出拟对在海外建设 AI 数据中心的美国科技公司征收“巨额税款”；面对多地社区因用电和噪音提出的反对意见，他还建议开发商与社区谈判并向社区付款。该构想尚未公布税种、税率、适用范围或实施时间。

**「数据中心选址与社区成本变化」** 若这项计划最终落地并实施，美国科技公司在海外建设 AI 数据中心将新增税负，可能促使其重新评估海外算力项目并偏向美国本土；但税种、税率、适用范围和生效时间尚未公布，当前无法量化对选址的影响。美国本地社区也可能以用电压力和噪音为由，在审批谈判中要求开发商提供付款或补偿承诺。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://asia.nikkei.com/business/technology/artificial-intelligence/us-tech-giants-hidden-ai-debt-swells-90-to-3.2tn-in-6-months">2026-11-04 — 日经：美科技巨头 AI 相关承诺半年增 90% 达 3.2 万亿美元</a></li>

</ul>
</details>

**标签**: `#AI数据中心`, `#美国科技政策`, `#跨境税务`, `#算力基础设施`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [为什么输出缓存难以奏效](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 7.0/10

rss · Sean Goedecke · 11月21日 00:00

**「背景」** LLM 推理通常会缓存输入，以免每轮重算完整对话历史；由于输出 token 的生成比输入摄取更贵，作者追问：代理反复引用代码、证据文档或既有回答时，是否也应缓存输出来避免浪费。

**「方案」** 一种直接做法是微调模型或调整提示，让它输出“src/script.py:12-15”之类的引用而非重复原文，再由代理框架展开这些引用；作者认为，这仍然只是在优化用户可见输出。按他自己的代理历史，输出 token 约 50% 是推理、44% 是工具调用、仅 6% 对用户可见，因而不可见的生成占 94%。即便非常乐观地省掉三分之二的可见 token，依据 Amdahl 定律也只会把总输出 token 节省约 4%，所以真正值得优化的是那 94%，而不是重复展示的 6%。作者进一步认为，核心手段是让模型更聪明，以更少的推理和工具调用抵达正确答案；他据此指出，单 token 贵 5 倍但用量少 6 倍的模型，总成本反而可能更低。与此同时，他猜测成熟推理服务可能已使用基于历史 n-gram 的推测解码来加速重复输出，因此“重复可被利用”并不等同于应建立面向代理响应的输出缓存。不过，6%/94% 的拆分来自作者个人历史，而且他无法读取前沿模型的思维链，只对成熟模型很少在内部推理中循环保持中等信心；工具调用是否也大量重复同样尚不确定。

**「启示」** 作者的核心结论是：参考式输出缓存通常只能压缩很小一部分代理成本，真正有效的杠杆是减少不可见的推理与工具调用，也就是用更高的模型能力换取更短的任务执行轨迹。

**标签**: `#LLM inference economics`, `#output caching`, `#AI agents`, `#Amdahl&\#x27;s law`, `#token optimization`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [阿里巴巴遭股东集体诉讼](https://www.zaobao.com.sg/news/china/story20261120-10029652) ⭐️ 7.0/10

阿里巴巴 11 月 19 日在纽约曼哈顿联邦法院遭股东集体诉讼，原告指控其在 2024 至 2026 年年报中低估出口管制违规风险，并隐瞒与 Alice Huang 及新加坡公司超速国际的业务关系。诉状称，相关消息与阿里股价随后四个交易日下跌 14%有关，赔偿金额未列明；阿里巴巴尚未回应，首席执行官吴泳铭也被列为被告。

telegram · zaihuapd · 11月20日 09:32

**「背景」** 2023 年，诉状所指的 Alice Huang 与丈夫康伟曾在上海向投资者推介一项在东南亚建立人工智能业务的计划。

**「投资者影响」** 原告称，有关阿里巴巴隐瞒出口管制风险及业务关系的报道公布后，其股价在四个交易日内下跌 14%，令持股投资者承受较大账面损失；相关指控及其与股价下跌的因果关系仍待法院验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cn.nytimes.com/technology/20261119/nvidia-alibaba-china-military/">cn.nytimes.com/technology/20261119/nvidia-alibaba-china-military</a></li>

</ul>
</details>

**标签**: `#阿里巴巴`, `#股东诉讼`, `#出口管制`, `#公司治理`

---

<a id="item-finance-news-2"></a>
### [北京拟禁止以正常损耗扣减租房押金](https://mp.weixin.qq.com/s/PmGxh5knIyxiBRhpRoJnoQ) ⭐️ 7.0/10

北京市住建委、市场监管局起草的住房租赁合同示范文本修订稿公开征求意见，拟明确承租人正常使用房屋产生的合理损耗不得作为扣减押金依据。征求意见稿还要求转租经营企业将押金存入监管账户，并强化押金、租金监管及个人信息保护；目前尚未生效。

telegram · zaihuapd · 11月20日 13:46

**「背景」** 此次文件由北京市住建委和市场监管局起草，用于修订现行住房租赁合同示范文本，目前仍处于公开征求意见阶段。

**「潜在影响」** 对北京承租人和转租经营租赁企业而言，征求意见稿若最终通过并实施，房东将不得以正常损耗为由扣减押金，转租经营企业也须将押金存入监管账户并接受更严格的租金监管。

**标签**: `#北京住房租赁`, `#押金监管`, `#租赁企业`, `#个人信息保护`

---