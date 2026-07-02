---
layout: default
title: "Horizon Summary: 2026-07-02 (EN)"
date: 2026-07-02
lang: en
---

> From 76 items, 13 important content pieces were selected

---

1. [Linux 6.9 Bug Fails to Wipe LUKS Encryption Keys on Suspend](#item-1) ⭐️ 8.0/10
2. [F-Droid: Android Developer Verification Is a Threat Masquerading as Protection](#item-2) ⭐️ 8.0/10
3. [Japan top court: AI cannot be patent inventor](#item-3) ⭐️ 8.0/10
4. [Egg Price Fixers Profited 1000x Their Fine](#item-4) ⭐️ 8.0/10
5. [Code review's primary goal is maintainability](#item-5) ⭐️ 8.0/10
6. [The Fall of the Theorem Economy](#item-6) ⭐️ 8.0/10
7. [Understand to Participate: Avoiding Cognitive Debt in AI Coding](#item-7) ⭐️ 8.0/10
8. [ECTC 2026 Roundup: EMIB-T, HBM4, Cooling, Photonics](#item-8) ⭐️ 8.0/10
9. [Chinese quantum startup Nakairangkai raises millions for neutral atom computers](#item-9) ⭐️ 8.0/10
10. [Kuaishou's Keling AI Raises $3B, Record for Video AI](#item-10) ⭐️ 8.0/10
11. [OpenAI Proposes US Government 5% Stake, Eyes Other AI Giants](#item-11) ⭐️ 8.0/10
12. [Banks and tech firms restrict employee AI use due to surging costs](#item-12) ⭐️ 8.0/10
13. [Anthropic in early talks with Samsung for custom AI chips](#item-13) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Linux 6.9 Bug Fails to Wipe LUKS Encryption Keys on Suspend](https://mathstodon.xyz/@iblech/116769502749142438) ⭐️ 8.0/10

A regression in Linux kernel 6.9 causes the LUKS suspend operation to no longer wipe disk-encryption keys from memory, potentially exposing encrypted data during suspend-to-RAM. The bug was introduced by a refactoring that omitted a single line C check. This is a critical security regression that undermines the protection of disk encryption during suspend, especially for users relying on Debian's cryptsetup-suspend addon. It highlights the fragility of large C codebases and the need for rigorous testing in security-sensitive kernel code. The bug was introduced during refactoring that missed a single line C check across files. The Debian cryptsetup-suspend addon, which uses the luksSuspend command to wipe keys, is not officially supported by the kernel but this regression still impacts users on affected distributions.

hackernews · IngoBlechschmid · Jul 2, 15:25 · [Discussion](https://news.ycombinator.com/item?id=48763035)

**Background**: LUKS (Linux Unified Key Setup) is a disk encryption specification. When a system suspends to RAM, the encryption master key remains in memory for resume. The luksSuspend command is designed to wipe the master key from memory and require re-entry of the passphrase on wake, protecting against cold boot attacks. Without this wipe, the key remains vulnerable to memory extraction.

<details><summary>References</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=48763035">Since Linux 6.9, LUKS suspend stopped wiping disk-encryption ...</a></li>
<li><a href="https://manpages.debian.org/unstable/cryptsetup-suspend/cryptsetup-suspend.7.en.html">cryptsetup- suspend (7) — cryptsetup- suspend ... — Debian Manpages</a></li>
<li><a href="https://github.com/Gunpyr/ubuntu-luks-suspend">GitHub - Gunpyr/ubuntu- luks - suspend : Lock encrypted root volume on...</a></li>

</ul>
</details>

**Discussion**: Community comments reflect mixed views. Some consider this a serious security bug that underscores the difficulty of maintaining invariant correctness in C codebases. Others downplay it because cryptsetup-suspend is not officially supported, while a few note that for typical users the risk is low. One commenter pointed out that the bug was caught via NixOS tests, praising the testing approach.

**Tags**: `#linux`, `#security`, `#encryption`, `#LUKS`, `#kernel-bug`

---

<a id="item-2"></a>
## [F-Droid: Android Developer Verification Is a Threat Masquerading as Protection](https://f-droid.org/2026/07/01/adv-malware.html) ⭐️ 8.0/10

F-Droid published an article arguing that Google's new Android developer verification system is a deceptive threat that undermines user freedom and could be used to block sideloading of apps from alternative stores like F-Droid. This critique highlights growing concerns about Google's control over Android, especially for privacy advocates and open-source enthusiasts, and fuels debate about mobile OS openness and the future of alternative app distribution. Google's developer verification system, announced in 2025, requires identity verification for all developers on Play Console and Android Developer Console, with an early access program starting October 2025 and enhanced reviews for apps with sensitive permissions.

hackernews · drewfax · Jul 2, 03:00 · [Discussion](https://news.ycombinator.com/item?id=48755965)

**Background**: F-Droid is a free and open-source app store for Android that prioritizes user freedom and privacy. Google's Play Store has long required developer accounts, but the new system extends verification to apps distributed outside the official store, potentially making sideloading more difficult and increasing Google's control over the Android ecosystem.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/F-Droid">F-Droid</a></li>
<li><a href="https://www.androidsage.com/2025/08/26/google-blocks-sideloading-of-android-apps/">It's Over: Google Blocks Sideloading of Android Apps</a></li>
<li><a href="https://f-droid.org/">F-Droid - Free and Open Source Android App Repository</a></li>

</ul>
</details>

**Discussion**: Commenters expressed mixed views: some supported F-Droid's stance and suggested alternative mobile OSes like SailfishOS and Graphene, while others criticized the article's tone as childish and counterproductive, fearing it would give Google ammunition to dismiss F-Droid. Some speculated that the verification system targets ad-blocking apps like NewPipe.

**Tags**: `#Android`, `#F-Droid`, `#privacy`, `#open source`, `#mobile OS`

---

<a id="item-3"></a>
## [Japan top court: AI cannot be patent inventor](https://japannews.yomiuri.co.jp/science-nature/technology/20260306-314930/) ⭐️ 8.0/10

Japan's Supreme Court ruled on March 6, 2026 that artificial intelligence cannot be listed as an inventor on patent applications, aligning with the policy in the United States. This decision sets a legal precedent in Japan, reinforcing that only natural persons can hold inventor status, which affects the patentability of AI-generated inventions and the incentives for AI-assisted innovation. The ruling mirrors the U.S. Patent and Trademark Office's stance that AI systems cannot be named inventors, though human inventors can receive patents for AI-assisted inventions if they contribute significantly.

hackernews · mushstory · Jul 2, 13:43 · [Discussion](https://news.ycombinator.com/item?id=48761536)

**Background**: Patent laws worldwide traditionally require inventors to be natural persons, as only humans can hold legal rights and responsibilities. Recent guidelines from the USPTO and the Japan Patent Office have clarified that AI can assist but not be named as an inventor. The case in Japan was part of a broader debate on intellectual property in the age of generative AI.

<details><summary>References</summary>
<ul>
<li><a href="https://www.congress.gov/crs-product/LSB11251">Artificial Intelligence and Patent Law | Congress.gov | Library of Congress</a></li>
<li><a href="https://www.federalregister.gov/documents/2024/02/13/2024-02623/inventorship-guidance-for-ai-assisted-inventions">Federal Register :: Inventorship Guidance for AI-Assisted Inventions</a></li>

</ul>
</details>

**Discussion**: Community comments largely support the ruling, arguing that AI lacks accountability and cannot own benefits. Some compare AI to a calculator, while others question whether AI-generated inventions can still be patented under a human inventor's name.

**Tags**: `#AI`, `#patents`, `#intellectual property`, `#Japan`, `#law`

---

<a id="item-4"></a>
## [Egg Price Fixers Profited 1000x Their Fine](https://www.thebignewsletter.com/p/crime-pays-the-egg-bandits-made-a) ⭐️ 8.0/10

Egg producers colluded to fix prices, making profits over a thousand times larger than the fines they ultimately paid. This highlights severe underdeterrence in antitrust enforcement, allowing corporations to treat fines as a cost of doing business and undermining market competition. During the egg price crisis, media blamed avian flu and inflation, but the price-fixing operation was a major cause; the fine paid was miniscule compared to illicit gains.

hackernews · toomuchtodo · Jul 2, 13:25 · [Discussion](https://news.ycombinator.com/item?id=48761229)

**Background**: Price fixing is an illegal agreement between competitors to raise prices, reducing competition and harming consumers. Antitrust laws aim to prevent such collusion, but fines are often too low to deter large corporations.

**Discussion**: Commenters expressed shock that the egg crisis was due to price fixing, not inflation or avian flu. Some noted that market concentration enables such collusion, and argued for stronger penalties like corporate accountability and even corporal punishment for white-collar crime.

**Tags**: `#price fixing`, `#antitrust`, `#corporate crime`, `#economics`, `#market concentration`

---

<a id="item-5"></a>
## [Code review's primary goal is maintainability](https://mathstodon.xyz/@mjd/115096720350507897) ⭐️ 8.0/10

A viral post argues that the primary purpose of code review is to identify code that will be hard to maintain, sparking a multi-faceted community discussion. This debate reframes how teams approach code review, emphasizing maintainability over bug detection alone, and influences best practices in software engineering. The post was shared on Mathstodon and received 237 points and 126 comments, indicating high engagement within the developer community.

hackernews · ColinWright · Jul 2, 11:41 · [Discussion](https://news.ycombinator.com/item?id=48759870)

**Background**: Code review is a software engineering practice where developers examine each other's code changes before merging. Traditionally, it aims to catch bugs and improve code quality. This post challenges that view by prioritizing long-term maintainability over immediate correctness.

**Discussion**: Community comments strongly disagree that maintainability is the sole primary goal. Commenters highlight other purposes such as knowledge transfer, safety against malicious code, team ownership, and catching bugs through code smells. One commenter accuses the post of justifying lazy reviewing.

**Tags**: `#code review`, `#software engineering`, `#maintainability`, `#best practices`, `#team collaboration`

---

<a id="item-6"></a>
## [The Fall of the Theorem Economy](https://davidbessis.substack.com/p/the-fall-of-the-theorem-economy) ⭐️ 8.0/10

An article by David Bessis argues that mathematics is moving away from a theorem-centric economy toward computational and AI-driven approaches, drawing parallels to Greg Egan's novel 'Diaspora'. This shift could redefine the role of mathematicians and the peer-review process, potentially accelerating discovery but also raising questions about the nature of mathematical truth and community validation. The article suggests that as proof assistants and AI systems become more capable, the traditional focus on proving theorems may diminish, much like Egan's concept of 'truth mining' where a vast database of formalized knowledge is explored through intuition and visualization.

hackernews · varjag · Jul 2, 08:01 · [Discussion](https://news.ycombinator.com/item?id=48758048)

**Background**: Theorem proving has been central to mathematics for centuries, but recent advances in automated theorem proving and formal methods—where proofs are checked by computers—are changing the landscape. Greg Egan's 1997 novel 'Diaspora' envisions a posthuman future where mathematics evolves into 'truth mining' within a fully formalized system. The article argues that we are now approaching that reality.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Automated_theorem_proving">Automated theorem proving</a></li>
<li><a href="https://en.wikipedia.org/wiki/Diaspora_(novel)">Diaspora (novel) - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Formal_methods">Formal methods - Wikipedia</a></li>

</ul>
</details>

**Discussion**: Commenters largely agree with the premise, with one noting that Egan's 'truth mining' presciently describes mathematics after full formalization. Another commenter suggests that mathematics is more about testing and gaining confidence, similar to software engineering, rather than rigorous proofs. Some discuss the potential for reduced open science due to private AI resources.

**Tags**: `#mathematics`, `#theorem proving`, `#AI`, `#formal methods`, `#mathematical culture`

---

<a id="item-7"></a>
## [Understand to Participate: Avoiding Cognitive Debt in AI Coding](https://simonwillison.net/2026/Jul/2/understand-to-participate/#atom-everything) ⭐️ 8.0/10

At the AI Engineer World's Fair 2026, Geoffrey Litt introduced the concept of 'understand to participate,' arguing that developers must maintain a deep understanding of their code to effectively collaborate with AI coding agents and avoid accumulating cognitive debt. This insight is crucial as AI coding agents become more sophisticated, posing a risk that developers lose understanding of their own code, which hampers creative participation and increases cognitive debt. It highlights a practical challenge that the software engineering community must address to fully benefit from AI-assisted development. The talk was one of over 300 recorded sessions at AIE, and Geoffrey also shared a Twitter thread summarizing his arguments. Cognitive debt, a term gaining traction, refers to the mental cost of moving fast without understanding why code works, analogous to technical debt but residing in the developer's mind.

rss · Simon Willison · Jul 2, 17:07

**Background**: Cognitive debt is a relatively new concept describing the mental overhead incurred when developers prioritize speed over understanding, especially in AI-assisted coding where agents can generate large code changes. To avoid cognitive debt, developers must actively learn from the agent's outputs and maintain a rich mental model of the codebase. This allows them to participate creatively rather than passively accepting or rejecting suggestions.

<details><summary>References</summary>
<ul>
<li><a href="https://medium.com/@willsh/what-is-cognitive-debt-5182e4a4fa98">What is Cognitive Debt? - Medium</a></li>
<li><a href="https://margaretstorey.com/blog/2026/02/09/cognitive-debt/">How Generative and Agentic AI Shift Concern from Technical Debt to ...</a></li>

</ul>
</details>

**Tags**: `#AI coding agents`, `#cognitive debt`, `#software engineering`, `#LLM collaboration`

---

<a id="item-8"></a>
## [ECTC 2026 Roundup: EMIB-T, HBM4, Cooling, Photonics](https://newsletter.semianalysis.com/p/ectc2026) ⭐️ 8.0/10

The ECTC 2026 conference highlighted Intel's EMIB-T packaging technology entering production, roadmaps for custom HBM and HBM4 with 2.8 TB/s bandwidth, microfluidic cooling breakthroughs, and photonic interconnects from companies like Lightmatter. These advancements are critical for next-generation AI accelerators and high-performance computing, addressing power delivery, thermal management, and bandwidth bottlenecks that limit scaling. Intel's EMIB-T adds through-silicon vias (TSVs) to the bridge for better power delivery and supports HBM4. HBM4 features a 2048-pin interface at >11 Gbps, delivering >2.8 TB/s per stack. Microfluidic cooling uses channels etched in silicon for up to 3x better heat removal.

rss · Semianalysis · Jul 2, 17:25

**Background**: Advanced packaging technologies like EMIB (Embedded Multi-die Interconnect Bridge) and CoWoS are used to integrate multiple chips (e.g., logic and HBM) in a single package. HBM (High Bandwidth Memory) is a type of DRAM stacked with through-silicon vias for high bandwidth, used in AI accelerators. Microfluidic cooling circulates coolant through microscopic channels directly on chips to manage heat. Photonic interconnects use light for faster, lower-power data transfer.

<details><summary>References</summary>
<ul>
<li><a href="https://www.tomshardware.com/pc-components/cpus/intel-details-new-advanced-packaging-breakthroughs-emib-t-paves-the-way-for-hbm4-and-increased-ucie-bandwidth">Intel details new advanced packaging breakthroughs — EMIB-T paves the way for HBM4 and increased UCIe bandwidth | Tom's Hardware</a></li>
<li><a href="https://www.tomshardware.com/tech-industry/semiconductors/intels-emib-t-heads-for-fab-rollout-this-year">Intel's EMIB-T packaging technology set for fab rollout this year — as TSMC CoWoS capacity remains limited, EMIB-T is preparing for advanced AI accelerator designs | Tom's Hardware</a></li>
<li><a href="https://news.microsoft.com/source/features/innovation/microfluidics-liquid-cooling-ai-chips/">AI chips are getting hotter. A microfluidics breakthrough goes straight to the silicon to cool up to three times better. - Source</a></li>

</ul>
</details>

**Tags**: `#semiconductor packaging`, `#HBM`, `#microfluidic cooling`, `#photonic interconnects`, `#advanced packaging`

---

<a id="item-9"></a>
## [Chinese quantum startup Nakairangkai raises millions for neutral atom computers](https://36kr.com/p/3877814169530630?f=rss) ⭐️ 8.0/10

Chinese startup Nakairangkai Quantum, founded by Peking University PhDs, announced a seed funding round of tens of millions RMB, led by Hillhouse Capital (GL Ventures), to advance its neutral atom quantum computing platform operating at nanokelvin temperatures. This funding underscores the growing prominence of neutral atom quantum computing in China, a route known for scalability and qubit uniformity, and suggests that cold-atom technology is moving from lab to commercial viability. Nakairangkai claims to be the only Chinese team that can engineer cooling of nine atomic species (e.g., rubidium, potassium, cesium) below 10 nK. The company has a full-stack product line including quantum simulation computers and expects 2026 revenue in the tens of millions RMB.

rss · 36氪 · Jul 2, 01:16

**Background**: Neutral atom quantum computers use laser-cooled atoms as qubits, offering natural uniformity and scalability. Nanokelvin temperatures are billionths of a degree above absolute zero, where thermal noise is minimized. The field accelerated after Harvard and QuEra demonstrated a programmable neutral atom processor in 2023.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Neutral_atom_quantum_computer">Neutral atom quantum computer - Wikipedia</a></li>
<li><a href="https://www.quera.com/neutral-atom-platform">Building Quantum Computers with Neutral Atoms | QuEra</a></li>
<li><a href="https://en.wikipedia.org/wiki/Nanokelvin">Nanokelvin</a></li>

</ul>
</details>

**Tags**: `#quantum computing`, `#neutral atom`, `#startup funding`, `#cold atom`, `#China`

---

<a id="item-10"></a>
## [Kuaishou's Keling AI Raises $3B, Record for Video AI](https://36kr.com/newsflashes/3878648324845831?f=rss) ⭐️ 8.0/10

On July 2, 2025, Kuaishou's video generation model Keling AI closed a nearly $3 billion funding round, with a post-money valuation of $18 billion, setting a global record for the largest funding round among video generation AI companies. This funding demonstrates strong commercial momentum and investor confidence in AI video generation, and marks the beginning of Keling AI's independent commercialization. The involvement of major tech and media investors underscores its industry impact. The round was co-led by CPE Yuanfeng, Guofang Venture Capital, BlueFive, Tencent, Zhongguancun Science City Fund (with UNISCI), and CITIC Securities, with participation from dozens of leading institutions including Alibaba Cloud and Baidu, as well as entertainment investors like Huace Media and Mango Industrial Investors.

rss · 36氪 · Jul 2, 15:25

**Background**: Keling AI is a video generation model developed by Kuaishou, a major Chinese tech company. It can generate videos from text or images. In April 2025, Kuaishou announced version 2.0 of Keling, which showed significant improvements. Video generation AI is a rapidly growing field with competitors like OpenAI's Sora and Runway.

<details><summary>References</summary>
<ul>
<li><a href="https://zenn.dev/taku_sid/articles/20250416_kelings_ai?locale=en">A Simple Guide to Keling 2.0: China’s Latest AI Video ...</a></li>
<li><a href="https://llm-stats.com/leaderboards/best-ai-for-video-generation">Best AI for Video Generation in 2026 — Ranked by Blind Human ...</a></li>

</ul>
</details>

**Tags**: `#Video Generation AI`, `#Funding`, `#Kuaishou`, `#Large Models`, `#AI Industry`

---

<a id="item-11"></a>
## [OpenAI Proposes US Government 5% Stake, Eyes Other AI Giants](https://www.bloomberg.com/news/articles/2026-07-02/openai-proposes-giving-the-us-government-a-5-stake-ft-says) ⭐️ 8.0/10

OpenAI has proposed that the US government take a 5% equity stake in the company, and potentially similar stakes in other major AI firms like Google and Meta, to allow the public to benefit from AI growth. This proposal could reshape AI governance by directly involving the government in profit-sharing, raising questions about control and conflicts of interest. It sets a precedent for how public benefits from AI are distributed. The plan involves a government vehicle holding 5% stakes in OpenAI, Anthropic, Google, and Meta. Other companies have not yet indicated acceptance, and regulatory and conflict-of-interest concerns remain unresolved.

telegram · zaihuapd · Jul 2, 06:02

**Background**: OpenAI is a leading AI research and deployment company, known for models like GPT-4. Anthropic, founded by former OpenAI employees, focuses on AI safety and develops Claude. The proposal aims to channel AI economic benefits to the public through government ownership.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Anthropic">Anthropic - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#AI`, `#OpenAI`, `#government stake`, `#policy`, `#tech giants`

---

<a id="item-12"></a>
## [Banks and tech firms restrict employee AI use due to surging costs](https://www.404media.co/companies-are-throttling-employees-ai-use-because-its-too-expensive/) ⭐️ 8.0/10

Citibank banned the use of GPT-5.5, Claude Opus 4.6 and 4.7 on June 24, 2026, citing excessive AI credit consumption, while Atlassian's monthly AI spending soared from $5 million to over $15 million in early 2025–2026, prompting usage caps and cost dashboards. This trend reveals that usage-based pricing for advanced AI models is creating unsustainable costs for enterprises, potentially slowing AI adoption and forcing companies to prioritize cost control over innovation. Atlassian's internal dashboard showed AI expenses growing 3x in about 9 months; Adobe decided not to renew its unlimited Claude contract; and Amazon previously shut down internal leaderboards that encouraged AI usage, revealing hidden token caps.

telegram · zaihuapd · Jul 2, 13:59

**Background**: Many AI tools, including GPT-5.5 and Claude Opus models, are priced on a usage-based model where customers pay per token or consume AI credits. These credits function as a prepaid unit of consumption, and more powerful models cost more credits per request. Without proper governance, enterprise spending can spiral as employees adopt these tools broadly.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/GPT-5.5">GPT-5.5</a></li>
<li><a href="https://schematichq.com/blog/ai-credits">AI Credits: How They Work, Pricing Models, and Implementation</a></li>
<li><a href="https://arstechnica.com/ai/2026/06/ai-costs-how-much-github-copilot-users-react-to-new-usage-based-pricing-system/">AI costs how much? GitHub Copilot users react to new usage-based pricing system. - Ars Technica</a></li>

</ul>
</details>

**Tags**: `#AI costs`, `#enterprise AI`, `#AI adoption`, `#cost management`, `#industry trend`

---

<a id="item-13"></a>
## [Anthropic in early talks with Samsung for custom AI chips](https://www.theinformation.com/articles/anthropic-talks-samsung-manufacture-custom-ai-chip) ⭐️ 8.0/10

Anthropic has begun developing its own custom AI chips and is in early-stage talks with Samsung Electronics for potential manufacturing, aiming to reduce reliance on external suppliers for its Claude models. This move signals a trend of vertical integration among leading AI companies, as they seek to optimize hardware for their models and secure supply chains. If successful, it could intensify competition with OpenAI's custom chip efforts and reshape the AI semiconductor landscape. Anthropic's chip project is still in early development, and the company is a later entrant compared to rivals like OpenAI, which has already partnered with Broadcom to launch the Jalapeño inference chip. Samsung's foundry business offers both design and manufacturing services for custom chips.

telegram · zaihuapd · Jul 2, 15:57

**Background**: Major AI companies like OpenAI and Anthropic are increasingly developing custom silicon to better handle the computational demands of large language models, reducing reliance on general-purpose GPUs. OpenAI's Jalapeño chip, announced in June 2026, is a dedicated inference chip built with Broadcom. Samsung's foundry is one of the few manufacturers capable of producing advanced chips for such applications.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/openai-broadcom-jalapeno-inference-chip/">OpenAI and Broadcom unveil LLM-optimized inference chip</a></li>
<li><a href="https://semiconductor.samsung.com/foundry/">Foundry Overview | Samsung Semiconductor Global</a></li>

</ul>
</details>

**Tags**: `#Anthropic`, `#AI chips`, `#Samsung`, `#semiconductor`, `#custom silicon`

---