---
layout: default
title: "Horizon Summary: 2026-06-30 (ZH)"
date: 2026-06-30
lang: zh
---

> 从 74 条内容中筛选出 9 条重要资讯。

---

1. [最高法院：获取手机位置数据须有搜查令](#item-1) ⭐️ 9.0/10
2. [Anthropic 发布 Claude Sonnet 5，专注智能代理能力](#item-2) ⭐️ 8.0/10
3. [Claude Code 在请求中秘密嵌入隐写标记](#item-3) ⭐️ 8.0/10
4. [Claude Science：面向科学研究的 AI 工作台](#item-4) ⭐️ 8.0/10
5. [1100 万篇论文交互地图，支持时间导航](#item-5) ⭐️ 8.0/10
6. [华为开源盘古 2.0，505B 参数，支持 512K 上下文](#item-6) ⭐️ 8.0/10
7. [Anthropic 获美国批准，向关键基础设施部署 Mythos 5 模型](#item-7) ⭐️ 8.0/10
8. [Claude Code 2.1.91 被指隐蔽遥测检测中国用户](#item-8) ⭐️ 8.0/10
9. [英国拟放宽苹果和谷歌应用支付规则](#item-9) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [最高法院：获取手机位置数据须有搜查令](https://www.androidpolice.com/supreme-court-protects-your-cell-phone-location-data-after-googles-role-in-a-conviction/) ⭐️ 9.0/10

6 月 29 日，美国最高法院以 6 比 3 裁定，执法机构必须获得搜查令才能从 Google 等第三方科技公司获取手机位置数据，将第四修正案保护扩展到此类数字记录。 这一里程碑式判决显著加强了对数百万美国人的数字隐私保护，限制了通过地理围栏令进行的政府监控，并要求获取位置数据时需有合理依据。 该案源于一起 2019 年银行劫案，警方使用地理围栏令要求 Google 提供特定区域内的用户数据；Google 从数百万用户中筛选出 19 个匿名账户，随后确定了嫌犯身份。裁决将案件发回下级法院，以裁定当年的搜查令是否合法。

telegram · zaihuapd · 6月30日 04:00

**背景**: 地理围栏令是一种法律命令，要求公司提供在特定时间段内、特定地理区域内所有设备的位置数据。第四修正案保护公民免受不合理搜查和扣押，而合理隐私期待的概念用于判断无搜查令的政府监控是否违宪。本案澄清了个人对其手机位置记录享有合理隐私期待，即使这些记录由第三方持有。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://zh.wikipedia.org/wiki/地理围栏">地理围栏 - 维基百科，自由的百科全书</a></li>
<li><a href="https://zh.wikipedia.org/zh-hans/隐私预期">隐私预期 - 维基百科，自由的百科全书</a></li>

</ul>
</details>

**标签**: `#privacy`, `#surveillance`, `#supreme court`, `#location data`, `#fourth amendment`

---

<a id="item-2"></a>
## [Anthropic 发布 Claude Sonnet 5，专注智能代理能力](https://www.anthropic.com/news/claude-sonnet-5) ⭐️ 8.0/10

Anthropic 发布了 Claude Sonnet 5，这是迄今为止最具智能代理能力的 Sonnet 模型，速度更快，定价与 Opus 相比有竞争力。 该模型降低了智能代理 AI 的成本，使更多开发者能够构建可使用工具并运行多步骤任务的自主系统，可能加速 AI 代理在开发工作流中的采用。 Claude Sonnet 5 在基准测试中表现不一：在某些编码任务上超越 Opus，但在漏洞发现和谜题解决上落后，且在高努力级别时每任务成本超过 Opus。

hackernews · marinesebastian · 6月30日 17:59 · [社区讨论](https://news.ycombinator.com/item?id=48736605)

**背景**: 智能代理 AI 模型旨在自主使用浏览器和终端等工具完成多步骤任务。Anthropic 的 Sonnet 系列历来是速度与能力的平衡，而 Opus 以更高成本提供更高质量。Claude Sonnet 5 旨在将更先进的代理功能引入 Sonnet 级别。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://platform.claude.com/docs/en/about-claude/models/whats-new-sonnet-5">What's new in Claude Sonnet 5 - Claude Platform Docs</a></li>

</ul>
</details>

**社区讨论**: 社区评论褒贬不一：一些用户质疑性价比，认为在中等努力级别以上，Opus 通常每美元表现更好。其他人赞赏速度和代理改进，但对某些基准测试（如琐事和工具调用）的倒退表示担忧。

**标签**: `#AI`, `#LLM`, `#Claude`, `#Anthropic`, `#machine learning`

---

<a id="item-3"></a>
## [Claude Code 在请求中秘密嵌入隐写标记](https://thereallo.dev/blog/claude-code-prompt-steganography) ⭐️ 8.0/10

一项逆向工程分析发现，Anthropic 的 Claude Code 工具在用户请求中偷偷嵌入隐写标记，且未予披露。 这引发了对 AI 开发工具透明度和信任的严重担忧，可能侵犯用户同意并违反《计算机欺诈与滥用法》等法律，影响广泛的软件工程和 AI 伦理社区。 这些标记通过隐写术嵌入，将数据隐藏在请求的正常文本中，难以被检测。该做法似乎旨在识别涉及模型蒸馏的中国公司的使用，但未事先告知用户。

hackernews · kirushik · 6月30日 15:44 · [社区讨论](https://news.ycombinator.com/item?id=48734373)

**背景**: 隐写术是将消息隐藏在其他非秘密数据中的做法，例如在语言模型生成的正常句子中隐藏文本。Claude Code 是 Anthropic 的代理式编码工具，运行在用户机器上，可编辑文件和执行命令。在此类工具中未公开使用隐写术并不常见，引发了关于伦理和法律界限的讨论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/product/claude-code">Claude Code | Anthropic's agentic coding system</a></li>
<li><a href="https://arxiv.org/abs/2505.03439">[2505.03439] The Steganographic Potentials of Language Models</a></li>

</ul>
</details>

**社区讨论**: 社区意见不一：有人谴责缺乏透明度及可能违反《计算机欺诈与滥用法》，也有人认为其意图（识别中国公司的模型蒸馏）明确且无害。多位评论者批评了其草率的实现，认为存在更巧妙的混淆方法。

**标签**: `#AI`, `#security`, `#steganography`, `#ethics`, `#transparency`

---

<a id="item-4"></a>
## [Claude Science：面向科学研究的 AI 工作台](https://claude.com/product/claude-science) ⭐️ 8.0/10

Anthropic 发布了 Claude Science，这是一款新产品，提供由本地服务器支持的基于 Web 的 UI，用于数据科学和计算研究，并集成了数据库和 HPC 集群。 Claude Science 使研究人员能够在安全环境中使用 AI 处理敏感数据，可能加速科学发现，同时维护数据隐私和可审计性。 与 Claude Code 不同，Claude Science 运行一个带有 Web UI 的本地服务器，适用于制药等封闭环境。它可以生成可审计的产物，并支持连接到机构 HPC 集群。

hackernews · lebovic · 6月30日 17:07 · [社区讨论](https://news.ycombinator.com/item?id=48735770)

**背景**: 高性能计算（HPC）集群是由多台强大计算机组成的并行工作系统，用于解决复杂的计算问题。许多研究机构使用 HPC 进行药物发现和气候建模等任务。Claude Science 连接到这些集群，使研究人员无需移动敏感数据即可利用 AI 进行数据分析和计算。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/news/claude-science-ai-workbench">Claude Science, an AI workbench for scientists \ Anthropic</a></li>
<li><a href="https://claude.com/product/claude-science">Claude Science beta | Claude by Anthropic</a></li>
<li><a href="https://en.wikipedia.org/wiki/High-performance_computing">High-performance computing - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 社区评论总体积极，称赞其适用于安全环境的架构（Web UI 加本地服务器）。一位研究人员测试了其 RNAi 设计功能，发现它生成了合理的初步方案但存在局限性。另一位评论者指出其侧重于数据科学而非更广泛的科学应用场景。

**标签**: `#Claude`, `#Anthropic`, `#data-science`, `#HPC`, `#scientific-computing`

---

<a id="item-5"></a>
## [1100 万篇论文交互地图，支持时间导航](https://www.reddit.com/r/MachineLearning/comments/1ujn3u5/a_map_of_the_latest_11_million_papers_split_by/) ⭐️ 8.0/10

一个新推出的网页工具，利用 SPECTER2 嵌入和 UMAP 降维，将来自 OpenAlex 和 arXiv 的 1100 万篇科学论文投影到二维空间，并支持时间切片和每日更新。 该工具使研究人员能够直观地探索科学文献的宏观趋势并发现相关论文，有助于应对每天海量出版物的跟进难题。 该地图使用 Voronoi 图标记高密度论文区域，支持关键词和语义查询，并包含机构、作者和主题的分析功能。自动摄取脚本确保每日更新。

reddit · r/MachineLearning · /u/icannotchangethename · 6月30日 11:55

**背景**: SPECTER2 是一种先进科学文档嵌入模型，基于 SciBERT 微调，能生成任务特定的嵌入。UMAP 是一种降维技术，能保留数据的局部和全局结构，常用于高维数据可视化。Voronoi 图将空间划分为围绕种子点的区域，这里用于创建围绕密集论文簇的标注区域。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://allenai.org/blog/specter2-adapting-scientific-document-embeddings-to-multiple-fields-and-task-formats-c95686c06567">SPECTER2: Adapting scientific document embeddings to ... - Medium</a></li>
<li><a href="https://umap-learn.readthedocs.io/en/latest/">UMAP: Uniform Manifold Approximation and Projection for ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Voronoi_diagram">Voronoi diagram</a></li>

</ul>
</details>

**标签**: `#scientific literature`, `#embedding`, `#UMAP`, `#visualization`, `#SPECTER2`

---

<a id="item-6"></a>
## [华为开源盘古 2.0，505B 参数，支持 512K 上下文](https://t.me/zaihuapd/42259) ⭐️ 8.0/10

在 2026 年华为开发者大会上，华为宣布开源盘古 2.0 模型，包括 505B 参数的 Pro 版和 92B 参数的 Flash 版，均支持 512K token 的上下文窗口。公司计划从 6 月 30 日起陆续开源预训练代码等七大组件。 此次发布确立了华为在开源大语言模型领域的重要地位，以前所未有的规模和长上下文能力挑战现有领先者。同时，它强化了华为 AI 生态，在美国制裁下减少对外国技术的依赖。 该模型针对华为昇腾 AI 芯片和鸿蒙系统进行了优化。505B Pro 版本是现有最大的开源模型之一，512K 上下文窗口可处理超长文档，如整本书或大型代码库。

telegram · zaihuapd · 6月30日 06:01

**背景**: 华为早在 2021 年就推出了盘古模型系列，早于全球大模型热潮。公司一直在构建包括昇腾芯片在内的全栈 AI 生态，其芯片在美国制裁下已展现出与 Nvidia 产品竞争的性能。开源盘古 2.0 旨在吸引开发者，加速华为 AI 基础设施的采用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://tech-insider.org/huawei-ascend-950pr-ai-chip-nvidia-china-2026/">Huawei Ascend 950PR: The 1.56 PFLOP AI Chip vs Nvidia [2026]</a></li>
<li><a href="https://www.huaweicentral.com/huawei-reveals-3-year-ascend-ai-chip-roadmap-950-coming-in-2026/">Huawei reveals 3-year Ascend AI chip roadmap, 950 coming in ...</a></li>
<li><a href="https://arxiv.org/html/2505.08651v1">Scaling Context, Not Parameters: Training a Compact 7B ...</a></li>

</ul>
</details>

**标签**: `#AI`, `#open-source`, `#Huawei`, `#large language model`

---

<a id="item-7"></a>
## [Anthropic 获美国批准，向关键基础设施部署 Mythos 5 模型](https://t.me/zaihuapd/42260) ⭐️ 8.0/10

2026 年 6 月 27 日，美国政府批准 Anthropic 将其最强网络安全模型 Mythos 5 重新部署给运营和保卫国家关键基础设施的组织。Anthropic 正在迅速为这些组织恢复访问，同时继续与政府谈判以扩大模型的适用范围。 这一决定标志着人工智能治理和国家网络安全领域迈出了重要一步，平衡了强大 AI 防御需求与安全限制之间的关系。它为美国政府未来如何监管和授权高风险 AI 模型用于关键场景树立了先例。 Mythos 5 此前因其在网络安全和生物领域的双重用途风险而受到限制。公众可以访问具有安全防护的版本 Claude Fable 5，该版本会屏蔽高风险领域的查询。

telegram · zaihuapd · 6月30日 07:04

**背景**: Anthropic 开发了具有先进能力的尖端 AI 模型 Mythos 5，但其强大功能引发了滥用担忧。为解决这一问题，Anthropic 还发布了带有防护措施的普通版本 Claude Fable 5。美国政府此前曾暂停 Mythos 5 向关键基础设施的部署，等待安全审查，6 月 27 日的批准是评估后的结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/06/26/us-government-anthropic-claude-mythos5-ai.html">Trump admin allows Anthropic to release Mythos AI model to ...</a></li>
<li><a href="https://www.anthropic.com/claude/mythos">Claude Mythos \ Anthropic</a></li>
<li><a href="https://www.anthropic.com/claude/fable">Claude Fable \ Anthropic</a></li>

</ul>
</details>

**标签**: `#AI governance`, `#cybersecurity`, `#critical infrastructure`, `#Anthropic`, `#US government`

---

<a id="item-8"></a>
## [Claude Code 2.1.91 被指隐蔽遥测检测中国用户](https://www.reddit.com/r/ClaudeAI/comments/1ujila1/anthropic_embedded_spyware_in_claude_code_and/) ⭐️ 8.0/10

一名安全研究人员逆向分析发现，Claude Code 2.1.91 版本中包含经过混淆的遥测代码，会检查系统时区是否为 Asia/Shanghai 或 Asia/Urumqi 以及代理是否指向中国域名，并通过 Unicode 替换将结果编码进 API 提示词，且更新日志未披露。 这一发现对一个广泛使用的 AI 开发工具提出了严重的隐私和透明度问题，可能削弱用户信任并引发监管关注。同时也凸显了反滥用措施与用户隐私之间的紧张关系。 遥测代码使用 XOR 密钥 91 进行混淆，针对中国相关时区（Asia/Shanghai、Asia/Urumqi）和代理 URL，并通过更改系统提示中的日期格式和 Unicode 撇号来编码信息。其目的据称是检测中国地区的未授权转售、账号滥用或模型蒸馏。

telegram · zaihuapd · 6月30日 10:34

**背景**: Claude Code 是由 Anthropic 开发的 AI 编程代理，能够读取代码库并执行命令。遥测通常用于收集使用数据以改进产品，但未经用户同意的隐蔽遥测违反了隐私预期。模型蒸馏是一种通过训练小模型模仿大模型的技术，Anthropic 可能希望防止以保护其知识产权。XOR 密码是一种简单的对称加密方法，常用于混淆。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Claude_Code">Claude Code</a></li>
<li><a href="https://en.wikipedia.org/wiki/XOR_cipher">XOR cipher</a></li>
<li><a href="https://en.wikipedia.org/wiki/Knowledge_distillation">Knowledge distillation - Wikipedia</a></li>

</ul>
</details>

**标签**: `#privacy`, `#telemetry`, `#Claude`, `#AI`, `#ethics`

---

<a id="item-9"></a>
## [英国拟放宽苹果和谷歌应用支付规则](https://www.reuters.com/world/uk-regulator-proposes-easing-apple-google-app-store-payment-rules-2026-06-30/) ⭐️ 8.0/10

英国竞争与市场管理局（CMA）于 6 月 30 日提议，允许应用开发者将用户引导至苹果和谷歌应用商店之外的支付选项，并考虑要求苹果开放其 NFC 技术用于非接触式支付。 这一监管举措可能大幅降低应用商店佣金，增加竞争，并通过赋予开发者更多自由以及降低消费者成本，重塑移动生态系统。 CMA 表示，若苹果或谷歌对引导用户至外部支付的行为收费，该费用必须公平合理且低于现有应用商店佣金，节省的部分应让消费者受益或用于创新。

telegram · zaihuapd · 6月30日 12:12

**背景**: NFC（近场通信）是一种短距离无线技术，可在约 4 厘米或更短距离内实现数据交换，常用于移动支付、门禁和票务。目前，苹果在 iOS 设备上限制 NFC 用于非接触式支付仅限其 Apple Pay 服务，CMA 提议开放此权限。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Near-field_communication">Near-field communication - Wikipedia</a></li>
<li><a href="https://baike.baidu.com/item/近场通信/9741433">近场通信_百度百科 一文详解NFC通信技术 - 知乎专栏 NFC 通信技术：从底层原理到工程实践的全面解析_nfc原理-CSDN博客 NFC（近场通信）技术及其工作原理详解-云社区-华为云 Near-field communication - Wikipedia NFC技术 (一) -基础介绍_nfc工作原理-CSDN博客</a></li>

</ul>
</details>

**标签**: `#反垄断`, `#应用商店`, `#支付`, `#iOS`, `#Android`

---