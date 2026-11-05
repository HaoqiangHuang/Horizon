---
layout: default
title: "Horizon Summary: 2026-11-05 (ZH)"
date: 2026-11-05
lang: zh
---

> 从 43 条内容中筛选出 17 条重要资讯。

---

**科技新闻**
1. [Kimi K3.1 Pro 开放权重发布](#item-tech-news-1) ⭐️ 8.0/10
2. [Go 公布 encoding/json/v2 新 API](#item-tech-news-2) ⭐️ 8.0/10
3. [Anthropic 开源 FlashProve 推进可证明推理](#item-tech-news-3) ⭐️ 8.0/10
4. [腾讯 Hy4 开放权重模型及科学与游戏开发工具](#item-tech-news-4) ⭐️ 8.0/10
5. [GLM-5.3-Flash 的 Trainium2 NKI 融合内核](#item-tech-news-5) ⭐️ 8.0/10
6. [OpenAI 流水线生成 948 个 Linux 提权利用](#item-tech-news-6) ⭐️ 8.0/10
7. [IEEE Spectrum 探讨用 AI 偿还以 PHP2Shell 为例的长期软件安全债务](#item-tech-news-7) ⭐️ 7.0/10
8. [白宫网络发现住宅代理出口，端点仍未确认](#item-tech-news-8) ⭐️ 7.0/10
9. [OpenAI 拟收购 Git 工具公司 Pierre Computer](#item-tech-news-9) ⭐️ 7.0/10
10. [AMD 预计 Q4 营收以约 170 亿美元首次超过 Intel](#item-tech-news-10) ⭐️ 7.0/10
11. [Huginn 在 B200 上的循环权重复用剖析](#item-tech-news-11) ⭐️ 7.0/10
12. [OpenAI 称印度成 ChatGPT 最大周活市场](#item-tech-news-12) ⭐️ 7.0/10
13. [Calif 声称绕过 iPhone 锁定模式并维持越狱](#item-tech-news-13) ⭐️ 7.0/10
14. [升腾 960DT 部分客户需自购 HBM](#item-tech-news-14) ⭐️ 7.0/10
15. [OpenAI Images 2.6 支持 GIF 并提速 50%](#item-tech-news-15) ⭐️ 7.0/10
16. [蓝牙 Core 7.0 纳入可选 HDT，LE 最高速率升至 7.5 Mbps](#item-tech-news-16) ⭐️ 7.0/10

**财经新闻**
1. [甲骨文取消腾讯 70 亿美元芯片租赁协议](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Kimi K3.1 Pro 开放权重发布](https://huggingface.co/moonshotai/Kimi-K3.1-Pro) ⭐️ 8.0/10

月之暗面已在 Hugging Face 发布 Kimi K3.1 Pro 开放权重；官方称其为原生多模态智能体模型，总参数量 2.8T、激活参数量 104B，上下文长度约 100 万 token，是 K3.1 系列的首个模型。官方同时开放 platform.kimi.ai 上的 kimi-k3.1-pro API，兼容 OpenAI 和 Anthropic 接口，公开权重采用 MXFP4 量化格式。

hackernews · abrarthought · 11月4日 15:30 · [社区讨论](https://news.ycombinator.com/item?id=50366999)

**「从 API 上线到权重公开」** Horizon 的 10 月 24 日日报曾报道，Kimi K3.1 Pro 已上线 Kimi、Work、Code 和 API，但完整权重尚未发布，官方承诺最晚于 2026 年 11 月 4 日公开。此次 Hugging Face 上线的是 MXFP4 量化权重，补齐了当时仍待交付的下载与本地部署环节。

**「自托管成为可选路径，但集群门槛较高」** 权重发布后，开发者可下载 MXFP4 量化权重，在自有基础设施上部署并独立评估 Kimi K3.1 Pro；但其总参数达 2.8T，实施前必须核算相应的显存与集群资源。缺少自托管条件的团队可改用兼容 OpenAI 和 Anthropic 接口的官方 API，公开定价为每百万输入 token 2 美元、每百万输出 token 10 美元。

**「硬件门槛与实际表现仍有分歧」** 评论者对部署门槛和性能评价不一：有人估计运行该模型可能需要约 8 张 B300 组成节点，也有人认为其未明显超过 DeepSeek V4.1 Flash、存在“刷榜”嫌疑；另一位称其未在自己测试中复现这种差距，认为它虽未处于最前沿但已足够强。另有评论者称 Together 等第三方推理商已在托管该模型，并报告 Together 吞吐约为月之暗面端点的两倍、Modal 更高，但这些数字尚非独立验证结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.kimi.ai/blog/kimi-k3-1-pro">2026-10-24 — Kimi K3.1 Pro 发布，完整权重待 11 月 4 日前公开</a></li>
<li><a href="https://www.yottalabs.ai/post/kimi-k3-1-pro-specs-price-open-weights-benchmarks">Kimi K 3 . 1 Pro : Specs, Price, Open Weights Date, and... | Yotta Labs</a></li>

</ul>
</details>

**标签**: `#large language models`, `#model release`, `#open weights`, `#inference optimization`, `#Moonshot AI`

---

<a id="item-tech-news-2"></a>
### [Go 公布 encoding/json/v2 新 API](https://go.dev/blog/jsonv2) ⭐️ 8.0/10

Go 官方博客介绍了 \`encoding/json/v2\`，这是面向 Go 开发者重新设计的 JSON API，涉及 JSON 编解码，并可能为更高效、针对具体场景优化的解析器提供接口基础。当前材料没有给出稳定版可用性、所需 Go 版本、兼容性范围或性能基准，因此只能确认该 API 设计已公布，不能据此断言它已默认启用或能够带来可量化的性能提升。

hackernews · olexsmir · 11月4日 17:52 · [社区讨论](https://news.ycombinator.com/item?id=50369106)

**「背景」** Go 团队此前已以实验形式提供 \`encoding/json/v2\` 和 \`encoding/json/jsontext\`，当时这两个包默认不可见，官方也明确表示不会停止支持原有的 \`encoding/json\` v1。Go 1.27 正式引入新 API，其中 \`jsontext\` 负责 JSON 文本处理，\`encoding/json/v2\` 则在此基础上提供重新设计的对象编解码接口。

**「现有项目无需强制迁移」** 现有使用 encoding/json 的应用可以继续依赖 v1：Go 官方表示 encoding/json 与 encoding/json/v2 均受 Go 1 兼容性承诺约束，v1 将无限期受支持，因此项目没有必须迁移到 v2 的要求。

**「迁移成本与实际体验」** CamouflagedKiwi 对整体设计持正面评价，但指出缺少 \`MarshalIndent\`，替代写法复杂且不直观，令迁移和快速输出易读 JSON 都更加麻烦。txomon 则称其公司使用 \`jsontext\` 处理客户端错误分类时体验良好，并认为其速度出色；这是个人经验与评价，而非独立基准测试结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://go.dev/blog/jsonv2">A new Go API for JSON - The Go Programming Language</a></li>
<li><a href="https://go.dev/blog/jsonv2-exp">A new experimental Go API for JSON</a></li>
<li><a href="https://go.dev/blog/jsonv2">A new Go API for JSON - The Go Programming Language</a></li>

</ul>
</details>

**标签**: `#Go`, `#JSON`, `#encoding/json/v2`, `#API design`, `#parsing performance`

---

<a id="item-tech-news-3"></a>
### [Anthropic 开源 FlashProve 推进可证明推理](https://www.anthropic.com/research/provable-inference) ⭐️ 8.0/10

Anthropic 已发布 FlashProve 的技术规范和代码，利用模型承诺与逐请求加密证明，核验某段输出是否由指定模型生成；发布方需提供不暴露权重的模型指纹，用户可在本地设备完成验证。该机制面向模型替换检测和第三方执行声明审计，但项目仍在研究中，Anthropic 表示目前没有部署计划。讨论中转述的实现数据包括约 6.5 MB 的承诺文件、每次请求一份证明，以及约 90–100 倍的计算开销；24 线程验证约需 17 秒，单线程约需 21 秒。

hackernews · ltononro · 11月4日 17:17 · [社区讨论](https://news.ycombinator.com/item?id=50368626)

**「可证明推理的基本机制」** “可证明推理”要求服务商先对模型权重作出承诺，再为每次请求生成密码学证明，使验证者无需重新运行模型，也能确认输出确由获准模型计算得出。Anthropic 的研究材料称，FlashProve 将这一机制应用于 Mixture-of-Experts 模型 Llama 4 Maverick：离线阶段生成较短的权重承诺，在线阶段逐请求生成证明；它目前仍是研究原型，而非已部署能力。

**「实际影响」** 实际采用中，客户端可利用公开的模型指纹和逐请求证明，在本地核验输出是否确由所声明的模型生成，从而发现模型替换或执行冒名，且无需获取模型权重；不过每份证明约 19 MB，验证需耗时数秒，参考实现单张 H100 的生成速度约为 110 token/s。由于该方案仍在研究且暂无部署计划，现阶段不会改变现有 API 的响应兼容性，验证方也需先接入承诺值与证明流程才能获得这一保障。

**「社区评价与归因争议」** 评论者认为 FlashProve 相比既有零知识证明结果是“良好的起点”，但一名自称参与 VerInf 工作的研究者指责 Anthropic 将方案缩减到 400B Maverick 时“几乎没有署名”。另有观点指出，开放权重模型可直接确定性重算，因此这种密码学证明对闭源提供商更具意义；这些均为社区评价，而非独立测量或部署承诺。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://assets.claude.com/8e1d181a83015078581c92d896757041713f0160.pdf">FlashProve: an open-source library for provable inference</a></li>
<li><a href="https://www.anthropic.com/research/provable-inference">Progress on provable inference for large language models</a></li>
<li><a href="https://shattered.io/anthropic-flashprove-provable-inference-72x-overhead-2026/">Anthropic FlashProve: Provable Inference at 72x [2026]</a></li>
<li><a href="https://www.anthropic.com/research/provable-inference">Progress on provable inference for large language models \ Anthropic</a></li>

</ul>
</details>

**标签**: `#provable inference`, `#large language models`, `#cryptographic verification`, `#AI security`, `#model provenance`

---

<a id="item-tech-news-4"></a>
### [腾讯 Hy4 开放权重模型及科学与游戏开发工具](https://hy.tencent.ai/research/hy4) ⭐️ 8.0/10

腾讯 Hy4 项目推出开放权重的通用基础模型，并开源由 Hy4 与 Hyra 2.0 联合研发的两个科学基础模型：用于单细胞表征的 HyCell 和用于物理场建模的 HyPDE，面向生物学与物理模拟研究者和开发者。游戏开发方面，腾讯与互动娱乐事业群（IEG）的专业开发者整理训练数据和评测，覆盖功能实现、游戏逻辑、状态跟踪与资产管线，并将 Hy4 适配 Unreal Engine、Unity、Godot 及多人游戏开发。腾讯承认，按其内部评测，Hy4 虽被称为较强开放权重模型之一，但与顶级专有模型在研究级数学、长程编程、模型自改进和高级视觉问答方面仍有差距；现有材料未说明具体权重、许可证或基准分数。

hackernews · Philpax · 11月4日 14:11 · [社区讨论](https://news.ycombinator.com/item?id=50365780)

**「前情：Hy4 预览版」** 腾讯于 2026 年 8 月 28 日发布并开放 Hy4 预览版，称该阶段已扩大模型规模、上下文长度和数据量，并升级预训练与后训练。此次 Hy4 发布还配套开放了由 Hy4 与 Hyra 2.0 共同开发的单细胞表征模型 HyCell 和物理场建模模型 HyPDE。

**「游戏开发工作流影响」** 游戏开发团队现在可以在 Unreal Engine、Unity 和 Godot 工作流中试用或自行部署 Hy4：腾讯称已针对这些主要引擎完成适配，并在 Hy 系列中首次加入视觉理解，而开放权重让组织能够选择本地托管而非只能调用专有 API。评测时应区分当前 Hy4 与官方 Hy4 preview；后者采用 770B 总参数、49B 激活参数和超过 100 万 token 的上下文配置，不能未经核对便将这些规格视为完整版的统一承诺。

**「社区评价」** 评论者对 HyCell 和 HyPDE 开放科学工具表示欢迎，也特别肯定腾讯明确承认 Hy4 与顶级专有模型的差距；simonw 则关注其对主流游戏引擎和多人开发的支持。chriddyp 报告称，Hy4 在 Plotly 数据分析评测中的成本与准确率处于 GPT-6.1 Sol 和 GPT-6.1 Terra 之间，但处理过程非常 thorough，因而速度较慢；这是社区用户的个人测试结果，并非腾讯公布的独立基准结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tencent.com/tencent-launches-hy4-joining-the-ranks-of-the-worlds-leading-open-source-ai-models/">Tencent Launches Hy4, Joining the Ranks of the World&#x27;s ...</a></li>
<li><a href="https://www.tencent.com/tencent-releases-and-open-sources-tencent-hy4-preview/">Tencent Releases and Open-Sources Tencent Hy4 preview</a></li>
<li><a href="https://interestingengineering.com/ai-robotics/tencent-hy4-open-source-model">China&#x27;s Tencent Hy 4 challenges world&#x27;s top models with 7.2% error rate</a></li>
<li><a href="https://www.tencent.com/tencent-releases-and-open-sources-tencent-hy4-preview/">Tencent Releases and Open -Sources Tencent Hy 4 preview - Tencent</a></li>

</ul>
</details>

**标签**: `#foundation models`, `#open-weight AI`, `#AI for science`, `#game development`, `#Tencent`

---

<a id="item-tech-news-5"></a>
### [GLM-5.3-Flash 的 Trainium2 NKI 融合内核](https://www.reddit.com/r/MachineLearning/comments/1xo0yuq/p_nki_layer_megakernels_for_glm53flash_on_aws/) ⭐️ 8.0/10

RunAnywhere 开源了 trnrt，这是一套面向 AWS Trainium2 trn2.48xlarge 的 GLM-5.3-Flash（320B MoE、1M token 上下文）推理引擎，作者称其可在单个实例上运行该模型。对 batch 1 的 KDA 层剖析显示，线性注意力递推仅占注意力计算的一半，其余时间主要消耗在 mHC 预投影（36%）、XLA 胶水操作（33%）、转置和流混合（各 10%）。团队据此将每个半层融合为单个 NKI megakernel，稀疏注意力层则融合整层，并利用每个物理 NeuronCore 的 28 MiB SBBM 保留工作集；作者测量显示，稀疏注意力融合及 KDA、MoE 内核使 batch 8 的解码步耗时从 32.2 毫秒降至 24.2 毫秒，但仍高于 6.1 毫秒的内存下限。该项目没有 AWS 现有部署或同轨迹 GPU 基线，AgentX 成绩也是作者自行运行而非官方 InferenceX，因此这些数据不能证明其优于现有 AWS 方案或 GPU。

reddit · r/MachineLearning · /u/WildCard727 · 11月4日 21:47

**「背景」** GLM-5.3-Flash 是一个总参数量 3200 亿、每次激活 180 亿参数的原生多模态混合架构。解码时除了推进注意力和循环状态，还需反复传输权重并跨多个 NeuronCore 同步；AWS Trainium2 上的 NKI megakernel 通过融合层内碎片化算子、减少 HBM 往返，并把可重叠的 collective 移入内核来降低这些开销。

**「可复现方案与精度风险」** trnrt 及其 docs/RESULTS.md 为需要在 Trainium2 上部署 GLM-5.3-Flash 的团队提供了可重跑的基线和可复用的 NKI 优化路径，但 24.2 毫秒应被视为作者对自身实现的测量值。生产评估还需单独验证稀疏注意力 prefill 中保留的近似：它影响 1.2% 的选择，使下一 token 的对数概率平均偏移 0.012 至 0.021 nat，并在 448 个位置中的 3 个改变了最高概率 token；本次构建尚未进行任务级评测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.z.ai/guides/vlm/glm-5.3-flash">GLM - 5 . 3 - Flash /FlashX - Overview - Z.AI DEVELOPER DOCUMENT</a></li>

</ul>
</details>

**标签**: `#AWS Trainium2`, `#NKI`, `#LLM inference`, `#megakernels`, `#GLM-5.3-Flash`

---

<a id="item-tech-news-6"></a>
### [OpenAI 流水线生成 948 个 Linux 提权利用](https://openai.com/index/a-thousand-fewer-paths-to-root/) ⭐️ 8.0/10

据这条 Telegram 转述，OpenAI 称其自主漏洞研究流水线在 2026 年 10 月的一次 Linux 内核扫描中动态复现了 1,724 个漏洞，生成 948 个可让本地低权限用户取得 root 的 LPE 利用程序，另有 291 个信息泄露 PoC。OpenAI 报告总 API 成本为 1,213,430 美元，按产出计算每个成功 LPE 约需 1,279 美元，并称实际开发一个成功 exploit 的成本约为 359 美元，但摘要未解释两种成本口径。所谓“按历史 Pwn2Own/TyphoonPWN 赏金价值 1,890 万至 6,630 万美元、回报为成本的 16 至 55 倍”是基于历史奖金的推算，而非已实现收入或独立估值。摘要还称至少 10 种利用技术经第三方专家确认具有新颖性，但当前材料是二手信息，未提供受影响内核版本、复现方法、CVE 对应关系、验证流程或第三方确认链接，因此相关效果与新颖性仍应视为 OpenAI 的报告主张。

telegram · zaihuapd · 11月5日 03:04

**「理解本地提权与自主研究流水线」** 这里的“本地提权（LPE）”是指攻击者已经获得普通用户的本地执行权限后，利用 Linux 内核漏洞将权限提升至 root；它不同于直接取得远程代码执行，但可能让已有的低权限账户或主机立足点转化为完整系统控制。OpenAI 的官方介绍将这套系统描述为覆盖漏洞发现、利用验证和补丁生成的自主管线，其中一次运行不仅验证了 948 个 LPE 漏洞，还生成了相应补丁，API 成本约为 120 万美元。

**「内核修复审查压力上升」** Linux 内核维护者和系统运营者需要审查并发布一批新的修复：OpenAI 官方页面称，其自主流水线已验证 948 个本地提权漏洞并生成对应补丁。现有材料未给出受影响的内核版本、CVE 编号或补丁合入状态，因此管理员应依据对应上游公告核对版本与修复情况，不能仅凭“948”这一总数判断系统是否已经消除提权风险。

**「评论者解释漏洞规模」** 评论者对“948”这一数量为何如此之高提出不同解释：Plasmoid 怀疑根源在于 Linux 内核的复杂度或安全模型，nas 则表示本地提权原本就较为常见，但仍认为 948 个漏洞令人震惊；这些均属个人看法，并非对漏洞数量的独立验证。另一名自称项目团队成员的评论者 dangelosaurus 表示愿意回答团队问题，因此讨论中可能包含来自项目内部的信息。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/a-thousand-fewer-paths-to-root/">A thousand fewer paths to root - OpenAI</a></li>
<li><a href="https://openai.com/index/a-thousand-fewer-paths-to-root/">A thousand fewer paths to root | OpenAI</a></li>

</ul>
</details>

**标签**: `#AI漏洞发现`, `#Linux提权`, `#内核安全`, `#漏洞利用自动化`, `#自主AI`

---

<a id="item-tech-news-7"></a>
### [IEEE Spectrum 探讨用 AI 偿还以 PHP2Shell 为例的长期软件安全债务](https://spectrum.ieee.org/ai-in-cybersecurity-php2shell-vulnerability) ⭐️ 7.0/10

IEEE Spectrum 的一篇分析文章以 PHP2Shell 漏洞为具体案例，讨论 AI 辅助安全审计如何加速识别并修复长期积累的软件安全债务，把此前被忽视的老旧代码中的隐蔽缺陷重新推到修复队列里。文章的核心是判断与论证：AI 工具已使漏洞发现与修复成为可批量推进的工作流，使“还清几十年的旧账”成为可能。现有材料只包含文章的分析与观点，未提供可复现的实测结果，也未涉及厂商发布的新能力，因此“AI 迫使我们偿还 40 年技术债务”应视为作者判断，而非已被独立验证的结论。

hackernews · pseudolus · 11月4日 11:52 · [社区讨论](https://news.ycombinator.com/item?id=50364336)

**「事件背景」** 这里的“技术债”主要指长期积累、此前未被发现或未及时修复的软件安全缺陷。Horizon 10 月 30 日的日报曾报道，一份技术报告称 PHP2Shell 与 Linux 内核 XFRM/TCP 释放后重用漏洞可组成攻击链，并在 25 台服务器上取得 root 权限；当时该数量、攻击归因及补丁部署状态尚未获独立核实。IEEE Spectrum 11 月 2 日的后续报道补充称，漏洞利用被披露给 PHP Foundation 后，4 名工程师历时 2 个月开发补丁，因此 PHP2Shell 构成了讨论 AI 审计如何逐步清偿旧安全债务的具体事件背景。

**「PHP 部署与漏洞披露的直接影响」** 对运行 PHP 的组织而言，PHP2Shell 已构成需要优先处理的暴露风险：Moody&\#x27;s 于 2026 年 10 月 22 日称，CVE-2026-109618 和 CVE-2026-109619 两项关键漏洞已获宣布且处于积极利用阶段；Qualys 的评估则称几乎所有 PHP 安装均暴露，并提供了修复版本和升级指导。运维团队因此应立即盘点互联网暴露的 PHP 资产，并依据相关修复指引完成升级，而不是等待人工逐项发现漏洞。与此同时，AI 加速漏洞发现正在加大协调披露的难度：研究指出，独立团队可能在数周内找到同一缺陷，两个多月的禁运期已难以保证保密，发布方和安全厂商需要为并行发现及更短的响应窗口调整披露流程。

**「社区讨论」** swatcoder 质疑这究竟是“偿还技术债务”还是开启一场被强制的、只做修复而不交付新功能的无限跑步机，并指出不少问题仅靠针对性窄补丁解决，另一些则需要重构；xbmcuser 更乐观，认为 AI 审计让“开源软件会被他人审计”这一承诺真正成为现实，并提到自己几个月前因类似观点被大量反对。Arbortheus 希望 AI 能顺带找出被国家或企业间谍机构扣留的后门（提到 Pegasus），Balgair 借《哥德尔、艾舍尔、巴赫》的龟兔赛跑寓言提醒理论上不存在绝对安全的系统，glennfiedler 则预计漏洞集中曝光的阶段“会让人难受几个月”。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://dreamgroup.com/blog/chained-php2shell-exploit-roots-25-servers">2026-10-30 — PHP2Shell 与 Linux 内核漏洞链据称攻破 25 台服务器</a></li>
<li><a href="https://spectrum.ieee.org/ai-in-cybersecurity-php2shell-vulnerability">PHP 2 Shell Is a Wakeup Call for AI in Cybersecurity - IEEE Spectrum</a></li>
<li><a href="https://labs.cloudsecurityalliance.org/research/csa-research-note-php2shell-pre-disclosure-exploitation-2026/">PHP2Shell: Exploitation Before Disclosure for an AI-Found Flaw</a></li>
<li><a href="https://www.moodys.com/web/en/us/insights/insurance/PHP2Shell-critical-PHP-vulnerabilities-under-active-exploitation.html">PHP2Shell: Critical PHP vulnerabilities under active exploitation</a></li>
<li><a href="https://blog.qualys.com/vulnerabilities-threat-research/2026/10/20/php-announces-critical-security-release-for-two-vulnerabilities">PHP2Shell: Find, Mitigate, and Patch Now | Qualys | Qualys</a></li>

</ul>
</details>

**标签**: `#AI-assisted cybersecurity`, `#software vulnerabilities`, `#technical debt`, `#PHP`, `#secure software`

---

<a id="item-tech-news-8"></a>
### [白宫网络发现住宅代理出口，端点仍未确认](https://layer3intel.com/blog/residential-proxies-white-house-network) ⭐️ 7.0/10

Layer 3 Intel 报告称，在被关联到白宫网络的流量中检测到住宅代理出口，并提出白宫内部可能有一台设备被植入代理 SDK、充当流量中继。受感染的具体终端、所在网络区段及操作者均未确认，代理出口本身也不能证明相关住宅 IP 的物理使用地点就是白宫。因此，这仍是需要进一步核验的疑似设备失陷，而不是已证实的白宫网络入侵。

hackernews · Rasbora · 11月4日 20:45 · [社区讨论](https://news.ycombinator.com/item?id=50371246)

**「代理出口不等于物理位置」** 住宅代理通常通过分散的终端设备转发流量，因此检测到某个“出口”只能证明该地址曾被用于代理服务，不能单凭 IP 归属认定代理程序实际运行在白宫内部。Layer 3 Intel 的数据将住宅代理活动与白宫网络地址关联起来，但没有定位受感染终端、具体网络分区或背后的操作者，进一步归因仍需端点与网络遥测证据。

**「影响：代理出口可能被滥用并触发处置」** 检测到与白宫网络关联的住宅代理出口，并不等于已经确认白宫终端遭到入侵；但若这些出口确由受感染设备提供，设备就可能充当付费代理的出口节点，经由住宅 IP 转发第三方流量并消耗受害者带宽（tool-2-1）。这类代理基础设施可被用于撞库、网页抓取等自动化攻击（tool-2-2），因此网络运营方应将这些出口作为调查线索，核对代理与终端日志、定位并隔离可疑设备，并检查相关 IP 是否引发下游信誉或滥用处置；在设备和归属尚未确认前，不应把 IP 归属直接视为白宫内部终端已被攻陷的证明。

**「社区讨论」** 评论者引用报告中的时段分布称，约一半活动发生在美东时间下午 5 点至午夜、清晨几乎没有，这更像一台有人长期在晚间使用且感染代理 SDK 的设备，而非公共访客 Wi‑Fi。另一派则认为，目前掌握的只是住宅 IP 空间及代理出口归属，没有证据将其物理定位到白宫；相关地址也可能位于安全实验室、媒体访客网络或其他地点，因此不能断定感染设备就在白宫。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://layer3intel.com/blog/residential-proxies-white-house-network">Residential Proxies Detected on White House Network</a></li>
<li><a href="https://securityarsenal.com/blog/android-tv-box-botnet-takedown-how-to-detect-and-remove-residential-proxy-malware-from-13m-compromised-devices">Android TV Box Botnet Takedown: How to Detect and Remove ...</a></li>
<li><a href="https://datadome.co/threat-research/inside-kimwolf-traffic-residential-proxies-fuel-credential-stuffing-web-scraping-fraud/">Inside Kimwolf Traffic: How Residential Proxies Fuel ...</a></li>

</ul>
</details>

**标签**: `#cybersecurity`, `#residential proxies`, `#network security`, `#botnet malware`, `#government networks`

---

<a id="item-tech-news-9"></a>
### [OpenAI 拟收购 Git 工具公司 Pierre Computer](https://openai.com/index/openai-to-acquire-pierre/) ⭐️ 7.0/10

OpenAI 宣布拟收购 Pierre Computer，将这家聚焦 Git 基础设施和代理式编程工作流的开发者工具公司纳入旗下。现有公告未披露交易金额、完成条件、团队留任安排或产品整合时间表，因此目前只能确认收购计划，不能视为交易已经完成。依赖 Pierre 工具链的开发者短期内能否获得与 OpenAI 编码代理更紧密的集成，也尚无明确承诺。

hackernews · itunpredictable · 11月4日 15:21 · [社区讨论](https://news.ycombinator.com/item?id=50366863)

**「Pierre 与 Codex 的既有技术联系」** Pierre Computer 开发了基于 Git 的代码存储服务 Code Storage，以及开源工具 Trees、Diffs 和 Highlights；其中 Diffs 提供可修复差异代码的 Edit 模式。在此次收购宣布前，Codex 应用已经使用 Trees 和 Diffs 进行文件浏览与代码审查，因此此次交易整合的是 Codex 已依赖的工具和团队，而非一套全新工作流。OpenAI 表示这些开源项目将继续开放源代码，现有 Code Storage 客户也可继续使用相关服务。

**「Code Storage 收购后继续可用」** OpenAI 计划收购 Pierre Computer，并在收购完成后继续向 Code Storage 客户提供服务，同时把其功能逐步纳入 Codex。依赖 Code Storage 存储代码及机器生成文件的团队无需因这项交易立即停用或迁移现有工作流，但公告尚未说明整合时间表、兼容性或具体迁移安排。

**「社区讨论」** 社区用户将此次收购与 OpenAI 扩大 Git 基础设施的方向联系起来，并称 Pierre 的 Code.Storage 已被多款代理式编程产品用于保存生成代码及其他动态文件；这些说法来自评论者，未在所给公告中得到独立确认。另有评论者质疑大型实验室吸收成功工具团队的目的，除产品和人才整合外是否也涉及构建训练数据，但这属于社区猜测，而非已披露事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gate.com/news/detail/openai-to-acquire-pierre-computer-company-and-expand-codex-git-tools-25415087">OpenAI to Acquire Pierre Computer Company and Expand Codex ...</a></li>
<li><a href="https://aicoder.com/news/news-20261104-openai-to-acquire-pierre-computer-code-storage-trees-diffs-into-codex-git-for-agents">OpenAI to Acquire Pierre Computer Company: Code Storage Will ...</a></li>
<li><a href="https://openai.com/index/openai-to-acquire-pierre/">OpenAI to acquire Pierre Computer Company, Inc. | OpenAI</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#AI agents`, `#Git infrastructure`, `#developer tools`, `#acquisitions`

---

<a id="item-tech-news-10"></a>
### [AMD 预计 Q4 营收以约 170 亿美元首次超过 Intel](https://www.tomshardware.com/pc-components/cpus/amd-expects-to-outsell-intel-in-q4-for-the-first-time-in-history-usd17b-guidance-would-exceed-intels-projections) ⭐️ 7.0/10

AMD 给出的 2026 年第四季度营收指引约为 170 亿美元，按营收计算预计将首次超过 Intel 的同期预期。AMD 管理层将 Instinct AI 加速器销售列为增长的主要驱动力，但这仍是前瞻性指引，而非已经确认的营收或出货结果；相较 Nvidia，Instinct 的规模目前也仍然有限。

hackernews · rbanffy · 11月4日 15:38 · [社区讨论](https://news.ycombinator.com/item?id=50367125)

**「营收比较基线」** AMD 第三季度营收为 134 亿美元，并预计第四季度达到约 170 亿美元；同期报道列出的英特尔第四季度营收预测中点为 155 亿美元。因此，“首次超越”比较的是两家公司第四季度的总营收指引，并非 x86 CPU 市占率或 AI 加速器出货量的直接统计。

**「对服务器采购与平台选型的影响」** 对数据中心采购方而言，这一节点把服务器 CPU 的议价天平推向 AMD：Mercury Research 数据显示，EPYC 在 2025 年第四季度已拿下服务器/数据中心市场营收的 41.3%（tool-3-2），2026 年 5 月的后续统计更报出 46.2% 的纪录份额（tool-3-1）；若 AMD 约 170 亿美元的 Q4 指引兑现，其将首次超过英特尔的营收预期，因此云厂商与服务器 OEM 在新一轮 EPYC 与 Xeon 招标中可预期更强硬的 AMD 定价与供货谈判。需要注意的是，此处对比的是公司指引与预测口径，而非已确认的出货实绩，不宜据此提前锁定或单一化供应商。平台迁移上仍需按负载实测：EPYC Genoa（9004）在核心数、内存带宽和 PCIe 通道数上领先，而 Xeon Scalable 4th Gen（Sapphire Rapids）在旧有应用的单核性能与 AMX AI 加速上占优（tool-3-3）。

**「评论者质疑 AI 突破叙事」** 多数评论者认为，这更多反映了 Intel 的执行不力、13/14 代 CPU 电压问题及 AMD 现有产品竞争力的改善，而非 AMD 在 AI 领域取得全面突破；也有人指出 Instinct 相对 Nvidia 仍规模很小。另有评论者强调更强的 CPU 竞争总体有益，并表示 AMD 理应获得一次营收领先，但这些属于个人观点或个案经历，而非已证实事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tomshardware.com/pc-components/cpus/amd-expects-to-outsell-intel-in-q4-for-the-first-time-in-history-usd17b-guidance-would-exceed-intels-projections">AMD expects to outsell Intel in Q4 for the first time in ...</a></li>
<li><a href="https://hothardware.com/news/amd-pace-top-intel-revenue-first-time-after-crushing-q3">AMD On Pace To Top Intel In Revenue For First Time After ...</a></li>
<li><a href="https://wccftech.com/amd-is-set-to-out-earn-intel-for-the-first-time-in-its-history-guiding-to-17-billion-in-q4-revenue-against-intels-15-5-billion-midpoint-projection/">AMD Is Set To Out-Earn Intel For The First Time In Its ...</a></li>
<li><a href="https://hothardware.com/news/amd-epyc-server-revenue-share-epyc-gains-intel-xeon">AMD EPYC Server Revenue Share Hits Record 46.2% as EPYC Gains ...</a></li>
<li><a href="https://www.techpowerup.com/346287/report-amd-breaks-40-server-revenue-share-for-the-first-time">Report: AMD Breaks 40% Server Revenue Share for the First ...</a></li>
<li><a href="https://www.prodisknetwork.com/blog/amd-epyc-vs-intel-xeon-2026">AMD EPYC vs Intel Xeon in 2026: Head-to-Head for Enterprise ...</a></li>

</ul>
</details>

**标签**: `#AMD`, `#Intel`, `#AI accelerators`, `#CPU market share`, `#semiconductors`

---

<a id="item-tech-news-11"></a>
### [Huginn 在 B200 上的循环权重复用剖析](https://www.reddit.com/r/MachineLearning/comments/1xnskvt/do_looped_transformers_save_hbm_traffic_profiling/) ⭐️ 7.0/10

作者在 NVIDIA B200 上使用可复现代码和 Nsight Compute 原始数据剖析 Huginn，发现共享权重的收益取决于其能否驻留缓存。8 个矩阵乘复用同一份 72 MiB 权重时，比使用 8 份相同权重快 24%，且几乎不再从 HBM 读取权重；当工作集增至 288 MiB、超过 L2 容量后，性能差异消失。完整的 Huginn Core 教学实现采用随机权重，其连续 8 次迭代耗时和 HBM 读取量都约为单次迭代的 8 倍，说明复用参数本身并不会阻止 GPU 每轮重新从 HBM 取数。

reddit · r/MachineLearning · /u/2dayyy6 · 11月4日 16:26

**「参数共享不等于省带宽」** 循环 Transformer 在多次迭代中重复使用同一组权重，而 HBM 是 GPU 位于片外的主存储器，L2 则是容量更小的片上缓存。判断权重共享能否减少 HBM 流量，关键不仅是参数量，还包括共享权重能否在迭代之间保留在缓存中。

**「大模型需按逐轮读取估算」** 对于在 B200 等 GPU 上优化 Huginn 或同类循环架构的开发者，共享权重只有在工作集能够驻留 L2 时才可能节省 HBM 流量；权重过大时，参数共享不能直接转化为带宽或性能收益。文中提出使用持久化内核跨迭代保留权重，但尚未提供相应实现或实测结果。

**标签**: `#Looped Transformers`, `#GPU Memory Systems`, `#HBM Traffic`, `#NVIDIA B200`, `#Model Profiling`

---

<a id="item-tech-news-12"></a>
### [OpenAI 称印度成 ChatGPT 最大周活市场](https://economictimes.indiatimes.com/tech/newsletters/morning-dispatch/openais-india-user-base-doubles-rapido-gov-quadruples/articleshow/135478625.cms) ⭐️ 7.0/10

OpenAI 印度区负责人称，印度已成为 ChatGPT 全球周活跃用户最多的市场，自今年 1 月以来当地用户数翻倍，但报道未披露绝对用户规模或统计方法。OpenAI 预计未来数周公布与 UPI 及其他支付方式相关的消息，目前这仍只是预告。公司还表示，企业采用正从试点阶段转向规模化部署。

telegram · zaihuapd · 11月4日 09:31

**「印度市场的本地化基础」** OpenAI 面向印度的产品适配重点包括语音、印地语及其他地方语言、低端智能手机和 UPI 支付，为 ChatGPT 在当地吸引用户提供了具体场景。报道所称“最大市场”仅指周活跃用户口径，未披露绝对用户规模或统计方法，也未说明收入或付费用户规模，因此这一排名目前属于 OpenAI 印度管理层给出的口径。

**「印度企业规模化部署需检查身份管理」** 随着印度企业的 ChatGPT 应用从试点转向规模化部署，组织应将 SSO、SCIM 和用户管理纳入上线检查，以应对账号与权限管理需求；OpenAI 帮助中心已提供这些企业级功能的配置指南。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://economictimes.indiatimes.com/tech/newsletters/morning-dispatch/openais-india-user-base-doubles-rapido-gov-quadruples/articleshow/135478625.cms">OpenAI’s India user base doubles; Rapido GOV quadruples</a></li>
<li><a href="https://cio.eletsonline.com/artificial-intelligence/chatgpt-india-largest-market/76671/">ChatGPT India Largest Market, Says OpenAI MD</a></li>
<li><a href="https://help.openai.com/">OpenAI Help Center</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#ChatGPT`, `#India`, `#AI adoption`, `#payments`

---

<a id="item-tech-news-13"></a>
### [Calif 声称绕过 iPhone 锁定模式并维持越狱](https://appleinsider.com/articles/26/11/04/apples-lockdown-mode-thwarted-by-a-new-persistent-iphone-jailbreak) ⭐️ 7.0/10

据 AppleInsider 转述，黑客团队 Calif 在 X 发布视频，声称一台启用“锁定模式”的 iPhone 18 Pro 已被越狱，且越狱状态在升级至 iOS 27.2 后仍然保留；演示中先通过 AirDrop 接收 PDF，再进入“设置”完成更新。Calif 未公开漏洞或利用代码，称正将漏洞披露给苹果，并表示不会发布越狱工具。由于目前仅有视频演示，这项安全突破仍待漏洞细节披露及独立验证；苹果则曾宣称锁定模式自 2022 年以来防护成功率为 100%。

telegram · zaihuapd · 11月4日 14:38

**「锁定模式与此前研究」** “锁定模式”是苹果为可能遭受定向间谍软件攻击的高风险用户提供的可选、极限防护措施，随 iOS 16、iPadOS 16 和 macOS Ventura 于 2022 年推出；苹果在 2026 年 3 月宣称，自该模式推出以来没有启用者被间谍软件攻破，但这一结论属于苹果的声明（tool-2-1、tool-2-2、tool-2-3）。Horizon 10 月 24 日摘要此前记录了 Calif 团队宣称攻破 iPhone，但当时未说明受影响型号、iOS 版本或完整利用链，也未明确是否绕过锁定模式；此次演示补充了 iPhone 18 Pro 和 iOS 27.2 的信息，却仍未提供漏洞细节或独立验证材料（tool-1-1）。

**「用户仍需保持锁定模式防护」** 如果该演示可复现，依赖 iPhone 锁定模式抵御恶意文件攻击的用户和安全团队不能仅凭升级至 iOS 27.2 判断风险已经消除，因为演示中的越狱在更新后仍然有效。Calif 尚未公开漏洞细节且表示不会发布越狱工具，因此当前没有公开的完整利用方案；用户仍应保持锁定模式开启、谨慎处理来源不明的 PDF，并等待苹果发布修复或披露后验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.calif.io/p/iphone">2026-10-24 — 研究项目称已成功攻破 iPhone</a></li>
<li><a href="https://support.apple.com/en-us/105120">About Lockdown Mode - Apple Support</a></li>
<li><a href="https://www.apple.com/newsroom/2022/07/apple-expands-commitment-to-protect-users-from-mercenary-spyware/">Apple expands commitment to protect users from mercenary ...</a></li>
<li><a href="https://techcrunch.com/2026/03/27/apple-says-no-one-using-lockdown-mode-has-been-hacked-with-spyware/">Apple says no one using Lockdown Mode has been hacked with ...</a></li>
<li><a href="https://www.idropnews.com/news/persistent-iphone-jailbreak-bypasses-lockdown-mode-ios-27-2/270604/">Persistent iPhone Jailbreak Bypasses Lockdown Mode</a></li>
<li><a href="https://www.gadgetreview.com/apples-lockdown-mode-was-supposed-to-protect-iphones-hackers-found-a-way-around-it">Apple&#x27;s Lockdown Mode Was Supposed to Protect iPhones ...</a></li>

</ul>
</details>

**标签**: `#iOS安全`, `#越狱`, `#Lockdown Mode`, `#漏洞披露`, `#Apple`

---

<a id="item-tech-news-14"></a>
### [升腾 960DT 部分客户需自购 HBM](https://thenextweb.com/news/huawei-hbm-smuggling-samsung-sk-hynix-ascend-960dt) ⭐️ 7.0/10

据 The Information 经 The Next Web 转述，华为已告知部分升腾 960DT 客户，这款下一代旗舰 AI 芯片主要使用三星和 SK 海力士的 HBM，客户需自行解决内存来源；报道将这一要求与中国厂商 HBM 产能不足联系起来。报道还称，相关 HBM 会先焊在性能极弱的处理器上，按处理器编码报关运往香港，再由人携带进入内地并加热拆下。深圳一名芯片经纪人称，单颗 HBM3E 价格已从一年前的数百美元升至约 4,000 美元；不过这仍是二手报道，来源未给出华为公告或独立验证的交付数据。

telegram · zaihuapd · 11月4日 14:52

**「国内 HBM3E 供给仍处早期扩张」** 10 月 29 日的日报曾援引路透社消息称，长鑫存储已向多家中国本土 AI 芯片设计公司送样 HBM3E，并计划在报道发布后两个月内启动限量生产；报道所述良率仅为 20% 至 30%，测试性能也更接近 SK 海力士上一代 HBM3。上述量产计划和指标尚未获得独立验证，仅表明当时国内高带宽内存产能仍处于早期扩张阶段，尚不能确认其能缓解升腾 960DT 的供货压力。

**「客户需自行承担 HBM 采购成本」** 受影响的升腾 960DT 客户需要自行锁定 HBM3E 货源、核验来源及进口合规性，并将内存成本单独纳入项目预算；据 The Information 转述，单颗 HBM3E 已从一年前的数百美元涨至约 4000 美元。TrendForce 还报道称，HBM 短缺已推动华为把升腾 950DT 的建议价格上调至超过 25 万元人民币，显示内存供给紧张会直接传导至加速器采购预算，因此客户不能再假定华为会统一解决 960DT 的内存供应。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/world/china/chinas-cxmt-start-advanced-ai-memory-production-despite-poor-yields-sources-say-2026-10-28/">2026-10-29 — 长鑫存储拟限量生产 HBM3E</a></li>
<li><a href="https://www.trendforce.com/news/2026/11/03/news-china-reportedly-obtains-smuggled-hbm-via-server-packages-huawei-960dt-faces-domestic-hbm-shortage/">[News] China Reportedly Obtains Smuggled HBM via Server...</a></li>

</ul>
</details>

**标签**: `#Huawei Ascend 960DT`, `#HBM3E`, `#AI accelerators`, `#semiconductor supply chains`, `#Huawei`

---

<a id="item-tech-news-15"></a>
### [OpenAI Images 2.6 支持 GIF 并提速 50%](https://openai.com/index/introducing-images-2-6/) ⭐️ 7.0/10

OpenAI 已将 Images 2.6 上线至 ChatGPT、Codex 和 API，新增 GIF 动图生成，并称整体生成速度提升 50%；编辑图像时，角色、产品和品牌细节的一致性也有所改善。API 提供 Flare 和 Sunburst 两个版本：Flare 在低质量设置下最快 6 秒出图，Sunburst 面向中高质量生成，强调细节与一致性。官方还称平台目前每周生成 40 亿张图片，但未披露速度对比、质量评测、定价或测试方法，因此这些提升主要是厂商声明，尚无独立基准佐证。

telegram · zaihuapd · 11月4日 23:42

**「Images 2.6 的 API 分层」** Images 2.6 在 API 端拆分为 GPT-Image-2.6 Flare 与 Sunburst：Flare 面向低质量、低延迟场景，OpenAI 官方页面称最快 6 秒即可出图；Sunburst 则覆盖中高质量，侧重细节和一致性。因此，GIF 动图支持与“生成速度提升 50%”分别对应输出格式扩展和 API 产品分层，但来源未提供独立基准或测试方法，速度提升幅度仍应视为官方口径。

**「API 开发者的档位选择」** API 使用者现在需要在 GPT Image 2.6 Flare 与 Sunburst 之间按场景取舍：Flare 面向低延迟，官方称最快 6 秒出图；Sunburst 面向中高质量及更稳定的产品、角色和品牌细节。OpenAI 声称整体生成速度较此前提升 50%，但现有材料未提供价格、GIF 限制或统一质量基准，迁移工作流前应分别实测延迟、成本和一致性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/introducing-images-2-6/">Introducing Images 2 . 6 | OpenAI</a></li>
<li><a href="https://openai.com/index/introducing-images-2-6/">Introducing Images 2 . 6 | OpenAI</a></li>
<li><a href="https://www.youtube.com/watch?v=HChz2zbWoIc">OpenAI Releases Images 2 . 6 : ChatGPT Makes GIFs, API ... - YouTube</a></li>

</ul>
</details>

**标签**: `#generative-AI`, `#image-generation`, `#OpenAI`, `#API`, `#text-to-image`

---

<a id="item-tech-news-16"></a>
### [蓝牙 Core 7.0 纳入可选 HDT，LE 最高速率升至 7.5 Mbps](https://www.bluetooth.com/press/bluetooth-high-data-throughput-opens-a-new-chapter-in-wireless-performance/) ⭐️ 7.0/10

蓝牙技术联盟于 11 月 4 日宣布采纳 Bluetooth High Data Throughput（HDT），将 Bluetooth LE 的理论最高速率从 2 Mbps 提高至 7.5 Mbps，并改善容量、能效与可靠性。HDT 是 Bluetooth Core 7.0 中的可选特性，可与旧设备兼容共存，但这并不意味着现有设备已经获得新速率。首个标准化应用将面向高端无线音频，支持无损及高解析度音频，相关产品预计于 2027 年推出。

telegram · zaihuapd · 11月5日 01:39

**「HDT 的可选特性定位」** 此前 Bluetooth LE 的理论最高速率为 2 Mbps，HDT 则以 Bluetooth Core 7.0 中可选特性的方式加入，而不是统一修改所有 LE 链路。蓝牙核心规范定义了实现互操作蓝牙设备所需的技术，因此旧设备仍可使用既有能力，而 7.5 Mbps 只有在相关设备均支持并启用 HDT 时才适用。

**「实际影响」** HDT 是 Bluetooth Core 7.0 中的可选特性，芯片与终端厂商需要显式实现并启用它才能用满 7.5 Mbps 的速率上限，同时由于它可与旧设备共存，现有蓝牙耳机、手柄和外设用户无需更换硬件即可继续使用（tool-2-1）。代价是速率红利不会立即落地：蓝牙技术联盟把高解析度与无损音频列为 HDT 的首个标准化应用方向，而首批相关音频产品预计要到 2027 年才上市（tool-2-1、tool-2-2），在此之前未支持 HDT 的设备仍停留在原有速率，采购或适配时需确认设备两端是否都支持 HDT 才能获得所宣称的容量与音质提升。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bluetooth.com/press/bluetooth-high-data-throughput-opens-a-new-chapter-in-wireless-performance/">Bluetooth® High Data Throughput opens a new chapter in ...</a></li>
<li><a href="https://www.bluetooth.com/wp-content/uploads/Files/Specification/HTML/Core-54/out/en/index-en.html">Bluetooth Core Specification</a></li>
<li><a href="https://www.androidpure.com/bluetooth-hdt-high-data-throughput/">Bluetooth HDT Promises Up to 7.5 Mbps, First Audio Gear Due 2027</a></li>
<li><a href="https://argenox.com/blog/bluetooth-is-about-to-get-much-faster-meet-hdt">Bluetooth HDT Is Coming: BLE Speeds Jump to 7.5 Mbps</a></li>

</ul>
</details>

**标签**: `#Bluetooth`, `#Bluetooth LE`, `#无线音频`, `#技术标准`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [甲骨文取消腾讯 70 亿美元芯片租赁协议](https://www.tradingview.com/news/seekingalpha:e51e68f4d094b:0-oracle-cancels-7b-ai-chip-lease-with-tencent-amid-us-concerns-ft/) ⭐️ 7.0/10

据报道，甲骨文在美国政府施压下取消了一项与腾讯价值约 70 亿美元、为期五年的 AI 芯片租赁协议，但相关报道未提供官方原始信源及明确取消日期。

telegram · zaihuapd · 11月4日 11:01

**「背景」** 此前，腾讯据报道与甲骨文签下一份为期五年、估值约 70 亿美元的 AI 芯片租赁协议，拟租用约 10 万枚先进芯片，并通过甲骨文在东南亚的数据中心获得在中国境内无法使用的芯片；该安排处于中美芯片出口限制背景下。

**「业务影响」** 腾讯原计划通过甲骨文在东南亚的数据中心取得最多约 10 万枚先进 AI 芯片，该五年协议取消后，这项境外 AI 算力扩充安排将无法按原计划落地。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.zerohedge.com/ai/oracle-kills-7bn-tencent-ai-chip-deal-under-trump-pressure">Oracle Kills $ 7 BN Tencent AI Chip Deal Under Trump Pressure</a></li>
<li><a href="https://diesignal.com/articles/tencent-signs-7-billion-five-year-lease-for-100-000-oracle-ai-chips-18f11e57">Tencent Leases 100 , 000 Oracle AI Chips in $ 7 Billion Five - Year Deal</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/oracle-cancels-7-billion-tencent-113659321.html?fr=sycsrp_catchall">Oracle Cancels $7 Billion Tencent AI Chip Leasing Agreement ...</a></li>
<li><a href="https://www.cnbctv18.com/business/companies/oracle-scraps-7-billion-chip-deal-with-china-tencent-after-us-pressure-report-20026711.htm">Oracle scraps $7 billion chip deal with China&#x27;s Tencent after ...</a></li>

</ul>
</details>

**标签**: `#甲骨文`, `#腾讯`, `#AI芯片`, `#出口管制`, `#云计算`

---