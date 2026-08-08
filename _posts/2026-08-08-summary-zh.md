---
layout: default
title: "Horizon Summary: 2026-08-08 (ZH)"
date: 2026-08-08
lang: zh
---

> 从 105 条内容中筛选出 12 条重要资讯。

---

1. [SGLang v0.5.17 发布：首日支持 Kimi K3 2.8T MoE 模型](#item-1) ⭐️ 8.0/10
2. [DeepSeek V4 Flash 0731：快速、强大、低成本的模型更新](#item-2) ⭐️ 8.0/10
3. [汇编耻辱堂：盘点慢得出奇的 x86 指令](#item-3) ⭐️ 8.0/10
4. [科技从业者普遍失落，引发行业文化反思](#item-4) ⭐️ 8.0/10
5. [OpenAI 宣布对关键网络能力实施更严格安全控制与隔离测试](#item-5) ⭐️ 8.0/10
6. [Oracle 禁止向 OpenJDK 贡献 AI 生成的代码](#item-6) ⭐️ 8.0/10
7. [AI 带动 HBM 需求，2027 年内存产能已被订满](#item-7) ⭐️ 8.0/10
8. [人工智能被用于设计全新病毒，BBC 报道](#item-8) ⭐️ 8.0/10
9. [DeepSeek 斥资 1.4 亿元参与宇树科技战略配售](#item-9) ⭐️ 7.0/10
10. [宇树科技 IPO 路演：近半募资投向&quot;大脑&quot;研发](#item-10) ⭐️ 7.0/10
11. [谷歌 AI 重组：商业化压力让科研愿景退居其次](#item-11) ⭐️ 7.0/10
12. [存储芯片巨头千亿元大动作](#item-12) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [SGLang v0.5.17 发布：首日支持 Kimi K3 2.8T MoE 模型](https://github.com/sgl-project/sglang/releases/tag/v0.5.17) ⭐️ 8.0/10

SGLang 发布了 v0.5.17，为首日支持 Moonshot AI 的 Kimi K3（一个 2.8 万亿参数的多模态 LatentMoE 模型）加入了完整服务能力。该版本还引入了 MiniMax-H3 视频生成支持、Rust 前端，以及多项推理优化（如用于 MoE 预填充的 DWDP）。 Kimi K3 是一个参数规模达 2.8 万亿、上下文长度达 100 万 token 的超大模型，主流推理框架的首日支持使其能够被尽早采用和测试。本版本还通过 KDA 感知前缀缓存、DSpark 投机解码等技术推动了 LLM 推理基础设施的发展，使更广泛的 AI 服务生态受益。 Kimi K3 采用 LatentMoE 架构，包含 896 个专家并使用 top-16 路由，将 69 个 KDA 线性注意力层与 24 个 MLA 层交错排列，并以原生 MXFP4 4 位精度发布。该版本已在 NVIDIA GB300 和 AMD MI35x 上验证，包含来自 194 位贡献者的 582 个 PR，特性涵盖 DCP 通信后端到会话引用感知的统一 radix 缓存等。

github · Fridge003 · 8月8日 00:19

**背景**: MoE（混合专家）模型每个 token 只激活全部参数中的一部分，这使得模型能够扩展到万亿参数规模，同时保持可接受的推理成本。LatentMoE 通过低维潜在空间进行路由并共享专家权重，减轻了内存带宽压力，但仍需要精细的服务优化。MXFP4 是一种基于块缩放因子的 4 位浮点格式，可显著降低内存占用和带宽需求；DSpark 则是一种投机解码框架，将半自回归草稿模型与置信度调度的验证机制相结合，以加速 token 生成。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.emergentmind.com/topics/latentmoe">LatentMoE : Efficient Latent Mixture of Experts</a></li>
<li><a href="https://en.wikipedia.org/wiki/Block_floating_point">Block floating point - Wikipedia</a></li>
<li><a href="https://arxiv.org/abs/2607.05147">[2607.05147] DSpark: Confidence-Scheduled Speculative ...</a></li>

</ul>
</details>

**标签**: `#LLM inference`, `#MoE`, `#SGLang`, `#Kimi K3`, `#AI infrastructure`

---

<a id="item-2"></a>
## [DeepSeek V4 Flash 0731：快速、强大、低成本的模型更新](https://arcprize.org/results/deepseek-v4-flash-0731) ⭐️ 8.0/10

DeepSeek 于 7 月 31 日发布了 DeepSeek V4 Flash 0731，这是其效率导向 MoE 模型（总参数 284B、激活 13B、支持 1M 上下文）的更新版本，取代早前的预览版。用户反馈其速度和能力有显著提升，适合作为日常主力模型。 该版本以极低成本（每百万输入 token 0.07 美元、每百万输出 token 0.18 美元）提供接近前沿的能力，可能给其他提供商带来压力，并扩大高质量 LLM 的普及度。这也表明 DeepSeek 持续在实用型高效大上下文模型方向发力。 该模型采用混合专家（MoE）架构，总参数 284B、激活参数 13B，支持 100 万 token 上下文。用户实测在 2x RTX Pro 6000 Blackwell 上预填充约 8k token/s、单流生成约 250 token/s，即使多会话并发，每日成本也低于 5 美元。

hackernews · tosh · 8月7日 17:56 · [社区讨论](https://news.ycombinator.com/item?id=49214008)

**背景**: DeepSeek-V4-Flash 是 DeepSeek 推出的效率导向混合专家（MoE）模型，属于 DeepSeek-V4 系列，该系列还包括 DeepSeek-V4-Pro（总参数 1.6T、激活 49B）。两个模型都支持 100 万 token 上下文。MoE 架构每个 token 只激活部分参数，从而实现快速推理并降低计算成本。0731 版本是继最初预览版之后的最新更新。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepinfra.com/deepseek-ai/DeepSeek-V4-Flash">deepseek-ai/DeepSeek-V4-Flash - Demo - DeepInfra</a></li>
<li><a href="https://openrouter.ai/deepseek/deepseek-v4-flash">DeepSeek V4 Flash 0423 - API Pricing &amp; Benchmarks | OpenRouter</a></li>
<li><a href="https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash">deepseek-ai/DeepSeek-V4-Flash · Hugging Face</a></li>

</ul>
</details>

**社区讨论**: 评论整体积极：有用户称它“几乎什么都能干，而且便宜到成本可以忽略不计”，即使在 12 个并发流下每日花费也不到 5 美元。另一位用户表示 0731 版本相比预览版“感觉整高一档”，尤其在调试和文档分析方面。不过也有用户提醒，自己的简单测试显示模型在基准测试分布之外会失败，质疑模型是否更偏向为基准而非真实场景优化。

**标签**: `#AI`, `#DeepSeek`, `#LLM`, `#model release`, `#performance`

---

<a id="item-3"></a>
## [汇编耻辱堂：盘点慢得出奇的 x86 指令](https://github.com/xoreaxeaxeax/asm-hall-of-shame) ⭐️ 8.0/10

GitHub 仓库 &\#x27;asm-hall-of-shame&\#x27; 发布，收录了执行速度异常缓慢的 x86 指令。它包含基准测试和最慢指令排行榜，并规定了公平测量的规则。 这个资源对底层程序员、性能工程师和安全研究人员很有价值，因为指令出人意料的慢速既可能导致性能问题，也可能带来新的攻击面。社区讨论表明它已激发出关于 SMM 陷阱和硬件行为的研究。 该仓库的规则规定，对于陷入、模拟或虚拟化的指令，只能计时陷阱本身，而不能计时处理器。当前排行榜中包括一次对 ACPI I/O 端口的 12 毫秒写入，这很可能陷入系统管理模式（SMM）。

hackernews · piotrgrabowski · 8月7日 18:01 · [社区讨论](https://news.ycombinator.com/item?id=49214098)

**背景**: x86 指令的延迟差异很大；简单指令可能只需几个周期，而微码指令或复杂指令则可能慢得多。某些指令会触发陷入固件（如 SMM），造成极大延迟。处理器微码是实现这些复杂指令的低层机制，维基百科和 Stack Overflow 等资源对此有说明。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Microcode">Microcode - Wikipedia</a></li>
<li><a href="https://stackoverflow.com/questions/40366643/what-is-a-microcoded-instruction">assembly - What is a microcoded instruction? - Stack Overflow</a></li>
<li><a href="https://tommesani.com/mmx-isse-latency/">SIMD Instruction Latency Map – Stefano Tommesani</a></li>

</ul>
</details>

**社区讨论**: 评论者将该仓库与相关工作联系起来，例如利用慢速指令攻击 SMI（Retr0id）。kazinator 指出，在具有握手机制的处理上，总线周期可能任意延长；monocasa 认为 12ms 的 ACPI 写入很可能陷入 SMM。layer8 开玩笑说 NOP 应该排第一，因为它做的事无限慢。

**标签**: `#assembly`, `#x86`, `#hardware`, `#low-level`, `#security`

---

<a id="item-4"></a>
## [科技从业者普遍失落，引发行业文化反思](https://www.noemamag.com/why-is-everyone-in-tech-so-sad/) ⭐️ 8.0/10

Noema 杂志发表题为《为什么科技行业里人人都这么悲伤？》的文章，探讨科技从业者日益增长的幻灭感，并引发 Hacker News 上 565 条评论的热烈讨论。文章将该问题概括为整个劳动者群体正逐渐对职业失去信心。 科技行业过去以“改变世界”为自我认同的核心，而普遍的信念丧失可能影响整个行业的人才留存、创新能力与心理健康。这一讨论之所以引发共鸣，是因为它把个人倦怠与科技职业价值评价方式的宏观结构变化联系起来。 评论者注意到文章提出的“工作主义（workism）”框架——即认为工作赋予人生意义的观念——并指出如今的产品已不再像 iPhone 时代那样引起公众兴奋。还有人观察到该帖很快从 Hacker News 首页消失，暗示这个话题可能让社区感到争议或不安。

hackernews · RickJWagner · 8月7日 12:42 · [社区讨论](https://news.ycombinator.com/item?id=49209539)

**背景**: 该文章发表于关注哲学、社会与技术的 Noema 杂志，内容很可能与近年来关于职业倦怠、“安静辞职”和科技行业裁员的讨论有关。“工作主义”（Workism）是一个描述“工作应成为身份与意义主要来源”这种文化期待的术语。Hacker News 的评论区通常被视为普通工程师对行业趋势情绪的风向标，因此回复中的情感基调具有参考意义。

**社区讨论**: 讨论兼具历史类比与个人证词：有评论者将科技从业者比作印刷工——一个因技术变革而消失的古老技能职业；另一位从业 20 年的工程师形容自己会幻想流浪街头，以此表明极度倦怠。还有评论者认为现代网络环境已变得充满敌意，让在线工作本身消耗情绪；也有不少人怀念产品发布会尚有意义的年代。

**标签**: `#tech culture`, `#burnout`, `#mental health`, `#career`, `#industry analysis`

---

<a id="item-5"></a>
## [OpenAI 宣布对关键网络能力实施更严格安全控制与隔离测试](https://openai.com/index/responding-next-frontier-critical-cyber-capabilities/) ⭐️ 8.0/10

OpenAI 发布了一份声明，概述其对“关键网络安全能力”的应对策略，包括对高能力模型实施更严格的安全控制并采用隔离测试环境。根据其 Preparedness Framework，达到“关键网络”阈值的模型必须能在无人干预的情况下识别并开发针对多个加固真实世界关键系统的功能性零日漏洞。 这一声明标志着 OpenAI 明确回应 AI 系统可能达到或超过关键网络安全能力的节点，以及公司的应对计划。它很可能影响 AI 安全政策、网络安全实践，以及高级模型在整个行业中的部署与审计方式。 OpenAI 表示，将针对更高能力模型及相关活动实施更严格的安全控制，包括隔离测试环境，并对智能体应用运维安全措施。Preparedness Framework 将关键网络安全阈值定义为：模型无需人工干预，即可针对许多加固的真实世界关键系统识别并开发各种严重程度的功能性零日漏洞。

hackernews · artninja1988 · 8月7日 16:39 · [社区讨论](https://news.ycombinator.com/item?id=49213029)

**背景**: OpenAI 的 Preparedness Framework 跟踪生物/化学、网络安全和 AI 自我改进等能力，并在部署前评估模型是否达到安全阈值。在网络安全领域，“关键”级别指模型能够自主发现并利用加固真实世界系统中的零日漏洞。OpenAI 表示，目前评估显示即使没有防护措施的高级模型也尚未能在网络等领域构成严重风险，但公司正在为未来情况变化准备控制措施。美国 DHS 也发布了面向关键基础设施的 AI 安全指南，涵盖使用 AI 的攻击、针对 AI 系统的攻击，以及设计与实施失败等风险类别。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/responding-next-frontier-critical-cyber-capabilities/">Responding to the next frontier of critical cyber capabilities | OpenAI</a></li>
<li><a href="https://openai.com/index/updating-our-preparedness-framework/">Our updated Preparedness Framework | OpenAI</a></li>
<li><a href="https://www.dhs.gov/sites/default/files/2024-04/24_0426_dhs_ai-ci-safety-security-guidelines-508c.pdf">Safety and Security Guidelines for Critical Infrastructure ...</a></li>

</ul>
</details>

**社区讨论**: 评论者大多持怀疑态度：有人追问 OpenAI 从未披露首次事件细节，所谓“更严格”是比什么更严格，并认为这种模糊措辞可能是为再次发生做准备。也有人分享了实际使用 Sol 等 AI 工具在几分钟内发现 RCE 漏洞的经验；还有人评价这像是让同一个 AI 同时充当网络安全问题的“原因”和“解决方案”。

**标签**: `#ai-safety`, `#cyber-security`, `#openai`, `#ai-agents`, `#policy`

---

<a id="item-6"></a>
## [Oracle 禁止向 OpenJDK 贡献 AI 生成的代码](https://app.dealroom.co/news/feed/oracle-bans-ai-generated-code-from-openjdk-despite-ellison-s-claim-oracle-isn-t-writing-its-own-code) ⭐️ 8.0/10

Oracle 已出台一项临时政策，禁止 OpenJDK 接受 AI 生成的代码贡献。根据 OpenJDK 法律页面，该政策的最终版本仍由 Oracle 法务团队起草中。 这一政策变化直接影响 Java/OpenJDK 生态系统，为开源项目如何处理 AI 生成的代码及其法律来源树立了重要先例。它也重新引发了关于 AI 生成代码是否具有版权，以及接受来源不明贡献的风险的讨论。 该临时政策发布在 OpenJDK 法律页面上，是针对 AI 生成代码的法律不确定性而制定的。社区成员指出，已有先例表明 AI 生成的代码可能不受版权保护，实际上可能属于公有领域，这与 Oracle 的许可证模式相冲突。

hackernews · delduca · 8月7日 17:36 · [社区讨论](https://news.ycombinator.com/item?id=49213754)

**背景**: OpenJDK 是 Java Platform, Standard Edition（Java SE）的官方参考实现，以 GNU 通用公共许可证（GPL）第 2 版附带链接例外条款发布。代码来源（code provenance）是指代码来自何处、由谁或由什么创建的、可验证的历史记录，对安全和法律合规越来越重要。Oracle 在 Java 版权方面有过法律纠纷历史，这很可能影响了它对 AI 生成贡献持谨慎态度的做法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/OpenJDK">OpenJDK</a></li>
<li><a href="https://www.gitclear.com/help/technical/code_provenance">What is &quot;code provenance&quot; and why does it matter? - GitClear</a></li>
<li><a href="https://nhimg.org/glossary/code-provenance/">What Is Code provenance? Definition &amp; Examples - nhimg.org</a></li>

</ul>
</details>

**社区讨论**: 社区意见不一。一些评论者支持这项禁令，认为 Oracle 希望保留起诉他人不当使用专有代码的能力；另一些人则怀疑该政策能否有效执行。还有几位评论者指出，原文是一篇糟糕的摘要，实际 OpenJDK 政策页面提供了更多上下文。

**标签**: `#OpenJDK`, `#Oracle`, `#AI-generated code`, `#open source`, `#legal`

---

<a id="item-7"></a>
## [AI 带动 HBM 需求，2027 年内存产能已被订满](https://www.ign.com/articles/ramageddon-continues-another-year-as-2027-memory-capacity-is-reportedly-sold-out) ⭐️ 8.0/10

据报道，受 AI 对高带宽内存（HBM）需求激增的推动，2027 年的内存产能已被预订一空。这将限制整体 DRAM 供应，并可能导致整个内存市场价格上涨。 这标志着行业的一个重大转变：AI 硬件需求正在提前数年消化内存制造产能，从而影响 PC、游戏机和手机中 DRAM 的成本与供应。消费者和制造商未来数年都可能面临更高的内存价格和更紧张的供应。 社区讨论指出，在同一技术节点上，生产 HBM 所消耗的晶圆供应量约为 DDR5 的三倍。这种取舍意味着 HBM 产能的提升会直接限制非 HBM DRAM 的供应增长。

hackernews · inigyou · 8月7日 07:58 · [社区讨论](https://news.ycombinator.com/item?id=49207236)

**背景**: 高带宽内存（HBM）是一种三维堆叠的 SDRAM 接口，最初由三星、AMD 和 SK 海力士联合开发，用于 AI 加速器和高性能 GPU。由于 HBM 晶粒更大且封装更复杂，生产相同位数所需的晶圆产能远高于普通 DDR5，因此在 HBM 需求激增时，传统内存供应就会变得紧张。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/High_Bandwidth_Memory">High Bandwidth Memory - Wikipedia</a></li>
<li><a href="https://semiengineering.com/high-bandwidth-memory-hbm-everything-you-need-to-know/">High Bandwidth Memory (HBM): Everything You Need To Know</a></li>

</ul>
</details>

**社区讨论**: 评论中强调了 HBM 与 DDR5 之间的晶圆产能取舍，一些人担心消费者面临的内存成本上涨问题。也有人因内存和存储压力而对 AI 持保留态度，还有人建议制定更可复用的内存标准，并指出这可能对消费电子产品产生通胀影响。

**标签**: `#HBM`, `#memory`, `#AI hardware`, `#supply chain`, `#semiconductors`

---

<a id="item-8"></a>
## [人工智能被用于设计全新病毒，BBC 报道](https://news.google.com/rss/articles/CBMiZkFVX3lxTE00STJoYnJWYV9QY3VaMUJ1QmxsZWFyUFVxazNXV1IxNXdoZDZndlNNZ1UtVzVqZTBza3pxaVdNSkloNjE5d1F5Y2ROX3JUU2hUWTRYWGRDOHloRnhIeVY5X0hlOWc5Z9IBa0FVX3lxTE1wVWV1U0JlbzFsV0dmOTJRcXMyaEtNSGlERjdhQkV3TDl0elVJRXc4eVI4dmF5eW1Vc0d3NGxkVlpaY2lSMEVVRmhhb0UwbDU1ODdLU1YxZDBGRXZiOUxIdEo1YzZSUkpib09v?oc=5) ⭐️ 8.0/10

据 BBC 报道，人工智能现已被用于设计全新的病毒。这一进展凸显了生成式 AI 与合成生物学日益交叉的趋势，并引发了对技术被滥用的担忧。 此事之所以重要，是因为它表明 AI 可能降低制造新型病原体的门槛，增加意外泄漏或被蓄意滥用的风险。这影响到政策制定者、生物安全专家和 AI 开发者，并促使人们迫切呼吁加强治理与防护措施。 这篇 BBC 报道目前只有链接，没有附带正文，因此具体技术细节尚不清楚。相关研究显示，DNA-Diffusion 等生成式 AI 模型能够设计合成 DNA 序列，原则上也可能扩展到病毒基因组，这凸显了双重用途的担忧。

google\_news · BBC · 8月7日 09:30

**背景**: 生成式 AI 模型从大型数据集中学习模式，并能够生成新的输出，包括 DNA 序列。在合成生物学中，这些模型被用于设计调控元件和蛋白质等有益应用，但同样的能力也可能被滥用来改造有害病毒。这通常被称为“具有双重用途的研究”，即正当科学也可能带来潜在风险。目前的治理框架仍在发展之中，尚难以跟上 AI 和生物技术的快速进步。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nature.com/articles/s41588-025-02443-4">Generative AI creates synthetic regulatory DNA sequences for ...</a></li>
<li><a href="https://www.rand.org/pubs/conf_proceedings/CFA4186-1.html">Biosecurity Governance Across Uncertain Artificial ...</a></li>
<li><a href="https://link.springer.com/article/10.1007/s43681-025-00872-9">Artificial intelligence and synthetic biology: biosecurity ...</a></li>

</ul>
</details>

**标签**: `#artificial intelligence`, `#biosecurity`, `#synthetic biology`, `#research`

---

<a id="item-9"></a>
## [DeepSeek 斥资 1.4 亿元参与宇树科技战略配售](https://news.google.com/rss/articles/CBMilAFBVV95cUxPNXpTeVBXY1BQUnozeW1wSHNBT3V2NWdrSzBJWEZiaU5hbW1lLTR6ZWV6dzhiQVE2SUZQODVuWjhaX1FtZ21KMVFQLUpmSE5ScWFvb2hBZnVjTDBJZU5jOWNBb1VLajIyaXVUbmhnck83ZHNCTVlTVDhwdVItcGx1cUlxTXE0RzJEeldNMF9LMmhiMUxM?oc=5) ⭐️ 7.0/10

DeepSeek（深度求索）斥资 1.4 亿元人民币参与宇树科技的战略配售，将这家知名 AI 实验室与领先机器人公司直接联系起来。此举明确旨在为具身智能铺路。 这项投资表明大模型 AI 与实体机器人之间的融合趋势日益增强，这是具身智能领域的关键方向。它可能加速先进智能在四足机器人及人形机器人上的集成落地，对科研和商业应用都会产生深远影响。 宇树科技总部位于杭州，以消费级和行业级四足机器人、人形机器人及灵巧机械臂著称。DeepSeek 参与战略配售，表明双方可能在具身智能研发方面建立长期合作关系。

google\_news · 21财经 · 8月8日 02:21

**背景**: 具身智能是一种通过与现实世界持续物理交互而发展的 AI 形态，将感知、学习与行动紧密结合在实体身体中。宇树科技由王兴兴于 2016 年创立，起初专注四足机器人，后来扩展到人形机器人平台。DeepSeek 是一家知名 AI 研究实验室。这笔投资将 AI 算法能力与实体机器人平台相连接，有望推动智能系统在真实环境中的运行能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Unitree_Robotics">Unitree Robotics - Wikipedia</a></li>
<li><a href="https://today.ucsd.edu/photo-essays/what-is-embodied-intelligence-and-what-can-it-do">What Is Embodied Intelligence and What Can It Do</a></li>
<li><a href="https://en.wikipedia.org/wiki/Embodied_cognition">Embodied cognition - Wikipedia</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#Unitree`, `#Embodied AI`, `#Robotics`, `#Investment`

---

<a id="item-10"></a>
## [宇树科技 IPO 路演：近半募资投向&quot;大脑&quot;研发](https://news.google.com/rss/articles/CBMieEFVX3lxTE1PWVJZTEVPNGg0dnA5bGRsM2pwc242ZGlfcVNmN01fa1lYZ1VLWVdnRXVWYVdycXlUV0VqWEUwOU1Jb05xR0VVbm9abVlHUFRiS3dCMnhCVXZJekY3Uy1ZOG43NlgzVlRqRjRHMENlYy1NRlZzT3luNQ?oc=5) ⭐️ 7.0/10

宇树科技，这家中国领先的机器人公司，在 IPO 路演中透露计划将募资的近半资金投向“大脑”研发，即控制机器人的 AI 与算法系统。这标志着公司将战略重心放在软件和智能而非纯硬件上。 这一投资方向表明宇树科技将 AI“大脑”视为机器人领域的下一竞争焦点。它可能加速更强大的人形和四足机器人的开发，并重塑投资者对机器人公司如何实现差异化的预期。 “近半”的表述暗示了 IPO 募资中将有约 40%至 50%用于“大脑”研发，但摘要中未透露具体比例和总金额。“大脑”很可能涵盖感知、决策与控制算法，包括 AI 训练和仿真。

google\_news · 中证网 · 8月8日 00:34

**背景**: 宇树科技以其四足机器人（如 Go1 和 B2）而闻名，并已通过 H1 型号进入人形机器人领域。在机器人行业中，“大脑”指实现自主行为的软件和 AI 系统，与由执行器、传感器和机械部件组成的物理“身体”相对。如今许多机器人公司都将 AI 视为关键差异点。

**标签**: `#robotics`, `#IPO`, `#artificial intelligence`, `#Unitree`, `#funding`

---

<a id="item-11"></a>
## [谷歌 AI 重组：商业化压力让科研愿景退居其次](https://news.google.com/rss/articles/CBMiSEFVX3lxTE1FYU1VSXozYTBsTWtiOFdpd3h0azlSNy0wV1BScnZBcjdUOVduTGY2TEkwcmtmU2ppUVN1dTYzeHBVeFB5X0dFVQ?oc=5) ⭐️ 7.0/10

据中国财经媒体报道，谷歌的 AI 业务重组以商业化为优先，将纯科研目标置于次要位置。这一动向延续了 2023 年 4 月 Google Brain 与 DeepMind 合并后的整合趋势。 作为全球领先的 AI 研究机构，谷歌向商业化倾斜可能重塑行业激励，减少开放式研究和学术合作。这也反映了科技行业将 AI 突破转化为盈利产品的普遍压力。 此次重组基于 2023 年 4 月成立的 Google DeepMind，其目前负责 Gemini、Imagen、Veo 和 Lyria 等产品。报道未给出具体组织变动的细节或日期，但标题表明科研雄心正被有意降级。

google\_news · 财联社 · 8月7日 15:58

**背景**: Google DeepMind 于 2010 年以 DeepMind Technologies 之名成立，2014 年被谷歌收购，并于 2023 年 4 月与谷歌的 Brain 团队合并成为 Google DeepMind。它以 AlphaGo 和 AlphaFold 以及开发 Gemini 大语言模型系列而闻名。Google Brain 成立于 2011 年，创造了 TensorFlow，并为谷歌众多 AI 项目做出贡献。当前的持续重组反映了在尖端研究与创收需求之间取得平衡的挑战。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Google_DeepMind">Google DeepMind</a></li>
<li><a href="https://en.wikipedia.org/wiki/Google_Brain">Google Brain</a></li>

</ul>
</details>

**标签**: `#Google`, `#AI`, `#Business Strategy`, `#Restructuring`

---

<a id="item-12"></a>
## [存储芯片巨头千亿元大动作](https://news.google.com/rss/articles/CBMijAFBVV95cUxPMWNOdElMTGRfMjRfRlJZczBWUGMwUHZqekNoRGtGM0RidmpnT0lkemRzN3k1ZldVeG9yNmVCY1oySHpDaHduTFF3U240WXFpSkRhTnE1V2FycnEyU3U4VjR2XzZkal9YQ0dHNFBnbl9CM19VZXd0TXpyUHFrSl9PZG9mNm40dC15VzZPbA?oc=5) ⭐️ 7.0/10

据 21 财经报道，一家存储芯片巨头正计划进行一项规模达千亿元人民币的大额投资。报道摘要未披露具体公司及项目细节。 这一规模的投资将位居半导体行业前列，可能显著影响全球存储芯片的供应与价格。它也反映出 AI 服务器和数据中心对存储芯片需求上升的趋势。 报道所称的“千亿元”意味着投资规模至少达到 1000 亿元人民币（约合 140 亿美元）。在缺乏更多细节的情况下，尚不清楚该投资针对的是先进 DRAM、NAND 闪存还是封装产能。

google\_news · 21财经 · 8月7日 23:51

**背景**: 存储芯片主要包括 DRAM 和 NAND 闪存，是计算机、智能手机和数据中心的关键元器件。存储行业属于资本密集且具有周期性的行业，三星、SK 海力士和美光等龙头厂商主导供应。大规模扩产通常出现在需求强劲的时期，例如当前由 AI 驱动的景气周期。

**标签**: `#storage chips`, `#semiconductor`, `#investment`, `#industry news`, `#memory`

---