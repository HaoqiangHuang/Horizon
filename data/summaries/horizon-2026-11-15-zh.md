# Horizon 每日速递 - 2026-11-15

> 从 37 条内容中筛选出 8 条重要资讯。

---

**科技新闻**
1. [Lovable 应用暴露护照资料及逾 20 万条私信](#item-tech-news-1) ⭐️ 8.0/10
2. [星舰完成首次轨道返回塔捕，助推器爆炸](#item-tech-news-2) ⭐️ 8.0/10
3. [SpaceX 在 Starship 第 15 次飞行中捕获飞船](#item-tech-news-3) ⭐️ 7.0/10
4. [意大利据报就 Android 数据访问问题罚 Meta 8.87 亿美元](#item-tech-news-4) ⭐️ 7.0/10
5. [纯 JAX 约 200 行实现 DeepSeek V3](#item-tech-news-5) ⭐️ 7.0/10
6. [PyPI 项目页上线新的安全与来源证明信号](#item-tech-news-6) ⭐️ 7.0/10
7. [Meta 因相册数据收集被意大利罚款 8.05 亿欧元](#item-tech-news-7) ⭐️ 7.0/10

**财经新闻**
1. [Anthropic 据报限制中港投资者参与 IPO](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Lovable 应用暴露护照资料及逾 20 万条私信](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

一项安全研究发现，多款由 Lovable 生成的 AI 应用因数据库行级安全（RLS）配置不足，暴露了用户护照资料和超过 20 万条私人消息。Lovable 安全负责人确认根因是行级安全配置不足，并称平台现会在发布前自动扫描每个应用，同时免费向用户提供更深入的静态应用安全测试（SAST）；发现问题时，用户可选择“修复”或启用后台自动修复。

hackernews · armcat · 11月14日 17:43 · [社区讨论](https://news.ycombinator.com/item?id=50499017)

**「背景：行级安全默认值」** 要理解这起事件，关键概念是 Supabase/PostgreSQL 的行级安全（RLS）：它按用户身份和权限限制表中每条记录的读取，配置不足会让本应受保护的数据被接口直接返回。社区讨论中有人称，Supabase 为降低接入门槛而长期默认不启用 RLS，并据称于 10 月 30 日修复了这一点，但既有项目是否同步采用新默认值仍有争议。

**「现有 Lovable 应用需立即核查数据库权限」** 本项研究涉及的护照资料和超过 20 万条私信表明，敏感数据未被前端页面展示并不等于受到访问控制；当行级安全（RLS）缺失或配置不足时，任何取得浏览器内置公开 anon key 的人都可能直接通过 Data API 读取数据表，许多配置下还可写入（tool-3-3）。开发者应逐表审计并补齐 RLS、显式授权和写入策略，同时注意 Supabase 自 2026 年 10 月 30 日起不再默认向 Data API 暴露新公共表：依赖旧默认的应用可能出现 42501 错误并需补充 GRANT，但这并不代表既有表已经修复（tool-3-1、tool-3-2）。

**「社区讨论责任与默认安全」** 讨论中的主要分歧在于责任归属：一名评论者认为 Supabase 长期采用的宽松数据库默认值也应负责，并声称相关问题虽据称已于 10 月 30 日修复，既有项目仍可能沿用旧设置；Lovable 安全负责人则强调平台已有的发布前扫描与自动修复能力。另有评论者认为，AI 生成应用数量庞大且攻击门槛较低，平台应采用默认拒绝数据库访问、最小权限 API 和自动鉴权测试等机制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.crissyfield.de/research/lovable-en/">Lovable : Many Apps Expose Sensitive Data — Crissy Field GmbH</a></li>
<li><a href="https://heydev.us/blog/supabase-tables-not-exposed-by-default-october-2026">Supabase Data API Change Oct 30, 2026: What Breaks</a></li>
<li><a href="https://dev.to/fixloopdev/supabase-oct-30-why-new-tables-get-42501-and-how-to-fix-grants-rls-2i8k">Supabase Oct 30: why new tables get 42501 (and how to fix ...</a></li>
<li><a href="https://www.guardlayer.io/blog/lovable-rls-vulnerability-cve-2025-48757">Lovable RLS vulnerability (CVE-2025-48757) and the 2026 leaks</a></li>

</ul>
</details>

**标签**: `#application-security`, `#row-level-security`, `#AI-generated-apps`, `#data-privacy`, `#Supabase`

---

<a id="item-tech-news-2"></a>
### [星舰完成首次轨道返回塔捕，助推器爆炸](https://www.spacex.com/launches/starship-flight-15) ⭐️ 8.0/10

SpaceX 称，第 15 次星舰试飞于当地时间 11 月 13 日从得州发射，成功入轨并在约 22.5 小时、绕地球约 14 圈后返回得州 Starbase，由发射塔机械臂首次直接捕获；任务还部署了全部 26 颗 Starlink V3，其中 3 颗携带摄像头检查隔热瓦。超重型助推器因技术问题中止返场，在墨西哥湾受控溅落过程中爆炸，未能实现原定的飞船与助推器两级塔捕，具体故障原因尚未公布。因此，本次成果是 SpaceX 宣布的飞船轨道返回塔捕成功，而完整的两级重复使用回收仍未完成。

telegram · zaihuapd · 11月14日 03:03

**「“塔捕”如何实现两级回收」** 星舰的“塔捕”是指让 Super Heavy 助推器和 Starship 飞船返回得州 Starbase 发射塔，由塔上机械臂直接夹住，而不是常规着陆或落海回收；要实现“双回收”，两级都必须完成这一动作。此次第 15 次试飞是 SpaceX 首次尝试在同一任务中塔捕助推器和飞船。

**「两级重复使用仍未完成验证」** 本次试飞已完成 26 颗 Starlink V3 卫星部署，并按 SpaceX 通报实现了星舰轨道返回后的发射塔捕获；但助推器改为在墨西哥湾溅落时爆炸，未能返场捕获，因此尚不能将两级同时回收视为已验证能力。SpaceX 后续需要查明爆炸原因并重新完成助推器返场捕获测试，才能确认整套回收流程可用于稳定复用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/13/spacex-launches-starship-in-key-test-flight-of-massive-rocket.html">SpaceX launches Starship in key test flight of massive ...</a></li>
<li><a href="https://www.youtube.com/watch?v=Kus39IK-ZvQ">SPACE X STARSHIP FLIGHT 15 LIVE | First-Ever Orbital ... - YouTube</a></li>
<li><a href="https://www.basenor.com/blogs/news/starship-flight-15-6-details-that-matter-for-todays-launch">Starship Flight 15 : 6 Details That Matter for Today&#x27;s Launch</a></li>
<li><a href="https://www.theguardian.com/science/2026/nov/13/spacex-starship-megarocket-blasts-off-earth-orbit">SpaceX Starship megarocket blasts off before expected return for...</a></li>

</ul>
</details>

**标签**: `#SpaceX Starship`, `#可重复使用运载火箭`, `#轨道返回与塔捕`, `#Starlink V3`, `#助推器故障`

---

<a id="item-tech-news-3"></a>
### [SpaceX 在 Starship 第 15 次飞行中捕获飞船](https://www.spacex.com/launches/starship-flight-15) ⭐️ 7.0/10

SpaceX 在“Starship Flight 15”中完成对返回的 Starship 飞船的捕获，是其推进飞行器完全复用方案的一次实飞进展。现有材料仅包含 SpaceX 官方社交媒体帖文，以及从第 15 次飞行视频约 53 分 53 秒处开始的相关片段，未提供捕获机构状态、捕获后检查结果或任务性能数据。因此，材料目前支持的结论仅限于此次捕获动作已经完成，尚不足以确认飞船能够恢复飞行、复用成本已经下降或发射节奏已经提高。

hackernews · ls612 · 11月14日 21:22 · [社区讨论](https://news.ycombinator.com/item?id=50500963)

**「从捕获到复用的技术门槛」** 全复用发射系统的关键不只是完成一次回收，而是让同一枚飞行器在捕获后经过检查、整修，再次执行发射任务。因此，Flight 15 的捕获属于全复用路线的一次飞行验证；SpaceX 的官方页面主要提供任务链接和视频，未给出复飞记录、翻修成本或运营频率数据，不能据此认定已经实现可规模化的重复使用。

**「两级完全复用仍待验证」** Flight 15 验证了星基地“筷子”机械臂能够捕获 Starship 飞船本体，但 Super Heavy 助推器未能一并回收，因此尚不能据此认定整套两级运载系统已具备完全复用能力。后续关键验收点是两级均成功回收并再次飞行，在此之前，基于该任务实现的低成本或高频运营仍属于待验证目标。

**「社区关注重复使用能力」** 评论者将此次捕获视为长期工程进展，但有人认为隔热罩能否经受重复使用，仍是 Starship 实现低成本重复飞行的关键。另有评论者推测，若助推器增加数吨推进剂，或许能同时捕获两级，但最终入轨质量比仍不确定；这些属于社区观点，并非 Flight 15 已经验证的结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.spacex.com/launches/starship-flight-15">SpaceX</a></li>
<li><a href="https://www.theguardian.com/science/2026/nov/13/spacex-starship-megarocket-blasts-off-earth-orbit">SpaceX Starship megarocket blasts off before... | The Guardian</a></li>
<li><a href="https://www.zerohedge.com/technology/watch-live-spacex-targets-historic-starship-booster-double-chopsticks-catch">Elon Musk&#x27;s &#x27;Mechazilla&#x27; Catches Starship Rocket In... | ZeroHedg...</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#Starship`, `#reusable launch systems`, `#spaceflight engineering`

---

<a id="item-tech-news-4"></a>
### [意大利据报就 Android 数据访问问题罚 Meta 8.87 亿美元](https://www.reuters.com/world/italy-fines-meta-887-million-over-android-users-data-access-2026-11-14/) ⭐️ 7.0/10

据报道，意大利因 Meta 被指在未获 Android 用户同意的情况下访问其照片和视频，已对其处以 8.87 亿美元罚款。现有材料没有说明数据访问是通过漏洞、系统权限还是其他方式实现，也未交代上诉状态，因此无法据此判断 Meta 是否绕过了 Android 的授权提示。此次处罚针对 Android 媒体权限的取得与告知，但具体整改要求尚不明确。

hackernews · giuliomagnifico · 11月14日 13:48 · [社区讨论](https://news.ycombinator.com/item?id=50497009)

**「背景」** 理解这起处罚的关键，是区分访问用户图库与仅选择单张照片上传：Facebook 据报通过单一的应用级授权请求访问图库，而意大利监管机构称，事前告知没有说明这也会允许应用基于图库照片生成建议。因此，争议不仅在于用户是否作出授权，还在于授权范围和用途告知是否充分。

**「媒体访问功能须强化告知与权限控制」** 意大利数据保护局称，Meta 的 Facebook 功能在可访问约 2,000 万名智能手机用户的照片和视频时，未充分告知用户其访问行为，并处以 8.05 亿欧元罚款。移动应用提供类似媒体访问能力时，应同时核验明确告知、用户授权和可撤回机制；现有材料并未说明 Meta 是否利用漏洞绕过 Android 权限，不能将此事直接解读为系统级越权。

**「评论者质疑授权与访问方式」** 评论者最集中的疑问是 Meta 如何在未获同意时访问照片，并认为报道缺少区分权限滥用、绕过授权提示与用户主动授权的技术细节。也有评论者指出，Android 功能本就需要设备授权且用户可以撤销权限，因此处罚所依据的“未获同意”具体指首次授权、后续访问还是告知不足，仍需监管文件澄清；这些属于评论者观点，并非已确认的技术事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50497009">Italy fines Meta $ 887 M over Android users &#x27; data access | Hacker News</a></li>
<li><a href="https://www.bbc.com/news/articles/cwn83gxemk35o">Italy fines Meta €805m over accessing users&#x27; photos</a></li>

</ul>
</details>

**标签**: `#privacy`, `#Android`, `#Meta`, `#regulation`, `#mobile security`

---

<a id="item-tech-news-5"></a>
### [纯 JAX 约 200 行实现 DeepSeek V3](https://github.com/Vaibhaav-Tiwari/deepseek-v3-jax) ⭐️ 7.0/10

Show HN 项目 Vaibhaav-Tiwari/deepseek-v3-jax 用约 200 行纯 JAX 重实现 DeepSeek V3，目标是让开发者从代码层面理解模型架构并开展实验，而不是提出新的模型突破。一名评论者称，该项目已在 Fedora、ROCm 和 RX 7600 XT 16GB 上端到端运行，并需要设置 HSA\_OVERRIDE\_GFX\_VERSION=11.0.0。该项目目前主要具有教育和实验价值，现有材料未证明它能复现官方实现的训练或推理效果，也未达到生产级一致性。

hackernews · VaibhaavTiwari · 11月14日 15:04 · [社区讨论](https://news.ycombinator.com/item?id=50497589)

**「项目定位」** 该项目并未搬运官方 DeepSeek-V3 权重，而是依据技术报告，用约 190 行纯 JAX 重建其架构，包括多头潜在注意力、无辅助损失的混合专家机制和多 token 预测；实现不依赖 Flax、Equinox 或 PyTorch。仓库及同期介绍称，作者实际从零训练的是使用公共领域侦探小说训练的约 3620 万参数小模型，而非完整规模的 DeepSeek-V3，因此该项目主要面向架构教学和实验。

**「降低 DeepSeek V3 的实验门槛」** 这个约 200 行的纯 JAX 实现为开发者提供了一个可读、可修改的 DeepSeek V3 实验基线；一名社区用户称，它让其 Fedora、ROCm 和 JAX 组合首次在 16GB RX 7600 XT 上端到端运行。该用户同时指出，此显卡需要配置两个环境变量，其中包括 HSA\_OVERRIDE\_GFX\_VERSION=11.0.0，因此消费级 AMD 用户仍需按硬件调整 ROCm/JAX 环境；这属于个人运行报告，不代表已验证与官方实现具有生产级数值一致性。

**「社区反馈」** 多名评论者认为，从第一性原理重建模型有助于理解推理流程和架构，也有人希望获得面向 Java、Python 及常规软件工程师的学习路线。实际使用者报告 Fedora、ROCm 和 RX 7600 XT 16GB 组合能够端到端运行，但需要上述 HSA\_OVERRIDE\_GFX\_VERSION 环境变量；这是单条社区经验，不能视为广泛兼容性保证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Vaibhaav-Tiwari/deepseek-v3-jax">GitHub - Vaibhaav-Tiwari/deepseek-v3-jax: DeepSeek V3 (MLA ...</a></li>
<li><a href="https://news.lavx.hu/article/deepseek-v3-architecture-rebuilt-in-190-lines-of-pure-jax">DeepSeek V3 Architecture Rebuilt in 190 Lines of Pure JAX</a></li>
<li><a href="https://elsolitario.org/en/2026/11/14/deepseek-v3-jax-190-lines/">DeepSeek V3 JAX Implementation in 190 Lines - elsolitario.org</a></li>

</ul>
</details>

**标签**: `#DeepSeek V3`, `#JAX`, `#LLM implementation`, `#AI education`, `#ROCm`

---

<a id="item-tech-news-6"></a>
### [PyPI 项目页上线新的安全与来源证明信号](https://blog.pypi.org/posts/2026-11-06-ui-updates-complete/) ⭐️ 7.0/10

PyPI 已上线重新设计的项目页面，以更清晰的方式向用户和开发者展示软件包的安全与来源证明（provenance）信号。现有材料表明界面改造已经完成，但未说明具体包含哪些验证状态、支持哪些发布流程或覆盖率，因此不能将其视为对所有恶意包的全面检测。

hackernews · rbanffy · 11月14日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50497892)

**「理解 PyPI 的来源证明」** PyPI 的 provenance（来源证明）依赖 Trusted Publishing：发布者配置该功能后，PyPI 可自动生成 provenance attestations，并减少依赖令牌式认证所暴露的风险。这类证明用于核验包的构建来源，并不等同于证明包内容无害；2026 年的包注册表调查显示，来源证明的生态覆盖仍不均衡，PyPI 被列为 L3。

**「来源信号不能替代安全审计」** 对 PyPI 用户和维护者，新页面将 provenance 与 Trusted Publisher 信息变成更易核验的发布来源线索；PyPI 的方案讨论提出，为采用 Trusted Publishing 的包提供零配置 provenance，并以 Trusted Publisher 身份作为 Sigstore 代码签名身份。但来源证明不等于包本身安全：一份事件报告记录了超过 170 个 npm 和 PyPI 包在 CI/CD 环境被攻陷后受到影响，说明该机制无法覆盖发布流水线本身遭入侵的风险。维护者因此应严格保护发布者身份和 CI 凭据，用户也应将 provenance 与项目信誉及包行为检查结合使用。

**「社区讨论」** 讨论者总体欢迎 PyPI 强调来源证明，并希望基于 Sigstore 的“无密钥”短期签名得到更广泛支持；有人同时呼吁让可信发布机制支持可复用的 CI/CD 工作流。批评者认为依赖托管 CI 和 OIDC 的信任模型可能加剧云服务集中与锁定，另有评论者提醒，来源证明主要能揭示原本可信项目遭入侵后的异常，不能证明一个陌生软件包本身并非恶意。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://zenn.dev/sqer/articles/e4df3d397f5651?locale=en">The 2026 State of Package Registry Provenance : Who Is Signing What?</a></li>
<li><a href="https://github.com/lirantal/pypi-security-best-practices">GitHub - lirantal/ pypi - security -best-practices: Collection of PyPI ...</a></li>
<li><a href="https://discuss.python.org/t/pre-pep-exposing-trusted-publisher-provenance-on-pypi/42337">Pre-PEP: Exposing Trusted Publisher provenance on PyPI</a></li>
<li><a href="https://threatfrontier.com/articles/mini-shai-hulud-supply-chain-worm-trusted-publishing">Mini Shai-Hulud Supply-Chain Worm Hits npm and PyPI</a></li>

</ul>
</details>

**标签**: `#PyPI`, `#software supply-chain security`, `#package provenance`, `#Python packaging`, `#Sigstore`

---

<a id="item-tech-news-7"></a>
### [Meta 因相册数据收集被意大利罚款 8.05 亿欧元](https://www.garanteprivacy.it/home/docweb/-/docweb-display/docweb/10321080) ⭐️ 7.0/10

意大利隐私保护机构 Garante 已就 Facebook Android 应用的相册数据收集行为对 Meta 处以 8.05 亿欧元罚款，涉及约 2000 万名意大利用户的照片、视频及元数据。监管机构称，2023 年上线的相册推荐功能默认开启且授权提示笼统，未能取得读取相册数据所需的具体同意。Meta 必须在 60 天内将该功能默认关闭并改为单独征得用户同意，否则不得向未提供有效授权的用户启用。

telegram · zaihuapd · 11月14日 14:37

**「相册推荐功能的授权背景」** Facebook Android 的相册推荐功能于 2023 年上线，默认开启，并以较为笼统的权限提示访问用户相册；该功能会读取照片、视频及元数据来生成推荐。此次争议的核心是应用对图库的批量访问是否获得了针对推荐用途的具体同意，以及默认开启设置能否满足这一要求。

**「相册推荐需重新授权」** 对约 2000 万名意大利 Facebook Android 用户而言，Meta 必须在 60 天内将相册推荐功能默认关闭，并在启用前针对相册照片、视频及元数据收集取得具体同意；未取得有效授权的用户将无法使用该功能。Meta 同时面临 8.05 亿欧元罚款。

**标签**: `#Privacy`, `#Data Governance`, `#Regulation`, `#Meta`, `#Android`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [Anthropic 据报限制中港投资者参与 IPO](https://m.economictimes.com/markets/us-stocks/news/anthropic-ipo-share-orders-from-china-are-said-to-be-rebuffed/articleshow/135809948.cms) ⭐️ 7.0/10

据《经济时报》援引匿名知情人士，Anthropic 拟以 1.4 万亿美元估值进行 IPO，计划 11 月 18 日定价、翌日上市并最多募资 904 亿美元，同时因《国际武器贸易条例》（ITAR）出口管制拒绝中国内地及香港投资者下单；相关说法尚未获公司或监管方确认。

telegram · zaihuapd · 11月14日 10:18

**「背景」** ITAR 是美国《国际武器贸易条例》的简称，属于国防相关商品、软件和技术出口管制框架。Anthropic 此次 IPO 由高盛和摩根士丹利参与承销、拟于 11 月 19 日挂牌；拒接中国内地及香港投资者下单仍仅是知情人士说法，尚未获公司或监管方正式确认。

**「中港投资者转向替代认购通道」** 据报道，中国内地及香港的机构投资者被承销银行以美国出口管制为由拒单，部分资金转而通过英属维尔京群岛信托、SPV 和掉期结构认购，直接影响相关投资者及融资通道。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/10/technology/anthropic-ipo-valuation-share-price.html">Anthropic Targets Valuation of Up to $ 1 . 4 Trillion for Blockbuster...</a></li>
<li><a href="https://www.zerohedge.com/markets/anthropic-launches-100-billion-ipo-worth-14-trillion-or-10-trillion-depending-whos-counting">Anthropic Launches $100 Billion IPO Worth $ 1 . 4 Trillion ...</a></li>
<li><a href="https://the-decoder.com/banks-bar-chinese-and-hong-kong-investors-from-anthropic-ipo-over-us-export-controls/">Banks bar Chinese and Hong Kong investors from Anthropic IPO ...</a></li>
<li><a href="https://aiweekly.co/alerts/banks-shut-china-hong-kong-investors-out-of-anthropic-ipo">Banks Shut China, Hong Kong Investors Out of Anthropic IPO</a></li>

</ul>
</details>

**标签**: `#Anthropic`, `#IPO`, `#出口管制`, `#中港投资者`

---

