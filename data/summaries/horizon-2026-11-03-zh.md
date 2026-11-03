# Horizon 每日速递 - 2026-11-03

> 从 43 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [ChatGPT 分享链接漏洞可致账号接管](#item-tech-news-1) ⭐️ 8.0/10
2. [400 多款 AI 应用被指暗藏色情深伪功能](#item-tech-news-2) ⭐️ 8.0/10
3. [vLLM v0.33.0rc3 转向 CUDA 13 并扩展模型支持](#item-tech-news-3) ⭐️ 7.0/10
4. [SGLang v0.5.23 新增多模型与低延迟推理支持](#item-tech-news-4) ⭐️ 7.0/10
5. [Astra 探索直接读写神经网络权重](#item-tech-news-5) ⭐️ 7.0/10
6. [Cloudflare 定向 DNS 构建降低延迟与内存](#item-tech-news-6) ⭐️ 7.0/10
7. [Ubuntu LTS 仍未修补 CVE-2026-98432](#item-tech-news-7) ⭐️ 7.0/10
8. [阿布扎比与 OpenAI 签署四项 AI 合作协议](#item-tech-news-8) ⭐️ 7.0/10

**科技博客**
1. [大模型读改权重并非超人能力](#item-tech-blog-1) ⭐️ 7.0/10
2. [受众俘获：代理指标如何扭曲真正目标](#item-tech-blog-2) ⭐️ 6.0/10

**财经新闻**
1. [Anthropic 招股书披露前三季度营收 332.4 亿美元、净亏损 1040 亿美元](#item-finance-news-1) ⭐️ 7.0/10
2. [英国拟延长多数永久居留申请等待期](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [ChatGPT 分享链接漏洞可致账号接管](https://www.parameter.ai/labs/we-found-a-gap-at-openai) ⭐️ 8.0/10

Parameter 研究团队披露并协助修复了一个 ChatGPT 分享链接漏洞：受害者只需打开恶意链接，即可在已登录的会话中触发代码执行、读取私密对话，并将数据发送至外部服务器，全程无需安装应用。该漏洞源于预览功能与图表组件之间的消息处理缺陷。OpenAI 已于 10 月 26 日完成修复，将问题定级为 P1，并向研究团队支付了 5000 美元赏金。

telegram · zaihuapd · 11月2日 10:24

**「HTML 预览沙箱逃逸」** 11 月 1 日的 Horizon 日报曾把这条攻击链具体化为针对 ChatGPT“HTML 预览”（曾称 Canvas）的沙箱逃逸：恶意代码通过 postMessage 触发父页面的 MathLive 虚拟键盘处理，再利用 innerHTML 注入不受沙箱限制的 iframe，随后借助 CSP 允许的 YouTube oEmbed 反射执行 JavaScript。Horizon 当时称 OpenAI 已关闭漏洞并支付总计 5,000 美元赏金，但未说明修复版本或部署时间；本次来源则补充了 10 月 26 日的修复日期和 P1 定级。

**「实际影响」** 恶意 ChatGPT 分享链接可借助页面中的 HTML/CSS 预览功能，在受害者已登录的会话中执行代码；受害者仅需打开链接，私密对话就可能被读取并外传至外部服务器，从而为账号接管创造条件。用户应避免打开来源不明的分享链接，安全团队则应将 ChatGPT 分享页视为潜在的认证会话代码执行载体；OpenAI 已于 10 月 26 日修复该问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://simonwillison.net/2026/Oct/31/how-we-took-over-chatgpt-accounts/">2026-11-01 — ChatGPT HTML 预览漏洞导致账户接管</a></li>
<li><a href="https://rrtechpulse.com/stories/chatgpt-shared-link-account-flaw/">ChatGPT shared link flaw, fixed Oct. 26 | RR Tech Pulse</a></li>
<li><a href="https://www.techtimes.com/articles/317528/20260601/chatgpt-share-links-deliver-malware-openai-domain-evading-corporate-web-filters.htm">ChatGPT Share Links Deliver Malware From OpenAI Domain...</a></li>

</ul>
</details>

**标签**: `#ChatGPT`, `#OpenAI`, `#安全漏洞`, `#账号接管`, `#代码执行`

---

<a id="item-tech-news-2"></a>
### [400 多款 AI 应用被指暗藏色情深伪功能](https://www.wired.com/story/hundreds-of-mundane-ai-apps-are-hiding-abusive-deepfake-features/) ⭐️ 8.0/10

WIRED 于 11 月 2 日调查发现，一个由 400 多款关联应用和网站组成的网络，以宠物画像、语言学习等普通 AI 工具为掩护，在满足特定条件时加载远程色情深伪界面，允许用户上传他人照片生成露骨图像或视频。研究人员通过代码、域名和广告追踪确认这些产品之间的关联；截至 9 月仍在 Google Play 上架的 27 款应用累计下载量超过 35 万次，其中不少被标记为适合所有年龄。苹果收到线索后下架了 19 款相关应用，称开发者在审核通过后替换了远端网页内容；谷歌在被联系前已移除其中多数应用，Meta 则称已阻止 209 款相关应用投放广告。报道将这一网络与中文开发者及一家香港注册公司联系起来，但相关运营方未回应置评请求，该归属仍属于媒体和研究人员的调查判断。

telegram · zaihuapd · 11月2日 12:45

**「动态远端内容带来的审核盲区」** 此次调查的关键背景是，移动应用获批后仍可由开发者替换服务器端的远端网页内容。苹果称涉事应用正是通过这种做法，在审核通过后加载色情深伪界面，因此仅检查首次提交版本的应用商店难以发现后续功能变化。

**「应用审核与设备治理风险」** 一次应用商店审核或“适合所有年龄”标签已不足以证明此类应用的后续内容安全：9 月仍在 Google Play 上架的 27 款相关应用累计下载超过 35 万次，企业采购和移动设备管理团队应排查相关应用，并审查其远端内容与权限。对开发者而言，审核通过后替换远端网页、隐瞒深伪功能会直接带来下架风险；Apple 已因此移除 19 款应用，因此申报功能应与线上实际提供的功能保持一致。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://appleinsider.com/articles/26/11/02/hundreds-of-ai-apps-were-part-of-a-network-hiding-sexually-abusive-deepfake-tools">Hundreds of AI apps hid abusive deepfake tools from reviewers</a></li>
<li><a href="https://aiweekly.co/alerts/wired-traces-400-ai-apps-hiding-abusive-deepfake-tools">WIRED traces 400+ AI apps hiding abusive deepfake tools</a></li>

</ul>
</details>

**标签**: `#AI深伪`, `#应用商店治理`, `#平台审核`, `#滥用安全`, `#技术调查`

---

<a id="item-tech-news-3"></a>
### [vLLM v0.33.0rc3 转向 CUDA 13 并扩展模型支持](https://github.com/vllm-project/vllm/releases/tag/v0.33.0rc3) ⭐️ 7.0/10

vLLM 发布了 v0.33.0 的第三个发布候选版 v0.33.0rc3，汇集 927 次提交，并新增 Reflection Beam-1.0、Yandex AliceAI-Foundation-80B-A3B、Recursive Flint 等模型支持。该版本将基础栈升级到 PyTorch 2.14.0、torchvision 0.29.0 和 Triton 3.8.0；默认 CUDA wheel 和镜像仅支持 CUDA 13.0，CUDA 12.9 wheel 及 \`-cu129\`、\`-cu129-ubuntu2404\` 镜像停止发布，同时提供与 libtorch ABI 稳定的 CUDA wheel、AWS EFA 镜像和 ROCm 10.0 默认产物，ROCm 7.2 仍可使用 \`-rocm72\` 变体。服务接口新增对受支持生成模型默认启用的 \`/v1/decisions\`、token embeddings 与可选 late chunking，并扩展推测解码及多种 NVIDIA、AMD 优化；其中 1.04–1.31 倍、1373→3390 tok/s 等性能数字来自相关 PR 基准，并非独立测量。升级前需检查兼容性：Medusa、MLP speculator 和旧 Ray compiled-graph executor 已被移除，生成暂停期间的请求现在返回 HTTP 503，NIXL connector 要求 NIXL 1.5 或更高版本，LM Format Enforcer 与 \`--ir-opriority\` 则已弃用。

github · khluu · 11月2日 10:10

**「部署基础」** vLLM 面向大模型推理与 API 服务，发布时会按 CUDA、ROCm、CPU 和 XPU 等后端分别提供 Python wheel 与 Docker 镜像，因此 PyTorch/libtorch ABI 和加速器运行时版本会直接影响现有部署能否继续复用。此次变更的底层背景是 CUDA 12.9 wheel 与 \`-cu129\` 镜像此前仍在发布；v0.33.0 将默认构建切换到 CUDA 13.0，同时以 \`-rocm72\` 保留 ROCm 7.2 通道，而默认 ROCm 构建转向 ROCm 10.0。

**「升级需重建 CUDA 环境」** 现有 CUDA 12.9 GPU 部署若升级到 vLLM v0.33.0，将无法继续使用已停发的 cu129 wheel 和镜像，必须切换到默认 CUDA 13.0 构建；该版本同时升级至 PyTorch 2.14.0、torchvision 0.29.0 和 Triton 3.8.0。由于 vLLM 文档指出其 CUDA 内核会因 CUDA 或 PyTorch 构建配置不同而产生二进制不兼容，并建议使用全新环境，运维方应重建隔离环境和容器镜像，而不是在现有 CUDA 12.9 环境中原地升级。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.vllm.ai/en/stable/getting_started/installation/gpu/">GPU - vLLM</a></li>

</ul>
</details>

**标签**: `#vLLM`, `#LLM inference`, `#PyTorch`, `#CUDA`, `#release notes`

---

<a id="item-tech-news-4"></a>
### [SGLang v0.5.23 新增多模型与低延迟推理支持](https://github.com/sgl-project/sglang/releases/tag/v0.5.23) ⭐️ 7.0/10

SGLang v0.5.23 已发布，发行说明称该版本包含 257 名贡献者提交的 1,007 个 PR，并为 Muse Spark Open、Beam-1.0、MiniMax-M3.1-Flash、MiniCPM-V 4.7 等 LLM/VLM，以及 Cosmos3-Nano-Sim、FastH3 Omni、FLUX.3 Image Klein、HY-Nomas、MOSS-Image 等扩散模型新增支持与 cookbook。发布说明报告，DeepSeek-V4.1 在 GB300 负载下 prefill 吞吐最高提高 1.5 倍，32K 至 64K 提示的首 token 延迟约降低 28%；启用可选的 NVIDIA megakernel 或 AMD monokernel 后，DeepSeek-V4.1-Flash 单用户 decode 在 GB300 和 MI350X 上最高分别快 44% 和 75%，这些数字对应项目方测试的特定配置。其他新增项包括可在单张消费级 GPU 上运行超出显存容量的 MoE 模型的 Paged Experts（项目方称最高比 CPU 卸载快 30 倍）、通过 SGLang-TorchTPU 支持 Google TPU7x、面向 FP8/NVFP4 量化 MoE 的可选 LoRA 引擎，以及让采用 decode 上下文并行的 DeepSeek 风格 MLA 模型将前缀缓存保留在 HiCache 文件式 L3 存储中的能力。用户可通过 \`uv pip install --prerelease=allow sglang==0.5.23\` 升级，官方同时提供 NVIDIA CUDA 13、AMD MI30x/MI35x ROCm 10、Intel GPU/XPU、Intel Xeon/CPU 和 TPU7x（TorchTPU，镜像标签 \`v0.1.0-tpu\`）的 Docker 镜像。

github · Fridge003 · 11月2日 22:14

**「理解此次版本的两条技术主线」** 理解 SGLang v0.5.23 时需要区分“模型覆盖”与“执行栈优化”：前者为新增 LLM/VLM 和扩散模型提供 cookbook，后者围绕 DeepSeek-V4.1、MoE、推测解码、缓存及持久化内核调整推理路径。MoE 会按 token 选择部分专家，推测解码则先由草稿模型提出 token、再由目标模型验证，因此发布说明中的首 token 延迟、prefill 吞吐和单用户解码提升均针对特定提示长度、并发度及硬件，不能直接视为所有工作负载的固定收益。

**「低延迟升级需分场景验证」** 升级至 SGLang 0.5.23 后，DeepSeek-V4.1-Flash 部署者可按硬件选择低延迟模式；发布说明称，NVIDIA megakernel 与 AMD monokernel 融合持久内核可让单用户 decode 在 GB300 和 MI350X 上最高分别提升 44% 和 75%。这些是发布方给出的性能上限而非普遍保证；该项目此前曾记录 DeepSeek-V4-Pro 在 2×4 GB300、并发 1 时 decode 吞吐回退约 5%，因此上线前应使用 \`uv pip install --prerelease=allow sglang==0.5.23\` 安装，并在目标模型、GPU 数量和并发条件下做 A/B 压测，再决定是否启用内核插件。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/sgl-project/sglang/issues/42074">[Bug] DeepSeek-V4-Pro decode ~5% slower at concurrency 1 on ...</a></li>

</ul>
</details>

**标签**: `#SGLang`, `#AI inference`, `#open source`, `#multimodal models`, `#diffusion models`

---

<a id="item-tech-news-5"></a>
### [Astra 探索直接读写神经网络权重](https://rikiyat.github.io/blog/weight-space-programming/) ⭐️ 7.0/10

研究项目 Astra 展示了“权重空间编程”：据项目博客，GPT-6 Astra 能够直接读取并改写神经网络权重，而不只是调整提示词或调用常规训练工具。博客称，Astra 可从原始权重判断小型网络所受的训练任务，并在没有环境反馈的情况下从零生成游戏网络，其表现超过经 PPO 训练 1 亿步的网络；作者还报告称，直接编辑一个小型 Qwen 模型的权重可改善其数学表现。现有材料主要是项目方博客和讨论片段，未提供足以复核该结果的模型、数据、基线、评测集或独立复现，因此这些结论应视为待验证的研究报告，而非已经证实的通用能力。

hackernews · dbreunig · 11月2日 18:21 · [社区讨论](https://news.ycombinator.com/item?id=50341174)

**「权重空间编程的概念与既有基础」** 这里的“权重空间编程”是指让模型直接读取、解释并改写神经网络参数中的数值权重，而不是仅通过提示词或环境反馈间接影响模型；例如，Astra 可依据权重幅度判断游戏玩家只会出现在底行。评论者 yurimo 指出，权重编辑、生成和定位本身已有研究，因此这项工作的关键新增点是 Astra 无需环境反馈即可原生完成这些操作，并将直接编辑用于提升 Qwen 的数学能力。

**「对模型开发者的影响」** 这为模型开发者提供了一条无需编写训练循环或依赖梯度下降的局部干预路径：GPT-6 Astra 直接编辑小型 Qwen3 模型的权重，在作者测试中仅改动约 0.016% 的权重，便将 MATH-500 得分从 7.9% 提高到 48.1%。不过该结果来自作者自测，尚不能视为独立验证或可泛化的优化能力；实际采用前仍需通过独立实验确认收益能否复现。

**「评论者质疑结果是否被夸大」** 评论者对结果的重要性存在分歧：yurimo 认为博客及其传播夸大了发现，并指出权重编辑、权重生成和权重识别此前已经存在；xg15 则认为，当前模型快速理解复杂系统的能力使这种表现并非完全出人意料。vessenes 将小型 Qwen 模型数学能力约提升 5 倍视为最惊人的证据，vanyle 则猜测它可能源于专门使用权重数据训练或递归自我改进路线；这些数字与因果解释仍需论文细节和独立验证支持。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50341174">Astra can read and write weights to improve Qwen | Hacker News</a></li>
<li><a href="https://kingy.ai/blog/weight-space-programming-ai-agent-model-weights/">Weight-Space Programming: GPT-6 Astra Edits Qwen - kingy.ai</a></li>
<li><a href="https://runtimewire.com/article/gpt-6-astra-edits-qwen-weights-weight-space-programming">GPT-6 Astra edited 0.016% of Qwen&#x27;s weights and its math ...</a></li>

</ul>
</details>

**标签**: `#weight editing`, `#LLM agents`, `#Qwen`, `#model introspection`, `#AI research`

---

<a id="item-tech-news-6"></a>
### [Cloudflare 定向 DNS 构建降低延迟与内存](https://blog.cloudflare.com/dns-targeted-zone-builds/) ⭐️ 7.0/10

Cloudflare 报告称，其 DNS 定向区域构建（targeted DNS zone builds）将 DNS 构建延迟缩短一半，并使内存使用量下降 85%，主要影响其大规模 DNS 区域构建流程。现有材料未提供测量环境、绝对时延、内存基线、适用版本或实现细节，因此这些数字应视为 Cloudflare 披露的内部案例结果，而非经过独立验证的性能基准。

hackernews · wondersky · 11月2日 14:47 · [社区讨论](https://news.ycombinator.com/item?id=50337558)

**「背景：DNS 区域全量重建」** 此前，Cloudflare 的 DNS 区域设置发生变化时，系统会重建整个区域，即使该区域包含数千万条记录，因此单次小改动也可能产生很高的延迟和内存开销。此次优化的前提是引入“定向构建”机制，仅重建受设置变更影响的部分，而不是默认执行全量重建。

**「对 DNS 基础设施的影响」** 对 Cloudflare 的 DNS 基础设施团队，按目标区域构建将构建延迟减半、内存占用降低 85%，可减少持续更新大量 DNS 区域时的资源压力；现有材料并未证明客户侧 DNS 解析或传播延迟同步下降。评估该方案时，运维团队仍需按实际变更速率验证吞吐量，并对关系化后的增量构建进行长期正确性测试，因为评论者对每秒处理 700 次变更是否足够以及可能引入的缺陷表示疑虑。

**「社区质疑」** 评论者主要追问这类优化的投入回报：在内存价格仍可能高企时，减少内存占用能带来多大研发收益；一名评论者还以“每秒 700 次变更”为参照，质疑这一吞吐量相对 Cloudflare 的规模是否偏低。另有评论者关心 relational 改造在长期运行中是否会引入新缺陷，这些均属于社区疑问，而非已证实的问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.cloudflare.com/dns-targeted-zone-builds/">How we halved DNS build delay and cut memory use by 85%</a></li>
<li><a href="https://daily.dev/posts/how-we-halved-dns-build-delay-and-cut-memory-use-by-85--jhnmypmtx">How we halved DNS build delay and cut memory use by 85%</a></li>

</ul>
</details>

**标签**: `#DNS`, `#Cloudflare`, `#Systems Performance`, `#Memory Optimization`, `#Technical Deep Dive`

---

<a id="item-tech-news-7"></a>
### [Ubuntu LTS 仍未修补 CVE-2026-98432](https://freenode.net/article/ubuntu-lts-kernels-still-unfixed-for-critical-cve-2026-98432) ⭐️ 7.0/10

据报道，截至 2026 年 11 月 2 日，Ubuntu LTS 内核仍未发布 CVE-2026-98432 的修补，这一状态已持续近三周；该 Linux IPv4 TCP 释放后使用漏洞被描述为可由远程攻击者无需认证、无需用户交互利用并实现代码执行。来源还称 Anthropic 已公布针对 MPTCP 监听端口的 RCE 利用示例；Go 官方安全团队提示，自 Go 1.24 起，Linux 上的 listen socket 默认启用 MPTCP，因此 Go 服务可能默认暴露于相关攻击面，即使没有 MPTCP 监听也可能受到同类攻击。报道没有说明 Ubuntu 延迟修补的原因，也未提供官方缓解指引。

hackernews · majorchord · 11月2日 18:39 · [社区讨论](https://news.ycombinator.com/item?id=50341462)

**「背景：漏洞已公开近三周，修复仍在测试」** Horizon 在 11 月 1 日的日报中已把 CVE-2026-98432 描述为 Linux 内核 IPv4 TCP 路径中的释放后重用（UAF）缺陷，CVSS 评分 9.8，且并非 MPTCP 专属问题，当时也没有已成功利用的公开演示。Ubuntu 安全页早在 10 月 15 日就登记了该 CVE，而 Ubuntu 官方博客称针对它的修复已进入 -proposed 仓库、正针对 22.04 LTS 等版本进行测试，这说明截至目前 Ubuntu 仍未发布正式安全更新。此外，一份此前未经独立核实的报告称该内核 UAF 曾与 PHP2Shell 组合成链式利用并取得服务器 root，这也意味着仅修补其中一处缺陷可能不足以阻断攻击。

**「对 Ubuntu LTS 与 Go 服务的实际影响」** 对运行在 Ubuntu LTS 上的服务而言，后果是默认暴露：自 Go 1.24 起，Linux 上的 listen socket 默认启用 MPTCP，而 CVE-2026-98432 是 IPv4 TCP 握手中的远程释放后使用（use-after-free）缺陷，CVSS 评分 9.8，攻击者无需认证、无需用户交互即可从网络侧触发；Anthropic 已公开针对 MPTCP 监听端口的远程 root 代码执行利用示例，Red Hat 的 Bugzilla 记录同时提到其 AlmaLinux 环境中相关内核参数默认处于关闭状态。该问题已于 10 月 15 日在上游内核修复、Red Hat 于 11 月 1 日发布修复内核，但 Ubuntu 至今未发布补丁，因此在补丁到位前，Ubuntu LTS 运维只能自行更新内核或采用缓解措施：讨论中有开发者建议用 iptables/nftables 在 raw PREROUTING 阶段按 TCP 标志位直接丢弃匹配数据包以阻断利用路径，而 Red Hat 的缓解方案被社区引述为「降低对该漏洞的暴露面但无法完全阻止」。此外，Go 官方安全团队提示，即使没有 MPTCP 监听的服务也可能受到同类攻击，故不能仅以「未启用 MPTCP」作为风险豁免理由。

**「社区建议与质疑」** 一名评论者建议在 raw PREROUTING 链中使用 iptables 的 u32 匹配规则提前丢弃相关 TCP 流量，称可在漏洞路径触发前阻断；该方案未获 Ubuntu 官方确认，应视为临时的社区建议。评论者还质疑 Ubuntu 为何近三周既不修补也不解释原因；有人援引 RHEL 的缓解方案，但转述的说法仅称其能“降低暴露、不能完全阻止”，具体覆盖范围并不清楚。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://atlasum.net/blog/cve-2026-98432-linux-ipv4-tcp-uaf">2026-11-01 — CVE-2026-98432：Linux IPv4 TCP 释放后重用漏洞</a></li>
<li><a href="https://dreamgroup.com/blog/chained-php2shell-exploit-roots-25-servers">2026-10-30 — PHP2Shell 与 Linux 内核漏洞链据称攻破 25 台服务器</a></li>
<li><a href="https://ubuntu.com/blog/fixes-available-in-proposed-pocket-for-cve-2026-98432">Fixes available in -proposed pocket for CVE-2026-98432 - Ubuntu</a></li>
<li><a href="https://ubuntu.com/security/CVE-2026-98432">CVE-2026-98432 | Ubuntu</a></li>
<li><a href="https://atlasum.net/blog/cve-2026-98432-linux-ipv4-tcp-uaf">Linux &#x27;s October 2026 TCP Use-After-Free: CVE - 2026 - 98432 — Atlas</a></li>
<li><a href="https://lilting.ch/en/articles/linux-ipv4-tcp-options-uaf-mptcp-rce">CVE - 2026 - 98432 Linux TCP Use-After-Free Can Give... | lilting channel</a></li>
<li><a href="https://bugzilla.redhat.com/show_bug.cgi?id=CVE-2026-98432">2553390 – ( CVE - 2026 - 98432 ) CVE - 2026 - 98432 kernel : ipv4: free...</a></li>

</ul>
</details>

**标签**: `#Linux kernel security`, `#Ubuntu LTS`, `#remote code execution`, `#vulnerability patching`, `#firewall mitigation`

---

<a id="item-tech-news-8"></a>
### [阿布扎比与 OpenAI 签署四项 AI 合作协议](https://thenextweb.com/news/openai-abu-dhabi-deals-machine-readable-government-mubadala) ⭐️ 7.0/10

阿布扎比与 OpenAI 签署四项协议，启动“机器可读政府”试点，将政策法规转换为 AI 可读格式，辅助官员核查许可和证书申请；该流程已在食品进口环节试点，最终决定权仍保留给官员。其余合作包括穆巴达拉与 OpenAI、G42 旗下 Inception42 开展投资分析，Inception42 另签五年协议向阿联酋政府、企业和学校提供模型，以及 ADNOC 成为首家采用 OpenAI Frontier 平台的能源公司。报道未披露协议条款、成本、具体模型或成效数据，因此这些部署的实际范围与结果仍待确认。

telegram · zaihuapd · 11月2日 15:55

**「“机器可读政府”的工作方式」** “机器可读政府”要求先把法规、许可条件及证明材料转换成 AI 可读取和比对的格式，再由系统辅助官员核查申请。现阶段首个食品进口合规试点已投入运行，但最终审批权仍由官员掌握，因此它是 AI 辅助的政务流程，而非全自动执法。

**「落地影响与边界」** “机器可读政府”在食品进口许可与证书审查中的试点，为进口商申请增加了法规驱动的机器辅助核查环节，但最终决定仍由官员负责；The National 报道称每项评估均可追溯，因此企业不应把模型输出视为自动获批结果。Inception42 的五年协议将向阿联酋政府、企业和学校提供模型，ADNOC 则成为首个使用 OpenAI Frontier 平台的能源公司；不过公开信息尚未给出模型或 API 规格、价格及成效数据，接入方仍需确认技术兼容性和适用的数据治理、网络安全要求。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://neuralbrew.ai/en/articles/2026/11/abu-dhabi-openai-four-agreements-adnoc-mubadala/">Abu Dhabi Signs Four Agreements with OpenAI: ADNOC, Mubadala ...</a></li>
<li><a href="https://aicoder.com/news/news-20261102-openai-abu-dhabi-four-agreements-adnoc-mubadala-inception42-machine-readable-government">OpenAI Signs Four Abu Dhabi Agreements: ADNOC Becomes First ...</a></li>
<li><a href="https://www.aiae.gov.ae/ai-in-abu-dhabi">AI in Abu Dhabi — Abu Dhabi AI - aiae.gov.ae</a></li>
<li><a href="https://www.thenationalnews.com/opinion/editorial/2026/11/03/openai-abu-dhabi-technology-governance/">Why Abu Dhabi&#x27;s AI deals have global implications - The National</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#阿布扎比`, `#AI政府`, `#企业AI`, `#战略合作`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [大模型读改权重并非超人能力](https://seangoedecke.com/llms-are-not-superhuman-at-reading-and-writing-neural-network-weights/) ⭐️ 7.0/10

rss · Sean Goedecke · 11月3日 00:00

**「背景」** Goedecke 评述的论文声称，GPT-6 Astra 能直接读取并修改神经网络权重，从权重判断小型网络受训的游戏，并修补 0.8B Qwen 在长程数学推理中的问题。他质疑这些演示是否代表“超人”能力，因为游戏识别任务结构高度简化，而权重修补也可能只是成熟的模型导向流程。

**「方案」** 游戏网络的输入通道逐一监听 8×8 网格，并以“agent”“moving objects”等含义标注；对第一层权重取 L2 范数即可得到热力图。作者认为，熟悉结构的研究者据此便能从玩家和移动物体的位置辨认至少前三个游戏，Astra 不运行 Python 就能计算范数虽属惊人，却不等于超人级的 AI 研究。Qwen 也并非普遍不会数学：原模型已能答对所有低于 32k token 的题目，真正故障是超过 32k token 后陷入重复循环。Astra 使用 Python 构造四对循环与非循环推理文本，通过残差差异定位相关权重，逐步削弱候选权重并测试，最终找到能阻止循环的补丁；作者将这一过程视为 Heretic abliteration 的权重导向做法，并类比源代码与编译后二进制，认为大模型辅助研究的主要价值仍会来自改进训练，而非直接修改权重。

**「启示」** 论文展示的更像是把既有机器学习技巧自动化并直接作用于权重，而非已经证明的超人自我改进能力。不过，文章对人类研究者对照的判断主要是论证，并未独立复现或深入评估论文结果。

**标签**: `#LLM weight editing`, `#model introspection`, `#abliteration`, `#recursive self-improvement`, `#technical skepticism`

---

<a id="item-tech-blog-2"></a>
### [受众俘获：代理指标如何扭曲真正目标](https://seangoedecke.com/audience-capture/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月3日 00:00

**「背景」** Goedecke 指出，公开写作的环境会奖励点击、评论和互动：聚合算法放大高互动内容，平台也可能用广告或付费鼓励参与度。对他而言，流量只是代理指标，真正想要的是让聪明且知情的人阅读、思考、反馈，并建立“审慎思考者”的声誉。

**「方案」** 他用“点击者”和“读者”区分两种受众：一篇文章可以有一万次浏览，却只让人扫过首句；低曝光的哲学或技术文章虽不热门，却可能吸引会认真阅读、讨论甚至来信的少数人。由此产生的“受众俘获”，是作者为追逐热点和互动不断制造迎合内容，最终失去原本想吸引的审慎读者；例如反复攻击微服务可能让数字上涨，却未必带来真正重视其观点的人。同一逻辑也适用于工程工作：晋升、Jira 工单数和浏览量都可能是代理指标，取决于它们是否服务于作者真正珍视的目标，而非目标本身是否客观高尚。Goedecke 承认有限妥协有时值得，例如为子女教育争取资源，但习惯性“赢代理游戏”可能什么也换不到；因此他更相信自己的品味，以及深度读者邮件或私信中稀薄但具体的反馈，而不把热门等同于成功。

**「启示」** 他的结论是：先辨认自己究竟在玩什么游戏，再用代理指标扩大触及面，而不是让它取代目标；否则，数字越漂亮，真正想建立的关系与作品反而越可能受损。

**标签**: `#proxy metrics`, `#audience capture`, `#engineering culture`, `#incentive design`, `#technical writing`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [Anthropic 招股书披露前三季度营收 332.4 亿美元、净亏损 1040 亿美元](https://www.cnbc.com/2026/11/02/anthropic-ant-s-1-quarter-financials.html) ⭐️ 7.0/10

据 CNBC 援引 Anthropic 周一更新的 IPO 招股书，公司截至 2026 年 9 月 30 日的前三季度营收为 332.4 亿美元，净亏损为 1040 亿美元；公司称亏损主要受可转换债券及衍生负债公允价值变动影响，并不等同于实际经营现金消耗。

telegram · zaihuapd · 11月2日 15:12

**「背景」** Anthropic 在为可能上市而向美国证监会提交的经修订 S-1 招股书中，更新了截至 2026 年 9 月 30 日的前九个月财务数据。此前招股书披露，公司 2025 年净亏损 420 亿美元，并计划未来数年承担 5180 亿美元的云计算、算力及基础设施义务。

**「影响」** Anthropic 约 8954 亿美元的采购及租赁承诺几乎全部投向算力与基础设施，将为芯片、云服务和数据中心供应商锁定巨额需求，而承诺的履行规模将成为 IPO 投资者评估其现金风险的重要依据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/02/anthropic-ant-s-1-quarter-financials.html">Anthropic releases amended IPO prospectus with Q3 financials</a></li>
<li><a href="https://www.cnbc.com/2026/09/28/anthropics-ipo-prospectus-shows-sweeping-ai-vision-surging-costs-reuters.html">Anthropic&#x27;s IPO prospectus shows sweeping AI vision ... - CNBC</a></li>
<li><a href="https://invezz.com/news/2026/11/02/anthropic-revenue-surges-12-fold-in-q3-with-895b-in-purchase-commitments/">Anthropic revenue surges 12 fold in Q3, with $ 895 B in purchase...</a></li>

</ul>
</details>

**标签**: `#Anthropic`, `#corporate financials`, `#AI infrastructure`, `#IPO`

---

<a id="item-finance-news-2"></a>
### [英国拟延长多数永久居留申请等待期](https://www.gov.uk/government/news/home-secretary-unveils-new-rules-for-migrants-settling-in-the-uk) ⭐️ 7.0/10

英国政府已向议会提交永久居留改革提案，拟将多数申请人的等待期由 5 年延长至 10 年，并为高薪者及医生、护士、教师等公共服务岗位人员设置 3 年或 5 年通道；具体实施时间尚未公布。

telegram · zaihuapd · 11月2日 23:50

**「背景」** 英国现行制度通常允许移民连续居住满 5 年后自动申请永久居留；英国内政部此前已就“有条件定居”改革启动公开咨询并征求意见至 2026 年 2 月 12 日，因此本次方案仍处于政策提案阶段，尚未生效。

**「影响」** 主要影响持临时签证在英国工作或生活的申请人及医疗机构：政府拟关闭“长期居留”通道，临时居留满 10 年也不能仅凭合法居留申请永居，而医生、护士和教师可走 5 年通道；该方案目前尚未生效。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gov.uk/government/consultations/earned-settlement">Earned settlement - GOV.UK</a></li>
<li><a href="https://www.gov.uk/government/consultations/earned-settlement/a-fairer-pathway-to-settlement-statement-and-accompanying-consultation-on-earned-settlement-accessible">A Fairer Pathway to Settlement: statement and accompanying ... Home Office consultation template - GOV.UK Briefing Note - City Of Wolverhampton Council do not, we will see a £10 billion pound drain on our public ... Briefing Note - City Of Wolverhampton Council Region/Directorate - eastdunbarton.gov.uk</a></li>
<li><a href="https://assets.publishing.service.gov.uk/media/6ae89fddf4a6b3f59cf37580/FINAL_VERSION_-_Earned_Settlement_-_Consultation_Response.pdf">Government response to settlement consultation</a></li>
<li><a href="https://www.davidsonmorris.com/earned-settlement/">Earned Settlement UK : 2026 ILR Reform Guide</a></li>
<li><a href="https://www.jobbatical.com/blog/uk-earned-settlement-ilr-updates">Earned Settlement UK : ILR New Rules &amp; Latest Update 2026</a></li>

</ul>
</details>

**标签**: `#英国`, `#移民政策`, `#永久居留`, `#劳动力市场`

---

