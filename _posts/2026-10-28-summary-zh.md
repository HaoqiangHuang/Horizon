---
layout: default
title: "Horizon Summary: 2026-10-28 (ZH)"
date: 2026-10-28
lang: zh
---

> 从 41 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [有限简单群分类的 Lean 形式化](#item-tech-news-1) ⭐️ 8.0/10
2. [Google DeepMind 发布 Genie 4 世界模型](#item-tech-news-2) ⭐️ 7.0/10
3. [Discord 计划开放公开服务器消息的搜索收录](#item-tech-news-3) ⭐️ 7.0/10
4. [苹果发布配备 M6 的 14 英寸 MacBook Pro](#item-tech-news-4) ⭐️ 7.0/10
5. [Tailscale SSH 漏洞调查与修复更新](#item-tech-news-5) ⭐️ 7.0/10
6. [Python 实验性 JIT 据报将被移除](#item-tech-news-6) ⭐️ 7.0/10
7. [Ψ-0.6：统一视觉语言模型的自适应思维流](#item-tech-news-7) ⭐️ 7.0/10
8. [中国团队声称实现 3.2 Pb/s 光纤实时传输](#item-tech-news-8) ⭐️ 7.0/10
9. [微软修复 Authenticator 安卓版令牌窃取漏洞](#item-tech-news-9) ⭐️ 7.0/10
10. [Anthropic 确认研究人员访问内部系统](#item-tech-news-10) ⭐️ 7.0/10
11. [Google 睡眠框架巩固持续学习参数](#item-tech-news-11) ⭐️ 7.0/10

**财经新闻**
1. [泡泡玛特第三季度营收同比下降 45%至 50%](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [有限简单群分类的 Lean 形式化](https://cfsg.axiommath.ai/) ⭐️ 8.0/10

据标题和项目链接，cfsg.axiommath.ai 提供了有限简单群分类的 Lean 形式化，面向群论研究者、形式化开发者以及需要可机检证明库的用户。现有材料没有说明形式化覆盖了原证明的哪些部分、采用何种 Lean 与数学库版本、能否完整构建或是否经过独立验证，因此尚不能确认它等同于一份全面验证的分类证明。附带来源正文与标题存在明显错配：它转述 OpenAI 公布局部光滑化猜想、反证 ETH 和四维杨–米尔斯存在性三项模型科研结果，并称计算机科学组已即时公开证明及 Lean 形式化；这些是发布方所称的成果，既未获材料中的独立验证，也不能作为 CFSG 形式化的技术依据。

hackernews · pfdietz · 10月27日 16:29 · [社区讨论](https://news.ycombinator.com/item?id=50261647)

**「背景」** 有限简单群分类（CFSG）是一项对所有有限简单群进行系统分类的群论定理。Axiom Math 的项目页称，该 Lean 形式化沿用 CFSG 的第一代证明，并由 Lean 内核检查每一个逻辑步骤，因此它覆盖的是完整的分类论证，而非零散定理的形式化。

**「机器验证的分类定理可供后续证明依赖」** 该成果把“有限单群必为素数阶循环群、交错群、Lie 型群或 26 个散在群之一”的完整分类证明纳入 Lean，并由 Lean 内核逐步检查；后续 Lean 项目因此可以引用这一机器验证版本，而不必重新处理原证明数千页的论证。需要注意，它沿用第一代分类证明，提供的是可复用的验证基础，而不是一套独立于既有证明的新论证。

**「自动形式化能否取代协作」** 社区最关注自动形式化能否把既有证明一次性转成长期可复用的 Lean 库：mlmonkey 提出将所有教科书证明自动形式化的设想，sebzim4500 则以分类证明曾发现遗漏散在群、原证明需要约百名数学家协作为由，认为这一过程仍离不开大型协作。vessenes 称项目团队在既有 1,000 多页证明中发现并补上了一个缺口，但这是评论者说法，现有材料没有予以独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cfsg.axiommath.ai/">CFSG in Lean</a></li>
<li><a href="https://cfsg.axiommath.ai/">CFSG in Lean</a></li>
<li><a href="https://cfsg.axiommath.ai/papers">Papers – CFSG in Lean</a></li>

</ul>
</details>

**标签**: `#Lean`, `#formal verification`, `#theorem proving`, `#group theory`, `#mathematics`

---

<a id="item-tech-news-2"></a>
### [Google DeepMind 发布 Genie 4 世界模型](https://deepmind.google/blog/genie-4-a-new-generation-of-world-simulation/) ⭐️ 7.0/10

Google DeepMind 宣布 Genie 4，这是一款由 Gemini 系列模型支撑、以 Gemini 3.8 Flash 作为引导代理拆解多步任务的世界模型；官方称其能够实时生成画面、环境音和可交互对话，并允许用户用自然语言中途修改场景。研究预览先向可信测试者开放，随后计划面向 Project Genie Ultra 订阅者以及 Gemini API、AI Studio 合作伙伴开放，生成内容将带有 SynthID 水印。官方材料未提供量化基准或独立验证，而社区示例显示物体和人物在离开画面后可能发生变化，模型在乐器指令及照片级写实要求上也有不稳定表现。

hackernews · acossta · 10月27日 16:06 · [社区讨论](https://news.ycombinator.com/item?id=50261319)

**「研究预览与评测尺度」** Genie 4 采用分阶段研究预览：Google DeepMind 先向可信测试者开放以收集反馈，随后再面向 Project Genie 的 Google AI Ultra 订阅者，以及 Gemini API 和 Google AI Studio 的早期合作伙伴。判断其“世界模拟”能力时，还应区分即时生成效果与跨时间的状态一致性；社区观察者报告对象离开画面再出现后可能改变身份或属性，但这属于体验反馈，并非官方基准已经证实的结论。

**「接入方应新增音画连续性测试」** 对计划接入 Gemini API 或 AI Studio 的团队，Genie 4 的验收范围应扩展到实时音画交互，而不只是视频清晰度：官方称其首次为 DeepMind 世界模型加入原生环境音和提示指定音频，社区样例却出现提示要求 saxophone、输出却像 clarinet，以及物体离开画面再返回后头盔、城堡或人物状态改变的情况；这些是用户观察而非系统性基准，但足以要求接入方单独测试音频提示遵循和跨帧连续性。当前仅向可信测试者提供研究预览，后续才面向 Project Genie Ultra 订阅者及 API、AI Studio 合作伙伴，团队还需在正式开放后验证带 SynthID 标记的输出如何被下游系统处理。

**「一致性不足引发质疑」** 评论者举例称，城堡、站台行人和香港摩托车手在离开画面后再次出现时发生了变化，因此认为 Genie 4 对画面内对象的一致性尚可，却不足以证明其已经具备所宣称的世界模拟能力。另有测试者指出，系统会把要求的萨克斯风变成单簧管，并且在反复要求照片级写实、排除游戏画面时仍输出游戏风格；这些属于社区观察，而非系统性基准结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepmind.google/blog/genie-4-a-new-generation-of-world-simulation/">Genie 4: A new generation of world simulation — Google DeepMind</a></li>
<li><a href="https://deepmind.google/blog/genie-4-a-new-generation-of-world-simulation/">Genie 4 : A new generation of world simulation — Google DeepMind</a></li>
<li><a href="https://arstechnica.com/google/2026/10/deepminds-genie-4-world-model-adds-audio-and-more-realistic-people-to-simulations/">DeepMind unveils Genie 4 world model promising... - Ars Technica</a></li>

</ul>
</details>

**标签**: `#world models`, `#generative video`, `#audio generation`, `#AI research`, `#model consistency`

---

<a id="item-tech-news-3"></a>
### [Discord 计划开放公开服务器消息的搜索收录](https://discord.com/blog/making-content-from-discoverable-servers-easier-to-discover) ⭐️ 7.0/10

Discord 计划让公开服务器中的消息可被搜索引擎收录，以便外部用户通过网页搜索找到社区讨论；这一变化将影响服务器管理员、既有发帖者和普通成员。现有材料未说明上线时间、默认开关、历史消息处理方式或服务器规模门槛，而且有评论者指出文章并未明确将搜索范围限定为 Google。

hackernews · DeepLogin · 10月27日 18:44 · [社区讨论](https://news.ycombinator.com/item?id=50263854)

**「可发现服务器与既有网页机制」** Discord 的“可发现服务器”（Discoverable Servers）原本就是平台最公开的服务器类型：至少拥有 1,000 名成员，并由管理员选择列入 Server Discovery，任何人都无需邀请链接即可加入。此次并非首次为服务器建立网页入口；Discord 此前已有网站功能，并计划于 11 月 16 日面向所有可发现服务器启用，管理员仍可按频道选择退出，而本项变更是在此基础上进一步让服务器消息进入搜索引擎索引。

**「服务器管理员面临新的索引与审核责任」** 若 Discord 按计划将公开服务器消息纳入 Google 等搜索引擎索引，服务器的曝光将从 DISBOARD、Discords.com 等按关键词或标签查找服务器的目录入口扩大到具体发言内容，管理员和版主需要决定是否开放索引，并应对随之而来的垃圾内容、审核和成员隐私问题。社区成员反对按服务器规模或活跃度设置门槛，因为这可能排除速度竞赛、模组和 ROM 破解等小众社区；管理员还应明确新旧消息的处理规则，避免不再活跃成员的历史发言在缺乏告知的情况下被公开。

**「社区讨论」** 一名服务器管理员希望借此提升游戏社区讨论的曝光，但质疑如何告知现有及已不活跃用户；另一名管理员反对按成员数或活跃度设置资格门槛，主张不同规模的社区都应能选择加入或退出。评论者还担忧 SEO 垃圾信息会加剧审核，并有人赞成 Discord 走向更开放的网络，但质疑此时改变及是否应出售相关数据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://discord.com/blog/making-content-from-discoverable-servers-easier-to-discover">Making Content from Discoverable Servers Easier to Discover</a></li>
<li><a href="https://www.theverge.com/tech/1019827/discord-is-turning-on-websites-for-all-discoverable-servers">Discord is turning on websites for all Discoverable Servers . | The Verge</a></li>
<li><a href="https://disboard.org/search">Search Discord Servers | DISBOARD: Discord Server List</a></li>
<li><a href="https://discords.com/">Discord Server List - Discords .com</a></li>

</ul>
</details>

**标签**: `#Discord`, `#search indexing`, `#privacy`, `#platform moderation`, `#community discoverability`

---

<a id="item-tech-news-4"></a>
### [苹果发布配备 M6 的 14 英寸 MacBook Pro](https://www.apple.com/in/newsroom/2026/10/apple-introduces-the-new-14-inch-macbook-pro-with-m6/) ⭐️ 7.0/10

苹果宣布推出配备 M6 芯片的 14 英寸 MacBook Pro。当前材料未提供芯片规格、内存与存储配置、起售价、上市时间或地区可用性，也没有实测性能数据，因此尚无法判断 M6 相对前代在处理器性能、端侧 AI 能力和续航方面的实际提升。

hackernews · beex · 10月27日 16:08 · [社区讨论](https://news.ycombinator.com/item?id=50261352)

**「此次发布的直接背景」** 10 月 26 日的 Horizon 日报转述 Bloomberg 报道称，苹果计划当周推出首批触屏 MacBook Pro，包括 14 英寸和 16 英寸版本，并首次为 Mac 引入触控、OLED 和灵动岛；当时完整规格与最终价格尚未确认。10 月 27 日的苹果官方新闻稿确认了 14 英寸 M6 MacBook Pro，并提到性能、设备端 AI 和连接速度，但没有在该摘要中确认上述全部屏幕特性，因此不能把此前传闻直接视为已发布规格。

**「对专业创作者的实际影响」** 对从事 3D 建模、产品可视化和动画渲染的创作者，新款 14 英寸 MacBook Pro（M6）提供了面向这些专业工作流的明确升级方向；第三方发布信息还提到连接规格改进以及最长 24 小时续航，但续航仍是厂商公布的上限值，并非独立实测结果。现有资料未提供关键性能基准、完整配置价格或软件兼容性，采购者应先用实际项目验证性能，并核对所需接口、软件和外设支持后再决定换机。

**「社区讨论」** 部分评论者认为，基础 M 系列芯片与 Pro／Max 层级并行容易造成命名和定位混淆；也有用户不愿为售价 6000 美元以上的开发机配置付费，并表示将继续使用现有 M1 设备以延长服役期。另有评论主张依据离线模型规模、上下文长度以及处理和生成吞吐量衡量端侧 AI，而不是只看功能演示。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/newsletters/2026-10-25/apple-to-unveil-touch-screen-macbook-pro-executive-promotions-in-box-checker">2026-10-26 — 苹果将发布首款触屏 MacBook Pro</a></li>
<li><a href="https://www.apple.com/newsroom/2026/10/apple-introduces-the-new-14-inch-macbook-pro-with-m6/">Apple introduces the new 14 - inch MacBook Pro with M 6 - Apple</a></li>
<li><a href="https://www.apple.com/newsroom/2026/10/apple-introduces-the-new-14-inch-macbook-pro-with-m6/">Apple introduces the new 14 - inch MacBook Pro with M 6 - Apple</a></li>
<li><a href="https://www.macrumors.com/2026/10/27/14-inch-macbook-pro-with-m6-chip/">Apple Announces New 14 - Inch MacBook Pro With... - MacRumors</a></li>
<li><a href="https://www.youtube.com/watch?v=3lKQgcfYBYo">Apple’s M 6 MacBook Pro &amp; iMac: Everything New! - YouTube</a></li>

</ul>
</details>

**标签**: `#Apple silicon`, `#MacBook Pro`, `#computer hardware`, `#on-device AI`, `#developer tools`

---

<a id="item-tech-news-5"></a>
### [Tailscale SSH 漏洞调查与修复更新](https://tailscale.com/ssh-investigation-update) ⭐️ 7.0/10

Tailscale 已发布 Tailscale SSH 安全调查与修复更新，面向使用 ACL 授权 Tailscale SSH 访问节点的管理员和开发者。当前材料未提供漏洞编号、受影响版本、修复版本或具体利用前提，也未说明是否已有独立验证，因此只能确认官方公布了调查与处置信息，无法据此判断特定部署是否已经修复或仍可被利用。

hackernews · figmert · 10月27日 19:55 · [社区讨论](https://news.ycombinator.com/item?id=50264857)

**「理解 Tailscale SSH 的授权边界」** Tailscale SSH 是由 Tailscale 接入并结合 ACL 授权的 SSH 模式，与系统直接运行 sshd 的方式不同；评估此次漏洞的影响范围，需要分别确认节点是否启用该模式、用户是否获得 ACL 允许的 SSH 权限，以及能否连接目标节点。一位自称曾任职于 Tailscale、目前负责企业 Tailscale 管理的评论者认为，受影响场景主要是 ACL 允许 Tailscale SSH、但未授予 sudoers 或 root 路径的配置；这是其审查修复代码后的个人判断，并非现有材料所含厂商一手说明。

**「升级 Tailscale 并收紧 SSH 授权」** 在受影响版本中，已获准通过 Tailscale SSH 登录 Linux 节点的用户可以使用用户名 \`-i\` 获取 root 会话，从而绕过 ACL 策略。管理员应将 Tailscale 升级至 1.98.9 或更高版本，并审查涉及 Tailscale SSH 的 ACL、sudo 与 root 授权配置。

**「社区对风险范围与替代方案的意见」** 一名自称前 Tailscale 员工、现负责相关部署的评论者称，其对漏洞及 GitHub 修复的审查表明，风险主要限于 ACL 允许 Tailscale SSH 进入节点、但未授予 sudoers 或 root 路径的账户；这是评论者的审查结论，并非当前材料中已独立验证的事实。多位评论者因攻击面和单一故障点方面的担忧，主张改用仅支持密钥认证的加固版 OpenSSH 或直接禁用 Tailscale SSH；这些属于个人运维偏好，材料未显示 Tailscale 官方提出了同样建议。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://tailscale.com/security-bulletins">Security Bulletins · Tailscale</a></li>

</ul>
</details>

**标签**: `#Tailscale SSH`, `#security vulnerabilities`, `#remediation`, `#access control`, `#SSH`

---

<a id="item-tech-news-6"></a>
### [Python 实验性 JIT 据报将被移除](https://lwn.net/SubscriberLink/1102102/0c00e4d550f25f8c/) ⭐️ 7.0/10

Python 的实验性 JIT 据报将被移除，但现有材料未说明具体决策方、移除范围或生效版本。这一功能此前被部分开发者寄望于缓解 free-threading 带来的性能损失，因此其移除引发了关于 Python 性能路线、PEP 审批流程及 Cython 等显式编译方案的讨论。由于 JIT 仍处于实验阶段，现有证据尚不足以表明这会立即影响常规 Python 用户或造成广泛的生态后果。

hackernews · f311a · 10月27日 11:17 · [社区讨论](https://news.ycombinator.com/item?id=50257419)

**「PEP 836 提案的撤回」** 在此次移除前，CPython 的实验性 JIT 团队曾提出标准追踪提案 PEP 836《JIT Go Brrr: The Path to a Supported JIT Compiler for CPython》，试图将该编译器转为正式、受支持的非实验功能；该提案在讨论数月后被撤回。相关报道据此称，实验性 JIT 预计在 Python 3.16 开发周期早期从 CPython 主分支移除，但这仍是预期安排，而非已经完成的发布事实。

**「对现有 JIT 用户的影响」** Python 3.13 的 copy-and-patch JIT 只是按需启用的实验功能，因此按当前报道移除它不会改变默认 CPython 用户的运行行为；但正在用该 JIT 做性能基准、原型或自动化构建的开发者将失去一条可继续投入的优化路线，需要改用解释器优化并重新验证性能。由于 Python 3.14 已将自由线程构建转为正式支持，开发者不应再把这项已报道将移除的实验 JIT 当作解决自由线程性能问题的长期方案。

**「社区讨论」** 部分评论者认为，该 JIT 原可帮助抵消自由线程模式的性能成本，其移除令人惋惜；另有评论者提出，可用装饰器让开发者按需内联并预编译 Cython 代码作为替代。讨论中也存在治理层面的分歧：有人将移除部分归因于 PEP 流程和开发者精力不足，但也有人认为严格遵循 PEP 制度有助于维持 Python 的长期质量。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.linuxnews.net/articles/python-s-experimental-jit-to-be-removed">Python&#x27;s experimental JIT to be removed - Linux News</a></li>
<li><a href="https://daily.dev/posts/python-s-experimental-jit-to-be-removed-2qgwrdoly">Python&#x27;s experimental JIT to be removed - daily.dev</a></li>
<li><a href="https://blog.imseankim.com/python-3-14-free-threading-jit-compiler-gil-removal-2026/">Python 3.14 Free-Threading and Experimental JIT: How Python ...</a></li>
<li><a href="https://www.sergiozabala.dev/en/blog/python-3-13-jit-free-threading/">Sergio Zabala | Python 3.13: The Experimental JIT and Free ...</a></li>

</ul>
</details>

**标签**: `#Python`, `#JIT compilation`, `#free-threading`, `#performance engineering`, `#Cython`

---

<a id="item-tech-news-7"></a>
### [Ψ-0.6：统一视觉语言模型的自适应思维流](https://www.reddit.com/r/MachineLearning/comments/1xgwq9u/%CF%8806_adaptive_streams_of_thought_in_a_unified/) ⭐️ 7.0/10

Ψ-0.6 将视觉语言理解、世界建模、推理与机器人控制整合到单一模型中，并通过强化学习选择以文字、深度、运动、相机位姿或想象场景进行推理的“思维流”。作者称，该模型在 MindCube 零样本复杂空间推理任务上超过领先开放权重模型，在 FlowBench 物体运动预测上优于其他世界模型，并实现了从模拟房间到真实机器人桌面的迁移。论文和代码均已提供，但 Reddit 摘要未列出具体指标、基线细节或独立验证，因此这些性能与迁移结果目前应视为作者报告。

reddit · r/MachineLearning · /u/FaeriaManic · 10月27日 16:09 · [社区讨论](https://www.reddit.com/r/MachineLearning/comments/1xgwq9u/%CF%8806_adaptive_streams_of_thought_in_a_unified/)

**「MindCube 的背景」** 理解 Ψ-0.6 在 MindCube 上的零样本结果，需要先明确该基准的用途：MindCube 用于测试视觉语言模型能否从有限视觉视角形成稳健的空间心理模型。此前一项 MindCube 研究通过让模型基于内部地图进行推理，将准确率从 37.8% 提升至 57.8%；这一数字属于先前研究，并非 Ψ-0.6 的实测提升。

**「对具身 AI 研发的影响」** 对具身 AI 研发者，公开实现把 RGB、文本、深度、光流、相机信息和生成图像纳入同一自回归 token 流，并用强化学习按问题选择中间表示，使团队可以试验以单一模型串联感知、世界建模、推理与控制，而不必维护多套专用模块（tool-3-1, tool-3-2）。但现有依据主要是项目方报告的 MindCube 零样本、FlowBench 运动预测及模拟房间到真实机器人迁移结果，缺少具体分数、基线细节和独立复现；采用前仍需在自身任务与硬件上验证，暂不宜据此直接替换现有流水线（tool-3-3）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2506.21458">[2506.21458] MindCube : Spatial Mental Modeling from Limited Views</a></li>
<li><a href="https://huggingface.co/datasets/MLL-Lab/MindCube">MLL-Lab/ MindCube · Datasets at Hugging Face</a></li>
<li><a href="https://arxiv.org/abs/2610.32177">[2610.32177] ||Psi;$-0.6: Adaptive Streams of Thought in a ...</a></li>
<li><a href="https://github.com/awwkl/psi-0.6">GitHub - awwkl/psi-0.6: Paper: &quot;Ψ-0.6: Adaptive Streams of ...</a></li>
<li><a href="https://pith.science/paper/2610.32177">Psi-0.6: Adaptive Streams of Thought in a Unified Vision ...</a></li>

</ul>
</details>

**标签**: `#world models`, `#vision-language models`, `#embodied AI`, `#multimodal reasoning`, `#reinforcement learning`

---

<a id="item-tech-news-8"></a>
### [中国团队声称实现 3.2 Pb/s 光纤实时传输](https://www.tomshardware.com/networking/3-2-pb-s-real-time-optical-fiber-transfer-speed-world-record-claimed-by-chinese-team-speed-fast-enough-to-download-more-than-20-000-4k-movies-in-one-second) ⭐️ 7.0/10

中国团队声称利用 24 芯光纤实现每秒 3.2 Pb/s 的实时传输，按报道换算，一秒内可传输超过 2 万部 4K 电影。测试采用兼容商用的硬件架构，并验证了空分复用及 S+C+L 多波段传输技术。该成绩较团队今年早些时候创造的 2.5 Pb/s 纪录提高近 30%；报道提到的实验室最高纪录 5.29 Pb/s 则使用了先进或实验性设备与信号处理。目前相关消息尚无论文、同行评审或完整实验细节，因此这一结果仍是有待核实的实验室纪录声明。

telegram · zaihuapd · 10月27日 03:45

**「纪录口径与链路背景」** 此前的实验室光纤传输纪录曾达到 5.29 Pb/s，但采用了先进或实验性设备与信号处理；本次 3.2 Pb/s 的差异在于以商用兼容架构在 24 芯光纤上实现实时传输，空分复用与 S+C+L 多波段共同构成系统总容量。补充报道显示，测试链路长 10.3 千米并使用实时收发器，因此该数值反映的是特定多芯测试链路的实时吞吐，不能直接视为单芯光纤或家庭宽带速率。

**「商业部署仍待验证」** 对云计算、AI 系统和数据中心运营商而言，若这项基于商用兼容硬件、10.3 公里 24 芯光纤链路的 3.2 Pb/s 结果得到复现，意味着现有光通信设施可能承载更高吞吐量；不过该速率的商业部署尚未得到确认，当前不宜将其视为可立即采购或上线的容量指标。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.notebookcheck.net/China-claims-3-2-Pb-s-optical-fiber-record-could-send-20-000-4K-movies-per-second.1434319.0.html">China claims 3.2 Pb/s optical fiber record — could send ...</a></li>
<li><a href="https://hwbusters.com/news/multi-core-fiber-hits-3-2-pb-s-in-real-time-but-the-record-link-ran-just-10-km/">Multi-Core Fiber Hits 3.2 Pb/s in Real Time, but the Record ...</a></li>
<li><a href="https://www.notebookcheck.net/China-claims-3-2-Pb-s-optical-fiber-record-could-send-20-000-4K-movies-per-second.1434319.0.html">China claims 3.2 Pb/s optical fiber record — could send ...</a></li>
<li><a href="https://x.com/tchsignal/status/2114756623877263625">TechSignal on X: &quot;China Claims 3.2 Pb/s Optical Fiber ...</a></li>

</ul>
</details>

**标签**: `#光纤传输`, `#3.2 Pb/s`, `#空分复用`, `#多波段技术`, `#网络硬件`

---

<a id="item-tech-news-9"></a>
### [微软修复 Authenticator 安卓版令牌窃取漏洞](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-80097) ⭐️ 7.0/10

微软已在 Microsoft Authenticator 安卓版 6.2606.4246 中修复高危漏洞 CVE-2026-80097；该漏洞可能使已安装并运行的恶意应用在无需 Android 权限的情况下，窃取用户已登录工作账户的令牌。研究人员称用户无需进一步操作，而微软认为攻击者仍需诱使用户完成身份验证，双方对利用条件的判断存在差异。微软首次发布公告时称尚未发现该漏洞遭到实际利用，相关 Android 用户应尽快升级至修复版本。

telegram · zaihuapd · 10月27日 12:04

**「利用条件与实际情况」** Microsoft Authenticator 的工作账户令牌是应用代表用户完成登录身份验证所需的关键材料。现有材料对利用前提存在分歧：研究人员称已安装并运行的恶意应用无需申请额外 Android 权限、用户也无需进一步操作；微软则认为攻击者仍需诱使用户完成身份验证。微软首次公告时称尚未发现该漏洞被实际利用。

**「立即更新 Authenticator 安卓版」** 使用 Microsoft Authenticator 安卓版的组织应尽快通过 Google Play 将应用升级至 6.2606.4246 或更高版本；外部报道指出，该漏洞影响此前的安卓版本。研究人员的测试显示，被窃取的令牌可完整访问账户的电子邮件、文件和日历，因此依赖 Authenticator 保护工作账户的管理员和用户应立即完成升级。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thehackernews.com/2026/10/microsoft-authenticator-flaw-let.html">Microsoft Authenticator Flaw Let Permissionless Android Apps Steal...</a></li>
<li><a href="https://www.techradar.com/pro/security/critical-microsoft-authenticator-flaw-let-malicious-android-apps-steal-access-to-your-precious-accounts">Critical Microsoft Authenticator flaw let malicious Android apps steal...</a></li>

</ul>
</details>

**标签**: `#安全漏洞`, `#身份验证`, `#Android`, `#Microsoft Authenticator`

---

<a id="item-tech-news-10"></a>
### [Anthropic 确认研究人员访问内部系统](https://www.washingtonpost.com/technology/2026/10/26/researchers-cybersecurity-start-up-cathedral-got-inside-anthropic/) ⭐️ 7.0/10

Anthropic 确认，网络安全初创公司 Cathedral 的研究人员利用第三方商业软件漏洞，进入了其部分销售、人力和 IT 系统；Cathedral 称，AI 代理在不足 12 小时内找到通路，接触到会议记录、薪资与录用信息及 Slack 消息。Anthropic 表示，监控系统在收到 Cathedral 报告前已发现部分活动并关闭通路，且客户发给模型的消息、模型回复、AI 系统代码和模型权重均未被访问。双方对事件影响和披露程度存在争议：Anthropic 认为 Cathedral 夸大了影响且未完整披露，Cathedral 则称其遵守安全研究惯例，并将数据访问限制在必要最低程度。

telegram · zaihuapd · 10月27日 12:43

**「事件背景」** Cathedral 的测试是在 Anthropic 的漏洞赏金计划框架下进行的，因此其访问虽属于安全研究，仍触及了销售、人力和 IT 等内部业务系统的权限边界。外部报道指出，AI 代理利用的是第三方行政和销售系统中的漏洞，而非直接攻破 Claude 模型；这使事件更接近第三方业务系统暴露与内部权限控制问题。

**「实际安全影响」** 此次事件表明，AI 代理不到 12 小时便能借助第三方软件漏洞进入销售、人力和 IT 等内部业务系统，因此企业不能只保护模型接口与权重，还需核查第三方组件漏洞、跨系统权限、异常监测和披露流程。Anthropic 称 Claude 对话、源代码和模型权重未被触及，但双方对活动范围与披露程度的说法不一，实际暴露范围仍需结合授权记录和访问日志核定。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techstartups.com/2026/10/26/ex-doge-ai-cybersecurity-startup-cathedral-breaches-anthropics-internal-systems-in-under-12-hours-using-ai-agents-exposing-sensitive-employee-data/">Ex-DOGE AI cybersecurity startup Cathedral ... - Tech Startups</a></li>
<li><a href="https://decrypt.co/381860/ai-agents-hack-anthropic-business-systems-12-hours">AI Agents Found a Way Into Anthropic &#x27;s Business Systems ... - Decrypt</a></li>
<li><a href="https://undercodenews.com/anthropic-confirms-limited-internal-system-access-during-cathedral-bug-bounty-test-rules-out-access-to-claude-conversations-and-model-weights-video/">Anthropic Confirms Limited Internal System Access During ...</a></li>
<li><a href="https://cybersecuritynews.com/anthropic-internal-system-breach/">Researchers Use AI Agents to Breach Anthropic’s Internal ...</a></li>
<li><a href="https://qz.com/cathedral-ai-agents-anthropic-systems-breach-102726">Cathedral AI agents broke into Anthropic in less than 12 hours</a></li>

</ul>
</details>

**标签**: `#AI安全`, `#Anthropic`, `#漏洞利用`, `#AI代理`, `#网络安全`

---

<a id="item-tech-news-11"></a>
### [Google 睡眠框架巩固持续学习参数](https://research.google/blog/the-sleep-framework-a-new-way-for-llms-to-retain-knowledge-in-continual-learning/) ⭐️ 7.0/10

Google Research 提出“睡眠框架”，让大语言模型在主动交互与离线“睡眠”阶段之间切换，将短期上下文巩固为长期参数，以缓解持续学习中的灾难性遗忘。来源称，该方法在 1000 万 token 长上下文、持续翻译和数学推理测试中超过了 GPT-4、SFT 等基线。但现有材料未提供论文、量化指标、消融实验和实现细节，且“超过 GPT-4”的评测口径不明，尚不足以判断其突破程度。

telegram · zaihuapd · 10月28日 01:46

**「持续学习为何需要“睡眠”」** 灾难性遗忘是持续学习中的核心问题：模型在学习新任务或新事实后，原有知识可能退化。Google 的“睡眠”框架借鉴生物学中的睡眠与记忆巩固机制，在主动交互之外加入离线巩固阶段，将短期上下文转化为长期参数更新，以继续吸收知识并保留既有能力。

**「对持续学习团队的影响」** 对需要让模型随新数据持续更新的团队，该框架提供了一个可复现的实验路径：周期性切换在线交互与离线“睡眠”，将短期上下文巩固为长期参数，以缓解灾难性遗忘。Google 称其在 1000 万 token 长上下文、持续翻译和数学推理测试中超过 GPT-4、SFT 等基线，但当前材料缺少量化结果、消融实验、官方代码及模型和硬件兼容性信息，因此更适合先按真实数据到达顺序开展验证，而不宜直接视为可部署方案；持续学习尤其需要检验非打乱数据流下的稳定性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://todayforai.com/en/story/story-ac73a1ee-65e">Google Research Introduces &#x27;Sleep Phase&#x27; Framework to Fix LLM ...</a></li>
<li><a href="https://openreview.net/forum?id=MqDVlBWRRV&amp;noteId=yahdtlh5Ti">SIESTA: Efficient Online Continual Learning with Sleep | OpenReview</a></li>

</ul>
</details>

**标签**: `#持续学习`, `#大语言模型`, `#灾难性遗忘`, `#长上下文`, `#Google Research`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [泡泡玛特第三季度营收同比下降 45%至 50%](https://asia.nikkei.com/business/consumer/pop-mart-s-revenue-halves-in-q3-as-labubu-craze-cools) ⭐️ 7.0/10

泡泡玛特 10 月 27 日提交的港交所文件显示，第三季度营收同比下降 45%至 50%，其中美国市场下降 70%至 75%。公司预计，由于海外高毛利销售占比下降，下半年毛利率较上半年最多收窄 2 个百分点。

telegram · zaihuapd · 10月27日 14:30

**「背景」** 高盛渠道跟踪报告显示，2026 年第三季度泡泡玛特天猫、抖音合计销售额同比下降 30%，其中 9 月单月下降 44%；港交所公告中的 45%至 50%则是公司第三季度整体收益同比降幅，并非仅指线上渠道。

**「影响」** 泡泡玛特在美国、亚太和欧洲等海外市场的收入明显下滑；由于高毛利海外销售占比下降，公司预计下半年毛利率较上半年最多收窄 2 个百分点。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wallstreetcn.com/articles/3784564">泡 泡 玛 特 Q3整体 收 益 同 比 下 降 45 %- 50 %， 美 洲最深 降 75 ...</a></li>
<li><a href="https://finance.eastmoney.com/a/202610273910327680.html">泡 泡 玛 特 三 季 度 收 入 同 比 下 降 约 50 %丨 港 股公告精选 _ 东方财富网</a></li>
<li><a href="https://original.ifeng.com/c/8xZTG8VFaqG">泡泡玛特三季度收益同比下降45%-50%，亚太降65%-70%、美洲降70%-75%、...</a></li>
<li><a href="https://www.huxiu.com/article/4900970.html">泡泡玛特收益腰斩 - 虎嗅网</a></li>

</ul>
</details>

**标签**: `#泡泡玛特`, `#季度业绩`, `#Labubu`, `#消费趋势`, `#毛利率`

---