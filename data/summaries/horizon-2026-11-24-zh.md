# Horizon 每日速递 - 2026-11-24

> 从 35 条内容中筛选出 16 条重要资讯。

---

**科技新闻**
1. [英伟达恢复黄仁勋 CEO 职务](#item-tech-news-1) ⭐️ 8.0/10
2. [GLM‑5.4 首发循环 Transformer 架构](#item-tech-news-2) ⭐️ 8.0/10
3. [Codex2api 疑似遭供应链投毒，密钥外泄](#item-tech-news-3) ⭐️ 8.0/10
4. [Anthropic 公开 Claude 发现的 VP≠VNP 论文及 Lean 4 证明](#item-tech-news-4) ⭐️ 8.0/10
5. [Stalwart 宣称可直接替代 Microsoft Exchange](#item-tech-news-5) ⭐️ 7.0/10
6. [Ladybird 发布首个可安装 Alpha 版本](#item-tech-news-6) ⭐️ 7.0/10
7. [NariQ：将 Qwen3.8-27B 压缩至约 10GB](#item-tech-news-7) ⭐️ 7.0/10
8. [Meta AI 负责人警告超级智能控制风险](#item-tech-news-8) ⭐️ 7.0/10
9. [ChatGPT 向付费用户推送 GPT-6.2 Sol](#item-tech-news-9) ⭐️ 7.0/10
10. [鸿蒙终端破亿，开源生态扩大](#item-tech-news-10) ⭐️ 7.0/10
11. [苹果 iPhone 浏览器限制遭企业组织要求调查](#item-tech-news-11) ⭐️ 7.0/10
12. [新加坡调查 Megaspeed 采购英伟达芯片案](#item-tech-news-12) ⭐️ 7.0/10

**科技博客**
1. [ERNIE 5.5 Flash 的 vLLM 插件化推理优化](#item-tech-blog-1) ⭐️ 8.0/10

**财经新闻**
1. [英伟达恢复黄仁勋 CEO 职务并展开调查](#item-finance-news-1) ⭐️ 8.0/10
2. [Anthropic IPO 后中国 AI 上市计划承压](#item-finance-news-2) ⭐️ 7.0/10
3. [SpaceX 据报向外出租 AI 算力](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [英伟达恢复黄仁勋 CEO 职务](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 8.0/10

英伟达董事会重新任命黄仁勋（Jensen Huang）担任公司总裁、CEO 兼董事。英伟达公告称，董事会决策过程中听取了美国政府高层的意见，并基于这些意见认定恢复黄仁勋职务不会构成国家安全风险。所给材料未披露导致其此前离任的调查、具体指控或完整决策时间线，因此不能据此判断英伟达或黄仁勋是否存在违法行为，公告中的风险认定也不等同于独立核验结论。

hackernews · jaz · 11月23日 14:00 · [社区讨论](https://news.ycombinator.com/item?id=50611576)

**「离任后的迅速复任」** 黄仁勋是 Nvidia 联合创始人，这次变动应理解为对其离任决定的逆转：ABC 报道称，他在辞职仅数周后即被重新任命。Nvidia 官方公告显示，黄仁勋获立即恢复为总裁兼 CEO，并同时重新成为董事会成员；这意味着董事会不仅交还经营权，也恢复了他参与公司治理的正式席位。

**「对中国芯片供货的影响」** 对中国市场采购英伟达 AI 芯片的企业，潜在影响是合规型号的供货与合规不确定性上升：路透社称英伟达已借助可出口芯片扭转中国市场业务，但黄仁勋此次离任风波的余波及美国重新加强审查可能威胁该业务。采购方应按具体型号和出口许可核验可用性并准备替代方案；黄仁勋获复任本身并不足以证明出口限制已经放宽。

**「评论者质疑治理独立性」** 评论者认为，争议重点不仅是黄仁勋能否胜任，也包括董事会问责标准及外部力量对治理的影响；一名评论者援引特拉华州 Caremark 义务的高门槛，并结合其对司法部不追究的说法，推测董事个人责任风险可能较低。其他评论者质疑这次迅速且一致的职位恢复说明形式上的董事会治理可能受到政治因素左右，也有人反驳称目前没有证据显示英伟达犯罪；这些均属于社区观点，而非已经核实的事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.abc.net.au/news/2026-11-24/nvidia-jensen-huang-timeline/107419314">Why Jensen Huang &#x27;s return isn&#x27;t the end of the Nvidia saga - ABC...</a></li>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Board-Reinstates-Jensen-Huang-as-President-CEO-and-Board-Director/default.aspx">NVIDIA Corporation - NVIDIA Board Reinstates Jensen Huang as ...</a></li>
<li><a href="https://www.reuters.com/world/china/how-nvidias-billion-dollar-turnaround-china-is-threatened-by-huangs-exit-2026-11-23/">How Nvidia’s billion-dollar turnaround in China is threatened ...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#Jensen Huang`, `#AI chips`, `#corporate governance`, `#export controls`

---

<a id="item-tech-news-2"></a>
### [GLM‑5.4 首发循环 Transformer 架构](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai 发布 GLM‑5.4，主打通用编程，并首次在该实验室的模型中采用循环 Transformer（Loop Transformer）架构。Z.ai 称，这种结构让一组共享权重的层多次迭代、持续修正隐藏状态，在不增加参数量的同时加深网络；GLM‑5.4 已上线，但常规 Z.ai API 暂不能访问该模型，也尚未开放权重，当前需订阅 Coding Plan。所给材料没有基准成绩或独立验证，因此尚不能确认这一架构变化已经带来实际能力或效率提升。

hackernews · foohis · 11月23日 10:06 · [社区讨论](https://news.ycombinator.com/item?id=50609685)

**「架构背景」** 传统 Transformer 在一次前向传播中只让每一层运行一次；循环 Transformer 则重复运行一组共享权重的层，并把上一轮得到的隐藏状态带入下一轮。所给材料没有列出 GLM‑5.4 的参数规模、循环次数或实测时延，因此它说明了计算方式的变化，却不足以证明实际性能收益。

**「实际影响」** 开发者若要试用 GLM‑5.4，当前需改用 Coding Plan；作者实测其 API 密钥可在常规 Z.ai 同一 OpenAI 兼容 Responses API 端点（https://api.z.ai/api/v1）调用新模型。现有 llm-zai 插件尚不支持 5.4，作者暂时发布了 llm-glm，并表示待前者补齐支持后可能退役自己的插件；由于没有开放权重，本地部署者仍无法使用该模型。作者的同提示 SVG 对比中，5.4 在 low、high、max 三档都与 5.3 相近，未显示明显的用户可见质量跃升。

**「社区讨论」** 有评论者赞赏 Z.ai 提供较多技术细节，认为循环 Transformer 是值得探索的方向，但也承认这种结构仍有问题待解决。另一位使用者称中国模型的“马拉松思考”在简单任务上也会反复自我质疑，令任务完成时间明显高于前沿模型；这是个人体验而非测量结果，但凸显了推理时间和工作流成本问题。

**标签**: `#loop transformers`, `#AI coding`, `#large language models`, `#model architecture`

---

<a id="item-tech-news-3"></a>
### [Codex2api 疑似遭供应链投毒，密钥外泄](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 8.0/10

一则 Telegram 消息及其所链接的事件复盘声称，Codex2api 作者账号遭入侵后，攻击者绕过 main 分支推送标签，使 Release 构建出带后门的版本；目前仅有二手转述，尚无独立核验。消息称受影响版本为 3.1.10–3.1.12，其中 v3.1.11 移除鉴权、可被无密码远程执行命令，另有工作流外传了 16 个 GitHub Actions secrets，并波及作者账号下至少 21 个仓库。报告建议已安装或更新这些版本的用户立即停用、回退至 3.1.9，并轮换 GitHub token、SSH key、数据库及 DeepSeek 等相关凭据。

telegram · zaihuapd · 11月23日 11:21

**「理解 GitHub 发布链风险」** 要理解这起疑似投毒事件，关键在于两个机制：GitHub 的 tag 可以触发独立于 main 分支的 Release 构建，而 Actions 工作流在运行时会接触仓库 secrets；因此，构建产物和工作流一旦被攻击者控制，恶意版本与凭据外泄可能沿同一条发布链发生。现有材料仅是 Telegram 对原始事件报告的转述，受影响版本及波及仓库的准确范围仍待核验。

**「受影响用户需立即处置」** 若该供应链投毒报告属实，安装或更新过 Codex2api 3.1.10–3.1.12 的用户面临无鉴权远程命令执行、16 个 GitHub Actions secrets 被外传及至少 21 个仓库受影响的风险；相关用户和组织应立即停用受影响版本、回退至 3.1.9，并轮换 GitHub token、SSH 密钥、数据库凭据和 DeepSeek 等所有相关密钥。

**标签**: `#软件供应链安全`, `#GitHub Actions`, `#密钥泄露`, `#后门`, `#Codex2api`

---

<a id="item-tech-news-4"></a>
### [Anthropic 公开 Claude 发现的 VP≠VNP 论文及 Lean 4 证明](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 8.0/10

Anthropic 于 11 月 24 日公开论文《VP ≠ VNP over every field》及配套 Lean 4 形式化代码；仓库称结果由内部研究用 Claude 模型发现，论文和代码均由 AI 撰写。该结果声称给出哈密顿圈多项式的超多项式算术电路下界，从而在所有域上证明 VP 是 VNP 的真子类，若成立将解决 Valiant 1979 年的代数复杂度猜想，但不涉及 P 与 NP。仓库称形式化证明经三项标准公理审计和独立 nanoda 内核复核后，除预留文件外没有 sorry；不过尚无人类数学家完整审阅，Lean 也无法确认形式化陈述与论文命题完全一致，附录 Q 已列出差异，因此该结论仍待独立验证。

telegram · zaihuapd · 11月24日 06:02

**「代数复杂度猜想的背景」** VP≠VNP 源于 Leslie Valiant 在 1979 年提出的代数复杂度问题：VP 与 VNP 是用域上的算术电路刻画计算能力的复杂度类，二者严格分离便写作 VP≠VNP。它常被称为 P 与 NP 的代数对应版本，但这里的超多项式下界针对算术电路，并不解决经典的 P 与 NP 问题；Lean 4 形式化用于让内核检查证明步骤，仍不能替代专家对形式化陈述与论文命题是否一致的审阅。

**「算术复杂性结论仍待独立验证」** 若论文陈述与其 Lean 4 形式化完全一致，该工作将给出哈密顿圈多项式的超多项式算术电路下界，并证明 VP 是 VNP 的真子类，但这不涉及 P 与 NP 问题的解决。当前研究者不应将其直接当作已确立定理引用：尽管形式化代码通过公理审计和 nanoda 内核复核且除预留文件外没有 \`sorry\`，尚无人类数学家完成通读，附录 Q 还列出了形式化陈述与论文命题之间的差异，因此关键影响仍取决于独立审查能否确认两者等价。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=UuOiRi9T-9c">Claude &#x27;s VP VNP Proof: 47 Years Open, Still Unchecked... - YouTube</a></li>
<li><a href="https://www.alphaxiv.org/abs/2611.vp-vnp-arithmetic-lower-bounds">VP VNP Over Every Field | alphaXiv</a></li>
<li><a href="https://github.com/anthropics/formal-math">GitHub - anthropics / formal - math · GitHub</a></li>
<li><a href="https://explainx.ai/blog/anthropic-claude-vp-vnp-valiant-lean-proof-claimed-vs-verified-2026">VP ≠ VNP Lean Proof: Claimed vs Verified (2026) - explainx.ai</a></li>
<li><a href="https://casrai.org/news/anthropic-claude-authored-vp-vnp-proof-unverified-lean-2026">Claude-Authored VP ≠ VNP Proof Posted, Unchecked — CASRAI</a></li>

</ul>
</details>

**标签**: `#Claude`, `#AI 定理证明`, `#Lean 4`, `#代数复杂性`, `#形式化验证`

---

<a id="item-tech-news-5"></a>
### [Stalwart 宣称可直接替代 Microsoft Exchange](https://stalw.art/blog/microsoft-exchange-replacement/) ⭐️ 7.0/10

Stalwart 博客文章将该邮件服务器定位为 Microsoft Exchange 的“直接替代品”，面向希望采用开源方案、减少 Exchange 许可与基础设施依赖的自托管邮件组织。现有材料没有列出具体兼容的 Exchange、MAPI、Outlook 或部署范围，也未提供迁移步骤或独立测试结果，因此“直接替代”目前只能视为项目方主张，而非已验证的全功能互换。评论还指出 Outlook 同步行为、邮件合规归档以及对专有协议的依赖可能限制其实际替代能力。

hackernews · shaunpud · 11月23日 22:32 · [社区讨论](https://news.ycombinator.com/item?id=50620349)

**「背景」** 所谓“可直接替代 Exchange”，前提是替代服务器能继续与现有 Outlook、Apple Mail 和移动设备通信，而不必要求用户全面更换客户端。Stalwart 1.2.0 通过支持 MAPI over HTTP、Exchange Web Services、ActiveSync 和 Autodiscover 来实现这一兼容层，因此这里的“drop-in”主要指客户端接入协议兼容；现有材料并未证明其与 Exchange 的全部功能及数据迁移流程完全等价。

**「迁移影响与上线前提」** Stalwart 1.2.0 已加入 MAPI、EWS、ActiveSync 和 Autodiscover，因此依赖这些协议的组织在迁移 Exchange 时可继续使用经典 Outlook、Apple Mail 和移动端客户端，而不必先统一更换客户端。不过，“即插即用”主要指客户端协议兼容，并不代表所有 Exchange 功能均可等价替代；管理员上线前仍需验证实际迁移流程和规模化承载能力，因为相关报道指出这些关键问题尚未得到解答。

**「社区讨论」** 评论者并未普遍接受“直接替代”的说法：hobo123 质疑 Outlook 停止支持本地 Exchange 后客户如何继续使用，traceroute66 则认为新版 Outlook 的云端同步和 Microsoft 365 捆绑让这一表述有所夸大。rmoriz 称德国 GoBD 要求邮件不可删除或篡改，并可能需保留约 10 年以供税务机关访问，但其表示 Stalwart 的常规及 OSS 版本缺少相关功能；andreashaerter 则认为支持 MAPI 等专有协议只能延续既有的协议锁定。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://stalw.art/blog/microsoft-exchange-replacement/">Stalwart is now a drop-in replacement for Microsoft Exchange</a></li>
<li><a href="https://www.learn.telusko.com/newsletter/stalwart-1-2-0-is-now-a-drop-in-replacement-for-microsoft-exchange">Stalwart 1.2.0 is now a drop-in replacement for Microsoft ...</a></li>
<li><a href="https://www.startuphub.ai/ai-news/technology/2026/stalwart-1-2-0-replaces-exchange-and-keeps-outlook-working">Stalwart 1.2.0 replaces Exchange and keeps Outlook…</a></li>
<li><a href="https://www.helpnetsecurity.com/2026/11/24/stalwart-microsoft-exchange-replacement/">Stalwart: Open-source Microsoft Exchange replacement</a></li>

</ul>
</details>

**标签**: `#email servers`, `#Microsoft Exchange`, `#open source`, `#self-hosting`, `#protocol compatibility`

---

<a id="item-tech-news-6"></a>
### [Ladybird 发布首个可安装 Alpha 版本](https://ladybird.org/posts/alpha/) ⭐️ 7.0/10

Ladybird 项目发布首个 Alpha 版，现在可在 macOS 和 Linux 直接下载安装，不再需要自行编译。该浏览器自行实现 HTML 解析、CSS 引擎、布局、JavaScript 和 WebAssembly 等核心组件，同时依赖 HarfBuzz、Skia、ffmpeg 和 SQLite，并让不同标签页运行在独立进程中。项目方明确警告部分网站尚不能工作且浏览器可能崩溃；作者实测多数网站可正常显示，Pyodide 与 ffmpeg 的 WebAssembly 工具可以运行，但使用 Service Worker 和 Web Worker 组合的 Datasette Lite 未能启动。项目方公布的 10 月单日最佳 Web Platform Tests 子测试通过数为 2,184,722，略低于 Firefox 的 2,189,315、高于 Safari 的 2,172,990；这是项目自报结果，而非独立测评。

hackernews · janvdberg · 11月23日 16:13 · [社区讨论](https://news.ycombinator.com/item?id=50614249)

**「从 SerenityOS 到独立浏览器」** Ladybird 起源于 SerenityOS 项目，现已作为独立浏览器开发；项目自行实现 HTML 解析、CSS 引擎、布局、JavaScript 和 WebAssembly 等核心组件，同时仍使用 HarfBuzz、Skia、FFmpeg 和 SQLite 等外部组件。2026 年 2 月，Andreas Kling 宣布借助 Claude Code 和 Codex，在两周内将 LibJS 的部分代码移植为 2.5 万行 Rust；项目方随后利用编码代理补齐 Web Platform Tests 功能，并称到 10 月底其测试通过数已接近 Firefox。

**「实际影响」** macOS 和 Linux 用户现在可直接安装 Ladybird alpha，无需自行编译，降低了开发者、安全研究者和早期用户参与兼容性测试的门槛；但官方明确将其定位给能够接受崩溃和网站失效的早期采用者，暂不适合作为无条件可靠的日常主力浏览器。试用者称多数受测网站能够正常渲染，但滚动略显卡顿，依赖复杂 Service Worker 与 Web Worker 组合的 Datasette Lite 则因相关 API 报错而无法启动，这类应用目前仍需准备替代浏览器并向项目提交问题。

**「社区体验与担忧」** 社区测试反馈总体积极：freakynit 称其测试的网站均能正确渲染，但轻微卡顿的滚动体验仍可察觉；alentred 称新闻网站及 Proxmox/NoVNC 等复杂场景表现良好，但尚未确定是否将其作为日常浏览器。评论者同时提出更高要求，drnick1 担忧指纹识别、权限粒度和页面活跃状态暴露，kvuj 则对 Ladybird 转向 SQLite、Skia 等成熟库、全自研理念减弱表示惋惜；这些均是个人意见，不是已经证实的产品缺陷。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ladybird.org/">Ladybird</a></li>
<li><a href="https://ladybird.org/posts/alpha/">Ladybird is now in alpha - Ladybird</a></li>

</ul>
</details>

**标签**: `#Ladybird`, `#web browsers`, `#alpha release`, `#open-source software`

---

<a id="item-tech-news-7"></a>
### [NariQ：将 Qwen3.8-27B 压缩至约 10GB](https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF) ⭐️ 7.0/10

Nari Labs 发布 NariQ，为 Qwen3.8-27B 提供 3-bit、2.5-bit 和 2-bit GGUF 量化，文件大小约为 10GB 级别，面向内存或显存受限的本地推理用户；作者声称这些版本在智能体、数学、多语言推理和图像理解任务上可接近 BF16 表现。按发布方自报数据，3-bit 在 DeepSWE、Terminal-Bench 2.1 和 AIME 25+26 上分别取得 41.0、63.8 和 98.3，略高于 BF16 的 39.8、62.6 和 97.7，但 2-bit 版本降至 28.6、52.4 和 86.0。作者还称其解码速度与 RTX PRO 6000 上的其他量化相当，并公布了 4K、16K 和 64K 上下文测试结果。当前运行这些文件必须使用 nari-labs 的 nari-llama.cpp 分支，基准结论及“接近 BF16”的说法仍缺少更广泛的独立验证。

hackernews · toebee · 11月23日 13:42 · [社区讨论](https://news.ycombinator.com/item?id=50611402)

**「量化与前序本地部署」** 模型量化通过降低权重表示的比特数来缩小文件并减少权重内存占用，但位宽越低，保持原模型能力的难度通常越高。Horizon 的 11 月 4 日摘要显示，Qwen 3.8 27B 此前已可通过 LM Studio 运行约 17GB 的 Q4\_K\_M 版本；此次 NariQ 将其制成 3.0、2.5 和 2.0 bpw 的 GGUF、压缩至约 10GB，并需使用专用的 nari-llama.cpp 分支，因此其“接近 BF16”表现属于该低位宽格式及特定运行实现下的作者主张。

**「当前部署兼容性限制」** 这为希望将 27B 模型压缩到约 10 GB 文件并在受限内存环境中本地运行的用户提供了可行路径，但目前必须使用 Nari Labs 的定制 llama.cpp 分支；原版 llama.cpp、Ollama 和 LM Studio 尚不能直接加载这些 NariQ GGUF 文件。因此，开发者现阶段需要从源码构建该分支进行验证，现有工具链则需等待官方兼容或自行适配。

**「社区质疑评测收益来源」** \[rao-v\] 认为该项目覆盖多类长程任务并使用留出评测，缓解了对 QAT 仅针对公开基准优化的担忧；但 \[WithinReason\] 表示，图表中的大部分增益可能来自评测框架（harness）差异，而非模型本身。实测反馈中，\[jedbrooke\] 报告 M3 Pro 18GB 上 3.0bpw 版本约为 3.8 tok/s、2.0bpw 版本约为 4.9 tok/s，其他 Mac 尚未测试；\[Retro\_Dev\] 与 \[IronWolve\] 则继续追问量化具体丢失的信息，以及 NariQ 与 TCQ、GSQ-RCO 等方法的公平横向比较。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://simonwillison.net/2026/Nov/3/qwen-can-interpret-model-weights/">2026-11-04 — 本地 Qwen 3.8 27B 也能解读模型权重</a></li>
<li><a href="https://github.com/nari-labs/nari-llama.cpp">GitHub - nari - labs / nari - llama . cpp : llama . cpp fork that runs NariQ ...</a></li>
<li><a href="https://news.ycombinator.com/item?id=50611402">NariQ : BF16-level Qwen 3 . 8 - 27 B in a 10 GB file | Hacker News</a></li>
<li><a href="https://github.com/nari-labs/nari-llama.cpp">GitHub - nari-labs/nari- llama . cpp : llama . cpp fork that runs NariQ ...</a></li>

</ul>
</details>

**标签**: `#LLM quantization`, `#Qwen`, `#local inference`, `#model compression`, `#llama.cpp`

---

<a id="item-tech-news-8"></a>
### [Meta AI 负责人警告超级智能控制风险](https://thenextweb.com/news/metas-ai-chief-says-superintelligence-is-arriving-and-control-is-at-risk) ⭐️ 7.0/10

Meta 首席 AI 官、超级智能实验室负责人 Alexandr Wang 在 X 发文称，超级智能已不再是遥远的未来议题；他把数学家 Levent Alpöge 借助 Anthropic Claude 完成、并于周六由 Lean 与 Mathlib 社区机器校验的黎曼猜想证明视为能力跃升迹象，认为 AI 与顶尖人类的差距只剩具体知识、工程整合和实验。Wang 警告，若系统能够无限自我改进或比人类聪明 1000 倍，人类将很难继续掌控，因此呼吁紧急投入安全、对齐与防护研究。该证明目前尚无人类可读版本，其所体现的能力以及超级智能到来的时间表仍主要是 Wang 的主张，不能视为已经独立证实的失控风险。

telegram · zaihuapd · 11月23日 12:49

**「形式化验证的黎曼猜想证明」** 这项例证的关键背景是，Lean 是一种形式化证明语言，Mathlib 提供相关的数学库；所谓“经 Lean 与 Mathlib 机器校验”，是指证明以机器可检查的代码表达并通过校验，而非仅提交自然语言推导。相关资料称，Lean FRO 与 Mathlib Initiative 曾发布联合验证声明，Levent Alpöge 于 11 月 20 日公开约 1700 万行的证明库，其官网另有一篇约四页的说明文本，但这不同于传统数学论文，当前报道所称“尚无人类可读版本”也意味着完整证明的人类可审阅形式仍不明确。这一案例可以说明 Claude 参与了高难度数学工作的工程流程，却不能仅凭一次形式化验证就认定“超级智能”已经出现。

**「形式验证不等于已获全面确认」** 对将 Claude 等模型用于高可信数学或研究流程的团队，这一案例要求把“形式化验证”与“人类可复核”分开验收：Lean 与 Mathlib 社区已认证该形式化证明，但独立数学家尚未验证相关结论，且证明尚无人类可读版本。因此，在获得可读论证和独立复核前，不宜将该成果视为已获全面确认的能力基准，也不应仅凭这一案例推断超级智能即将失控。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://tr.euronews.com/2026/11/23/claude-yapay-zekasi-riemann-hipotezini-cozdu-bilim-ve-toplum-icin-ne-anlama-geliyor">Claude yapay zekası Riemann hipotezini çözdü: Bilim ve... | Euronews</a></li>
<li><a href="https://onedio.com/haber/meta-nin-yapay-zeka-sorumlusu-alexandr-wang-atom-bombasi-riemann-hipotezi-nin-yaninda-ev-odevi-gibi-1396639">Riemann Nedir? Riemann Hipotezi Nedir? - Onedio</a></li>
<li><a href="https://www.log.com.tr/levent-alpogenin-riemann-hipotezine-yonelik-kaniti-dogrulandi/">Levent Alpöge &#x27;nin Riemann hipotezine yönelik kanıtı doğrulandı</a></li>
<li><a href="https://www.ibm.com/think/news/anthropic-claude-riemann-hypothesis-math-proof">Anthropic mathematician claims AI helped solve a 167 ... - IBM</a></li>
<li><a href="https://www.datastudios.org/post/claude-riemann-hypothesis-proof-lean-community-certifies-levent-alpoge">Claude-assisted Riemann hypothesis proof certified by Lean ...</a></li>

</ul>
</details>

**标签**: `#超级智能`, `#AI 安全`, `#Claude`, `#Lean/Mathlib`, `#黎曼猜想`

---

<a id="item-tech-news-9"></a>
### [ChatGPT 向付费用户推送 GPT-6.2 Sol](https://x.com/ChatGPT/status/2124942186425069836) ⭐️ 7.0/10

ChatGPT 官方账户于 11 月 23 日宣布，GPT-6.2 Sol 已上线 Chat 标签页，并开始向 Plus、Pro、Business 和 Enterprise 用户推送。官方称，新版本在处理复杂请求和详细指令、联网查找并按价格或位置筛选购物选项、识别照片中的文字与路牌符号，以及判断是否主动提出后续建议方面有所改进；这些能力描述尚未经过独立验证。公告没有提供基准测试、技术文档、API 接入方式或具体推送进度，因此无法量化其相对既有模型的提升。

telegram · zaihuapd · 11月24日 00:44

**「从 API 与工作场景扩展至 Chat」** Horizon 11 月 18 日的日报曾报道，OpenAI 已推出面向日常工作效率的 GPT-6.2 Sol，并可通过 API 的 gpt-6.2-sol 标识调用，同时进入 ChatGPT Work 与 Codex。此次变化是在该版本已有开发者及工作场景可用基础上，将其进一步扩展到 Chat 标签页和 Plus、Pro、Business、Enterprise 等付费层级，而非首次发布模型。

**「付费用户可检查模型可用性」** Plus、Pro、Business 和 Enterprise 用户可在 Chat 标签页查看 GPT-6.2 Sol 是否已推送到自己的账户；开发者也不应假定 API 已同步支持该版本，因为相关接入信息尚未公布。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/introducing-gpt-6-2-astra-sol/">2026-11-18 — OpenAI 发布 GPT-6.2 Astra 与 Sol</a></li>

</ul>
</details>

**标签**: `#ChatGPT`, `#GPT-6.2 Sol`, `#model rollout`, `#multimodal AI`, `#paid tiers`

---

<a id="item-tech-news-10"></a>
### [鸿蒙终端破亿，开源生态扩大](https://www.xinhuanet.com/20261124/68842538167d4e59a875056d5eb885ad/c.html) ⭐️ 7.0/10

华为终端有限公司 11 月 24 日宣布，搭载 HarmonyOS 5、6、7 的手机、平板和电脑数量已突破 1 亿台，鸿蒙可获取的应用与服务超过 46 万项，注册开发者超过 1200 万人。同一公告称，开源鸿蒙已聚集 1.4 万余名贡献者和 120 余个行业发行版；合作伙伴贡献的 160 余项创新能力已被 1600 余款应用集成调用，相关功能一年的使用量增长 90 倍。上述数字均为华为披露，报道未提供独立核验、活跃设备数量或应用收入等拆分数据。

telegram · zaihuapd · 11月24日 01:46

**「从首次发布到规模节点」** 鸿蒙操作系统于 2019 年首次发布，并在 2024 年 10 月发布原生鸿蒙。此次公告以搭载 HarmonyOS 5、6、7 的手机、平板和电脑为统计范围，披露其到 2026 年 11 月累计突破 1 亿台，同时单列开源鸿蒙的贡献者与行业发行版数据。

**「开发者需区分装机与使用」** 合作伙伴贡献的 160 余项能力已被 1600 余款应用集成调用，且相关功能使用量一年增长 90 倍，说明这些合作能力已有实际集成案例。开发者评估鸿蒙功能复用和商业分发机会时，应将 1 亿台设备总量与功能调用、活跃用户及应用收入分开考量，因为公告没有披露这些转化数据。

**标签**: `#HarmonyOS`, `#开源鸿蒙`, `#操作系统`, `#开发者生态`, `#消费电子`

---

<a id="item-tech-news-11"></a>
### [苹果 iPhone 浏览器限制遭企业组织要求调查](https://appleinsider.com/articles/26/11/23/eu-urges-to-challenge-apples-grip-on-iphone-browsers?utm_source=rss) ⭐️ 7.0/10

包括 Mozilla 和 Shopify 在内的欧盟企业及民间组织已联署致信欧盟委员会，要求对苹果限制 iPhone 浏览器引擎的做法立案，联署方称其代表约 4.5 万至 5.5 万家组织，征集截至 2026 年 12 月 3 日。联署方指出，苹果虽依据《数字市场法》允许竞品浏览器使用自有引擎，但技术及法律限制仍使厂商难以将现有欧盟用户从 WebKit 迁移。该信还援引联署方测算称，若半数原生 iOS 应用转向网页，欧盟企业每年可节省 110 亿欧元开发成本和 13 亿欧元 App Store 费用；目前这仅是调查请求，相关节省数字也非监管结论或独立验证结果。

telegram · zaihuapd · 11月24日 03:02

**「背景：欧盟允许替代引擎后的 WebKit 迁移停滞」** 根据 2024 年 3 月的欧盟《数字市场法》合规决定，苹果在欧盟 iPhone 上已允许浏览器使用非 WebKit 的自有引擎。但据 Mozilla、Shopify 等联署方称，此后近两年并没有任何一款真正不含 WebKit 的浏览器在欧盟上市，原因是技术与法律要求使厂商无法把既有的欧盟用户从 WebKit 迁出。这正是本次联名信要求欧委会对苹果浏览器规则启动执法程序的出发点。

**「对 iOS 开发与分发的影响」** 这封联名信目前不会立即改变苹果的浏览器或 App Store 规则；它只是要求欧盟委员会启动调查，而非监管结论。若后续执法放宽将现有欧盟用户迁出 WebKit 的技术或法律限制，开发者才可能通过 Web 版本降低对 App Store 分发的依赖。联署方估算，若半数原生 iOS 应用转为 Web，欧盟企业每年可节省 110 亿欧元开发成本和 13 亿欧元 App Store 费用；这些数字仍是联署方测算，开发者应以正式调查结论和实际兼容性为准。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.yahoo.com/news/politics/articles/eu-coalition-presses-eu-commission-191706516.html?fr=sycsrp_catchall">EU Coalition Presses EU Commission to Act on Apple Browser ...</a></li>
<li><a href="https://www.iclarified.com/103743/coalition-urges-eu-action-on-apples-ios-browser-rules">Coalition Urges EU Action on Apple&#x27;s iOS Browser Rules</a></li>
<li><a href="https://www.apfelpatient.com/news/apple-browser-engines-eu-open-letter">Apple: Alliance calls for EU proceedings over iOS browsers</a></li>
<li><a href="https://appleinsider.com/articles/26/11/23/eu-urges-to-challenge-apples-grip-on-iphone-browsers">EU urges to challenge Apple&#x27;s grip on iPhone browsers</a></li>
<li><a href="https://www.macrumors.com/2026/11/23/coalition-of-eu-businesses-challenges-apple/">Coalition of 55,000 EU Businesses Challenges Apple</a></li>
<li><a href="https://www.yahoo.com/news/politics/articles/eu-coalition-presses-eu-commission-191706516.html?fr=sycsrp_catchall">EU Coalition Presses EU Commission to Act on Apple Browser ...</a></li>

</ul>
</details>

**标签**: `#欧盟数字市场法`, `#iPhone浏览器`, `#WebKit`, `#应用商店`, `#平台监管`

---

<a id="item-tech-news-12"></a>
### [新加坡调查 Megaspeed 采购英伟达芯片案](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

新加坡总理黄循财表示，不会允许新加坡成为企业规避美国芯片出口管制的通道，并称当局正在调查 Megaspeed 采购英伟达芯片的交易。美国商务部此前一天将 Megaspeed 及另外 6 家东南亚企业列入贸易黑名单，共涉及 8 家企业；美国《联邦公报》称，这些企业存在向未获授权用户转移先进计算产品的“重大风险”，相关实体包括其在马来西亚和泰国的关联公司。路透社还报道，阿里巴巴新加坡子公司 Apex Enterprise Solutions 同样在列；阿里巴巴否认曾转移受管制的先进计算芯片。

telegram · zaihuapd · 11月24日 05:03

**「芯片管制延伸至第三国远程访问」** 11 月 17 日的日报曾报道，美国商务部工业与安全局（BIS）发布临时最终规则，将先进 AI 芯片及相关服务器的出口管制扩展至远程访问；向新加坡等东南亚市场再出口此类芯片须申请许可，以封堵借第三国数据中心绕开限制的路径。11 月 18 日的日报还称，英伟达停止披露新加坡子公司销售数据，当时美国正调查该业务是否可能牵涉芯片转运；但相关收入只是新加坡实体侧的账面归属，不能据此证明芯片最终流向、交易违法或收入被用于规避管制。

**「东南亚算力采购审查收紧」** Megaspeed 被列入美国黑名单后，依赖东南亚算力供应链的企业和云客户需加强 GPU 最终用户、用途及转售链条核验；英伟达也在要求云合作伙伴更严密地追踪 GPU。采购方应重新审查 Megaspeed、Apex Enterprise Solutions 等涉事主体的订单和交易对手，但美国商务部尚未说明针对 Megaspeed 的禁令具体何时生效，阿里也否认 Apex 转移过受管制芯片，因此不能据此认定现有订单已被全面禁止。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ft.com/content/dbde7a30-548c-4f9d-a4be-7898a0c24dcf">2026-11-18 — 英伟达停止披露新加坡子公司销售数据</a></li>
<li><a href="https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/">2026-11-17 — 美国将先进 AI 芯片管制延伸至远程访问</a></li>
<li><a href="https://uz.kursiv.media/en/2026-11-24/us-blacklist-megaspeed-alice-huang/">US blacklists Megaspeed , once led by China spy suspect Alice Huang</a></li>
<li><a href="https://www.bbc.com/news/articles/cv98xpg5dg5zo">US to blacklist Asian AI firm Megaspeed after Nvidia scandal</a></li>
<li><a href="https://www.techrepublic.com/article/news-nvidia-ai-chip-tracking-apac-singapore-china/">Nvidia Tightens AI Chip Tracking in Southeast Asia as China...</a></li>

</ul>
</details>

**标签**: `#芯片出口管制`, `#英伟达`, `#AI硬件`, `#新加坡`, `#东南亚`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [ERNIE 5.5 Flash 的 vLLM 插件化推理优化](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 8.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** ERNIE 5.5 Flash Preview 是 280B 总参数、每 token 激活 14B 的稀疏 MoE 模型，支持 1M token 上下文、思考和工具调用。挑战集中在长上下文索引、512 个路由专家及新型注意力与 MoE 结构；若逐算子实现，会反复搬运中间张量并增加内核启动开销。

**「方案」** 作者为完整前向链路定制融合核：VHA 合并低秩混合与 FP8 量化，Multi-Router Latent MoE 合并路由、Top-10 选择和缩放，MultiMax 单遍处理约 20 万 logits；作者称融合核较朴素实现快 1.55～6.53 倍，MultiMax 与门控结果位级一致。FlashIndexer 以轻量头路由和阈值预筛缩小 DSA 的 2048 top-k 候选，作者称在 1M 上下文加速 1.4 倍；路由专家采用与推理粒度、尺度和舍入一致的 W4A8 QAT，其他权重与 KV 缓存为 FP8，3 层 DSpark 每步最多提议 7 token，作者称编码和 Agent 负载的平均接受长度超过 4.0。该模型通过独立插件的 vllm.general\_plugins 入口自动注册，复用 vLLM 的缓存、CUDA Graph、并行、PD 连接、KV offload 与 OpenAI 服务；作者强调无需维护分支、专用镜像或等待 nightly 构建。

**「启示」** 其价值在于用独立插件把模型专属优化接入 vLLM，实现发布日支持；但文章缺少基准硬件、端到端吞吐、精度评测和部署成本数据，加速幅度与“无损”结论仍待验证。

**标签**: `#LLM inference`, `#vLLM`, `#mixture-of-experts`, `#kernel optimization`, `#speculative decoding`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [英伟达恢复黄仁勋 CEO 职务并展开调查](https://nvidianews.nvidia.com/news/nvidia-board-reinstates-jensen-huang-as-president-ceo-and-board-director) ⭐️ 8.0/10

英伟达董事会全票恢复黄仁勋的总裁兼首席执行官及董事职务，并称在听取美国政府高层意见后认为复任不构成国家安全风险。董事会同时成立独立董事调查委员会，调查黄仁勋曾成为外国情报活动目标的报道，并设立国家安全与出口管制委员会。

telegram · zaihuapd · 11月23日 14:02

**「背景」** 黄仁勋复任前，Colette Kress 担任临时 CEO；英伟达董事会是在与黄仁勋讨论并听取美国政府高层意见后全票决定复任，并称经评估其复任不构成国家安全风险。

**「市场与合规影响」** 英伟达投资者与 AI 芯片客户是直接受影响方：CNBC 称黄仁勋复任消息公布后，英伟达股价大涨 31%；与此同时，董事会新设国家安全与出口管制委员会并招聘首席合规官，使出口合规成为公司治理和芯片业务的重点环节。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://nvidianews.nvidia.com/news/nvidia-board-reinstates-jensen-huang-as-president-ceo-and-board-director">NVIDIA Board Reinstates Jensen Huang as President, CEO and ...</a></li>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Board-Reinstates-Jensen-Huang-as-President-CEO-and-Board-Director/default.aspx">NVIDIA Corporation - NVIDIA Board Reinstates Jensen Huang as ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html">Jensen Huang reinstated as Nvidia CEO. Stock skyrockets 31%</a></li>

</ul>
</details>

**标签**: `#英伟达`, `#CEO变动`, `#公司治理`, `#出口管制`, `#国家安全`

---

<a id="item-finance-news-2"></a>
### [Anthropic IPO 后中国 AI 上市计划承压](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 7.0/10

Anthropic 规模 1195 亿美元的创纪录 IPO 成为科技股抛售导火索，自 6 月底以来，中国科技股市值累计蒸发 1.7 万亿美元。据报道，DeepSeek、月之暗面和阶跃星辰筹备或考虑中的上市计划因此蒙上阴影，但具体上市安排受影响程度尚未说明。

telegram · zaihuapd · 11月23日 09:31

**「背景」** Anthropic 此次 IPO 的定价被视为 OpenAI、DeepSeek、月之暗面（Kimi）和阶跃星辰等公司的估值参照，也将检验投资者是否愿意为 AI 增长和高额算力投入支付溢价。

**「中国 AI 公司融资承压」** Anthropic 上市后的科技股抛售已使中国科技股市值自 6 月底以来缩水 1.7 万亿美元，并给 DeepSeek、月之暗面和阶跃星辰推进股票发行带来更大的估值与融资压力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ifeng.com/c/8yCMLqBOM0H">戏剧性一幕， Anthropic 上 市 当天遭硅谷联合抵制_凤凰网</a></li>

</ul>
</details>

**标签**: `#人工智能`, `#IPO`, `#中国科技股`, `#市场抛售`

---

<a id="item-finance-news-3"></a>
### [SpaceX 据报向外出租 AI 算力](https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html) ⭐️ 7.0/10

据《纽约时报》援引三名知情人士报道，SpaceX 自 2026 年 5 月起向 Anthropic 和 Google 等公司出租数据中心算力，每月收入达数十亿美元；马斯克据称称 SpaceX 在 AI 领域落后，出租算力比自用更赚钱。上述数字和内部言论尚未获 SpaceX 确认。

telegram · zaihuapd · 11月24日 02:06

**「背景」** 据《纽约时报》援引三名知情人士，SpaceX 自 2026 年 5 月起将数据中心算力出租给 Anthropic 和 Google 等外部客户；马斯克称，出租比用于 SpaceX 自有 AI 项目更赚钱。

**「潜在影响」** 若报道属实，Anthropic 和 Google 租用 SpaceX 数据中心算力将增加其可用 AI 算力，并为 SpaceX 带来每月数十亿美元收入；但该收入规模及内部战略说法尚未获公司确认。

**标签**: `#SpaceX`, `#AI算力租赁`, `#Anthropic`, `#Google`, `#数据中心`

---

