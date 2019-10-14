## How NOT To Evaluate Your Dialogue System: An Empirical Study of Unsupervised Evaluation Metrics for Dialogue Response Generation ##
## 摘要Abstaract ##
- 回复生成的评价方式目前都是从其他NLP任务中借鉴的如机器翻译任务.
- 从机器翻译任务借鉴的评价指标跟人类判断的相关性很低.
- 根据定量和定性的结果指出现在正在应用的评价指标的缺点.
- 对未来评价指标的发展提出了建议.

## 简介 Introduction ##
对话回复生成系统中一个重要的话题是如何评价生成回复的质量.  
通常,在以任务为中心的对话中评价是使用人工标注的监督标签完成的,如任务完成测试.  
这种以监督的目标优化的模型成为监督的对话模型,其他为非监督的对话模型.  
本文专注于非监督的对话模型如聊天机器人,然而非监督对话模型的自动评价仍然是一个开放问题.  
机器翻译领域的BLEU,METEOR和自动摘要生成领域的ROUGE被借鉴迁移到对话领域.但是应用这些指标的一个重要假设是生成的回复与标准回复具有重叠的单词.
但是有效的回复不只有一个,就有可能模型生成的回复与标准回复没有重叠的部分,甚至连语义也不相似.  
对词重叠评价指标和词向量评价指标与人类评价的相关性进行了研究,发现他们之间的相关性很低.  
对话系统领域需要一个与人类评价具有很强相关性的自动评价指标.

## 相关工作 Related Work ##
本文关注与模型无关的指标,即生成回复的模型不评价回复的质量.因此不介绍困惑度.  
本文只考虑对比生成回复与标准回复的评价指标,因此不考虑基于检索的指标如召回率和准确率.  
一些工作应用了BLEU,deltaBLEU对对话系统进行评价.但即使可以参考的正确回复有很多,BLEU的相关性与人类评价也不是很强.

## 评价指标 Evaluation Metrics ##
本文专注于比较生成回复和标准回复的自动评价指标.

### 词重叠评价指标 Word Overlap-based Metics ###
- BLEU
- METEOR
- ROUGE
### 词向量评价指标 Embedding-based Metrics ###
- Greddy Matching  
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Greddy%20Matching.PNG?raw=true)
- Embedding Average  
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Embedding%20Average.PNG?raw=true)
- Vector Extrema  
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Vector%20Extrema.PNG?raw=true)

## 相关性分析 Human Correlation Analysis ##
### 数据收集 ###
25个计算机系的志愿者给定一个上下文和回复,对回复进行评分,评分区间为1-5,1代表回复不适合上下文,5代表回复是合理的.  
在25个志愿者中,有23个的Cohen's kappa 分数是大于0.2的,有2个的分数小于0.2被排除.  
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/correlation.PNG?raw=true)

### 结果 Survey Result ###
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/correlation2.PNG?raw=true)  
上图计算了自动评价结果和人类判断之间的Pearson相关性(线性相关)和Spearman相关性(单调相关).  
首先观察到的是BLEU-4与人类判断的相关性很低.实际上,BLEU-3和BLEU-4很大一部分回复的分数都是0,但相关性分数与BLEU-2相近,
可能是因为平滑常数给了单词和词语一个很小的权重.  
因此,如果使用BLEU评价回复,建议使用BLEU-2.  

将回复中的停用词,标点符号剔除,再次计算BLEU分数以及与人类评价的相关性,发现相关性分数降低.这表明,BLEU对回复中不改变语义的部分很敏感.  
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/correlation3.PNG?raw=true)

最后测试了回复长度对自动评价指标的影响,结果如下图所示,结果表明BLEU和METEOR相比于基于词向量的评价指标和人类评价对回复的长度更敏感.  
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/correlation4.PNG?raw=true)

## 讨论 Discuss ##
- 整合多种回复 Incorporating multiple responses  
通常,在对话系统模型的训练数据中,一个输入对应着一个输出.已经有一些工作通过检索得到很多合理的回复用于BLEU指标的计算.
但没有一个标准的流程.而且也需要测试多个回复的BLEU指标与人类评价的相关性.
- 寻找合适的评价指标
作者认为基于词向量的评价指标是最有前景的一种评价方式,因为基于词向量的评价指标可以被解释为比较了生成回复与标准回复的主题是否一致.
此外,可以考虑更先进的句子向量技术如skip-thought 向量

提到的所有评价指标都未考虑上下文直接对生成回复与标准回复进行比较,评价指标可以通过考虑上下文信息做出改进.  
评价指标也可以成为评价模型的形式.评价模型可以是判别模型,对模型产生的回复和人类的回复进行区分.也可以收集人类的评分标注,训练评分模型   
最后,要注意的是我们必须考虑一个假设:学习一个评分模型并不比训练一个对话模型容易.如果假设成立的话,
那么我们只能用自动评价指标粗略的评价对话系统之后再由人类进行评价.


