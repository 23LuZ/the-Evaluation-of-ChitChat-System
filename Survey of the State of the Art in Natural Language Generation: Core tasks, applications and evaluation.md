## Survey of the State of the Art in Natural Language Generation: Core tasks, application and evaluation ##
接下来重点介绍自然语言生成中的不同的评价方式及其之间的关系。

## 评价 ##
系统的评论值得作为一个话题进行全面的讨论，这也成为了自然语言生成中的一个主要讨论问题。
促进这一发展的一个因素是许多自然语言生成竞赛的建立。

自然语言生成评价的特点是种类繁多（可变输入 variable input，多种可能的输出 multiple possible output），因此很难直接比较系统。
也很难对自然语言生成评估进行详尽的回顾。接下来以一个假设场景为例（如下图所示），对自然语言生成的评价进行说明。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/hypothetical%20evaluation%20scenario.PNG?raw=true)

图中的场景为海上石油钻井平台。

设置 ‘setup’的相关特征是系统本身及其用户(在这里是工程师)。

系统的任务‘task’是从根据天气预报数据生成天气预报，最终目标是方便用户计划钻井和维护作业。

图中也展示了自然语言生成评价中一些常见的指标及相应方法，可以是主观的即人类的判断，也可以是客观的即通过指标进行计算。

评价方法的根本区别是内在（intrinsic）和外在（extrinsic）评价的区别。在nlg的情况下，内在评估可衡量系统的性能，
而无需参考设置的其他方面，例如系统相对于其用户的有效性。 在示例场景中，与文本质量，输出的正确性和可读性有关的问题被认为是内在的，
而系统是否真正达到了在石油钻井平台上支持适当决策的目标这一问题是外在的。

## 内在方法 Intrinsic Methods ##
NLG的内在评价主要有两种方法：一种依赖人类的判断（human judgements），一种依赖语料库。

### 主观（人类）判断 subjective(human)judgements ###
人类判断通常是根据模型标准对系统的输出进行评分。一些常用的标准有：
- 流畅性或可读性（Fluency or Readability）
- 准确度（Accurancy），充分性(adequacy)，相关性(relevance)或正确性(correctness)：

上述这些常用的标准并未完全覆盖所有的标准。如在标题生成任务中，还要评价标题的创造力。

使用级别（scale）来评价。当离散时，顺序级别（ordinal scale）是主要的方法。当连续时，比如可以是以视觉方式呈现的滑块，主体可能会做出更细微的判断。

可能相比于比较一个系统的好坏，比较两个系统谁好谁坏更容易。典型的方法是两两比较（binary comparisons）

幅值估计（magnitude estimation），即没有给对象一个预先定义的比例，而是要求他们选择自己的对象，然后继续将每个项目与“模量”进行比较，该量模作为整个实验的比较点，
将基于偏好的范式与标准评级量表两种方法来评估来自两个不同领域的系统，发现前者对系统之间的差异更敏感，而对受试者之间的差异更不敏感。

主观评估的另一个问题是评估者之间的可靠性。 不同评估者的多项判断可能显示出较大差异。一种迭代的方法可能改善这个问题，
对判断者进行培训之后进行讨论，来更新评估准则。但是，这在时间和资源上都更加昂贵。

通过在线平台如亚马逊众包平台进行主观的人工评价对广泛使用的语言如英语更可行。但也有一些问题值得注意如收集数据的可靠性等。

###  使用语料库的客观类人度量 Objective Humanlikeness Measures Using Corpora ###
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/n-gram%20overlap.PNG?raw=true)
![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/string%20distane%20&%20content%20overlap.PNG?raw=true)

### 评估类型兼容性和风格效果  Genre Compatibility and Stylistic Effectiveness###
更多的是通过外在评价对文本类型和风格进行评价，比如在笑话生成中，评价方式为让测试者评价这个笑话是否好笑。

## 外在评价方法 Extrinsic Evaluation Methods ##
外在评价方法衡量实现预期目标的有效性（effectiveness）。在示例场景中，预期目标为帮助工程师计划钻井和维护作业。

有效性取决于应用领域和系统目的，包括：
- 劝说和行为改变，例如接触个性化的戒烟信
- 阅读有关迁徙鸟类的博客后，参与生态问题
- 生成患者报告后在医疗环境中提供决策支持
- 通过生成个人叙述来增强具有复杂交流需求的用户之间的语言互动
- 在辅导对话中提高学习效率

基于问卷调查或自我报告的研究可用于解决外部标准，在许多情况下，评估取决于绩效或成就的某种客观衡量。比如在VR游戏中，根据系统产生的指令，用户花费多长时间完成任务。

外在评价的缺点除了时间和资源消耗大，还有依赖适当的用户群（当必须从特定人群中抽样用户时，例如示例场景中的工程师，可能很难获得）以及在现实环境中进行研究的可能性。

## 黑盒 vs 玻璃盒评估 Black Box Versus Glass Box Evaluation ##
黑盒评估评价的是整个系统，玻璃盒评估评价的是系统的部件，典型的例子是消融实验（ablation experiment）

## 评价方法之间的关系 On the Relationship Between  Evaluation Methods ##
从外在，面向任务的评价方法到依赖自动评价和人工判断的内在评价方法，所提到的多种方法是相关的吗？

事实证明，很少有多种评估方法可以对一个系统或要比较的一组系统的相对排名做出一致的结论。

### 指标与人类判断 Metrics Versus Human Judgements ###

