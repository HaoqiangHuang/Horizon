---
layout: default
title: "Horizon Summary: 2026-10-26 (ZH)"
date: 2026-10-26
lang: zh
---

> 从 28 条内容中筛选出 4 条重要资讯。

---

**科技新闻**
1. [Brotli 高危漏洞扩展至 Python 和 Node.js](#item-tech-news-1) ⭐️ 8.0/10
2. [Nanbeige4.3-33B 开放代理教师模型](#item-tech-news-2) ⭐️ 7.0/10
3. [苹果将发布首款触屏 MacBook Pro](#item-tech-news-3) ⭐️ 7.0/10

**财经新闻**
1. [中国 2025 年末总人口降至 14.0489 亿](#item-finance-news-1) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Brotli 高危漏洞扩展至 Python 和 Node.js](https://www.aikido.dev/blog/python-packages-vulnerable-node2shell-brotli-cve-2026-111497) ⭐️ 8.0/10

据 Aikido Security 报道，谷歌 Brotli 解码器漏洞 CVE-2026-111497 影响 1.0.3 至 1.2.0 版本，CVSS 4.0 评分为 9.2，Node.js 和 Python 相关组件均受影响。远程未认证攻击者可发送特制压缩流，触发内存损坏、敏感数据泄露、进程崩溃，甚至可能执行任意代码。Python 的 Brotli 需升级至 1.2.1，brotlicffi 需升级至 1.2.1.0；Node.js 修复版本为 22.23.4、24.22.1 或 26.12.1。该漏洞最初以 Node2Shell 名称披露，后被称为 HTTP2Shell；OpenAI 称其于 2026 年 2 月发现此问题。

telegram · zaihuapd · 10月25日 02:42

**「从 Node2Shell 到 HTTP2Shell」** Horizon 10 月 24 日的日报已将该问题描述为可能波及 Node.js、Python 等运行时的 Brotli 内存安全缺陷，但当时材料尚未提供 CVE 编号、完整受影响版本或独立验证。此次披露补充了 CVE-2026-111497 的标识、版本范围及修复版本，进一步明确了风险边界和升级路径。

**「立即升级受影响的 Brotli 组件」** 部署了 Google Brotli 1.0.3 至 1.2.0、并会解码不可信压缩内容的 Python 或 Node.js HTTP 服务面临越界写入风险，可能导致进程崩溃、敏感内存泄露，甚至被远程未认证攻击者执行任意代码。运维团队应立即将 Python 的 Brotli 升级至 1.2.1、brotlicffi 升级至 1.2.1.0，并将 Node.js 更新至 22.23.4、24.22.1 或 26.12.1。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://nitter.click/AikidoSecurity/status/2113759110625906950?__galadriel=lPmlGl9id4oAd5UeBwMhlYKArHyr6lR2IDGujPwB5HV2kQ1aLoPWFd5A9sGuzNcmrp8fUso8qygmHcKTDZ8MNHWqQ3bDJcycV87xp_0VypzQLYj6O_RRHlZuQqj33oASGY2YLSoAiMjeOZN40h7Stf8AG7DPrGZbAPVKUXy36HoMudRbvwF3_r2uYNmfJMhpKzywQDM6Ab8">2026-10-24 — Brotli 解码漏洞引发多语言 RCE 风险</a></li>
<li><a href="https://app.opencve.io/cve/CVE-2026-111497">CVE-2026-111497 - Vulnerability Details - OpenCVE</a></li>
<li><a href="https://nvd.nist.gov/vuln/detail/cve-2026-111497">NVD-CVE-2026-111497</a></li>

</ul>
</details>

**标签**: `#Brotli`, `#CVE-2026-111497`, `#Python`, `#Node.js`, `#漏洞修复`

---

<a id="item-tech-news-2"></a>
### [Nanbeige4.3-33B 开放代理教师模型](https://www.reddit.com/r/MachineLearning/comments/1xf6x35/nanbeige_releases_nanbeige4333b_an_apache_20/) ⭐️ 7.0/10

Nanbeige 发布 Nanbeige4.3-33B，以 Apache 2.0 许可开放权重，并将其定位为计划中的 3B 较小代理模型的教师；模型卡标注其上下文窗口为 512K。发布团队称，在相同测试框架和推理设置下，该模型的 Terminal-Bench 2.1 得分为 80.9，高于 Qwen3.8-27B 的 73.0；但其 SWE-Bench Pro 得分为 60.3，低于对方的 61.7，这些结果尚无独立复现。多轮工具调用评估会通过 preserve\_thinking=true 保留此前推理，模型卡建议仅在代理任务而非普通聊天中采用该设置；复现时应固定此选项，并同时比较任务成功率和总生成 token 数。

reddit · r/MachineLearning · /u/jatingargiitk · 10月25日 16:32

**「教师模型与蒸馏背景」** 在模型蒸馏中，“教师模型”是规模更大的参考模型，其输出或推理轨迹可用于训练更小的“学生模型”；33B 稠密模型 Nanbeige4.3-33B 被定位为尚未发布的 3B 智能体的教师。该项目的代理评测使用 \`preserve\_thinking=true\` 延续多轮工具调用中的先前推理，因此后续复现或比较学生模型时，应固定这一设置，并将任务成功数与生成 token 数一并比较。

**「代理开发者的直接影响」** 开发者现在可以在 Apache 2.0 许可下获取 Nanbeige4.3-33B 权重，将其作为具有 524,288 上下文窗口的教师模型开展蒸馏和代理研究，但计划中的 3B 较小模型尚未发布。复现其多轮工具调用评测时，应按模型卡建议启用 \`preserve\_thinking=true\`；同时，团队自报的 Terminal-Bench 2.1 得分虽高于 Qwen3.8-27B，但在 SWE-Bench Pro 上反而较低，因此应按实际工作负载选型，而非将其视为全面领先的部署模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/nanbeige-opens-33b-model-under-apache-20-with-512k-context">Nanbeige Opens 33B Model Under Apache 2.0 With 512K Context</a></li>
<li><a href="https://www.datastudios.org/post/nanbeige-4-3-33b-open-weight-dense-agentic-model-512k-context">Nanbeige4.3-33B: Apache 2.0 dense agentic coding model with ...</a></li>
<li><a href="https://aiweekly.co/alerts/nanbeige-opens-33b-model-under-apache-20-with-512k-context">Nanbeige Opens 33 B Model Under Apache 2.0 With... | AI Weekly</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#open-weight models`, `#model distillation`, `#language models`, `#agent benchmarks`

---

<a id="item-tech-news-3"></a>
### [苹果将发布首款触屏 MacBook Pro](https://www.bloomberg.com/news/newsletters/2026-10-25/apple-to-unveil-touch-screen-macbook-pro-executive-promotions-in-box-checker) ⭐️ 7.0/10

据该消息援引 Bloomberg 的报道，苹果计划于本周三发布首批触屏 MacBook Pro，提供 14 英寸和 16 英寸版本，并在 Mac 上首次引入触控、OLED 屏幕和灵动岛。触屏预计作为键盘与触控板的补充，而起售价将高于现款 2499 美元。当前内容仅为对 Bloomberg 报道的简短转述，完整技术规格及最终发布信息仍待苹果确认。

telegram · zaihuapd · 10月25日 14:25

**「苹果触屏路线的转变」** 此前，苹果高管多年来一直以人体工学为由否定触屏笔记本，此次引入触控因而代表其产品立场的明显调整。据 Bloomberg 转述，触控仍将被定位为键盘和触控板的补充，而不是取代传统输入方式；具体机型与上市信息仍待苹果正式发布确认。

**「用户换机影响」** 对考虑购买的用户，触屏 MacBook Pro 将为 MacBook Pro 增加触摸输入，但触控仍定位为键盘和触控板的补充，不能据此假设传统输入方式会被取代。新机预计起售价高于现款 2499 美元，而且发布与上市时间可能不同步：发布预计在 10 月 27 日前后，实际上市可能延至 2026 年末或 2027 年初，因此预算和供货情况仍需等待苹果官方确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tweaktown.com/news/114001/apple-is-reportedly-planning-to-launch-a-touchscreen-macbook-later-this-month/index.html">Apple is reportedly planning to launch a touchscreen MacBook later...</a></li>
<li><a href="https://www.squaredtech.co/touchscreen-macbook-apple-launching-with-m5-not-waiting-for-m7">Touchscreen MacBook Pro : Latest Launch Plans Explained</a></li>

</ul>
</details>

**标签**: `#Apple`, `#MacBook Pro`, `#触屏`, `#OLED`, `#消费电子`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [中国 2025 年末总人口降至 14.0489 亿](https://weibo.com/1796087453/5357878513767954) ⭐️ 8.0/10

据该消息援引的《中国统计年鉴 2026》，中国 2025 年末总人口为 14.0489 亿，较 2024 年末减少 339 万；全年出生人口 792 万，自然增长率为-2.41‰。

telegram · zaihuapd · 10月25日 12:02

**「背景」** 此前，中国人口在 2021 年出现近 61 年来首次自然负增长，当年出生人口为 956 万。

**「潜在影响」** 《求是》网此前的条件性分析称，若中国在 2025 年前后达到人口峰值并开始负增长，经济增长将面临需求侧冲击，老龄化也会通过人口总量效应影响消费需求；本次数据显示这一条件已经出现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bilibili.com/video/BV1tu411X7DK/">bilibili.com/video/BV1tu411X7DK</a></li>
<li><a href="https://www.qstheory.cn/qshyjx/2021-05/21/c_1127473014.htm">认识把握 人 口 形势带来 的 机遇与挑战</a></li>

</ul>
</details>

**标签**: `#中国人口`, `#人口负增长`, `#出生率`, `#宏观经济`, `#统计年鉴`

---