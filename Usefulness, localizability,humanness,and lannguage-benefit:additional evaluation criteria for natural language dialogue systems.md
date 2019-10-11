## Usefulness, localizability, humanness, and lannguage-benefit: additional evaluation criteria for natural language dialogue systems ##

## 摘要 ##
本文使用ALICE/AIML聊天机器人架构开发涵盖不同语言，流派，文本类型和用户群体的聊天机器人，来说明自然语言对话系统评估的定性方面。

本文概述了在自然语言对话系统中应用的评价技术，包括黑盒（black box），玻璃盒（glass box），比较（comparative），
定量（quantitative）和定性（qualitative）评估。

在NLP对话系统评估中有四个方面通常被忽略：
- 有用性（usefulness）： 用户的质量需求
- 可本地化（localizability）：对新体裁（genre）和语言的本地化
- 人性（humanness）或自然（naturalness）：与人类对话相比
- 语言优势（language benefit）：与其他接口相比

## 简介 ##
如果计算机系统被用户或顾客使用，那么有用性是第一个要考虑的定性指标。

本地化指标也经常被忽略，为了不仅仅是玩具演示，系统需要易于适应新的语言类型甚至新的语言。
重要的是要查看此过程有多么容易，否则就该系统而言，该系统显然不是“可重用”或可移植的。

另一个评估人机对话系统的方法是比较人机对话系统产生的语料和与人-人对话的语料，从而评估生成自然语言的“人性”。

评价的第四个方面是评估“语言效益”，通过采用自然语言对话，而不是一个简单的基于关键字接口获得。

## ALICE/AIML 聊天机器人框架 ##

聊天机器人的发展源于ELIZA，其扮演了心理医生的角色。然后PARRY诞生，其模仿的是一位偏执狂病人。
PARRY可以帮助研究偏执狂，EILIZA可以作为一名助手，在一个小时之内接待上百名病人。

ALICE使用人工智能标记语言（AIML）编写。

## 口语对话系统（SLD）中使用的评估技术 ##
对话系统可以分为口语对话系统和文本对话系统。其中，口语对话系统可以是系统主导系统，用户主导系统和混合主导系统（取决于谁控制对话）。

在系统主导系统中系统控制对话，从用户获取信息来完成任务。在用户主导系统中用户控制对话。在混合主导系统中，系统和用户分别在某些时刻主导对话。

Hirschman和Thompson指出，评估对于系统的发展来说是很重要的。对于系统开发者来说，通过评估，可以判断系统性能是否提高了。
对于系统集成者来说，可以确定应该在哪里使用哪种方法，对于消费者来说，可以确定哪个系统最能满足个人需求。

口语对话系统中具有四种评估方式：主观（subjective），客观（objective），定量（quantitative）和定性（qualitative）评价。

- 主观评价（subjective evaluation）：基于用户的判断，包括的指标有：上下文适当性（可将回复分为合适，不合适和摸棱两可的)，
隐式恢复（用户可以使用上下文从错误中恢复）。
- 客观评价（objective evaluation）：不涉及人工评价，包括：根据参考答案判断正确答案的比例，任务完成度，话语的数量等。 
- 定量评价（quantitative evaluation）：计算一些统计数据，在系统之间进行比较。
- 定性评价（qualitative evaluation）：使用一些规则或专家来判断一些参数。

对SLD进行评估的目的可分为：
- 充分性评估（adequacy evaluation），即确定系统是否符合特定目的； 
- 诊断评估（diagnostic evaluation），判断系统性能概况，主要是通过示例性输入的测试完成的； 
- 性能评估（performance evaluation），是对一个或多个特定领域中系统性能的度量。

可以确定两个评估口语对话系统的方法：玻璃盒（glass box，基于组件的评估）和黑盒（black box，基于整个系统的评估）评估。


介绍了两个新的指标：查询密度（query density）和概念效率（concept efficiency）。
查询密度衡量的是每个用户查询引入的新概念的平均数量，而概念效率则列出了成功理解一个概念所需的平均轮次。

## 有用性评价（usefulness evaluation） ##
YPA是一种自然语言对话系统，允许用户从英国电信的黄页中检索信息。黄页包含广告，广告商名称和联系信息。 
YPA系统返回地址，如果未找到地址，则开始对话，系统要求用户提供更多详细信息，以便为用户提供所需的地址。

为了评估YPA，从一个查询语料库中提取了75个查询，并准备了一个响应表以查看返回的地址是否合适，
需要多少对话步骤，召回的地址总数以及相关的地址数。 结果显示，在75个查询中有62个返回了地址，其中74％与原始查询有关。

用同样的方法评估古兰经聊天机器人，其以英文版和阿拉伯版的伊斯兰教圣经文本作为语料。
从伊斯兰站点中随机抽取67个句子作为古兰经聊天机器人的输入，输出由5个穆斯林和6个非穆斯林进行评价。

评价标准为：相关的（Related R）：答案是正确的而且主题是一致的；
部分相关的（partially related PR）：答案是错误的但主题是一致的；
不相关的（not related NR）：答案是错误的而且主题是不一致的。

得到的结果如下图所示：

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/The%20proportion%20of%20each%20answer%20type%20identified%20by%20users%20of%20the%20Qur%E2%80%99an%20chatbot.PNG?raw=true)

主观评价：1代表无意义的回复，5代表适当的回复。

## 本地化（Localizability） ##
评价的可本地化性测试使自然语言对话系统适应新领域或新语言而不影响其工作方式有多么容易。
根据这一目标，某些对话系统已被设计为可通过改变领域语料库，重新训练从而适应新领域。

本文可通过8种不同的语料获得8个聊天机器人，针对其中一个语料得到的聊天机器人，采用4种不同的匹配算法
（依次匹配 atomic，第一个单词匹配 first word，最重要的单词匹配 the most significant word，随机匹配 no match）,得到四个原型。
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/The%20training%20corpora.PNG?raw=true)

对这四种原型产生的4个回复进行评价，结果如下图：
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Matching%20types%20in%20the%20Afrikaans%20Prototype.PNG?raw=true)

## 人性评价（Humanness evaluation） ##
对话系统的人性方面衡量的方式为测试对话系统欺骗用户使其相信自己正在与真实的人而不是虚拟的人交流的能力。

Colby使用这个策略测试PARRY，精神科医生对PARRY和三个患有偏执狂的病人进行询问，无法区分PARRY和病人。

在Loebner prize竞赛中也采取了这个策略，用户与参赛聊天机器人交谈10分钟，如果在这10分钟之内用户无法确定交谈对象是人类还是机器人，那么聊天机器人获胜。

但是10分钟很短不足以判断出聊天机器人的人性，而且评价很主观，之依赖参与测试的用户。因此，提出一种新的比较方式。
分别从词汇（lexical）、词性（part-of-speech）和语义（sematic）三个层面比较聊天机器人的回复和人类的回复。

## 语言效益评估（language benefit evaluation） ##
通过将自然语言对话系统与基于关键字的接口系统相比较，可获得语言效益评价。

Happy Assistant是“基于自然语言对话框的导航系统，可帮助用户访问电子商务网站以查找有关产品和服务的相关信息”。
系统的可用性（usability）通过评估系统在易用性，系统流程，系统响应的有效性和用户词汇方面是否满足用户期望得到的。

相比于通过搜索引擎获得信息，人们更喜爱通过聊天机器人获得信息。

## 结论 ##
不同的评价技术：
- 黑盒 black box
- 玻璃盒 glass box
- 比较 comparative
- 定量 quantitative
- 定性 qualitative

四个经常被忽略的评价指标：
- 有用性 usefulness
- 可本地化 localizability
- 人性或自然性 humanness
- 语言效益 language benefit
