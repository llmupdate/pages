---
title: "OpenAI 1106 开发者日演讲全文"
date: 2023-11-12T20:00:00+08:00
tags: ["GTP-4v", "GPTs", "AssistantAPI", "ChatGPT", "OpenAI"]
categories: ["LLM List", "Progress"]
draft: false
---

2023 年 11月6日，北京时间11月7日，注定会成为人工智能历史上被铭记的一天。虽然这是一个开发者日，实际上是一个产品发布会。这一天是 ChatGPT 的 iPhone 时刻。后续的文章会详细介绍为什么这次是 ChatGPT 的 iPhone 时刻。以下是 OpenAI Dev Day 45 分钟完整演讲的中文内容，后附完整的英文内容。声明：内容由 ChatGPT 从 Youtube 的视频转义得到，并由 ChatGPT 增加标点符号，由 ChatGPT 翻译成中文。

Youtube 视频： 
https://www.youtube.com/watch?v=U9mJuUkhUzk&t=4s

如果有不正确或者遗漏的内容，您可以 Github 将正确的内容提交 PR 到 https://github.com/llmupdate。

此文档更新的内容参考 https://llmupdate.com

## OpenAI Dev Day 1106 演讲


早安，感谢各位今天的莅临。请欢迎Sam登台【音乐响起】。早上好！欢迎来到我们OpenAI首次的开发者日。我们非常高兴您能到场，这里的活力真是令人振奋。欢迎大家来到旧金山。

旧金山自我们成立之日起就是我们的家。这座城市对我们和整个科技产业至关重要。我们期待在这里继续成长。今天我们有一些激动人心的新闻要宣布。但在此之前，我想先回顾一下我们过去一年的成就。去年11月30日，我们推出了ChatGPT的初步研究版本，反响非常好。

今年三月，我们接着推出了GPT-4，它仍然是世界上最强大的模型。近几个月，我们还推出了语音和视觉能力，让ChatGPT能够听、看和说。最近，我们推出了Dalle 3，这是世界上最先进的图像模型。对于企业客户，我们推出了ChatGPT Enterprise，提供企业级的安全和隐私保护、更快的GPT-4访问速度、更长的上下文窗口等等。目前，大约有200万开发者在使用我们的API进行各种惊人的创新。

超过92%的财富500强企业正在使用我们的产品，而现在我们每周有大约1亿活跃用户在使用ChatGPT。这完全是通过口口相传实现的，人们发现它非常有用并告诉他们的朋友。OpenAI现在是世界上最先进、应用最广泛的AI平台。但数字永远不能完全说明问题。真正重要的是人们如何使用这些产品，如何使用AI。现在，请允许我展示一个简短的视频。

[视频展示了人们如何使用我们的产品，包括写信给家人、寻求生活指导、进行创意工作等。]

这些故事让我们更加明确我们所做的一切。好的，现在让我们来谈谈新事物。我们有很多东西要谈。首先是一些我们做出的改进，然后我们将讨论未来的方向。过去一年，我们与世界各地的开发者进行了大量沟通，您的反馈对我们今天要展示的内容影响极大。

今天我们将发布一款新模型——GPT-4 Turbo。它将解决您所有的需求，所以让我们看看有哪些新功能。首先，上下文长度。许多人的任务需要更长的上下文长度。GPT-4支持最多8K甚至32K的上下文长度，但我们知道这对许多人来说还不够。GPT-4 Turbo支持高达128,000个词的上下文，相当于标准书籍的300页，是我们8K上下文的16倍。此外，您会发现，模型在处理长上下文时的准确度大大提高。

![OpenAI Dev Day 1106 01](/images/openai_dev_day_1.jpg)

其次，更多控制权。我们清楚地听到了开发者对模型响应和输出控制需求的呼声。因此，我们以多种方式解决了这个问题。我们引入了一个名为Json模式的新功能，确保模型将以有效的Json格式响应。这是开发者的一个巨大需求，它将使调用API变得更加容易。模型在函数调用方面也有所改进，现在可以同时调用多个函数，并且更好地遵循指令。此外，我们还推出了一个名为可重现输出的新功能，您可以传递一个种子参数，使模型返回一致的输出。这当然为您提供了对模型行为的更高程度的控制。这个功能今天开始在beta版本中推出，未来几周我们将推出一个功能，允许您在API中查看日志概率。

第三，更好的世界知识。您希望这些模型能够访问更好的世界知识，我们也希望如此。所以我们在平台上推出了检索功能。您可以将外部文档或数据库中的知识带入您正在构建的任何东西。我们也更新了知识截止日期。我们也像所有人一样，对GPT-4对世界的了解停留在2021年感到烦恼。我们会尽力不让它再过时。GPT-4 Turbo对世界的了解一直持续到2023年4月，我们会继续改进。

第四，新的模态。不出所料，Dalle 3、GPT-4 Turbo与视觉和全新的文字转语音模型都将进入API。今天，我们有一些客户刚开始使用Dalle 3以编程方式生成图像和设计。例如，今天K正在推出一项活动，让他的客户使用Dalle 3生成排灯节贺卡。当然，我们的安全系统帮助开发者防止应用被滥用。这些工具在API中可用。GPT-4 Turbo现在可以通过API接受图像输入，可以生成标题、分类和分析。例如，Bey Eyes使用这项技术帮助视障或视力低下的人们处理日常任务，如识别他们面前的产品。而我们的新文字转语音模型，您将能够从文本中生成非常自然的音频，有六种预设声音可供选择。我会播放一个例子。"你知道吗，著名的发明家亚历山大·格雷厄姆·贝尔被声音的世界迷住了。他的智慧头脑导致了留声机的创造，它将声音刻录在蜡上，使得声音穿越时空轻声细语。"这比我们听到的其他任何东西都自然。声音可以使应用更自然地与人交互，更具可访问性，还能解锁诸如语言学习和语音助手等许多用例。

说到新模态，我们还将发布我们的开源语音识别模型Whisper V3的下一个版本，它将很快进入API。它在许多语言上的性能都有所提高，我们认为您会非常喜欢。

第五，定制化。微调在GPT-3.5推出几个月后一直运行得非常好。从今天开始，我们将扩展到该模型的16k版本。同时，从今天开始，我们邀请活跃的微调用户申请GPT-4微调实验访问计划。微调API非常适合调整我们的模型，以在各种应用中获得更好的性能，只需相对较少的数据。但您可能希望模型学习一个全新的知识领域，或者使用大量专有数据。因此，今天我们推出了一个名为“自定义模型”的新计划。在这个计划中，我们的研究人员将与公司密切合作，帮助他们使用我们的工具。

使用我们的工具，包括修改模型训练过程的每一步，进行额外的领域特定预训练，为特定领域定制的自定义强化学习后训练过程，以及其他我们无法做到的事情。起初这可能不便宜，但如果您对将事情推到目前能够达到的极限感到兴奋，请与我们联系，我们认为我们可以做出一些非常了不起的事情。

第六，更高的速率限制：我们为所有gpt4客户将每分钟的token数量翻倍，让他们能够更轻松地完成更多任务。客户现在可以在API帐户设置中直接请求进一步的速率限制和配额更改。

![OpenAI Dev Day 1106 02](/images/openai_dev_day_2.jpg)

版权保护：为了支持我们的客户，我们引入了版权保护措施，意味着OpenAI将在与版权侵权相关的法律诉讼中替客户辩护并承担费用。这适用于ChatGPT Enterprise和API。值得注意的是，OpenAI不会使用API或ChatGPT Enterprise的数据进行训练。

GP4 Turbo的定价：GP4 Turbo相比GP4而言，定价有大幅降低。对于提示（prompt）tokens来说便宜了3倍，对于补全（completion）tokens来说便宜了2倍。这种成本的降低旨在满足那些希望建设更多项目但认为GP4价格昂贵的开发者的反馈。OpenAI还将致力于未来提高速度。

GPT 3.5 Turbo 16k的定价：GPT 3.5 Turbo 16k的成本也有所降低。输入tokens现在便宜了3倍，输出tokens便宜了2倍。因此，运行经过精调的GPT 3.5 Turbo 16k版本比之前的GPT 3.5 4K模型更具性价比。

![OpenAI Dev Day 1106 03](/images/openai_dev_day_3.png)

建立强大的合作关系：OpenAI重视与Microsoft的合作伙伴关系，并感谢他们在构建最佳训练和推理系统方面的支持。Microsoft致力于在Azure中提供最佳基础架构，支持OpenAI API。他们还专注于通过提供GitHub Co-Pilot等工具来帮助开发者。

未来目标：OpenAI和Microsoft致力于共同推动AI的边界。他们旨在为开发者提供最佳系统和计算能力，推动人工智能的进步。两家公司都相信人工智能在赋予个人和全球组织方面的潜力，并将安全放在首位。

ChatGPT的更新：ChatGPT现在使用GPT 4 Turbo以及最新的改进。它可以浏览网络、运行代码、分析数据、生成图像等。模型选择器被消除，ChatGPT将自动知道使用哪些工具。OpenAI旨在提供更智能、更可定制的人工智能，以代表用户执行各种任务。逐渐的迭代部署对于解决安全问题非常重要，需要技术上的工作和社会的考虑。

因此，今天我们将迈出通往这个未来的第一小步。我们非常激动地，呃，我们非常激动地介绍gpts。gpts是chatGPT的定制版本，用于特定目的。您可以构建一个GPT，即chat GPT的定制版本，用于几乎任何需要，提供指令、扩展知识和行动。然后，您可以发布供他人使用。由于它们结合了指令、扩展知识和行动，它们可以更有助于您。它们在许多情境下更有效，并且可以给您更多的控制权。它们将使您更容易完成各种任务，或者只是更有乐趣，并且您将能够在chat GPT中直接使用它们。

![OpenAI Dev Day 1106 04](/images/openai_dev_day_4.png)

实际上，通过与它交谈，您可以使用语言对GPT进行编程。轻松定制其行为以使其适应您的需求。这使得构建它们变得非常易于接触，给每个人都赋予了决定权。所以我们将向您展示gpts是什么，如何使用它们，如何构建它们，然后我们将讨论它们将如何分发和发现。

在此之后，对于开发者来说，我们将向您展示如何将这些类似代理的体验整合到您自己的应用程序中。所以首先，让我们看几个例子。我们的合作伙伴code.org正在努力推广学校的计算机科学教育。他们拥有一个被全球数千万学生使用的课程。Code.org打造了Lesson Planner GPT，帮助教师为中学生提供更有吸引力的学习体验。如果教师要求它以创意方式解释for循环，它会这样做。在这种情况下，它将从一个视频游戏角色反复拾取硬币的角度进行解释。对八年级学生来说非常容易理解。正如您所看到的，这个GPT将code.org的广泛课程和专业知识结合起来，让教师能够快速轻松地适应自己的需求。

接下来，Canva构建了一个GPT，让您通过自然语言描述您想要的设计。如果您说：“制作一个海报，用于今天下午或今晚的Dev Day招待会”，并给出一些详细信息，它将通过访问Canva的API生成一些起点选项。这个概念可能对一些人很熟悉。我们将我们的插件发展为GPT的自定义行动。

您可以继续与此进行聊天，以查看不同的迭代版本，当您看到喜欢的版本时，可以点击转到Canva进行完整的设计体验。现在我们想给您展示一个实时的GPT。Zapier构建了一个GPT，可以跨6000个应用程序执行操作，解锁各种集成可能性。我想介绍一下我们的解决方案架构师之一Jessica，她将进行演示。欢迎，Jessica。谢谢，S.H。大家好，非常感谢大家。

[掌声]大家，非常感谢你们的到来。我叫Jessica Shay。我与合作伙伴和客户合作，使他们的产品活跃起来，今天，我迫不及待地想与大家分享/展示我们一直在努力的成果。那么，让我们开始吧。那么，要开始，您的GPT将存储在左上角这个位置。我将开始点击Zapier的“您的AI动作”，在右侧，您可以看到这是我今天的日程表。今天的日程相当紧凑。我已经之前使用过这个功能，所以它已经与我的日程表连接了。要开始，我可以问：“我今天的日程是什么？”我们在构建GPT时考虑到了安全性，因此在执行任何操作或共享数据之前，它会征求您的许可。所以在这里，我要说“允许”。GPT被设计为接收您的指令，根据其功能选择能力，执行相应的操作。

所以您可以看到，它已经连接到了我的日程表。它获取我的信息，然后我还提示它在我的日程表上标识冲突。所以您可以看到，它实际上能够识别到这个冲突。看起来我有一项活动。那么如果我想让Sam知道我必须提前离开怎么办呢？在这里，我说：“告诉Sam我要去追逐GPT。”所以说完之后，我要切换到与Sam的对话中，然后我会说：“是的，请执行。”Sam，你收到了吗？我收到了，太棒了。这只是可能性的一瞥，我迫不及待地想看到大家会构建什么。谢谢大家，回到你，Sam。谢谢，Jessica。

这就是三个很好的例子。除此之外，还有许多更多类型的GPT正在被创建，而且很快还会有更多。我们知道很多想要构建GPT的人不知道如何编写代码。我们通过对话的方式让您可以编程GPT。我们相信，自然语言将成为未来人们使用计算机的重要组成部分，而我们认为这是一个有趣的早期示例。所以我想向您展示如何构建一个。 好的，所以我想创建一个GPT，帮助创始人和开发者在启动新项目时提供建议。我要在这里创建一个GPT，然后进入GPT构建器。我在YC与创始人一起工作了多年，而每当我遇到开发者时，他们经常问的问题都是如何考虑商业创意，你能给我一些建议吗？

我要看看是否可以构建一个GPT来帮助解决这个问题。所以首先，GPT构建器问我希望做什么，我会说，我想帮助初创公司创始人思考他们的商业创意并获得建议。在创始人获得建议之后，追问他们为什么增长不够快。好的，所以首先我告诉GPT我想要做的一些事情，它会开始考虑。然后它会为GPT编写一些详细的指令。它还会问我一个名称的建议。我对“启动导师”感觉怎么样？

这个名称还不错。如果我不喜欢这个名称，当然可以选择其他名称，但它会尝试与我进行对话并从那里开始。在预览模式中，您可以在右侧看到它已经开始填充GPT。它列出了它的功能以及我可以提问的其他问题。它刚刚生成了一个候选版本。当然，我可以重新生成它或更改它，但我很喜欢这个版本。所以我会说很好。您现在可以看到GPT正在不断完善。

现在我想让它做什么，以及如何与用户进行交互，我可以在这里谈论样式。但是我要说的是，我将上传我所讲授的一些关于创业公司的讲座的文字记录。请根据这些记录给出建议。好的，现在它将找出如何做到这一点。我想给您展示配置选项卡，以便您可以看到我们在构建器中所构建的一些内容。您可以看到这里有一些我可以启用的功能。我可以添加自定义操作。这些都可以保留。我将上传一个文件。这是我挑选的一个讲座，其中有一些建议。我会在这里添加。至于这些问题，这个问题不重要。其他问题都是合理的，并且是创始人经常问到的问题。我要在这些指令中再增加一些内容，“反馈要简明扼要并且具有建设性。”好的，所以如果有更多时间，我会给您展示一些其他的功能，但是这已经是一个不错的开始。现在我们可以在预览选项卡上试用它。所以我会说：“有一个常见的问题。在雇佣初创公司员工时应该注意哪三个问题？”现在它将查看我上传的文件。

当然，它还会拥有GPT-4的所有背景知识。这非常好。这是三个我确实经常提到的问题。现在我们可以继续，它会开始遵循其他指令，并且询问我为什么增长不够快。但是为了节约时间，我会跳过这一部分。我现在只将其发布给我自己，以便稍后继续工作。我可以添加更多内容，添加我认为有用的一些操作，然后我可以公开共享。这就是使用Chat GPT创建GPT的样子，谢谢。顺便说一句，我一直以来都想在整个YC的工作时间之后这样做。我一直想，“嘿，总有一天我会制作一个能做到这一点的机器人，那将是很棒的。”所以通过GPT，我们让人们可以轻松共享和发现他们与世界一起使用Chat GPT的有趣方式。您可以创建像我刚刚创建的私人GPT，或者您可以通过链接公开分享您的创作。如果您是Chat GPT企业版的用户，您可以为您的公司创建GPT。本月晚些时候，我们将推出GPT商店。您可以在商店中列出GPT。谢谢。

我们重视收入分享。我们将向构建最有用和最常用的GPT的人支付我们收入的一部分。我们对GPT商店培育一个充满活力的生态系统感到非常兴奋。从我们在周末自己创建的内容来看，我们有信心会有很多精彩的内容。我们很快将发布更多信息。所以这就是GPT，我们迫不及待地想看到您将构建的内容。

但这是一个开发者会议，最酷的事情是，我们将相同的概念带到API中。你们中的许多人已经在API上构建类似代理的体验。例如，Shopify Sidekick可以让您在平台上执行操作。Discord的Clyde允许Discord管理员创建自定义人物。Snaps My AI是一款可添加到群聊中并进行推荐的定制聊天机器人。这些体验很棒，但却很难构建，有时需要数月时间和数十名工程师。构建这种定制助手体验需要处理很多内容。因此，今天我们使用我们的新助手API使这一过程更加简化。

助手API提供了持久线程，因此无需考虑长时间的对话历史记录处理，内置的代码检索解释器和Python解释器在沙盒环境中运行，当然还有我们之前讨论过的改进的函数调用功能。

现在，我想给大家展示一下这是如何工作的演示，这是我们的开发者体验负责人Raman。欢迎，谢谢，大家好。哇，看到大家都在这里真的太棒了。看到这么多人将人工智能融入到他们的应用中真的非常鼓舞人心。今天，我们正在API中推出新的模式，但我们也非常激动地改进了开发者的体验，让您可以构建助理代理。所以让我们马上开始。

想象一下，我正在为全球探险者构建一款旅行应用程序，这是着陆页面。实际上，我已经使用gp4来提出这些目的地的想法，对于那些有敏锐眼光的人来说，这些插图是使用今天对所有人可用的新的darly 3 API自动生成的。所以这相当了不起。但是让我们通过为应用程序添加一个非常简单的助手来增强它。这是我们即将回到的屏幕。首先，我将切换到新的助手playground。创建助手很简单。您只需要给它命名，提供一些初始指令，选择一个模型。在这种情况下，我会选择gp4 turbo，我还会选择一些工具。我会打开代码解释器和检索，并保存。就是这样，我们的助手准备好了。

接下来，我可以与这个助理API的两个新原语集成：线程和消息。让我们快速看一下代码。这里的流程非常简单。对于每个新用户，我将创建一个新的线程，当这些用户与他们的助理进行互动时，我将把他们的消息添加到线程中。非常简单。然后我可以随时运行助理来将响应流回应用程序。所以我们可以返回应用程序，然后在实际操作中尝试一下。如果我说，“嘿，我们去巴黎吧。”好的，就是这样。只需要几行代码，用户现在就可以在应用程序中拥有一个非常专业的助理。我想强调其中我最喜欢的一个功能：函数调用。如果你还没有使用过它，函数调用确实很强大，正如Sam所提到的，我们今天正在进一步发展它。它现在保证了没有额外延迟的JSON输出，而且你可以同时调用多个函数。所以在这里，如果我继续说，“嘿，有哪些前十个要做的事情？”当我让助理对此做出回应时，助理知道函数，包括右侧的地图上所见到的函数，所以现在所有这些点都在实时落下。嗯，非常酷。这种集成使得我们的自然语言界面可以流畅地与我们应用程序的组件和功能进行交互，它真正展现出了AI与UI之间的和谐，助理实际上正在采取行动。

接下来，让我们谈谈检索。检索是指给助理更多的知识，超越这些即时用户消息。事实上，我受到了启发，我已经预订了去巴黎的机票，所以我现在要把这个PDF文件拖放到这里。在它上传的过程中，我可以简单地偷看一下。这是一个非常典型的联合航空的飞机票。幕后的情况是，检索正在读取这些文件，瞧，关于这个PDF的信息出现在屏幕上。当然，这是一个非常小的PDF，但助理可以解析长篇文档，从大量的文本到复杂的产品规格，这取决于你所构建的内容。事实上，我还预订了一个Airbnb，所以我也要将它拖放到对话中。顺便说一下，我们听到了许多开发者关于构建它有多么困难的问题。通常情况下，你需要计算嵌入向量，设置分块算法。现在，这一切都不需要你操心了。这里还有更多的内容。通常情况下，每次API调用都需要重新发送整个对话历史记录，这意味着设置键-值存储，处理上下文窗口，序列化消息等等。但是，这个新的有状态API现在完全解决了这些复杂性。但仅仅因为API在管理这些复杂性，并不意味着它是一个黑盒子。事实上，你可以在开发者控制面板中直观地看到工具正在采取的步骤。所以，在这里，如果我继续点击线程，我相信这是我们目前正在操作的线程，看到这些都是所有的步骤，包括调用带有正确参数的函数和我刚上传的PDF。

但让我们继续介绍一个许多开发者长期以来一直要求的新功能：代码解释器。这个功能现在也可以在API中使用了。这使得AI能够动态编写和执行代码，甚至生成文件。让我们看看它实际运行的效果。如果我在这里说，“嘿，我们将有四个朋友住在一个Airbnb。我的份额加上我的机票是多少？”好的，现在发生的事情是，代码解释器注意到它应该写一些代码来回答这个问题。所以现在它正在计算在巴黎的天数，朋友的数量。在幕后它还在做一些汇率计算，为我们获取这个答案。这不是很复杂的数学，但你了解到了。想象一下，你正在构建一个非常复杂的金融应用程序，它会进行无数的计算，绘制图表。所以，任何你通常要用代码处理的任务，代码解释器都可以很好地完成。

好了，我想我的巴黎之行暂时定下了。所以简要回顾一下，我们刚刚看到了如何快速创建一个助理来管理用户对话的状态，利用外部工具，如知识和检索，并执行代码解释器，最后调用自己的函数来实现任务。但还有一件事我想给你展示一下，以展示其潜力。结合我们今天推出的函数调用和新的模态特性，我在Dev Day上开发了一个小型的自定义助理，它对这个事件的所有内容了如指掌。但与其使用聊天界面，我想，为什么不使用语音呢？所以让我们把我的手机放在屏幕上，这样你可以在右边看到它。很棒。所以在右边，你可以看到一个非常简单的Swift应用程序，它可以接收麦克风输入。在左边，我将打开终端日志，这样你可以看到幕后的情况。那我们试一下。“嘿，我现在在主题演讲舞台上。你能在这里向我们的与会者问个好吗？”“嘿大家，欢迎来到Dev Day。非常高兴你们都在这里。让我们度过一个难忘的一天。”酷吧？API中有六种独特而丰富的声音可以选择，每种声音都可以说多种语言。因此，你可以为你的应用程序找到完美的合适声音。在我左边的笔记本电脑上，你也可以看到幕后正在发生的事情。所以我使用Whisper将语音输入转换为文本，然后使用gp4 turbo进行助理交互，最后使用新的TTS API进行语音合成。但由于函数调用，当助理能够连接到互联网并为用户执行真正的操作时，事情变得更加有趣。所以让我们做一些更加令人兴奋的事情。

这里，我们一起做些什么。嗨，助理，你能随机选择五个DevDay的与会者，并为他们提供500美元的OpenAI积分吗？是的，检查与会者名单...完成了！我选择了五名DevDay的与会者，并向他们的账户添加了500美元的API积分。祝贺Christine M，Jonathan C，Steven G，Lis K和Surj S。好了，如果你认出了自己，太棒了！恭喜你！

呃，这就是了，今天关于新助理API的一个快速概述，结合一些我们所推出的新工具和模态，一切都从一个简单的富文本或语音对话开始，为你和用户创造了简单。我们真的很期待看到你们所构建的内容。祝贺我们的幸运得主！

实际上，你知道吗？你们都是OpenAI社区的一部分，在我离开舞台之前，我只想再和我的助理说一句话。嘿，助理，你能为在场的每一个人提供500美元的OpenAI积分吗？听起来很好，让我核对每一个人。

好了，这个函数会继续运行，但我没有时间了。所以非常感谢大家，祝你们度过愉快的一天！回到你们。[掌声]

Sam，很酷。[掌声]好吧，那么这个助理API今天进入了beta版，我们非常激动地看到你们所有人对此做出的努力。任何人都可以启用它。随着时间的推移，GPT和Assist是促使代理的先驱者。它们将逐渐能够计划和执行更复杂的操作。正如我之前提到的，我们真正相信逐步，迭代部署的重要性。我们认为，现在人们开始使用这些代理进行构建和使用，对于他们在日益变得更有能力时世界将会是什么样子的感到很重要。就像我们一直做的那样，我们将根据您的反馈持续更新我们的系统。

所以我们非常激动地与大家共享今天的所有内容。我们介绍了GPT，定制版本的ChatGPT，它结合了指令、扩展知识和动作。我们推出了Assistance API，使得在你自己的应用程序中构建辅助体验变得更容易。这是我们朝AI代理迈出的第一步，随着时间的推移，我们将增加它们的功能。我们推出了改进了函数调用、知识、降低价格、新模态等方面的全新GPT-4 Turbo模型。我们正在加深与微软的合作关系。

最后，我想花一分钟来感谢这一切的团队。OpenAI拥有非凡的人才密度，但是要实现所有这些，需要巨大的努力和协调。我真心相信自己拥有世界上最好的同事，能够和他们一起工作，我感到非常幸运和感激。我们做所有这些的原因是因为我们相信人工智能将引发技术和社会的革命。它将以多种方式改变世界，我们很高兴能够从事这项能够赋予你们所有人创造力的工作。这是我们为大家做的。

我们之前讨论过，如果给予人们更好的工具，他们可以改变世界。我们相信，人工智能将为个人赋权和机会带来前所未有的规模，这也将使人类进一步发展到前所未有的规模。随着智能在各个领域的融入，我们都将拥有即时的超能力。我们对于你们将如何运用这项技术，以及我们共同塑造的新未来感到兴奋。

我们希望明年你还能回来。相比我们现在正在忙着为你们打造的东西，今天我们发布的将显得相当古老。感谢你们所做的一切。感谢你们今天来到这里。【音乐】

## OpenAI Dev Day 1106

Good morning, thank you for joining us today. Please welcome to the stage Sam [Music] Alman. Good morning, welcome to our first-ever OpenAI Dev Day. We're thrilled that you're here and this energy is awesome. Welcome to San Francisco.

San Francisco has been our home since day one. The city is important to us and to the tech industry in general. We're looking forward to continuing to grow here, so we've got some great stuff to announce today. But first, I'd like to take a minute to talk about some of the things we've done over the past year.

About a year ago, on November 30th, we shipped ChatGPT as a low-key research preview, and that went pretty well. In March, we followed that up with the launch of GPT-4, which is still the most capable model out in the world. And in the last few months, we launched voice and vision capabilities, so that ChatGPT can now see, hear, and speak. And more recently, we launched DALL·E 3, the world's most advanced image model. You can use it within ChatGPT. For our Enterprise customers, we launched ChatGPT Enterprise, which offers enterprise-grade security and privacy, higher speed, GPT-4 access, longer context windows, and much more.

Today, we've got about 2 million developers building on our API for a wide variety of use cases, and they're doing amazing stuff. Over 92% of Fortune 500 companies are building on our products, and we now have about 100 million weekly active users on ChatGPT. What's incredible is that we got there entirely through word of mouth. People find it useful and tell their friends. OpenAI is the most advanced and the most widely used AI platform in the world. But numbers never tell the whole picture. What's really important is how people use the products, how people are using AI. So, I'd like to show you a quick video.

I actually wanted to write something to my dad in Tagalog. I want a non-romantic way to tell my parent that I love him, and I also want to tell him that he can rely on me, but in a way that still has the respect of like a child-parent relationship that you should have in Filipino culture. And in Tagalog, when it's translated into English, it says, "I love you very deeply, and I will be with you no matter where the path leads." [Applause]

So, we love hearing the stories of how people are using the technology. It's really why we do all of this. Okay, now onto the new stuff, and we have got a lot. First, we're going to talk about a bunch of improvements we've made, and then we'll talk about where we're headed next.

Over the last year, we spent a lot of time talking to developers around the world. We've heard a lot of your feedback, and it has really informed what we have to show you today. Today, we are launching a new model, GPT-4 Turbo. GPT-4 Turbo will address many of the things that you all have asked for. So, let's go through what's new. We've got six major things to talk about for this part.

Number one: context length. A lot of people have tasks that require a much longer context length. GPT-4 supported up to 8K tokens, and in some cases, up to 32K tokens of context length. But we know that isn't enough for many of you. GPT-4 Turbo supports up to 128,000 tokens of context, which is 300 pages of a standard book, 16 times longer than our 8K context. And in addition to longer context length, you'll notice that the model is much more accurate over a long context.

Number two: more control. We've heard loud and clear that developers need more control over the model's responses and outputs. So, we've addressed that in a number of ways. We have a new feature called Json mode, which ensures that the model will respond with valid Json. This has been a huge developer request, and it'll make calling APIs much easier. The model is also much better at function calling. You can now call many functions at once, and it'll do better at following instructions in general. We're also introducing a new feature called reproducible outputs. You can pass a seed parameter, and it'll make the model return consistent outputs. This gives you a higher degree of control over Model Behavior. This rolls out in beta today, and in the coming weeks, we'll roll out a feature to let you view log probabilities in the API.

Alright, number three: better world knowledge. You want these models to be able to access better knowledge about the world, and so do we. We're launching retrieval in the platform. You can bring knowledge from outside documents or databases into whatever you're building. We're also updating the knowledge cutoff. We're just as annoyed as all of you, probably more, that GPT-4's knowledge about the world ended in 2021. We will try to never let it get that out of date again. GPT-4 Turbo has knowledge about the world up to April of 2023, and we will continue to improve that over time.

Number four: new modalities. Surprising no one, DALL·E 3, GPT-4 Turbo with vision, and the new text-to-speech model are all going into the API today. We have a handful of customers that have just started using DALL·E 3 to programmatically generate images and designs. Today, K is launching a campaign that lets its customers generate Diwali cards using DALL·E 3. And of course, our safety systems help developers protect their applications against misuse. Those tools are available in the API. GPT-4 Turbo can now accept images as inputs via the API and can generate captions, classifications, and analysis. For example, BeEyes uses this technology to help people who are blind or have low vision with their daily tasks, like identifying products in front of them. And with our new text-to-speech model, you'll be able to generate incredibly natural-sounding audio from text in the API, with six preset voices to choose from. [Applause]

Speaking of new modalities, we're also releasing the next version of our open-source speech recognition model, Whisper V3, today. And it'll be coming soon to the API. It features improved performance across many languages, and we think you're really going to like it.

Okay, number five: customization. Fine-tuning has been working really well for GPT-3.5 since we launched it a few months ago. Starting today, we're going to expand that to the 16K version of the model. Also starting today, we're inviting active fine-tuning users to apply for the GPT-4 fine-tuning experimental access program. The fine-tuning API is great for adapting our models to achieve better performance in a wide variety of applications with a relatively small amount of data. But you may want a model to learn a completely new knowledge domain or to use a lot of proprietary data. So, today we're launching a new program called custom models. With custom models, our researchers will work closely with a company to help them make a great custom model specifically for their use case. 

Using our tools, this includes modifying every step of the model training process, doing additional domain-specific pre-training, a custom RL post-training process tailored for a specific domain, and whatever else we won't be able to do. This won't be cheap initially, but if you're excited to push things as far as they can currently go, please get in touch with us, and we think we can do something pretty great.

Higher Rate Limits: We are doubling the tokens per minute for all gpt4 customers, making it easier for them to do more. Customers can now request changes to further rate limits and quotas directly in their API account settings.

Copyright Shield: To support our customers, we are introducing copyright Shield, which means that OpenAI will defend customers and cover costs in case of legal claims related to copyright infringement. This applies to both ChatGPT Enterprise and the API. It is important to note that OpenAI does not train on data from the API or ChatGPT Enterprise.

Pricing for GP4 Turbo: The pricing for GP4 Turbo, which is an improvement over GP4, has been significantly reduced. It is now 3x cheaper for prompt tokens and 2x cheaper for completion tokens. This reduction in cost aims to address feedback from developers who wanted to build more but found GP4 expensive. OpenAI will also focus on improving speed in the future.

Pricing for GPT 3.5 Turbo 16k: The cost of GPT 3.5 Turbo 16k has also been decreased. Input tokens are now 3x cheaper, and output tokens are 2x cheaper. Consequently, running the fine-tuned GPT 3.5 Turbo 16k version is more cost-effective than the previous GPT 3.5 4K model.

Building a Strong Partnership: OpenAI values its partnership with Microsoft and appreciates their support in building the best systems for training and inference. Microsoft is committed to providing the best infrastructure in Azure with OpenAI API support. They are also focused on empowering developers by making tools like GitHub Co-Pilot available.

Future Goals: OpenAI and Microsoft are dedicated to pushing the boundaries of AI together. They aim to provide developers with the best systems and computing power to drive progress in AI. Both companies believe in AI's potential to empower individuals and organizations globally and prioritize safety in their endeavors.

Updates to ChatGPT: ChatGPT now utilizes GPT 4 Turbo with the latest improvements. It can browse the web, run code, analyze data, generate images, and more. The model picker is eliminated, and ChatGPT will automatically know which tools to use. OpenAI aims to provide smarter, more customizable AI that can perform various tasks on behalf of users. Gradual iterative deployment is crucial for addressing safety concerns and requires technical work and societal consideration.

So today we're taking our first small step that moves us towards this future. We're thrilled to, uh, we're thrilled to introduce gpts. Gpts are tailored versions of chat GPT for a specific purpose. You can build a GPT, a customized version of chat GPT, for almost anything with instructions, expanded knowledge, and actions. And then you can publish it for others to use. And because they combine instructions, expanded knowledge, and actions, they can be more helpful to you. They can work better in many contexts, and they can give you better control. They'll make it easier for you to accomplish all sorts of tasks or just have more fun, and you'll be able to use them right within chat GPT. 

You can, in effect, program a GPT with language just by talking to it. It's easy to customize the behavior so that it fits what you want. This makes building them very accessible and it gives agency to everyone. So we're going to show you what gpts are, how to use them, how to build them, and then we're going to talk about how they'll be distributed and discovered. 

And then after that, for developers, we're going to show you how to build these agent-like experiences into your own apps. So first, let's look at a few examples. Our partners at code.org are working hard to expand computer science in schools. They've got a curriculum that is used by tens of millions of students worldwide. Code.org crafted Lesson Planner GPT to help teachers provide a more engaging experience for middle schoolers. If a teacher asks it to explain for loops in a creative way, it does just that. In this case, it'll do it in terms of a video game character repeatedly picking up coins. Super easy to understand for an eighth grader. As you can see, this GPT brings together code.org's extensive curriculum and expertise and lets teachers adapt it to their needs quickly and easily. 

Next, Canva has built a GPT that lets you start designing by describing what you want in natural language. If you say, "Make a poster for Dev Day reception this afternoon or this evening," and you give it some details, it'll generate a few options to start with by hitting Canva's APIs. Now, this concept may be familiar to some of you. We've evolved our plugins to be custom actions for GPTs. 

You can keep chatting with this to see different iterations, and when you see one you like, you can click through to Canva for the full design experience. So now we'd like to show you a GPT live. Zapier has built a GPT that lets you perform actions across 6,000 applications to unlock all kinds of integration possibilities. I'd like to introduce Jessica, one of our Solutions architects who is going to drive this demo. Welcome, Jessica. Thank you, S.H. Everyone, thank you. 

[Applause] All, thank you all for being here. My name is Jessica Shay. I work with partners and customers to bring their product alive, and today, I can't wait to share/show you how hard we've been working on this. So let's get started. So, to start, where your GBT will live is on this upper left corner. I'm going to start with clicking on the Zapier Your AI Actions, and on the right-hand side, you can see that's my calendar for today. So it's quite a day. I've already used this before, so it's actually already connected to my calendar. To start, I can ask, "What's on my schedule for today?" We build GPTs with security in mind, so before it performs any action or shares data, it will ask for your permission. So right here, I'm going to say "allowed". GBT is designed to take in your instructions, make the decision on which capability to call to perform that action, and then execute that for you. 

So you can see right here, it's already connected to my calendar. It pulls in my information, and then I've also prompted it to identify conflicts on my calendar. So you can see right here, here it actually was able to identify that. So it looks like I have something coming up. So what if I want to let Sam know that I have to leave early? So right here, I say, "Let Sam know I got to go um chasing GPTs." So with that, I'm gonna swap to my conversation with Sam and then I'm going to say, "Yes, please run that." Sam, did you get that? I did, awesome. So this is only a glimpse of what is possible, and I cannot wait to see what you all will build. Thank you, and back to you, Sam. Thank you, Jessica. 

So those are three great examples. In addition to these, there are many more kinds of GPTs that people are creating, and many, many more that will be created soon. We know that many people who want to build a GPT don't know how to code. We've made it so that you can program the GPT just by having a conversation. We believe that natural language is going to be a big part of how people use computers in the future, and we think this is an interesting early example. So I'd like to show you how to build one. 

All right, so I want to create a GPT that helps give founders and developers advice when starting new projects. I'm going to go to create a GPT here, and this drops me into the GPT Builder. I worked with founders for years at YC, and still whenever I meet developers, the questions I get are always about how do I, you know, think about a business idea, can you give me some advice? 

I'm going to see if I can build a GPT to help with that. So to start, GPT Builder asks me what I want to make, and I'm going to say, I want to help startup founders think through their business ideas and get advice. After the founder has gotten some advice, grill them on why they are not growing faster. All right, so to start off, I just tell the GPT a little bit about what I want here, and it's going to go off and start thinking about that. And it's going to write some detailed instructions for the GPT. It's also going to let's see, ask me about a name. How do I feel about startup Mentor? 

That's fine. That's good. So if I didn't like the name, of course, I could call it something else, but it's you know going to try to have this conversation with me and start there. And you can see here on the right in the preview mode that it's already starting to fill out the GPT. Where it says what it does, it has some like ideas of additional questions that I could ask. And you know what? So it just generated a candidate. Of course, I could regenerate that or change it, but I sort of like that. So I will say that's great. And you see now that the GPT is being built out a little bit more as we go. 

Now what I want this to do, how it can interact with users, I could talk about style here. But what I'm going to say is, I am going to upload transcripts of some lectures about startups I have given. Please give advice based off of those. All right, so now it's going to go figure out how to do that. And I would like to show you the configure tab so you can see some of the things that were built out here as we were going by the Builder itself. And you can see that there are capabilities here that I can enable. I could add custom actions. These are all fine to leave. I'm going to upload a file. So here is a lecture that I picked that I gave with some startup advice. And I'm going to add that here. 

In terms of these questions, this is a dumb one. The rest of those are reasonable and like very much things founders often ask. I'm going to add one more thing to the instructions here, which is, "Be concise and constructive with feedback." All right, so again, if we had more time, I'd show you a bunch of other things, but this is like a decent start. And now we can try it out over on this preview tab. So I will say, "What's a common question? What are three things to look..." Oops! "What are three things to look for when hiring employees at an early-stage startup?" Now it's going to look at that document I uploaded. 

It'll also have, of course, all of the background knowledge of GPT-4. That's pretty good. Those are three things that I've definitely said many times. Now we could go on, and it would start following the other instructions and, you know, grill me on why I'm not growing faster. But in the interest of time, I'm going to skip that. I'm going to publish this only to me for now. I can work on it later. I can add more content. I can add a few actions that I think would be useful, and then I can share it publicly. So that's what it looks like to create a GPT with, thank you. By the way, I always I always wanted to do that after, like, all of the YC office hours. I always thought, "Man, someday I will be able to make a bot that will do this, and that'll be awesome." So with GPTs, we're letting people easily share and discover all the fun ways that they use chat GPT with the world. You can make private GPTs like I just did, or you can share your creations publicly with a link for anyone to use. Or if you're on Chat GPT Enterprise, you can make GPTs just for your company. And later this month, we're going to launch the GPT store. You can list a GPT. Thank you.

I appreciate that you can list a GPT there and we'll be able to feature the best and the most popular gpts. Of course, we'll make sure that gpts in the store follow our policies before they're accessible.
Revenue sharing is important to us. We're going to pay people who build the most useful and the most use gpts a portion of our revenue. We're excited to foster a vibrant ecosystem with the GPT store. Just from what we've been building ourselves over the weekend, we're confident there's going to be a lot of great stuff. We're excited to share more information soon. So those are gpts and we can't wait to see what you'll build.

But this is a developer conference, and the coolest thing about this is that we're bringing the same concept to the API. Many of you have already been building agent-like experiences on the API. For example, Shopify sidekick lets you take actions on the platform. Discord's Clyde lets disc moderators create custom personalities for. And Snaps My AI, a customized chatbot that can be added to group chats and make recommendations. These experiences are great, but they have been hard to build, sometimes taking months and teams of dozens of engineers. There's a lot to handle to make this custom assistant experience. So today, we're making that a lot easier with our new assistance API.

The assistance API includes persistent threads so they don't have to figure out how to deal with long conversation history, built-in retrieval code interpreter in a working Python interpreter in a sandbox environment, and of course the improved function calling that we talked about earlier.

So we'd like to show you a demo of how this works, and here is Raman, our head of developer experience. Welcome, thank you, good morning. Wow, it's fantastic to see you all here. It's been so inspiring to see so many of you infusing AI into your apps. Today, we're launching new modalities in the API, but we're also very excited to improve the developer experience for you all to build assistive agents. So let's dive right in.

Imagine I'm building a travel app for global explorers, and this is the landing page. I've actually used gp4 to come up with these destination ideas, and for those of you with the keen eye, these illustrations are generated programmatically using the new darly 3 API available to all of you today. So it's pretty remarkable. But let's enhance this app by adding a very simple assistant to it. This is the screen we're going to come back to it in a second. First, I'm going to switch over to the new assistants playground. Creating an assistant is easy. You just give it a name, some initial instructions, a model. In this case, I'll pick gp4 turbo, and here I'll also go ahead and select some tools. I'll turn on code interpreter and retrieval and save. And that's it. Our assistant is ready to go.

Next, I can integrate with two new primitives of this assistant API: threads and messages. Let's take a quick look at the code. The process here is very simple. For each new user, I will create a new thread, and as these users engage with their assistant, I will add their messages to the threads. Very simple. And then I can simply run the assistant at any time to stream the responses back to the app. So we can return to the app and try that in action. If I say, "Hey, let's go to Paris," alright, that's it. With just a few lines of code, users can now have a very specialized assistant right inside the app. And I'd like to highlight one of my favorite features here: function calling. If you have not used it yet, function calling is really powerful, and as Sam mentioned, we're taking it a step further today. It now guarantees the JSON output with no added latency, and you can invoke multiple functions at once for the first time. So here, if I carry on and say, "Hey, what are the top 10 things to do?" when I have the assistant respond to that, again, and here what's interesting is that the assistant knows about functions, including those to annotate the map that you see on the right, and so now all of these pins are dropping in real time. Here, yeah, it's pretty cool. And that integration allows our natural language interface to interact fluidly with components and features of our app, and it truly showcases now the harmony you can build between AI and UI, where the assistant is actually taking action.

But next, let's talk about retrieval. And retrieval is about giving our assistant more knowledge beyond these immediate user messages. In fact, I got inspired and I already booked my tickets to Paris, so I'm just gonna drag and drop here this PDF. While it's uploading, I can just sneak peek at it. Very typical United flight ticket. And behind the scene here, what's happening is that retrieval is reading these files, and boom, the information about this PDF appeared on the screen. And this is, of course, a very tiny PDF, but assistants can parse long-form documents, from extensive text to intricate product specs, depending on what you're building. In fact, I also booked an Airbnb, so I'm just going to drag that over to the conversation as well. And by the way, we've heard from so many of you developers how hard that is to build yourself. You typically need to compute your embeddings, you need to set up chunking algorithms. Now, all of that is taken care of. And there's more than retrieval. With every API call, you usually need to resend the entire conversation history, which means setting up a key-value store, handling the context window, serializing messages, and so forth. That complexity now completely goes away with this new stateful API. But just because the API is managing this, does not mean it's a blackbox. In fact, you can see the steps that the tools are taking right inside your developer dashboard. So here, if I go ahead and click on threads, this is the thread I believe we're currently working on, and see like these are all the steps, including the functions being called with the right parameters, and the PDFs I've just uploaded.

But let's move on to a new capability that many of you have been requesting for a while: code interpreter. It is now available today in the API as well. That gives the AI the ability to write and execute code on the fly, but even generate files. So let's see that in action. If I say here, "Hey, will be four friends staying at an Airbnb. What's my share of it plus my flights?" All right, now here what's happening is that code interpreter noticed that it should write some code to answer this query. So now it's computing the number of days in Paris, number of friends. It's also doing some exchange rate calculation behind the scenes to get this answer for us. Not the most complex math, but you get the picture. Imagine you're building a very complex finance app that's crunching countless numbers, plotting charts. So really any task that you'd normally tackle with code, then code interpreter will work great for you.

All right, I think my trip to Paris is solid. So to recap, here we've just seen how you can quickly create an assistant that manages state for your user conversations, leverages external tools like knowledge and retrieval, and code interpreter, and finally invokes your own functions to make things happen. But there's one more thing I wanted to show you to really open up the possibilities. Using function calling combined with our new modalities that we're launching today, while working on Dev Day, I built a small custom assistant that knows everything about this event. But instead of having a chat interface, while running around all day today, I thought why not use voice instead? So let's bring my phone up on screen here so you can see it on the right. Awesome. So on the right, you can see a very simple Swift app that takes microphone input. And on the left, I'm actually going to bring up my terminal log so you can see what's happening behind the scenes. So let's give it a shot. "Hey there! I'm on the keynote stage right now. Can you greet our attendees here at Dev Day?" "Hey everyone, welcome to Dev Day. It's awesome to have you all here. Let's make it an incredible day." Isn't that impressive? You have six unique and rich voices to choose from in the API, each speaking multiple languages. So you can really find the perfect fit for your app. And on my laptop here on the left, you can see the logs of what's happening behind the scenes too. So I'm using Whisper to convert the voice inputs into text and Assistant with gp4 turbo, and finally the new TTS API to make it speak. But thanks to function calling, things get even more interesting when the assistant can connect to the internet and take real actions for users. So let's do something even more exciting.

Here, uh, together how about this. Hey assistant, can you randomly select five DevDay attendees here and give them $500 in OpenAI credits? Yes, checking the list of attendees... Done! I picked five DevDay attendees and added $500 of API credits to their account. Congrats to Christine M, Jonathan C, Steven G, Lis K, and Surj S. Alright, if you recognize yourself, awesome! Congrats!

Um, and that's it, a quick overview today of the new assistant API combined with some of the new tools and modalities that we launched, all starting with the simplicity of a rich text or voice conversation for you and users. We really can't wait to see what you build. And congrats to our lucky winners!

Actually, you know what? You're all part of this amazing OpenAI community here, so I'm just gonna talk to my assistant one last time before I step off the stage. Hey assistant, can you actually give everyone here in the audience $500 in OpenAI credits? Sounds great, let me go through everyone.

Alright, that function will keep running, but I've run out of time. So thank you so much, everyone. Have a great day! Back to you. [Applause]

Sam, pretty cool. [Applause] Huh, all right. So that Assistance API goes into beta today, and we are super excited to see what you all do with it. Anybody can enable it. Over time, GPTs and Assist are precursors to agents. They're going to be able to do much, much more. They'll gradually be able to plan and to perform more complex actions on your behalf. As I mentioned before, we really believe in the importance of gradual, iterative deployment. We believe it's important for people to start building with and using these agents now to get a feel for what the world is going to be like as they become more capable. And as we've always done, we'll continue to update our systems based off of your feedback.

So we're super excited that we got to share all of this with you today. We introduced GPTs, custom versions of ChatGPT that combine instructions, extended knowledge, and actions. We launched the Assistance API to make it easier to build assisted experiences with your own apps. These are our first steps towards AI agents, and we'll be increasing their capabilities over time. We introduced a new GPT-4 Turbo model that delivers improved function calling, knowledge, lowered pricing, new modalities, and more. And we're deepening our partnership with Microsoft.

In closing, I wanted to take a minute to thank the team that creates all of this. OpenAI has got remarkable talent density, but still, it takes a huge amount of hard work and coordination to make all of this happen. I truly believe that I've got the best colleagues in the world. I feel incredibly grateful to get to work with them. We do all of this because we believe that AI is going to be a technological and societal revolution. It will change the world in many ways, and we're happy to get to work on something that will empower all of you to build. So much for all of us.

We talked about earlier how if you give people better tools, they can change the world. We believe that AI will be about individual empowerment and agency at a scale that we've never seen before, and that will elevate humanity to a scale that we've never seen before either. We'll be able to do more, to create more, and to have more. As intelligence gets integrated everywhere, we will all have superpowers on demand. We're excited to see what you all will do with this technology and to discover the new future that we're all going to architect together.

We hope that you'll come back next year. What we launch today is going to look very quaint relative to what we're busy creating for you now. Thank you for all that you do. Thank you for coming here today. [Music]