## Automated Scoring of Chatbot Responses in Conversational Dialogue
### 摘要
- 对机器人回复的质量进行自动评价和打分
- 结合人类和聊天机器人回复的单词表示，使用机器学习算法如SVM,RF和神经网络，学习聊天机器人回复的质量
- 对生成回复进行分类，回复是否是有效的可接受的还是无效的，因为合理的回复不只一个

### 聊天机器人的评价
数据集来自WOCHAT，选取了有人类标注的数据集：Vaild/Acceptable/Invaild，但是人工标注的内部一致性较低

任务可以分为三步：
- 构建参考答案 Ground truth construction
Vaild/Acceptable/Invaild --》 1.0，0.5.0.0
   - optimistic 1.0 (1.0,0.5) 0.0   二分类 binary classification
   - pessimistic 1.0(1.0) 0.0 (0.5,0.0)  二分类
   - averaging  regression 回归
  optimistic和pessimistic是将average的回归问题分解为两个简单二分类问题，两个分类器训练完成后，它们的输出可以被结合（投票/平均）来解决回归问题
- 特征提取 Feature extraction
  Bag-of-words 词袋模型 + SVM/RF + binary cross-entropy
  word embedding + NN + mean squared error + The epoch with the best F1-score or Pearson correlation coefficient on the development set
  is selected as the final model
- 学习 Learning

### 实验
#### 评价指标
- 二分类问题：F1-score,accuracy
- regression Pearson's correlation
