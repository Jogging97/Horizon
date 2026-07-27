---
layout: default
title: "Horizon Summary: 2026-07-27 (ZH)"
date: 2026-07-27
lang: zh
---

> 从 94 条内容中筛选出 10 条重要资讯。

---

1. [美国公民在边境搜查中使用紧急擦除功能后面临指控](#item-1) ⭐️ 9.0/10
2. [vLLM v0.26.0 新增 Inkling 模型支持与 DeepSeek-V4 性能优化](#item-2) ⭐️ 8.0/10
3. [Decker 以现代 1 位图形重现 HyperCard 的简洁性](#item-3) ⭐️ 8.0/10
4. [AI 代币转售与欺诈泛滥市场](#item-4) ⭐️ 8.0/10
5. [欧盟委员会提议通过浏览器隐私设置消灭 Cookie 横幅](#item-5) ⭐️ 8.0/10
6. [用 ARM64 汇编从零实现 YOLO26n 推理](#item-6) ⭐️ 8.0/10
7. [开源 4B 模型接近 o3 级瑞典医学问答准确率](#item-7) ⭐️ 8.0/10
8. [英伟达与 Anthropic 在旧金山宣布重大 AI 协议](#item-8) ⭐️ 7.0/10
9. [硅谷加速推动人工智能军事化](#item-9) ⭐️ 7.0/10
10. [皮米尺度尺实现原子观测](#item-10) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [美国公民在边境搜查中使用紧急擦除功能后面临指控](https://www.techspot.com/news/113236-us-prosecutors-charge-atlanta-man-after-grapheneos-phone.html) ⭐️ 9.0/10

一名美国公民在机场边境搜查中使用 GrapheneOS 的紧急擦除功能后遭到指控，这是美国首例涉及该安全功能的法律案件。 此案凸显了在美国边境使用紧急擦除等隐私功能的法律风险，可能使用户望而却步，或促使相关工具的设计和认知发生变化。 GrapheneOS 的紧急擦除功能在输入特定 PIN 时会完全重置设备，包括移除 eSIM；案件焦点在于该行为是否构成妨碍边境搜查。

hackernews · eecc · 7月26日 22:21 · [社区讨论](https://news.ycombinator.com/item?id=49063022)

**背景**: GrapheneOS 是一款注重隐私的基于 Android 的操作系统，它提供了紧急 PIN/密码功能，可在胁迫下擦除设备。美国边境官员拥有广泛的设备搜查权限，故意擦除数据可能引发法律后果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ibtimes.co.uk/us-federal-case-duress-passcodes-border-1810655">American Charged in First Known US Case Over Use of a &#x27; Duress ...</a></li>
<li><a href="https://privacygear.nl/en/guides/grapheneos-duress-pin-guide/">GrapheneOS duress PIN: wipe your phone under... — PrivacyGear.nl</a></li>
<li><a href="https://en.wikipedia.org/wiki/GrapheneOS">GrapheneOS</a></li>

</ul>
</details>

**社区讨论**: 评论者们就法律风险展开辩论，一些人认为用户必须承担使用紧急功能带来的后果，另一些人则建议使用 VeraCrypt 的诱饵操作系统等替代方案以避免被定罪。

**标签**: `#security`, `#GrapheneOS`, `#border surveillance`, `#digital rights`, `#encryption`

---

<a id="item-2"></a>
## [vLLM v0.26.0 新增 Inkling 模型支持与 DeepSeek-V4 性能优化](https://github.com/vllm-project/vllm/releases/tag/v0.26.0) ⭐️ 8.0/10

vLLM v0.26.0 新增了对 Inkling 模型系列的支持，为 DeepSeek-V4 带来了显著的性能优化（如专用路由内核、fused\_topk\_bias），通过 head\_dtype 引入了 fp32 lm\_head，并扩展了对 AMD 和 XPU 平台的硬件兼容性。 此版本通过支持新兴模型架构并在 DeepSeek-V4 等流行模型上实现重大性能提升，巩固了 vLLM 作为领先开源推理引擎的地位。扩展的硬件支持降低了 AMD 和 XPU 系统用户的使用门槛。 Inkling 模型系列获得了全面支持，包括分段 CUDA 图、Hopper FA4 相对注意力、MTP=1 推测解码和 ModelOpt NVFP4 量化。DeepSeek-V4 优化通过专用路由内核实现了高达 2.94% 的端到端 TPOT 提升。

github · khluu · 7月27日 01:06

**背景**: vLLM 是一个用于大型语言模型的高性能推理和服务引擎，因其高效的 PagedAttention 和 CUDA 图优化而被广泛用于生产环境。CUDA 图通过捕获操作序列来减少内核启动开销，而分段 CUDA 图则允许为可变批量大小提供动态图形形状。此次新版本延续了 vLLM 快速创新的步伐，共有 212 位贡献者提交了超过 400 次提交。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/thinkingmachines/Inkling">thinkingmachines/ Inkling · Hugging Face</a></li>
<li><a href="https://docs.vllm.ai/en/stable/design/cuda_graphs/">CUDA Graphs - vLLM</a></li>
<li><a href="https://docs.vllm.ai/en/latest/features/speculative_decoding/mtp/">MTP (Multi-Token Prediction) - vLLM</a></li>

</ul>
</details>

**标签**: `#LLM`, `#vLLM`, `#inference`, `#performance`, `#open-source`

---

<a id="item-3"></a>
## [Decker 以现代 1 位图形重现 HyperCard 的简洁性](https://beyondloom.com/decker/) ⭐️ 8.0/10

Decker 是一个将 HyperCard 的简便与强大功能带到现代系统的平台，支持 1 位图形和基于卡片的交互式媒体环境。 对于怀旧用户和错过 HyperCard 时代的人来说，Decker 提供了一个难得的机会，可以体验或重新发现一种无需复杂编程即可创建交互式内容的直观工具。 Decker 采用让人联想到早期 Macintosh 美学的 1 位显示，其可编写脚本的卡片/堆栈模型忠实于原始 HyperCard 的理念。

hackernews · tosh · 7月26日 18:23 · [社区讨论](https://news.ycombinator.com/item?id=49060856)

**背景**: HyperCard 是经典 Mac OS 上的革命性软件环境，允许用户创建包含文本、图像和脚本的“卡堆”，使非开发人员也能轻松编程。Decker 在现代平台上复兴了这一概念，在保持简洁性的同时更新了技术。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://8bitnews.io/article/1-bit-graphics">1 - Bit Graphics</a></li>

</ul>
</details>

**社区讨论**: 评论者表达了对 HyperCard 易用性和非程序员潜力的怀念，但有些人质疑这样的平台在今天是否还有空间。其他人欣赏其美学和功能，但也有少数批评者认为像 1 位图形这样的自我限制会阻碍实用性。

**标签**: `#HyperCard`, `#retro computing`, `#visual programming`, `#macOS`, `#interactive media`

---

<a id="item-4"></a>
## [AI 代币转售与欺诈泛滥市场](https://vectoral.com/blog/token-relay-market) ⭐️ 8.0/10

一项详细分析揭示，AI 代币转售和欺诈在 AI 市场中普遍存在，其手段包括滥用计费系统、免费额度和订阅模式，造成了不公平的竞争格局。转售商通过盗用账户和支付欺诈，以官方价格 70–93%的折扣提供 AI 代币。 这种系统性欺诈削弱了 AI 平台的财务诚信，扭曲了竞争，损害了无法匹敌折扣价格的合法企业和初创公司。随着代币使用成为关键指标，这也引发了对 AI API 市场的安全性和可信度的担忧。 转售操作通常依赖 AWS、Azure 等云服务商提供的免费额度，或通过订阅滥用，大规模使用代币进行未经授权的自动化。文章指出，攻击者手段高超，利用被盗金融工具和盗用账户来制造大规模的折扣代币市场。

hackernews · mlenhard · 7月26日 15:17 · [社区讨论](https://news.ycombinator.com/item?id=49058993)

**背景**: AI 代币是用于衡量和计费 AI 模型使用的计算输出单位，类似于 API 调用。随着 AI 应用的激增，代币欺诈也日益增长，转售商通过非法手段提供深度折扣。这个问题与数字广告领域的早期转售市场类似，其中计费系统滥用创造了折扣广告展示市场。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://explainx.ai/blog/ai-token-black-market-claude-resellers-distillation-2026">AI Token Black Market: Claude Resellers at 70–93% Off ...</a></li>
<li><a href="https://techcrunch.com/2026/05/28/just-like-gold-and-oil-well-soon-be-able-to-trade-ai-token-futures/">Just like gold and oil, we&#x27;ll soon be able to trade AI token futures | TechCrunch</a></li>

</ul>
</details>

**社区讨论**: 社区评论强调了与广告欺诈的历史相似性、免费云额度在促成廉价推理中的作用，以及设计防止滥用的订阅合同的挑战。一位评论者指出代币欺诈是一场“猫鼠游戏”，并提到一个名为 WorkOS Radar 的产品旨在大规模解决这一问题。

**标签**: `#AI token economy`, `#fraud`, `#API reselling`, `#subscription models`, `#financial integrity`

---

<a id="item-5"></a>
## [欧盟委员会提议通过浏览器隐私设置消灭 Cookie 横幅](https://killthecookiebanner.eu/) ⭐️ 8.0/10

欧盟委员会提出允许用户在浏览器中一次性设置隐私偏好，从而消除每个网站上单独的 Cookie 横幅。 这一转变可显著改善用户体验和网络无障碍性，同时通过一个通用的、具有法律约束力的信号来取代常被忽视的横幅，从而加强隐私法规的执行。 该提案与现有的机制（如全球隐私控制（GPC））一致，后者从浏览器发送通用退出信号，并已在《加州消费者隐私法案》（CCPA）等法律中获得法律认可。

hackernews · rapnie · 7月26日 11:53 · [社区讨论](https://news.ycombinator.com/item?id=49057175)

**背景**: Cookie 横幅是根据欧盟《电子隐私指令》强制要求的，用于获取用户对非必要 Cookie 的同意。然而，它们因侵入性、误导性且经常不被网站尊重而受到广泛批评。浏览器级隐私设置旨在简化同意管理并减少用户疲劳。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Global_Privacy_Control">Global Privacy Control - Wikipedia</a></li>
<li><a href="https://globalprivacycontrol.org/">Global Privacy Control — Take Control Of Your Privacy</a></li>
<li><a href="https://termly.io/resources/articles/what-is-global-privacy-control/">What Is Global Privacy Control (GPC)? Explanation for Businesses</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍支持该提案，指出横幅令人烦恼、普遍不合规以及无障碍问题。一些人认为横幅不能构成知情同意，并呼吁对不合规网站进行更严格的执法和罚款。

**标签**: `#privacy`, `#cookie banners`, `#EU regulation`, `#web standards`, `#user experience`

---

<a id="item-6"></a>
## [用 ARM64 汇编从零实现 YOLO26n 推理](https://www.reddit.com/r/MachineLearning/comments/1v6w394/i_implemented_the_yolo26n_model_inference_from/) ⭐️ 8.0/10

一个本科毕业设计项目完全从零使用 ARM64 汇编和 C 语言实现了 YOLO26n 模型推理，不依赖任何推理框架，在树莓派 4 上成功进行目标检测。 该实现包含 ARM NEON SIMD 优化、Winograd 卷积、优化 GEMM 内核、缓存感知分块、自定义 ARM64 微内核和算子融合，但性能提升低于最初预期。

reddit · r/MachineLearning · /u/Forward\_Confusion902 · 7月26日 06:43

**背景**: YOLO（You Only Look Once）是一种流行的实时目标检测模型。ARM64 是一种 64 位处理器架构，广泛应用于移动和嵌入式设备。NEON SIMD 通过并行数据处理提升速度。Winograd 卷积通过减少乘法次数来降低卷积计算复杂度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2201.10369">[2201.10369] Winograd Convolution for Deep Neural Networks: Efficient Point Selection</a></li>
<li><a href="https://www.linkedin.com/pulse/introduction-arm-neon-simd-optimization-vijay-panchal">Introduction to ARM Neon SIMD Optimization</a></li>
<li><a href="https://medium.com/data-science/how-pytorch-2-0-accelerates-deep-learning-with-operator-fusion-and-cpu-gpu-code-generation-35132a85bd26">How Pytorch 2.0 Accelerates Deep Learning with Operator Fusion ...</a></li>

</ul>
</details>

**标签**: `#ARM64`, `#YOLO`, `#edge AI`, `#inference`, `#assembly`

---

<a id="item-7"></a>
## [开源 4B 模型接近 o3 级瑞典医学问答准确率](https://www.reddit.com/r/MachineLearning/comments/1v71wds/openweight_4b_models_approach_o3level_medical/) ⭐️ 8.0/10

微调后的开源 4B 模型在瑞典医学考试问题上达到 87%的准确率，逼近 OpenAI o3 模型在 MedQA-SWE 数据集上 88%的准确率。 这表明通过适当微调，小型高效的开源模型在专业任务上可媲美最先进的闭源模型，使先进医学 AI 更易获取且成本更低。 最佳结果来自启用推理并采用 S-GRPO 论文早期退出技术的 Qwen3.5-4B；该模型尽管提示为瑞典语，但推理过程使用英语，而用于缩短推理轨迹的强化学习方法仅带来微小提升。

reddit · r/MachineLearning · /u/AccomplishedCat4770 · 7月26日 11:58

**背景**: MedQA-SWE 是首个瑞典语开源临床问答数据集，包含来自医学执业考试的 3180 道多选题。MedGemma 是基于 Gemma 模型为医疗应用微调的一系列模型。S-GRPO 是一种强化学习方法，允许从推理轨迹中提前退出以控制输出长度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developers.google.com/health-ai-developer-foundations/medgemma/model-card">MedGemma 1.5 model card | Health AI Developer Foundations | Google for Developers</a></li>
<li><a href="https://arxiv.org/abs/2505.07686">S - GRPO : Early Exit via Reinforcement Learning in Reasoning Models</a></li>
<li><a href="https://huggingface.co/datasets/nicher92/medqa-swe">nicher92/medqa-swe · Datasets at Hugging Face</a></li>

</ul>
</details>

**标签**: `#LLM`, `#medical QA`, `#fine-tuning`, `#open-weight models`, `#reasoning`

---

<a id="item-8"></a>
## [英伟达与 Anthropic 在旧金山宣布重大 AI 协议](https://news.google.com/rss/articles/CBMiSEFVX3lxTE9GMEV0MEpVTzc5MEZ5bmdVYTJZeUtCUFRQSnhFZGRBVlZJNHRBLWxzYVNlTWpTaUk0VHo3dFJoR3V3NmRUZ0UzbA?oc=5) ⭐️ 7.0/10

英伟达（Nvidia）和 Anthropic 在旧金山举行的韩美科技巨头峰会上宣布了一项重大协议。该协议可能涉及英伟达为 Anthropic 的 AI 开发提供计算基础设施。 这一合作加强了领先 AI 模型开发商 Anthropic 与主导硬件供应商英伟达之间的联盟，可能加速更安全、更强大 AI 系统的开发。这也凸显了美亚科技合作在人工智能领域日益增长的重要性。 协议的具体条款尚未披露，但预计涉及 Anthropic 使用英伟达最新 GPU 技术来训练其 Claude 模型。该协议是在包括三星和 SK 海力士等韩国大型企业高管出席的聚会上宣布的。

google\_news · 财联社 · 7月26日 20:11

**背景**: Anthropic 是一家专注于 AI 安全的公司，由前 OpenAI 员工创立，以其 Claude 系列大型语言模型而闻名。英伟达是用于训练和部署 AI 模型的 GPU 的主要供应商，受益于 AI 热潮。旧金山的会议汇集了韩国和美国的科技领袖，讨论尖端技术合作。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Anthropic">Anthropic</a></li>
<li><a href="https://en.wikipedia.org/wiki/Claude_%28AI%29">Claude ( AI ) - Wikipedia</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#Anthropic`, `#AI`, `#Business Deal`, `#Tech Giants`

---

<a id="item-9"></a>
## [硅谷加速推动人工智能军事化](https://news.google.com/rss/articles/CBMiUkFVX3lxTE1LTnBGWHY2bkdTSmo4ZTBJN0FpNGJGd1RVcWZoOUdNd3UwaGJYT2xXcEpRX2R1NmtrUEpjdWFqLU85WkY1N2hTLWFIUEJyZkpURmc?oc=5) ⭐️ 7.0/10

中国军网近期一篇文章指出，硅谷企业正越来越多地与军方合作，加速了人工智能的军事化进程。例如，“梅文计划”利用人工智能分析无人机视频并识别目标，体现了这一趋势。 人工智能融入军事行动引发了重大的伦理和地缘政治担忧，因为自主系统可能改变战争的性质。这一发展也对现有的关于致命自主武器系统的国际规范和军备控制努力构成了挑战。 由美国国防部发起的“梅文计划”利用无人机监控数据训练人工智能模型，以自动识别军事目标，并辅以人工验证。超过 100 个国家支持制定具有法律约束力的文书来规范自主武器系统，但大国仍在继续投资于人工智能军事技术。

google\_news · 中国军网 · 7月26日 23:23

**背景**: 人工智能军事化是指将人工智能技术用于军事目的，例如自主无人机、目标识别和决策支持系统。“梅文计划”是一个典型案例，利用深度学习分析大量无人机视频。致命自主武器系统（LAWS）可以在没有人为干预的情况下独立选择并攻击目标，引发了关于道德和控制的辩论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://oecd.ai/en/incidents/2024-04-23-5ec4">US Military &#x27;s Project Maven AI Causes Harm and Faces... - OECD. AI</a></li>
<li><a href="https://www.orfonline.org/expert-speak/ai-in-real-time-warfare-lessons-from-project-maven">AI in Real-Time Warfare: Lessons from Project Maven</a></li>
<li><a href="https://en.wikipedia.org/wiki/Autonomous_weapons_systems">Autonomous weapons systems</a></li>

</ul>
</details>

**标签**: `#AI`, `#military`, `#geopolitics`, `#technology ethics`

---

<a id="item-10"></a>
## [皮米尺度尺实现原子观测](https://news.google.com/rss/articles/CBMiYkFVX3lxTFBCX195NFdNOWYyTGRBeFdQaHpyRkJRM3FKNG1TWkdXX25DTTZBOXEtMkVXUjlQOEdFbUJUT3FRbWJzV2Y0dklBOHh2eVFOeWdxLXFTbkdOTWF3bmhRWFFfNS1R?oc=5) ⭐️ 7.0/10

中国科学院研发出一种皮米尺度尺，能够实现原子级别的观测，突破了光学显微镜的极限。 这一突破可能革新纳米技术和材料科学，提供前所未有的原子尺度测量精度，推动物理和化学领域的新发现。 该尺在皮米尺度（1 pm = 10⁻¹²米）工作，比埃更小，可测量单个原子及其位置。具体的技术方法或仪器细节尚未公开。

google\_news · 中国科学院 · 7月27日 02:25

**背景**: 传统光学显微镜受光波波长限制，分辨率仅约 200 纳米。原子尺度测量通常需要扫描隧道显微镜或电子显微镜等技术，而达到皮米精度是一项重大进展。皮米是长度单位，等于一万亿分之一米，常用于测量原子半径。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://unitconvertertool.com/convert/picometer-to-finger/">Convert pm to finger - Free Online Picometer to Finger Converter</a></li>
<li><a href="https://hackaday.com/2015/09/30/teeny-tiny-very-small-atomic-resolution-and-the-home-hobbyist/">Teeny Tiny Very Small – Atomic Resolution And The... | Hackaday</a></li>

</ul>
</details>

**标签**: `#nanoscale measurement`, `#picometer`, `#atomic observation`, `#Chinese Academy of Sciences`, `#microscopy`

---