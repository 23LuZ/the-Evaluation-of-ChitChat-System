### Framework for the Formulation of Metrics for Conversational Agent Evaluation

#### 摘要 Abstract
最初对话系统的评估面临的挑战是制定需要捕获和度量的指标，以评估特定的对话系统。

本文介绍了一个新框架，该框架已用于制定指标并对两个不同领域的对话系统进行了评估。

#### 简介 Introduction 
软件质量模型应用于对话系统的评估。质量定义为系统，组件或过程满足客户或用户需求或期望的程度。

软件质量主要是根据满足要求的程度（例如正确性，可靠性和可用性）来衡量的。 影响质量的因素称为质量属性或度量（quality attributes or metrics）。 
质量指标有不同的分类。质量指标可以分为两大类：可以直接衡量的指标（例如性能 performance）和可以间接衡量的指标（例如可用性 usability）。 
这些度量可以分别转换为客观度量和主观度。

对对话系统的评估必须适合各个应用领域的目标。 因此，无法将评估指标归纳为“一刀切”（one size fits all）的评估框架。现有框架的弱点在于，
它们无法识别需要评估的各个评估指标，而这些指标每个对话代理都是不同的。

#### 背景 Background
##### 对话代理 Conversational Agents
对话代理的本质是人类与计算机上运行的应用程序进行自然语言对话。应用人工智能技术已应用于多种领域如引导销售，教育等。

##### 对话代理的评估 Conversation Agent Evaluation
Walker等人提出PARADISE框架进行口语系统的评估。

Moller提出了质量标准分类法。 他们将质量描述为两个独立的问题，包括服务质量和体验质量。 服务质量描述了客观标准，
例如达到理想结果的对话持续时间，轮次。 
虽然这些是定义明确的项目，可以轻松确定，但是以主观标准描述用户体验的“体验质量”是一个较为模糊的领域，并且没有明确的定义，例如 用户满意度。

Artstein对交互式软件质量的评估分为两个不同的类别，即“务实质量”和“享乐质量”。 务实质量与以任务为导向的质量有关，例如任务完成的有效性和效率。 
享乐的质量与非任务导向的方面有关，例如审美印象和用户刺激。 这两个类别可以分别转换为客观度量和主观度量.

从早期到今天，该领域研究人员的普遍共识是，“可用性”是CA中最重要的性能指标.应通过主观和客观措施相结合来评估CA / Dialogue系统的有效性

由于多年来CA评估框架尚未正式开发，因此可以采用的替代方案是软件评估框架主要用于评估新软件的功能和可用性（即客观和主观）。

#### 针对多种目标的对话代理评价框架 Novel Framework for the Formulation of Evaluation Metrics Suited to Individual CA Goals
与任何工程学科一样，软件开发需要一种用于反馈和评估的测量机制。

目标问题指标 Goal Question Metrics GQM 方法：要对系统进行评估，必须首先确定系统的目标，然后可以将这些目标追溯到以下问题：
旨在从业务上回答这些目标。 最后，提供一些可衡量指标来回答所述目标的问题。
因此，重要的是至少要从总体上讲清楚每个CA的目标是什么，以便可以在可能的情况下对这些目标进行量化，并且可以对量化的信息进行分析，以了解是否达到了目标。
- 目标-列出系统的主要目标。
- 问题-从每个目标中得出必须回答的问题，以确定是否达到目标。
- 指标：确定必须测量的内容才能充分回答问题。 一组度量标准与每个问题相关联，以便以定量方式回答。
指标可以分为两类：客观的和主观的

GQM模型是如下图所示的自上而下的层次模型，顶层从目标（指定测量目的，要测量的对象，要测量的问题以及采取测量的观点）开始。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/GQM%20Model.PNG?raw=true)

将目标细化为几个问题。 每个问题都是一个度量标准，其中一些是客观的，一些是主观的。 
为了回答同一目标下的不同问题，可以使用相同的度量标准

这个新的CA评估框架被用于评估两个新型对话代理系统UMAIR(客户服务 customer service)和Abdullah CITS（online tutor）.

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/UMAIR%20GQM%20Diagram2.PNG?raw=true)

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Abdullah%20CITS%20GQM%20Diagram2.PNG?raw=true)

#### 讨论与总结 Discussion and Conclusion 
使用GQM方法可以根据不同对话代理的应用目标选择不同的度量指标，标准化整个流程。
