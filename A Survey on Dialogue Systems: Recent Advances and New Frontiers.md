## A Survey on Dialogue Systems: Recent Advances and New Frontiers ##

## 评价 ##
非任务型对话系统
- 词重叠指标 word overlap metrics：BLEU,MENTOR,ROUGE
- 词向量指标 word embedding metrics：Embedding Average,Embedding Extrema,Embedding Greedy 
- 基于评分模拟的评价方法：训练评分神经网络结构，RNN结构，GAN结构(图灵测试的思想)

值得注意的是虽然词重叠和词向量指标已被广泛应用于非任务型对话系统的评价，但是研究表明这些指标与人类的判断或者具有很弱的相关性或者没有相关性。
此外，词向量指标能够有效的将基线模型与最先进的模型区分开。

>可继续参考的文献  
>
>[1] P.-H. Su, D. Vandyke, M. Gasic, D. Kim, N. Mrksic, T.-H. Wen, and S. Young. Learning from real users: Rating dialogue success with neural networks for rein- forcement learning in spoken dialogue systems. arXiv preprint arXiv:1508.03386, 2015.
>
>[2] C. Tao, L. Mou, D. Zhao, and R. Yan. Ru- ber: An unsupervised method for automatic evalu- ation of open-domain dialog systems. arXiv preprint arXiv:1701.03079, 2017.
>
>[3] R. Lowe, M. Noseworthy, I. V. Serban, N. Angelard- Gontier, Y. Bengio, and J. Pineau. Towards an auto- matic turing test: Learning to evaluate dialogue re- sponses. In Proceedings of the 55th Annual Meeting of the Association for Computational Linguistics (Vol- ume 1: Long Papers), pages 1116–1126, Vancouver, Canada, July 2017. Association for Computational Linguistics.
>
>[4] A. Kannan and O. Vinyals. Adversarial evaluation of dialogue models. arXiv preprint arXiv:1701.08198, 2017.
>
>[5] E. Bruni and R. Fern´andez. Adversarial evaluation for open-domain dialogue generation. In Proceedings of the 18th Annual SIGdial Meeting on Discourse and Dialogue, pages 284–288, 2017.
