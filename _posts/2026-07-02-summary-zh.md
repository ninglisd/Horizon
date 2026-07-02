---
layout: default
title: "Horizon Summary: 2026-07-02 (ZH)"
date: 2026-07-02
lang: zh
---

> 从 77 条内容中筛选出 13 条重要资讯。

---

1. [Linux 6.9 回归：LUKS 挂起未清除加密密钥](#item-1) ⭐️ 8.0/10
2. [F-Droid：安卓开发者验证是一匹特洛伊木马](#item-2) ⭐️ 8.0/10
3. [PeerTube：去中心化视频平台替代方案](#item-3) ⭐️ 8.0/10
4. [定理经济的衰落](#item-4) ⭐️ 8.0/10
5. [ECTC 2026：EMIB-T、定制 HBM、冷却与光子互连](#item-5) ⭐️ 8.0/10
6. [北大博士团队获数千万融资，打造纳开温区中性原子量子计算机](#item-6) ⭐️ 8.0/10
7. [美图 CEO 谈 AI 产品战略与全球扩张驱动营收增长](#item-7) ⭐️ 8.0/10
8. [快手可灵 AI 融资近 30 亿美元创纪录](#item-8) ⭐️ 8.0/10
9. [苹果协助 FBI 揭露 iCloud 匿名邮箱用户身份](#item-9) ⭐️ 8.0/10
10. [云服务商 Cloudflare 将于 9 月起拦截混合用途 AI 爬虫](#item-10) ⭐️ 8.0/10
11. [OpenAI 提议美国政府持股 5%，可能纳入 Google 和 Meta](#item-11) ⭐️ 8.0/10
12. [花旗禁用 GPT-5.5，企业因 AI 成本飙升限制使用](#item-12) ⭐️ 8.0/10
13. [PS3 商店 2027 年关闭：档案员紧急抢救游戏](#item-13) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Linux 6.9 回归：LUKS 挂起未清除加密密钥](https://mathstodon.xyz/@iblech/116769502749142438) ⭐️ 8.0/10

Linux 内核版本 6.9 引入的一个回归导致 `cryptsetup luksSuspend` 命令不再从内核内存中清除磁盘加密密钥，使得密钥在系统挂起期间可能被访问。 此回归在系统挂起时将加密密钥留在内存中，暴露给冷启动攻击或其他内存提取技术，从而削弱了 LUKS 加密系统的安全性。它影响了依赖 `luksSuspend` 在休眠或挂起期间保护数据的用户。 该漏洞在 NixOS 上被发现，据信自 Linux 6.9 以来就已存在，但由于系统仍然看似正常运行，可能未被注意到。`luksSuspend` 命令并非 Linux 官方部分，而是 Debian 的一个扩展，但已被广泛采用。

hackernews · IngoBlechschmid · 7月2日 15:25 · [社区讨论](https://news.ycombinator.com/item?id=48763035)

**背景**: LUKS（Linux 统一密钥设置）是一种磁盘加密规范。使用 dm-crypt 和 LUKS 时，加密密钥在系统运行期间保留在内核内存中。`cryptsetup luksSuspend` 命令用于通过从内存中清除密钥并阻止 I/O 来挂起 LUKS 设备，恢复时需要重新输入密码短语。这防止了密钥在休眠或挂起期间存在于内存中。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/vianney/arch-luks-suspend">GitHub - vianney/arch-luks-suspend: Lock encrypted root volume on suspend in Arch Linux · GitHub</a></li>
<li><a href="https://en.wikipedia.org/wiki/Linux_Unified_Key_Setup">Linux Unified Key Setup - Wikipedia</a></li>
<li><a href="https://www.reddit.com/r/archlinux/comments/hpd4hh/suspend_with_luks/">r/archlinux on Reddit: Suspend with LUKS</a></li>

</ul>
</details>

**社区讨论**: 评论者指出，这种回归可能容易被忽视，因为从功能角度看一切仍然“正常”。有些人认为该功能并非官方支持，而是 Debian 的扩展，因此指责内核可能不公平。还有人指出，对于挂起到 RAM，加密密钥预期会留在内存中，因此此漏洞仅对需要清除密钥的特定用例有影响。

**标签**: `#linux`, `#security`, `#disk-encryption`, `#kernel`, `#luks`

---

<a id="item-2"></a>
## [F-Droid：安卓开发者验证是一匹特洛伊木马](https://f-droid.org/2026/07/01/adv-malware.html) ⭐️ 8.0/10

2026 年 7 月 1 日，F-Droid 发布文章，谴责谷歌新的安卓开发者验证政策是对侧载和开放性的威胁，尤其影响 F-Droid 用户。 该政策可能有效控制 Google Play 之外可安装的应用，破坏安卓开放性的核心承诺，并可能损害整个自由开源软件生态系统。 谷歌的开发者验证将于 2026 年 9 月开始推出，要求开发者完成身份验证才能在安卓上分发应用，包括通过侧载方式。

hackernews · drewfax · 7月2日 03:00 · [社区讨论](https://news.ycombinator.com/item?id=48755965)

**背景**: 安卓开发者验证是谷歌的一项新安全措施，通过验证开发者身份来阻止恶意行为者。F-Droid 是一个流行的自由开源应用仓库，依赖侧载分发应用。批评者认为该验证可能被用来阻止或限制未经谷歌批准的应用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/F-Droid">F-Droid</a></li>
<li><a href="https://docs.getupdraft.com/android/android-developer-verification">Android Developer Verification | App Distribution for iOS, Android ...</a></li>

</ul>
</details>

**社区讨论**: 评论显示强烈反对，建议转向替代的移动 Linux 系统，如 SailfishOS、Ubuntu Touch 或 Graphene。有人批评 F-Droid 的文章过于夸张，而其他人则认为这是对谷歌日益增强的控制的有效警告。

**标签**: `#Android`, `#F-Droid`, `#privacy`, `#security`, `#open-source`

---

<a id="item-3"></a>
## [PeerTube：去中心化视频平台替代方案](https://github.com/Chocobozzz/PeerTube) ⭐️ 8.0/10

PeerTube 是一个自由、去中心化且联邦化的视频平台，允许用户在不依赖 YouTube 等集中式商业服务的情况下托管视频。它使用 ActivityPub 实现联邦，并利用 WebTorrent 进行点对点流媒体传输。 PeerTube 提供了一种尊重隐私的集中式平台替代方案，让内容创作者和观众对数据有更多控制权，减少对企业服务器的依赖。它支持更广泛的联邦宇宙（fediverse）生态系统，推动去中心化网络的发展。 每个 PeerTube 实例独立运行，并通过 ActivityPub 与其他实例联邦，实现跨实例的视频发现。该平台还使用点对点技术来减少热门视频期间的服务器负载。

hackernews · doener · 7月2日 11:17 · [社区讨论](https://news.ycombinator.com/item?id=48759634)

**背景**: 像 YouTube 这样的传统视频平台将数据和控制集中化，引发了隐私、审查和货币化方面的担忧。PeerTube 采用的联邦化允许不同服务器在保持独立的同时进行通信，类似于电子邮件的工作方式。ActivityPub 是实现这种互操作性的 W3C 标准协议，而 WebTorrent 允许浏览器参与点对点文件共享。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/PeerTube">PeerTube - Wikipedia</a></li>
<li><a href="https://github.com/Chocobozzz/PeerTube">GitHub - Chocobozzz/PeerTube: ActivityPub-federated video streaming platform using P2P directly in your web browser · GitHub</a></li>
<li><a href="https://joinpeertube.org/">What is PeerTube? | JoinPeerTube</a></li>

</ul>
</details>

**社区讨论**: 社区评论中，有专业 YouTuber 对缺乏货币化表示担忧，指出视频制作成本高昂。其他人则称赞隐私和开源特性，但也指出缺乏内容和观众，使得采用面临挑战。一些用户成功将 PeerTube 用于开源教程，从现有实例嵌入视频。

**标签**: `#decentralization`, `#video platform`, `#federation`, `#open source`

---

<a id="item-4"></a>
## [定理经济的衰落](https://davidbessis.substack.com/p/the-fall-of-the-theorem-economy) ⭐️ 8.0/10

文章认为，以定理证明为核心的数学时代正在终结，形式化和自动化将重点转向直觉和可视化，类似于软件测试。 这一转变可能改变数学的实践方式，使其更具协作性和可及性，同时挑战传统数学证明和严谨性的观念。 文章将形式化数学与软件测试进行了类比，并引用格雷格·伊根的小说《离散》中设想的数学成为借助证明助手进行的“真理挖掘”。

hackernews · varjag · 7月2日 08:01 · [社区讨论](https://news.ycombinator.com/item?id=48758048)

**背景**: 证明助手是一种交互式软件工具，帮助人类构建和验证形式证明。数学形式化涉及将数学陈述转化为可由计算机检查的精确符号语言。这些工具已成熟到可以处理复杂数学的程度，导致一些人认为它们将改变数学工作的本质。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Proof_assistant">Proof assistant</a></li>
<li><a href="https://plus.maths.org/proof-assistants-part-1">Proof assistants | plus.maths.org</a></li>
<li><a href="https://en.wikipedia.org/wiki/Mathematical_formalization">Mathematical formalization</a></li>

</ul>
</details>

**社区讨论**: 评论者指出格雷格·伊根的小说《离散》中对“真理挖掘”的预见性描述，认为这是形式化后数学的愿景。其他人则将其与软件测试类比，认为数学的本质一直是洞察而非严格证明。一个相关担忧是私人对 AI 资源的掌控可能限制开放科学。

**标签**: `#mathematics`, `#formalization`, `#proof assistants`, `#software testing`, `#epistemology`

---

<a id="item-5"></a>
## [ECTC 2026：EMIB-T、定制 HBM、冷却与光子互连](https://newsletter.semianalysis.com/p/ectc2026) ⭐️ 8.0/10

在 ECTC 2026 上，英特尔推出了具有厚垂直铜连接和更细间距的 EMIB-T 封装，微软则展示了直接在芯片上集成的微流体冷却技术。会议还涵盖了定制 HBM、HBM4 封装挑战以及来自 Lightmatter 的光子互连。 这些进展解决了芯片封装、冷却和互连中的关键扩展瓶颈，对 AI/ML 硬件和高性能计算的性能与效率至关重要。 英特尔的 EMIB-T 支持低于 45μm 的间距，目标达到 35μm；微软的微流体冷却在活动 CMOS 器件上实现了最高功率密度，且无需蒸发用水。

rss · Semianalysis · 7月2日 17:25

**背景**: 先进封装技术如英特尔的 EMIB（嵌入式多芯片互连桥）可实现芯片间的高密度连接。微流体冷却通过直接在芯片上微通道循环冷却液来高效散热。光子互连使用光而非电信号进行更快、更低功耗的数据传输。HBM（高带宽内存）将 DRAM 芯粒与逻辑基底堆叠，提供宽内存带宽。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://spectrum.ieee.org/intel-advanced-packaging-for-ai">Intel Advanced Packaging for Bigger AI Chips - IEEE Spectrum</a></li>
<li><a href="https://datacenters.microsoft.com/wp-content/uploads/2025/09/Microfluidic-Cooling-Infographic.pdf">Microfluidics cooling: Cooling at the micro level for Microsoft’s datacenters</a></li>
<li><a href="https://www.linkedin.com/pulse/future-computing-photonic-interconnects-semiconductor-elxie">The Future of Computing : Photonic Interconnects and...</a></li>

</ul>
</details>

**标签**: `#packaging`, `#interconnects`, `#cooling`, `#HBM`, `#ECTC`

---

<a id="item-6"></a>
## [北大博士团队获数千万融资，打造纳开温区中性原子量子计算机](https://36kr.com/p/3877814169530630?f=rss) ⭐️ 8.0/10

由中国北京大学博士团队创立的纳开启元量子科技公司完成首轮数千万元融资，由高瓴创投领投。公司专注于纳开温区中性原子量子计算机的研发，声称是国内唯一能将多种原子冷却至 10nK 以下并实现工程化的团队。 此轮融资表明市场对中性原子量子计算路线的兴趣日益增长，该路线在可扩展性方面具有优势。纳开量子的进展有望加速中国在全球量子竞赛中的地位，并推动实用化量子计算在工业中的应用。 纳开量子成立于 2026 年 4 月，已获得千万级市场订单，预计 2026 年全年营收达数千万元。其核心技术包括将铷、钾、铯等九种元素的原子冷却至 10nK 以下，并采用先进的光晶格技术实现高精度操控。

rss · 36氪 · 7月2日 01:16

**背景**: 中性原子量子计算机利用激光囚禁的中性原子来编码量子比特，具有天然全同性和高可扩展性。与超导量子比特不同，它不需要大量低温冷却，但实现高保真度和长相干时间仍有挑战。纳开温（纳开尔文）是极低温度（接近绝对零度），可抑制热运动以增强量子效应。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Neutral_atom_quantum_computer">Neutral atom quantum computer</a></li>
<li><a href="https://www.quera.com/neutral-atom-platform">Building Quantum Computers with Neutral Atoms | QuEra</a></li>

</ul>
</details>

**标签**: `#quantum computing`, `#neutral atom`, `#startup`, `#funding`, `#China`

---

<a id="item-7"></a>
## [美图 CEO 谈 AI 产品战略与全球扩张驱动营收增长](https://36kr.com/p/3877112973733895?f=rss) ⭐️ 8.0/10

美图 CEO 吴欣鸿在专访中透露，AI 驱动的产品收入占比已从一年前的 35%提升至 76.6%，海外月活跃用户重回 1 亿。公司还设立了快速孵化工作室和严格的产品市场适配标准，例如上线半年内 ARR 需达到 10 万美元。 这展示了美图从挣扎中的修图应用向 AI 驱动影像领军者的成功转型，提供了可复制的全球扩张和快速产品迭代范本。其洞察对正在探索 AI 变现和国际化的科技公司尤为有价值。 Picchi 和 MeituHub 等新产品是从用户行为洞察中“自然生长”出来的，而 MVLAND 和 Artflo 则是 CEO 的个人热爱项目。美图执行严格的产品开发时间线：从立项到市场验证控制在 1 个月内，PMF 标准为 6 个月内 ARR 达到 10 万美元。

rss · 36氪 · 7月2日 00:30

**背景**: 美图以其修图应用“美图秀秀”闻名，多年因依赖广告而挣扎于盈利。AI 浪潮和订阅模式转型使其得以用 Wink（视频编辑）和 RoboNeo（AI 创意助手）等 AI 工具重建产品线，瞄准全球市场。公司现在设立小型创新工作室，提供最高 1000 万元资金用于快速孵化 AI 产品。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.roboneo.com/">AI Social Media Creation Agent for Scalable Video Production & Trend-Driven Content</a></li>
<li><a href="https://wink.ai/">Wink AI - Video and Image Enhancer & Editor for All Scenes</a></li>

</ul>
</details>

**标签**: `#AI`, `#technology strategy`, `#business transformation`, `#Meitu`, `#product development`

---

<a id="item-8"></a>
## [快手可灵 AI 融资近 30 亿美元创纪录](https://36kr.com/newsflashes/3878648324845831?f=rss) ⭐️ 8.0/10

2025 年 7 月 2 日，快手旗下视频生成大模型可灵 AI 完成近 30 亿美元融资，创下全球视频大模型公司单轮融资规模新纪录。 此次创纪录融资验证了 AI 视频生成的商业潜力，标志着可灵 AI 开启独立商业化进程，反映了投资者对视频类生成式 AI 的强烈信心。 本轮融资由 CPE 源峰、国方创投、BlueFive、腾讯、中关村科学城基金（联合国科投资）和中信证券联合领投，阿里云、百度等顶级产业资本以及华策影视、芒果产业投资人（厚为资本）等多家文娱机构参与。

rss · 36氪 · 7月2日 15:25

**背景**: 可灵 AI 是快手开发的先进视频生成模型，能够根据文本提示生成专业视频和图像。AI 视频生成市场近年来爆发式增长，OpenAI 的 Sora 等公司也在这一领域竞争。本轮融资反映了训练和部署大规模视频模型所需的巨额资本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://app.klingai.com/cn/ai-video/cute-kitten-cuddle-request/287913723146798">可 灵 AI - 新一代 AI 创意生产力平台</a></li>
<li><a href="https://itopmarketing.com/info20490">AI 版“爱死机”刷屏！ 我用它背后的 可 灵 AI ...</a></li>

</ul>
</details>

**标签**: `#AI video generation`, `#funding`, `#Kuaishou`, `#generative AI`, `#venture capital`

---

<a id="item-9"></a>
## [苹果协助 FBI 揭露 iCloud 匿名邮箱用户身份](https://t.me/zaihuapd/42302) ⭐️ 8.0/10

苹果向 FBI 提供了与“隐藏邮箱地址”别名关联的真实 iCloud 账户信息，该别名被用于发送威胁邮件，从而识别出 Alden Ruml，他承认威胁了 FBI 局长 Kash Patel 的女友。 此案表明苹果的“隐藏邮箱地址”功能在刑事调查中并不能保证匿名性，引发了依赖该功能保护隐私的用户重大担忧。 用户 Alden Ruml 通过 iCloud+功能生成了 134 个匿名邮箱地址，其真实身份通过一份宣誓书被披露，他在书中承认发送了威胁邮件。

telegram · zaihuapd · 7月2日 01:03

**背景**: 苹果的“隐藏邮箱地址”是 iCloud+中的一项隐私功能，允许用户创建唯一、随机的邮箱地址，将邮件转发到真实收件箱而不暴露真实地址。虽然旨在保护隐私，但苹果保留将这些匿名地址与用户实际账户关联的能力，通常仅在类似 FBI 调查这样的合法请求下才会披露。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://support.apple.com/en-us/105078">How to use Hide My Email with Sign in with Apple - Apple Support</a></li>
<li><a href="https://clean.email/have-you-been-pwned/hide-my-email">Use Apple Hide My Email To Protect Your Inbox</a></li>

</ul>
</details>

**标签**: `#privacy`, `#Apple`, `#FBI`, `#anonymous email`, `#security`

---

<a id="item-10"></a>
## [云服务商 Cloudflare 将于 9 月起拦截混合用途 AI 爬虫](https://techcrunch.com/2026/07/01/cloudflares-new-policy-pushes-ai-companies-to-pay-for-publishers-content/) ⭐️ 8.0/10

自 2026 年 9 月 15 日起，Cloudflare 将默认阻止那些同时用于搜索索引和 AI 训练的混合用途爬虫抓取带广告的客户页面。 该政策迫使 Google 等 AI 公司将其搜索爬虫与 AI 训练爬虫分离，可能要求它们为用于 AI 模型的内容付费，保护出版商的版权。 Cloudflare 特别指出，Google 的双用途爬虫利用了一个漏洞：网站通常阻止 AI 爬虫但允许 Googlebot 搜索，而 Google 会借此进行 AI 训练。

telegram · zaihuapd · 7月2日 05:37

**背景**: 许多网站依赖广告收入，希望阻止 AI 公司免费使用其内容。Cloudflare 作为主流 CDN 和安全服务商，可为数百万网站设置默认规则。混合用途爬虫是指同时为搜索结果和 AI 模型训练收集数据的机器人。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcrunch.com/2026/07/01/cloudflares-new-policy-pushes-ai-companies-to-pay-for-publishers-content/">Cloudflare's new policy pushes AI companies to pay for publishers' content | TechCrunch</a></li>
<li><a href="https://www.theregister.com/ai-and-ml/2026/07/01/cloudflare-to-block-cynical-search-and-scrape-bots-from-ad-supported-web-pages/5264727">Cloudflare to block cynical search-and-scrape bots from ad-supported web pages</a></li>
<li><a href="https://blog.cloudflare.com/control-content-use-for-ai-training/">Control content use for AI training with Cloudflare’s managed robots.txt and blocking for monetized content</a></li>

</ul>
</details>

**社区讨论**: 来源中提到，许多网站阻止了 AI 爬虫但未阻止 Google 搜索，使得 Google 利用这一漏洞进行 AI 训练。

**标签**: `#Cloudflare`, `#AI crawlers`, `#web scraping`, `#content policy`, `#Google`

---

<a id="item-11"></a>
## [OpenAI 提议美国政府持股 5%，可能纳入 Google 和 Meta](https://www.bloomberg.com/news/articles/2026-07-02/openai-proposes-giving-the-us-government-a-5-stake-ft-says) ⭐️ 8.0/10

OpenAI 提议让美国政府持有公司 5%的股份，并建议类似结构可适用于 Google、Meta 等其他主要 AI 公司，让公众分享 AI 发展的收益。 该提议可能重塑 AI 治理和公共利益分享模式，为政府参与私营 AI 公司树立先例，并回应垄断和公共利益方面的担忧。 该计划涉及一个政府载体同时持有多家 AI 公司 5%的股份，可能引发监管和利益冲突问题；目前其他公司是否会接受尚不明确。

telegram · zaihuapd · 7月2日 06:02

**背景**: OpenAI 是一家领先的 AI 研究和部署公司，以 ChatGPT 闻名。美国政府一直在探索 AI 监管和公共利益保障的方式。该提议提出了直接股权持有作为公众参与 AI 利润和治理的新机制。

**标签**: `#AI governance`, `#OpenAI`, `#U.S. government`, `#tech policy`, `#artificial intelligence`

---

<a id="item-12"></a>
## [花旗禁用 GPT-5.5，企业因 AI 成本飙升限制使用](https://www.404media.co/companies-are-throttling-employees-ai-use-because-its-too-expensive/) ⭐️ 8.0/10

花旗银行自 6 月 24 日起完全禁用 GPT-5.5、Claude Opus 4.6 和 4.7 等最新 AI 模型，理由是这些模型消耗过多 AI 积分。同时，Atlassian 的 AI 月支出从 2025 年 8 月的 500 万美元飙升至 2026 年 5 月的逾 1500 万美元，公司已终止无限使用并推出成本追踪面板。 这一趋势揭示了企业采用 AI 时面临的财务瓶颈：即便是大型公司也难以控制按用量计费的强大模型成本。这预示着企业可能放缓 AI 部署，重新评估前沿工具的投资回报率。 Adobe 选择不续签无限使用 Claude 的合同，该合同于 6 月 30 日到期。亚马逊此前关闭了鼓励 AI 使用的内部排行榜，员工随后发现此前未知的 token 使用上限。咨询公司埃森哲在推动客户快速采用 AI 的同时，将 AI 成本管理包装为新商机。

telegram · zaihuapd · 7月2日 13:59

**背景**: 许多企业 AI 工具采用基于积分的定价模式，每次操作（如生成文本或处理文档）会消耗一定数量的积分。GPT-5.5 和 Claude Opus 等高级模型每次任务需要更多积分，导致员工大量使用时成本迅速攀升。公司通常将订阅费与按用量积分相结合，但如果缺乏管控，广泛采用可能导致预算超支。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://schematichq.com/blog/ai-credits">AI Credits: How They Work, Pricing Models, and Implementation</a></li>
<li><a href="https://en.wikipedia.org/wiki/Claude_(language_model)">Claude (AI) - Wikipedia</a></li>
<li><a href="https://metronome.com/blog/the-rise-of-ai-credits-why-cost-plus-credit-models-work-until-they-dont">The Rise of AI Credits: Why Cost-Plus Credit Models Work (Until They Don’t) | Metronome blog</a></li>

</ul>
</details>

**标签**: `#AI costs`, `#enterprise AI`, `#cost management`, `#technology trends`

---

<a id="item-13"></a>
## [PS3 商店 2027 年关闭：档案员紧急抢救游戏](http://no-intro.org/) ⭐️ 8.0/10

索尼宣布将于 2027 年 7 月永久关闭 PS3 和 PS Vita 的 PlayStation Store，数字档案管理员紧急备份游戏数据。RPCS3 模拟器团队呼吁社区使用 no-intro.org 数据库协作保存。 这一事件凸显了纯数字游戏所有权的脆弱性，以及在线商店关闭时文化重要软件面临丢失的风险。随着行业向全数字化分发发展，社区驱动的保存变得至关重要。 no-intro.org 数据库记录游戏转储的加密签名、文件大小和序列号，帮助社区验证哪些游戏已备份。RPCS3 警告称，从未推出实体版的游戏可能在商店关闭后永久丢失。

telegram · zaihuapd · 7月2日 15:04

**背景**: 索尼的 PS3 和 PS Vita 的 PlayStation Store 自 2000 年代中期上线，提供数字购买和下载。随着主机世代更替，公司常关闭在线服务，导致之前购买的内容无法访问，除非已备份。No-Intro 等保存组织维护精编的游戏元数据集以确保准确存档，而 RPCS3 等模拟器需要合法的游戏转储才能运行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://x.com/nointro_org">No-Intro (@nointro_org) / Posts / X</a></li>
<li><a href="https://myrient.erista.me/files/No-Intro/">Index of /files/No-Intro - Content Listing | Myrient - Erista</a></li>

</ul>
</details>

**标签**: `#数字保存`, `#PS3`, `#游戏模拟器`, `#索尼`, `#社区协作`

---