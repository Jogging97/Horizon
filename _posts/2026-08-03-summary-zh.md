---
layout: default
title: "Horizon Summary: 2026-08-03 (ZH)"
date: 2026-08-03
lang: zh
---

> 从 88 条内容中筛选出 7 条重要资讯。

---

1. [Qwen 3.8-Max：2.4 万亿参数，首次开源 Max 级模型](#item-1) ⭐️ 9.0/10
2. [DNA 分析设备曝漏洞，30 年法医证据面临篡改风险](#item-2) ⭐️ 8.0/10
3. [Kakehashi：在 Linux ARM 上原生运行 macOS 二进制的实验性用户空间](#item-3) ⭐️ 7.0/10
4. [英语学习者核心词汇的变迁：从 1953 年到现在](#item-4) ⭐️ 7.0/10
5. [CausalVLBench：用于大视觉语言模型的视觉因果推理新基准](#item-5) ⭐️ 7.0/10
6. [苹果限制漏洞报告提交，应对 AI 生成的低质量报告](#item-6) ⭐️ 7.0/10
7. [美国多州拟取消数据中心税收优惠，AI 基础设施成本或将上升](#item-7) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Qwen 3.8-Max：2.4 万亿参数，首次开源 Max 级模型](https://qwen.ai/blog?id=qwen3.8) ⭐️ 9.0/10

通义千问正式发布 Qwen 3.8-Max，这是 Qwen 迄今最强的模型，总参数达 2.4 万亿，活跃参数 95B。这是 Qwen 首次开源 Max 级模型权重，预计下周开放。 开源 Max 级旗舰权重，意味着开发者与研究人员将首次获得原本闭源的前沿能力，可能加速编程、智能体办公及长周期任务方面的创新。这也表明开源 AI 领域竞争加剧，尤其在中国 AI 实验室之间。 Qwen 3.8-Max 基于 Qwen 3.5 架构，据称可自主运行编码任务超过 10 天，并在 24 小时内参加 WWW2025 多模态对话意图识别竞赛，击败 526 支队伍中的 458 支。模型现已通过 QwenCloud API 提供服务；下周的开源版本还将包含 Qwen3.8-27B。

hackernews · ai2027 · 8月3日 02:16 · [社区讨论](https://news.ycombinator.com/item?id=49150470)

**背景**: 在大语言模型中，总参数代表模型的容量，而活跃参数是每次前向推理实际使用的子集；2.4 万亿总参数、95B 活跃参数的模式通常意味着使用混合专家（MoE）架构。MoE 模型通过门控网络把每个输入路由到少量专门的专家子网络，从而在超大规模下控制推理成本。Qwen Max 系列历来是阿里巴巴最强的闭源旗舰系列；此次开源打破了以往惯例，为开源前沿模型树立了新标杆。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Qwen">Qwen - Wikipedia</a></li>
<li><a href="https://www.f22labs.com/blogs/active-vs-total-parameters-whats-the-difference/">Active vs Total Parameters: What’s the Difference?</a></li>
<li><a href="https://www.investing.com/news/stock-market-news/alibaba-unveils-qwen-38max-ai-model-shares-jump-4829755">Alibaba unveils Qwen 3.8-MAX AI model; shares jump By Investing.com</a></li>

</ul>
</details>

**社区讨论**: 社区评论者普遍对开源权重感到兴奋，有人称赞 Qwen3.8-27B 是强大的本地模型，在不大幅增大模型体积的情况下没有对手。也有人对公告时间和链接表示困惑；还有一些宏观观点：有人希望封禁开源模型的政策窗口尽快过去，以便让 Fable 级模型成为本地基线，也有人调侃称一旦 OpenAI 和 Anthropic 上市，此类发布将成为可靠的卖出信号。另有评论者质疑 “cowork” 是否已成为通用行业术语。

**标签**: `#AI`, `#LLM`, `#Qwen`, `#Open Source`, `#Machine Learning`

---

<a id="item-2"></a>
## [DNA 分析设备曝漏洞，30 年法医证据面临篡改风险](https://www.wsj.com/tech/cybersecurity/security-flaw-placed-30-years-of-dna-evidence-at-risk-of-hacking-1932775a) ⭐️ 8.0/10

一组法医学和计算机科学家发现，美国多数犯罪实验室使用的 DNA 分析设备存在安全漏洞，并演示了借助 AI 生成的代码可在不触发分析软件警报的情况下篡改 DNA 扫描数据。Thermo Fisher Scientific 现已发布高危安全公告，并推出加入数字签名的软件更新。 该漏洞威胁到约 30 年来刑事 DNA 证据的完整性，可能让调查和法庭案件中的 DNA 图谱被悄然篡改。由于全美 200 多家实验室缺乏统一监管，这一缺陷引发了对全国法医数据可靠性的广泛担忧。 研究人员借助 Anthropic 的 Claude 首次成功篡改文件约耗时 45 分钟，且修改后的文件未触发常用分析软件的警报。Thermo Fisher 表示正与美国 CISA 合作，尚未发现漏洞被实际利用的案例，并建议无法更新软件实验室采取额外安全措施。

telegram · zaihuapd · 8月3日 05:15

**背景**: DNA 分析仪将遗传样本转换为数字图谱，供刑事调查中存储和比对。该漏洞似乎源于输出文件缺少数字签名，导致数据是否被改动难以验证。由于美国众多犯罪实验室使用同一款 Thermo Fisher 设备和软件，一个弱点就可能影响全国范围的法医鉴定结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.wsj.com/tech/cybersecurity/security-flaw-placed-30-years-of-dna-evidence-at-risk-of-hacking-1932775a">Exclusive | Security Flaw Placed 30 Years of DNA Evidence at ...</a></li>
<li><a href="https://documents.thermofisher.com/TFS-Assets/CORP/Product-Guides/fsa_hid_bulletin.pdf">Security Bulletin</a></li>
<li><a href="https://book.st-hakky.com/en/news/security-flaw-puts-30-years-dna-at-risk">DNA Evidence Security Vulnerability: Tampering Made Possible ...</a></li>

</ul>
</details>

**标签**: `#cybersecurity`, `#forensics`, `#DNA analysis`, `#vulnerability`, `#AI`

---

<a id="item-3"></a>
## [Kakehashi：在 Linux ARM 上原生运行 macOS 二进制的实验性用户空间](https://github.com/wie-project/kakehashi) ⭐️ 7.0/10

Kakehashi 是一个实验性用户空间，可在 Linux ARM 上原生运行 macOS 命令行二进制文件。目前已有 curl、7-Zip 和 Git 的工作原型，证明无需完整虚拟机即可执行 Mach-O 二进制文件。 这很重要，因为它开辟了在 Linux ARM 硬件上直接运行 macOS 命令行工具的道路，可能扩大跨平台的软件兼容性。如果成熟，它可以补充 Darling 等项目，并在开发和自动化领域开启新的应用场景。 原型显示出性能差距——目前 7-Zip 比原生 Linux 执行慢约 5.2 倍，但作者已制定了清晰的优化计划。curl 在自动化 Docker 测试脚本中通过了 200 多个命令和选项，Git 支持基本的版本控制功能。

hackernews · vlad\_kalinkin · 8月2日 16:26 · [社区讨论](https://news.ycombinator.com/item?id=49145937)

**背景**: 在操作系统中，用户空间是应用程序运行的内存区域，与内核空间分离。macOS 二进制文件使用 Mach-O 格式，与 Linux 的 ELF 格式不同，因此直接运行它们需要兼容层来翻译系统调用和二进制格式。Darling 等项目旨在为基于 Darwin 的二进制文件提供这样的层，目前已有支持 ARM64 的开放拉取请求。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/User_space_and_kernel_space">User space and kernel space - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Mach-O">Mach - O - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Compatibility_layer">Compatibility layer - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: Hacker News 上的讨论表现出浓厚的兴趣，评论者提到了相关项目 Darling 及其开放的 ARM64 拉取请求。一些人认为 Kakehashi 仍处于早期阶段，并对其未来方向感到好奇；还有人设想在其之上构建类似 yabridge 的桥接，以在 Linux 上运行 macOS AU 插件。总体情绪积极但对成熟度持谨慎态度。

**标签**: `#macOS`, `#linux`, `#ARM`, `#binary-compatibility`, `#userspace`

---

<a id="item-4"></a>
## [英语学习者核心词汇的变迁：从 1953 年到现在](https://pudding.cool/2026/07/essential-words/) ⭐️ 7.0/10

《The Pudding》的一篇互动文章追溯了 1953 年至 2023 年间英语学习者核心词汇的变化。分析发现，1953 年词表中近四分之一的单词已消失，而 2023 年词表中 39%的单词是新出现的。 这一变化之所以重要，是因为词汇表并非中性：它们承载着一个社会认为外来者需要了解的重要内容。从 humble、loyalty 等词转向 community、identity 等词，可能会影响英语学习者理解和融入英语文化的方式。 文章指出，“社交-交际”类别的词汇数量几乎没有变化，但内容发生了很大变化。诸如 humble、loyalty、fellowship、generous、polite、companionship 等词，让位给了 community、identity、organization、ethnic、gender、narrative 等词。

hackernews · c-oreills · 8月2日 15:41 · [社区讨论](https://news.ycombinator.com/item?id=49145590)

**背景**: 1953 年的参照基准很可能是指 General Service List（GSL），这是 Michael West 编制的一份经典英语高频词表，包含约 2000 个单词，曾广泛用于英语教学。现代语料库语言学利用大规模数字化真实文本集合来衡量词频并更新此类词表，例如 Academic Word List（AWL）就是这样产生的。通过比较新旧词表，研究者可以观察语言使用和文化重点如何随时间演变。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/General_Service_List">General Service List - Wikipedia</a></li>
<li><a href="https://www.eapfoundation.com/vocab/general/gsl/">GSL ( General Service List )</a></li>
<li><a href="https://www.eapfoundation.com/vocab/academic/awllists/">Academic Word List ( AWL )</a></li>

</ul>
</details>

**社区讨论**: 评论区大多对文章的语言学见解展开讨论，有人指出并不存在唯一“正确”的词汇表，因为学习者的目标各不相同（如旅行、看电视或读报）。一位评论者将“亲近的个人品质”向“远距离的社会类别”的转变归因于不平等加剧和部落化倾向，另一位评论者则抱怨这个互动页面是一个恼人的“滚动劫持”设计。

**标签**: `#language learning`, `#linguistics`, `#education`, `#cultural shifts`, `#ESL`

---

<a id="item-5"></a>
## [CausalVLBench：用于大视觉语言模型的视觉因果推理新基准](https://www.reddit.com/r/MachineLearning/comments/1vdd7ty/r_causalvlbench_benchmarking_visual_causal/) ⭐️ 7.0/10

研究人员推出了 CausalVLBench，这是一个用于评估大型视觉语言模型（LVLMs）视觉因果推理能力的综合性基准。它包含三个任务：因果结构推断、干预目标预测和反事实预测。 因果推理是多模态人工智能中一项关键但尚未充分探索的能力。CausalVLBench 为衡量这一能力提供了标准化方法，帮助研究界识别当前 LVLMs 的短板，并指导开发更稳健的模型。 该基准专为多模态上下文学习设计，涵盖了一套全面的视觉因果推理任务。该论文可在 arXiv 上获取，并已被 EMNLP 2025 接收。

reddit · r/MachineLearning · /u/moschles · 8月2日 09:07

**背景**: 视觉因果推理是指从图像或视频中理解因果关系的能力，例如推断因果结构、预测干预效果以及推理反事实情景。大型视觉语言模型结合了视觉和文本理解能力，但此前缺乏专门的基准来衡量它们在因果任务上的表现。CausalVLBench 通过提供统一的评估框架填补了这一空白。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2506.11034">[2506.11034] CausalVLBench: Benchmarking Visual Causal ... CausalVLBench: Benchmarking Visual Causal Reasoning in Large ... CausalBench: A Comprehensive Benchmark for Causal Learning ... CausalBench: A Comprehensive Benchmark for Evaluating Causal ... CausalBench+ Quickstart - CausalBench</a></li>
<li><a href="https://aclanthology.org/2025.emnlp-main.1561/">CausalVLBench: Benchmarking Visual Causal Reasoning in Large ...</a></li>

</ul>
</details>

**标签**: `#benchmark`, `#vision-language models`, `#causal reasoning`, `#evaluation`

---

<a id="item-6"></a>
## [苹果限制漏洞报告提交，应对 AI 生成的低质量报告](https://www.ft.com/content/4532122d-90f2-4433-9df6-ca99d8a141d2?syn-25a6b1a6=1) ⭐️ 7.0/10

苹果自 6 月起限制研究人员同时提交漏洞报告的数量，并引入 30 天冷却期，以遏制借助 AI 模型生成的低质量报告。意大利初创公司 Bynario 称，ChatGPT 帮助其在三周内于 macOS 中发现 50 多个漏洞，包括一条提权漏洞链，但因提交限额而无法向苹果报告。 这凸显了 AI 加速漏洞发现与传统人工漏洞披露流程之间的张力，影响安全研究人员生态，也可能改变苹果及其他厂商处理 AI 辅助发现结果的方式。 苹果表示已与 Bynario 联系并审核其提交内容，同时也在内部使用 AI：本周系统安全更新修复的漏洞数量约为平时的五倍，并致谢 Anthropic 和 OpenAI 的工具。30 天冷却期和限额适用于同时提交的数量，研究人员必须决定优先报告哪些发现。

telegram · zaihuapd · 8月2日 05:50

**背景**: 漏洞披露计划允许安全研究人员通过漏洞赏金平台向厂商报告缺陷，以便在攻击者利用之前修复。AI 模型如今能生成看起来合理但经常为误报的漏洞报告，令这些系统不堪重负；苹果的限制正是对这一噪音的回应。提权是一种攻击技术，让用户或进程获得超出预期的更高权限，而一条提权漏洞链可导致攻击者完全控制系统。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://bynar.io/">Bynario — Autonomous Vulnerability Detection &amp; Remediation</a></li>
<li><a href="https://cybersecuritynews.com/ai-polluting-bug-bounty-platforms/">AI Polluting Bug Bounty Platforms with Fake Vulnerability Reports</a></li>
<li><a href="https://blog.quest.com/understanding-the-cyber-kill-chain-and-how-it-impacts-microsoft-365/">Cyber kill chain defined : How it impacts Microsoft 365</a></li>

</ul>
</details>

**标签**: `#AI security`, `#vulnerability disclosure`, `#Apple`, `#ChatGPT`, `#cybersecurity`

---

<a id="item-7"></a>
## [美国多州拟取消数据中心税收优惠，AI 基础设施成本或将上升](https://theinformation.com/articles/exclusive-data-center-costs-set-rise-u-s-states-move-repeal-tax-breaks) ⭐️ 7.0/10

美国多个州正考虑取消或收紧此前给予大型数据中心的税收减免政策，包括服务器设备和电力费用等方面的免税优惠。这一政策转向可能推高数据中心建设与运营成本，并影响未来 AI 基础设施的选址布局。 数据中心是 AI 浪潮的物理基础，因此税收政策变化直接影响云服务商和 AI 开发者的成本结构。如果建设成本上升，企业可能调整选址策略，各州也可能面临 AI 基础设施投资节奏放缓。 地方政府面临的压力主要来自数据中心激增的电力需求、沉重的基础设施投入以及税收收入的减少。该报道为 The Information 的独家消息，但未指明具体州名或法案名称。

telegram · zaihuapd · 8月3日 00:42

**背景**: 多年来，美国许多州通过免除服务器、电力等费用等税收激励措施来吸引数据中心投资。随着 AI 算力需求爆发，地方政府开始重新评估这类补贴是否仍然合理。政策结果将影响未来 AI 基础设施的建设成本与选址。

**标签**: `#AI infrastructure`, `#data centers`, `#tax policy`, `#cloud computing`, `#regulation`

---