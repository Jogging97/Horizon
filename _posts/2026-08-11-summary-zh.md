---
layout: default
title: "Horizon Summary: 2026-08-11 (ZH)"
date: 2026-08-11
lang: zh
---

> 从 100 条内容中筛选出 7 条重要资讯。

---

1. [Claude 将黎曼 zeta 函数零点下界提升至 67.2%](#item-1) ⭐️ 9.0/10
2. [vLLM v0.27.0 发布：新增 Kimi K3、多款新模型与 PyTorch 2.13](#item-2) ⭐️ 8.0/10
3. [英国式匿名限制借儿童安全法案蔓延至美国](#item-3) ⭐️ 8.0/10
4. [扎克伯格抨击封闭式 AI 竞争对手，Meta 回归开源模型](#item-4) ⭐️ 8.0/10
5. [Meta 发布 Muse Glimmer：面向常驻本地智能体的 30B 开源模型](#item-5) ⭐️ 8.0/10
6. [NVIDIA GPU 上的 TileRT 挑战专用低延迟推理芯片](#item-6) ⭐️ 8.0/10
7. [手工设定 Transformer 权重实现 100%乘法准确率，无需训练](#item-7) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Claude 将黎曼 zeta 函数零点下界提升至 67.2%](https://www.anthropic.com/research/riemann-zeta) ⭐️ 9.0/10

Anthropic 披露，一个未发布的 Claude 研究版本将黎曼 zeta 函数零点位于临界线上的比例下界从 41.6% 提高到 67.2%。该结果通过 Claude Code 中的长程智能体计算完成，消耗约 3100 万输出 token，并协调约 60 个子代理。 这一成果意义重大，因为它表明大语言模型能够将智能体推理与形式化验证相结合，从而做出真正的数学发现。它改进了 Baluyot、Goldston 等人的解析数论下界，可能加速 AI 辅助的数学研究。 这项工作并未解决黎曼猜想，而是利用 Baluyot 和 Goldston 的方法改进了相关的下界结果。Anthropic 的数学家和外部专家 Brian Conrey、Dan Goldston 已审查验证，Claude 还生成了可形式化验证的 Lean 证明，为这一改进提供了严谨性。

telegram · zaihuapd · 8月11日 01:32

**背景**: 黎曼 zeta 函数是数论中的核心对象，黎曼猜想断言其所有非平凡零点都位于临界线 Re\(s\)=1/2 上。长期以来，数学家们研究临界线上的零点比例，Hardy 等证明了正比例，此前的最佳下界约为 41.6%。Claude Code 是一种在终端中运行的智能体编程助手，可协调多个 AI 子代理；而 Lean 是一个证明助手，其最小可信内核可验证形式化的数学证明。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Lean_%28proof_assistant%29">Lean (proof assistant) - Wikipedia</a></li>
<li><a href="https://code.claude.com/docs/en/overview">Overview - Claude Code Docs</a></li>

</ul>
</details>

**标签**: `#AI-assisted math`, `#Riemann zeta`, `#theorem proving`, `#Claude`, `#Lean`

---

<a id="item-2"></a>
## [vLLM v0.27.0 发布：新增 Kimi K3、多款新模型与 PyTorch 2.13](https://github.com/vllm-project/vllm/releases/tag/v0.27.0) ⭐️ 8.0/10

vLLM v0.27.0 发布，包含 242 位贡献者提交的 561 个 commit，新增 Kimi K3 全栈支持、Qwen3.5 和 K-EXAONE-2.0 等新模型，并将 PyTorch 升级到 2.13.0，同时深化了 SM100 上的 FlashAttention 4 支持。 作为最广泛使用的 LLM 推理引擎之一，本次发布让用户可以直接部署 Kimi K3 等前沿模型，并受益于 DeepSeek-V4 吞吐提升和 JIT warmup 降低首请求延迟等性能优化。同时，它也体现了对 NVIDIA Rubin 与 ROCm gfx1250 等下一代硬件支持的持续推进。 值得关注的技术细节包括用于 Kimi K3 的 AttnRes 内核、DeepGEMM 支持、DSpark AR 融合以及可选的 shared-expert 分片。PyTorch 2.13.0 属于破坏性环境变更，XPU 和 CPU 后端也同步升级到了 torch 2.13。

github · khluu · 8月10日 21:18

**背景**: vLLM 是一个开源的高吞吐 LLM 推理与 serving 引擎。Attention Residuals（AttnRes）是一种用对前层输出的 softmax attention 取代固定累加的机制，从而能够实现高效的内核实现。DeepGEMM 是一个为 NVIDIA Hopper Tensor Cores 优化的简洁高效 FP8 矩阵乘法库，DSpark 则是一种用于加速解码的投机解码 draft-model 方法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/deepseek-ai/DeepGEMM">GitHub - deepseek-ai/ DeepGEMM : DeepGEMM : clean and efficient...</a></li>
<li><a href="https://arxiv.org/abs/2603.15031">[2603.15031] Attention Residuals - arXiv.org Hydra-2P: Making Attention Residuals Kernel-Efficient Self-evolving: AttnRes Kernel Optimization Given FLA Triton ... LOW-RANK ATTENTION RESIDUALS - arXiv.org flash-attn-res · PyPI</a></li>

</ul>
</details>

**标签**: `#vllm`, `#llm-inference`, `#release`, `#pytorch`, `#machine-learning`

---

<a id="item-3"></a>
## [英国式匿名限制借儿童安全法案蔓延至美国](https://www.effort.news/uk-lobby) ⭐️ 8.0/10

《Effort News》的一篇文章警告称，英国限制网络匿名性的做法正通过加州 AB 2273 和《儿童在线安全法》（KOSA）等儿童安全立法传入美国。文章认为，这些以英国《适龄设计规范》为蓝本的法案可能会终结成年人在网络上的匿名性。 此事意义重大，因为美国历来保护匿名言论，而采用英国式年龄验证可能会为数字身份要求开全球先例。这些法律一旦通过，将影响美国所有网民，而不仅仅是儿童。 文章具体提及加州议会法案 AB 2273 及其起草者对英国《适龄设计规范》（AADC）的依赖，以及可能将开源软件定罪化的《数字年龄保证法》AB 1856。文章还声称，非政府组织刻意利用“儿童安全”话语来推动数字身份法律，从而阻止成年人匿名上网。

hackernews · slowin · 8月10日 23:45 · [社区讨论](https://news.ycombinator.com/item?id=49251411)

**背景**: 英国《在线安全法》由 Ofcom 执行，要求提供色情内容的服务实施高效的年龄保证措施以阻止儿童访问。在美国，《儿童在线安全法》（KOSA）为平台设定了“注意义务”，要求其保护未成年人免受有害内容侵害。年龄保证技术包括年龄验证、年龄估计和年龄推断，正在快速发展，但也引发隐私担忧。文章将这些举动视为更广泛的跨大西洋终结网络匿名趋势的一部分。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gov.uk/government/collections/online-safety-act">Online Safety Act - GOV.UK</a></li>
<li><a href="https://www.ofcom.org.uk/online-safety/illegal-and-harmful-content/age-assurance">Age assurance duties under the Online Safety Act - Ofcom</a></li>
<li><a href="https://jamesmadison.org/what-is-kosa-and-what-does-it-mean-for-americas-teens/">What Is KOSA and What Does It Mean for... - James Madison Institute</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍持怀疑态度：有人批评众议员 Buffy Wicks 在科技立法上“轻信”，指出她的 AB 1043 和 AB 1856 由暗钱资助；还有人认为任何以“儿童安全”为名的说法都是在操纵人们放弃自由。不过也有反观点承认，许多人确实想保护儿童，科技公司发布的有害内容加剧了这种需求。

**标签**: `#privacy`, `#legislation`, `#digital identity`, `#anonymity`, `#child safety`

---

<a id="item-4"></a>
## [扎克伯格抨击封闭式 AI 竞争对手，Meta 回归开源模型](https://www.ft.com/content/4e3957f8-ea7c-4c46-a3de-cdce8e526878) ⭐️ 8.0/10

马克·扎克伯格在 Meta 官网发布了一篇题为《未来属于每个人》的宣言，公开抨击封闭式 AI 竞争对手，并重申 Meta 对开源 AI 模型的承诺。这标志着 Meta 明确回归开源模型战略，将 Llama 系列作为其 AI 路线的核心支柱。 此事意义重大，因为它影响着当前开源与封闭 AI 的辩论，涉及开发者、初创企业以及整个 AI 生态。扎克伯格的态度也表明，Meta 希望通过提供可自由获取、可定制的模型，与 OpenAI 和 Google 等专有 AI 领导者竞争。 Meta 的“开源”模型实际上是开放权重（open-weight），并非开放源代码促进会（OSI）定义下的完全开源，因为它们带有使用限制。宣言中有一段称开源可防止对安全和经济都不利的权力集中，但实际承诺的语气比一些新闻报道所暗示的要弱。

hackernews · root-parent · 8月10日 14:06 · [社区讨论](https://news.ycombinator.com/item?id=49243880)

**背景**: 开源 AI 模型免费、可定制且由社区驱动，而封闭源模型是专有的，对底层代码和权重访问有限。Meta 在 2023 年发布了 Llama 2 并称其为开源，但开放源代码促进会以及一些学者因使用限制而对此标签提出异议。开放权重模型允许用户下载和修改参数，已成为 AI 行业中的一个关键中间地带。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Llama_%28language_model%29">Llama (language model) - Wikipedia</a></li>
<li><a href="https://hai.stanford.edu/ai-definitions/what-is-an-open-weight-model">What is an Open-Weight Model? - Stanford HAI</a></li>
<li><a href="https://cloudsecurityalliance.org/articles/open-source-models-vs-closed-source-models-a-simple-guide">Open vs. Closed-Source AI Guide | CSA</a></li>

</ul>
</details>

**社区讨论**: 评论既包含怀疑也包含支持。像 bushido 和 ViktorRay 这样的用户认为，即便不信任扎克伯格，Meta 的开源贡献仍是“净正面”的；而 forestrywat 则讥讽这是“我快输了，所以要改规则”的举动。blueSky1989 则引用了一段关于 AI 权力集中的危险性，aabhay 指出实际承诺比头条标题所体现的要弱。

**标签**: `#AI`, `#Open Source`, `#Meta`, `#LLM`, `#Industry Strategy`

---

<a id="item-5"></a>
## [Meta 发布 Muse Glimmer：面向常驻本地智能体的 30B 开源模型](https://research.meta.ai/blog/introducing-muse-glimmer-open-agentic-model) ⭐️ 8.0/10

Meta 推出了 Muse Glimmer，一个 30B 参数、专为常驻本地智能体工作流优化的模型，并宣布将发布其开放权重版本以及 Muse Spark 1.2 的权重。该模型可在单张 GPU 上运行，采用 Apache 2.0 许可，并提供 GGUF 量化格式供本地推理。 此次发布标志着 AI 向高效、本地运行的智能体方向转变，可能降低对云端基础设施和大型数据中心的依赖。开放权重让开发者和自托管爱好者能够在消费级硬件上部署强大的自主智能体，也加剧了开放权重模型领域的竞争。 Muse Glimmer 将多步推理、可靠工具调用、多模态理解和失败恢复集成到单一模型中，可完全本地运行而无需云端。官方 GGUF 版本包括面向高显存平台的动态 K 量化版，以及可轻松装入 24GB 显存的 17GB 精简版。

hackernews · riordan · 8月10日 10:10 · [社区讨论](https://news.ycombinator.com/item?id=49241679)

**背景**: 开放权重模型是指核心组件公开发布、任何人都可以下载、查看并在自己的基础设施上运行的 AI 模型。常驻本地智能体是长期运行的自主助手，能够在没有云服务器的情况下读取文件、调用 API 并执行多步驟工作流。Meta 此举延续了行业向本地化、高效化 AI 发展的趋势，并与 Qwen 等其他开放权重模型形成对比。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/meta-models/Muse-Glimmer-30B">meta-models/Muse-Glimmer-30B · Hugging Face</a></li>
<li><a href="https://developer.meta.com/ai/models/muse-glimmer/">Muse Glimmer | Meta</a></li>
<li><a href="https://huggingface.co/meta-models/Muse-Glimmer-30B-GGUF">meta-models/Muse-Glimmer-30B-GGUF · Hugging Face</a></li>

</ul>
</details>

**社区讨论**: 评论区总体对本地 AI 和开放权重持乐观态度，有人将 Muse Glimmer 与即将发布的 Qwen3.8 27B 对比，并称赞 Meta 在开放权重美国模型领域占据主导地位的战略举措。但一位用户实测完整版模型后表示失望，称让其修复缺陷代码时模型不断循环、越陷越深。另一位用户则指出 Muse Spark 1.2 权重开源计划对自托管爱好者是特别好的消息。

**标签**: `#LLM`, `#Meta`, `#local AI`, `#open weights`, `#agentic workflows`

---

<a id="item-6"></a>
## [NVIDIA GPU 上的 TileRT 挑战专用低延迟推理芯片](https://newsletter.semianalysis.com/p/ultra-high-interactivity-on-nvidia) ⭐️ 8.0/10

SemiAnalysis 发文探讨 NVIDIA 的 TileRT 软件能否在 batch size 为 1 的推理场景中实现超高交互性，与 Cerebras、Groq LPU、SambaNova 等专用芯片竞争。文章描述了一种分离式设计：高吞吐量的 prefill 引擎搭配由 NVIDIA GPU 上的 TileRT 驱动的高交互性 decode 引擎。 如果 TileRT 能在通用 NVIDIA GPU 上缩小延迟差距，将削弱专用低延迟推理硬件的核心卖点，并改变 AI 系统选择基础设施的方式。这对所有部署交互式大语言模型应用、同时看重响应速度与成本的人来说都很重要。 TileRT 将整个 decode 计算图静态编译为 NVIDIA GPU 上的单个 persistent kernel，最大化计算、内存读写与通信之间的重叠。其 v0.1.3 版本新增了对 GLM-5 和 DeepSeek-V3.2 的支持，在 8 块 NVIDIA B200 GPU 上实现了超低延迟性能。

rss · Semianalysis · 8月10日 04:51

**背景**: 大语言模型推理通常分为两个阶段：prefill（处理输入提示）和 decode（逐 token 生成输出）。Prefill 是计算密集型，decode 是内存密集型，因此分离式服务（disaggregated serving）让二者运行在不同的 GPU 池上，以避免互相干扰并提高效率。传统 GPU 针对大 batch 的高吞吐量做了优化，而 Groq LPU 等专用加速器则优先保证 batch size 为 1 负载的确定性、低延迟执行。TileRT 是一个开源运行时，试图把这种低延迟特性带到 NVIDIA GPU 上。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://newsletter.semianalysis.com/p/ultra-high-interactivity-on-nvidia">Ultra-High Interactivity on NVIDIA GPUs? - TileRT InferenceX</a></li>
<li><a href="https://github.com/tile-ai/TileRT">GitHub - tile-ai/TileRT: Tile-Based Runtime for Ultra-Low-Latency LLM Inference · GitHub</a></li>
<li><a href="https://www.digitalocean.com/community/tutorials/prefill-decode-disaggregation">Prefill/Decode Disaggregation: Why Production LLM Inference ...</a></li>

</ul>
</details>

**标签**: `#NVIDIA`, `#Inference`, `#AI Hardware`, `#Low-Latency`, `#GPU Computing`

---

<a id="item-7"></a>
## [手工设定 Transformer 权重实现 100%乘法准确率，无需训练](https://www.reddit.com/r/MachineLearning/comments/1vkrnb5/transformers_are_famously_bad_at_arithmetic_so_i/) ⭐️ 8.0/10

作者使用自己编写的编译器 Torchwright，将小学乘法算法转换为标准 Phi-3 Hugging Face 检查点的权重。最终模型正确回答了全部 3,000,000 个三位数乘法问题，并发布了支持最高 12 位×12 位乘法的检查点。 这证明无需任何训练即可将精确算术直接编码到 Transformer 权重中，绕过了大型语言模型的一个众所周知弱点。它还为算术任务提供了一种可解释、低成本的替代方案，并可能启发新的神经符号或权重编译方法。 作者构建了四个变体——小学算法风格、硬件风格、草稿本风格和暴力记忆风格——它们计算相同的函数，但在层数、宽度、生成 token 数和参数使用上各有不同。相比之下，在禁用推理的情况下，六个前沿模型中有五个在七位数乘法上得分为 0/500。

reddit · r/MachineLearning · /u/notforrob · 8月10日 17:37

**背景**: Transformer 通常通过梯度下降训练来预测下一个 token，由于精确的多步计算难以从下一 token 预测中学习，它们常常在精确算术上表现不佳。此前的研究如 Tracr 和 ALTA 已探索将 RASP 程序编译到 Transformer 权重中，而草稿本（scratchpad）技术帮助模型将任务分解为中间步骤。这项工作延续了‘权重编译’而非训练的思路，展示了在标准模型中手工指定算法行为的一种实用方法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://paperswithcode.co/paper/2410.18077">ALTA: Compiler -Based Analysis of Transformers ... | Papers with Code</a></li>
<li><a href="https://arxiv.org/html/2406.06467v2">How Far Can Transformers Reason? The Globality Barrier and ...</a></li>
<li><a href="https://deepwiki.com/inschrift-spruch-raum/transturing/2.3-weight-compilation-vs.-training">Weight Compilation vs. Training | inschrift-spruch-raum ...</a></li>

</ul>
</details>

**标签**: `#transformers`, `#arithmetic`, `#weight compilation`, `#interpretability`, `#ML research`

---