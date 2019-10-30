### RUBER: An Unsuperised Method for Automatic Evaluation of Open-Domain Dialog SyStems

#### 摘要 Abstract
- 提出一种自动评价方法 RUBER：a Referenced metric and Unreferenced metric Blended Evaluation Routine.
- 在评价时既考虑标准答案(groundtruth reply),也考虑问题（query，先前用户的话语 previous user-issued utterance）
- 评价方法需要训练，但是不需要标签
- RUBER可以灵活地扩展到不同的数据集和语言
- 实验证明RUBER在生成模型和检索模型中的评价结果与人工评价有很高的相关性

#### 简介 Introduction
RUBER具有一些特性：
- referenced metric 基于词向量的评分器测量生成回复与标准回复的相似度
- unreferenced metric 基于神经网络的评分器测量生成回复与问题之间的相关性，应用了负采样（negative sampling）训练网络
- combine referenced and unreferenced metric 生成回复与标准回复很相像意味着高质量，但生成回复与标准回复差别很大也有可能是正确回复，因此生成回复
与问题之间的相关性可以提供一些额外信息。启发性地将两个评分器结合起来。
- 不需要人工评分数据，因此方法是非监督的（unsupervised）
- RUBER的评价结果与人工评价结果的Pearson和Spearman系数要比自动评价方法评价结果与人工评价的高
- 在一个领域训练的RUBER模型可以直接迁移到另一个领域而无需重新训练

#### 经验观察 Empirical Observations
考虑一个问题：‘What makes a good reply in open-domain dialog systems?’ 在开放领域对话系统中，怎么样算一个好的回复？
- 观察1：与标准回复相像意味着一个好的回复。这种假设也是采用词重叠评价方法BLEU，MENTOR的原因。但是也有很多正确回复不仅与标准回复没有相同的字，词语，
而且甚至语义也不相关。所以词重叠评价方法的结果就会有很大的方差。所以本文采用基于词向量的相似度测量方法。
- 观察2：在对话中，一个问题的正确回复会有很多种。此外，标准回复可能很通用如‘我不知道’。因此，只考虑标准回复不足以评价生成回复的质量。
- 观察3：在对话中，问题也包含很多信息可以用来评价生成回复的质量，生成回复与问题越相关代表着生成回复的质量越高。

#### 方法 Methodology

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/RUBER.PNG?raw=true)

##### Referenced Metric
使用向量池化方法（vector pooling approach）：分别取单词向量每个维度的最大值和最小值，然后拼接起来作为句子最后的表示。

得到生成回复和标准回复的向量表示后，使用余弦向量计算相似度。

$$ v_{max}[i]=max{w_1[i],w_2[i],...,w_n[i]} $$

$$ v=[v_{max};v_{min}] $$

$$ s_R(r,\hat r)=cos(v_r,v_{\hat r}) $$

与vector extreme的区别在于vector extreme每一维度取绝对值最大的值，没有考虑符号的特征。

##### Unreferenced Metric
使用神经网络捕获生成回复与问题之间的语义相关性。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/unreferenced%20score.PNG?raw=true)

- 问题和生成回复中的每个字都被映射为词向量
- 通过双向GRU得到问题和生成回复的语义表示
- 计算‘quadratic feature’（二次特征）
- 将问题，二次特征和生成回复的向量表示拼接起来
- 拼接的向量首先通过非线性激活函数tanh，最后通过非线性激活函数sigmiod，将输出固定在0-1之间

采用负采样训练模型，目标函数为：
$$ J = max{0,\Delta - S_U(q,r) + S_R(q,r^-)} $$

##### Hybird Approach
使用启发式策略：
- 将每个评分器的打分归一化到（0，1）
$$ \hat s = \frac{s-min(s^')}{max(s^')-min(s^')} $$
- 最小，最大，几何平均和算术平均min, max, geometric averaging, and arithmetic averaging，每种策略产生的结果相近，都优于其他方法

#### 实验 Experiments
##### 设定 Setup
训练集为豆瓣语料，包含1449218个问答对。词向量为在豆瓣语料训练的50维向量。

被评价的对话模型为检索模型feature-based retrieval-and-reranking system和生成模型Seq2Seq with Attention

9名志愿者对模型产生的回复进行打分，打分标准为2-好，1-一般，0-不好

##### 定量分析 Qantitative Analysis

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Correlation%20between%20automatic%20metrics%20and%20human%20annotation.PNG?raw=true)

##### 定性分析 Qualitative Analysis

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Score%20correlation%20of%20the%20retrieval%20dialog%20system.PNG?raw=true)

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Score%20correlation%20of%20the%20generative%20dialog%20system.PNG?raw=true)

#### 案例分析 Case Study

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Case%20study.PNG?raw=true)

#### 迁移 Transferability
将模型直接迁移到贴吧语料。虽然性能轻微下降，但是也优于其他方法。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Correlation%20between%20automatic%20metrics%20and%20human%20annotation%20in%20the%20transfer%20setting.PNG?raw=true)

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Score%20correlation%20of%20the%20generative%20dialog%20system%20%20in%20the%20transfer%20setting.PNG?raw=true)

### 相关工作 Related Work
entropy：使用熵来衡量生成回复的信息，这种度量标准独立于问题和标准回复

### 结论 Conclusion
RUBER是针对单轮对话的评价，但可以扩展到多轮对话：修改Unreferenced Metrics中的神经网络，将上下文的信息考虑进去。
