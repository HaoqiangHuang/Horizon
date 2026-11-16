# Horizon 每日速递 - 2026-11-16

> 从 35 条内容中筛选出 4 条重要资讯。

---

**科技新闻**
1. [Meta FAIR 与 NYU 解耦多模态视觉编码](#item-tech-news-1) ⭐️ 8.0/10
2. [现代 LLM 位置嵌入：实现与理论](#item-tech-news-2) ⭐️ 7.0/10
3. [美团开源 LongCat-2.5，称训练全程使用升腾](#item-tech-news-3) ⭐️ 7.0/10

**财经新闻**
1. [美法官驳回三大 DRAM 厂商撤诉动议](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Meta FAIR 与 NYU 解耦多模态视觉编码](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

Meta FAIR 与 NYU 研究团队在一项受控研究中从头训练了 200 多个多模态语言模型，在数据一致且将视觉编码器预训练计入总算力预算的条件下，分别检验了编码器是否预训练、是否保留仅供视觉词元使用的参数，以及编码器放置位置三个因素。团队报告称，独立视觉编码器预训练并非必要：使用对比学习、自监督和两种字幕目标预训练的编码器，在匹配计算量下最多只能与从头训练者打平；将 MetaCLIP 预训练延长 6.5 倍虽将 ImageNet 线性探测准确率从 80.4%提高至 84.4%，却未提升 VQA 表现。视觉专属参数仍然必要：从 0.6B 到 6.4B 的模型中，无编码器方案均落后，约需 3 倍计算量才能追平；让 LLM 共享编码器参数只改善了文本表现，未改善 VQA。编码器位置也可替换：在 LLM 前 8 层加入零初始化、仅供视觉词元使用的注意力投影和 FFN 的“in-fusion”方案，在 1.7B 至 6.4B 规模上与独立编码器相当，首词元延迟约低 13%；在 1.7B 规模下，其 VQA 得分为 45.0，高于独立编码器的 44.4、文本共享参数的 42.3 和末 8 层分支的 35.1。

reddit · r/MachineLearning · /u/trungh98 · 11月15日 17:38

**「研究背景」** 多模态语言模型通常先由视觉编码器处理图像，再将视觉表示送入语言模型；相关设计往往把视觉编码器预训练、仅供视觉 token 使用的参数，以及编码器相对于语言模型的放置位置捆绑在一起，因此不同模型之间的数据和算力差异很难揭示真正起作用的因素。《Unbundling Multimodal Vision Encoding》将这三项设计拆开，在统一数据、从头训练和匹配算力的条件下分别比较，以检验视觉能力是否必须依赖独立的预训练编码器。

**「对 MLLM 训练的影响」** 对训练多模态语言模型的团队，这项由作者报告的受控实验支持把“是否预训练视觉编码器”和“是否保留视觉专属参数”分开决策：在相同数据和计算预算下，单独预训练最多只能与从头训练持平，因此可将其视为可选步骤；但无编码器模型在 0.6B–6.4B 规模均落后，约需 3 倍计算才能追平，不能直接删除视觉专属参数。实现上，将视觉专用分支接入 LLM 前 8 层在 1.7B–6.4B 规模与独立编码器相当，并报告首 token 时间降低约 13%，可作为资源受限团队评估的结构方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.alphaxiv.org/">Explore | alphaXiv</a></li>

</ul>
</details>

**标签**: `#multimodal-language-models`, `#vision-encoders`, `#model-training`, `#ablation-studies`

---

<a id="item-tech-news-2"></a>
### [现代 LLM 位置嵌入：实现与理论](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 7.0/10

文章《Understanding Positional Embeddings in Modern LLMs》是一篇面向 LLM 工程师和开发者的技术解读，聚焦现代大语言模型中位置嵌入的实现。现有材料将 Hacker News 上的讨论概括为：实现层面的说明有用，但要真正理解位置嵌入，还需要更深入的数学理论。材料没有提供文章正文，因此无法确认其具体覆盖的模型、公式或实验结论；这不是一项新产品或新功能发布。

hackernews · vismit2000 · 11月15日 12:14 · [社区讨论](https://news.ycombinator.com/item?id=50506376)

**「理解位置编码的前提」** 位置编码之所以是 Transformer 的独立组成部分，是因为注意力机制本身只依据 token 表示和因果掩码进行信息交换，并不会自动提供可区分的绝对位置；模型因此需要额外机制表示词序。相关方法从可学习的绝对位置表发展到在注意力中编码相对位置关系的表示方法，例如 RoPE，而一些现代架构还会改造或省略显式位置编码。

**「对开发者的直接影响」** LLM 工程师可利用文中针对经典位置编码、RoPE 及现代架构如何调整或省略显式位置信息的图解、数学说明和小型 PyTorch 实现，更直接地比较并实现这些方案。Hacker News 评论者则认为文章偏重实现、缺少群表示等理论基础；若要推导或修改位置编码，开发者不能只照抄实现，而应补充相关理论。这一批评属于评论者观点，并非经过独立验证的结论。

**「社区讨论：群表示理论视角」** 评论者 programjames 认为，这篇文章主要停留在位置嵌入的实现层面；要真正理解它们，应把位置嵌入视为群表示，并借助这种结构推导和参数化出可微且可学习的表示。其举例称，Rotary positional embeddings（RoPE）可视为平移群的表示，而 n 维平移群 ℝⁿ 是阿贝尔群；这是对文章理论深度的评论，所提供的评论内容在此处被截断。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-positional-embeddings">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://daily.dev/posts/understanding-positional-embeddings-in-modern-llms-415mglzuo">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://techbytes.app/posts/understanding-positional-embeddings-in-modern-llms/">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-positional-embeddings">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://zeli.app/story/50506376">Why LLMs Need Positional Embeddings · 22 HN comments | Zeli</a></li>

</ul>
</details>

**标签**: `#large-language-models`, `#positional-embeddings`, `#transformer-architecture`, `#representation-theory`

---

<a id="item-tech-news-3"></a>
### [美团开源 LongCat-2.5，称训练全程使用升腾](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 7.0/10

美团 LongCat 团队在模型正式发布约一周后开放了 LongCat-2.5 权重，采用 MIT 许可证，允许商用。该模型总参数量为 1.6 万亿，每个 token 激活约 480 亿参数，支持文本、图像和视频输入，主要面向自主完成长时、多步骤任务，尤其是编程任务。美团称其训练全程使用华为升腾加速卡、未使用英伟达 GPU；官方披露的 Terminal Bench v2.1 得分为 88.4，略低于 Claude Opus 5 的 89.1，但相关训练方法和评测细节尚缺乏第三方验证。

telegram · zaihuapd · 11月15日 11:08

**「从代码编辑到项目执行」** LongCat-2.5 延续了此前的 LongCat 产品线：LongCat 官方资料称，LongCat-2.0 主要用于编写和编辑代码，而 2.5 进一步面向跨代码库、终端、浏览器、表格和设计画布完成完整项目。此次是在模型正式发布约一周后开放权重，变化重点是从代码层面的辅助转向多工具、多环境的长时程任务执行。

**「可商用，但仍需验证部署条件」** MIT 权重允许开发者将 LongCat-2.5 用于商业项目，并围绕文本、图像和视频输入开发长流程编程智能体；准备替换现有模型的团队应先在真实代码库中测试代码质量与长任务稳定性。官方所称“全程使用升腾、未使用英伟达 GPU”仅针对训练过程，不能据此推断推理部署也无需英伟达硬件，而第三方评测和具体部署要求仍不充分。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.longcatai.org/">LongCat AI - LongCat - 2 . 5 Native Multimodal Agent Model ( 1 . 6 T)</a></li>
<li><a href="https://presentofai.com/e/39988">Meituan releases 1.6T-parameter LongCat 2 . 5 on Chinese chips</a></li>
<li><a href="https://help.apiyi.com/en/new-chinese-agent-model-switch-checklist-en.html">Should You Switch to the Newly Released Domestic Agent Model...</a></li>

</ul>
</details>

**标签**: `#AI智能体`, `#大语言模型`, `#开源模型`, `#华为升腾`, `#多模态`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美法官驳回三大 DRAM 厂商撤诉动议](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 7.0/10

美国法官 Noël Wise 驳回美光、三星和 SK 海力士要求撤销 DRAM 价格操纵集体诉讼的动议，认为原告提交的新证据显示三家厂商的同步行动更像“编队飞行”；案件将进入后续审理，但价格操纵指控尚未得到证实。

telegram · zaihuapd · 11月15日 16:39

**「案件背景」** 这是一起拟议的间接购买者集体诉讼，原告是指通过电脑、手机等产品间接购买 DRAM（常用内存芯片）的消费者和小企业，指控美光、三星和 SK 海力士限制传统 DRAM 供应并推高价格；法官 Noël Wise 驳回撤诉动议，只是让指控进入后续审理，并不等于已经认定价格操纵。

**「行业影响」** 美光、三星和 SK 海力士将就 DRAM 集体诉讼进入证据披露等后续程序，DRAM 采购企业可能面临供应与价格不确定性，但价格操纵指控尚未获证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge">Judge denies motion to dismiss DRAM price - fixing lawsuit against...</a></li>
<li><a href="https://litnews.ai/articles/garciaguirre-samsung-sk-hynix-micron-dram-conspiracy-suit-survives-dismissal">Judge Refuses to Dismiss DRAM Supply Conspiracy Suit Against...</a></li>
<li><a href="https://finance.yahoo.com/technology/articles/judge-denies-motion-dismiss-dram-152445837.html?fr=sycsrp_catchall">Judge denies motion to dismiss DRAM price-fixing lawsuit ...</a></li>
<li><a href="https://wccftech.com/federal-judge-rejects-memory-makers-defense-samsung-micron-sk-hynix-dram-shortage-lawsuit/">Federal Judge Rejects Memory Makers’ Defense To ... - Wccftech</a></li>

</ul>
</details>

**标签**: `#DRAM`, `#反垄断`, `#价格操纵`, `#半导体`, `#集体诉讼`

---

