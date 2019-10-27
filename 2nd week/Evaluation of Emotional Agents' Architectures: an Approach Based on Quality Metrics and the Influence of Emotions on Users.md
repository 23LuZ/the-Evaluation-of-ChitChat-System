### Evaluation of Emotional Agents' Architectures: an Approach Based on Quality Metrics and the Influence of Emotions on Users
- 满意 Satisfaction - 情感 Affect
读懂并回应参与者的情绪 Read and respond to moods of human participant

#### 摘要 Abstract
在开发的早期阶段，需要确定系统的质量。代理（agents）的体系结构（architectures）也是系统的一部分，因此也需要对其质量进行评估。

情感在我们的日常生活中扮演着重要的角色，因此研究者们提出了一些具有情感的对话系统。

本文的主要目的是：
- 提出一种评估具有情感的对话系统的方法
- 该方法不仅评估架构设计的质量属性
- 还对使用该系统的用户的主观体验进行评估

在评估架构设计的质量时，评估的质量属性有：可扩展性（extensibility），模块化（modularity）和复杂性（complexity）。

在评估对用户主观体验的影响时，选择在计算机游戏领域进行评估，选择的指标有：娱乐（enjoyment），感觉支持（felt support），温暖（warm），关怀（caring），
信任（trust），合作（cooperation），智慧（intelligence），趣味性（interestingness），情绪反应的自然性（naturalness of emotional reactions),
可信度（believability）,减少沮丧感（reducing of frustration），喜爱（likeability）以及平均时间（average time）和平均尝试次数（average attempts）

我们已经试验了我们的方法，并评估了五个具有情感的对话系统的体系结构：BDIE，DETT，Camurri-Coglio，EBDI和Emotional-BDI。


### 简介 Introduction
情感被认为是更加有效的人机交互（HCI）的关键要素。开发具有情感的对话系统已经成为工业界和学术界的共同主题。

体系结构对软件系统的质量有很大的影响，在大型软件系统中，诸如性能，安全性和可变性之类的软件质量属性不仅取决于代码级实践（code level），
而且还取决于整个软件体系结构。

本文提出的方法是基于目标定义明确的度量模型，评估体系结构的质量属性以及用户与具有情感的对话系统交互的影响

### 度量对话系统体系结构的方法 Methods for Measuring Agents' Architectures
#### A. 分析和实验评估方法 Analytical and Experimental Evaluation Methods
- 分析方法 Analytical Methods
数学评估方法具有结果确定性优势，但是也有缺点，系统若过于复杂，那么会产生难以处理的数学模型
- 实验方法 Experimental Methods
实验评估方法测量特定系统运行的特定实例的属性。最后，通过对概念设计和基于观测的系统的性能之间的一般关系进行归纳推断，
将结果用作证明或反对某些结论的证据。

#### B. 评估对话系统的体系架构 Evaluation of Agents' Architectures
功能和架构属性的比较依赖域（domain），因此，Hexmoor着重于对架构本身的质量进行实证评估，开发独立于领域的指标。

GQM度量模型具有三个级别：概念（conceptual），操作（operational）和定量(quantitative)三个级别，分别涉及目标，问题和度量方法。
这项研究也采用了GQM范式。

#### C. 评估具有感情的对话系统 Evaluating of Emotional Agents
从Beale和Creed的这次调查的比较表中(仅接受那些最重要的研究)，选择了显示出积极结果的十二个指标， 这些度量指标与评估模拟情绪对用户主观体验的影响有关。

### 评估情感对话系统的方法
#### A. 提出的方法 Proposed Model
在表I中，我们将用于评估体系结构的度量标准模型概括为三个级别，在该模型中，我们可以从两个评估目标中跟踪用于回答和评估的四个问题的度量标准，
确定目标是否实现。 在表I的第一列中，我们放置了在评估情感代理的体系结构中必不可少的目标：
- 评估架构设计的质量；
- 结合对话系统评估人机交互

在第二列中，我们编写了源于目标的问题，而在第三列中，则是负责回答每个评估问题的度量指标。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/MEASUREMENT%20MODEL.PNG?raw=true)

#### B. 评估步骤 Evaluation Steps
##### 质量属性评估 Quality Attributes Evaluation
可扩展性指标有助于验证体系结构是否设计为利用新技能扩展或改进它们，而无需对其基础结构进行重大更改。 
该指标与模块和组件的概念密切相关。

对于模块化，其度量标准有助于验证模块是否可以彼此分离并重组而无需花费大量成本。

复杂性具有几个度量标准，这些度量涉及体系结构元素之间的关系，元素的数量模块（例如知识元素，组件和实例）以及元素的总数（例如大小）。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/METRICS.PNG?raw=true)

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/OTHER%20METRICS.PNG?raw=true)

对质量属性的评估如下：
- 架构模型分析 Analysis of architectural models：对架构的模型和图表进行初步分析，以识别和计数所有模块，组件，模块之间的通信，架构服务和知识元素；
- 评估可扩展性 extensibility：对于每种体系结构，计算Cha和Cp，求解方程式（1）和（2）；
- 评估模块性 modularity：对于每种架构，计算Cha和Cp，求解方程式（1）和（2），还计算Fi和；
- 评估复杂度 complexity：对于每种架构，计算ACmM，ASM，AKM，ACM和Sz；
- 架构排序：为了使用上面计算的指标比较架构，我们应该计算所有指标的算术平均值，然后对架构按照平均值进行排序；
- 质量属性分析：为了比较所有架构并发现最佳的架构设计

在对架构进行排序时，水平条形图对于进行比较非常有用，将架构名称作为纵坐标，并将计算出的度量值放在横坐标上。可以考虑架构相对于平均值的位置对纵坐标值进行排序。
它应该为每个指标绘制一个图表。例如，这使您更容易查看哪种架构具有最高的内聚性或最低的耦合。

#### 评估人机交互 Computer-Human Interaction Evaluation
参与者与具有感情的对话系统进行交互，并表达主观感受。根据收集到的数据，对系统进行分析。
人机评估的评估如下：
- 设计应用 Design applications：（i）首先选择一个领域，我们建议游戏，因为当前游戏角色的丰富性和复杂性； 
（ii）为对话系统使用特定的方法和开发平台，我们建议分别使用Prometheus和JADEX； 
（iii）定义情感代理将使用的“情感表达”； （iv）最后，实施带有情感代理的一个应用和没有情感代理的第二个应用；
- 准备调查表 Prepare questionnaires：在使用应用程序之前准备第一份问卷以验证用户的情感表达，
在使用该应用程序后准备第二份问卷以供回答，其问题涉及参与者的主观体验的度量指标；
- 定义和组织人口 Define and organize the population：（i）考虑地理位置选择人口，平衡男女人数，并且参加者的年龄范围不要太大
（ii）将人群分为两类：一组用于与情感代理互动，而另一组则与没有情感的代理互动；
- 验证对情感表达的理解 Validate the understanding of emotional expressions：发放第一份问卷；
- 进行实验和应用问卷 Perform Experiments and Apply Questionnaires：使人群与对话系统进行互动； 除了与情感代理互动的主观用户体验数据外，
还应收集用户表现信息并将其记录在同一问卷中；
- 分析情感表达验证的结果 Analyze results of emotional expressions validation：数据分析应着重于每个情感表达的错误率和识别命中率，
这种验证的结果可以确认所用情感表达的问题，例如，悲伤和担忧表达之间的混淆；
- 分析主观经验的结果 Analyze results of subjective experience：基于第二份问卷答案，关于参与者的主观经验，结果的分析可分为两个阶段：
（i）主观变量的分析； （ii）分析情感因素对游戏容易程度和困难程度中用户表现变量的影响。

### 结论 Conclusion
这项工作中提出的方法主要是为情感代理的架构设计者和涉及情感代理的应用程序开发人员提供的。 
应用程序开发人员现在可以具有客观的标准来分析和选择最有助于实现所需质量的体系结构。 
情感主体架构的设计者现在可以使用我们提出的指标来验证和确认自己的架构。



