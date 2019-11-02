## Towards an Automatic Turing Test: Learning to Evaluate Dialogue Responses
### 摘要 Abstract
- 将自动对话评价看作是一个学习问题（learning problem），提出评价模型（ADEM）。
- ADEM将人类回复评分数据作为训练集进行训练，给定一个输入回复，学习评价输入回复的‘人类评分’（human-like scores）。
- ADEM模型预测的结果在话语级别（utterance level）和系统级别（system level）与人类判断相关性较高。
- ADEM模型能够迁移到训练期间未见到的模型。

### 简介 Introduction
- 人工评价具有很多缺点，费事，花费多，缺乏可扩展性，特殊的领域需要评价者具有特定的背景知识，无法快速地对模型效果进行评价从而促进模型的改进、效果的提升
因此，开发一个能够自动评价对话模型生成回复质量的模型很重要：自动图灵测试 automatic Turing test

- 假设一个‘好’的聊天机器人就是回复被人类评价者认为很合适（appropriateness），如果是其他的质量属性/指标，人工评价者之间的一致性会很低，
或者与‘合适性’的相关性很高。
因此，收集了一个包含‘合适性’打分的对话回复数据集，用这个数据集训练自动对话评价模型 automatic dialogue evaluation model ADEM

- 模型的训练采用的半监督方法，使用层级RNN结构预测人类打分。
- ADEM分数在话语级别和系统级别与人工分评的相关性都很高
ADEM能够扩展到评价新的模型，模型的回复在训练中没有出现过。

### 数据收集 Data Collection
- 收集人类对回复的打分，每个回复一个得分
- 回复需要多种形式，相关的、不相关的、一致的和不一致的等，使得模型能够学习比较参考回复和候选回复
- 收集了来自4个不同模型的回复：TD-IDF，DE，HRED，人类产生的回复（不是语料库中的参考回复）

#### ADEM An Automatic Dialogue Evaluation Model
设计的模型要能够：
- 捕捉语义相似性
- 利用上下文和参考回复对模型回复进行评分


RNN encoder预训练后参数固定。
ADEM不是一个检索模型，其知道参考回复，是在已知参考回复的情况下，进行评分预测

ADEM模型使用半监督的方法进行训练，首先对VHRED模型进行预训练，然后将RNN部分参数固定作为ADEM模型的RNN参数

#### 实验 Experiment
- Twitter 数据集
- 为了减小单词表大小，使用BPE，其将单词切分为字串 sub-words或者字母 character
- 人类倾向于给较短的回复打高分，因为较短的回复更加通用，因而很大可能也是合理的回复。因此，从相同分数的不同长度的回复中采样，
避免ADEM使用回复长度来预测分数
- 训练完VHRED模型后，使用PCA对上下文表示的维度进行降维降到50维

#### 结果 Result
- 话语级别的相关性 Utterance-level correlations
![]()
![]()

- 系统级别的相关性 System-level correlations
![]()
![]()

- 扩展到之前未见到的模型 Generalization to previously unseen models
![]()

- 定性分析 Qualitative Analysis
   - ADEM能够给‘坏’的回复打低分，‘好’的回复打高分
   - ADEM的缺点是打分太保守，原因在于训练ADEM的目标函数是均方误差，模型为了避免预测极值受到较大的惩罚，学会预测接近人类平均得分的评分
   
 #### 相关工作 Related work
 - RL相关工作 是在对话级别 conversation-level上对对话进行评价，无法评价单个对话回复
 - 半自动评价方法，类似BLEU，ROUGRE，评价对话的连贯性
 
 #### 讨论 Discussion
 - ADEM在Twiiter数据集上训练，也可泛化到其他数据集，未来会继续研究ADEM的域泛化能力
 - 合适性之一指标可能不能完全覆盖聊天机器人的最终目标，因此模型会受到人类给通用回复打高分的影响，可进一步改进
 - 未来研究的一个方向是建立评价模型，能够评价系统与人类进行有意义的互动的能力的模型，与单一评价指标来说，更接近聊天机器人的最终目标
