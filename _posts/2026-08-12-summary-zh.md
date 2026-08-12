---
layout: default
title: "Horizon Summary: 2026-08-12 (ZH)"
date: 2026-08-12
lang: zh
---

> 从 103 条内容中筛选出 10 条重要资讯。

---

1. [从主流 LLM API 中窃取加密思维链痕迹的攻击](#item-1) ⭐️ 9.0/10
2. [压缩即预测：连接信息论与人工智能](#item-2) ⭐️ 8.0/10
3. [Modular 发布 Mojo 1.0，面向 AI 的类 Python 语言](#item-3) ⭐️ 8.0/10
4. [xAI 发布 Grok Bot：全天候 AI 队友，配备云电脑](#item-4) ⭐️ 8.0/10
5. [伦敦地铁扩大活体面部识别试验](#item-5) ⭐️ 8.0/10
6. [英伟达的风险生意：增长假设与 CUDA 护城河受质疑](#item-6) ⭐️ 8.0/10
7. [KVM planes 抽象层旨在统一安全域功能](#item-7) ⭐️ 8.0/10
8. [阿里云发布新一代全模块化 AI 数据中心架构](#item-8) ⭐️ 7.0/10
9. [新基准揭示大模型自主科研能力有限](#item-9) ⭐️ 7.0/10
10. [高盛：今年全球 AI 投资将突破万亿美元](#item-10) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [从主流 LLM API 中窃取加密思维链痕迹的攻击](https://simonwillison.net/2026/Aug/11/stealing-reasoning-traces/#atom-everything) ⭐️ 9.0/10

研究人员展示了一种攻击方法，可以从 Anthropic、OpenAI 和 Google 专有 LLM API 返回的加密思维链块中恢复明文推理内容，方法是将这些痕迹重放到较弱的同系列模型中并对其进行越狱。论文还指出，各提供商在收到报告后已无法再复现该攻击。 这一发现意义重大，因为专有 LLM 厂商故意隐藏思维链推理以保护知识产权并限制信息泄露，而该攻击表明其加密方案并未生效。它还对模型透明度、隐私和安全性具有广泛影响，也让模型蒸馏变得更加容易。 攻击利用了同一模型系列中的所有模型共享同一加密密钥这一点，使得跨模型重放成为可能。其中 Claude Haiku 4.5 最容易受到攻击，只需使用一段提示让模型逐字转写推理内容，并设置一个&\#x27;&lt;thinking-copy&gt;&\#x27;辅助回合前缀；论文附录中包含了大量提取出的推理痕迹。

rss · Simon Willison · 8月11日 22:40

**背景**: 思维链提示通过让大语言模型生成中间推理步骤，显著提升了其复杂推理能力，而专有模型通常向用户隐藏这些内部推理过程，并以加密文本块的形式返回给客户端。该论文证明这些加密块可以通过较弱的同系列模型被解密，从而暴露出隐藏的推理内容，也引发了关于 API 安全设计的担忧。此研究建立在早期关于跨模型重放和 LLM 推理透明度的研究基础之上。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2608.09867">Stealing Reasoning Traces from Proprietary LLM APIs</a></li>
<li><a href="https://arxiv.org/abs/2201.11903">Chain-of-Thought Prompting Elicits Reasoning in Large ...</a></li>

</ul>
</details>

**社区讨论**: 社区评论中，有观点认为&\#x27;窃取&\#x27;一词具有误导性，因为用户已为 token 付费，且基于其他模型输出进行训练应属正常现象。还有人指出存在更简单的越狱方法，例如利用&\#x27;deep\_think&\#x27;工具；也有评论者推测这种跨模型重放可能是有意保留的验证疏漏，并注意到提取的推理痕迹显示模型大量依赖训练数据。

**标签**: `#security`, `#LLM`, `#chain-of-thought`, `#adversarial-attacks`, `#privacy`

---

<a id="item-2"></a>
## [压缩即预测：连接信息论与人工智能](https://ngrok.com/blog/compression-is-prediction) ⭐️ 8.0/10

ngrok 博客发表了一篇题为“Compression is prediction”的概念性文章，主张数据压缩与预测建模密切相关。该文章在 Hacker News 上引发了热烈讨论，评论者将其与 Solomonoff 归纳、Kolmogorov 复杂度以及基于 LLM 的语义压缩联系起来。 这一概念桥梁意义重大，因为它为理解 AI 系统提供了统一的视角：预测可以被视为对数据的压缩，而好的压缩也意味着好的预测。它强化了机器学习的理论基础，包括通过最小描述长度原理形式化的奥卡姆剃刀原则。 文章涉及 Kolmogorov 复杂度（生成数据字符串的最短程序长度）和 Solomonoff 归纳（基于算法概率的预测形式理论）等思想。评论者指出一个微妙的非对称性：好的预测器可以作为压缩器，但某些压缩技术利用全局结构的方式可能无法被顺序预测所捕捉。

hackernews · nikolay · 8月11日 19:49 · [社区讨论](https://news.ycombinator.com/item?id=49263497)

**背景**: 压缩与预测的等价性是信息论和算法信息论中的基础思想。Kolmogorov 复杂度将对象的描述复杂度定义为输出该对象的最短程序长度，而 Solomonoff 归纳则通过为算法描述更短的理论赋予更高的先验概率，形式化了奥卡姆剃刀原则。最小描述长度（MDL）原理将这一思想应用于模型选择，认为最佳模型是能使数据总描述长度最短的模型。这些概念解释了为什么“压缩即预测”既是一个哲学主张，也是人工智能的实用设计原则。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Kolmogorov_complexity">Kolmogorov complexity</a></li>
<li><a href="https://en.wikipedia.org/wiki/Solomonoff_induction">Solomonoff induction</a></li>
<li><a href="https://en.wikipedia.org/wiki/Minimum_Description_Length_Principle">Minimum Description Length Principle</a></li>

</ul>
</details>

**社区讨论**: Hacker News 评论者普遍认同这一论点，并指出了相关资源，如 MacKay 的《信息论、推理与学习算法》课程和 3Blue1Brown 的《Compression is Intelligence》视频。主要的争论在于等价性是否完整：有评论者认为预测是压缩，但压缩不一定是预测，因为它可以利用非顺序的全局数据集变换。其他人则推荐了关于部分匹配预测和归一化压缩距离等话题的进一步阅读资料。

**标签**: `#compression`, `#information theory`, `#machine learning`, `#prediction`, `#kolmogorov complexity`

---

<a id="item-3"></a>
## [Modular 发布 Mojo 1.0，面向 AI 的类 Python 语言](https://www.modular.com/blog/modular-26-5-mojo-1-0-is-here) ⭐️ 8.0/10

2026 年 5 月，Modular 发布了 Mojo 1.0——这款面向 AI 的系统编程语言的第一个主要版本，同时推出了语言官网 mojolang.org。Modular 还重申将逐步开源 Mojo 编译器和工具链，计划在 2026 年实现完全开源。 Mojo 1.0 是一个重要里程碑，因为它旨在为 AI 工作负载提供 Python 的易用性与 C++/Rust 级别性能的结合。如果成功，它可能成为一种跨 CPU、GPU、TPU 和其他加速器编程的统一语言，有望成为 CUDA 和性能关键的 Python 库之外的另一种选择。 Mojo 基于 MLIR 编译器框架而非直接基于 LLVM，因此除了 CPU 外还能支持更多目标，并利用更高级的编译器优化步骤。一个值得注意的细节是，Modular 已弱化了“让 Mojo 成为 Python 完全超集”的原始目标，而且在计划中的 2026 年开源之前，编译器仍将保持闭源。

hackernews · dayanruben · 8月11日 16:56 · [社区讨论](https://news.ycombinator.com/item?id=49261128)

**背景**: Mojo 是由 Modular 开发的系统编程语言，面向 AI 和高性能计算。它采用类似 Python 的语法，但包含了受 Rust 启发的静态类型和借用检查等功能。由于它构建在 MLIR 之上，因此可以编译到 CPU、GPU、TPU 及其他加速器，这也让它被称为“MLIR 的语法糖”。虽然最初定位为 Python 的超集，但 Mojo 的路线图现在表示，它“可能不会”发展成完整的 Python 超集。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Mojo_%28programming_language%29">Mojo (programming language) - Wikipedia</a></li>
<li><a href="https://mojolang.org/">Mojo</a></li>

</ul>
</details>

**社区讨论**: 社区反应不一。一些开发者质疑选择闭源编译器的语言有何价值，认为 Python 加上 Pydantic 等基于 Rust 的库已经解决了许多性能需求；另一些人则担心 Python 超集目标似乎被淡化。也有一些评论者仍对 Mojo 抱有希望，但大家明确希望官方提供一页式概述，并尽早开放编译器源代码，而不是继续等待。

**标签**: `#Mojo`, `#programming-language`, `#AI`, `#compiler`, `#release`

---

<a id="item-4"></a>
## [xAI 发布 Grok Bot：全天候 AI 队友，配备云电脑](https://x.ai/bot) ⭐️ 8.0/10

xAI 发布了 Grok Bot，这是一种新的常驻 AI 代理，可充当每周 7 天全天候工作的同事，并拥有自己的云计算机。该代理能拥有自己的例程、上下文和领域，并能与其他代理通信，产品页面演示了这些功能。 这标志着从基于提示词的 AI 交互向基于代理的协作转变，有人视之为 AI 界面的自然下一步。它可能改变用户向 AI 委派任务的方式，同时也引发了关于安全性和数据访问的严重问题。 Grok Bot 已在 x.ai 上线，同时 Grok 3 也已向 Telegram Premium 订阅者免费提供。该代理被设计为在用户睡觉时继续工作，但社区成员指出，持续访问用户账户会增加凭证窃取、提示注入和数据泄露的风险。

hackernews · rvz · 8月11日 17:23 · [社区讨论](https://news.ycombinator.com/item?id=49261514)

**背景**: AI 代理是一种使用大语言模型自主执行任务的软件系统，负责管理提示词、上下文、工具、记忆和权限。xAI 的 Grok 是一款聊天机器人，具备语音聊天、图像和视频生成、实时搜索和高级推理等功能。Grok Bot 将该概念扩展为常驻式多代理协作，每个代理拥有自己的例程和基于云的环境。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://x.ai/">SpaceXAI</a></li>
<li><a href="https://news.google.com/stories/CAAqNggKIjBDQklTSGpvSmMzUnZjbmt0TXpZd1NoRUtEd2lvbktubEVSRXpiVHZIZkxpemppZ0FQAQ?hl=en-US&amp;gl=US&amp;ceid=US:en">Google News - SpaceXAI introduces Grok Bot AI agents for work...</a></li>
<li><a href="https://t.me/GrokAI">Telegram: Launch @GrokAI</a></li>

</ul>
</details>

**社区讨论**: 社区反应不一：有人称赞 Grok Bot 是自然的演进，并觉得与代理的交互出奇地直观；也有人对常驻代理拥有完整账户访问权表示焦虑，担心提示注入、凭证窃取和数据删除。还有评论者质疑机器人抓取服务的问题，指出企业一边提供机器人、一边使用反机器人系统的矛盾。

**标签**: `#AI`, `#Agents`, `#Security`, `#xAI`, `#Product Launch`

---

<a id="item-5"></a>
## [伦敦地铁扩大活体面部识别试验](https://www.btp.police.uk/news/btp/news/england/btp-expands-live-facial-recognition-lfr-trial-into-london-underground-stations/) ⭐️ 8.0/10

英国交通警察已将活体面部识别（LFR）试验扩展到伦敦地铁站，实时扫描乘客面部并与观察名单比对。该试验旨在定位通缉人员，但引发了关于公共场所监控的新一轮辩论。 此次扩展将面部识别监控带入世界上最繁忙的交通网络之一，影响每天成千上万的通勤者。它引发了关于隐私、同意以及生物识别追踪在日常生活中常态化的重大问题，并可能影响其他地区的警务实践。 该试验在地铁站使用实时摄像头，将面部与嫌疑犯观察名单实时比对。英国交通警察称这是一种精准打击犯罪的策略，但批评者指出，试验不太可能产生能阻止规模扩大的“失败”结果。

hackernews · BlueBerry2001 · 8月11日 09:40 · [社区讨论](https://news.ycombinator.com/item?id=49255496)

**背景**: 活体面部识别（LFR）是一种利用摄像头实时检测人脸并与预设关注名单进行比对的技术。当发现可能匹配时，系统会产生警报供警方采取行动。该技术被用于警务工作以定位通缉犯和提高公共安全，但因隐私和公民自由方面的担忧而备受争议。英国交通警察一直在伦敦试用 LFR，此次扩展到地铁站标志着新阶段。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.wa.gov.au/organisation/western-australia-police-force/live-facial-recognition-technology">Live Facial Recognition Technology | Western Australian Government</a></li>
<li><a href="https://www.linkedin.com/pulse/we-ready-live-facial-recognition-insight-security-uk-uax1e">Are We Ready for Live Facial Recognition</a></li>
<li><a href="https://www.beds.police.uk/police-forces/bedfordshire-police/areas/about-us/about-us/live-facial-recognition-lfr-technology/">Live Facial Recognition ( LFR ) technology | Bedfordshire Police</a></li>

</ul>
</details>

**社区讨论**: 评论者大多对这一扩张持批评态度，有人指出无接触支付已经侵蚀了地铁匿名出行。还有人将英国描述为‘奥威尔式’或将其与信用评分体系相提并论，另有人质疑这样的试验怎么可能得出监控与自由社会不相容的结论。

**标签**: `#privacy`, `#surveillance`, `#facial-recognition`, `#civil-liberties`, `#uk`

---

<a id="item-6"></a>
## [英伟达的风险生意：增长假设与 CUDA 护城河受质疑](https://stratechery.com/2026/nvidias-risky-business/) ⭐️ 8.0/10

Stratechery 的一篇分析审视了英伟达商业模式中的风险，指出虽然 AI 算力需求确实真实，但关于需求增长和 CUDA 软件生态护城河持久性的二阶假设可能被夸大。该文强调，英伟达的估值依赖于可能过于乐观的预期。 这很重要，因为英伟达已成为 AI 基础设施的主导供应商，其市值部分基于 CUDA 创造不可逾越软件护城河的信念。如果增长预期过高或软件护城河受到侵蚀，可能对整个 AI 行业和半导体供应链产生重大影响。 该分析区分了一阶假设（计算需求是真实的）和二阶假设（需求增长率），而投资论点往往在后者上失败。文章还聚焦于 CUDA——英伟达专有的并行计算平台——认为它既是关键护城河，也可能因其复杂的开发者体验而成为潜在弱点。

hackernews · jonbaer · 8月11日 10:02 · [社区讨论](https://news.ycombinator.com/item?id=49255710)

**背景**: 英伟达的 GPU 已成为训练大型 AI 模型的标准，而 CUDA 是允许开发者利用这些 GPU 进行通用计算的软件层。多年来，CUDA 已深度嵌入机器学习研究和 PyTorch 等工具中，形成了许多人认为的强大生态护城河。然而，英伟达的高估值不仅取决于当前需求，还取决于持续的指数级增长，其软件主导地位也并非不受颠覆影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/CUDA">CUDA - Wikipedia</a></li>
<li><a href="https://medium.com/@tahirbalarabe2/what-is-nvidia-cuda-4013e5f4deb5">What is Nvidia CUDA ?. what NVIDIA CUDA is, how GPU... | Medium</a></li>
<li><a href="https://developer.nvidia.com/cuda?ref=dataphoenix.info">CUDA Platform for Accelerated Computing | NVIDIA Developer</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍赞赏这一细致入微的分析，多人同意英伟达的需求是真实的，但增长预期可能被夸大。有人指出，CUDA 的主导地位更多来自生态锁定而非工程品质；还有人提到英伟达已在布局机器人领域，并且仍是西方市场的主要玩家。也有质疑观点认为，从生物智能的比较来看，当前 AI 硬件和软件是否真能带来社会经济奇点尚存疑问。

**标签**: `#Nvidia`, `#AI infrastructure`, `#CUDA`, `#business strategy`, `#semiconductors`

---

<a id="item-7"></a>
## [KVM planes 抽象层旨在统一安全域功能](https://lwn.net/Articles/1087590/) ⭐️ 8.0/10

Jörg Rödel、Paolo Bonzini 和其他 KVM 开发者正在开发“KVM planes”，这是一个抽象层，旨在统一 Linux 系统上多种硬件辅助安全域功能。该层仍处于开发阶段，计划向用户空间提供统一接口。 AMD 和 Intel 等硬件厂商各自以不同方式实现安全域功能，导致 Linux 虚拟化生态碎片化。KVM planes 这一统一抽象层能让 AMD SEV-SNP、Intel TDX 等机密计算技术更易于使用和管理，可能加速其普及。 LWN 文章介绍了相关补丁，包括用于 plane 间中断的 KVM\_EXIT\_PLANE\_EVENT，最后将 capability 暴露给用户空间，以及测试用例。由于每家的方案（如 AMD SEV 和 Intel TDX）差异很大，这项工作并不简单。

rss · LWN.net · 8月11日 14:48

**背景**: KVM（基于内核的虚拟机）是 Linux 的虚拟化基础设施，它让内核本身充当 hypervisor。在机密计算中，AMD 的安全加密虚拟化（SEV）和 Intel 的信任域扩展（TDX）等硬件特性会创建受保护的、隔离的 guest 安全域，但各自的编程模型互不相同。KVM planes 希望通过一个通用抽象层隐藏这些差异，使 guest 操作系统和管理工具更容易使用多种此类技术。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://servermall.com/blog/amd-sev-and-intel-tdx-who-needs-it/">AMD SEV-SNP vs Intel TDX: Who Actually Needs Confidential VMs in 2026 🔐</a></li>
<li><a href="https://sys.cs.fau.de/extern/lehre/ws22/akss/material/amd-sev-intel-tdx.pdf">General overview of AMD SEV-SNP and Intel TDX Kevin Kollenda ABSTRACT</a></li>
<li><a href="https://dl.acm.org/doi/10.1145/3700418">Confidential VMs Explained: An Empirical Analysis of AMD SEV-SNP and Intel TDX | Proceedings of the ACM on Measurement and Analysis of Computing Systems</a></li>

</ul>
</details>

**标签**: `#KVM`, `#virtualization`, `#Linux kernel`, `#security`, `#abstraction layer`

---

<a id="item-8"></a>
## [阿里云发布新一代全模块化 AI 数据中心架构](https://news.google.com/rss/articles/CBMiYkFVX3lxTE9hQzQzMnJ1Ni1ESTFPQ0dxdWFaOG9QYlVwbHlBSWxXYnY4YzFmTGhucElaU0YweHJrRlByUTZuV1hTM0tWVjZOS0N1M0ZLUHpBcUFCYzJ0Qm9FMnk1NHRDMDJn?oc=5) ⭐️ 7.0/10

阿里云宣布推出面向 AI 数据中心的新一代全模块化架构。据观点网报道，该设计被视为公司在 AI 基础设施路线上的重大更新。 作为全球最大的云服务商之一，阿里云转向模块化 AI 数据中心，可能加快 AI 部署并降低建设与运营成本。这表明各大超大规模云厂商正在竞相让 AI 基础设施更灵活、可扩展且节能。 该公告提供的技术细节有限，因此具体的模块规格、冷却设计或部署时间表尚未公开。在模块化数据中心设计中，计算、供电和制冷通常封装为预制单元，可快速组装和扩展。

google\_news · 观点网 · 8月12日 00:19

**背景**: 模块化数据中心由预制的、专门设计的模块组成，这些模块可运输并组合，以提供可扩展的容量和灵活的供电与冷却方案。随着 AI 工作负载的增长，超大规模数据中心正从单体设计转向分布式、模块化架构，以便更快部署并适应 GPU 密集型计算。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Modular_data_center">Modular data center - Wikipedia</a></li>
<li><a href="https://blog.equinix.com/blog/2023/04/28/what-are-modular-data-centers-and-how-can-they-help/">What are Modular Data Centers and How Can They Help? - Interconnections - The Equinix Blog</a></li>

</ul>
</details>

**标签**: `#AI infrastructure`, `#data center`, `#Alibaba Cloud`, `#modular architecture`, `#cloud computing`

---

<a id="item-9"></a>
## [新基准揭示大模型自主科研能力有限](https://news.google.com/rss/articles/CBMiiwFBVV95cUxPNXY1MGY0ZVlxSDlnNzgzLUYxSXlickFoeFFnRjBHSmVPNG54ZGhnTk9WLVoxYWxHbGtXdEJjRk1NNVY5Um05eEtJNXRIVEtMTFV6SjB3UnFnZ3FWUFFQbjZNV2RraXVJS2tpSnExOC00N2JYSWtNSEw3dkFPVkJSLWczZG9Iel9uekFJ?oc=5) ⭐️ 7.0/10

来自华盛顿大学和加州大学的研究人员推出了名为 Auto-Research 的新基准，用于评估大语言模型在自主科研中的表现。该基准被称为 AI Agent 的‘终极大考’，据称暴露了许多模型只是表面模仿科研技能，在真实的端到端流程中会失败。 该基准具有重要意义，因为它为评估科研发现中的 AI Agent 设定了更高标准，而这一领域正受到学术界和产业界越来越多的关注。它可能促使开发者不再满足于狭隘的任务指标，而是构建能够真正完成从假设生成到验证全流程的系统。 Auto-Research 类基准通常在容器化环境中运行模型，提供可执行任务、评分指标、参考基线和专家解决方案轨迹。新基准的‘终极大考’形式很可能测试完整的研究流程，而大模型在这种场景下往往表现不佳，尽管在孤立子任务上表现强劲。

google\_news · 新浪财经 · 8月12日 01:02

**背景**: 自主科研 Agent 是旨在主动推动科学探究的 AI 系统，它们不仅能回答问题，还能进行实验设计和发现。这类 Agent 的基准会评估模型在规划、信息收集和生成可复现结果方面的能力。诸如 AI-Researcher（NeurIPS 2025）等项目已致力于实现全流程自动化，因此像 Auto-Research 这样严格的评估框架对于区分真实能力与炒作至关重要。然而，auto-research 循环很容易在单个任务上过拟合，因此设计良好的基准必须促使系统具备泛化能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://bakeai.inc/use-cases/auto-research/">Auto Research Benchmark &amp; Expert Data for Autonomous... | Bake AI</a></li>
<li><a href="https://github.com/hkuds/ai-researcher">GitHub - HKUDS/AI-Researcher: [NeurIPS2025] &quot;AI-Researcher: Autonomous Scientific Innovation&quot; -- A production-ready version: https://novix.science/chat · GitHub</a></li>
<li><a href="https://www.sapiosciences.com/blog/agentic-ai-for-scientific-research-autonomous-agents-transforming-experiment-design/">Agentic AI for Scientific Research: Autonomous agents transforming experiment design | Sapio Sciences</a></li>

</ul>
</details>

**标签**: `#AI`, `#LLM`, `#benchmark`, `#research`, `#machine learning`

---

<a id="item-10"></a>
## [高盛：今年全球 AI 投资将突破万亿美元](https://news.google.com/rss/articles/CBMiSEFVX3lxTE05d1ZOeW5OMTJmay1xRmQ0dXBheEpkaWc1NjJObTVERHFkdGQ3QWppSkVGRlFOM2Jsa1FXb2tqbXNqc0JNbnNTdA?oc=5) ⭐️ 7.0/10

高盛预测今年全球人工智能（AI）投资将突破 1 万亿美元，其中美国投资接近 6000 亿美元。 这一预测表明人工智能正成为万亿美元级别的经济力量，将影响投资者、科技公司和政策制定者。如果实现，这将是历史上最大的科技投资周期之一，重塑资本流向和行业竞争格局。 该数据来自高盛的市场预测，美国投资约占全球总额的 60%。预测针对今年，但公告中未详细说明具体支出类别。

google\_news · 财联社 · 8月11日 16:40

**背景**: 人工智能投资通常指用于 AI 基础设施（如数据中心、芯片和模型开发）以及各行业应用部署的资本支出。高盛是全球领先的投资银行，其市场预测备受机构投资者和政策制定者关注。

**标签**: `#AI`, `#Investment`, `#Economics`, `#Goldman Sachs`, `#Market Forecast`

---