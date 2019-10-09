## Evaluating Quality of Chatbots and Intelligent Conversational Agents ##

## 摘要 ##
聊天机器人除了能够增强用户体验、支持学习，还可能造成社会危害--散布谣言和错误信息，攻击他人在网上发布的观点和看法。

本文
- 介绍了与聊天机器人开发和实施有关的问题--质量问题和属性（quality issues and attributes）。

- 并对质量评估方法（quality assessment approaches）进行了回顾。

- 基于质量属性和层次分析法（Analytic Hierarchy Process-AHP）提出了一个质量评估方法。

## 简介 ##
从2007年到2015年，聊天机器人参与了所有在线互动的三分之一到二分之一，并且随着新聊天机器人的应用，这一比例还在不断增长。

聊天机器人对于公司来说是有用处的：减少回复的时间、提供增强的用户服务、增加用户的满意度和增加对用户的吸引力。

但有一些设计的聊天机器人是有害的，比如，Twitter上的僵尸粉丝，增加购买僵尸粉丝的用户的粉丝数，被用来传播虚假新闻和谣言，并且攻击表达自己观点的用户。

由于聊天机器人的灵活性和易用性（与基于网页的应用程序或移动应用程序相比）聊天机器人可能会成为通用的用户接口，并且代替应用程序apps。
此外，聊天机器人也可能成为虚拟现实（VR）环境中的重要接口。

因此，明确发展和实现高质量聊天机器人的质量属性（quality attribute），并且根据这些属性确定质量保证（quality assurance）的机制是很重要的。

## 背景 ##
聊天机器人的发展起源于图灵测试，聊天机器人的发展目标就是通过图灵测试。

最早的聊天机器人是1955年的ELIZA，其扮演的角色为心理医生。使用的技术为简单的关键词匹配。

19实际80年代，ALICE诞生，ALICE使用人工智能标记语言（Artifical Intelligence Markup Language(AIML)）进行编写。

聊天机器人是对话代理（conversational agents）的一种,对话代理是对话系统（dialog system）的一类。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Relationships%20between%20classes%20of%20software-based%20dialog%20systems.PNG?raw=true)

## 方法 ##
本文通过查阅工业界和学术界的文献
- 提供聊天机器人和对话代理的质量属性
- 确定合适的质量保证方法

## 质量属性 ##
从筛选出的32篇论文和10篇文章中可提取出质量属性，根据相似性聚类发现，他们与ISO 9214的可用性概念很相似。

可用性（usability）概念为：特定用户在特定环境中实现特定目标的有效性（effectiveness），效率（efficiency）和满意度（satisfaction）。

特别的：
- 有效性（effectiveness）：特定用户实现其目标的准确性（accuracy）和完整性（completeness）。
- 效率（efficiency）：充分利用资源实现目标。
- 满意度（satisfaction）：用户是否满意。

下表概述了根据ISO 9214组织的质量属性

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/efficiency.PNG?raw=true)
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/effectiveness.PNG?raw=true)
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/effectiveness2.PNG?raw=true)
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/satisfaction.PNG?raw=true)
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/satisfaction2.PNG?raw=true)

## 质量评估（Quality Assessment） ##

### 之前的方法 ###
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Quality%20assessment%20approaches.PNG?raw=true)
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Quality%20assessment%20approaches2.PNG?raw=true)
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Quality%20assessment%20approaches3.PNG?raw=true)
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Quality%20assessment%20approaches4.PNG?raw=true)

如果这些指标与列出的质量属性的综合分类列表中的各个元素相关联，
则可以在确定优先级和向下选择过程之后使用分析层次结构（AHP）来完成两个或多个聊天机器人的比较

### 综合方法：层次分析法 ###
层次分析法是一种结构化方法，可用于涉及定量和定性考虑因素的复杂决策过程。
1. 创建质量属性的层次化结构，并选择能够表示这些属性的指标。
2. 在一个或多个产品的质量属性之间进行成对比较。
3. 创建比较矩阵并计算每个矩阵的第一个主特征向量，以评估相对优先级和全局优先级。
4. 结合优先级并计算不一致因素，以确定哪个产品最能满足质量属性的层次结构。

假设在过去一年中，对一个聊天机器人进行了升级，想查看聊天机器人的质量是否提高了：
查看最重要的质量属性是哪些，并选择质量评估指标。下图是一个例子：
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/AHP%20example.PNG?raw=true)
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/AHP%20example2.PNG?raw=true)

AHP在类别之间和类别内使用成对评估,首先要建立属性的层次结构，如下图所示，顶层是目标，第二层是质量属性类别，第三层是质量属性，最后一层是被展示的选项。
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Hierarchical%20model%20of%20prioritized%20quality%20attributes.PNG?raw=true)

第一步是类间的成对比较。在AHP中，只有数字1，3，5，9被使用。
创建一个矩阵，每一个元素代表每行的类别相比于每列的类别有多重要。如果列的类别更重要，记录一个倒数。
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Priority%20matrix%20for%20quality%20categories.PNG?raw=true)

第二步进行类内的比较。
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Priority%20matrix%20for%20selected%20%E2%80%9CHumanity%E2%80%9D%20quality%20attributes.PNG?raw=true)

第三步使用测量值（在表3的“旧”和“新”列中）比较聊天机器人的不同版本在每个质量属性方面的表现
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Priority%20matrix%20for%20selected%20%E2%80%9CEscalation%E2%80%9D%20quality%20attribute.PNG?raw=true)

计算完成后，假设某些属性更重要，而另一些属性不那么重要，则结果可帮助选择最能满足质量属性的方案。最终结果为下图：
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/AHP%20results%20for%20the%20example%20problem.PNG?raw=true)

## 结论 ##
本文通过调研文献，1）收集和阐明聊天机器人和对话代理的质量属性，以及2）发现并综合质量保证方法

本文中的很多材料都可以被应用：
- 质量属性可用作聊天机器人团队的清单，以确保他们已解决关键问题。
- 通过选择最重要的质量属性，可以比较两个或多个会话系统。
- 可以在两个时间点对系统进行比较，以查看质量是否有所提高。

最后提出层次分析法，并给出示例。该示例说明了如何使用这种面向目标的方法来评估两种不同的聊天机器人实现的质量。


