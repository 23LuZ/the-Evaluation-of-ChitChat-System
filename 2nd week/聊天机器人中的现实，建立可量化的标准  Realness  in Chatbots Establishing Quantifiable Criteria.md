## 聊天机器人中的现实，建立可量化的标准                              ‘Realness’ in Chatbots: Establishing Quantifiable Criteria 

- 效率 Efficiency-- 表现 Performance    

  能够避免不合适的话语，并进行损害控制 

  Avoid inappropriate utterances and be able to perform damage control

- 效用 Effectiveness -- 功能性 Functionality  类人 Humanity

  使用适当的正式程度的语言

  Use appropriate degrees of formality, linguistic register

  使人信服的，满意的，自然的交互

  Convincing, Satisfying, & natural interaction

- 满意 Satisfaction -- 情感 Affect  辅助功能 Accessibility

  提供问候，表达个性

  Provide greeting, convey personality

  回应社交线索或缺乏社交线索

  Responds to social cues or lack thereof

### 摘要

本文的目标是生成可被聊天机器人用户可接受的可衡量的评价标准。总结了两项研究的结果。

第一个，14名参与者对与ELIZA类型机器人聊天的内容进行关键事件分析（critical incident analysis），对结果进行了内容分析，得到了7个主题。

第二个，将这些主题表达为类似态度的陈述，20名参与者分别与在Chatterbox 挑战赛中获胜的5个聊天机器人和失败的5个聊天机器人对话。潜在变量分析将主题缩减为4个，从而产生了4个可靠性很强的子量表，可以很好的区分这两类机器人。

根据对自由形式的评论进行内容分析得到的四个维度，可以判断聊天机器人对话的自然性。

### 1 评价自然性 Evaluating for Naturalness

对话代理或聊天机器人是能够代表计算机使用者执行操作的系统。也就是，减轻用户使用计算机系统的认知工作量。有两个策略：

- 使用一组很好学习的交流约定：自然语言或者可以接受的会话常规结构，因此用户无需学习复杂的语言如SQL，其他查询语言或者高度受限的编程语言。
- 使用户和计算机共享广泛的知识类别。计算机，用户或者两者都拥有特定的细节,以便通过协商知识来解决问题,而任何一方都不必关注自己难以或无法表示的细节。

交互的自然性和共享知识空间对聊天机器人/对话的自然性来说是很重要的两个特点。

聊天机器人已经发展超过55年了。图灵测试被认为了评价聊天机器人的试金石，尽管有一些研究者认为图灵测试既没有提供计算机中智能操作的定义，也没有提供证明此类智能的必要和充分的条件。

那么，对于用户代理来说，什么才是令人信服的，令人满意的，自然的接口？

也行是为了回答这个问题，比如Loebner Prize 挑战赛每年运行类似图灵测试的测试，以鼓励创建一个可以自然对话的聊天机器人。

但Loebner Prize挑战赛的评测是对图灵测试的一个扩展修改，原始的二元‘是/否’决定被排名所取代，在该排名中，人工评价者按照‘类人’程度对聊天机器人进行排名，而且未指定绝对的‘类人’程度阈值。

Cohen在文章《If not the Turning test, then what?》中描述了很多针对机器人的差异智能测试，这些测试中的大部分都需要具有强大的理解，操作和产生语言背后概念的能力。这些能力被认为对证明人类智力很重要，但是是否与聊天机器人的自然性评价相关还值得怀疑。

但是，科恩提出的‘一个好的挑战的标准’完全符合此处提出的研究目标：

1. 必须能够产生反馈,要比图灵测试的‘是否’结果更加充分
2. 必须具有单调性，允许重复挑战以验证先前挑战的结果
3. 必须‘吸引研究界的心和思想’

玻璃盒评价（glass box）从技术上对给定对话的语法，句法，句子结构和答案是否适当进行评价，黑盒评价（black box）广泛尝试评价用户满意度。但这两种方法并不是很适合聊天机器人的评价。应该从功能上定义聊天机器人的成功：“最佳评估取决于它是否实现了该服务或任务”，但是聊天机器人不再主要用于基于工作的任务，而仅仅是为了成为有趣的对话伙伴，那么应该怎么办呢？

Semeraro等使用一种自上而下的方法来评估其基于代理的接口，构建了一个调查表，评估了聊天机器人的学习和帮助用户的能力，其理解能力，导航的便利性，有效性，印象和命令。但这是一种主观的方法。

还可以使用类似1-10评分系统来评价自然性和继续对话的技术能力，表示为‘自然性’和‘持续对话的意愿’。

但是，这些方法的问题在于，用于测试聊天机器人的量表和问卷本身并未被普通用户验证为足够，并且缺乏作为测量工具的可靠性和有效性。

### 2 研究1：用用户的话 In the Words of the Users

这项研究使用了一个以ELIZA方案为模型的聊天机器人，它包含三层：

- 第1层：在给定主题上保持交流，其中标记（token）与类型相关联，而类型与其他类型相关联；
- 第2层：用于查找新主题并转换至新主题的交换代理程序；
- 第3层：通用社交控制：阶段性会话标记（tokens）

在实验中14名参与者与上边提到的聊天机器人进行三分钟的交流。交流结束后，参与者需要将对话记录中最不寻常的三个对话标记出来并解释为什么，以及三个最使人信服的三个对话标记出来并解释。（关键事件技术 critical incident technique）。

通过内容分析了上边产生的数据，共有三名评估者参加。第一名评估者审阅用户回复，并将用户回复（user response）归到特定的主题（specific theme)(没有先验创建主题)。由第二名评估者进行交叉验证。评估者之间的可靠性约为0.53，比较低，但没有更适合的方法。对存在分歧的项目进行了讨论，并在第三位独立评估者的主持下将其置于相互同意的类别中。

用户确定的主题中出现了令人放心的对称性。 例如，是否令人信服：保持主题令人信服，而没有做到则令人信服； 口语或会话式英语令人信服，而正式或不寻常的语言则相反。 对提示做出适当的反应是类人的，而对提示做出的反应则不是。 在不适当的时间提供意想不到的短语不会给人留下深刻印象，但损害控制可以纠正这种情况。

一共提取了7个主题，它们是：

1.  保持主题 Maintenance of themes
2.  回应特定问题 Responding to a specific question 
3.  回应社交线索 Responding to social cues 
4. 使用适当的语言记录 Using appropriate linguistic register 
5. 问候和个性 Greetings and personality 
6. 给予对话线索 Giving conversational cues 
7. 不当言语和损害控制 Inappropriate utterances and damage control

但是，没有迹象表明聊天机器人会感知到失败对话的相对严重性。 换句话说，很难说出用户是否认为聊天机器人无法保持对话主题比在对话过程中传达不适当的言论更为严重。

 ### 3 研究2：量化  Towards Quantification
针对上边提取的7个主题，每个主题提出4个问题，制作出一份问卷。12名研究者和研究生对问卷进行了审核，最终问卷由23个问题组成，每个主题由2-4个问题进行衡量。

问题的答案为五点频率量表：“总是”，“经常”，“有时”，“很少”和“从不”，问卷最后有一个开放式问题：“您认为这个聊天机器人最擅长什么？”

20名参与者与‘Chatterbox’挑战赛中获胜的5个聊天机器人和失败的5个聊天机器人进行交流5分钟，然后填写问卷。

使用主成分分析（PCA），得到四个因素：
- 尽职尽责 Conscientiousness 是最大的因素，由十个问题组成，这些问题衡量聊天机器人如何保持对话主题以及其响应的适当程度。
- 礼节 Manner 是第二个因素，由6个问题组成，评估了聊天机器人显示礼貌行为和交谈习惯的能力。 问候，道歉，社交礼貌和介绍是在此因素范围内衡量的结构。
- 彻底性 Thoroughness，由4个问题组成，用于测量聊天机器人的正式语法和句法能力。
- 原创性 Originality，它由三个问题组成，这些问题衡量了聊天机器人产生原始材料的能力以及在对话中主动出击的能力。

彻底性是区分聊天机器人好坏的最大因素。

开放式问题“您认为这个聊天机器人最擅长什么？”被编码用于内容分析。数据中共有四个突出主题：
- 问与答 Asking and Answering：这里强调了用户和聊天机器人之间的对话的互动性。
- 原创性 Originality：用户经常指出某些聊天机器人响应的原创性（或缺乏原创性）。
- 个性 Personality：参与者经常将聊天机器人称为具有“个性”：聊天机器人话语中的举止和礼貌问题是一个又一次出现的问题。
- 与用户的关系 Relationship with User：一个有趣的主题，可能表明聊天机器人和用户之间存在某种主体间的感觉。

### 4 结合结果和下一步 Combining the Results and the Next Step
最终步骤是通过添加第二项研究的内容分析的因素对23个问题进行修订。

用户可以根据PCA得到的四个方面来判断聊天机器人的自然性。这些可能在某种程度上是相互关联的，
因此在一个方面表现出色的聊天机器人也将在另一个或多个方面表现出色。
- 聊天机器人应该认真负责 A Chatbot should be Conscientious。 它应该能够跟踪对话，关注对话流程，维护主题，获取适当的提示以及提出并回答相关问题。
- 聊天机器人应显示原创性 A Chatbot should Display Originality。 它应该具有一些有关会话主题的有趣信息，并且应该能够在对话中主动出击，可以通过建议更改相关主题。
- 聊天机器人应显示礼节 A Chatbot should Display Manners。 它应该表明它具有良好的会话习惯，如果会话偏离正轨，可以进行损害控制，并且应该保持适当的（也许是友好的）个性并与用户建立联系。
- 聊天机器人应该彻底 A Chatbot should be Thorough。 它应该使用一致的适当的语法和拼写，并与用户采用一致的适当的语言。












> Morrissey, K., & Kirakowski, J. (2013, July). ‘Realness’ in Chatbots: Establishing Quantifiable Criteria. In International Conference on Human-Computer Interaction (pp. 87-96). Springer Berlin Heidelberg
