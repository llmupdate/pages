---
title: "解锁 Manus -  探索 AI 智能体 Manus 背后的黑魔法"
date: 2025-03-15T08:45:01+08:00
tags: ["Agent", "Browser Use", "Computer Use", "Manus", "AGI"]
categories: ["LLM List", "Progress", "AI Agent"]
draft: false
# weight: 1
# aliases: ["/first"]
author: "David"
# author: ["Me", "You"] # multiple authors

showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Desc Text."
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
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/llmupdate/pages/manus-technique-report-20250315.md"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

# 解锁 Manus - 探索 AI 智能体 Manus 背后的魔法

在 AI 智能体迅速崛起的 2025 年，**Manus** 以其惊艳的自主能力和技术架构，成为普通人手中的"超级助手"。它不仅能"思考"，还能"行动"，从个性化旅行规划到克隆 Hacker News 网站，Manus 展现了 AI Agent 的魔法。 毫不夸张地说，Manus 开启了 2025 年的 Agent 元年，后面会有更多好用的 Agent 出来。

Manus 刚刚出来，不少朋友家人问我，Manus 的能力真的很强吗？Manus 纯粹是在做营销吧？
我回答他们说，Manus 的能力真的很强，是到目前为止最好用的智能体。 另外一个方面，谈到营销，我不太关注 Manus 是不是在做营销。 更加关注 Manus 实际的技术能力，产品能力，能不能解决问题，能不能替我干活。

一个团队只有具备一流的工程技术能力，一流的产品能力，才能做出 Manus 这样的产品。 虽然几天之内 Manus 被复刻出了大量的 Open Manus， 我估计6个月之内都不一定有体验跟 Manus 一样好的开源替代。

另外， twitter 上面有人爆出来通过提示词 Prompt 对话的方式，越狱了 Manus， 把 Manus 运行过程中的整个系统都下载了下来， 实际上每个用户的任务都是在一个容器中执行，用户可以拿到容器的完全权限，甚至可以在上面安装软件，执行任意命令，这个不是 Manus 被"越狱"，而是产品本身就提供了很好的开放性，让用户能够接管 AI 的整个工作空间。

从技术角度来讲，实际上 Manus 的工作空间在 Visual Studio Code Server 中，这个 Code Server 运行在 Ubuntu 的容器之上，Code Server 实际就是 VS Code 的一个开发环境，用户可以通过浏览器打开这个开发环境，用户在 Code Server 中可以打开 Terminal 来执行任意的命令。

 文章末尾有介绍如何使用 Manus 能够达到最好效果，如何避免使用 Manus 的各种坑。
 * 如何恢复因为高负载停止的 Manus 任务
 * 如何从 Manus 的 workspace 进入到 Terminal
 * 如何从 Manus 的 workspace 中安装软件包，执行命令
 * 如何下载已经实现完成项目，但是测试或者发布失败的 Manus 任务的工作空间到本地
 * 如何让 Manus 在遇到上下文过程的问题之后，继续工作（竟然可以这样！！！）

-- 

## 对于 Manus 的总体评价

* 从能力上讲，比 OpenAI Operator, Deep Research, Claude Computer Use 都更进了一步。 比如 Cline/Cursor/Windsurf 之类集成了 MCP 的产品而言，能力还不够强。 到现在为止，Manus 是给普通人用的最好用的智能体。 Claude Desktop App + MCP， Cline/Cursor/Windsurf 也都很好用，但是这几个工具都只适合给到开发者用（能够完成很多事情）， 而Manus 是给到普通人用的。
* Manus 目前不算通用智能体，目前仍然是围绕内容的内容类智能体。包含了内容收集，内容处理，内容创作能力的智能体。目前缺少的是动作执行，跟外部系统的交互，比如帮我订餐，淘宝购物下单，订机票，订酒店，这些是目前 Manus 还没有，或者说没有开放的能力。内部可能已经有了，但是没有开放出来。执行动作的能力有很多需要考虑的问题（带来的危险也会高很多很多）。
* Manus 让大家理解到了什么智能体， 为什么我们不再需要用 dify, coze 这样的产品去创建工作流。 因为有了智能体，智能体会自己规划执行。

---

## 使用案例：看看 Manus 的"作品"

在 Google 中搜索 site:manus.space 能找到大量由 manus 创建的网站。访问 [Manus Space 案例](https://www.google.com/search?q=site%3Amanus.space)，体验这些 Manus 创建的网站产品：
- **IBIT ETF Overview**: [kwjamaxw.manus.space](https://kwjamaxw.manus.space/)
- **Vibe Coding Course**: [qcogqnqq.manus.space](https://qcogqnqq.manus.space/)
- **2024 中文播客报告**: [xtttauxb.manus.space](https://xtttauxb.manus.space/)
- **AI Generated Games**: [gizzyazl.manus.space](https://gizzyazl.manus.space/)
- **Hacker News 克隆站**: [rhgmvpjb.manus.space](https://rhgmvpjb.manus.space/)
- **Apple 官网克隆站**： [bxzlhlmm.manus.space](https://bxzlhlmm.manus.space/)
- **Transformer 架构学习站**： [inevjngi.manus.space](https://inevjngi.manus.space/)

更多回放案例：
- **特斯拉股票分析回放**: [查看过程](https://manus.im/share/xFgpHb15vKqfRPWIs3JJPJ?replay=1)
- **复制 Hacker News**：[回放](https://manus.im/share/bSzULj3ETQFtcHUcEWPL1m?replay=1)
- **2.5D 城市图游戏**：[回放](https://manus.im/share/4gQbKs2RgQQt6uMUSIA4NQ?replay=1)
- **实时字幕音乐网站**：[回放](https://manus.im/share/lfhStFAPQJLeq9zjnJ9B6T?replay=1)

---

## Manus 能做什么？从内容采集到创作的全能选手

Manus 是一款专注于内容采集、分析和创作的智能体，应用场景多样化：

- **个性化旅行规划**  
  从网络收集旅游信息，为你定制旅行指南。比如，规划 4 月的日本之行，提供个性化建议和详细行程。

- **股票分析**  
  深入分析股票数据，生成视觉化的仪表板。例如，[特斯拉股票分析](https://manus.im/share/xFgpHb15vKqfRPWIs3JJPJ?replay=1) 展示了全面洞察。

- **教育内容创建**  
  为教师打造交互式教学资源，如生成解释动量定理的视频，发布为静态网站（[动量守恒定律动画](https://iciwktuq.manus.space/)）。

- **商业决策支持**  
  提供保险政策比较表，或分析亚马逊过去四季度的市场情绪变化，助力决策。

- **网站开发与部署**  
  创建知识类网站、学习网站甚至 Web 游戏，用纯 JavaScript/HTML 实现，自动部署到 manus.space 子域名。比如 [AI 生成游戏](https://gizzyazl.manus.space/)。

- **复制现有网站**  
  输入 Apple 官网或 Hacker News，Manus 能生成几乎一模一样的静态网站并部署，如 [Hacker News 克隆站](https://rhgmvpjb.manus.space/)。

---

## Manus 如何超越传统 AI 产品？

与传统 AI 聊天机器人仅停留在"对话"不同，Manus 的核心在于**任务规划与自主执行**。它能将复杂任务分解为步骤，调用 29 种工具，从"思考"到"行动"，交付完整结果。其优势包括：

- **自主执行**：不仅建议，还直接完成任务。
- **任务分解**：化繁为简，逐步推进。
- **工具使用**：整合多种工具，灵活应对。
- **记忆能力**：记住你的偏好，提供个性化体验。
- **结果导向**：验证输出，确保质量。对于创建可以交互的网站任务，Manus 会自己执行测试和部署。

相比 OpenAI Operator、Deep Research 等，Manus 更进一步，尤其适合普通用户，而非仅限开发者（如 Claude Desktop App、Cline、Cursor）。

---

## 技术架构揭秘：Manus 的"魔法"来源

Manus 的"魔法"能力源于其基于领先推理能力的基础模型，加上自研的处理特定微调模型，同时整合了搜索，浏览器自动执行，代码自动执行，自动测试，自动发布，把整个流程串了起来，使得我们能够体验到结果导向的智能体的能力：

1. **容器与虚拟机**  
   每个任务在 Ubuntu 容器中运行（4 核 4G 内存，13G 磁盘），结合 KVM 虚拟机隔离。容器内用 Chrome 浏览网页，大量使用 Python 和 Node.js/TypeScript。

2. **多智能体系统**  
   包括 Task Planning、Web Search、Browser Use、Code Generation、Code Execution、Application Test 和 Deployment Agent，聚合了多种能力。

3. **语言模型**  
   基于 Claude 3.5 Sonnet 和自研 Qwen 微调模型（参考 o1 的 COT 训练），成本低且高效。Claude Sonnet 3.7 也在测试中。

4. **任务执行与代码执行**  
   Manus 种没有使用 MCP 协议，而是使用类似于 OpenHands 的 CodeAct 方法，自研的 Qwen 微调模型来进行任务执行，代码执行，这种方法比传统的方法具有更高的准确性。 参考论文： [https://openreview.net/pdf?id=jJ9BoXAfFa](https://openreview.net/pdf?id=jJ9BoXAfFa)

5. **工作空间透明性**  
   通过 Visual Studio Code Server（运行于 Docker），用户可在浏览器查看 workspace，运行命令、安装软件，体验全开放环境。

6. **自动部署**  
   静态网站自动发布到 manus.space 子域名（如 [Transformer 学习站](https://inevjngi.manus.space/)），依托 AWS/Google Cloud，Manus 的 API 路由用到 APISIX，数据分析用到 Plausible。

---

## Manus 的定位与限制

### 智能体分类
- **信息收集与处理**：如 Deep Research、Manus。
- **决策与行动**：帮助规划旅游，订机票，订酒店，订景点门票（目前还没有）。
- **能力增强**：增强机器/人类的能力，比如图像识别，视频理解。 即便是模糊不清的图片，也能够识别出来（用来增强某一特定领域的能力，比如 OCR，超分，理解CT图片）。
- **通用智能体**：平台级全能型（如 Claude Desktop App）。

### 通用智能体垂直专用智能体
- **垂直专用智能体**：例如内容创作，信息检索，收集的智能体。比如 Deep Research, Manus，OpenAI Operator， Browser Use 都是属于专用智能体。
- **通用的智能体**: 通用智能体啥事都能干的，平台级别的智能体，比如 Claude Desktop App。 （Cline, Cursor, Windsurf 虽然是写代码用的智能体，我认为也算是通用智能体）

- **Manus 的当前限制**：
  1. 非通用智能体，暂无外部交互（例如不能执行订餐、淘宝下单购物、订酒店、订机票、发送微信消息等）。
  2. 未接入 MCP 协议，功能扩展受限。
  3. 仅支持静态网站，动态功能（如用户登录，用户发布内容）暂时没有。
  4. 上下文长度有限，复杂任务易超限。
  5. 稳定性问题，任务可能挂起。

虽然 Manus 有这些不足和限制，但 Manus 让人们开始了解和认识智能体：它自己规划任务，选择工具，执行任务，过程中能够对于任务的结果对环境有感知，能够自己修复任务的执行。 通过 Manus 我们直接给出需求， Manus 自动出流程步骤，自动跑出来结果，我们不再需要通过 Dify、Coze 等工作流工具搭建复杂的工作流。

---

## 使用 Manus 过程中的常见问题

### 1.如何避免 Manus 中的知识带来的问题 Knowledge Management

每次创建任务的时候， Manus 会给出建议的知识， 可以确认接收这些知识。 

![Pasted image 20250315172626.png](/images/manus/Pasted%20image%2020250315172626.png)

![Pasted image 20250315172651.png](/images/manus/Pasted%20image%2020250315172651.png)

要特别注意的是这些知识确认之后，在后面的任务中默认是开启的，会影响后面的任务执行。 因此新启动任务时，记得要点击页面左下角的知识图标（ 📖），然后在知识管理里面禁用，或者删除不用的知识。

![Pasted image 20250315172909.png](/images/manus/Pasted%20image%2020250315172909.png)
### 2. Manus 任务因为负载过高停止后，如何继续？
例如下面的任务，Manus 因为系统负载过高停止。 这个时候可以给 Manus 指令，请继续前面的任务。 Manus 如果有资源，会继续运行前面的任务。
![Pasted image 20250315173706.png](/images/manus/Pasted%20image%2020250315173706.png)

### 3.Manus 任务的上下文超过最大长度后，如何完成未完成的任务？

因为上下文长度过长，Manus 完成了部分任务之后会停止执行。这个时候如果直接重新启动一个任务，用同样的提示词，下次还是会上下文过长。 那么怎么处理呢？ 分两种情况
* 任务已经完成，只是没有发布内容，这种情况可以人工进入到 VS Code 里面下载项目
* 任务部分完成，部分没有完成，这种情况可以进入到 VS Code 下载项目目录，打包成 zip 包。 然后新创建一个会话，粘贴打包的zip文件来带上上次执行了一部分的项目，提交任务后，manus 会继续处理没有完成的任务。比如这个任务是带着上次完成一半的项目的 zip 压缩包附件，重新提交的任务。

![Pasted image 20250315172221.png](/images/manus/Pasted%20image%2020250315172221.png)

### 4.Manus 的任务，如何进入任务的 VS Code 的工作空间

在任务执行过程中， 点击其中的一条命令，或者一个文件， 页面右侧会出来 Manus's Computer， 在 Manus Computer 的右侧下拉图标点击之后，会出来 VS Code， 点击这个 VS Code 进入到 VS Code 界面。
![Pasted image 20250315173852.png](/images/manus/Pasted%20image%2020250315173852.png)

![Pasted image 20250315174236.png](/images/manus/Pasted%20image%2020250315174236.png)
### 5.Manus 任务停止后如何下载项目内容

进入到 VS Code， 右键点击项目目录，点击 "Download" 来下载整个目录到本地。

![Pasted image 20250315171409.png](/images/manus/Pasted%20image%2020250315171409.png)


### 6.如何进入到容器的 Terminal

在 VS Code 里面，点击左侧下拉菜单，点击 Terminal 即可进入终端，终端里面可以执行命令，安装软件。

![Pasted image 20250315174356.png](/images/manus/Pasted%20image%2020250315174356.png)

### 7.Terminal 里面如何安装软件

前面的步骤进入 terminal 后，在 Terminal 里面， 可以使用 sudo 命令提升权限来安装软件， 例如升级系统，安装网络流量监测包：

![Pasted image 20250315174519.png](/images/manus/Pasted%20image%2020250315174519.png)

例如这个容器里面安装网络流量检测包之后，可以看到实时的网络流量。
你甚至可以安装 tmux，在里面跑多个终端运行不同的命令来玩。
![Pasted image 20250315174614.png](/images/manus/Pasted%20image%2020250315174614.png)


### 8.让 Manus 收集信息如何能够收集到高质量的学术/技术资料

记得务必让 Manus 使用英文来搜索。 Manus 使用英文能够查找到最全的资料。 默认使用中文对话，我跑过的例子通常只查找中文的资料，找到的内容会非常有限。 例如这个对话，让搜索英文，出来的内容使用中文。

![Pasted image 20250315175055.png](/images/manus/Pasted%20image%2020250315175055.png)

## 技术讨论与资源

- 创始人 Yichao 'Peak' Ji 分享：[OpenAI o1 复现思路](https://medium.com/@peakji/a-small-step-towards-reproducing-openai-o1-b9a756a00855)
- 自研模型：[Steiner-32b-preview](https://huggingface.co/peakji/steiner-32b-preview)
- 代码执行论文：[OpenHands 参考](https://openreview.net/forum?id=jJ9BoXAfFa)


---

## Agent 讨论群

扫码加入如下群进一步讨论智能体 Agent 技术, 包含  Manus, Claude MCP, OpenAI Operator, Browser/Computer Use, Deep Research, GLM-PC, CrewAI, SmolAgent, AutoGen, AG2, OpenHands 等：

![Pasted image 20250315193020.png](/images/manus/AI_Agent_Tech_no_title.png)

扫码加入如下群，讨论 智能体产品的使用（非技术）

![Pasted image 20250315193037.png](/images/manus/AI_Agent_User_no_title.png)
---

*发布于 2025 年 3 月 15 日*