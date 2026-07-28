---
layout: default
title: "Horizon Summary: 2026-07-28 (ZH)"
date: 2026-07-28
lang: zh
---

> 从 91 条内容中筛选出 11 条重要资讯。

---

1. [月之暗面发布 Kimi K3：首个开源 2.8 万亿参数模型](#item-1) ⭐️ 10.0/10
2. [Linux 内核提出用 hazard pointers 替代 RCU](#item-2) ⭐️ 9.0/10
3. [Fastjson2 曝远程代码执行漏洞，暂无补丁](#item-3) ⭐️ 9.0/10
4. [Anthropic 对开源权重模型的微妙立场](#item-4) ⭐️ 8.0/10
5. [Kik 用户名缺少下划线，无辜男子入狱 18 个月](#item-5) ⭐️ 8.0/10
6. [单人评估发现前沿 LLM 存在左倾偏见](#item-6) ⭐️ 8.0/10
7. [中国开始量产国产 DUV 光刻机](#item-7) ⭐️ 8.0/10
8. [微软推出首款网络安全专用 AI 模型](#item-8) ⭐️ 7.0/10
9. [英伟达微软等成立开放安全 AI 联盟](#item-9) ⭐️ 7.0/10
10. [钠离子电池即将大规模生产](#item-10) ⭐️ 7.0/10
11. [绿盟科技用大模型实现 AI 自主渗透测试](#item-11) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [月之暗面发布 Kimi K3：首个开源 2.8 万亿参数模型](https://huggingface.co/moonshotai/Kimi-K3) ⭐️ 10.0/10

月之暗面在 Hugging Face 上正式开源了 Kimi K3 模型，总参数量达 2.8 万亿，激活参数 104B，是全球首个开放的开源 3T 级模型。它采用了全新的 Kimi Delta Attention \(KDA\) 和 Attention Residuals \(AttnRes\) 架构，基于 Stable LatentMoE 框架，拥有 896 个专家，每 token 激活 16 个。 Kimi K3 标志着开源 AI 领域的重大里程碑，它证明超大规模模型（3T 级）可以公开开放，有望加速长上下文推理、多模态理解和智能体任务的研究与应用。其开源特性挑战了前沿模型闭源的趋势。 Kimi K3 原生支持文本、图像和视频理解，上下文窗口达 100 万 token，并支持 MXFP4 量化。在 GPQA Diamond、BrowseComp 和 DeepSWE 等基准测试中，它与 GPT-5.6 Sol、Claude Fable 5 等前沿模型互有胜负。

telegram · zaihuapd · 7月27日 15:15

**背景**: Kimi K3 采用混合专家（MoE）架构，将模型分为众多专门的子网络（专家），每个 token 仅激活部分专家以节省计算同时保持高容量。新的 KDA 和 AttnRes 机制旨在改善长序列和深层网络中的注意力质量。MXFP4 是 OCP Microscaling 标准下的 4 位量化格式，能降低内存占用并实现高效推理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.kimi.com/blog/kimi-k3">Kimi K3 Tech Blog: Open Frontier Intelligence</a></li>
<li><a href="https://arxiv.org/pdf/2603.15031">Attention Residuals</a></li>

</ul>
</details>

**社区讨论**: 社区注意到其许可证非标准：与之前的 K2 许可证不同，K3 要求年营收超过 2000 万美元的 Model-as-a-Service 企业必须与月之暗面签订单独协议，因此不能称为真正开源。一些人对模型的庞大规模和具有竞争力的定价（OpenRouter 上输入$3/百万 token，输出$15/百万 token）表示赞赏。

**标签**: `#AI`, `#大模型`, `#开源`, `#Moonshot AI`, `#Kimi K3`

---

<a id="item-2"></a>
## [Linux 内核提出用 hazard pointers 替代 RCU](https://lwn.net/Articles/1084015/) ⭐️ 9.0/10

Mathieu Desnoyers 和 Paul McKenney 为 Linux 内核提出了一种 hazard pointer 实现，作为广泛使用的 RCU 机制的性能改进替代方案。 如果被采纳，hazard pointers 可以减少无锁数据结构的内存开销和清理延迟，提升内核性能和可扩展性，尤其是在 RCU 宽限期延迟成问题的场景中。 Hazard pointers 通过跟踪哪些指针正在被使用来加速回收未用对象，代价是每个线程的开销。该实现正在内核邮件列表上接受审查。

rss · LWN.net · 7月27日 16:51

**背景**: Read-copy-update（RCU）是一种同步机制，确保在所有读取者完成之前不会删除数据，这可能会增加内存开销和延迟。Hazard pointers 是一种替代方案，它为每个线程关联一组受保护的指针，一旦没有线程持有引用，就可以立即回收。它们已经是 C++26 标准的一部分。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Hazard_pointer">Hazard pointer - Wikipedia</a></li>
<li><a href="https://docs.kernel.org/RCU/whatisRCU.html">What is RCU? -- “Read, Copy, Update” — The Linux Kernel documentation</a></li>

</ul>
</details>

**标签**: `#linux-kernel`, `#lockless-data-structures`, `#hazard-pointers`, `#RCU`, `#kernel-development`

---

<a id="item-3"></a>
## [Fastjson2 曝远程代码执行漏洞，暂无补丁](https://mp.weixin.qq.com/s/LJaul1jNjK9pXRAkoUiMEA) ⭐️ 9.0/10

7 月 27 日，长亭科技披露 Fastjson2 存在远程代码执行漏洞，影响 2.0.62 及以前所有版本。项目维护者已确认问题，但尚未发布补丁。 Fastjson2 是 Java 应用中广泛使用的 JSON 处理库，该漏洞允许攻击者绕过 AutoType 校验执行任意代码。由于漏洞严重且无补丁，许多生产系统面临直接风险。 该漏洞绕过了 Fastjson2 2.0.62 及以前版本中的 AutoType 安全机制。修复方案 PR \#7695 已被关闭且未合入主分支，因此所有已发布版本均存在漏洞。

telegram · zaihuapd · 7月27日 10:31

**背景**: Fastjson2 是阿里巴巴开发的高性能 Java JSON 库，提供快速的 JSON 序列化/反序列化功能。AutoType 是一个在 JSON 中嵌入类型信息以支持多态反序列化的特性，但常被用作攻击向量。与 Fastjson 1.x 不同，Fastjson 2 要求显式开启 AutoType 并采用默认拒绝策略，但此漏洞绕过了这些保护。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/alibaba/fastjson2">GitHub - alibaba/fastjson2: FASTJSON2 is a Java JSON ...</a></li>
<li><a href="https://alibaba.github.io/fastjson2/autotype_cn.html">FASTJSON 2 Autotype机制介绍 | fastjson2</a></li>

</ul>
</details>

**标签**: `#security`, `#vulnerability`, `#fastjson`, `#RCE`, `#Java`

---

<a id="item-4"></a>
## [Anthropic 对开源权重模型的微妙立场](https://www.anthropic.com/news/position-open-weights-models) ⭐️ 8.0/10

Anthropic 发表了一份立场声明，反对禁止开源权重模型，同时支持对华先进芯片出口管制以及所有能力足够强的模型必须接受强制性安全测试。 这一来自领先 AI 公司的政策声明影响了正在进行的 AI 治理讨论，但批评者认为这是虚伪且利己的，因为它保护了 Anthropic 的闭源商业模式，同时限制了开源权重竞争对手。 Anthropic 明确不主张彻底禁止开源权重模型，但支持对华芯片出口管制，并认为所有具备足够能力的模型都应进行强制性安全测试，批评者称由于成本过高这实际上等于禁令。

hackernews · surprisetalk · 7月27日 22:03 · [社区讨论](https://news.ycombinator.com/item?id=49076057)

**背景**: 开源权重模型是指其训练参数（权重）公开发布的 AI 模型，允许任何人下载、运行和微调。这与 Anthropic 的 Claude 等闭源模型形成对比，后者仅能通过 API 访问。争论的核心在于平衡创新与安全，一方面担忧开源权重可能被滥用于有害目的，另一方面限制措施可能阻碍研究和竞争。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://allthings.how/what-is-an-open-weight-ai-model-and-how-to-use-one/">What is an Open Weight AI Model and How to Use One</a></li>
<li><a href="https://opensource.org/ai/open-weights">Open Weights: not quite what you’ve been told</a></li>

</ul>
</details>

**社区讨论**: 社区评论非常批评：用户指责 Anthropic 虚伪，指出其反对禁令却支持芯片出口管制的矛盾，并认为强制性安全测试实际上会禁止开源权重模型。一些人认为 CEO Dario Amodei 的立场是出于自身利益，保护 Anthropic 专有且昂贵的模型免受开源竞争。

**标签**: `#AI safety`, `#open-weights`, `#policy`, `#Anthropic`, `#regulation`

---

<a id="item-5"></a>
## [Kik 用户名缺少下划线，无辜男子入狱 18 个月](https://arstechnica.com/tech-policy/2026/07/police-missed-one-underscore-and-sent-the-wrong-man-to-prison/) ⭐️ 8.0/10

警方在向 Kik 发出传票时，误将用户“fus\_ro\_dah”中的下划线遗漏，请求了错误用户的信息，导致一名无辜男子被错误定罪并监禁 18 个月。 此案暴露了数字取证流程和法律程序中的严重缺陷，表明一个简单的打字错误就能毁掉人生，并削弱公众对司法系统的信任。 受害者与犯罪毫无关联；未发现不雅图像，警方也无法证明他在相关时段使用过 Kik。尽管如此，他仍被以引诱未成年人、提供色情材料及持有儿童色情制品三项罪名定罪。

hackernews · quantified · 7月27日 22:10 · [社区讨论](https://news.ycombinator.com/item?id=49076116)

**背景**: 数字取证依赖于用户名和 IP 地址等准确标识符。Kik 用户名区分大小写并包含下划线；缺失下划线可能指向不同用户。本案中，错误通过传票、电子邮件记录和 ISP 数据层层放大，最终导致无辜者被起诉。

**社区讨论**: 评论者对系统性的失败表示愤慨，指出辩护律师本应更严格地质疑证据。部分人质疑受害者除了撤销定罪外未获得任何赔偿，强调名誉损害将伴随一生。

**标签**: `#digital forensics`, `#wrongful conviction`, `#police error`, `#legal system`, `#HackerNews`

---

<a id="item-6"></a>
## [单人评估发现前沿 LLM 存在左倾偏见](https://www.reddit.com/r/MachineLearning/comments/1v8fnzw/evaluated_6_frontier_llms_gpt54_claude_sonnet_46/) ⭐️ 8.0/10

一项对六款前沿 LLM（GPT-5.4、Claude Sonnet 4.6、Claude Opus 4.7、Gemini Pro/Flash、Grok 4.3）进行的单人评估，使用了八个偏见基准（约 20,600 个样本），发现所有模型均表现出左倾政治偏见，并在种族相关问题上表现出显著的拒绝回答行为。 该评估提供了实证证据，表明前沿 LLM 一致表现出左倾偏见，即使它们自我报告相反（例如 Grok）。在种族问题上的高拒绝率也引发了在敏感场景部署这些模型时的公平性和透明度问题。 该评估使用了八个已建立的偏见基准（WinoBias、BBQ Race/Ethnicity、SeeGULL、OpinionsQA、cajcodes Political Bias、Hyperpartisan News、Political Compass），每项任务仅使用单一提示模板，且未进行多次运行平均。值得注意的是，GPT-5.4 拒绝了 20.3%的种族相关问题，Claude Opus 4.7 拒绝了 13.8%，Grok 拒绝了 9.5%。

reddit · r/MachineLearning · /u/marggggggggg · 7月27日 22:37

**背景**: 诸如 BBQ（偏见基准问答）之类的偏见基准用于评估问答中的社会偏见，涵盖种族和性别等类别。cajcodes Political Bias 数据集包含从保守（0）到自由（4）的偏见评分标注的合成语句。拒绝行为，即 LLM 拒绝回答，是一种已知的安全机制，但也可能表明隐藏的偏见或过度谨慎。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://engineersofai.com/docs/llms/llm-evaluation/safety-and-bias-evaluation">Safety and Bias Evaluation | EngineersOfAI - Technical Education for...</a></li>
<li><a href="https://huggingface.co/datasets/cajcodes/political-bias">cajcodes/political-bias · Datasets at Hugging Face</a></li>
<li><a href="https://arxiv.org/html/2407.18418v1">The Art of Refusal: A Survey of Abstention in Large Language Models</a></li>

</ul>
</details>

**标签**: `#bias`, `#LLM evaluation`, `#fairness`, `#political bias`, `#machine learning`

---

<a id="item-7"></a>
## [中国开始量产国产 DUV 光刻机](https://www.theinformation.com/articles/china-starts-mass-producing-homegrown-duv-chipmaking-tools-advance-local-chip-industry) ⭐️ 8.0/10

中国已开始大规模生产自主研发的浸没式深紫外（DUV）光刻机，今年目标生产约 5 台，将交付给中芯国际和华虹半导体等国内主要芯片制造商。 这标志着中国在美国主导的出口限制下推动半导体自给自足的重要一步，并可能逐步改变全球光刻机供应链格局，减少对 ASML 的依赖。 国产 DUV 设备在性能和可靠性上仍落后于 ASML，芯片厂商可能需要数月测试才能投入量产。部分关键部件来自日本，今年本地供应链延误已影响产量。

telegram · zaihuapd · 7月27日 14:10

**背景**: 深紫外（DUV）光刻使用 193 纳米波长的光来印制集成电路；浸没式光刻在透镜和晶圆之间引入液体（通常是水）以提高分辨率，可制造 45 纳米以下的特征。ASML 目前主导先进光刻机市场，中国企业正努力开发替代品。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/DUV_lithography">DUV lithography</a></li>
<li><a href="https://en.wikipedia.org/wiki/Immersion_lithography">Immersion lithography</a></li>

</ul>
</details>

**标签**: `#semiconductor`, `#lithography`, `#China`, `#DUV`, `#manufacturing`

---

<a id="item-8"></a>
## [微软推出首款网络安全专用 AI 模型](https://news.google.com/rss/articles/CBMiSEFVX3lxTE90NHNwakN1UXZ6dXlwR0F2YmFFM2tPOEIzY2k4RlFGUUtLVEhjc2NIRE8xSjdpUkJkb0VkUERrZlZPTzM0ODN5Tw?oc=5) ⭐️ 7.0/10

微软推出了其首款专为网络安全设计的 AI 模型，并同步发布了一个代号为 MDASH 的多模型智能安全平台，该平台可协调 100 多个专用智能体，实现端到端的漏洞发现与验证。 这标志着大规模 AI 防御的重大转变，因为攻击者越来越多地利用 AI 进行自动化的复杂攻击。微软的入局表明，大型科技公司正大力投资专用 AI 模型以应对 AI 驱动的威胁，有望为网络安全行业树立新标准。 该模型是微软多模型 AI 协调器（MDASH）的一部分，该协调器结合了多个专用智能体以覆盖安全的不同方面。此外，微软还开发了一款轻量级扫描仪，用于检测开源大模型中的后门，以提升对 AI 系统的信任。

google\_news · 财联社 · 7月28日 00:41

**背景**: 网络安全越来越依赖 AI 来防御和发起攻击。传统的基于规则的系统难以应对能够实时适应的 AI 驱动威胁。微软的新模型旨在自动化威胁检测和响应，利用机器学习识别新型攻击模式。该公司还积极参与 AI 安全研究，包括用于验证 AI 模型完整性的工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcrunch.com/2026/07/27/microsoft-launches-its-first-cyber-model-and-a-new-agentic-cybersecurity-system/">Microsoft launches its first cybersecurity model , plus... | TechCrunch</a></li>
<li><a href="https://thehackernews.com/2026/02/microsoft-develops-scanner-to-detect.html">Microsoft Develops Scanner to Detect Backdoors in Open-Weight...</a></li>

</ul>
</details>

**标签**: `#AI`, `#Cybersecurity`, `#Microsoft`, `#Security`

---

<a id="item-9"></a>
## [英伟达微软等成立开放安全 AI 联盟](https://news.google.com/rss/articles/CBMickFVX3lxTE5KeGhzckxyX1V4ZlZjMlJjcjFUQ1ZxX0xUdmNSYWw0R0JqTVp6N2JoR19ocTMwZkUxRFpKSmhfMnVMVUYwekdaTEpRU0RrSWhoLWQwNXVQVzNpUzFPRHhZelJ4cGhRRzFkQ1VTZmE5OTkydw?oc=5) ⭐️ 7.0/10

英伟达、微软等科技公司联合成立了一个开放安全 AI 联盟，旨在利用人工智能提升网络安全防御能力。 这一合作标志着业界在利用 AI 加强网络安全方面的重大努力，可能带来更先进、更协同的网络威胁防御机制。 该联盟被描述为“开放”，表明其邀请更广泛的组织参与，并旨在分享最佳实践和 AI 驱动的安全解决方案。

google\_news · 新浪新闻\_手机新浪网 · 7月28日 01:13

**背景**: 网络安全威胁日益复杂，传统防御方法往往难以跟上。人工智能技术，尤其是机器学习，能够分析海量数据以检测异常并实时响应威胁，使其成为网络安全领域有前景的工具。

**标签**: `#AI`, `#cybersecurity`, `#NVIDIA`, `#Microsoft`, `#alliance`

---

<a id="item-10"></a>
## [钠离子电池即将大规模生产](https://news.google.com/rss/articles/CBMicEFVX3lxTE5fb29oR3k3N1VwV1htZC1ma0RLYW9CVk1aV3dyS3hxZzAyTEU5Z0c5ZFN4MVh3dDVZS19PRXZyNWdBWmYtVzAyM245Q2FvemFWZnFIUVY1V0dEenNfQkF5V2dITnNrdkJxRV8wMWZNZU8?oc=5) ⭐️ 7.0/10

据报道，钠离子电池即将迈入大规模生产阶段，标志着向商业化迈出了重要一步。 钠离子电池为锂离子电池提供了更便宜且资源丰富的替代方案，可能降低储能和电动汽车的成本及供应链风险，加速可再生能源和电动汽车的普及。 目前全球钠离子电池产量不到锂离子电池的 1%，但雅迪等公司已推出使用钠离子电池的轻便摩托车，首款钠离子电动汽车于 2023 年底在中国亮相。

google\_news · 中国科技网 · 7月27日 17:01

**背景**: 锂离子电池主导便携电子和电动汽车，但依赖稀缺的锂和钴。钠离子电池使用丰富的钠（类似食盐），工作原理相似，但能量密度较低，更适合固定储能和短途车辆。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Sodium-ion_battery">Sodium-ion battery - Wikipedia</a></li>
<li><a href="https://www.iea.org/commentaries/sodium-ion-battery-momentum-grows-but-challenges-remain">Sodium-ion battery momentum grows, but challenges remain – Analysis - IEA</a></li>

</ul>
</details>

**标签**: `#sodium-ion batteries`, `#energy storage`, `#mass production`, `#battery technology`

---

<a id="item-11"></a>
## [绿盟科技用大模型实现 AI 自主渗透测试](https://news.google.com/rss/articles/CBMipwFBVV95cUxPdUoyN0g1ankyaWFLSTZEOUZDUXV2TUxjS0xPZUFlb3FKTm1ya29PZG95OG1XYmtIdFBwS1JTZDBIbkliMF94YU5Ub29tR0J5dkN5VW9OYVF4bjRCZFRVSWZiNkJ2cGFROTUwcHVhUE54MF9oZ3l1ckVaeFRmLUxKem5JXzJrZ1Zfb21WMmJjWE1Oa01MbGc5R1MtLVlMV3dTZmFKLWMtSQ?oc=5) ⭐️ 7.0/10

绿盟科技声称已开发出基于大语言模型的自主渗透测试系统，标志着 AI 驱动网络安全的新阶段。该系统能够自主执行复杂的渗透测试任务，无需人工干预。 这一进展可大幅减少渗透测试所需的时间和专业知识，使安全评估更便捷、更持续。同时也引发了对 AI 自动化攻击能力的潜在担忧。 据称该系统利用大语言模型自主推理漏洞并执行利用策略。但未披露技术细节或与现有工具（如 PentestGPT 或 PentAGI）的比较。

google\_news · 新浪财经 · 7月28日 02:52

**背景**: 渗透测试是一种通过模拟攻击来评估安全性的受控授权方法。传统上，它需要高技能安全专家手动识别漏洞并执行利用。最近的研究，如 USENIX Security 2024 上展示的 PentestGPT，已表明大语言模型可以辅助或部分自动化这些任务，但完全自主的渗透测试仍是一个具有挑战性的目标。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.usenix.org/conference/usenixsecurity24/presentation/deng">PentestGPT: Evaluating and Harnessing Large Language Models for Automated Penetration Testing | USENIX</a></li>
<li><a href="https://pentagi.com/">PentAGI - Advanced AI-Powered Penetration Testing</a></li>
<li><a href="https://arxiv.org/html/2507.00829v1">On the Surprising Efficacy of LLMs for Penetration-Testing</a></li>

</ul>
</details>

**标签**: `#AI`, `#cybersecurity`, `#penetration testing`, `#large language models`

---