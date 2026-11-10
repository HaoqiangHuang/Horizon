---
layout: default
title: "Horizon Summary: 2026-11-10 (ZH)"
date: 2026-11-10
lang: zh
---

> 从 44 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [Anthropic 发布 Claude Fable 5.2 与 Mythos 5.2](#item-tech-news-1) ⭐️ 8.0/10
2. [谷歌发布 TPU 8tx 与 8i Max](#item-tech-news-2) ⭐️ 8.0/10
3. [E-means 用十分之一训练轮数挑战 k-means](#item-tech-news-3) ⭐️ 7.0/10
4. [Google Gemini 被指会将 Drive 文件与邮件交给人工标注](#item-tech-news-4) ⭐️ 7.0/10
5. [Watched Earth：查询近七天卫星过境与影像](#item-tech-news-5) ⭐️ 7.0/10
6. [Meta 发布轻量级 Muse Ember 模型](#item-tech-news-6) ⭐️ 7.0/10
7. [LingBot-Touch 用潜变量预测改进触觉预训练](#item-tech-news-7) ⭐️ 7.0/10
8. [Seedream 5.5 发布，支持百轮连续编辑](#item-tech-news-8) ⭐️ 7.0/10
9. [ChatGPT 9 月访问量据报创 613.5 亿次新高](#item-tech-news-9) ⭐️ 7.0/10
10. [欧盟数字公平法案草案限制成瘾性设计](#item-tech-news-10) ⭐️ 7.0/10

**财经新闻**
1. [前三季度中国新能源乘用车出口增长 138.8%](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Anthropic 发布 Claude Fable 5.2 与 Mythos 5.2](https://www.anthropic.com/claude-fable-and-mythos-5-2) ⭐️ 8.0/10

Anthropic 宣布 Claude Fable 5.2 与 Mythos 5.2 两个模型版本，主要面向需要评估编码能力、模型档位和推理投入的开发者与团队。现有材料未附官方发布正文，因此无法核实 Mythos 5.2 的具体定位、两版相对前代的改动、价格、可用渠道或官方基准结果。讨论焦点集中在 Fable 5.2 的实际编码表现、不同档位之间的平衡，以及 Anthropic 的对比模型选择和 effort 曲线设计。

hackernews · lairv · 11月9日 18:01 · [社区讨论](https://news.ycombinator.com/item?id=50429068)

**「评测基线与竞品背景」** Anthropic 的评测同时列出 Fable 5.2、Fable 5.1 和 Opus 5.5；除非另有说明，结果启用了安全防护并采用每个模型可用的最高 effort（推理强度），因此并非统一固定推理预算下的横向比较。Horizon 10 月 29 日的日报还记录了 Google 发布主攻网络安全的 Gemini 4 Carbon，其初期仅向部分防御者和可信伙伴开放，这一有限可用状态也是理解当前相关基准对比的背景。

**「实际影响」** 面向高难度编码、推理和视觉任务的开发团队，应将 Claude Fable 5.2 纳入模型选型测试，并重新评估依赖 Opus 5.5 或 Fable 5.1 的现有流程：Anthropic 称 5.2 在其评估的几乎所有能力上超过 Opus 5.5，OpenRouter 则列出其相对 Fable 5.1 在编码、推理和视觉方面的提升。不过这些信息主要来自厂商及平台基准，最终选型仍应以自身工作负载实测为准，不宜假定其在所有任务上均更优。

**「社区反馈」** 一名早期测试者称，Fable 5.2 处理了一个 60 万行 Fortran 代码库，将某项计算材料科学工作提速 36 倍，相关工作可在两天内完成；另一名评论者转述称，1,000 个 Fable 5.2 智能体在 30 小时内形式化了费马大定理，而依赖专用编排工具和人类指导的未发布研究版耗时 11 天。这些均为评论者报告或转述，并非独立验证；其他用户认为 Anthropic 的模型档位较此前更平衡、Fable 5.2 与 Opus 5.5 在普通任务中仍难区分，同时质疑 Fable xHigh 对 Carbon Med 的对比、Carbon 的 effort-intel 曲线，以及 robodojo 测试为何改用 Argon 而非 Carbon。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/claude-fable-and-mythos-5-2">Introducing Claude Fable 5 . 2 and Claude Mythos 5 . 2 \ Anthropic</a></li>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-carbon/">2026-10-29 — Google 发布 Gemini 4 Carbon，先限网络安全伙伴测试</a></li>
<li><a href="https://www.anthropic.com/claude-fable-and-mythos-5-2">Introducing Claude Fable 5 . 2 and Claude Mythos 5 . 2 \ Anthropic</a></li>
<li><a href="https://openrouter.ai/anthropic/claude-fable-5.2">Claude Fable 5 . 2 - API Pricing &amp; Benchmarks | OpenRouter</a></li>

</ul>
</details>

**标签**: `#large language models`, `#Anthropic`, `#AI model releases`, `#code generation`, `#model evaluation`

---

<a id="item-tech-news-2"></a>
### [谷歌发布 TPU 8tx 与 8i Max](https://blog.google/innovation-and-ai/infrastructure-and-cloud/global-network/tpu-8i-max-and-8tx/) ⭐️ 8.0/10

谷歌宣布推出 TPU 8tx 和 TPU 8i Max 两款面向代理式 AI 工作负载的新张量处理单元。TPU 8tx 面向政府机构及受严格监管行业，用于处理机密数据，并将与 AMD 芯片协同；TPU 8i Max 面向超长上下文应用，将两颗 TPU 集成在同一封装中，旨在提供更强算力和更大内存。报道还称苹果、Meta、甲骨文和 Anthropic 已成为 TPU 客户，但现有材料未提供这两款新 TPU 的规格、价格、每 token 功耗或成本，以及与 NVIDIA 产品的可比数据。

hackernews · \_benx\_ · 11月9日 21:56 · [社区讨论](https://news.ycombinator.com/item?id=50432831)

**「TPU 产品线的前代与分工」** 作为理解此次发布的背景，Google 第八代 TPU 并非只推出一款通用芯片：Google Cloud 博客称，8tx 和 8i Max 使这一代产品组合扩展至年内四款新 TPU 系统，其中 8tx 沿用现有芯片基础并结合 AMD EPYC Turin 主机支持机密计算，8i Max 则在同一封装中组合两颗 8i 芯片，以应对超长上下文工作负载。Horizon 在 11 月 6 日的日报中还记录了 TPUv7（Ironwood）面向外部 AI 基础设施客户公布 AgentX 等推理基准的情况；此次变化是进一步扩展到安全计算和大上下文等专用系统，而非仅提高单一芯片的规格。

**「部署选型与采购风险」** 对受监管机构而言，8tx 提供面向机密数据安全推理的专用选项，并被描述为可与 AMD 芯片协同工作；对超长上下文应用，8i Max 通过在同一封装中集成两颗 TPU，以获得更高算力和更大内存。现有公开材料未提供售价、每 token 成本或功耗及明确供货条件，因此团队在替代或扩充 NVIDIA GPU 前，仍需向 Google 核实可用性，并基于自身工作负载测试成本与兼容性。

**「社区讨论」** 讨论主要聚焦于产品可获得性和性价比：评论者追问谷歌为何不直接销售这些 TPU，并要求提供各型号的 watt/token、$/token 数据及与 NVIDIA 产品的对比；另有用户称 Colab 可用的最强型号仍为 v6e-1，难以支撑严肃工作。一位评论者还推荐了 TPUSync 和 Strata 等开源项目，以说明相关模型目前采用的 TPU 工作方式。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cloud.google.com/blog/topics/ai-infrastructure/tpu-8tx-and-tpu-8i-max">Introducing TPU 8tx and TPU 8i Max | Google Cloud Blog</a></li>
<li><a href="https://www.servethehome.com/google-tpu-8tx-8i-max-amd-epyc-turin/">Google TPU 8tx Pairs AMD EPYC Turin Hosts with Confidential ...</a></li>
<li><a href="https://newsletter.semianalysis.com/p/tpu-strikes-the-king">2026-11-06 — Google TPUv7 以 AgentX 基准拓展外部推理</a></li>
<li><a href="https://blog.google/innovation-and-ai/infrastructure-and-cloud/global-network/tpu-8i-max-and-8tx/">Introducing TPU 8 tx and TPU 8 i Max</a></li>

</ul>
</details>

**标签**: `#Google TPU`, `#AI accelerators`, `#AI infrastructure`, `#agentic AI`, `#open-source tooling`

---

<a id="item-tech-news-3"></a>
### [E-means 用十分之一训练轮数挑战 k-means](https://e-means.github.io/) ⭐️ 7.0/10

E-means 项目提出了一种新的聚类方法，声称只需 k-means 约十分之一的训练轮数，就能达到或超过其聚类质量，目标是降低大规模聚类的迭代成本。该性能目前主要是项目方主张，现有材料缺少统一基准和独立复现；社区实测显示收益显著但依赖场景：GPU 上的 IVF 索引构建获得了 146 倍加速，现有索引批量重建加速 2.5 倍，而一个球面网格松弛用例并未发现改进。因此，E-means 更像是 Lloyd/k-means 的潜在快速替代方案，而非已被全面验证的替代品。

hackernews · porridgeraisin · 11月9日 18:45 · [社区讨论](https://news.ycombinator.com/item?id=50429734)

**「背景」** 理解这一结果需要区分训练轮数与实际耗时：论文将 e-means 定义为一种带小批量更新的指数移动平均优化方法，并研究衰减率和批量大小对最终性能的影响。这里的 epoch 指遍历训练向量的一次，论文报告 e-means 在 DINO10B 数据集上用 2 个 epoch 达到了 Faiss-GPU 和 Flash-KMeans 在 25 个 epoch 时的损失。

**「实际收益取决于工作负载」** 对批量、GPU 密集型聚类，E-means 可能显著缩短重建时间：一名开发者称将其用于 IVF 索引后获得 146 倍 GPU 加速，Antfly 的整库重建也快了 2.5 倍；但该测试中的增量插入时间几乎未变，网格松弛用例则没有优势。GPU 收益还取决于内存访问路径，因此团队应先用自己的数据和目标指标做基准测试，再决定是否替换 k-means，不能直接根据“十分之一训练轮数”推断端到端收益。

**「社区实测」** real\_faxenoff 称，将方法适配到 code-daemon 的 IVF 索引后，在 GPU 上获得了 146 倍加速；kingcauchy 则报告，现有索引批量重建（例如分片拆分）快了 2.5 倍，但整体插入耗时变化不大，因为增量聚类只占 CPU 时间的一小部分。jlhawn 在二十面体等面积球面网格的“松弛”任务中实测后认为 E-means 不如 Lloyd 算法；shiandow 尝试从期望最大化角度理解其更新规则，wood\_spirit 则希望它能被纳入 SciPy，这些属于用户观点或功能建议。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/html/2611.09501v1">e-means: outperforming k-means (in one-tenth the epochs)</a></li>
<li><a href="https://openreview.net/forum?id=pt14gnV3dl">$e$-means : Outperforming k-means (in one-tenth the epochs)</a></li>
<li><a href="https://dzen.ru/a/avKUjdfnyBjy_xLl">e - means обошёл результат 25 проходов k - means за три | Дзен</a></li>

</ul>
</details>

**标签**: `#machine learning`, `#clustering`, `#k-means`, `#GPU acceleration`, `#vector indexing`

---

<a id="item-tech-news-4"></a>
### [Google Gemini 被指会将 Drive 文件与邮件交给人工标注](https://github.com/thisisme6598/gemini_files/) ⭐️ 7.0/10

一项发布在 GitHub 上的社区调查指控称，启用 Connected Apps 的 Google Gemini 消费者版，可能把通过 Google Drive 和 Gmail 工具读取的个人文件与邮件内容交给人工标注员。现有证据主要来自社区研究，材料未交代触发条件、涉及的数据范围、标注频率，以及这些数据是否会被用于训练或改进 Gemini。评论者称 Workspace Gemini 遵循不同且据称不受人工审查的规则，因此该指控目前只应适用于消费者版 Gemini，不能外推至全部 Google AI 产品。

hackernews · gf74918 · 11月9日 18:24 · [社区讨论](https://news.ycombinator.com/item?id=50429426)

**「背景：Connected Apps 与人工审阅承诺」** 要理解这项调查，关键是 Gemini 的 Connected Apps 授权机制：启用后，消费版 Gemini 可从 Gmail、Google Drive 等连接的数据源获取信息，用于聊天回答或自动化任务；Google 的帮助文档也提醒，邮件引用可能包含较旧信息，用户应核对回答所列来源（tool-1-2、tool-2-1、tool-2-2）。据该 GitHub 调查称，争议在于 Google 似乎从 2023 年“个人 Gmail、Docs 和 Drive 内容不会被人工审阅”的承诺，转向让消费版 Gemini 的连接数据进入可能接受人工审阅的流程；这一指控目前不能直接外推至 Workspace Gemini（tool-1-1、tool-1-2）。

**「实际影响」** 在消费者版 Gemini 中启用 Connected Apps 并授权 Gmail 或 Google Drive 的用户，相关邮件、文档和文件内容可能进入人工审核流程；Google 的说明显示，审核人员可接触摘要、摘录、生成媒体和系统推断，而非完整原文件。因此，个人和团队应检查并撤销不必要的 Gmail、Drive 连接，避免通过这些连接提交机密或敏感资料；这项变化针对消费者版 Connected Apps，不能据此推断所有 Workspace 数据都采用相同处理方式。

**「讨论聚焦实际范围与数据用途」** 一些评论者把这项指控与自身经历联系起来，例如怀疑 Gemini 曾异常准确地回应私人邮件内容；这属于个人推测，而非已证实的因果关系。讨论主要区分了消费者版 Connected Apps 与 Workspace 版的不同审查机制，同时担忧被标注的数据可能被用于模型训练，但现有材料没有提供可核实的 Google 确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/google-gemini-routes-personal-drive-gmail-to-human-reviewers">Google Gemini Routes Personal Drive, Gmail to Human Reviewers</a></li>
<li><a href="https://letsdatascience.com/news/github-repo-alleges-gemini-sends-connected-drive-and-email-d-07306ae3">GitHub repo alleges Gemini sends connected Drive and email ...</a></li>
<li><a href="https://support.google.com/gemini/answer/14959807?hl=en-UM&amp;co=GENIE.Platform=Desktop">Use apps connected to Gemini with a work or school Google Account...</a></li>
<li><a href="https://support.google.com/gemini/answer/17094507?hl=en-BZ&amp;co=GENIE.Platform=Android">Manage your tasks and workflows in Gemini Apps - Android phone...</a></li>
<li><a href="https://daily.dev/posts/google-gemini-routes-personal-drive-files-and-emails-to-human-annotators-1yiwwc2e8">Google Gemini routes personal Drive files and emails to...</a></li>
<li><a href="https://aiweekly.co/alerts/google-gemini-routes-personal-drive-gmail-to-human-reviewers">Google Gemini Routes Personal Drive, Gmail to Human Reviewers</a></li>
<li><a href="https://support.google.com/gemini/answer/13594961?hl=en">Gemini Apps Privacy Hub - Google Help Google Reversed Its Gemini Privacy Commitment. Enterprise… Google Gemini Warning: Don’t Share Confidential Information Gemini Apps Privacy Hub - Gemini Apps Help - Google Help Generative AI in Google Workspace Privacy Hub</a></li>

</ul>
</details>

**标签**: `#Google Gemini`, `#AI privacy`, `#human annotation`, `#Gmail`, `#Google Drive`

---

<a id="item-tech-news-5"></a>
### [Watched Earth：查询近七天卫星过境与影像](https://www.watched.earth/) ⭐️ 7.0/10

开源项目 Watched Earth 允许用户输入任意地点，查找过去 7 天内从该地上空经过的卫星，并在存在真实影像时展示对应的 Sentinel-2、Landsat 或 NASA 图像；项目不会保存用户位置。作者称，工具在浏览器中基于 CelesTrak 星历目录使用 SGP4，约半秒即可完成过境搜索，同时在 GPU 上绘制约 1.7 万个在轨对象，并逐帧求解开普勒方程。作者还称，其过境算法针对极区、反经线和狭小扫描带与暴力计算结果对比时没有遗漏，并发现 Sentinel-2 影像时间戳有时会比卫星实际过境时间早或晚 5 至 10 分钟。项目已开放 GitHub 源码，并正在征集更多影像数据源的建议。

hackernews · a585gupt · 11月9日 17:51 · [社区讨论](https://news.ycombinator.com/item?id=50428907)

**「卫星过境与影像匹配」** 判断一个地点是否真的被卫星“拍到”，需要区分轨道过境与实际成像：前者通过 SGP4 传播 CelesTrak 目录中的轨道数据，后者则要检索 Sentinel-2、Landsat 和 NASA 影像，并将照片与对应过境事件匹配。项目文档还说明会检查目标地点是否被云层遮挡；作者称 Sentinel-2 的成像时间常比实际过境时间相差 5 至 10 分钟，因此影像时间匹配是得出结果前的关键步骤。

**「实际影响」** 用户输入具体地点后，可筛出过去 7 天内经过其上空的卫星，并查看对应的 Sentinel-2、Landsat 或 NASA 真实影像；系统仅在确有影像时标为“已拍摄”，不会把单纯过境误作可用观测结果。这为遥感影像检索和徒步行程规划提供了更直接的浏览器入口。

**「社区讨论」** HN 用户 adonovan 特别肯定了轨道渲染、相机地面轨迹、过境时间序列和多源数据整合，wnissen 则称该工具比 Copernicus 更易用，并认为它适合规划背包旅行。也有评论者将其高度评价为“风格与实质的最佳结合”，但这些属于用户体验和主观评价，不能独立验证其性能声明。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/dev-Armaan/satellites">GitHub - dev-Armaan/satellites</a></li>

</ul>
</details>

**标签**: `#satellite tracking`, `#orbital mechanics`, `#geospatial imagery`, `#GPU visualization`, `#open source`

---

<a id="item-tech-news-6"></a>
### [Meta 发布轻量级 Muse Ember 模型](https://research.meta.ai/blog/muse-ember) ⭐️ 7.0/10

Meta 发布 Muse Ember，并将其称为 Muse 系列中体积最小、效率最高的模型；该模型面向复杂推理和智能体任务，提供 100 万 Token 上下文窗口，可处理文本、图像、音频和视频，并支持工具调用、跨应用工作流与自动修复代码。Muse Ember 提供 minimal、low、medium、high、xhigh 和 max 六档推理强度；Meta 称，其在 Artificial Analysis 智能指数上的表现可比 Claude Haiku 5.5，单任务成本约为后者的三分之一，并在多项测试中超过 GPT-6 Luna。该模型目前通过 Meta Model API 提供，输入和输出价格分别为每百万 Token 0.10 美元和 0.50 美元。

hackernews · dvaplima · 11月9日 17:58 · [社区讨论](https://news.ycombinator.com/item?id=50429024)

**「Muse 系列的演进背景」** Muse 的这次发布可放在同一系列此前的评测背景中理解：11 月 2 日的 Horizon 日报提到，SemiAnalysis 的 GDPx 评测将 Muse Wonder Full 评为当时可用模型中网络安全能力最佳者，但由于评测方法和完整结果披露有限，这只是评测方的判断。Ember 此次扩展了 Muse 系列中更小、更低成本的定位，并已通过 Meta Model API 提供；不过当前材料没有披露参数量或本地部署要求，因此“最小”首先应理解为 Meta 的产品定位，而非硬件需求结论。

**「接入成本与部署限制」** 开发团队现在可通过 Meta Model API 接入 Muse Ember，按每百万输入 Token 0.10 美元、输出 0.50 美元付费，并利用其 100 万 Token 上下文、多模态输入和工具调用能力处理智能体任务；成本敏感型团队可据此与现有模型进行工作负载成本对比。Artificial Analysis 已将 Muse Ember（Max）纳入 Intelligence Index v5.0.1，选型时应按该明确版本并结合自有样本复测；当前公开路径是托管 API，需要自托管或可审计权重的项目应另行确认开放权重安排。

**「评论者质疑实际效用与权重开放」** Simon Willison 将六档推理强度与 SVG 输出质量对比后认为，更多推理 token 这一次没有明显改善结果；另有评论指出，Muse 的最佳外部成绩并非来自 Meta 自有智能体测试框架，而是在 mini-swe-agent 上取得，因此评测环境值得区分。djacksondev 认为 Muse 系列存在“基准成绩突出、实际用途有限”的情况，Retro\_Dev 则称仍未找到开放权重。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://newsletter.semianalysis.com/p/gdpx-measuring-frontier-model-capabilities">2026-11-02 — GDPx 聚焦高价值领域的前沿模型评测</a></li>
<li><a href="https://artificialanalysis.ai/models/muse-ember">Muse Ember (max) - Intelligence , Performance ... | Artificial Analysis</a></li>
<li><a href="https://artificialanalysis.ai/models/releases/muse-ember">Muse Ember Models - Intelligence , Performance ... | Artificial Analysis</a></li>

</ul>
</details>

**标签**: `#language models`, `#model efficiency`, `#reasoning effort`, `#benchmark evaluation`, `#open weights`

---

<a id="item-tech-news-7"></a>
### [LingBot-Touch 用潜变量预测改进触觉预训练](https://www.reddit.com/r/MachineLearning/comments/1xs05uo/latent_prediction_beats_reconstruction_for/) ⭐️ 7.0/10

Robbyant 的新论文提出 LingBot-Touch：以 JEPA 式掩码潜变量预测学习触觉表征，而不是重建原始像素或信号，推理代码和模型检查点均已公开。在相同数据、同规模对比中，触觉到视频 top-5 recall 在 1K 小时分别为 32.1%（JEPA）、5.6%（MAE）和 4.4%（VAE）；4K 小时时 JEPA 达到 49.3%，而 MAE 仍低于 9%、VAE 降至 3.1%。作者认为，稀疏触觉信号中的大量近零背景会让重建损失容易退化为“学会什么都不学”。模型将磁性、压阻和视触觉传感器统一到指尖标准坐标并输入共享 Transformer，以 5D RoPE 编码时间、手指和三维位置；掩码率在前 300 步从 40% 升至 80%，以免稀疏信号中的全部接触像元被遮住并引发梯度爆炸。冻结编码器在 26 个真实机器人任务、4 种策略的 104 个任务—策略组合中有 89 个取得最高分；对预训练未见的磁性手，论文报告 LingBot-VLA 指标从 57.21 提升至 75.04。

reddit · r/MachineLearning · /u/Zealousideal-War7154 · 11月9日 18:52

**「潜空间预测与信号重建的区别」** 理解这一结果的关键是区分两类自监督目标：MAE、VAE 重建要求模型恢复像素或原始传感信号，而 JEPA 式方法改为根据可见上下文预测被遮挡区域的潜表征。触觉片段通常含有大量近零背景，重建损失可能在没有学到有效接触信息时继续下降；Robbyant 的公开实现因此采用模态专用分词器和共享 Transformer，统一处理磁性、压阻式与视触觉信号。

**「触觉预训练目标的影响」** 对机器人触觉预训练开发者，论文报告称，在相同数据和模型规模下，JEPA 式掩码潜变量预测比 MAE、VAE 重构更能学到与接触相关的表示：1K 小时训练的触觉到视频 Top-5 召回率分别为 32.1%、5.6% 和 4.4%，冻结 LingBot-Touch 编码器还在 104 个策略—任务组合中的 89 个取得最高分。开发者可用已公开的推理代码和检查点评估这一方案，但应先在目标传感器与任务上验证，因为现有证据限于论文测试的三类触觉传感器和 26 项真实机器人任务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Robbyant/lingbot-touch">GitHub - Robbyant/lingbot-touch: Learning Heterogeneous ...</a></li>
<li><a href="https://technology.robbyant.com/lingbot-touch">LingBot-Touch Tactile Foundation Model - Robbyant</a></li>

</ul>
</details>

**标签**: `#tactile-sensing`, `#self-supervised-learning`, `#JEPA`, `#dexterous-manipulation`, `#robotics`

---

<a id="item-tech-news-8"></a>
### [Seedream 5.5 发布，支持百轮连续编辑](https://seed.bytedance.com/zh/blog/%E7%94%9F%E6%88%90%E6%9B%B4%E7%9C%9F%E5%AE%9E-%E7%99%BE%E8%BD%AE%E7%BC%96%E8%BE%91%E6%9B%B4%E7%A8%B3%E5%AE%9A-seedream-5-5-%E5%8F%91%E5%B8%83) ⭐️ 7.0/10

字节跳动发布图像创作模型 Seedream 5.5，支持对同一作品进行最多 100 轮连续编辑，并可原生生成带透明通道的素材。字节称，该版本提升了图像真实感和文字渲染能力，在影视、办公场景评测中的可用率达到上一版本的两倍以上；这一性能结论来自厂商自述，尚无独立评测或具体基准数据。模型正陆续上线即梦、豆包、豆包工作和火山方舟，具体可用范围以各平台后续开放情况为准。

telegram · zaihuapd · 11月9日 08:34

**「连续编辑与评测指标」** “百轮连续编辑”是指在同一作品上反复施加修改指令，而不是每轮从零生成；“原生透明通道”则意味着输出图像自带透明度信息，可直接用于后续合成。字节以“影视、办公场景可用率”衡量相较上一版本的改进，但材料未披露该指标的样本、口径或基准数字，因此其“提升至两倍以上”的说法不能视为独立评测结论。

**「实际影响与采用注意」** 对图像创作者和开发团队而言，Seedream 5.5 的直接工作流变化是：同一作品最多可连续编辑 100 轮，并能原生生成带透明通道的素材，从而把反复改稿和后续合成纳入同一创作流程；该能力正陆续上线即梦、豆包、豆包工作和火山方舟，但并非所有用户已立即可用。实际采用时，团队应在各平台开放后重点验证多轮编辑中的一致性、文字渲染和透明边缘，因为字节所称“影视、办公场景可用率达到上一版本两倍以上”仍属厂商评测，现有第三方测评页面仅提供内容标题、未给出可复现基准，不宜据此认定质量已普遍提升。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=X3tciasY2DY">即 梦 Seedream 5 5 测 评 ！ 鹈鹕竟然对了！#ai - YouTube</a></li>

</ul>
</details>

**标签**: `#生成式AI`, `#图像生成`, `#Seedream 5.5`, `#多轮编辑`, `#字节跳动`

---

<a id="item-tech-news-9"></a>
### [ChatGPT 9 月访问量据报创 613.5 亿次新高](https://www.businessinsider.com/chatgpt-growth-rebounds-openai-rivals-ai-market-share-2026-11) ⭐️ 7.0/10

据 Business Insider 转述 Graphite 数据，ChatGPT 在全球主要 AI 聊天机器人流量中的占比超过 81%，单个竞争对手均不足 10%。ChatGPT 9 月月度访问量环比增长近 20%，达到创纪录的 613.5 亿次；此前在 2025 年上半年快速增长后曾停滞 7 个月，随后恢复增长。该报道未提供 Graphite 的统计口径、地区拆分或原始数据链接，且仅为二手转述，因此相关市场份额与访问量数字尚缺乏独立核验。

telegram · zaihuapd · 11月9日 14:32

**「此前的流量份额基线」** 本次“恢复增长”的前史是，ChatGPT 在 2025 年上半年快速增长后曾连续七个月停滞。较早的第三方估算显示，2025 年 8 月其全球 AI 聊天机器人流量份额为 80.92%；另一份月度数据则在 3 月记录到 87% 的份额和 477 亿次访问。由于报道未说明这些数据与本次 Graphite 数据是否采用相同口径，它们只能作为趋势参照，不能用来精确计算份额变化。

**「优先验证 ChatGPT 渠道，但不要替代搜索渠道」** 对需要选择 AI 聊天入口的产品与增长团队，ChatGPT 已是覆盖最大的单一聊天机器人网页渠道：其流量占比超过 81%，而任一竞争对手均未达到 10%，因此面向终端用户的首轮功能测试和触达试点应优先覆盖 ChatGPT。作为量级参照，2025 年 3 月的较早对比显示，全部聊天机器人的访问量仍略低于 Bing，因此这并不意味着 ChatGPT 已能取代搜索渠道；网页访问份额也不能直接外推为 API 调用量或付费市场份额，鉴于 Graphite 未披露完整统计口径，采购或容量规划前仍应复核原始数据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wccftech.com/google-attracts-1-6-trillion-visitors-or-34x-compared-to-chatgpt-as-it-dominates-search-engine-battle/">Google Attracts 1.6 Trillion Visitors Or 34x Compared To ChatGPT As...</a></li>
<li><a href="https://thetechmusk.com/chatgpt-captures-more-than-80-of-global-ai-chatbot-market/">ChatGPT Captures More Than 80% of Global AI Chatbot Market! | TTM</a></li>
<li><a href="https://wccftech.com/google-attracts-1-6-trillion-visitors-or-34x-compared-to-chatgpt-as-it-dominates-search-engine-battle/">Google Attracts 1.6 Trillion Visitors Or 34x Compared To ChatGPT As...</a></li>

</ul>
</details>

**标签**: `#ChatGPT`, `#AI聊天机器人`, `#市场占有率`, `#访问量增长`, `#OpenAI`

---

<a id="item-tech-news-10"></a>
### [欧盟数字公平法案草案限制成瘾性设计](https://www.mlex.com/mlex/articles/2546584/digital-businesses-face-addictive-design-controls-under-draft-eu-consumer-law) ⭐️ 7.0/10

一份泄露的欧盟《数字公平法案》草案拟要求数字企业允许用户关闭自动播放、连续使用奖励等可能诱导过度使用的功能，并为在线订阅提供取消按钮、续费提醒和人工客服，在免费试用转为付费前取得明确同意。草案还禁止面向未成年人的游戏付费抽奖、“付费获胜”和画像广告，要求游戏虚拟货币标明真实币值；欧盟委员会计划于 11 月 11 日提交法案，并同步改革消费者保护合作框架。违规企业最高可被处以全球营业额 6%的罚款，但两项提案仍须欧洲议会和成员国政府批准，尚未成为生效法律。

telegram · zaihuapd · 11月9日 16:42

**「从草案到生效」** 这类立法针对的是数字服务利用产品机制影响消费选择的问题，拟通过关闭自动播放和连续使用奖励、明确订阅取消与续费程序，以及披露游戏虚拟货币的真实币值，限制诱导过度使用和模糊付费安排。欧盟委员会还计划同时改革消费者保护合作框架，但两项提案均须欧洲议会与成员国政府同意，因此目前仍属拟议立法，而非已生效的义务。

**「潜在合规影响」** 若草案按现有方向获批，数字平台和游戏开发商将需要改造用户界面、订阅及付费流程，停止面向未成年人的付费抽奖、“付费获胜”和画像广告，并披露游戏虚拟货币对应的真实币值；违规企业最高可能被处以相当于全球年营业额 6% 的罚款。由于提案仍须欧洲议会与成员国批准，这些目前属于待确认的合规风险，而非已经生效的义务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://eprs.europarl.europa.eu/EPRS_BRI%282026%29791529">Towards a digital fairness act | EPRS Website</a></li>
<li><a href="https://www.euronews.com/2026/11/09/eu-to-blacklist-ten-manipulative-online-design-traps-leaked-draft-shows">EU to blacklist ten online design &#x27;traps&#x27;, leaked draft shows</a></li>
<li><a href="https://www.reuters.com/legal/litigation/companies-risk-fines-6-global-turnover-unfair-digital-trade-practices-eu-draft-2026-11-09/">Companies risk fines of 6% global turnover for unfair digital ...</a></li>

</ul>
</details>

**标签**: `#欧盟监管`, `#数字公平`, `#反成瘾设计`, `#游戏虚拟货币`, `#消费者保护`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [前三季度中国新能源乘用车出口增长 138.8%](https://finance.sina.com.cn/tech/roll/2026-10-26/doc-iniwpfnc2438186.shtml) ⭐️ 7.0/10

据新浪财经报道，2026 年前三季度中国新能源乘用车出口 388.7 万辆，同比增长 138.8%；同期国内零售量为 775.8 万辆，同比下降 12.8%。

telegram · zaihuapd · 11月10日 02:56

**「背景」** 作为此前基线，乘联分会数据显示，2026 年 1 至 6 月新能源乘用车批发销量为 678.8 万辆，同比增长 5.1%，整体销量增长相对温和。

**「行业影响」** 对新能源车企而言，出口增长可部分抵消国内零售下滑对销量的冲击，海外市场正成为缓冲国内需求疲软的重要渠道。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://m.nbd.com.cn/articles/2026-07-08/4461678.html">6月燃油 乘 用 车 销量 降 39...</a></li>

</ul>
</details>

**标签**: `#中国新能源汽车`, `#出口增长`, `#国内零售`, `#汽车行业`

---