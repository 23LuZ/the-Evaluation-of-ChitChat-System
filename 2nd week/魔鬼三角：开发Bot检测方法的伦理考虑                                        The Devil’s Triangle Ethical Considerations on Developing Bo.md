## 魔鬼三角：开发Bot检测方法的伦理考虑                                        The Devil’s Triangle: Ethical Considerations on Developing Bot Detection Methods

- 效率 Efficiency - 表现 Performance

  操作鲁棒性 Robustness to manipulation

#### 摘要 Abstract

社交媒体越来越多地使用机器人。 为了保护用户的真实性，使用机器学习算法来检测这些机器人。 

这些方法的道德维度尚未得到充分考虑。 以Twitter用户的个人资料图像的直方图分析为例，该论文演示了准确性（accuracy），透明度（transparency）和鲁棒性（robustness）之间的权衡。 

因为在伦理上没有普遍的最佳选择，所以这些维度形成了一个“魔鬼三角”。

#### 机器人是一个道德问题-操作与真实性 Bots as an ethical problem - manipulation vs. authenticity

今天，人们无法想象没有基于互联网的社交媒体网络和平台的社交互动：很多人都拥有一个Facebook或Twitter帐户，并使用它与彼此进行沟通或随时收集或传播信息。此外，人们有机会创建社交内容并分享他们的图片，视频和事件。

这些功能以及数字社区的迅速发展，不仅使它们成为私人用途，而且也有商业，政治和宗教目的。实际上，出于多种原因，人们对这种“社交内容”很感兴趣，并且认为人们可以在社交媒体平台上收集的信息是原始和真实的。

最近，随着社交机器人和僵尸网络的暴露，真实性和可靠信息来源的外观开始崩溃，从而加强了社交网络中欺骗，滥用和操纵的证据。

探讨机器人如何在社交平台上破坏真实性的技术，人们可以从“假冒追随者”（fake followers）的泛滥开始，这只是在提高特定Twitter帐户的知名度，从而提高该账户的影响力与受关注度，进而吸引真正的追随者。

最近在社交网络的不同阶段还积累了“社会欺诈”(soical fraud)的证据。 作为示例，可以考虑#YaMeCance Twitter标签的边缘化，它是传播信息和组织现代墨西哥抗议暴力与腐败运动的主要交汇点。 社交机器人通过发布垃圾邮件或反抗议消息，淹没真实对话，干扰或威胁积极参与者来削弱这个主题标签。

由平台运营商自己提供，以检测和控制具有误导性的机器人文章和推文，并将其与“真实的人为”信息分开。区分社交网络中的机器人和人类的一种或多或少有效的方法是采用监督式机器学习方法。基于人类和机器人在社交网络中的行为以及它们之间的区别，这些技术的目的是开发可将人类用户与机器人区分开的“检测算法”或“分类器”。所有这些方法都或多或少准确地预测了社交平台的未知用户是否是机器人的可能性，这包括出错的可能性。

因此，上述道德困境仍然以某种方式继续存在：不能确定由机器学习算法做出的预测是否一直正确。 因此，不仅从机器学习技术上检测机器人的结果在道德上是有问题的，而且在决策上还会产生决定。 在下文中，我们将通过跟踪有关其准确性，透明度和鲁棒性的问题，探索采用机器学习方法的机器人检测开发过程的道德内容。

#### 直方图分析作为机器人检测方法 Histogram analysis as a bot detection method

我们不断进行的“机器人狩猎”项目产生的基本思想是：探索新的检测方法以适应Twitter上社交机器人的动态可变性，我们诊断出机器人经常使用漫画人物或图标（例如Twitter提供的鸡蛋图标）作为他们的个人资料照片或头像。这一发现提出了一个问题，即是否有可能建立一个框架，以通过扫描Twitter用户的头像，预测他们是机器人还是人类。下载机器人头像和真实用户头像后，编写了一种算法，该算法将RGB色彩模型中的每张个人资料图片转换为灰度，然后使用Open CV提取图片的直方图。 根据直方图训练一个有监督的学习方法（支持向量机）区分机器人和人类账户。最后结果精度达到83.6%。

#### 开发检测机器人机器学习算法中的伦理问题。 魔鬼的三角形 Ethical questions in developing bot detection by machine learning algorithms aka. the devil’s triangle

可以扩展特征空间并组合成为更加复杂的分类器，如好友关注者比率，推文，访问的持续时间等特征，这将提高分类器的准确率，从伦理的角度来看，创建更复杂的分类器是进入‘魔鬼三角’的第一步。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/The%20devil%E2%80%99s%20triangle.PNG?raw=true)

#### 处理透明度  Dealing with transparency

如果将机器人检测算法公开，那么机器人将进行升级改造，检测算法将失效。道德的话来说，这种情况下的（太多）透明度会增加社交网络中的不确定性以及操纵和欺诈的可能性，并将其提升到一个全新的水平，因为产生了新一代的新机器人（称为2.0）

如果开发了新的分类器来识别新的bot-2.0代，则它必须包括所有相关功能，以将三个用户类别（人类，bots-1.0和bots-2.0）分开，而不是两个。机器人内部的较大差异将对我们的预测造成另一个威胁：对操纵的鲁棒性逐渐减弱。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Increased%20transparency%20will%20cause%20continuous%20bot%20variations%20and%20a%20decrease%20in%20detection%20robustness.PNG?raw=true)

#### 差异与鲁棒性 Variance vs. robustness 

针对2.0机器人的出现，可以整合2.0机器人的特征到分类器，提高分类器的精度，或者针对整个机器人群体的普通特征重新训练一个通用分类器。

![](https://github.com/23LuZ/the-Evaluation-of-ChitChat-System/blob/master/pics/Increase%20of%20the%20features%20range%20will%20enhance%20the%20accuracy%20and%20decrease%20the%20transparency.PNG?raw=true)

#### 总结 Conclusion

机器学习机器人检测方法的开发人员应牢记，仍然存在（目前仍很简单）道德问题，并且没有“约束条件下的最优”。





