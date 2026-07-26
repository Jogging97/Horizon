---
layout: default
title: "Horizon Summary: 2026-07-26 (ZH)"
date: 2026-07-26
lang: zh
---

> 从 90 条内容中筛选出 9 条重要资讯。

---

1. [vLLM v0.26.0 发布，支持 Inkling 模型家族和 DeepSeek-V4 优化](#item-1) ⭐️ 8.0/10
2. [Claude 5 模型上下文工程的新规则](#item-2) ⭐️ 8.0/10
3. [通用汽车投资钠离子电池用于电网储能](#item-3) ⭐️ 8.0/10
4. [开源权重 AI 迎来类似 Kubernetes 的标准化时刻](#item-4) ⭐️ 8.0/10
5. [安卓可能限制设备端 ADB 以提升安全性](#item-5) ⭐️ 8.0/10
6. [Ruff v0.16.0 将默认规则从 59 条扩充到 413 条](#item-6) ⭐️ 8.0/10
7. [DeepSeek 因内部言论泄露暂停超 100 亿美元融资](#item-7) ⭐️ 8.0/10
8. [黄仁勋开通社交账号，首封公开信点燃 AI 路线之争](#item-8) ⭐️ 7.0/10
9. [丁薛祥主导中国 AI 芯片攻坚，中美科技战加剧](#item-9) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [vLLM v0.26.0 发布，支持 Inkling 模型家族和 DeepSeek-V4 优化](https://github.com/vllm-project/vllm/releases/tag/v0.26.0) ⭐️ 8.0/10

vLLM v0.26.0 引入了 Inkling 模型家族并提供完整支持栈，跨厂商大幅提升 DeepSeek-V4 性能，新增 fp32 lm\_head 支持、灵活注意力后端，以及成熟的 KV 卸载功能。该版本包含来自 212 位贡献者的 411 次提交。 此版本显著增强了 vLLM 对最新大型语言模型（尤其是 Inkling 多模态 MoE 模型和 DeepSeek-V4）的运行能力，使高性能推理更加易用。注意力后端的灵活性和 KV 卸载改进有利于混合模型和大规模部署。 Inkling 模型家族包括分段 CUDA 图支持、Hopper FA4 相对注意力、MTP=1 推测解码、LoRA 和 ModelOpt NVFP4 量化。DeepSeek-V4 获得了专用路由内核（E2E TPOT 提升 2.94%）以及跨 NVIDIA、AMD 和 Intel 硬件的其他内核优化。

github · khluu · 7月25日 10:38

**背景**: vLLM 是一个开源的高吞吐量 LLM 推理引擎。Inkling 模型家族是一个多模态 MoE 模型，总参数 975B，激活参数 41B，支持文本、图像和音频。FlashAttention-4 \(FA4\) 是一种针对 Hopper GPU 的新注意力算法，通过流水线和异步执行提升性能。NVFP4 是 NVIDIA ModelOpt 提供的 4 位浮点量化格式。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/introducing-inkling/">Inkling : Our Open-Weights Model - Thinking Machines Lab</a></li>
<li><a href="https://modal.com/blog/reverse-engineer-flash-attention-4">We reverse-engineered Flash Attention 4</a></li>
<li><a href="https://forums.developer.nvidia.com/t/lama-cpp-ggml-nvfp4-quantization-type-support-might-arrive-soon/362772">Lama.cpp ggml - nvfp4 quantization type support might arrive soon</a></li>

</ul>
</details>

**标签**: `#vLLM`, `#LLM inference`, `#model optimization`, `#DeepSeek`, `#release notes`

---

<a id="item-2"></a>
## [Claude 5 模型上下文工程的新规则](https://claude.com/blog/the-new-rules-of-context-engineering-for-claude-5-generation-models) ⭐️ 8.0/10

Anthropic 发布了一篇博客文章，详细介绍了 Claude 5 系列模型的上下文工程新最佳实践，并透露他们删除了 Opus 5 和 Fable 5 的 Claude Code 系统提示中超过 80% 的内容，且性能未受影响。 这改变了开发者应为 Claude 代理组织上下文的方式，强调简洁而非冗长的指令，并引发了关于自动内存在上下文管理中作用的讨论。 该博客基于对 Claude Code 自身系统提示的审计，社区争论的焦点在于自动内存容易产生不一致且不透明的决策，部分用户表示禁用后性能得到提升。

hackernews · mellosouls · 7月25日 20:42 · [社区讨论](https://news.ycombinator.com/item?id=49051361)

**背景**: 上下文工程是设计和管理跨多次请求提供给大模型的信息的实践，与单轮提示不同。Claude 5 代模型包括 Opus 5 和 Fable 5，它们的能力提升需要调整提示策略。自动内存允许 Claude 在会话中自行记录笔记，但仅限于 200 行的索引，且无语义搜索功能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://claude.com/blog/the-new-rules-of-context-engineering-for-claude-5-generation-models">The new rules of context engineering for Claude 5 generation models</a></li>
<li><a href="https://www.mager.co/blog/2026-07-24-context-engineering-claude-5/">Claude Is Unhobbled. Your Context Engineering Is Not.</a></li>
<li><a href="https://simonwillison.net/2026/Jul/24/introducing-claude-opus-5/">Introducing Claude Opus 5 | Simon Willison’s Weblog</a></li>

</ul>
</details>

**社区讨论**: 社区成员担忧 Anthropic 过度依赖自动内存，它经常虚构上下文连接并做出隐藏的假设；用户 &\#x27;threecheese&\#x27; 和 &\#x27;sothatsit&\#x27; 表示禁用自动内存并手动管理 CLAUDE.md 和文档后效果更好。另一评论者认为这种转变可能是 Anthropic 锁定工具的策略。

**标签**: `#context engineering`, `#prompt engineering`, `#Claude`, `#LLM memory`, `#AI agents`

---

<a id="item-3"></a>
## [通用汽车投资钠离子电池用于电网储能](https://spectrum.ieee.org/sodium-ion-battery-peak-energy) ⭐️ 8.0/10

通用汽车宣布支持用于美国电网储能的钠离子电池技术。这项投资支持钠离子电池作为锂离子电池的廉价替代品用于固定式储能的发展。 钠离子电池比锂离子电池更便宜、更可持续，因为钠资源丰富，减少了对锂和钴等稀缺材料的依赖。这可能降低电网储能成本，加速可再生能源整合，使公用事业和消费者受益。 这些钠离子电池的往返效率达到 96%，与锂离子电池相当。然而，它们的能量密度较低，这对于固定式电网储能来说不如电动汽车关键。

hackernews · rbanffy · 7月25日 21:48 · [社区讨论](https://news.ycombinator.com/item?id=49051947)

**背景**: 钠离子电池的工作原理与锂离子电池类似，但使用钠离子作为电荷载体。钠在海水中储量丰富且广泛可得，使这些电池更便宜且更环保。虽然已在小型应用中得到商业化，但正由宁德时代和 Natron Energy 等公司扩展到电网储能领域。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Sodium-ion_battery">Sodium-ion battery - Wikipedia</a></li>
<li><a href="https://www.iea.org/commentaries/sodium-ion-battery-momentum-grows-but-challenges-remain">Sodium-ion battery momentum grows, but challenges remain – Analysis - IEA</a></li>

</ul>
</details>

**社区讨论**: 评论强调 96%的往返效率对电网储能很有吸引力，一位用户指出改用钠离子电池可减少现有锂电池的暖通空调电力消耗。另一位用户询问钠离子电池何时可供家庭使用。有人对通用汽车的参与表示怀疑，提及一家美国钠离子公司此前因缺乏资金而失败。

**标签**: `#sodium-ion batteries`, `#grid storage`, `#GM`, `#energy storage`, `#battery technology`

---

<a id="item-4"></a>
## [开源权重 AI 迎来类似 Kubernetes 的标准化时刻](https://tobi.knaup.me/2026-07-25-open-weight-ai-is-having-its-kubernetes-moment/) ⭐️ 8.0/10

Tobi Knaup 的一篇文章指出，开源权重 AI 模型正沿着与 Kubernetes 相同的轨迹发展，成为 AI 开发的标准化基础，类似于 Kubernetes 对云基础设施的标准化。 这很重要，因为如果开源权重 AI 成为事实标准，它将降低准入门槛、刺激创新，并将 AI 行业的权力从少数大型实验室转移，使 AI 更易获取和可审计。 开源权重模型仅发布训练后的权重和偏置，允许推理和微调但不可完全复现。与开源不同，它们可能带有限制性许可证，且其来源难以确定——权重只是数字，使得基于来源的监管具有挑战性。

hackernews · tknaup · 7月25日 14:49 · [社区讨论](https://news.ycombinator.com/item?id=49048034)

**背景**: 开源权重 AI 模型是神经网络模型，其训练后的参数（权重）公开发布，任何人都可以下载并运行。Kubernetes 是一个用于自动化容器化应用程序部署、扩展和管理的开源平台，已成为云基础设施的行业标准。这个类比表明，开源权重模型可能类似地成为 AI 系统的默认构建块。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://hai.stanford.edu/ai-definitions/what-is-an-open-weight-model">What is an Open-Weight Model? - Stanford HAI</a></li>
<li><a href="https://en.wikipedia.org/wiki/Kubernetes">Kubernetes - Wikipedia</a></li>
<li><a href="https://opensource.org/ai/open-weights">Open Weights: not quite what you’ve been told</a></li>

</ul>
</details>

**社区讨论**: 评论者讨论了按来源监管开源权重模型的可行性，指出权重只是数字无法追溯。其他人将定价动态比作&\#x27;tokenomics&\#x27;，并认为真正的标准化需要公开训练数据和协作开发，类似于 Linux。一些人称赞了 OpenAI 现有的开源权重模型，但希望更新更频繁。

**标签**: `#AI`, `#open-source`, `#Kubernetes`, `#regulation`, `#open-weight models`

---

<a id="item-5"></a>
## [安卓可能限制设备端 ADB 以提升安全性](https://kitsumed.github.io/blog/posts/android-may-soon-restrict-on-device-adb/) ⭐️ 8.0/10

谷歌正在考虑限制设备端 ADB（安卓调试桥）的访问权限以提升安全性，这一话题在社区中引发了热烈讨论。该变化将限制开发者和高级用户在设备上直接使用 ADB 的方式。 这一限制可能严重影响依赖 ADB 进行调试、自动化和侧载的安卓开发者和高级用户。它也加剧了关于安卓开放性与安全性的持续争论，可能使该平台更接近 iOS 式的限制。 谷歌旨在解决的安全攻击需要用户同时启用开发者选项和远程 ADB，这是一种小众场景，影响不到 0.1%的用户。替代方案包括将 ADB 限制在特定的 IP 地址或接口上，而非全面禁止。

hackernews · shscs911 · 7月25日 06:57 · [社区讨论](https://news.ycombinator.com/item?id=49045159)

**背景**: 安卓调试桥（ADB）是一个命令行工具，允许开发者与安卓设备通信以进行调试和其他高级操作。设备端 ADB 可直接在设备上实现这些功能，便于在没有 PC 的情况下进行自动化和故障排除。多年来，谷歌一直在加强安卓的安全性，包括限制侧载，这引发了开发者社区的批评。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Android_Debug_Bridge">Android Debug Bridge - Wikipedia</a></li>
<li><a href="https://developer.android.com/tools/adb">Android Debug Bridge (adb) | Android Studio | Android Developers</a></li>
<li><a href="https://help.esper.io/hc/en-us/articles/12657625935761-Installing-the-Android-Debug-Bridge-ADB-Tool">Installing the Android Debug Bridge (ADB) Tool – Esper Help</a></li>

</ul>
</details>

**社区讨论**: 社区意见分歧：有人认为攻击面过于小众，不值得如此限制；另一些人则认为这是谷歌逐步收紧安卓控制的下一个合理步骤。有评论者担心 ADB 本身最终可能被限制，需要用户交出身份并付费，这呼应了安卓正在失去开放性的担忧。

**标签**: `#Android`, `#ADB`, `#security`, `#developer tools`, `#Google`

---

<a id="item-6"></a>
## [Ruff v0.16.0 将默认规则从 59 条扩充到 413 条](https://simonwillison.net/2026/Jul/25/ruff/#atom-everything) ⭐️ 8.0/10

Ruff v0.16.0 于 2026 年 7 月 23 日发布，将其默认规则集从 59 条大幅增加到 413 条，无需任何配置即可默认启用更多检查。 这一变化意味着使用 Ruff 的 Python 开发者将立即捕捉到更多问题，包括语法错误和运行时错误，无需额外努力即可提升代码质量。这也展示了 Ruff 的快速增长及其与 AI 编程代理的集成，正如 Simon Willison 使用 GPT-5.6 和 Claude 自动修复新发现的问题。 新的默认规则能捕获诸如 datetime.now\(\) 未带时区调用、捕获盲 Exception 以及无用的属性访问等问题。Simon Willison 在新的 Ruff 上运行了他的项目（Datasette、sqlite-utils、LLM），发现了数百个问题，其中 sqlite-utils 显示 1618 个错误，通过 --fix --unsafe-fixes 修复了 1538 个。

rss · Simon Willison · 7月25日 22:44

**背景**: Ruff 是一个用 Rust 编写、速度极快的 Python 代码检查器和格式化工具。它旨在成为 Flake8、isort 和 Black 等工具的替代品。截至 v0.16.0，Ruff 共有 968 条规则，其中 413 条默认启用。Ruff 背后的公司 Astral 最近被 OpenAI 收购。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/astral-sh/ruff">GitHub - astral-sh/ruff: An extremely fast Python linter and code formatter, written in Rust. · GitHub</a></li>
<li><a href="https://docs.astral.sh/ruff/">Ruff - Astral Docs</a></li>

</ul>
</details>

**标签**: `#Python`, `#linting`, `#Ruff`, `#developer tools`, `#release`

---

<a id="item-7"></a>
## [DeepSeek 因内部言论泄露暂停超 100 亿美元融资](https://www.bloomberg.com/news/articles/2026-07-25/deepseek-said-to-tell-backers-of-funding-pause-after-viral-posts) ⭐️ 8.0/10

DeepSeek 在创始人梁文锋对内部言论泄露表示不满后，暂停了一轮至少 100 亿美元的融资，并开始重新评估信息披露流程。 这一暂停影响了这家领先 AI 初创公司的增长轨迹和 IPO 时间线，凸显了在高风险融资环境中内部沟通的敏感性。 本轮融资原计划至少募集 1000 亿元人民币，投前估值 4800 亿元。DeepSeek 刚于 2026 年 6 月完成首轮 70 亿美元融资，投资者包括腾讯、宁德时代和国家人工智能产业投资基金。

telegram · zaihuapd · 7月26日 01:17

**背景**: DeepSeek 是一家开发大语言模型的中国 AI 初创公司。该公司最近完成了大规模首轮融资，并正在筹备 IPO。暂停融资表明在机密投资者会议记录被泄露到网上后，公司内部出现了动荡。

**标签**: `#DeepSeek`, `#funding`, `#AI`, `#China`, `#startup`

---

<a id="item-8"></a>
## [黄仁勋开通社交账号，首封公开信点燃 AI 路线之争](https://news.google.com/rss/articles/CBMif0FVX3lxTE05NlJ6b3B5bUE1VXk1TWpJbWxpRWk4Mi02d2d1QzROX2RXR0dzdGpIVVN1ekhBUWNuVmVscVNEckc4cWpXQTl5MjRKbmZST0FqQzBKWUFZNkY4ay1HUWswMU51b2xJanJvRVpQNTFYNWFPSnRmUDVCVUFtR3R1R3M?oc=5) ⭐️ 7.0/10

英伟达 CEO 黄仁勋首次开通社交媒体账号，并发布一封公开信，公开质疑主流 AI 发展方向，重新点燃了关于 AI 发展路径的争论。 作为 AI 硬件领域的关键人物，黄仁勋的公开立场可能影响行业趋势和投资方向，从而加速或改变 AI 研究与商业化的进程。 这封公开信发布在他新创建的社交媒体账号上，标志着他首次直接参与 AI 战略的公开讨论；信中的具体论点尚未完全披露，但被描述为“撕开”了 AI 路线之争。

google\_news · 新浪网 · 7月26日 03:47

**背景**: AI 路线之争指的是关于人工智能发展路径的持续争议，例如是继续扩大模型规模，还是转而追求效率和专用智能。作为 GPU 巨头英伟达的领导人，黄仁勋的介入使这场讨论更具分量。

**标签**: `#AI`, `#Jensen Huang`, `#NVIDIA`, `#open letter`, `#AI competition`

---

<a id="item-9"></a>
## [丁薛祥主导中国 AI 芯片攻坚，中美科技战加剧](https://news.google.com/rss/articles/CBMiogRBVV95cUxOaHQ5LWI1dXVyS2Y5bWhZVmN0eXpETDdVTm10SWs1M1JxVkVYMURnd05wVnF4OHBPd2c1YktjcXoya3FxdWR6N1g5X0dhTHNSSjdtOHo5a2NQTFBUeWRDUDhqTEl5LUU0bVc1TUJBRVAxWHVLb3A5TURLMEZoT20xc25qdTVmMXp1Nm5EYWJnMEF0OWhLVmtxOHJpQnYySl83cHRJa3dvV25XTU5yX24zMVV5Y1loYjdkVE45VlFmMVhxdXF2ZFdBT2U3TDh4aXpOc29ucmNLYWdGZGwzTFpxajRKLTczeEdxV0tGQ3R1WDdGcG9VaUxhME9KZG4wejAwYjhJN1h6WHUyS2ZlLWRFb2p3UmhKYktJaUUzWXlyZHJiQnlfX3dGNGd5bEtBa3lVeHBzOWx3dm9aU3BkQVExLXdfdlU5NF9vRmZaVk9XRFF3aDFsRjk1ZkZsVVZNZTBFSnRyeGVmQ1l3anJpZkF1dXR6cHVQTmRobDdDSGM1VE9iNXBPSTJlaGozLW9vcE5oY3FrVUtwaGk5LUF4ZWMwc0ZyeUdZSnJfbFMwdTJpb2ZwZE5CcTNqTjZQX3ZaVExJWEExcUtOLWRMaHdtTXRaVVJXV2ZiLU1rYXNxajBpSkI1eE9IWk14NzZwRENKYnpzTnhCLVNnMU5fMTliWG5JRlJILUd1UlhuUGVYV1dYVkY1cUVLR1hkNHhrSGd6LXUyaUE?oc=5) ⭐️ 7.0/10

中国任命副总理丁薛祥牵头全国性 AI 芯片研发攻坚行动，进一步加剧了中美技术竞争。此举标志着中国在半导体领域全面推动自主可控的战略意图。 这一动态凸显了中美科技战的持续升级，AI 芯片成为经济与军事优势的关键争夺领域。其结果可能重塑全球供应链格局，并决定未来技术领导权的归属。 以经济管理见长的丁薛祥将协调各部委及国有企业推动芯片突破。该计划可能涉及加大国家资金投入、人才引进以及绕过美国出口管制的努力。

google\_news · RFI · 7月25日 10:52

**背景**: 美国已对华实施先进半导体及制造设备的严格出口管制，旨在遏制中国 AI 和军事技术进步。作为回应，中国正通过大规模国家主导项目（如本次 AI 芯片攻坚）追求自主可控，以降低对外国技术的依赖。

**标签**: `#AI`, `#chips`, `#geopolitics`, `#China`, `#US-China relations`

---