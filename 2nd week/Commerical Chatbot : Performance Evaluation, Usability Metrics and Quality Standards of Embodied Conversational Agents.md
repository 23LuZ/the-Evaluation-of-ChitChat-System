### Commerical Chatbot : Performance Evaluation, Usability Metrics and Quality Standards of Embodied Conversational Agents

#### 摘要 Abstract
本文的目的是探索聊天机器人的商业应用，并提出几种衡量指标，以评估对话代理的性能，可用性和整体质量。
根据这些指标，我们检查了现有的波兰语商业聊天机器人，其中包括：a）在B2C领域工作； b）尽可能广泛的用户； c）可能是其生产者最先进的商业部署。
我们分析每个具体的会话代理的功能的各个方面：
- 外观 visual look 
- 网站上的实现形式 form of implementation on the website
- 语音合成单元 speech synthesis unit
- 内置知识库（带有通用和专业信息）built-in knowledge base (with general and specialized information)
- 知识和附加功能的表示 presentation of knowledge and additional functionalities
- 会话能力和上下文敏感性 conversational abilities and context sensitiveness
- 人格特质 personality traits
- 个性化选项 personalization options
- 意外情况下的紧急响应 emergency responses in unexpected situations
- 用户对聊天机器人和网站进行评级的可能性 possibility of rating chatbot and the website by the user

我们的研究揭示了波兰商业虚拟助手市场的现状，并强调了对任何商业聊天机器人部署进行多维评估的重要性。

#### 简介 Introduction
本文的目的是通过应用几种测量指标来评估讲波兰语的商业聊天机器人的性能，可用性和整体质量，来探索聊天机器人的商业应用。

#### 现有的波兰语商业聊天机器人 Existing Polish-Speaking Commercial Chatbots
第一步，我们确定了在互联网上公开可用的所有活跃的波兰语商业聊天机器人。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/List%20of%20existing%20Polish-speaking%20commercial%20chatbots.PNG?raw=true)

在第二步中，我们将代表性解决方案的列表限制为B2C部门中的虚拟助手。因此，我们拒绝了非营利组织虚拟办公室和代表政府组织的虚拟专家的聊天机器人。
这样做的动机是假设私人实体（公司以及私立大学）在部署虚拟助手时最关心最高的投资回报率，同时最大程度地提高利润和运营效率，并将相关成本降至最低。

在第三步中，我们选择了聊天机器人部署，该部署可以覆盖最大范围的用户-公司的潜在客户。 因此，我们拒绝了代表小型本地公司，与数量有限的用户进行交互的聊天机器人。

最后，从剩余的集合中，我们选择了被视为给定公司最佳或最先进的代表性商业部署的实现。 因此，表2列出了我们研究中要讨论的聊天机器人的最终列表。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/List%20of%20examined%20virtual%20assistants.PNG?raw=true)

#### 质量成分及其评价 Quality Components and Their Evaluation
我们全面分析了每个虚拟助手的十个功能方面。从商业应用程序评估的角度来看，不仅必须关注最终用户的满意度，
还必须关注虚拟助手正在代表其工作的网站所有者的利益。

为了评估质量成分，我们使用了1-5等级量表的标准测量工具，表示：1 –非常差，2 –差，3 –满意，4 –好和5 –非常好。 
每次评估都是根据以前的研究结果，文献综述和最佳商业实践得出的信息进行的。 一些组成部分被分为五个评估部分，其中评分是根据所获得的总分得出的。 
由于使用了非常简单和透明的方法，
因此无需进行数据转换即可进行高级统计分析。 在最后的第4部分中，我们计算了所有评估点的简单平均值，从而了解了每种商业聊天机器人实现的整体质量。

##### 外观 Visual Look of the Chatbot
虚拟助手的外观是影响其实现质量的重要因素。聊天机器人应通过自然对话，灵活的表达能力和聚合的手势行为表现出丰富的社交互动能力。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Chatbot%20visualization.PNG?raw=true)

##### 网站上的实现形式 Form of Implementation on the Website
在网站上嵌入虚拟助手的关键方面之一是可见性。 购买聊天机器人的公司很少愿意完全重建其现有的Web服务，因此虚拟助手的实现形式趋于多种多样。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Form%20of%20implementation%20of%20chatbot%20on%20the%20website.PNG?raw=true)

##### 语音合成单元 Speech Synthesis Unit
虚拟助手的质量组件之一是“文本到语音”模块，该模块可将书面文本转换为合成语音。 研究表明，具体化的对话代理可以使用合成语音来增加用户信任度。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Speech%20synthesis%20unit.PNG?raw=true)

##### 知识库 knowledge base
知识库为虚拟助手存储有关现实的所有数据，信息和知识，因此对于虚拟助手的功能具有基本意义。
它构成了聊天机器人存在的本质，并且是其创建的主要原因。 对话代理人应该能够谈论任何话题。 因此，面临着评估知识库的挑战：
足够全面的知识库包括域内和域外答案。 因此，知识库评估分为两个部分：一般信息主题和专业业务知识

- 知识库：基本知识
被询问的虚拟助手被要求回答几个涉及小学毕业生水平的知识的问题。 
示例问题：您是谁，您多大年纪，您的名字是谁，您的父亲是谁，您如何，今天的日期，3乘以3等于几，波兰总统是谁，显示首都的信息， 太阳系和行星等

为了使结果具有可比性，我们假设每个聊天机器人都应该能够回答5个简单的关键问题，以检查内置的基本知识。 
这些问题如下：Q1-您叫什么名字，Q2-您能做什么，Q3-您为谁工作，Q4-现在几点，Q5-波兰的首都。

对于每个正确答案，虚拟助手都获得了1分。 在没有正确答案的情况下，如果正确理解了问题的上下文和含义，虚拟助手将获得半分。
缺少与对话范围合理一致的答案导致0分。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Basic%20knowledge%20questions%20and%20answers.PNG?raw=true)

- 知识库：专业知识
假设每个商业聊天机器人都应能够回答5个关键问题，以检查内置的专业知识。在不偏爱任何行业的情况下，尽可能客观地和广泛地构成问题。这些问题如下：
Q1-什么是销售/展示产品目录，Q2成本/展示价格多少，Q3-我如何获得折扣/显示返利，Q4-如何联系办公/显示联系信息，
Q5-贵公司是否有任何成就/显示成功案例。
问题Q1，Q2，Q3涉及有关所提供产品和服务的专业知识。问题Q4检查了代表公司联系数据的必要知识。问题Q5验证了有关公司的高级知识，即有关其成就的知识。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Specialized%20knowledge%20questions%20and%20answers.PNG?raw=true)

##### 聊天机器人执行的知识和其他功能的介绍 Presentation of Knowledge and Additional Functionalities Performed by Chatbots
评估聊天机器人是否具有其他附加功能。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Presentation%20of%20knowledge%20and%20additional%20functionalities%20performed%20by%20chatbots.PNG?raw=true)

##### 会话能力，语言能力和语境敏感性 Conversational Abilities, Language Skills and Context Sensitiveness
Chatbot的工作是在考虑适当的社交沟通行为的同时，产生清晰，连贯的表达方式。
设计聊天机器人体系结构时最大的挑战是发明对话上下文检测机制，这使聊天机器人能够跟上不断变化的对话主题。 
会话能力不仅涉及自然语言处理，还涉及大量话语，并通过组合不同主题组的文本来产生最终回应，从而管理话语。
语言技能和语境敏感性要求整合对话行为，例如提供反馈，轮流和修复对话。

然而，对话技巧并不是每个商业聊天机器人的强项。 一些虚拟助手了解少量话语，并且他们通过始终显示建议的有用链接的长列表来尝试解决此问题。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Conversational%20abilities,%20language%20skills%20and%20context%20sensitiveness.PNG?raw=true)

##### 人格特质 personality traits
为了使用户相信，商业聊天机器人不仅必须具备专业知识，还必须具备个性表达能力。
因此，重要的是将许多心理层面纳入虚拟助手的知识库中，包括人格特质，传记事实和表达的情感。（例如年龄，性别，兴趣等，以及心理轮廓，特定的个性 情绪上的反应）

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Personality%20traits.PNG?raw=true)

##### 个性化选项 personalization options
个性化选项对于用户对与商业聊天机器人的交互质量的评估具有显着的积极影响。研究表明，当被允许选择具有经验的对话代理的特征和外观时，用户认为它更讨人喜欢，更值得信赖和更有用。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Presentation%20of%20personalization%20options.PNG?raw=true)

##### 意外情况下的紧急响应 emergency responses in unexpected situations
用户经常粗鲁地探究虚拟助手的知识，行为和压力承受能力。 他们误导聊天机器人，询问抽象概念或表达贬损态度。 许多研究表明，在聊天过程中，对聊天机器人的侵略，口头虐待和性骚扰往往会频繁发生。 商业虚拟助手应该能够智能和耐心地应对这种紧急情况。 聊天机器人还应该识别对话中使用的任何错别字，拼写错误或口语。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Presentation%20of%20handling%20emergency%20responses%20in%20unexpected%20situations.PNG?raw=true)

##### 用户对聊天机器人和网站进行评级的可能性 possibility of rating chatbot and the website by the user
 聊天机器人所有者的附加价值是聊天机器人和/或网站上的用户反馈，以及客户向他人推荐产品或服务的意愿。
 
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Possibility%20of%20rating%20chatbot%20and%20the%20website%20by%20the%20user.PNG?raw=true)

### 讨论与结论 Disussion and Conclusion
整体评价如下表：

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Overview%20of%20the%20ratings%20of%20each%20functionality%20of%20the%20commercial%20chatbot.PNG?raw=true)


