# Horizon 每日速递 - 2026-11-27

> 从 37 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [英伟达据报暂停东南亚四国 AI 服务器出货](#item-tech-news-1) ⭐️ 8.0/10
2. [面向 AMD GPU 的 llama.cpp 分支瞄准推理加速](#item-tech-news-2) ⭐️ 7.0/10
3. [预印本：从零锥出发代数量子化引力](#item-tech-news-3) ⭐️ 7.0/10
4. [Neuralink 获准开展渐冻症脑机接口关键试验](#item-tech-news-4) ⭐️ 7.0/10

**科技博客**
1. [谁有权判定 AI 写作](#item-tech-blog-1) ⭐️ 5.0/10

**财经新闻**
1. [SpaceX 向儿童投资账户赠送股份，马斯克等额配捐](#item-finance-news-1) ⭐️ 8.0/10
2. [荷兰反对美国限制 ASML 对华销售法案](#item-finance-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [英伟达据报暂停东南亚四国 AI 服务器出货](https://www.ft.com/content/7838a715-07d4-4605-aa60-21f5af2b2370) ⭐️ 8.0/10

据《金融时报》报道，英伟达已要求戴尔、美超微等主要制造伙伴暂停向马来西亚、新加坡、泰国和印度尼西亚发运搭载其芯片的 AI 服务器，相关厂商已通知四国买家订单无法出厂。冻结据称与美国商务部收紧先进芯片出口管制有关；新规要求区域云服务商在 90 天内取得出口许可，并核实客户是否涉及受限制的中国实体。目前尚不清楚这项暂停是临时措施还是会长期实施。

telegram · zaihuapd · 11月26日 07:38

**「此前的转运审查」** 理解此次暂停的背景，是新加坡等东南亚节点因可能成为先进芯片输往中国的中转渠道而受到美国审查。Horizon 11 月 18 日日报曾报道，英伟达在美国调查其新加坡业务是否牵涉对华转运期间停止披露该子公司销售数据；当时披露的 2025 年 1040 亿美元外部收入仅代表新加坡实体的账面归属，不能证明芯片最终流向中国。此次事件则把合规压力具体推进到服务器订单的发运环节，与美国要求区域云服务商取得出口许可并核查客户的新规直接相连。

**「交付与合规影响」** 马来西亚、新加坡、泰国和印度尼西亚的买家将面临搭载英伟达芯片的 AI 服务器订单暂停出厂，恢复交付的时间尚未确定；戴尔、美超微等制造商已通知当地买家订单受阻。受影响的区域云服务商应按美国商务部新规，在 90 天内取得出口许可并核查客户是否涉及受限的中国实体，以避免继续因合规审查而延迟供应。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ft.com/content/dbde7a30-548c-4f9d-a4be-7898a0c24dcf">2026-11-18 — 英伟达停止披露新加坡子公司销售数据</a></li>
<li><a href="https://nypost.com/2026/11/26/business/nvidia-halts-server-shipments-to-4-southeast-asian-countries-report/">Nvidia halts server shipments to 4 Southeast Asian countries: report</a></li>
<li><a href="https://www.trendforce.com/news/2026/11/26/news-nvidia-reportedly-suspends-ai-server-shipments-to-four-southeast-asian-countries-as-u-s-targets-chinese-ai-access/">[News] NVIDIA Reportedly Suspends AI Server Shipments to Four ...</a></li>
<li><a href="https://www.wsj.com/tech/nvidia-tells-partners-to-pause-shipments-to-southeast-asia-5b791cb0">Nvidia Tells Partners to Pause Shipments to Southeast Asia</a></li>
<li><a href="https://www.reuters.com/world/asia-pacific/nvidia-halts-chip-shipments-southeast-asia-ft-reports-2026-11-26/">Nvidia halts server shipments to four Southeast Asian ...</a></li>

</ul>
</details>

**标签**: `#AI accelerators`, `#export controls`, `#NVIDIA`, `#cloud infrastructure`, `#Southeast Asia`

---

<a id="item-tech-news-2"></a>
### [面向 AMD GPU 的 llama.cpp 分支瞄准推理加速](https://devnull.land/amd-specific-llama-cpp) ⭐️ 7.0/10

该 Hacker News 条目介绍了一个面向 AMD GPU 的 llama.cpp 专用分支，目标是在受支持的 AMD 硬件上加速本地大语言模型推理。现有条目未提供分支名称、具体代码改动、GPU 与 ROCm 兼容范围、模型配置或可复现基准，因此只能确认其优化方向，无法据此判断它是否已形成适用于不同 AMD 设备的通用性能提升。

hackernews · julianlam · 11月26日 17:11 · [社区讨论](https://news.ycombinator.com/item?id=50657265)

**「AMD 分叉背景」** llama.cpp 的 AMD 专用分叉通常只针对特定模型或硬件组合，并借助前沿模型辅助开发；相关页面具体推荐 AMD 显卡用户尝试 \`llama.cpp-rdna-boosts\`。不过，现有材料未说明具体代码改动、测试配置或可复现的基准方法，因此其相对上游版本及不同 Radeon 型号的性能仍需验证。

**「对 AMD 本地推理用户的影响」** 对拥有受支持 AMD GPU 的本地 LLM 用户，这一 fork 提供了在 llama.cpp 基线上叠加一组小型优化补丁的路径，可针对 AMD 后端定向调优而无需整体更换推理框架；部署时应按显卡型号及 ROCm 或 Vulkan 版本重新验证。现有社区实测显示，Radeon AI Pro R 9700 运行 Qwen3.8 27B 时，llama.cpp Vulkan 的原始生成速度约为 57.9 tok/s、可见文本约为 29 tok/s，而 vLLM Radiance 在 4 个并发请求下合计约为 55 tok/s；MI25 用户也报告 ROCm 10.x 编译的 llama.cpp 在双卡上运行良好。这些是个案数据，并非该 fork 在所有硬件上的统一加速比；用户还应对 Strata、HaloPFX 和 Hipfire 等其他 AMD 优化实现分别进行基准测试。

**「社区实测与讨论」** 评论者报告了各自环境中的具体结果：一位称基于 Radeon 9700 的 Radiance engine 运行 4-bit Qwen3.8-27B 时，预填充速度为 2400 tok/s、解码速度为 150 tok/s，并可在显存中同时运行 3 路、每路 200k 上下文的代理任务；另一位在 MI100 上使用移植了部分 Nvidia 内核的 vicuna.cpp，称经 Claude 辅助进行数值校验后，Qwen3.8 性能提高至原来的 2—3 倍且运行较稳定。还有评论提到 gfx906 等早期 AMD 数据中心卡凭借 HBM2 带宽形成了持续优化生态，以弥补缺少 tensor core 和原生 bf16 的不足；这些均为个人报告，硬件、量化方式、模型和实现各不相同，不能直接横向比较或视为独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://devnull.land/amd-specific-llama-cpp">AMD - specific fork of llama . cpp | devnull.land</a></li>
<li><a href="https://news.ycombinator.com/item?id=50657265">AMD -specific fork of llama . cpp | Hacker News</a></li>
<li><a href="https://devnull.land/amd-specific-llama-cpp">AMD -specific fork of llama . cpp | devnull.land</a></li>
<li><a href="https://getrigbase.com/builds/r9700-qwen38-27b-vaditaslim/">Radeon AI Pro R 9700 : Qwen3.8 27B on llama . cpp , Ollama and vLLM...</a></li>

</ul>
</details>

**标签**: `#llama.cpp`, `#AMD GPUs`, `#LLM inference`, `#local AI`, `#GPU optimization`

---

<a id="item-tech-news-3"></a>
### [预印本：从零锥出发代数量子化引力](https://arxiv.org/abs/2611.34924) ⭐️ 7.0/10

arXiv:2611.34924 提出一种针对四维洛伦兹时空中真空广义相对论的背景独立代数量子化方案：从一阶引力出发，在体子区域相交的零锥上求解约束，在有限的 G\_N 下获得约化相空间，再将正则泊松括号提升为对易关系，并通过形变约化作用定义可观测量代数。作者还称使用高斯波函数构造量子态，但这是尚未经同行评审确认的预印本主张，现有摘要片段也不足以验证其代数类型、路径积分严格性和背景独立性。

hackernews · hecmmm · 11月26日 05:37 · [社区讨论](https://news.ycombinator.com/item?id=50651863)

**「方法背景」** 这项工作采用正则量子引力路线：先分解一阶广义相对论的哈密顿量与约束，再通过求解约束消去非物理自由度；论文选择四维洛伦兹时空中的相交零锥，在有限 G\_N 下由边界数据构造约化相空间。随后，作者将约化相空间的经典 Poisson 括号提升为对易关系，并以形变后的约化作用量定义可观测代数，同时给出相应的路径积分表示。

**「研究与验证影响」** 对量子引力研究者，这项工作把“不依赖预设背景来构造量子引力振幅”具体化为一套可审查的程序：在四维洛伦兹时空的一阶真空广义相对论中，于相交零锥上求解约束，得到有限 G\_N 的约化相空间，再将其泊松括号提升为可观测量代数并构造高斯波函数。其实际价值取决于该代数能否满足论文提出的公理、振幅条件以及与欧氏表述的等价性，因此目前更适合作为待同行评议的候选框架，而不是已经验证的新量子引力理论。

**「评审与可检验性仍受质疑」** 评论者 kdavis 质疑摘要中似乎出现的 I 型代数是否符合包含引力时预期的 II 型代数，并追问洛伦兹路径积分的严格构造方式，以及在相交零锥上量子化如何与背景独立并存；ibobev 则询问论文是否给出可检验的新预测。物理版块回应称相关讨论被 AI 话题主导，建议等待该领域专家审查论文。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2611.34924">An algebraic quantization of gravity from the null cone</a></li>
<li><a href="https://alphaxiv-scroll.vercel.app/">Swipe through video explainers of the papers trending on alphaXiv...</a></li>
<li><a href="https://arxiv.org/pdf/2611.34924">An algebraic quantization of gravity from the null cone</a></li>
<li><a href="https://arxiv.org/abs/2611.34924">[2611.34924] An algebraic quantization of gravity from the null cone</a></li>
<li><a href="https://alphaxiv-scroll.vercel.app/">Swipe through video explainers of the papers trending on alphaXiv...</a></li>

</ul>
</details>

**标签**: `#quantum gravity`, `#canonical quantization`, `#general relativity`, `#null-cone methods`

---

<a id="item-tech-news-4"></a>
### [Neuralink 获准开展渐冻症脑机接口关键试验](https://www.bloomberg.com/news/articles/2026-11-25/neuralink-gets-clearance-for-brain-implant-trial-in-als-patients?srnd=phx-technology) ⭐️ 7.0/10

据彭博报道，Neuralink 宣布获得 FDA 许可，将在美国启动名为“LINK”的植入式脑机接口关键临床试验，面向渐冻症患者招募，测试将大脑信号转换为计算机控制指令的能力；报道将其称为美国首个获批的此类关键试验。Neuralink 称，设备此前已在全球为超过 30 名瘫痪患者植入，本次试验产生的数据将作为未来申请医疗器械上市许可的重要依据。现有材料未披露试验设计、样本量、主要终点或监管文件，“关键试验”及后续上市路径仍主要来自报道转述，不能等同于已获医疗器械上市批准。

telegram · zaihuapd · 11月26日 07:15

**「LINK 试验的技术与临床背景」** Neuralink 的植入式脑机接口通过读取神经信号并将其转换为动作，用于控制计算机或机械臂；公司官网称，临床试验参与者已经能够用思维执行这些操作。对 Neuralink VOICE 试验的报道还显示，患延眠起病型渐冻症的参与者 Terry 可在几乎无法动嘴时通过脑信号生成语音。由此，LINK 试验把相关技术从早期可行性和安全性验证推进到面向医疗器械上市许可申请的关键临床阶段。

**「实际影响与限制」** 对 Neuralink 而言，获准开展 LINK 试验后，将在美国面向渐冻症患者招募受试者，并生成用于支持未来医疗器械上市申请的数据；此次许可仅允许开展临床试验，并不等于产品已获准上市。潜在受试者和临床机构应以正式招募公告及入组标准为准，因为现有报道尚未披露样本量、主要终点、风险或对照安排。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://neuralink.com/">Neuralink — Pioneering Brain Computer Interfaces</a></li>
<li><a href="https://pasqualepillitteri.it/zh/news/18798/neuralink-jianbingzheng-huanzhe-wo-ai-ni">Neuralink 让 渐 冻 症 患者仅凭思维说出我爱你 | Pasquale Pillitteri</a></li>
<li><a href="https://imr.sjtu.edu.cn/upload/file/20230710/20230710143542.pdf">ANVISA</a></li>

</ul>
</details>

**标签**: `#脑机接口`, `#Neuralink`, `#FDA`, `#临床试验`, `#渐冻症`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [谁有权判定 AI 写作](https://seangoedecke.com/who-gets-to-decide-if-something-is-written-by-ai/) ⭐️ 5.0/10

rss · Sean Goedecke · 11月27日 00:00

**「背景」** 围绕作品是否由 AI 生成的纠纷，表面是检测准确性，实质是裁判权归属：谁能决定文学奖、学生是否通过，以及谁可参与公共讨论。反 AI 者若让科技检测器或社群共识掌握裁决权，可能反而把制度权力交给技术部门。

**「方案」** 作者把 Pangram 视为“工具化裁决”：反对 AI 者可能因不信任科技资本、算法化考核和效率优先流程而拒绝它，哪怕它也是 AI 工具。他支持该工具，因为在他看来，替代方案只剩文学奖委员会或社群自行认定；而非 AI 使用者并不擅长辨伪，既会漏掉 AI 痕迹，也会把冗长、礼貌误判为 AI。普通调查还受撒谎、事后生成草稿和缺少可行加密认证影响；作者也认为 C2PA 不适合此任务。因此，他主张若担心科技公司监控制裁，应推动开源方案或政府自建公共检测平台，而非让社群自我执法。但其可靠性判断主要靠论证：文中仅提到 Pangram 及第三方测试在同一数据集上存在假阳性与假阴性，没有给出独立误差率或对抗性失效分析。

**「启示」** 作者的核心结论是：AI 写作争议不只是检测器的技术选择，更是裁决权的制度分配；在他看来，质疑检测工具仍比让缺乏经验的社群决定一篇作品是否由 AI 写成更可取。

**标签**: `#AI detection`, `#AI governance`, `#content provenance`, `#institutional power`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [SpaceX 向儿童投资账户赠送股份，马斯克等额配捐](https://ir.spacex.com/updates/releases-details/2026/SpaceX-to-Invest-in-the-Next-Generation-of-Americans-2026-r_LYQ5cH94/default.aspx) ⭐️ 8.0/10

SpaceX 宣布向每个当前有效的 Trump Account（面向美国儿童的税收优惠投资账户）赠送 1 股新发行的 A 类普通股；马斯克称将等额配捐，即每个孩子共获 2 股。公司总裁兼 COO 格温·肖特韦尔另称个人捐赠超过 200 万股，但账户数量、股份估值和总成本均未披露，暂无法判断活动总规模。

telegram · zaihuapd · 11月26日 08:31

**「背景」** Trump Account 是美国面向儿童的税收优惠投资账户，符合条件的现有账户持有人预计将于 2026 年 12 月起收到捐赠股份。

**「影响」** 美国儿童的 Trump Account 将各持有两股 SpaceX A 类普通股（公司新发一股、马斯克等额配捐），让相关家庭获得该公司的直接股权敞口；新增股数可能稀释现有股东权益，但有效账户总数未披露，无法量化稀释幅度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ir.spacex.com/updates/releases-details/2026/SpaceX-to-Invest-in-the-Next-Generation-of-Americans-2026-r_LYQ5cH94/default.aspx">SpaceX to Invest in the Next Generation of Americans</a></li>
<li><a href="https://www.cnbc.com/2026/11/02/trump-accounts-spacex-shares-shotwell.html">Trump Accounts to get SpaceX shares from Shotwell in December</a></li>
<li><a href="https://www.cnbc.com/2026/11/25/spacex-musk-trump-account-stock.html">SpaceX, Elon Musk to donate one share each to active Trump ...</a></li>
<li><a href="https://finance.yahoo.com/markets/stocks/articles/spacex-elon-musk-share-every-123835466.html?fr=sycsrp_catchall">SpaceX and Elon Musk Will Each Give a Share to Every Active ...</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#Trump Accounts`, `#股权捐赠`, `#儿童储蓄`

---

<a id="item-finance-news-2"></a>
### [荷兰反对美国限制 ASML 对华销售法案](https://www.bloomberg.com/news/articles/2026-11-26/netherlands-plans-to-fight-rollout-of-proposed-us-curbs-on-asml) ⭐️ 8.0/10

荷兰外贸与发展合作大臣斯约 erd·斯约尔兹马 11 月 26 日表示，荷兰反对美国拟议的《MATCH 法案》要求荷兰、日本等盟友收紧对华半导体设备出口管制，否则美国将单方面限制相关设备销售。荷兰正与欧盟委员会协调，并联合德国和法国游说将该法案从美国年度国防政策法案中剔除；中国约占阿斯麦 2026 年销售额的 20%，外界预计美国国会 12 月中旬表决时该法案通过可能性较大。

telegram · zaihuapd · 11月26日 14:56

**「背景」** MATCH Act 于 2026 年 4 月在美国国会提出，拟要求荷兰等关键盟友在 150 天内收紧对华先进芯片制造设备及服务的出口管制；该法案仍待表决，荷兰正推动将其从美国年度国防法案中剔除。

**「潜在影响」** 若 MATCH Act 获通过并实施，ASML 对华销售及相关服务将面临自 2024 年以来最重大的出口管制变化，其约占今年销售额 20%的中国业务可能承压，但法案最终能否通过仍不确定。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-26/netherlands-plans-to-fight-rollout-of-proposed-us-curbs-on-asml">Netherlands to Fight Rollout of Proposed US Curbs on ASML</a></li>
<li><a href="https://www.thedefensenews.com/US-Pushes-Bill-to-Compel-Netherlands-to-Halt-Remaining-ASML-Machine-Sales-and-Service-to-China/">US Pushes Bill to Compel Netherlands to Halt Remaining ASML ...</a></li>
<li><a href="https://finance.yahoo.com/markets/stocks/articles/match-act-puts-asml-china-170806376.html">MATCH Act Puts ASML China Revenue And Service Exposure Under...</a></li>

</ul>
</details>

**标签**: `#ASML`, `#semiconductor export controls`, `#China`, `#Netherlands`, `#U.S. policy`

---

