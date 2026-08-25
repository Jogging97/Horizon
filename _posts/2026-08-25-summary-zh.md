---
layout: default
title: "Horizon Summary: 2026-08-25 (ZH)"
date: 2026-08-25
lang: zh
---

> 从 100 条内容中筛选出 9 条重要资讯。

---

1. [画图和照片应用为本地图像添加不可见 GUID 水印](#item-1) ⭐️ 8.0/10
2. [Jabber/XMPP 25 周年：回顾数字独立与开放消息](#item-2) ⭐️ 8.0/10
3. [seL4 安全证明现已完整覆盖 AArch64](#item-3) ⭐️ 8.0/10
4. [AI 依赖或致编程专业技能崩溃，文章引发热议](#item-4) ⭐️ 8.0/10
5. [SQLite 数据库文件可直接作为 Linux 可执行程序](#item-5) ⭐️ 8.0/10
6. [量子计算对 ECDSA 的威胁：为后量子密码学做好准备](#item-6) ⭐️ 8.0/10
7. [Unbounded Labs 用 1931 年前的英文文本训练复古 LLM](#item-7) ⭐️ 8.0/10
8. [中国 AI 飞跃幕后的智囊：华尔街日报人物侧写](#item-8) ⭐️ 7.0/10
9. [OpenAI 评欧盟 AI 行为准则与欧洲未来](#item-9) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [画图和照片应用为本地图像添加不可见 GUID 水印](https://xusheng.dev/posts/reversing/mspaint_invisible_watermark/main/) ⭐️ 8.0/10

一篇逆向工程文章揭露，微软画图（Paint）和照片（Photos）应用会向图像嵌入基于 GUID 的不可见水印，即使是本地生成且用户未开启任何水印功能时也会发生。该不可见水印无法关闭，会在后台静默添加。 这引发了严重的隐私和匿名性问题，因为每个水印都与可关联到微软账户的唯一 GUID 绑定，一旦图像被传唤，可能暴露用户的身份和联系方式。这也表明消费级软件正趋向于采用隐藏的取证式水印这一更广泛的行业趋势。 根据引用原始分析的评论，画图和照片应用会对经过 AI 处理的图像同时添加可见水印（可关闭）和不可见水印（无法禁用），即使使用本地模型也是如此。不可见水印嵌入在图像的像素数据中而非仅存在于元数据中，因此难以检测和移除。

hackernews · ComputerGuru · 8月24日 15:28 · [社区讨论](https://news.ycombinator.com/item?id=49421158)

**背景**: GUID（全局唯一标识符）是一种 128 位数字，用于标识计算机系统中的信息，通常由微软软件生成。不可见水印是一种隐写技术，将数据嵌入图像中，人眼无法察觉，但可被算法检测到。此类水印通常用于内容保护和取证追踪，但在消费级应用中静默嵌入引发了关于用户同意和数据隐私的质疑。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Universally_unique_identifier">Universally unique identifier - Wikipedia</a></li>
<li><a href="https://www.techtarget.com/searchwindowsserver/definition/GUID-global-unique-identifier">What is GUID?</a></li>
<li><a href="https://www.imatag.com/digital-watermarking">Invisible Digital Watermarking | The smart way to protect your online content</a></li>

</ul>
</details>

**社区讨论**: 社区反应大多持批评态度。一位用户认为 AI 方面是转移视线，真正的问题在于秘密添加的唯一标识符，这使得版权传票可以要求微软提供用户的个人数据。另一位用户提醒微软过去在水印实现上草率，举了 Copilot 标记被错误应用到 Azure DevOps 提交的案例，并建议不要使用画图或其他启用 LLM 的应用。一些评论者对画图从简单像素编辑器发生如此大的变化表示惊讶。

**标签**: `#privacy`, `#watermarking`, `#Microsoft`, `#AI`, `#surveillance`

---

<a id="item-2"></a>
## [Jabber/XMPP 25 周年：回顾数字独立与开放消息](https://gultsch.de/posts/25-years-of-digital-independence/) ⭐️ 8.0/10

gultsch.de 上的一篇纪念文章庆祝 Jabber/XMPP 协议诞生 25 周年，肯定其作为去中心化消息标准的地位，并讨论其当前的相关性。这个周年纪念引发了社区的热烈讨论，话题涉及协议历史、现有项目以及它给开放通信带来的启示。 25 年来，XMPP 一直是联邦式消息领域最古老、最具影响力的开放协议之一；这篇回顾提醒人们，在围墙花园平台盛行的时代，数字独立依然意义重大。它引发的讨论也深化了与 Matrix 等新协议的对比，对评估去中心化通信技术的人很有价值。 文章及其评论提到了一些实际的 XMPP 部署，包括 jmp.chat 等短信/电话桥接服务，Dino、Cheogram、Conversations、Movim 等客户端，以及 Prosody、ejabberd 等服务器。有社区成员认为 Matrix 是“重新发明轮子”而不是在 XMPP 基础上改进，也有人好奇近年来大型公共 Jabber 社区都去了哪里。

hackernews · inputmice · 8月24日 15:51 · [社区讨论](https://news.ycombinator.com/item?id=49421536)

**背景**: XMPP 最初名为 Jabber，1999 年出现，是一种基于 XML 流、开放且去中心化的即时消息协议。2000 年代末，Google Talk、Facebook 聊天等服务曾广泛采用它，但后来许多大型提供商转向了专有协议。近年来 XMPP 仍在不断发展，而 Matrix 等新协议也致力于提供联邦式、端到端加密的通信。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/XMPP">XMPP - Wikipedia</a></li>
<li><a href="https://xmpp.org/about/technology-overview/">An Overview of XMPP | XMPP - The universal messaging standard</a></li>
<li><a href="https://en.wikipedia.org/wiki/Matrix_%28protocol%29">Matrix (protocol) - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论总体带有怀旧和积极色彩：有人称赞 XMPP 以及 Movim、Fluux 团队的工作，也有人描述用 ejabberd 和 XMPP 客户端搭建 AI 代理网络的经验。还有人分享了从 Google Voice 迁移到 jmp.chat 的实际经历，并争论 Matrix 的路线是否真的带来架构优势，或者正如一位评论者所说，只是重新发明了轮子并造成供应商锁定。

**标签**: `#XMPP`, `#decentralized messaging`, `#open protocols`, `#Matrix`, `#digital independence`

---

<a id="item-3"></a>
## [seL4 安全证明现已完整覆盖 AArch64](https://proofcraft.systems/news-2026/#2026-08-21) ⭐️ 8.0/10

seL4 微内核的正式安全证明（涵盖机密性、完整性和可用性）现已在 AArch64（64 位 ARM）架构上完成。这标志着 seL4 项目的一个重要里程碑，将其经过验证的保证扩展到最广泛使用的处理器家族之一。 这一成就显著扩大了 seL4 可部署的范围，使其具备最高保证，包括依赖 ARM 硬件的汽车、航空电子等关键嵌入式系统。由于 AArch64 主导移动和嵌入式市场，这一证明使得正式验证对更多类别的现实世界设备变得实用。 正如社区回应所指出的，该证明目前仅适用于非 MCS（混合关键性系统）配置和单核（unicore）系统。它也不涉及侧信道时序攻击，这仍然是已验证 seL4 设计的一个已知局限。

hackernews · snvzz · 8月24日 11:32 · [社区讨论](https://news.ycombinator.com/item?id=49418255)

**背景**: seL4 是一个开源、高保证、基于能力（capability）的微内核，使用正式数学验证来证明机密性、完整性和可用性等属性。正式验证通过数学方法确凿地确定系统满足其规范，不同于只检查特定情况的测试。AArch64 是 ARM 架构的 64 位执行状态，广泛用于智能手机、嵌入式设备和服务端。在 AArch64 上完成证明意味着针对 ARM 指令集语义验证 seL4 的实现，在机器码层面提供端到端的安全保证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/SeL4">seL4 - Wikipedia</a></li>
<li><a href="https://sel4.systems/About/">What is seL4? | seL4</a></li>

</ul>
</details>

**社区讨论**: 社区评论意见不一：一位用户预测侧信道时序攻击可能会使该结果失效，另一位用户则指出了非 MCS 和仅限单核（unicore）范围的“细则”局限。其他人讨论了 seL4 的实际采用者——如 GenodeOS、LionsOS，以及一家中国汽车制造商将其用作车载 hypervisor——并认为 seL4 需要类似本地 Linux 的环境，才能诚实地宣称其能力模型改善系统安全性。

**标签**: `#seL4`, `#formal verification`, `#security`, `#microkernel`, `#AArch64`

---

<a id="item-4"></a>
## [AI 依赖或致编程专业技能崩溃，文章引发热议](https://larsfaye.com/articles/ai-coding-will-prevent-expertise) ⭐️ 8.0/10

作者 Lars Faye 撰文指出，过度依赖 AI 编程工具会侵蚀开发者的深层专业技能，最终可能导致编码能力的“崩溃”。这篇文章在 Hacker News 上引发大量讨论，获得 478 分和 472 条评论。 这很重要，因为随着 AI 辅助编程工具的普及，行业可能面临未来缺乏能够维护复杂系统的资深开发者的风险，进而影响软件质量和创新。这场辩论突出了短期生产力与长期技能培养之间的核心矛盾。 文章副标题强调“长期技能培养中持续摩擦的必要性”，暗示深度学习需要挑战和阻力。评论者指出，虽然“氛围编程”（vibe coding）很流行，但“引导式编程”（guided coding）提供了一条折中之路，既能保持专业性又能产出更高质量的代码。

hackernews · larsfaye · 8月24日 15:52 · [社区讨论](https://news.ycombinator.com/item?id=49421554)

**背景**: 软件手工艺（Software Craftsmanship）是一场强调开发者编程技能和责任感的运动，是对主流软件行业过度关注财务问题的回应。大语言模型（LLM）是在海量文本上训练的人工智能模型，能够生成、总结和分析代码，是 AI 辅助编程工具的基础。AI 辅助软件开发工具列表的快速扩充反映了这类工具的增长态势，也为本文关于 LLM 可能削弱软件工匠技能的论点提供了背景。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Software_craftsmanship">Software craftsmanship</a></li>
<li><a href="https://en.wikipedia.org/wiki/Large_language_model">Large language model - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/List_of_AI-assisted_software_development_tools">List of AI-assisted software development tools - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 讨论大多支持文章前提；用户 ryandvm 指出，企业强制要求 AI 生成代码，导致代码产出速度超过人类能够理解和审查的速度。apatheticonion 则反驳说，在 Zed 或 VSCode 等编辑器中使用集成的 LLM 进行“引导式编程”，其生产力不亚于氛围编程，同时质量更高且能保留专业技能。xyzelement 和 LandoCalrissian 补充道，一些开发者主动寻求挑战，而当前 AI 依赖的趋势不可持续。

**标签**: `#AI`, `#Software Engineering`, `#Coding`, `#Expertise`, `#LLM`

---

<a id="item-5"></a>
## [SQLite 数据库文件可直接作为 Linux 可执行程序](https://simonwillison.net/2026/Aug/24/your-executable-is-a-sqlite-database/) ⭐️ 8.0/10

Farid Zakaria 的 selfdb 项目演示了一种 Linux 模式：通过将 ELF 可执行文件组件存入 SQLite 数据表，并借助自定义的 self-exec 解释器，SQLite 数据库文件可直接作为二进制程序执行。 这一技巧创造性地融合了 SQLite 与 ELF 文件格式，模糊了数据与代码之间的界限。对于探索多语言文件（polyglot files）、自定义解释器以及基于 binfmt\_misc 的可执行格式的系统程序员而言，具有重要意义。 该技巧将 SQLite 文件偏移 68 处的 4 字节 application ID 设置为“SELF”（Structured Executable &amp; Linkable Format），并使用 self.sql 模式将 ELF 的各个组成部分存储在多张 SQLite 表中。内核可通过 binfmt\_misc 注册识别该模式，例如：&\#x27;:self:M:68:SELF::/usr/local/bin/self-exec:&\#x27;。

rss · Simon Willison · 8月24日 11:38

**背景**: ELF（Executable and Linkable Format）是 Linux 上可执行文件和共享库的标准二进制格式。SQLite 数据库将数据保存在单个文件中，其固定 100 字节的文件头包含位于第 68–71 字节的 application ID 字段，用于标识应用程序文件格式。binfmt\_misc 是 Linux 内核的一项功能，允许注册任意二进制格式并由用户空间处理程序执行。selfdb 项目结合这些概念，使一个数据库文件既可以作为有效的 SQLite 数据库，又可以作为可执行程序。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Binfmt_misc">binfmt _ misc - Wikipedia</a></li>
<li><a href="https://sqlite.org/pragma.html">Pragma statements supported by SQLite</a></li>
<li><a href="https://en.wikipedia.org/wiki/Executable_and_Linkable_Format">Executable and Linkable Format - Wikipedia</a></li>

</ul>
</details>

**标签**: `#SQLite`, `#Linux`, `#ELF`, `#executable`, `#systems programming`

---

<a id="item-6"></a>
## [量子计算对 ECDSA 的威胁：为后量子密码学做好准备](https://lwn.net/Articles/1088305/) ⭐️ 8.0/10

LWN 的一篇文章分析了近期量子计算研究，这些研究降低了破解 ECDSA 密钥所需的内存，公开的研究成果将内存使用量比 2023 年的最先进水平降低了一半以上。文章还列出了为后量子密码学做好准备所需的配置和协议更改。 实用的量子计算机可能在几年内出现，而 ECDSA 广泛应用于 TLS 证书、代码签名和加密货币中。由于软件更新传播缓慢，现在就开始向后量子算法迁移对于避免“Y2Q”安全危机至关重要。 文章引用了以混淆结果形式发表的研究，该研究表明在量子计算机上分解 ECDSA 密钥所需的内存大幅降低；而 ecdsa.fail 上的公开研究比 2023 年的最先进水平将内存使用量降低了一半以上。文章还指出，计算机制造商正在宣传具有更持久叠加态的量子处理器。

rss · LWN.net · 8月24日 14:57

**背景**: 包括 ECDSA 在内的大多数公钥算法依赖于椭圆曲线离散对数问题的难度，而 Shor 算法可以在足够强大的量子计算机上高效解决该问题。后量子密码学（PQC）是开发被认为能抵御量子攻击的算法的学科；NIST 于 2024 年发布了首批三个 PQC 标准。由于迁移需要数年时间，密码学家建议现在就做准备，Mosca 定理对此概念进行了形式化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Post-quantum_cryptography">Post-quantum cryptography</a></li>
<li><a href="https://en.wikipedia.org/wiki/Shor&#x27;s_algorithm">Shor&#x27;s algorithm</a></li>

</ul>
</details>

**标签**: `#quantum computing`, `#cryptography`, `#ECDSA`, `#security`, `#post-quantum`

---

<a id="item-7"></a>
## [Unbounded Labs 用 1931 年前的英文文本训练复古 LLM](https://www.reddit.com/r/MachineLearning/comments/1vx94er/bart_a_vintage_llm_r/) ⭐️ 8.0/10

Unbounded Labs 发布了 Bart，一个从头训练的 2.82B 参数 LLM，使用 1931 年前英语文本的 201 亿个 token，同时发布了最大的复古 SFT 数据集（41.6 万对）和名为 Vintage CORE 的 20 项基准测试套件。 这是一次罕见的尝试，用于测试在时代合适的数据上训练的 LLM 能否重新发现历史性的科学见解，回应了 Demis Hassabis 的假设。该项目还提供了开源数据集和基准测试，可能促进对领域特定和历史基础模型的进一步研究。 Bart 在单个 H100 GPU 上训练了五天，MFU 达到 60%，成本约 807 美元。团队将哈佛大学机构藏书从 2420 亿 token 筛选到 230 亿 token，并通过自主实验（100 次运行，26 项改进）来优化训练。

reddit · r/MachineLearning · /u/soggydoggy8 · 8月24日 17:20

**背景**: 大型语言模型通常在大量现代互联网文本上进行预训练，因此它们反映了当代语言和知识。使用 1931 年前的英语等档案文本进行训练，使研究人员能够探讨模型是否能独立得出早期时代的科学结论。消融研究通过移除组件来测量其贡献，用于验证设计选择，而后训练（如 SFT）则对基础模型进行微调以使其遵循指令。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Ablation_%28artificial_intelligence%29">Ablation (artificial intelligence) - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Post-training_of_large_language_models">Post-training of large language models</a></li>

</ul>
</details>

**标签**: `#LLM`, `#NLP`, `#AI research`, `#training`, `#historical text`

---

<a id="item-8"></a>
## [中国 AI 飞跃幕后的智囊：华尔街日报人物侧写](https://news.google.com/rss/articles/CBMimAFBVV95cUxObVFFZExpS1RKc3IwRThDMUdrZi1PZlR1bEVnUjdBQk11RDlVMzNlajVwYWFTY0wzVEhkMHNQdUVYNkpXaFhlWDBVWnIxaWtWNnpfVERadktBUjBfeThsLWEtVEhVTi1KVHdyaTZXcnVNQlVmNWxnX25DVTRpOW5ZeWgxOFZYX3lJNDlvaTRoRVR4UFE5aXRSag?oc=5) ⭐️ 7.0/10

《华尔街日报》的一篇报道（由端傳媒转载）介绍了推动中国人工智能取得惊人进展的关键幕后智囊。文章着重讲述了此人如何凭借远见与统筹，助推中国 AI 实力在全球舞台上快速崛起。 这篇人物报道之所以重要，是因为它揭示了支撑中国 AI 快速崛起的战略决策与人才力量，而这正是全球科技竞争与政策博弈的核心议题。了解中国 AI 方向背后的关键人物，有助于各国政府、投资者和研究者预判其未来布局。 原报道将焦点放在一位核心规划者身上，而非机构层面的集体努力，以幕后视角展示了顶层战略如何转化为具体的 AI 突破。总部位于香港的端傳媒以中文呈现转载此文，方便中文读者阅读。

google\_news · 端傳媒Initium Media · 8月24日 23:25

**背景**: 中国在 AI 领域领先的雄心最早于 2017 年以《新一代人工智能发展规划》正式确立，设定了到 2030 年成为世界 AI 领导者的分阶段目标。此后，中国政府进一步推行“人工智能+”行动，推动 AI 与各行业深度融合。北京智源人工智能研究院（BAAI）等机构也作为连接学术界、产业界和顶尖人才的协作平台迅速崛起。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.qstheory.cn/2026-06/02/c_1187498.htm">AI -driven innovation opens new possibilities for smart living in China</a></li>
<li><a href="https://english.www.gov.cn/policies/latestreleases/202508/27/content_WS68ae7976c6d0868f4e8f51a0.html">China issues guideline to accelerate &#x27;AI Plus&#x27; integration ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Beijing_Academy_of_Artificial_Intelligence">Beijing Academy of Artificial Intelligence</a></li>

</ul>
</details>

**标签**: `#AI`, `#China`, `#Technology`, `#Research`, `#Policy`

---

<a id="item-9"></a>
## [OpenAI 评欧盟 AI 行为准则与欧洲未来](https://news.google.com/rss/articles/CBMic0FVX3lxTE9LbGxGNGtLZFZqVS1aUXVaQmFaNF85NEhWekhmVUp3WjlRc0VVeXdISTVFVkpaZmk2UVIyUU44ZTB6U01OZk1qTzZVTTZFOUJwNXhQOFNNRjU0VzFJLV9pV2lDV2ljaUxoNnQxTVQ0STRCLWM?oc=5) ⭐️ 7.0/10

OpenAI 已就欧盟《人工智能行为准则》发表看法，阐述了该框架可能如何影响欧洲 AI 的开发与部署。该声明是对欧盟不断演进的 AI 监管格局的直接回应。 作为全球领先的 AI 开发商之一，OpenAI 的立场可能影响其他公司应对欧盟合规的方式，并有助于塑造《人工智能法案》的实际执行。欧盟的监管路径正被全球视为 AI 治理的潜在范本。 欧盟《人工智能法案》已于 2024 年 8 月 1 日生效，而《行为准则》旨在帮助通用人工智能（GPAI）模型开发者满足法案要求。OpenAI 发表声明时，《行为准则》仍在起草中，其中详细规定了高能力模型在透明度和安全方面的义务。

google\_news · OpenAI · 8月24日 08:09

**背景**: 欧盟《人工智能法案》是主要监管机构首次对人工智能进行全面监管，根据风险水平将 AI 应用分为不可接受、高风险、有限风险和低风险等类别。《行为准则》是一个自愿性框架，旨在澄清 ChatGPT 等通用 AI 的提供者如何遵守该法案。OpenAI 的参与反映了领先 AI 公司与寻求平衡创新与安全的政策制定者之间日益密切的互动。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://artificialintelligenceact.eu/">EU Artificial Intelligence Act | Up-to-date developments and analyses of the EU AI Act</a></li>
<li><a href="https://en.wikipedia.org/wiki/EU_AI_Act">EU AI Act</a></li>
<li><a href="https://www.fahadhussain.com/the-eus-ai-code-is-brave-but-insufficient/">The EU &#x27;s AI code is brave-but insufficient - Fahad Hussain</a></li>

</ul>
</details>

**标签**: `#AI regulation`, `#EU`, `#OpenAI`, `#policy`, `#artificial intelligence`

---