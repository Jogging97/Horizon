---
layout: default
title: "Horizon Summary: 2026-07-25 (ZH)"
date: 2026-07-25
lang: zh
---

> 从 105 条内容中筛选出 10 条重要资讯。

---

1. [SGLang v0.5.16 新增 DSpark 推测解码和 Inkling 支持](#item-1) ⭐️ 9.0/10
2. [Anthropic 发布 Claude Opus 5，无需数据留存](#item-2) ⭐️ 9.0/10
3. [伊朗革命卫队声称摧毁亚马逊巴林数据中心](#item-3) ⭐️ 9.0/10
4. [印度政府要求 GitHub 移除蓝牙聊天应用 Bitchat](#item-4) ⭐️ 9.0/10
5. [OpenAI 发布 Presence 引发软件股抛售](#item-5) ⭐️ 9.0/10
6. [Postgres LISTEN/NOTIFY 确实可扩展](#item-6) ⭐️ 8.0/10
7. [Claude Opus 5 在 Artificial Analysis 智能排行榜上排名第一](#item-7) ⭐️ 8.0/10
8. [中国开源 AI 正重塑全球算力格局](#item-8) ⭐️ 7.0/10
9. [浙江发布人工智能赋能政策 全面实施“人工智能+”行动](#item-9) ⭐️ 7.0/10
10. [萨顿：大模型缺真实体验，2040 年有五成概率理解心智](#item-10) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [SGLang v0.5.16 新增 DSpark 推测解码和 Inkling 支持](https://github.com/sgl-project/sglang/releases/tag/v0.5.16) ⭐️ 9.0/10

SGLang v0.5.16 引入了 DSpark，一种基于置信度的推测解码算法，在 DeepSeek-V4-Pro 上达到 383.7 tok/s，并新增了对 Inkling 的支持，这是一个 975B 参数的多模态 MoE 模型，支持 100 万 token 上下文。 DSpark 在不重新训练模型的情况下显著加速推理，提供更快速的响应，而 Inkling 以其巨大的规模和长上下文代表了多模态 AI 的飞跃，两者都推动了实际 AI 部署的进步。 DSpark 使用半自回归块草稿和基于置信度的自适应验证窗口大小调整，Inkling 混合了滑动窗口、完全注意力和 Mamba2 线性注意力，并包含 NVFP4 MoE 以及可选的视觉/音频塔，输入吞吐量高达 71.7k tok/s。

github · Qiaolin-Yu · 7月25日 00:13

**背景**: 推测解码通过使用较小的草稿模型生成候选 token，再由较大的目标模型并行验证，从而加速 LLM 推理。MoE（混合专家）模型每个 token 仅激活部分参数，使得在保持推理效率的同时拥有更大的总参数量。DSpark 通过根据草稿模型的置信度动态调整验证窗口，减少了计算浪费。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.techtimes.com/articles/319236/20260628/deepseek-releases-dspark-speculative-decoding-makes-v4-85-percent-faster.htm">DeepSeek Releases DSpark: Speculative Decoding Makes V4 Up to 85 Percent Faster</a></li>
<li><a href="https://thinkingmachines.ai/news/introducing-inkling/">Inkling: Our Open-Weights Model - Thinking Machines Lab</a></li>

</ul>
</details>

**标签**: `#speculative decoding`, `#AI inference`, `#MoE`, `#multimodal LLM`, `#GitHub release`

---

<a id="item-2"></a>
## [Anthropic 发布 Claude Opus 5，无需数据留存](https://www.anthropic.com/news/claude-opus-5) ⭐️ 9.0/10

Anthropic 宣布推出全新旗舰 AI 模型 Claude Opus 5，在更低成本下实现接近 Fable 5 的智能水平，且一般访问无需数据留存。 此次发布让组织能够在不牺牲数据隐私的前提下使用顶级模型，消除了企业采用的关键障碍。同时，它也加剧了 AI 模型提供商之间的竞争，特别是与 OpenAI 和 Google 的竞争。 Opus 5 在基准测试中的表现与 Fable 5 相差不到 0.5%，而每次任务成本仅为后者的一半，并且在计算机使用方面以三分之一成本超越了 Fable 5。与之前的 Opus 模型一致，它一般访问无需数据留存要求。

hackernews · alvis · 7月24日 16:57 · [社区讨论](https://news.ycombinator.com/item?id=49038433)

**背景**: Claude 是 Anthropic 专注安全性的 AI 模型系列。Opus 模型为最高层级，提供一流推理能力。Fable 是另一条模型线，具有类似智能水平但实施了严格的 30 天数据留存政策，而 Opus 5 避免了这一点。这使得 Opus 5 对隐私敏感的应用尤其有吸引力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/news/claude-opus-5">Introducing Claude Opus 5 \ Anthropic</a></li>
<li><a href="https://www-cdn.anthropic.com/c5fbac3f0b1280a933ebd26d3cb8bb9f5bdeaf48/Claude+Opus+5+System+Card.pdf">Claude Opus 5 System Card</a></li>
<li><a href="https://coursiv.io/blog/claude-opus-5">Claude Opus 5 : Release Date, What We Know &amp; Model... | Coursiv Blog</a></li>

</ul>
</details>

**社区讨论**: 评论者们强调数据留存优势是最重要的因素。一位用户报告 Opus 5 在图像到 HTML 转换准确性上超越 Fable 5。其他人注意到写作风格的差异，Opus 5 保留了“Claude 语言特色”而 Fable 则有所不同。一些人还讨论了模型路由服务的趋势。

**标签**: `#AI`, `#LLM`, `#Claude`, `#Anthropic`, `#machine learning`

---

<a id="item-3"></a>
## [伊朗革命卫队声称摧毁亚马逊巴林数据中心](https://houseofsaud.com/irgc-claims-destroyed-amazon-bahrain-data-center/) ⭐️ 9.0/10

伊朗伊斯兰革命卫队（IRGC）声称对摧毁亚马逊在巴林的数据中心负责，该数据中心属于 AWS me-south-1 区域，此举加剧了中东云基础设施领域的紧张局势。 这一事件凸显了集中式云基础设施在地缘政治冲突中的脆弱性，可能扰乱该地区客户的正常服务。它还引发了对数据中心冗余性的担忧，以及依赖 AWS 中东服务的企业将受到的影响。 据社区报告，AWS 巴林 me-south-1 区域至少包含三个数据中心（如 BAH53），彼此相距数公里，这意味着需要多次协调攻击才能让整个区域离线。据报道，破坏发生在 2026 年 7 月 16 日至 22 日左右，卫星图像显示一个变电站和数据中心本身均受损。

hackernews · thisislife2 · 7月24日 09:52 · [社区讨论](https://news.ycombinator.com/item?id=49033240)

**背景**: AWS 区域通常设计有多个数据中心（可用区），彼此相距较远以确保高可用性。me-south-1 区域是 AWS 在中东的唯一区域，服务于海湾地区及其他地区的客户。伊朗与海湾国家之间的地缘政治紧张局势长期威胁着区域基础设施，但这是已知的首批针对大型云数据中心的攻击之一。

**社区讨论**: 社区讨论表现出讽刺与担忧并存：有人指出，尽管遭受破坏，me-south-1 的可用性仍高于问题频发的 us-east-1 区域；另有人强调，中东唯一仍在运行的 AWS 区域是在特拉维夫。评论者还指出，这证明和平环境是集中式基础设施可靠运行的必要条件。

**标签**: `#cloud-infrastructure`, `#aws`, `#geopolitics`, `#cybersecurity`, `#data-center`

---

<a id="item-4"></a>
## [印度政府要求 GitHub 移除蓝牙聊天应用 Bitchat](https://www.thehindu.com/news/national/government-orders-github-to-remove-bluetooth-based-chat-app-bitchat-over-security-concerns-jack-dorsey/article71262049.ece) ⭐️ 9.0/10

印度政府以安全为由，下令 GitHub 移除去中心化蓝牙网状聊天应用 Bitchat，称其可能被反国家分子利用以规避监控。 此举加剧了关于政府监控和审查的辩论，尤其是针对一款旨在实现离线加密通信的开源工具，可能对印度的隐私和言论自由产生寒蝉效应。 Bitchat 由 Jack Dorsey 于 2025 年 7 月发布，利用蓝牙网状网络实现无需互联网的点对点消息传递，私信采用端到端加密。GitHub 遵守了移除命令，引发技术界批评。

hackernews · rootkea · 7月24日 14:41 · [社区讨论](https://news.ycombinator.com/item?id=49036433)

**背景**: 像 Bitchat 这样的蓝牙网状聊天应用即使在互联网受限时也能通信，这对活动人士很有价值，但令政府担忧。印度在 2008 年孟买袭击事件后有严格的通信监控历史，包括禁止卫星电话，以及在抗议期间偶尔封锁社交媒体。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/BitChat">BitChat - Wikipedia</a></li>
<li><a href="https://bitchat.free/">bitchat</a></li>

</ul>
</details>

**社区讨论**: 评论者批评政府的理由，认为这等同于控制所有通信形式。一些人提供了印度持续非暴力抗议的背景，暗示此次删除是更广泛审查努力的一部分。其他人指出印度历史上曾试图禁止其无法监控的技术。

**标签**: `#censorship`, `#government-surveillance`, `#open-source`, `#India`, `#privacy`

---

<a id="item-5"></a>
## [OpenAI 发布 Presence 引发软件股抛售](https://www.businessinsider.com/openai-release-turns-a-bad-week-ugly-for-software-stocks-2026-7) ⭐️ 9.0/10

OpenAI 于 2026 年 7 月 22 日发布了企业 AI 智能体平台 Presence，导致 Workday、Atlassian、HubSpot 和 Salesforce 等多只软件股大幅下挫。 Presence 通过提供面向客户服务、销售和内部工作流程的 AI 自动化功能，直接与老牌 SaaS 厂商竞争，标志着企业软件格局的重大转变。 该产品允许企业为 AI 智能体设置数据访问权限和策略，为大规模、可重复的工作流程提供强有力的治理和运营监督。

telegram · zaihuapd · 7月24日 12:05

**背景**: Salesforce 等企业 SaaS 厂商依赖 CRM 和客户服务等工具的订阅收入。OpenAI 的 Presence 集成了 AI 智能体功能，可自动化这些任务，可能降低对传统软件订阅的需求，因此引发股价大幅下跌。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://help.openai.com/en/articles/20001405-openai-presence">OpenAI Presence - OpenAI Help Center</a></li>
<li><a href="https://finance.sina.com.cn/stock/usstock/c/2026-07-22/doc-iniisxzu8626887.shtml">OpenAI推出Presence企业平台 欲跳出大模型竞争 - 新浪财经</a></li>
<li><a href="https://www.ithome.com/0/980/300.htm">OpenAI 推出 OpenAI Presence，布局企业软件赛道 - IT之家</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#enterprise AI`, `#SaaS`, `#stock market`, `#competition`

---

<a id="item-6"></a>
## [Postgres LISTEN/NOTIFY 确实可扩展](https://www.dbos.dev/blog/postgres-listen-notify-scalability) ⭐️ 8.0/10

一篇详细分析对 Postgres LISTEN/NOTIFY 进行基准测试，证明其每秒可处理 6 万条通知，打破了它不可扩展的迷思。 这很重要，因为许多开发者担心扩展性问题而避免使用 LISTEN/NOTIFY；分析表明，正确使用时它适用于高吞吐量实时应用，尤其是结合社区验证的架构模式。 基准测试显示吞吐量为 6 万/秒，但评论者指出扩展性是一个连续谱；实用建议包括使用独立的监听进程和代理（例如用 Rust 实现）来管理订阅。

hackernews · KraftyOne · 7月24日 19:05 · [社区讨论](https://news.ycombinator.com/item?id=49040296)

**背景**: PostgreSQL 的 LISTEN/NOTIFY 允许客户端会话订阅命名通道并异步接收通知，避免了持续轮询。它常用于实时功能，但此前有人认为它每秒只能处理几千个事件。本文用具体数据挑战了这一看法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.postgresql.org/docs/current/sql-listen.html">PostgreSQL: Documentation: 18: LISTEN</a></li>
<li><a href="https://www.postgresql.org/docs/current/sql-notify.html">PostgreSQL: Documentation: 18: NOTIFY</a></li>
<li><a href="https://www.cybertec-postgresql.com/en/listen-notify-automatic-client-notification-in-postgresql/">LISTEN / NOTIFY: Automatic client notification in PostgreSQL</a></li>

</ul>
</details>

**社区讨论**: 评论者强调“可扩展”是一个连续谱，6 万/秒对某些用例可能不够，对另一些则过多。一位用户分享成功经验：用 Rust GraphQL 订阅代理，仅用 3-4 个 LISTEN 连接管理数万个订阅。另一位指出，使用缩放因子不当的技术是一种常见错误。

**标签**: `#PostgreSQL`, `#scalability`, `#websockets`, `#real-time`, `#database`

---

<a id="item-7"></a>
## [Claude Opus 5 在 Artificial Analysis 智能排行榜上排名第一](https://artificialanalysis.ai/models) ⭐️ 8.0/10

Claude Opus 5 在 Artificial Analysis 智能排行榜上夺得第一名，在综合智能指数上超越了 GPT-5.6 和 Kimi K3 等竞品。 这一排名突显了 AI 模型智能的快速进步，但也引发了关于成本和审查权衡的讨论。用户和开发者在选择模型时，必须在性能、实际可靠性和价格之间进行权衡。 该排行榜使用 AA 智能指数 v4.0，该指数汇总了 10 项具有挑战性的评估中的性能。Claude Opus 5 在最大努力模式下得分为 61，而 GPT-5.6 Sol 得分为 59，且 Claude Opus 5 在高努力模式下与 GPT-5.6 Sol 得分相同。

hackernews · aarondong · 7月24日 19:45 · [社区讨论](https://news.ycombinator.com/item?id=49040741)

**背景**: Artificial Analysis 智能排行榜是一个综合基准，通过评估 AI 模型在数学、科学、编程、代理任务和推理方面的表现，提供整体智能得分。其目的是防止狭隘的专业化，并跟踪 AI 的整体进展。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://artificialanalysis.ai/leaderboards/models">LLM Leaderboard - Comparison of AI models from OpenAI ...</a></li>
<li><a href="https://www.datalearner.com/en/leaderboards/external/aa-quality-index">Artificial Analysis Intelligence Index - AI Model Leaderboard ...</a></li>

</ul>
</details>

**社区讨论**: 社区评论显示了对 Claude 审查和高成本的担忧。用户 andy99 指出由于安全机制导致的可靠性问题，而 chmod775 指出 GPT-5.6 和 Kimi K3 以一半的成本取得了相近的得分。讨论还强调了不同努力级别下的细微性能差异。

**标签**: `#AI`, `#language models`, `#leaderboard`, `#Claude Opus 5`, `#artificial analysis`

---

<a id="item-8"></a>
## [中国开源 AI 正重塑全球算力格局](https://news.google.com/rss/articles/CBMif0FVX3lxTE01d0JGYzBHWFdkWHpRd3Q3bkpwa0hILTB2VXZjTDlEcEZpQm9Qa0VxR2NBMUpDcExORGJQZXQ0VEdfX3RmT0xfNnRYeXFoOFZjVXpWY3N4dzN6bWwwV3hRWmpiT2ZzeGhUVG1ORTFUZUFRZ1BwZTFpZTc3LUNjaHc?oc=5) ⭐️ 7.0/10

据报道，中国开源 AI 项目正在改变全球算力分配的格局，挑战传统主导地位。 这一转变可能推动高性能计算民主化，降低成本，加速全球 AI 创新，尤其对资源有限地区意义重大。 文章指出，中国开源模型和框架正获得关注，可能减少对专有硬件和软件生态的依赖。

google\_news · 新浪网 · 7月25日 01:16

**背景**: 开源 AI 项目允许全球开发者免费访问和修改前沿模型。中国在 AI 基础设施上投入巨大，其开源贡献正日益与西方竞争。这一发展可能重塑 AI 硬件和软件的全球供应链与权力格局。

**标签**: `#open-source`, `#AI`, `#computing power`, `#China`

---

<a id="item-9"></a>
## [浙江发布人工智能赋能政策 全面实施“人工智能+”行动](https://news.google.com/rss/articles/CBMiYkFVX3lxTE9aZU5rclItWWR4OGFDd2t3QkxFOGFYNlhxeVgtY0Zub0VhX2RRWVQ1T3BlQkJUd3NCUFNwemNIWmh6ekF4RGJuVDRKRFFHRnlhSUpvdzJVWVdrZkZGVVFvS2dn?oc=5) ⭐️ 7.0/10

2025 年 10 月 27 日，浙江省发布人工智能赋能政策，全面实施“人工智能+”行动，该政策基于 2025 年 5 月发布的《关于支持人工智能创新发展若干措施的通知》等前期措施。 该政策彰显了政府大力推动人工智能在各行业应用的决心，有望加速浙江省在制造业、医疗健康和金融等领域的人工智能融合，并为其他省份树立标杆。 该政策每年择优评选不超过 10 个“人工智能+”标杆项目，每个项目最高给予 500 万元补助，并计划到 2027 年建设国家级人工智能医疗行业应用基地。

google\_news · 观点网 · 7月24日 11:59

**背景**: “人工智能+”是指将人工智能技术融合到各行业中，类似于“互联网+”的概念。浙江省已通过多项政策积极推动人工智能，包括 2025-2027 年的人工智能+医疗健康行动计划和余杭区实施方案，目标是在 2025 年底前实现人工智能核心产业营业收入突破 1000 亿元。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://sjt.zj.gov.cn/art/2025/5/20/art_1229563385_2555353.html">浙江省人民政府印发关于支持人工智能创新发展若干措施的通知</a></li>
<li><a href="https://www.yuhang.gov.cn/art/2025/10/27/art_1229174782_1862109.html">杭州市余杭区人民政府关于印发《余杭区加快建设人工智能创新高地核心承载地实施方案（2025年版）》的通知</a></li>
<li><a href="https://www.hit180.com/74458.html">浙江省印发加快推动“人工智能+医疗健康”高质量发展行动计划（2025-2027年）</a></li>

</ul>
</details>

**标签**: `#AI policy`, `#China`, `#government`, `#artificial intelligence`, `#Zhejiang`

---

<a id="item-10"></a>
## [萨顿：大模型缺真实体验，2040 年有五成概率理解心智](https://news.google.com/rss/articles/CBMiWkFVX3lxTFBWU3dKblQ4LTk4b2lCMUFuRmVHeVAxcHVZT09rN1Y1c204YzlxLTZ5dE9NWVRKQlN5V0I4czdDRXNEOFVWMU1ENFNndGZHd1REVkp4YVFKdk9nZw?oc=5) ⭐️ 7.0/10

图灵奖得主理查德·萨顿表示，当前大语言模型不具备真实的体验或理解，并预测到 2040 年 AI 有 50%的概率能够深入洞悉心智。 作为顶尖 AI 研究者的观点，这一看法挑战了仅靠规模扩展就能实现意识的观念，将影响研究方向和公众对 AI 能力与局限的预期。 以强化学习闻名的萨顿强调体验和互动的重要性，而不仅仅是数据规模，但他并未提供新的技术证据或实现理解的路线图。

google\_news · 上观新闻 · 7月24日 21:00

**背景**: 理查德·萨顿是图灵奖得主和强化学习先驱。图灵奖是计算机科学领域的最高荣誉。关于大语言模型是否能获得意识或真正理解的争论仍在持续，许多专家怀疑当前架构在缺乏根本性突破的情况下能否实现此类能力。

**标签**: `#AI`, `#large language models`, `#consciousness`, `#Turing Award`, `#Richard Sutton`

---