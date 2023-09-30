---
title: "大模型周报-2023年9月重要进展"
date: 2023-09-29T09:54:54+08:00
draft: false
# weight: 1
# aliases: ["/first"]
tags: ["LLaMa", "GPT", "ChatGPT"]
categories: ["LLM List", "Progress"]
author: "David"
# author: ["Me", "You"] # multiple authors

showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "大模型周报, 2023年9月重要进展"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "/images/chatgpt-can-now-see-hear-and-speak-alt.avif" # image path/url
    alt: "chatgpt can now see hear, and speak" # alt text
    caption: "chatgpt can now see hear and speak" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---

最近两周在大模型领域也是发生了不少重要的事情。 Falcon 发布了180B的模型，阿里巴巴发布 Qianwen 14B，效果跟 Baichuan 13B 相当。影响更大的是 OpenAI 发布了多模态的 GPT。 就是最早 GPT 4 发布的时候演示的上传一张 Web 页面设计的草稿图，GPT 立刻做出网站的多模态的例子，现在终于面向公众发布。

## ChatGPT 多模态, ChatGPT 可以看（识别图片），听，讲（语音对话）, 2023/09/25, OpenAI

ChatGPT 发布了多模态的功能， 就是最早 GPT 4 发布的时候演示的上传一张 Web 页面设计的草稿图，GPT 立刻做出网站的多模态的例子，现在终于面向公众发布。 

![ChatGPT询问天空中的云朵产生的原因](/images/chatgpt-can-now-see-hear-and-speak-alt.avif)

ChatGPT 多模态功能的发布，意味着用户在日常生活中的很多场景可以跟 GPT 进行互动，跟 GPT 请教如何动手解决日常生活的问题。 
比如说如何调解自行车座位高度，如何拆卸自行车，如何安装梳妆台甚至抽油烟机，如何拆卸电风扇，安装电脑主机等等。 这在一年前都是不可思议的事情。现在 GPT 可以手把手教我们如何动手解决问题。

这次官方给了 App 版本的几个例子。 一个例子是一张图片，对着天空拍一张图，问 ChatGPT “引起这种云的原因是”， 然后 GPT 理解图片后可以给出答复。 还有一个例子是跟 ChatGPT 求助如何调低山地车的座位高度。

* 1.视频中用户拍了一张图片，问 ChatGPT 如何调低车的座位高度。
* 2.ChatGPT 回答说先找到座位后面的快速调解高度的手柄（Lever）或者是松紧螺栓（Bolt）。 如果是手柄的话，打开它。 如果是松紧螺栓的话，就需要用到六角扳手（Allen Wrench）来打开松紧螺栓。然后调整座位高度，最后调整手柄或者松紧螺栓来固定座位，确保位置合适骑行。 
* 3.ChatGPT 接着说，如果你有工具，跟我展示一下工具，我将指导你如何使用。
* 4.用户接着拍了车座位后面的固定件，问ChatGPT 这是手柄还是松紧螺栓。 ChatGPT 说这是松紧螺栓。你需要六角扳手来调整车座的高低。
* 5.用户拍了一张手头工具箱的说明书，以及工具箱，然后问 ChatGPT 我有没有需要的六角扳手？
* 6.ChatGPT 指出来工具箱里面最左边的是六角扳手。 
* 7.然后用户顺利把车座高度调低。

[![ChatGPT协助调低自行车座位高度视频](/images/chatgpt-help-to-lower-bike-seat-2.jpg)](/video/ChatGPT-multimodel-2023-09.mp4)


https://openai.com/blog/chatgpt-can-now-see-hear-and-speak


## Qianwen 14B, 2023/09/25, Alibaba

通义千问-14B（Qwen-14B）是阿里云研发的通义千问大模型系列的140亿参数规模的模型。Qwen-14B是基于Transformer的大语言模型, 在超大规模的预训练数据上进行训练得到。预训练数据类型多样，覆盖广泛，包括大量网络文本、专业书籍、代码等。

Qwen-14B-Chat是在基座模型上经过精细SFT得到的对话模型。借助基座模型强大性能，Qwen-14B-Chat生成内容的准确度大幅提升，也更符合人类偏好，内容创作上的想象力和丰富度也有显著扩展。

开源的 Qwen 14B 模型可用于商用。 评估下来千问 14B 的效果跟Baichuan 13B 的效果不相上下。

https://help.aliyun.com/zh/dashscope/developer-reference/tongyi-qianwen-7b-14b-api-detailes

[Qwen论文地址](https://qianwen-res.oss-cn-beijing.aliyuncs.com/QWEN_TECHNICAL_REPORT.pdf)

[Qwen Github 仓库](https://github.com/QwenLM/Qwen)

[HuggingFace 模型库](https://huggingface.co/Qwen/Qwen-14B)

[HuggingFace Qianwen 14B Chat模型库](https://huggingface.co/Qwen/Qwen-14B-Chat)


## Falcon 180B, 2023/09/06, TII

由 Technology Innovation Institute (TII) 训练的开源大模型 Falcon 180B 发布。
作为当前最大的开源大模型，有180B 参数并且是在在 3.5 万亿 token 的 TII RefinedWeb 数据集上进行训练，
参数量是 LLaMa 2 的2倍还要多。 你可以在 Hugging Face Hub 中查阅其 基础模型、聊天模型，以及其 Demo 应用。

从架构维度来看，Falcon 180B 是 Falcon 40B 的升级版本，并在其基础上进行了创新，比如利用 Multi-Query Attention 等来提高模型的可扩展性。可以通过回顾 Falcon 40B 的博客 Falcon 40B 来了解其架构。Falcon 180B 是使用 Amazon SageMaker 在多达 4096 个 GPU 上同时对 3.5 万亿个 token 进行训练，总共花费了约 7,000,000 个 GPU 计算时，这意味着 Falcon 180B 的规模是 Llama 2 的 2.5 倍，而训练所需的计算量是 Llama 2 的 4 倍。

其训练数据主要来自 RefinedWeb 数据集 (大约占 85%)，此外，它还在对话、技术论文和一小部分代码 (约占 3%) 等经过整理的混合数据的基础上进行了训练。这个预训练数据集足够大，即使是 3.5 万亿个标记也只占不到一个时期 (epoch)。

已发布的 Falcon 180B 聊天模型在对话和指令数据集上进行了微调，混合了 Open-Platypus、UltraChat 和 Airoboros 数据集。

虽然 Falcon 180B 的参数量巨大，运行模型所需要的算力要求也高。 我自己评估下来，效果仍然不如 LLaMa 2的。

‼️ 商业用途: Falcon 180b 可用于商业用途，但条件非常严格，不包括任何“托管用途”。如果您有兴趣将其用于商业用途，我们建议您查看 [许可证](https://hf.co/spaces/tiiuae/falcon-180b-license/blob/main/LICENSE.txt) 并咨询您的法律团队。

[Falcon 180B Introduction](https://huggingface.co/blog/falcon-180b)

[Falcon 180B 中文介绍](https://huggingface.co/blog/zh/falcon-180b)

[180B 基础模型](https://huggingface.co/tiiuae/falcon-180B/)

[180B Chat模型](https://huggingface.co/tiiuae/falcon-180B-chat)

[Falcon 180B Demo](https://huggingface.co/spaces/tiiuae/falcon-180b-demo)


## 彩蛋分享-代码生成：如何运行 WizardCoder 15B, 34B，Phind CodeLlama 34B 代码生成模型

代码生成模型里面先后有 CodeGeex, StarCoder, WizardCoder, CodeLLaMa, Phind CodeLlama 等等。 其中 WizardCoder 是效果非常好的模型，而 Phind CodeLlama 的评测效果看起来比 WizardCoder 的更好。
WizardCoder 是基于 StarCoder 和 LLaMa 的编码模型。

ggml/gguf 量化版本可以在 mac studio ultra 的 cpu 上运行, gguf 是新的格式，运行方式类似。没有量化的版本要在 A100 以上配置的GPU上面运行。也可以使用 WizardCoder Python 34B， 生成 Python 代码的效果比 15B 的更好。

https://huggingface.co/TheBloke/WizardCoder-15B-1.0-GGML

https://huggingface.co/WizardLM/WizardCoder-Python-34B-V1.0

https://huggingface.co/TheBloke/WizardCoder-Python-34B-V1.0-GGUF

Phind CodeLlama 34B 是基于 CodeLlama 34B 的代码生成模型，训练的时候使用了 8w 私有的高质量的编程问题和答案进行微调。 目前是开源的代码生成模型里面效果最好的。

https://huggingface.co/TheBloke/Phind-CodeLlama-34B-v2-GGUF

https://huggingface.co/Phind/Phind-CodeLlama-34B-v2

https://www.phind.com/blog/code-llama-beats-gpt4


**下载 GGML 模型，编译 Koboldcpp 来运行模型，提供 HTTP 服务可以在浏览器上访问**

```
git clone https://huggingface.co/TheBloke/WizardCoder-15B-1.0-GGML
git clone https://github.com/LostRuins/koboldcpp
cd koboldcpp
make -j8

```

**WizardCoder-15B-1.0-GGML 代码模型，运行命令：**

```
python3.10 /Users/david/workspace/WizardCoder-15B-1.0-GGML/koboldcpp/koboldcpp.py  ~/workspace/WizardCoder-15B-1.0-GGML/WizardCoder-15B-1.0.ggmlv3.q8_0.bin 8000
```

**使用的 koboldcpp 工具的说明**
* Amounts to Gen 设置成512， Format 设置成 Instruction Mode，勾选 Markdown，以便能看到代码的格式化输出。
* koboldcpp 支持流式输出， 只需要在 URL 后面增加  streaming=1 的参数即可，例如： http://localhost:8000/?streaming=1#

WizardCoder 代码生成的效果，远远好于 StarCoder 和 CodeGeex。 我跑的还是量化的版本。提了一个问题，让计算圆柱体体积， 27s 输出完整的代码。 "Implement a Python function to calculate volume for Cylinders"

生成代码的用的这个： https://huggingface.co/TheBloke/WizardCoder-15B-1.0-GGML

WizardCoder 支持中文的输入。