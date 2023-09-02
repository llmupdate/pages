---
title: "大模型和AI到 202309 的重要进展"
date: 2023-09-01T20:05:01+08:00
draft: false
---

此文按时间线顺序记录下来 2023 年 9 月前大模型与AI领域，从个人角度看到的最重要的进展（后续可能会有部分内容更新）。
如果有不正确或者遗漏的内容，您可以 Github 将正确的内容提交 PR 到 https://github.com/llmupdate。

此文档更新的内容参考 https://llmupdate.com

## CodeLLaMa 发布，2023/08/24, Facebook

Facebook 基于 LLaMa 2 的底座，实现了 CodeLLaMa 编码模型。 写代码的能力略高于 ChatGPT 3.5，还没有达到 ChatGTP 4的能力。
平时在使用中 ChatGPT 3.5 的编码能力已经基本够用。 偶尔用 GPT 4 的效果甚至不如 ChatGPT 3.5。

随着 CodeLLaMa 的发布， WizardCoder， Phind CodeLLama 的代码生成效果甚至好于 CodeLLaMa， 比 ChatGPT 3.5 的生成效果都要好。 其中 WizardCoder 34B V1.0 的编码效果好于 GPT-4 0315 的版本。

按照 Phind-CodeLlama-34B-v1 给出的测评分数， Phind-CodeLlama-34B-v1 生成代码的效果也好于 GPT-4 0315 版本。

https://github.com/facebookresearch/codellama
https://ai.meta.com/research/publications/code-llama-open-foundation-models-for-code/
https://huggingface.co/Phind/Phind-CodeLlama-34B-v2
https://huggingface.co/codellama/CodeLlama-34b-Instruct-hf
https://huggingface.co/WizardLM/WizardCoder-Python-34B-V1.0

## Seamless m4t, 2023/08/22, Facebook

Seamless m4t 实现了200多种语言的跨语言的语音翻译，可以做到如下的功能：
* 跨语言的语音翻译：比如输入法语语音，自动翻译成英语语音/文本
* 跨语言的文本翻译：比如输入法语文本，自动翻译成英语文本/语音

当然同一种语言也是支持的。 Seamless m4t 既实现了 ASR 语音识别，又实现了 TTS 文本转语音，同时实现了跨语言的自动翻译。
意味着翻译，同声传译都可以被 AI 来替代。

https://ai.meta.com/blog/seamless-m4t/
https://about.fb.com/news/2023/08/seamlessm4t-ai-translation-model/
https://about.fb.com/news/2023/05/ai-massively-multilingual-speech-technology/
https://huggingface.co/spaces/facebook/seamless_m4t

## LLaMa 2, 2023/07/18, Facebook

LLaMa2 是在 2023年1月到7月之间训练的模型。 Facebook 发布了 7B, 13B, 70B 的 LLaMa 2模型，分别有70亿，130亿，700亿参数。 

LLaMa2 相比 LLaMa 多了 40% 的训练数据，提升了1倍的上下文长度到4k，有更好的逻辑推理能力，回复更加安全，各项测评的分数更高，且允许商用。 随着 LLaMa 2 的发布，大量开源的基于 LLaMa 2 的效果更好的二次训练/微调的模型出来。 

LLaMa 2 在大量的测试中接近 ChatGPT 3.5 甚至超过 ChatGPT 3.5 的效果。

https://github.com/facebookresearch/llama/

https://ai.meta.com/research/publications/llama-2-open-foundation-and-fine-tuned-chat-models/

https://github.com/facebookresearch/llama-recipes/

https://huggingface.co/meta-llama


## StableDiffusion SDXL 1.0, 2023/07/18, Stability AI

Stable Diffusion 发布了 SDXL 版本。 SDXL 也集成到了 Stability AI 收购的产品 clipdrop 上。

与其前身一样，SDXL具有使用文本提示进行图像生成、修复和扩展（创建位于图像边界之外的新部分）的能力。SDXL 是最新的人工智能图像生成模型，它能够根据文本生成逼真的人脸、根据图像生成文本解释，能够合成更高质量的图像，同时使用更短、更简单的提示即可生成图像。

与Stable DiffusionV1-v2相比，Stable Diffusion XL主要做了如下的优化：

对Stable Diffusion原先的U-Net，VAE，CLIP Text Encoder三大件都做了改进。
增加一个单独的基于Latent的Refiner模型，来提升图像的精细化程度。
设计了很多训练Tricks，包括图像尺寸条件化策略，图像裁剪参数条件化以及多尺度训练等，能够生成 1024x1024 分辨率的图片。

https://stablediffusionxl.com/

https://github.com/Stability-AI/generative-models

https://arxiv.org/abs/2307.01952

https://clipdrop.co/stable-diffusion

https://huggingface.co/stabilityai/stable-diffusion-xl-1.0-tensorrt

https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0

https://huggingface.co/stabilityai/stable-diffusion-xl-refiner-1.0

https://stability.ai/blog/stable-diffusion-public-release


## Baichuan 13B, 2023/07/11, 百川智能

7月11日，百川智能正式发布130亿级参数量的开源LLM Baichuan-13B-Base、Baichuan-13B-Chat及其INT4/INT8两个量化版本。
支持中英文双语。

Baichuan-13B 上下文窗口为 4096，开源可商用。 是开源的支持中文的模型标杆之一。

https://github.com/baichuan-inc/Baichuan-13B

https://huggingface.co/baichuan-inc/Baichuan-13B-Chat

## Claude 2, 2023/07/11, Anthropic

Anthropic是由前OpenAI高管共同创立的人工智能初创公司，7月推出了 Claude 2。

Claude 2 7月开始在美国和英国的网页和付费API（有限访问）上提供测试版。
API的定价仍然是每生成1000个单词约0.0465美元）。

https://techcrunch.com/2023/07/11/anthropic-releases-claude-2-the-second-generation-of-its-ai-chatbot/


## ChatGLM2-6B，2023/06/15, 清华

清华发布了推理能力更好，运行效率更高，编码和对齐能力更强，并且支持 8K, 32K 的上下文。
ChatGLM2-6B 除了可以用于学术研究，也允许用于商用。 ChatGLM 是开源的支持中文的模型标杆之一。

https://github.com/THUDM/ChatGLM2-6B

https://huggingface.co/THUDM/chatglm2-6b

https://huggingface.co/THUDM/chatglm2-6b-32k

https://github.com/THUDM/WebGLM


## Baichuan 7B，2023/06/15, 百川智能
baichuan-7B 是由搜狗创始人王小川创立的百川智能开发的一个开源、可商用的大规模预训练语言模型。
基于 Transformer 结构，在大约1.2万亿 tokens 上训练的70亿参数模型，支持中英双语，上下文窗口长度为4096。
在标准的中文和英文权威 benchmark（C-EVAL/MMLU）上均取得非常好的效果。

https://huggingface.co/baichuan-inc/Baichuan-7B


## ChatGPT 函数调用 - function call, 2023/06/13, OpenAI

OpenAI在6月13号升级了ChatGPT，推出了函数调用（Function calling），可以在调用 ChatGPT 的接口时，通过 functions 告诉 ChatGPT 我们有哪些函数可以调用， 然后 ChatGPT 根据请求条件自动判断建议调用的函数名，以及参数，使用 json 格式返回， 在返回结果的 function_call 里面返回函数和参数的信息。

这样开发者收到返回之后，可以调用本地服务器的函数。从而达到使得 ChatGPT 可以跟外部系统交互的目的， 因此也实现了 Langchain 期初设计的时候解决的大量问题。 包括联网查搜索引擎，查天气，查股票，购物，订餐，知识库问答等等功能都可以实现。

https://openai.com/blog/function-calling-and-other-api-updates


## PaLM 2, 2023/05/11, Google

5月11日 Google I/O 开发者大会发布大语言模型 PaLM2（Pathways Language Model 2），称在部分任务上超越 GPT-4。

2022年 4月，谷歌发布第一代 PaLM 大型语言模型（Pathways Language Model），在 7800亿 token 的高质量文本上训练 5400 亿参数的稠密自回归 Transformer，在数百个自然语言、代码和数学推理任务上实现了state-of-the-art 的结果。

2023年5月11日，谷歌最新发布了新的大型语言模型模型 PaLM2，推出了超过 25 种由 PaLM 2 提供支持的产品和功能。
谷歌办公全家桶 Workspace, 谷歌聊天机器人 Bard 深度集成 PaLM2。
谷歌云上线多个基础大模型，提供生成式 AI 服务。

PaLM2 相比于其他的大语言模型不同的一点是，大语言模型在手机端运行的可能。其中 PaLM2 中最小的 Gecko（壁虎）模型可以直接运行在手机上。

PaLM2 建立在谷歌的基础研究和最新的基础设施之上，提供了不同规模的四个版本以便胜任不同任务和部署：“壁虎” （Gecko），“水獭”（Otter）、“野牛”（Bison）和“独角兽”（Unicorn）。轻量级的 Gecko 模型可以在移动设备上运行，速度非常快，可以在设备上运行出色的交互式应用程序，支持离线使用。这使在手机也能运行交互式应用程序，每秒可以处理20个token。

实际上 GPT 的 Tranformer 架构，最早是 2017 年 Google 提出来的架构，Transformer 为近年来人工智能突破性发展奠定了基础。

https://ai.google/discover/palm2/

https://developers.generativeai.google/models/language

https://blog.google/technology/ai/google-palm-2-ai-large-language-model/

## Falcon, 2023/05, TII

开源、允许商用的 Falcon，40B 的效果超过了 LLaMa 65B的效果。

https://huggingface.co/tiiuae/falcon-40b-instruct

https://huggingface.co/tiiuae/falcon-7b-instruct

https://huggingface.co/blog/falcon

https://news.ycombinator.com/item?id=36145185

https://huggingface.co/TheBloke/falcon-40b-instruct-GPTQ


## Segment Anything Model(SAM), 2023/04/05, Facebook

Facebook 提出了 SAM 模型，并且开放了开源的实现。 
SAM 模型可以用来分割任意的图像，从图像中通过点选，或者框选的方式自动把物体标注出来。
也可以通过文本的 Prompt 来从图片中选择要分割的部分。

https://github.com/facebookresearch/segment-anything

https://segment-anything.com/

https://segment-anything.com/demo

https://arxiv.org/abs/2304.02643


## ChatGPT 插件, 2023/03/23， OpenAI

ChatGPT 的官网 Web 网站上开放了插件市场，可以选择使用不同的插件。 
因此可以查询实时的天气，可以从搜索引擎检索数据，甚至可以通过 ChatGPT 下单订餐，呼叫出租车，购物等等。
还有数学计算，语音对话，语言学习等等插件，补足了大语言模型数据不实时，数学逻辑不够好，不能联网等等方面的不足。

https://openai.com/blog/chatgpt-plugins

https://arxiv.org/abs/2302.07842

https://github.com/openai/chatgpt-retrieval-plugin


## Claude, 2023/03, Anthropic

Anthropic是由前OpenAI高管共同创立的人工智能初创公司，创立了 Claude 以与 ChatGPT 竞争。 
可以在 Quaro 的 App Poe 上面使用 Claude。 Claude 比 ChatGPT 能够支持更长的上下文文本，能处理更长的内容。

[Introducint to Claude](https://www.anthropic.com/index/introducing-claude)

https://www.anthropic.com/index/introducing-claude


## ChatGLM-6B，2023/03/14，清华

清华发布了开源的中英文双语对话模型，仅允许用于学术研究。
伴随着 ChatGLM-6B 的开放，商业化的 13B， 130B 也很快面向公众开放。

https://github.com/THUDM/ChatGLM-6B



## ChatGPT 4, 2023/03/13, OpenAI

GPT 4 的学术能力，逻辑能力，专业能力大幅提升。GPT-4 可以处理更长的文本，从 3.5 的 4k 上下文增加到 8k 的上下文长度。
GPT-4 回答的准确性也比 GPT-3.5 高很多，产生的内容也更加安全，有更好的创造性和协作性能。

在 GPT-3.5 版本模型下，ChatGPT 的 SAT 成绩只能排倒数 10% 的水平，然而 GPT-4 模型可以超越 90% 考生的水平。
期初 GPT-4 只开放到了部分 ChatGPT Plus 的订阅用户，后来逐渐开放到了所有用户。

https://openai.com/research/gpt-4

https://cdn.openai.com/papers/gpt-4-system-card.pdf

https://arxiv.org/abs/2303.08774 GPT-4 Technical Report


## LLaMa, 2023/02/24, Facebook

Facebook 开放了 7B, 13B, 65B 的 LLaMa 模型，分别有70亿，130亿，650亿参数。 
LLaMa 模型仅供学术研究使用，不可以用于商业用途。 且别申请审核通过后才可以下载。

很快有人把模型放到了BitTorrent上，使得互联网的用户无需申请就可以下载。这个人不仅把模型放到了BT上，同时还提交了github 的 Pull Request，请求合并包含有 BIT 链接的代码仓库内容变更。

虽然 LLaMa 仅供学术研究，但由于优异的能力，被很多公司、个人用于二次训练。 其中有大量效果更好的模型一一出现，包括 Falcon, WizardLM, Vicuna, Alpaca, Mosaic MPT 等等二次训练的模型。

很快 llama.cpp 出现，使得在 CPU， Mac 的机器上运行大模型成为可能。 可以在 64G 的 M2 MacBook Pro 上面运行 LLaMa 7B 和 13B。 Windows 上使用 CPU 也可以运行。

参考： 
https://github.com/facebookresearch/llama/

https://ai.facebook.com/blog/large-language-model-llama-meta-ai/

https://github.com/ggerganov/llama.cpp

## ChatGPT/GPT-3.5, 2022/11/30, OpenAI

GPT 3.5 的技术是 70 年来计算机发展史上的重大突破。这一技术的诞生对未来的影响可以比肩互联网对人类的影响。 伴随着 GPT-3.5 的诞生，以及已经成熟的图像生成，语音生成技术，AI 在创造大量机会的同时，也会导致大量传统工作机会的减少。

GPT 3.5 可以用来润色文案，编写文案，生成运营文章，做旅游规划，市场调研，产品分析，取名字，写诗，写周报，写代码，翻译代码，解释代码，查找代码中的 Bug，语言翻译，文章内容总结等等。

可以从这里访问：
[ChatGPT](https://chat.openai.com/)

https://help.openai.com/en/articles/6825453-chatgpt-release-notes

https://openai.com/blog/chatgpt

https://openai.com/blog/instruction-following/

https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html

## Langchain, 2022/11, Harrison Chase

Langchain 使得 LLM 模型可以与外部数据源、外部系统进行交互。
从而可以增加联网、数据分析、知识库问答，外部系统 API 调用等等功能。 使得 LLM 可以结合丰富的 Agent 来完成不同任务。

期初 Langchain 是配合 GPT-3 使用的框架，后来对于 ChatGPT, LLaMa 等 LLM 框架有了成熟的支持。 Langchain 是围绕 LLM 进行应用开发的利器。

Langchain 在 2023/04 获得2000万美金的融资。

https://github.com/langchain-ai/langchain

https://blog.langchain.dev/tag/release-notes/

https://python.langchain.com/docs/get_started/introduction.html


## Stable Diffusion, 2022/08/22,  Stability AI

Stable Diffusion 是一个开源的文字生成图片的模型，反过来也可以用来理解图片（从图片生成文字），以及图片修复，各种复杂的图片处理，包括背景替换，换脸等等。 2022 年 08/22 SD 发布了第一个版本， 11/24 发布 2.0。 

Stable Diffusion 一个只有20来人的团队，做出来的文字生图产品模型，让国内国外各大 Top 的互联网公司望尘莫及。

值得一提的是， Stable Diffusion 的大规模使用得益于 ControlNet 插件的诞生，以及大量社区模型的助力。


https://github.com/Stability-AI/stablediffusion

https://stability.ai/stablediffusion

https://stability.ai/blog/stable-diffusion-v2-release

https://huggingface.co/stabilityai/stable-diffusion-2-1

https://github.com/lllyasviel/ControlNet


## MidJourney, 2022/07/17, Open Beta, Midjourney, Inc.

MidJourney 在 2022 年 7 月发布了文字生图图片的商业产品。使用文字的提示词（Prompt），即可生成各种逼真的图片。
用户通过在 Discord 里面使用 Discord 的机器人命令来跟 MidJourney 交互，绘制艺术图。

只有 11 个人的 MidJourney，做到年营收超过1亿美金。

https://www.midjourney.com/

## GPT-3, 2020, OpenAI

GPT-3 是在 ChatGPT/GPT-3.5 之前最智能的大语言模型。
GPT-3展示了语言模型的性能与模型大小、数据集大小和计算量之间呈幂律关系。足够大的数据训练的语言模型可以解决它从未遇到过的自然语言处理任务。也就是说，GPT-3将模型作为一个通用解决方案来研究许多下游任务，而无需进行微调。GPT-3 被大量用于内容的生成。

人工智能的成本正在呈指数增长。使用Tesla V100云实例训练GPT-3耗费超过460万美元。

尽管增加模型容量明显提高了性能，但模型内部的运行机制仍不清楚。模型是否已经学会了推理，或者只是以更智能的方式记忆训练样本，这些仍然是未知的问题。
https://lambdalabs.com/blog/demystifying-gpt-3

GPT-3 的完整论文是开放的，因此有大量的第三方，以及开源的实现版本。包括 Bloom，以及阿里巴巴，百度等企业训练的 GPT-3 模型。