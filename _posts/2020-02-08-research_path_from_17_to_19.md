---

title: 谣言检测近年研究技术路线图
tag: Rumor_Detection

---


| 谣言检测17-19年研究进展 |
| --- |
| 年份 | CCF | 会议 | 题目 | 算法 | 研究组 | 备注 |
| 19 | A | WWW | Detect Rumors on Twitter by Promoting Information Campaigns with Generative Adversarial Learning | GAN(GRU based) | [CUHK] Ma Jing | 基于GAN的思想，提出两个生成器功能分别为1）输入谣言特征表示输出真实Twitter特征表示和2）输入真实Twitter特征表示输出谣言特征表示，通过生成器生成与输入特征表示相反的特征用于迷惑判别器，增强判别器判断谣言的能力。其中生成器及判别器均基于GRU实现。用了二分类的TWITTER和pheme数据集。 |
| 19 | A | WWW | Reply Aided Detection of Misinformation via Bayesian Deep Learning | BiLSTM + MLP | [UCL] | 将claim构成词向量序列输入BiLSTM中编码，再接MLP并由多元高斯分布求得潜在随机变量z，同时将所有回复的词向量输入BiLSTM和LSTM编码得到隐状态h，通过将z和h拼接输入MLP得到谣言检测结果，用了RumourEval和PHEME数据集。 |
| 19 | B |   | Computers &amp; Security-Attention-based Convolutional Approach for Misinformation Identification from Massive and Noisy Microblog Posts | GNN + Attention + CNN | [自动化所] 吴书组 | 提出content and temporal co-attention机制的Event2vec模型表示事件分布（有清洗数据功能？），和CNN结合。启示：先清洗数据，然后用GNN结合attention表示事件，结合CNN。 |
| 18 | A | ACL | Rumor Detection on Twitter with Tree-structured Recursive Neural Networks | RvCNN | [CUHK] Ma Jing | 首先将事件相关的推特集根据转发和回复关系构成树状结构，分为自顶而下和自底而上两种信息传播结构。 |
| 18 | A | SIGKDD | EANN Event Adversarial Neural Networks for Multi-Modal Fake News Detection |   | [纽约州立水牛城分校] | 提出事件对抗神经网络检测虚假信息。推特用的MediaEval数据集，微博用的Jin Zhiwei发表在多模态论文中的数据。 |
| 18 | A | WWW | Detect Rumor and Stance Jointly by Neural Multi-task Learning |   | [CUHK] Ma Jing | 基于神经网络的多任务学习结构提出了一种同时解决谣言检测和观点立场检测两种任务的方法。 |
| 18 | A | AAAI | Early Detection of Fake News on Social Media Through Propagation Path Classification with Recurrent and Convolutional Networks | GRU + CNN | [新泽西理工学院] | 基于GRU和CNN把pooling结果拼接再接多层神经网络（带dropout）。weibo和Twitter15、Twitter16三个数据集。 |
| 18 | B | CIKM | Rumor Detection with Hierarchical Social Attention Network | BiLSTM + Attention | [计算所] 曹娟组 | 双向LSTM然后加attention机制，数据集为16年rumdect数据集（Twitter加kwon，weibo数据集） |
| 17 | A | IJCAI | A Convolutional Approach for Misinformation Identification | CNN | [自动化所] 吴书组 | |

