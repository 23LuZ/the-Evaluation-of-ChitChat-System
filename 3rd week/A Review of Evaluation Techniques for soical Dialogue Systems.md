### A Review of Evaluation Techniques for soical Dialogue Systems
#### 摘要 Abstract
社交对话系统的评估具有很大的挑战性，因为成功的社交对话系统的定义不是很明确，而且如何衡量社交对话系统的成功也不是很明确。（任务不明确，评价指标不明确）。

通用的方法是使用人工评价，但使用人工评价有很多的缺点：
- 评价人员具有主观性
- 费时费力，花费多
- 需要精心设计评价过程
- 无法做到及时评价模型的效果，以快速改进模型，调整模型的结构或参数

#### 自动评价指标 Automatic Metrics
人工评价的缺点恰好就是自动评价的优点，自动评价客观，快速地对模型的效果进行评价，以加速模型算法的调整。

##### 词重叠指标 Word-Overlap Metric
词重叠指标只考虑了生成回复与参考回复之间的相似性，未考虑生成回复是否是问题的合适回复，与问题之间的相关性

##### 基于机器学习方法的对话评价方法 Machine Learning Methods for Dialogue Evaluation
基于机器学习的评价方法在轮次级别（turn-level）上运行，旨在提供‘好’的响应的估计模型。
优点是相比BLEU，ROUGE更接近人类回复。缺点是此类方法对每个域都需要重新训练。

**判别模型　discriminative　Models**
这些模型的目标为区分‘好’，‘坏’回复。灵感来源于图灵测试
- 下一话语分类 NUC
- 对抗评价模型 Adversarial evaluation model

**分类模型 Classification Models**
- ADEM 回复首先由人类进行打分,然后被用来训练模型,模型预测回复的'人类评分' 

##### 基于奖励的指标 Reward-based Metrics
基于强化学习的模型应用于非任务型对话系统,可以增加回复的多样性,避免通用回复'我不知道',评价指标在这里被实现为奖励功能.

- 轮次级别的奖励 Turn-level rewards,启发式的
  - 连贯性 Coherence 连续轮次的语义相似性
  - 信息流 Information Flow 同一发言者的发言之间的语义相似性
  - 很容易回答 Ease of answering 互信息
  
在他们的实验中，他们发现RL方法在对话长度，答案的多样性和多轮对话的整体质量方面都优于其他系统。 
这表明建议的奖励功能至少成功地部分捕获了问题和回复之间的关系，这在评估潜在回复时很有用，而无需人工生成的参考。
但是，虽然轮次级别的连贯性是评估质量的关键因素，但并不一定反映对话的整体质量。

- 系统级别的奖励 System-level rewards,使用Wizard-of-OZ 实验
  - 对话深度 Conversational depth：属于同一主题的连续轮数
  - 词汇多样性/信息获取 Lexical diversity/information gain：系统和用户引入对话的唯一单词的数量
  - 总体对话时长 Overall dialogue length
 
#### 结论与讨论 Conclusion and Discussion
- 未来,自动评价方法可以涵盖从自然性和连贯性到长期的参与和交流的所有对话方面,而不是只考虑一个方面的表现
- 基于单词的度量标准（例如BLEU）忽略了可能存在许多同样有效和适当的响应的事实
- 基于回合的度量标准没有考虑通用响应的过度使用
- 系统级奖励是基于启发式的


