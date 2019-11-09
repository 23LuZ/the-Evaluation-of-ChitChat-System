## Survey on Evaluation Methods for Dialogue Systems

### 简介 Introduction
- 高质量对话的定义并不是很明确，通常取决于应用，即使假设了一个定义，也不是很明确应该如何衡量，评价。
比如，假设一个高质量的对话系统就是能够产生合理的回复，但是不清楚该怎样衡量回复的合理性或者合理性到底意味着什么
- 到现在，提出了很多自动评价方法，但是这些评价方法通常跟它们要评价的对话系统的质量属性有关。
- 自动评价方法的目标是自动化和可重复性，并且跟人类的评价具有很高的相关性，以便对不同的对话系统进行评价，并且解释出对话系统的哪些特征与质量相关

### 评价 Evaluation
自动评价方法的要求：
- 自动的 Automatic
- 可重复性 Repeatable
- 与人类评价相关 Correlated to human judgments
- 区分不用的对话系统 Differentiate between different dialogue systems
- 可解释性 Explainable

人工评价 Human Evaluation 的人群来自：Lab-experiments，In-field experiments（使用对话系统的用户），Crowd-sourcing

人工评价需要考虑很多因素：需要正确指导用户，需要准备任务，以使实验接近真实条件。 此外，需要考虑到用户行为的高度可变性，

自动评价方法分为：
- 对人类评分进行建模 model the human rating：需要收集人类对对话的评价数据 
- 对用户行为进行建模 model the user behaviour：模拟人类行为
- 细粒度方法 finer-grained methods：对对话系统的某一个方面进行评价 

### 闲聊系统
#### 评价方法 Evaluation methods
对闲聊系统进行评价的两个常用方法是评价回复的合理性 appropriateness，或者类人性 human likeness。
但这两个方法都是粗粒度的 coarse-grained。针对特定的系统的特定特征，细粒度fine-grained的方法应该被应用。比如提高回复的多样性，应测量词汇复杂度

#### 通用评价指标 General metrics
对话系统的评价分为两个层次：粗粒度的 coarse-grained evaluation，细粒度的 fine-grained evaluation

粗粒度评估集中在对话系统生成或选择的响应是否充分。 另一方面，细化的评估集中在其行为的特定方面。 
粗粒度的评估基于两个概念：响应的充分性（或适当性）和与人的相似性。 
细粒度的评估集中于对话系统应表现出的特定行为。 在这里，我们重点介绍为保持连贯性coherence 而设计的方法以及保持对话主题的能力。

合理性 Appropriateness 封装了许多更细粒度的概念如连贯性，相关性或正确性
- word-overlap metrics
- model based methods

类人性 Human Likeness
- 图灵测试，对抗学习

细粒度评价指标 Fine-grained metrics
- topic-based evaluation  DAN topic breadth, topic depth
