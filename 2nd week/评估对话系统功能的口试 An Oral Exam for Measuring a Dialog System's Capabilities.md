## 评估对话系统功能的测试 An Oral Exam for Measuring a Dialog System's Capabilities

- 效率 Efficiency - 表现 Performance 

  Graceful degradation

- 效用  Effectiveness - 功能 Functionality

  具有广度的知识，并且能够灵活的运用 Contains breadth of knowledge, is flexible in interpreting it.

### 摘要 Abstract

本文提出了一种在对话系统功能的广度（breadth）和灵活性（flexibility）方面进行衡量的模型和方法。

人工评价者对系统进行定向的口试，并对系统在每个测试问题上的表现发表主观看法。

通过对两个可公开访问的对话系统和一个人进行测试得到的结果，可以表明所提出的度量标准为了解这些系统的相对优势和劣势提供了有用的见解。

### 简介 Introduction

当前对话系统最明显的两个缺点是缺乏广度和灵活性。

广度是系统充分执行各种推理任务的能力。也就是能回答很多问题。

灵活性是系统能够充分执行几乎需要相同知识和推理的各种的能力。也就是能回答同一问题的不同变种。

如果工程师要向通用的对话系统迈进，就必须有一个科学的流程来支持它们。本文做出以下贡献：

- 研究人员需要一个模型来明确描述系统的能力，以便在此基础上评估对话系统。 我们提出了这样一个模型以及该模型的一个示范实例。
- 完整的对话系统的复杂功能，广度和灵活性难以描述，并且在有限的空间中，研究人员没有好的选择来简洁地报告此信息。 我们提供了一种方法和指标，用于在给定的模型实例中评估系统的性能，这将使研究人员可以简明扼要地报告有关其系统的信息，而今天这些信息尚未报告
- 出于演示目的对几种现有系统进行了评估，提供了结果并分析了该方法的可靠性和实用性。

### 提出的方法 Proposed Approach

所有功能都是外部可观察到的行为，与内部表示和过程无关。

#### 能力分类 Capability Taxonomy

一个功能$k\in K$, 其类别为$c \in C$。本文所使用的功能和类别所下图所示：

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Summary%20of%20the%20example%20taxonomy%20of%20capabilities%20and%20capability%20categories.PNG?raw=true)

能力是行为的一般类别，需要进一步指定才能生成单个测试问题。 测试域由一组参数$\Theta$和一个函数组成:$Param:\ K\times\Theta\ \rightarrow \{T,F\}$ ,只有能力接受域参数时，返回True。本文中，$\theta\in \Theta$ 是简单的一个或两个单词形式的物理对象或动作动词。

#### 实例化功能分类和域 Instantiating a Capability Taxonomy and Domain

需要使用能力和能力类别来实例化上述分类法模型，并且需要定义评估的主要范围。

测试的可靠性将取决于功能定义和文档的清晰度。 应该选择分类法设计者希望系统具有的各种功能，将要求非常相似知识和推理能力的能力分为同类。

评估的范围比较小，选取了作者比较感兴趣的范围。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/The%20domain%20of%20evaluation%20used%20within%20this%20paper.PNG?raw=true)

#### 启发试验 Elicitation Trials

人类测试人员对系统进行测试以评价系统是否具有需要的能力。人类测试人员使用一种能够测试系统并将结果参数化的工具进行系统评价。测试人员根据工具提供的示例提出问题。

试验过程如下：通过评价工具选定‘Class Search’能力，物理名词‘coffee shop’，那么对应‘Class Search’能力的示例问题展示出来，测试人员根据示例问题结合物理名词‘coffee shop’提出新的问题，如下图所示，结果被评定为失败。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/coffee%20shop%20example.PNG?raw=true)

每个系统 $s$ 的试验 $t$ 结果可表示为 $t=(e[t],k[t],\theta[t],o[t])$,其中，$e[t]$ 代表测试者，$k[t]$ 代表测试的能力， $\theta[t]$  代表能力对应的参数，$o[t]$ 代表结果${0,1}$

#### 评价指标 Evaluation Metrics

##### 评价表现 Evaluating Performance

能力 $k$ 的表现如下：
$$
P_k(s)=Average(\{o[t];t\in T_s,k[t]=k\})
$$
能力类别 $c$ 的表现如下：
$$
P_c(s)=Average(\{P_k(s);k\in c\})
$$
整体表现如下：
$$
P_{total}(s)=\sum_{c\in C}P_c(s)
$$

##### 评价广度 Evaluating Breadth

广度应衡量系统利用各种推理过程和知识的能力。 就我们的能力分类模型而言，这意味着广度应衡量可以执行的能力类别的多样性。

衡量多样性本身就是一个复杂的问题，为了简化问题，采用归一化的香农熵测量（normalized Shannon entropy measure ),可用 $\tilde H(Q)$ 表示，其中 $Q$ 为离散概率分布：
$$
\tilde H(Q)=-\frac{1}{\ln(n)}\sum_{i=1}^nq_i*\ln(q_i)
$$
系统的广度 $B$  就是能力类别表现的多样性：
$$
B(s)=\begin{cases} 0\ \ \  if\ P_{total}=0 \\
\tilde H(Q_B)\ \ \ otherwise\end{cases}
$$
$Q_B$ 具有质量密度函数：
$$
q_B(c)=\frac{P_c(s)}{P_{total}(s)},\ c\in C
$$
由于估计量偏差对样本量的依赖，因此只能在基于相同样本数的广度度量之间进行比较。

##### 评价灵活性 Evaluating Flexibility 

灵活性应该直观地衡量系统用同样的一些知识和推理过程回答不同表示的问题的能力，因此，我们将能力类别的灵活性$F_c$计算为该类别中能力表现的多样性：
$$
F_c(s)=\begin{cases}
0,\ \ if \ \ P_c(s)=0 \\
\tilde H(Q_F(c)) \  \ otherwise
\end{cases}
$$
$Q_F(c)$ 的质量分布函数为:
$$
q_F(k)=\frac{P_k(s)}{\sum_{k'\in c}P_{k'}(s)},k \in c
$$
该措施将区分具有一种高度专业能力的系统和具有多种能力的系统。

### 过程 Procedure

6名评价者对两个对话系统Google Now、Cleverbot和一个人类进行评价。每个评价者针对每个系统的每个功能进行两次试验，最终得到468个试验结果。

### 实验结果 Experimental Results

本文试图评估关于我们的方法的三个主张。 

- 模型和指标可以区分具有少量高度专业功能的系统和具有一般功能的系统。 
- 这种评估方法可通过不同的测试者提供可靠的结果。 
- 在对话系统评估的典型时间范围内可以执行此评估。要求评价者快速准确地进行试验，平均62秒一个试验，30分钟可完成所有的任务，符合评价的典型时间范围。

实验结果如下图所示：

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/breadth%20and%20flexibility.PNG?raw=true)

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/performance.PNG?raw=true)

### 先前工作 Prior Work

#### 评价聊天机器人 Evaluating Chatbots

图灵测试是最著名的试验。人们普遍认为应该通过观察行为来评估智能，而不是坚持诸如“思想”之类的不可观察的内部现象。Cohen对图灵测试提出了许多有用的批评和替代。 首先，作者认为它的结果不够具体，无法用作增量进展的基准。 此外，作者认为，可以通过图灵测试的系统不一定能在其他与智力相关的测试中普遍表现良好。 尽管如此，图灵测试还是标志性的，并在年度勒布纳竞赛中进行。

Shawar 提出了几个聊天机器人的小规模评估方法，试图提供比Loebner竞赛更多有用的信息。 他们通过生成3个版本的ALICE聊天机器人系统进行测试，分析了聊天系统响应的合理性，信息检索系统的结果的相关性以及查找答案的能力。相对于Loebner / Turing标准，这是重要的进步，但是定义需要更精确，测试可靠性需要更好地理解，而性能则需要通过能力来分解。

Morrissey 得到影响聊天机器人自然性的四个因素：认真，礼貌，彻底和独创。 这些因素可以作为我们此处采用的方法中的能力类别进行调整，它们将构成更大的综合能力格局的一部分。

Vinyals提出了一种新颖的聊天机器人架构，并通过众包的人工评估者选择对问题更合适的回答来比较系统。 但是，没有选择问题的明确标准，也没有对这些问题正在测试的内容或系统根据所问问题类型的性能差异变化进行分析。

### 结论和未来工作 Conclusion and Future Work 

- 本文提出了一个评价模型和评价指标。主要针对表现Performance（整体）、广度Breadth（类间）和灵活性Flexibility（类内）三个质量属性进行评价。

- 本文针对的领域测重于作者感兴趣的功能领域，未来需要进一步标准化。

  
