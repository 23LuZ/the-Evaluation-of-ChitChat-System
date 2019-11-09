## ACUTE-EVAL:Improvd dialogue evaluation with optimized questions and multi-turn comparisons
### 摘要
评价很难，有两个方面的原因：
- 自动评价指标跟人工评价的相关性很低
- 人工评价的一致性也很低
两个最常用的人工评价方式：
- 单轮成对比较 single-turn pairwise evaluation
- 多轮likert分数 multi-turn Likert scores
提出一种新的评价方法:针对两个完整的对话，在一个完整对话中，要求评价者只关注其中一个发言者，然后进行成对比较

对问题进行优化以最大程度地提高对不同评价者判断的鲁棒性，从而实现更好的测试

这些测试在self-play模型聊天设置中进行，能够实现更快更便宜的测试

### 简介
single-turn pairwise 评价简单，能够便宜，快速地进行，并且鲁棒性要高于打分，但无法评价多轮对话

multi-turn likert 要求评价者与聊天机器人进行多轮对话，然后给出一个整体分数，花费多还费时间但对整个对话进行评价更准确。
但是每个评价者给出的整体分数都有不同的偏差和方差。而且评价者容易受到他们评价的第一个系统的影响。因此，该指标无法在多篇文章之间进行比较。
这就要求评价新模型时同时要评价基准模型，增加了开发新模型的成本。

介绍一个新方法ACUTE-EVAL，通过结合以上两种方法的优点，引入多回合对话成对比较 pairwise relative comparsion setup for multi-turn的方法，从而缓解上述缺点

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/self-play%20examples.PNG?raw=true)

本文的贡献如下：
- 提出了一种具有清晰机制的新评估方法，可提供快速，廉价的迭代。
这种评估方法可以有效地重用以前论文中的数据，从而可以独立于基准来评估新模型，并大大降低了评价成本
- 优化了问题，选取了一致性最高的问题
- 提供了在目前效果最好的检索和生成模型在两个任务上表现的比较结果
- 方法可用于self-play框架，而不是人机对话日志，能够更加廉价但与人工评价具有高一致性的进行评价

### 方法：ACUTE-EVAL
执行该方法的步骤如下：
- 收集模型A和B的对话日志
- 在许多试验中，要求评价者对两个模型的对话日志中的对话片段进行比较，然后对结果进行核对，以确定获胜者A或者B，以及统计意义

每一步都采取了不同的方法：
- 人机对话 Human-Model chats 
- 自问自答 Self-Chats 
人机对话日志收集起来很费时间和金钱，限制了模型的快速迭代发展，使用替代方法：模型自己进行对话
- 问题优化 Question Optimization
众所周知，调查中问题的框架和措辞会极大地影响答复的方向，在评估的情况下就是评价者之间的一致性。
旨在提出和评价多种潜在的问题措辞，以达成更高的一致性。
    - 选取human-human logs 和 human-model logs(回复效果很差的基线模型)进行比较。评价者之间应该能够具有很大的共识
    - 然后提出不同措辞的问题进行实验，一致性最高的问题被选为最终的问题
    尽管在评价者之间具有较高的共识并不能保证评价者能够按预期解释问题，但是这增加了统一理解问题的可能性。
    在我们的实验中，我们发现在四个维度上具有较高一致性的问题：参与度，趣味性，知识和类人的（ngagingness, interestingness, knowledge and humanness）
- 评价者的质量 Annotation Quality
我们建议将单个评价者可以完成的评价数量限制为仅几对。对human-human logs 和 human-model logs比较失败的评价者排除，对于打分从未给出理由的评价者排除。
每个对话对只出现一次。

### 实验
新方法的评价结果，基本上与Likert score结果一致。但统计意义更加显著

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/ACUTE-EVAL%20results%20on%20the%20Engagingness%20question%20for%20the%20PersonaChat.PNG?raw=true)

self-play模式下，评价结果与新方法和Likert score基本一致，除了HF。原因可能在于HF自我聊天会在模型本身中产生表面退化，并且看起来不自然。
由于特定模型的不足之处（在这种情况下为HF），因此必须谨慎处理自聊性能结果的结论，但我们认为这是模型开发周期中早期实验的合理选择，可以更快地进行研究迭代。

自聊的一个问题是强大的模型可以轻松地作弊，并且只需回忆训练示例就可以非常精确。 在实践中，我们发现没有一个模型能表现出这种行为。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/ACUTE-EVAL%20results%20for%20self-chats%20for%20the%20Engag-%20ingness%20question%20on%20PersonaChat.PNG?raw=true)
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/self-play%20examples.PNG?raw=true)

各个方法的成本效益

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Relative%20cost%20effectiveness%20of%20potential%20collection%20methods.PNG?raw=true)

### 结论
- 当前的人类评估方法（如multi-turn Likert）运行昂贵，存在评价者偏差和方差问题，并且可能无法产生统计意义
- 提供了一种新颖的评估方法，通过优化问题并在一对人机对话中进行比较，可以在对当前模型进行基准测试时进行更敏感的统计测试。
- 利用自动聊天机器人评估，通常可以提高灵敏度，同时获得更便宜的评估。 
