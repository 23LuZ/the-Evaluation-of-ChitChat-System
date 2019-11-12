## Better Automtic Evaluation of Open-Domain Dialogue System with Contextualized Embeddings

### 对RUBER做出改进
- RUBER的参考指标和非参考指标都依赖于词向量，对RUBER做出改进，使用BERT词向量，也就是动态词向量 contextualized word embeddings
- 为了更好地利用词向量，探索了不同的网络架构和目标函数

### 非参考指标
- 词向量 

将静态的word2vec词向量换为动态的BERT词向量，动态的BERT词向量能够根据上下文产生词向量，也就是说在不同的上下文中，同一个字会有不同的词向量。
-句子表示 

将双向RNN换为简单的池化，原因是BERT词向量是在双向transformer中训练得到的，已经包含了单词上下文的完整信息，如果再加一层双向RNN可能只是
增加参数，对效果提升没有帮助。
- 多层感知器网络 Multilayer Perceptron Network 

MLP是RUBER模型非参考指标的最后一部分，原来的目标函数为排序损失（Ranking loss），即最大化参考回复和随机采样回复与问题的相关性分数，
将其换为交叉熵损失（Cross entropy loss），将非参考分数预测看作是一个简单的二分类问题，将问题-参考回复对标记为1，问题-随机采样回复对标记为0，
MLP分类器最后一层中softmax函数的输出给出每对问题和回复的相关性得分。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/An%20illustration%20of%20changes%20applied%20to%20RUBER%E2%80%99s%20unreferenced%20metric%E2%80%99s%20architecture..PNG?raw=true)

### 参考指标
- 将静态词向量换位动态BERT词向量

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/BERT-based%20referenced%20metric.PNG?raw=true)

### 结果
- 非参考指标

改进后的模型，即词向量由word2vec换为BERT词向量、句子表示由双向RNN变为最大池化和目标函数由排序损失换为交叉熵，获得了与人工评价最高的相关性。
此外，最大池化表现总是优于评价池化，对于基于word2vec的模型，排名损失通常表现更好，而表现最好的基于BERT的模型使用的是交叉熵损失。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Correlation%20and%20similarity%20values%20between%20automatic%20evaluation%20metrics.PNG?raw=true)

- 参考指标+非参考指标

仍然是改进模型的表现更好，但相比于非参考指标的结果，相关性有所下降，表明参考指标的应用对相关性的提高并没有帮助，与RUBER模型的结果相矛盾。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Correlations%20and%20similarity%20values%20between%20relatedness%20scores%20predicted%20by%20different%20unreferenced%20models%20and%20human%20judgments.PNG?raw=true)

### 未来发展
未来，将模型扩展到多轮对话，并且在评价指标中考虑其他质量属性如创造性，新颖性等。

