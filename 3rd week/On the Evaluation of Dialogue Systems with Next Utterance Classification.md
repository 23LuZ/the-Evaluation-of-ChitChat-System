### On the Evaluation of Dialogue Systems with Next Utterance Classification

#### 摘要 Abstract
最近的工作提出了将下一个话语分类（NUC）作为替代任务，以根据文本数据构建对话系统。

在本文中，我们调查了人类在此任务上的表现，以验证NUC作为评估方法的相关性
- 人类能够以超过猜测的概率（chance）对回复进行分类，从而确认任务是可行的
- 人类的分类水平根据任务域和专业知识水平而变化，因此在这种类型的任务上可以产生一系列不同的表现
- 使用最新的机器学习方法构建的自动对话系统具有与人类新手相似的性能，但比专家更差，因此证实了此类任务在推动自动对话系统进一步研究的实用性

#### 简介 Introduction
非监督系统（unsupervised system）可分为基于生成的系统（response generation system）和基于检索的系统（retrievel-based system）

基于检索的系统能够应用评价指标：recall，precision。最初由Schatzmann等人介绍，用于评估用户仿真（user simulation）。 
最近这种框架在端到端对话系统的评估中获得了关注。 
这些模型接受了从候选列表中选择正确响应的任务的训练，我们称其为“下一个话语分类”，并使用了recall进行评估。 

NUC很有用处的原因有：
- 表现（损失或错误率）很容易计算
- 调整任务的难度很简单，可以改变回复列表中回复的个数，可以改变错误回复的选择标准：随机或有意选择迷惑的回复
- 任务是可以解释的，而且可以跟人类的表现进行比较
- 与训练端到端的生成模型相比，这是一项更轻松的任务
- 进行NUC训练的模型可以通过从全语料库检索转换为对话系统

因此，NUC既可以看作是中间任务（intermediate task），可以用来评估系统理解自然语言对话的能力，也可以是构建聊天机器人的有用框架。

在本文中，我们考虑了人类在多大程度上可以实现NUC，人类的表现是否根据专业知识而有所不同，
机器性能是否有提高的空间（或已经达到人类的表现），我们应该着手进行更复杂的对话任务 。

#### NUC的技术背景 Technical Background on NUC
下一个话语分类（NUC）是一项任务，它很容易评估，专为对话系统的训练和验证而设计。 

在NUC任务中，模型或用户需要从回复列表中选出最合适的回复。该列表中包含参考回复，随机从语料库中采样其他回复（很可能也有正确回复）。

使用Recall@k（模型在排名最高的前k个响应中找到的正确响应的百分比）对它们进行评估。

#### 调查方法 Survey Methodology
- 语料：SubTle Corpus,Twitter Corpus,Ubuntu Dialogue Corpus
- 参与者：众包平台雇佣的145个参与者，计算机学院的8个志愿者
- 任务：人类参与者和ANN模型分别对从语料库中抽取形成NUC问答对进行NUC任务
- ANN模型：双编码器模型 Dual Encoder DE model.回复r是上下文c的真实下一句的概率是$P(r \ is \ correct \ response )=\sigmoid(c^TMr)$

#### 结果 Result
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Average%20results%20on%20each%20corpus.PNG?raw=true)

#### 讨论 Discussion
人类在“下一个话语分类”任务上的表现优于当前的对话模型，这表明这些模型有很大的改进空间，可以更好地理解人类对话的本质。

使用尽可能多的相关指标来自动评估对话系统。 应该进行进一步的研究，以发现能够准确反映对话系统性能的指标或任务
