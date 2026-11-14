---
layout: default
title: "Horizon Summary: 2026-11-14 (ZH)"
date: 2026-11-14
lang: zh
---

> 从 39 条内容中筛选出 8 条重要资讯。

---

**科技新闻**
1. [TorchTitan 在 384 块 GH200 上扩展 1T MoE](#item-tech-news-1) ⭐️ 8.0/10
2. [Haskell 生态技术愿景聚焦工具链与调试](#item-tech-news-2) ⭐️ 7.0/10
3. [FAA 全国性地面停飞指令](#item-tech-news-3) ⭐️ 7.0/10
4. [FM-1 Workbench：浏览器测试自定义固件](#item-tech-news-4) ⭐️ 7.0/10
5. [AI 据称从哥德尔笔记中恢复数百项定理](#item-tech-news-5) ⭐️ 7.0/10
6. [Microsoft 365 核心服务全球宕机超 12 小时](#item-tech-news-6) ⭐️ 7.0/10
7. [DeepSeek 扩展应用 API 并开放独立工具调用](#item-tech-news-7) ⭐️ 7.0/10
8. [OpenAI 推出 ChatGPT Wallet 支付钱包](#item-tech-news-8) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [TorchTitan 在 384 块 GH200 上扩展 1T MoE](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

发帖方报告，PyTorch/TorchTitan 团队在 JUPITER 的 384 块 GH200 上将约 1T 参数 MoE 训练扩展至约 1,300 tokens/s/GPU，较起点提高 14 倍；这是作者给出的运行结果，摘要未提供独立复现。配置采用 384 路 FSDP、节点内 4 路专家并行且不使用流水线并行；初始 84 秒的基线步骤中有 68 秒用于等待网络，团队因此以全激活重计算单项提升 4 倍吞吐，并用 FlexShard 按完整专家分片，让 Muon 的 Newton-Schulz 在本地零通信执行。团队还向 TorchTitan 贡献了在参数驻留 Grace 主机时仍在 GPU 上运行 Newton-Schulz 的修复，将优化器步骤从 42 秒降至约 2 秒并提高 35% 吞吐；FP8 专家 all-gather 提升 18%，缓存分配器跨 CUDA 流修复则提升 21%，并把 384 个 rank 的分配器重试降为零。按注意力成本预排批次提升 13%，组限制路由提升 7%，但早期试跑提示后者可能损害训练；\`private\_unshard\_async\_op\` 当时仍是私有、仅计划转为公共 API 的开关。

reddit · r/MachineLearning · /u/f14-bertolotti · 11月13日 16:28

**「万亿参数 MoE 的分片基础」** 约 1T 参数 MoE 的全部权重无法装入单卡，因此该实验采用 384 路 FSDP 切分参数，并通过节点内 4 路专家并行让每张 GPU 持有完整专家矩阵、负责接收对应 token。团队没有采用需要大量微批次的流水线并行，以避免节点间通信和流水线气泡拖慢故障排查；与此同时，FlexShard 按完整专家分片，使 Muon 的 Newton–Schulz 正交化能够在 GPU 本地完成，无需聚合被切散的矩阵。

**「对大规模 MoE 训练的直接影响」** 这为拥有类似 384 卡 GH200 集群的机构提供了一条无需 root 权限的公开 PyTorch 训练路径：作者在 JUPITER 共享系统上以 TorchTitan 的 FSDP 与专家并行训练了约 1T 参数 MoE，报告吞吐约为每 GPU 1,300 tokens/s。同类工程可优先测试作者的三个优化：将主机参数上的 Newton–Schulz 运算移至 GPU 后，优化器步由 42 秒降至约 2 秒、吞吐提高 35%；修正 FSDP 侧 CUDA 流缓存分配后，384 个 rank 的分配器重试归零、吞吐提高 21%；FP8 专家 all-gather 带来 18% 提升。TorchTitan 已提供 FSDP2 与 4D 并行能力，PyTorch 社区也有在 FSDP2 中启用 FP8 all-gather 的实践，但这些倍率不能直接外推：\`unshard\_async\_op\` 当时仍是私有接口，组限制路由虽提高 7% 吞吐却可能损害早期训练效果，团队仍需按自身互连拓扑和模型配置验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.skills.sh/orchestra-research/ai-research-skills/distributed-llm-pretraining-torchtitan">distributed-llm-pretraining-torchtitan...</a></li>
<li><a href="https://discuss.pytorch.org/t/distributed-w-torchtitan-enabling-float8-all-gather-in-fsdp2/209323">[Distributed w/ Torchtitan] Enabling Float8 All - Gather in FSDP 2</a></li>

</ul>
</details>

**标签**: `#mixture-of-experts`, `#large-scale training`, `#TorchTitan`, `#PyTorch`, `#GPU systems`

---

<a id="item-tech-news-2"></a>
### [Haskell 生态技术愿景聚焦工具链与调试](https://discourse.haskell.org/t/a-technical-vision-for-the-haskell-ecosystem/15078) ⭐️ 7.0/10

一篇题为《A technical vision for the Haskell ecosystem》的论坛长文提出 Haskell 生态的技术愿景，面向语言用户、工具链维护者和库作者讨论可用性、调试与生态方向。当前材料未提供文章正文，无法核实具体提案、版本目标、兼容承诺或实施时间表；该帖属于方向性讨论，并非已经交付的语言或工具更新。

hackernews · cosmic\_quanta · 11月13日 14:43 · [社区讨论](https://news.ycombinator.com/item?id=50484235)

**「技术治理背景」** 这篇愿景的制度背景是 Haskell Foundation 技术领导委员会经过数周讨论后完成组建并进入运作状态。委员会表示，将通过主动制定倡议和提案来推进需要资金与执行的生态项目，并向企业、承包者和志愿者开放参与，因此讨论重点是生态治理与开发方向，而非某个语言版本的发布。

**「社区关注不同的生态优先级」** ecshafer 认为 Haskell 的简洁表达与类型安全可能适合 AI 代理式编程；pmkary 则更关心它能否像 JavaScript 一样覆盖桌面、移动和 Web 应用。georgewsinger 以其 Haskell VR 合成器支持实时单步调试的实践强调交互式调试的价值，time4tea 则把 JVM 的长期 API 稳定性和软硬件映射作为相关目标的参照。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://discourse.haskell.org/t/a-technical-vision-for-the-haskell-ecosystem/15078">A technical vision for the Haskell ecosystem</a></li>

</ul>
</details>

**标签**: `#Haskell`, `#functional programming`, `#programming languages`, `#developer tooling`, `#software ecosystem`

---

<a id="item-tech-news-3"></a>
### [FAA 全国性地面停飞指令](https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247) ⭐️ 7.0/10

美国联邦航空管理局（FAA）于 11 月 13 日发布全国性地面停飞指令，暂停全美离场航班，直接影响航空旅客与承运人。现有材料提供了 FAA 公告和《纽约时报》实时报道链接，但尚未给出完整的故障调查或恢复时间表。空管通信网络故障是报道中的主要方向，而与 SMART AI 空管部署有关只是评论者提出的可能性，现有证据无法确认 AI 系统是诱因。

hackernews · zulln · 11月13日 21:05 · [社区讨论](https://news.ycombinator.com/item?id=50489641)

**「背景」** 全国性地面停飞是指 FAA 对全美离场航班统一实施暂停，以在空管通信等关键系统异常时控制运行风险。一名评论者援引 FAA 11 月 10 日公告称，名为 SMART 的系统已在全部 22 个空管中心投入使用，因此社区猜测 AI 部署可能与此次中断有关；另一名评论者则援引《华尔街日报》称，故障涉及 L3Harris 负责监督、承载空管无线电频率的电信网络。现有材料尚未证实其中任一说法是停飞原因。

**「进出航班全面延误」** 全国性停飞令使美国所有机场的离港航班暂停，同时造成进港航班延误；随着沿途管制设施逐步恢复，航班只能在 FAA 空中交通管制系统指挥中心协调后获准起飞，航空公司和旅客需等待分批放行，不能预期停飞会立即全面解除。

**「故障原因与处置状态仍有争议」** 评论者援引《华尔街日报》称，中断似乎涉及 L3Harris 监督的电信网络；该网络承载空管控制员与飞行员通信所用的关键无线电频率，但是否也影响雷达馈送尚不清楚。另有评论者将故障与 FAA 于 11 月 10 日宣布将在全国 22 个空管中心使用 SMART 系统联系起来，但这只是未经证实的因果猜测；评论中还出现了地面停飞被解除以及官员预计故障可能持续较长时间两种说法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theguardian.com/us-news/live/2026/nov/13/us-politics-latest-news-updates-democrats-republicans-donald-trump-van-hollen-chuck-schumer?page=with:block-6af791ef8f080d8d1c27a4e8">US flight outage live updates: FAA grounds ... | The Guardian</a></li>
<li><a href="https://www.abc.net.au/news/2026-11-14/follow-live-us-aviation-authority-grounds-all-flights/107385742">US aviation authority grounds all departing flights , citing...</a></li>

</ul>
</details>

**标签**: `#FAA`, `#Air Traffic Control`, `#AI Systems`, `#Critical Infrastructure`, `#Aviation Outage`

---

<a id="item-tech-news-4"></a>
### [FM-1 Workbench：浏览器测试自定义固件](https://open.m-vave.com/fm1-workbench) ⭐️ 7.0/10

FM-1 Workbench 是一个面向 FM-1 可编程音乐设备的固件实验平台，用于开发、测试自定义及生成式固件。平台汇集社区项目并提供可在浏览器中运行的模拟器，让用户先试用不同固件方案，再考虑是否安装到硬件。现有材料将其描述为面向软硬件创作者的小众工具，未提供广泛行业采用或重大技术突破的证据。

hackernews · simonebrunozzi · 11月13日 19:14 · [社区讨论](https://news.ycombinator.com/item?id=50488325)

**「FM-1 固件开发生态」** FM-1 此前已形成由社区自定义固件和浏览器模拟器组成的开发生态：资源库集中提供固件目录、文档、MIDI SysEx 协议工具及刷写器，另有模拟器可加载固件中心等来源的作者构建版本。在这一基础上，Workbench 将 WebAssembly 模拟、测试和 USB 直刷固件整合进在线工作台，定位是把原本分散的试用与刷写流程集中起来。

**「可试用并可回退的固件开发流程」** 实际影响是，用户可借助浏览器模拟器先试用社区生成的 FM-1 固件，再决定是否刷入硬件，并在刷写后通过 Workbench 恢复官方固件。兼容性上，若要从 M-VAVE Open 或 Big Screen 转到 FM-1 Mirror 等方案，需先在 Chrome 或 Edge 的“Device update → Recovery &amp; force update → Restore original V15”流程中恢复原版 V15；更新界面还要求确认已备份，因此用户操作自定义固件时应先保存现有工作。

**「社区讨论」** 评论者对其价值存在分歧：jimmyjazz14 认为多数固件功能用电脑和 MIDI 控制器早已能够实现，而且通常更省事；tlahtinen 则表示会每隔几天安装新固件，并特别依赖浏览器模拟器筛选 NACHTFART、DUB-1 等方案。swiftcoder 将固件项目的增长及厂商支持视为后 LLM 音乐技术中少见的亮点，但这些属于用户体验和主观评价，而非独立测量结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/aroum/fm1-custom-fw/blob/main/README.md">fm 1 - custom -fw/README.md at main · aroum/ fm 1 - custom -fw · GitHub</a></li>
<li><a href="https://joakimeriksson.github.io/fm1-emu/">FM - 1 Emulator</a></li>
<li><a href="https://www.youtube.com/watch?v=SSGu3JJb20s">ChoralRoot on a Big Screen: Adding FM - 1 Mirror to a Community ...</a></li>
<li><a href="https://github.com/pfkellogg/fm1-mirror">GitHub - pfkellogg/ fm 1 -mirror: The M - VAVE FM - 1 &#x27;s screen, big, on...</a></li>

</ul>
</details>

**标签**: `#FM-1`, `#music hardware`, `#custom firmware`, `#generative music`, `#creative coding`

---

<a id="item-tech-news-5"></a>
### [AI 据称从哥德尔笔记中恢复数百项定理](https://www.theguardian.com/science/2026/nov/13/kurt-godel-notebooks-ai-helps-unlock-hidden-discoveries-man-who-transformed-maths) ⭐️ 7.0/10

《卫报》报道称，AI 协助解读了库尔特·哥德尔未发表的笔记，并从中找出数百项据称已获证明的定理，相关工作还涉及他研究的 14 个逻辑主题。现有材料未披露这些证明的识别与复核方法，也缺少可供独立检验的技术证据，因此这仍是受到质疑的研究主张，而非已经确认的数学突破。

hackernews · bookofjoe · 11月13日 17:30 · [社区讨论](https://news.ycombinator.com/item?id=50486748)

**「手稿释读与证明核验」** 哥德尔的未刊笔记本并非已经整理、验证并可直接引用的论文，而是需要先解读其手写记号（包括评论中提到的 Gabelsberger 速记）、复原论证，再判断其中内容是否构成有效证明。因此，所谓“数百个已证明定理”能否成立，关键在于转写和证明核验是否可靠、可复查；现有材料没有提供这套方法或独立验证。

**「定理主张仍待独立验证」** 现阶段，这些成果只能被视为有待核查的候选定理，而不能直接计入已验证的数学发现。研究团队需要公布手稿转写与释读方法、证明检查流程及其技术证据，并说明 AI 是否参与判断证明的逻辑有效性，才能让数学界评估这批手稿的可靠性。

**「评论者质疑解释与验证」** 一位评论者援引科学史家的说法，称哥德尔通常只发表经过严格审查的工作，并据此质疑这些定理只是偶然写成的；这是评论者的判断，而非已验证事实。另一名评论者指出，AI 并未讨论这些笔记体系的一致性或完备性，也有人希望进一步了解那 14 个逻辑主题的具体内容。

**标签**: `#AI for mathematics`, `#Gödel archives`, `#formal logic`, `#AI-assisted discovery`

---

<a id="item-tech-news-6"></a>
### [Microsoft 365 核心服务全球宕机超 12 小时](https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/) ⭐️ 7.0/10

据路透社报道，Microsoft 365 旗下的 Outlook、Teams 和 Copilot 截至 11 月 13 日仍处宕机状态，故障已持续超过 12 小时。微软将原因归为服务器问题，表示未发现恶意活动，并称已扩大修复范围、出现回稳迹象。澳大利亚、日本和美国部分政府机构以及 Euronext 邮件系统受到影响，台湾部分金融机构改用传真确认交易；此次中断被描述为 Microsoft 365 今年第二次服务中断。

telegram · zaihuapd · 11月13日 12:21

**「Microsoft 365 中断背景」** 此次事件涉及 Microsoft 365 的核心服务：Outlook 邮件、Teams 协作和 Copilot 均受到影响；截至 11 月 13 日，故障已持续超过 12 小时，波及澳大利亚、日本和美国部分政府机构，以及 Euronext 邮件和台湾交易确认等金融流程。微软将原因归因于服务器问题并称未发现恶意活动，但现有材料没有公布具体根因；报道将其称为 Microsoft 365 今年第二次中断，表明这是大范围服务可用性事件，尚不足以据此认定为安全攻击。

**「关键业务需要备用通信通道」** 此次中断已从日常协作波及政府通信和金融交易确认，例如台湾金融机构改用传真确认交易、Euronext 邮件受阻。依赖 Microsoft 365 的机构应准备邮件和 Teams 之外的备用通信及人工确认流程，以降低核心服务故障对业务连续性的影响。

**标签**: `#Microsoft 365`, `#Service Outage`, `#Microsoft Teams`, `#Cloud Infrastructure`

---

<a id="item-tech-news-7"></a>
### [DeepSeek 扩展应用 API 并开放独立工具调用](https://mp.weixin.qq.com/s/78KBHc4-4N5b2vfL9SkutQ) ⭐️ 7.0/10

据该消息，DeepSeek 扩展了现有 API：开发者开启相应参数后，即可使用深度思考、搜索、文件输入、链接读取和语音等能力，工具调用与上下文拼接由服务端自动完成。V4.1-Flash 已被纳入三个接口的支持范围，Search、Fetch、OCR、ASR、TTS 还可单独调用；官方同时开源了 deepseek-ai/chat-demo，该前端 Demo 可导入历史对话，并支持基于 API 本地部署网页端。该信息来自二手渠道，尚未提供接口文档、价格、性能指标和兼容性细节，实际可用范围仍需以官方文档为准。

telegram · zaihuapd · 11月13日 14:27

**「背景：V4.1-Flash 的模型与接口基础」** Horizon 11 月 3 日的日报曾报道，SGLang v0.5.23 发行说明新增了对 DeepSeek-V4.1 与 DeepSeek-V4.1-Flash 的支持，并称在 GB300 负载下 V4.1 的 prefill 吞吐最高提升 1.5 倍、32K 至 64K 提示的首 token 延迟约降低约 28%（均为项目方在特定配置下的测试数据），说明本次开放 API 所依托的模型版本此前已在开源推理侧可用。DeepSeek 官方 API 文档确认，V4.1-Flash（deepseek-flash）的搜索、网页读取、OCR、ASR、TTS 能力同时覆盖 Messages、Responses 与 Chat Completions 三个接口，工具调用与上下文拼接由服务端处理，其中这五项工具也可作为独立 API 提供给自定义流程。Hugging Face 上的 V4.1-Flash 模型页另提到，面向生产使用还提供 deepseek-recipe——一套带 Python 绑定的 Rust 库，提供与协议感知工具包一致的提示词格式。

**「现有 API 可直接接入多模态工具」** 按该消息，开发者可在原有 DeepSeek API 中通过参数启用深度思考搜索、文件输入、链接阅读和语音，并单独调用 Search、Fetch、OCR、ASR、TTS；服务端负责工具调用与上下文拼接，因此不必自行编排多套外部工具。官方开源的 chat-demo 还支持导入历史对话，可用于本地部署和接口联调；但在生产接入前，仍需核对 V4.1-Flash 涉及的三个接口、参数与鉴权方式、限流和计费，因为官方 API 平台明确说明价格可能调整，具体应以 API 文档为准。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/sgl-project/sglang/releases/tag/v0.5.23">2026-11-03 — SGLang v0.5.23 新增多模型与低延迟推理支持</a></li>
<li><a href="https://api-docs.deepseek.com/news/news261113/">The full DeepSeek App experience, now via API | DeepSeek API Docs</a></li>
<li><a href="https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash">deepseek - ai / DeepSeek - V 4 . 1 - Flash · Hugging Face</a></li>
<li><a href="https://www.deepseek.com/en/platform/">DeepSeek | API Platform</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#大模型API`, `#工具调用`, `#多模态AI`, `#开源Demo`

---

<a id="item-tech-news-8"></a>
### [OpenAI 推出 ChatGPT Wallet 支付钱包](https://openai.com/index/introducing-chatgpt-wallet/) ⭐️ 7.0/10

OpenAI 宣布推出 ChatGPT Wallet，允许智能体代用户付款而不接触真实卡号；首批通过 dots 向美国年满 18 岁、持有美国发行卡的 ChatGPT Pro 用户开放。该钱包与美国运通、万事达和 Visa 合作，用户需逐笔核对商品与金额，并通过 Face ID 或指纹确认后，由支付网络签发替代真实卡号的令牌。

telegram · zaihuapd · 11月13日 15:43

**「支付预告与钱包落地」** Horizon 11 月 5 日的日报曾报道，OpenAI 预告未来数周会公布与 UPI 及其他支付方式相关的消息，但当时没有具体功能或开放范围。此次发布的 ChatGPT Wallet 落地范围则是美国 18 岁以上 ChatGPT Pro 用户，需使用美国发行的卡并逐笔进行 Face ID 或指纹确认，不能视为此前所指的印度 UPI 功能已经上线。

**「支付仍需用户逐笔批准」** 符合条件的美国 18 岁以上 ChatGPT Pro 用户现在可通过 dots 授权智能体使用美国运通、万事达或 Visa 卡结账；智能体接触的是令牌化卡号，用户仍须逐笔核对商品与金额，并通过 Face ID 或指纹确认。该能力暂不适用于其他地区、其他订阅层级或非美国发行的卡，不能视为面向所有 ChatGPT 用户的通用支付服务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://economictimes.indiatimes.com/tech/newsletters/morning-dispatch/openais-india-user-base-doubles-rapido-gov-quadruples/articleshow/135478625.cms">2026-11-05 — OpenAI 称印度成 ChatGPT 最大周活市场</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#payments`, `#OpenAI`, `#tokenization`

---