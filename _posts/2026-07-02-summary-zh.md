---
layout: default
title: "Horizon Summary: 2026-07-02 (ZH)"
date: 2026-07-02
lang: zh
---

> 从 76 条内容中筛选出 13 条重要资讯。

---

1. [Linux 6.9 漏洞导致挂起时未清除 LUKS 加密密钥](#item-1) ⭐️ 8.0/10
2. [F-Droid：安卓开发者验证实为伪装成保护的威胁](#item-2) ⭐️ 8.0/10
3. [日本最高法院：AI 不能列为专利发明人](#item-3) ⭐️ 8.0/10
4. [鸡蛋价格操纵者获利远超罚款](#item-4) ⭐️ 8.0/10
5. [代码审查的首要目标是可维护性](#item-5) ⭐️ 8.0/10
6. [定理经济的衰落](#item-6) ⭐️ 8.0/10
7. [理解才能参与：避免 AI 编码中的认知债务](#item-7) ⭐️ 8.0/10
8. [ECTC 2026 综述：EMIB-T、HBM4、冷却、光子学](#item-8) ⭐️ 8.0/10
9. [北大博士团队创立的中性原子量子公司获数千万融资](#item-9) ⭐️ 8.0/10
10. [快手可灵 AI 获近 30 亿美元融资，创纪录](#item-10) ⭐️ 8.0/10
11. [OpenAI 提议美国政府持股 5%，并考虑纳入其他 AI 巨头](#item-11) ⭐️ 8.0/10
12. [银行和科技公司因成本飙升限制员工 AI 使用](#item-12) ⭐️ 8.0/10
13. [Anthropic 与三星洽谈定制 AI 芯片](#item-13) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Linux 6.9 漏洞导致挂起时未清除 LUKS 加密密钥](https://mathstodon.xyz/@iblech/116769502749142438) ⭐️ 8.0/10

Linux 内核 6.9 版本中的一个回归错误导致 LUKS 挂起操作不再从内存中清除磁盘加密密钥，可能在挂起到 RAM 时暴露加密数据。该漏洞由重构时遗漏了一行 C 语言检查引入。 这是一个严重的安全回归，削弱了挂起期间磁盘加密的保护，尤其影响依赖 Debian 的 cryptsetup-suspend 插件的用户。它凸显了大型 C 代码库的脆弱性以及安全敏感内核代码需要严格测试。 该漏洞在重构期间引入，跨文件遗漏了一行 C 语言检查。Debian 的 cryptsetup-suspend 插件使用 luksSuspend 命令清除密钥，虽然该插件未获内核官方支持，但此回归仍影响受影响发行版的用户。

hackernews · IngoBlechschmid · 7月2日 15:25 · [社区讨论](https://news.ycombinator.com/item?id=48763035)

**背景**: LUKS（Linux 统一密钥设置）是一种磁盘加密规范。当系统挂起到 RAM 时，加密主密钥保留在内存中以便恢复。luksSuspend 命令旨在从内存中清除主密钥，并在唤醒时要求重新输入密码，以防范冷启动攻击。如果不进行清除，密钥仍易受内存提取攻击。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=48763035">Since Linux 6.9, LUKS suspend stopped wiping disk-encryption ...</a></li>
<li><a href="https://manpages.debian.org/unstable/cryptsetup-suspend/cryptsetup-suspend.7.en.html">cryptsetup- suspend (7) — cryptsetup- suspend ... — Debian Manpages</a></li>
<li><a href="https://github.com/Gunpyr/ubuntu-luks-suspend">GitHub - Gunpyr/ubuntu- luks - suspend : Lock encrypted root volume on...</a></li>

</ul>
</details>

**社区讨论**: 社区评论观点不一。一些人认为这是一个严重的安全漏洞，凸显了在 C 代码库中保持不变性正确性的困难。另一些人则淡化其影响，因为 cryptsetup-suspend 未获官方支持，还有少数人指出对普通用户风险较低。有评论者指出该漏洞是通过 NixOS 测试发现的，并赞扬了这种测试方法。

**标签**: `#linux`, `#security`, `#encryption`, `#LUKS`, `#kernel-bug`

---

<a id="item-2"></a>
## [F-Droid：安卓开发者验证实为伪装成保护的威胁](https://f-droid.org/2026/07/01/adv-malware.html) ⭐️ 8.0/10

F-Droid 发布文章，指称谷歌新的安卓开发者验证系统是一种欺骗性威胁，会损害用户自由，并可能用于阻止来自 F-Droid 等替代商店的应用侧载。 这一批评凸显了人们对谷歌控制安卓的日益担忧，尤其是对隐私倡导者和开源爱好者而言，并引发了关于移动操作系统开放性和替代应用分发未来的辩论。 谷歌于 2025 年宣布的开发者验证系统要求所有在 Play Console 和 Android Developer Console 上的开发者进行身份验证，并于 2025 年 10 月启动早期访问计划，对具有敏感权限的应用进行更严格的审查。

hackernews · drewfax · 7月2日 03:00 · [社区讨论](https://news.ycombinator.com/item?id=48755965)

**背景**: F-Droid 是一个面向安卓的自由开源应用商店，优先考虑用户自由和隐私。谷歌 Play 商店长期以来要求开发者注册账户，但新系统将验证扩展到官方商店之外分发的应用，可能会使侧载更加困难，并增强谷歌对安卓生态系统的控制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/F-Droid">F-Droid</a></li>
<li><a href="https://www.androidsage.com/2025/08/26/google-blocks-sideloading-of-android-apps/">It's Over: Google Blocks Sideloading of Android Apps</a></li>
<li><a href="https://f-droid.org/">F-Droid - Free and Open Source Android App Repository</a></li>

</ul>
</details>

**社区讨论**: 评论者表达了不同观点：一些人支持 F-Droid 的立场，并建议使用 SailfishOS 和 Graphene 等替代移动操作系统；另一些人则批评文章的语气幼稚且适得其反，担心这会给谷歌提供忽视 F-Droid 的借口。还有人推测该验证系统针对的是 NewPipe 等广告屏蔽应用。

**标签**: `#Android`, `#F-Droid`, `#privacy`, `#open source`, `#mobile OS`

---

<a id="item-3"></a>
## [日本最高法院：AI 不能列为专利发明人](https://japannews.yomiuri.co.jp/science-nature/technology/20260306-314930/) ⭐️ 8.0/10

2026 年 3 月 6 日，日本最高法院裁定，人工智能不能列为专利申请的发明人，这与美国的政策保持一致。 这一决定在日本确立了法律先例，强化了只有自然人才可成为发明人的原则，影响 AI 产生发明的专利性及 AI 辅助创新的激励。 该裁决与美国专利商标局的立场一致，即 AI 系统不能被列为发明人，但人类发明人若做出重大贡献，可为 AI 辅助的发明申请专利。

hackernews · mushstory · 7月2日 13:43 · [社区讨论](https://news.ycombinator.com/item?id=48761536)

**背景**: 全球专利法传统上要求发明人是自然人，因为只有人类才能拥有法律权利和责任。近期美国专利商标局和日本专利局的指南均明确，AI 可以协助但不得列为发明人。日本的这一案件是生成式 AI 时代知识产权更广泛讨论的一部分。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.congress.gov/crs-product/LSB11251">Artificial Intelligence and Patent Law | Congress.gov | Library of Congress</a></li>
<li><a href="https://www.federalregister.gov/documents/2024/02/13/2024-02623/inventorship-guidance-for-ai-assisted-inventions">Federal Register :: Inventorship Guidance for AI-Assisted Inventions</a></li>

</ul>
</details>

**社区讨论**: 社区评论普遍支持该裁决，认为 AI 缺乏责任能力，不应拥有权益。有人将 AI 比作计算器，也有人质疑 AI 生成的发明是否仍能以人类发明人名义获得专利。

**标签**: `#AI`, `#patents`, `#intellectual property`, `#Japan`, `#law`

---

<a id="item-4"></a>
## [鸡蛋价格操纵者获利远超罚款](https://www.thebignewsletter.com/p/crime-pays-the-egg-bandits-made-a) ⭐️ 8.0/10

鸡蛋生产商合谋操纵价格，获利超过其最终支付罚款的一千倍。 这突显了反垄断执法中的严重威慑不足，使企业将罚款视为经营成本，破坏了市场竞争。 在鸡蛋价格危机期间，媒体归咎于禽流感和通货膨胀，但价格操纵操作是主要原因；相比非法收益，支付的罚款微不足道。

hackernews · toomuchtodo · 7月2日 13:25 · [社区讨论](https://news.ycombinator.com/item?id=48761229)

**背景**: 价格操纵是竞争者之间为抬高价格而达成的非法协议，这会减少竞争并损害消费者利益。反垄断法旨在防止此类共谋，但罚款往往过低，无法威慑大型企业。

**社区讨论**: 评论者震惊地发现鸡蛋危机源于价格操纵，而非通胀或禽流感。有人指出市场集中度使这种共谋成为可能，并主张加强惩罚，如追究企业责任，甚至对白领犯罪实施体罚。

**标签**: `#price fixing`, `#antitrust`, `#corporate crime`, `#economics`, `#market concentration`

---

<a id="item-5"></a>
## [代码审查的首要目标是可维护性](https://mathstodon.xyz/@mjd/115096720350507897) ⭐️ 8.0/10

一篇热门帖子认为，代码审查的首要目的是找出难以维护的代码，这引发了多方面的社区讨论。 这场辩论重新定义了团队进行代码审查的方式，强调可维护性而非仅关注缺陷检测，并影响软件工程的最佳实践。 该帖子发布在 Mathstodon 上，获得了 237 个赞和 126 条评论，表明开发者社区对此高度关注。

hackernews · ColinWright · 7月2日 11:41 · [社区讨论](https://news.ycombinator.com/item?id=48759870)

**背景**: 代码审查是一种软件工程实践，开发者在合并代码前相互检查变更。传统上，它旨在发现缺陷并提高代码质量。该帖子挑战了这种观点，将长期可维护性置于即时正确性之上。

**社区讨论**: 社区评论强烈反对将可维护性视为唯一首要目标。评论者强调其他目的，如知识传递、防止恶意代码的安全检查、团队所有权以及通过代码异味发现缺陷。有评论者指责该帖子是为懒惰审查找借口。

**标签**: `#code review`, `#software engineering`, `#maintainability`, `#best practices`, `#team collaboration`

---

<a id="item-6"></a>
## [定理经济的衰落](https://davidbessis.substack.com/p/the-fall-of-the-theorem-economy) ⭐️ 8.0/10

David Bessis 的一篇文章指出，数学正从以定理为中心的经济转向计算和 AI 驱动的方法，并与 Greg Egan 的小说《Diaspora》中的概念相呼应。 这一转变可能重新定义数学家的角色和同行评审过程，可能加速发现，但也引发了对数学真理本质和社区验证的质疑。 文章指出，随着证明助手和 AI 系统能力的增强，传统上以证明定理为重点的做法可能会减少，类似于 Egan 的“真理挖掘”概念，即通过直觉和可视化探索形式化知识的庞大数据库。

hackernews · varjag · 7月2日 08:01 · [社区讨论](https://news.ycombinator.com/item?id=48758048)

**背景**: 几个世纪以来，定理证明一直是数学的核心，但近期自动定理证明和形式化方法（由计算机验证证明）的进展正在改变这一格局。Greg Egan 1997 年的小说《Diaspora》设想了一个后人类未来，其中数学在完全形式化的系统中演变为“真理挖掘”。文章认为我们现在正接近这一现实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Automated_theorem_proving">Automated theorem proving</a></li>
<li><a href="https://en.wikipedia.org/wiki/Diaspora_(novel)">Diaspora (novel) - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Formal_methods">Formal methods - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍认同这一观点，其中一位指出 Egan 的“真理挖掘”精准描述了完全形式化后的数学。另一位评论者认为数学更像软件工程中的测试和积累信心，而非严谨证明。也有人讨论私人 AI 资源可能导致开放科学的减少。

**标签**: `#mathematics`, `#theorem proving`, `#AI`, `#formal methods`, `#mathematical culture`

---

<a id="item-7"></a>
## [理解才能参与：避免 AI 编码中的认知债务](https://simonwillison.net/2026/Jul/2/understand-to-participate/#atom-everything) ⭐️ 8.0/10

在 2026 年 AI 工程师世界博览会上，Geoffrey Litt 提出了“理解才能参与”的概念，认为开发者必须保持对代码的深刻理解，才能有效协作 AI 编码智能体，避免累积认知债务。 这一见解至关重要，因为随着 AI 编码智能体变得越来越复杂，开发者可能面临失去对自身代码理解的风险，这会阻碍创造性参与并增加认知债务。它凸显了软件工程界在充分利用 AI 辅助开发时必须应对的实际挑战。 该演讲是 AIE 录制 300 多场会议之一，Geoffrey 还在 Twitter 上发布了一个主题总结他的论点。认知债务是一个日益受到关注的术语，指为了快速推进而不理解代码为何工作的心理成本，类似于技术债务但存在于开发者的大脑中。

rss · Simon Willison · 7月2日 17:07

**背景**: 认知债务是一个相对较新的概念，描述了开发者在 AI 辅助编码中优先速度而非理解时所承受的心理负担，尤其是当智能体可能生成大量代码变更时。为避免认知债务，开发者必须主动从智能体的输出中学习，并保持对代码库的丰富心智模型，从而创造性参与，而非被动接受或拒绝建议。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://medium.com/@willsh/what-is-cognitive-debt-5182e4a4fa98">What is Cognitive Debt? - Medium</a></li>
<li><a href="https://margaretstorey.com/blog/2026/02/09/cognitive-debt/">How Generative and Agentic AI Shift Concern from Technical Debt to ...</a></li>

</ul>
</details>

**标签**: `#AI coding agents`, `#cognitive debt`, `#software engineering`, `#LLM collaboration`

---

<a id="item-8"></a>
## [ECTC 2026 综述：EMIB-T、HBM4、冷却、光子学](https://newsletter.semianalysis.com/p/ectc2026) ⭐️ 8.0/10

ECTC 2026 会议重点介绍了 Intel 的 EMIB-T 封装技术进入量产、定制 HBM 和 HBM4（带宽 2.8 TB/s）的路线图、微流体冷却突破以及 Lightmatter 等公司的光子互连技术。 这些进步对于下一代 AI 加速器和高性能计算至关重要，解决了限制扩展的功率传输、热管理和带宽瓶颈。 Intel 的 EMIB-T 在桥接器中增加了硅通孔（TSV）以改善功率传输，并支持 HBM4。HBM4 采用 2048 引脚接口，速度>11 Gbps，每堆栈带宽>2.8 TB/s。微流体冷却采用在硅中蚀刻的通道，散热效果提升高达 3 倍。

rss · Semianalysis · 7月2日 17:25

**背景**: 先进封装技术如 EMIB（嵌入式多芯片互连桥接）和 CoWoS 用于在单个封装中集成多个芯片（例如逻辑和 HBM）。HBM（高带宽内存）是一种通过硅通孔堆叠的 DRAM，用于 AI 加速器。微流体冷却通过芯片上的微小通道循环冷却液来管理热量。光子互连使用光进行更快、更低功耗的数据传输。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tomshardware.com/pc-components/cpus/intel-details-new-advanced-packaging-breakthroughs-emib-t-paves-the-way-for-hbm4-and-increased-ucie-bandwidth">Intel details new advanced packaging breakthroughs — EMIB-T paves the way for HBM4 and increased UCIe bandwidth | Tom's Hardware</a></li>
<li><a href="https://www.tomshardware.com/tech-industry/semiconductors/intels-emib-t-heads-for-fab-rollout-this-year">Intel's EMIB-T packaging technology set for fab rollout this year — as TSMC CoWoS capacity remains limited, EMIB-T is preparing for advanced AI accelerator designs | Tom's Hardware</a></li>
<li><a href="https://news.microsoft.com/source/features/innovation/microfluidics-liquid-cooling-ai-chips/">AI chips are getting hotter. A microfluidics breakthrough goes straight to the silicon to cool up to three times better. - Source</a></li>

</ul>
</details>

**标签**: `#semiconductor packaging`, `#HBM`, `#microfluidic cooling`, `#photonic interconnects`, `#advanced packaging`

---

<a id="item-9"></a>
## [北大博士团队创立的中性原子量子公司获数千万融资](https://36kr.com/p/3877814169530630?f=rss) ⭐️ 8.0/10

中国初创公司纳开启元（纳开量子）由北京大学博士团队创立，宣布完成由高瓴创投领投的数千万人民币种子轮融资，用于推进其纳开温区中性原子量子计算平台。 此轮融资凸显了中性原子量子计算在中国日益重要的地位，该路线以可扩展性和量子比特一致性著称，并表明冷原子技术正从实验室走向商业可行。 纳开量子声称是国内唯一能将铷、钾、铯等九种原子工程化冷却至 10 纳开尔文以下的团队。公司拥有包括量子模拟计算机在内的全栈产品线，预计 2026 年营收达数千万元。

rss · 36氪 · 7月2日 01:16

**背景**: 中性原子量子计算机使用激光冷却的原子作为量子比特，具有天然的一致性和可扩展性。纳开尔文温度是比绝对零度高十亿分之一度的温区，热噪声极低。该领域在 2023 年哈佛与 QuEra 展示可编程中性原子处理器后加速发展。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Neutral_atom_quantum_computer">Neutral atom quantum computer - Wikipedia</a></li>
<li><a href="https://www.quera.com/neutral-atom-platform">Building Quantum Computers with Neutral Atoms | QuEra</a></li>
<li><a href="https://en.wikipedia.org/wiki/Nanokelvin">Nanokelvin</a></li>

</ul>
</details>

**标签**: `#quantum computing`, `#neutral atom`, `#startup funding`, `#cold atom`, `#China`

---

<a id="item-10"></a>
## [快手可灵 AI 获近 30 亿美元融资，创纪录](https://36kr.com/newsflashes/3878648324845831?f=rss) ⭐️ 8.0/10

2025 年 7 月 2 日，快手旗下视频生成大模型可灵 AI 完成近 30 亿美元融资，投后估值达 180 亿美元，创下全球视频生成 AI 公司最大融资纪录。 本轮融资显示了 AI 视频生成领域的强劲商业势头和投资者信心，标志着可灵 AI 独立商业化发展的正式开启。顶级科技与传媒投资者的参与凸显了其行业影响力。 本轮融资由 CPE 源峰、国方创投、BlueFive、腾讯、中关村科学城基金（联合国科投资）、中信证券联合领投，阿里云、百度等顶级产业资本，以及华策影视、芒果产业投资人（厚为资本）等头部文娱产业方积极参与。

rss · 36氪 · 7月2日 15:25

**背景**: 可灵 AI 是快手（中国大型科技公司）开发的视频生成大模型，能够根据文本或图片生成视频。2025 年 4 月，快手发布了可灵 2.0 版本，性能有显著提升。视频生成 AI 是一个快速增长领域，竞争对手包括 OpenAI 的 Sora 和 Runway 等。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://zenn.dev/taku_sid/articles/20250416_kelings_ai?locale=en">A Simple Guide to Keling 2.0: China’s Latest AI Video ...</a></li>
<li><a href="https://llm-stats.com/leaderboards/best-ai-for-video-generation">Best AI for Video Generation in 2026 — Ranked by Blind Human ...</a></li>

</ul>
</details>

**标签**: `#Video Generation AI`, `#Funding`, `#Kuaishou`, `#Large Models`, `#AI Industry`

---

<a id="item-11"></a>
## [OpenAI 提议美国政府持股 5%，并考虑纳入其他 AI 巨头](https://www.bloomberg.com/news/articles/2026-07-02/openai-proposes-giving-the-us-government-a-5-stake-ft-says) ⭐️ 8.0/10

OpenAI 提议美国政府持有该公司 5%的股份，并可能类似地持有谷歌和 Meta 等其他主要 AI 公司的股份，以便公众分享 AI 发展的收益。 该提议可能通过让政府直接参与利润分享来重塑 AI 治理格局，引发关于控制和利益冲突的讨论，并为公众如何从 AI 中获益树立先例。 该计划涉及由一个政府载体统一持有 OpenAI、Anthropic、谷歌和 Meta 各 5%的股份。其他公司尚未表示接受，监管和利益冲突问题仍未解决。

telegram · zaihuapd · 7月2日 06:02

**背景**: OpenAI 是一家领先的人工智能研究和部署公司，以 GPT-4 等模型闻名。Anthropic 由前 OpenAI 员工创立，专注于 AI 安全并开发 Claude。该提议旨在通过政府持股将 AI 的经济收益分配给公众。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Anthropic">Anthropic - Wikipedia</a></li>

</ul>
</details>

**标签**: `#AI`, `#OpenAI`, `#government stake`, `#policy`, `#tech giants`

---

<a id="item-12"></a>
## [银行和科技公司因成本飙升限制员工 AI 使用](https://www.404media.co/companies-are-throttling-employees-ai-use-because-its-too-expensive/) ⭐️ 8.0/10

花旗银行于 2026 年 6 月 24 日禁用了 GPT-5.5、Claude Opus 4.6 和 4.7，理由是这些模型消耗大量 AI 积分；而 Atlassian 的月度 AI 支出从 2025 年 8 月的 500 万美元飙升至 2026 年 5 月的逾 1500 万美元，促使公司设置使用上限并推出成本追踪面板。 这一趋势表明，先进 AI 模型的按用量计费模式正在给企业带来不可持续的成本，可能减缓 AI 采用步伐，迫使企业在创新与成本控制之间做出取舍。 Atlassian 的内部仪表板显示 AI 支出在约 9 个月内增长了 3 倍；Adobe 决定不再续签无限的 Claude 使用合同；Amazon 此前关闭了鼓励 AI 使用的内部排行榜，并暴露出此前未知的 token 使用上限。

telegram · zaihuapd · 7月2日 13:59

**背景**: 许多 AI 工具（包括 GPT-5.5 和 Claude Opus 模型）采用按使用量计费模式，客户按 token 付费或消耗 AI 积分。这些积分相当于预付费的消费单位，越强大的模型每次请求消耗的积分越多。如果没有适当的管理，企业支出会随着员工广泛使用而急剧膨胀。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/GPT-5.5">GPT-5.5</a></li>
<li><a href="https://schematichq.com/blog/ai-credits">AI Credits: How They Work, Pricing Models, and Implementation</a></li>
<li><a href="https://arstechnica.com/ai/2026/06/ai-costs-how-much-github-copilot-users-react-to-new-usage-based-pricing-system/">AI costs how much? GitHub Copilot users react to new usage-based pricing system. - Ars Technica</a></li>

</ul>
</details>

**标签**: `#AI costs`, `#enterprise AI`, `#AI adoption`, `#cost management`, `#industry trend`

---

<a id="item-13"></a>
## [Anthropic 与三星洽谈定制 AI 芯片](https://www.theinformation.com/articles/anthropic-talks-samsung-manufacture-custom-ai-chip) ⭐️ 8.0/10

Anthropic 已开始自研 AI 芯片，并与三星电子就潜在代工合作进行早期洽谈，旨在减少对 Claude 模型外部芯片供应商的依赖。 此举表明领先 AI 公司正推进垂直整合，通过定制硬件优化模型并保障供应链。若成功，可能加剧与 OpenAI 定制芯片的竞争，重塑 AI 半导体格局。 Anthropic 的芯片项目仍处于早期开发阶段，相比 OpenAI 等对手入场较晚——OpenAI 已与 Broadcom 合作推出 Jalapeño 推理芯片。三星代工业务提供定制芯片的设计与制造服务。

telegram · zaihuapd · 7月2日 15:57

**背景**: OpenAI 和 Anthropic 等主要 AI 公司正越来越多地开发定制芯片，以更好地满足大型语言模型的计算需求，减少对通用 GPU 的依赖。OpenAI 于 2026 年 6 月发布的 Jalapeño 芯片是专为推理设计的芯片，由 Broadcom 制造。三星代工厂是少数能够生产此类先进芯片的制造商之一。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/openai-broadcom-jalapeno-inference-chip/">OpenAI and Broadcom unveil LLM-optimized inference chip</a></li>
<li><a href="https://semiconductor.samsung.com/foundry/">Foundry Overview | Samsung Semiconductor Global</a></li>

</ul>
</details>

**标签**: `#Anthropic`, `#AI chips`, `#Samsung`, `#semiconductor`, `#custom silicon`

---