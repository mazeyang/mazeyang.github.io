# Anomaly Detection in ICLR 2020

7 posters


- 1. Classification-Based Anomaly Detection for General Data. *Liron Bergman, Yedid Hoshen* [[pdf]](https://openreview.net/pdf?id=H1lK_lBtvS)

**Abstract**: Anomaly detection, finding patterns that substantially deviate from those seen previously, is one of the fundamental problems of artificial intelligence. Recently, classification-based methods were shown to achieve superior results on this task. In this work, we present a unifying view and propose an open-set method to relax current generalization assumptions. Furthermore, we extend the applicability of transformation-based methods to non-image data using random affine transformations. Our method is shown to obtain state-of-the-art accuracy and is applicable to broad data types. The strong performance of our method is extensively validated on multiple datasets from different domains.

**Keywords**: anomaly detection



- 2. Robust Subspace Recovery Layer for Unsupervised Anomaly Detection. *Chieh-Hsin Lai, Dongmian Zou, Gilad Lerman* [[pdf]](https://openreview.net/pdf?id=rylb3eBtwr)

**Abstract**: We propose a neural network for unsupervised anomaly detection with a novel robust subspace recovery layer (RSR layer). This layer seeks to extract the underlying subspace from a latent representation of the given data and removes outliers that lie away from this subspace. It is used within an autoencoder. The encoder maps the data into a latent space, from which the RSR layer extracts the subspace. The decoder then smoothly maps back the underlying subspace to a ''manifold" close to the original inliers. Inliers and outliers are distinguished according to the distances between the original and mapped positions (small for inliers and large for outliers). Extensive numerical experiments with both image and document datasets demonstrate state-of-the-art precision and recall. 

**Keywords**: robust subspace recovery, unsupervised anomaly detection, outliers, latent space, autoencoder



- 3. Novelty Detection Via Blurring. *Sungik Choi, Sae-Young Chung* [[pdf]](https://openreview.net/pdf?id=ByeNra4FDB)

**Abstract**: Conventional out-of-distribution (OOD) detection schemes based on variational autoencoder or Random Network Distillation (RND) are known to assign lower uncertainty to the OOD data than the target distribution. In this work, we discover that such conventional novelty detection schemes are also vulnerable to the blurred images. Based on the observation, we construct a novel RND-based OOD detector, SVD-RND, that utilizes blurred images during training. Our detector is simple, efficient in test time, and outperforms baseline OOD detectors in various domains. Further results show that SVD-RND learns a better target distribution representation than the baselines. Finally, SVD-RND combined with geometric transform achieves near-perfect detection accuracy in CelebA domain.

**Keywords**: novelty, anomaly, uncertainty




- 4. Deep Semi-Supervised Anomaly Detection. *Lukas Ruff, Robert A. Vandermeulen, Nico Görnitz, Alexander Binder, Emmanuel Müller, Klaus-Robert Müller, Marius Kloft* [[pdf]](https://openreview.net/pdf?id=HkgH0TEYwH) [[code]](https://tinyurl.com/y6rwhn5r)

**Abstract**: Deep approaches to anomaly detection have recently shown promising results over shallow methods on large and complex datasets. Typically anomaly detection is treated as an unsupervised learning problem. In practice however, one may have---in addition to a large set of unlabeled samples---access to a small pool of labeled samples, e.g. a subset verified by some domain expert as being normal or anomalous. Semi-supervised approaches to anomaly detection aim to utilize such labeled samples, but most proposed methods are limited to merely including labeled normal samples. Only a few methods take advantage of labeled anomalies, with existing deep approaches being domain-specific. In this work we present Deep SAD, an end-to-end deep methodology for general semi-supervised anomaly detection. Using an information-theoretic perspective on anomaly detection, we derive a loss motivated by the idea that the entropy of the latent distribution for normal data should be lower than the entropy of the anomalous distribution. We demonstrate in extensive experiments on MNIST, Fashion-MNIST, and CIFAR-10, along with other anomaly detection benchmark datasets, that our method is on par or outperforms shallow, hybrid, and deep competitors, yielding appreciable performance improvements even when provided with only little labeled data. 

**Keywords**: anomaly detection, deep learning, semi-supervised learning, unsupervised learning, outlier detection, one-class classification, deep anomaly detection, deep one-class classification



- 5. RaPP: Novelty Detection with Reconstruction along Projection Pathway. *Ki Hyun Kim, Sangwoo Shim, Yongsub Lim, Jongseob Jeon, Jeongwoo Choi, Byungchan Kim, Andre S. Yoon* [[pdf]](https://openreview.net/pdf?id=HkgeGeBYDB) [[code]](https://drive.google.com/file/d/1KJ45tO5RX9_8dhoyQQ6zUd-ZbCoDvxmq/view?usp=sharing)

**Abstract**: We propose RaPP, a new methodology for novelty detection by utilizing hidden space activation values obtained from a deep autoencoder. Precisely, RaPP compares input and its autoencoder reconstruction not only in the input space but also in the hidden spaces.
We show that if we feed a reconstructed input to the same autoencoder again, its activated values in a hidden space are equivalent to the corresponding reconstruction in that hidden space given the original input.
In order to aggregate the hidden space activation values, we propose two metrics, which enhance the novelty detection performance.
Through extensive experiments using diverse datasets, we validate that RaPP improves novelty detection performances of autoencoder-based approaches.
Besides, we show that RaPP outperforms recent novelty detection methods evaluated on popular benchmarks.

**Keywords**: Novelty Detection, Anomaly Detection, Outlier Detection, Semi-supervised Learning



- 6. Robust anomaly detection and backdoor attack detection via differential privacy. *Min Du, Ruoxi Jia, Dawn Song* [[pdf]](https://openreview.net/pdf?id=SJx0q1rtvS) [[code]](https://www.dropbox.com/sh/rt8qzii7wr07g6n/AAAbwokv2sfBeE9XAL2pXv_Aa?dl=0)

**Abstract**: Outlier detection and novelty detection are two important topics for anomaly detection. Suppose the majority of a dataset are drawn from a certain distribution, outlier detection and novelty detection both aim to detect data samples that do not fit the distribution. Outliers refer to data samples within this dataset, while novelties refer to new samples. In the meantime, backdoor poisoning attacks for machine learning models are achieved through injecting poisoning samples into the training dataset, which could be regarded as “outliers” that are intentionally added by attackers. Differential privacy has been proposed to avoid leaking any individual’s information, when aggregated analysis is performed on a given dataset. It is typically achieved by adding random noise, either directly to the input dataset, or to intermediate results of the aggregation mechanism. In this paper, we demonstrate that applying differential privacy could improve the utility of outlier detection and novelty detection, with an extension to detect poisoning samples in backdoor attacks. We first present a theoretical analysis on how differential privacy helps with the detection, and then conduct extensive experiments to validate the effectiveness of differential privacy in improving outlier detection, novelty detection, and backdoor attack detection.

**Keywords**: outlier detection, novelty detection, backdoor attack detection, system log anomaly detection, differential privacy



- 7. Input Complexity and Out-of-distribution Detection with Likelihood-based Generative Models. *Joan Serrà, David Álvarez, Vicenç Gómez, Olga Slizovskaia, José F. Núñez, Jordi Luque* [[pdf]](https://openreview.net/pdf?id=SyxIWpVYvr)

**Abstract**: Likelihood-based generative models are a promising resource to detect out-of-distribution (OOD) inputs which could compromise the robustness or reliability of a machine learning system. However, likelihoods derived from such models have been shown to be problematic for detecting certain types of inputs that significantly differ from training data. In this paper, we pose that this problem is due to the excessive influence that input complexity has in generative models' likelihoods. We report a set of experiments supporting this hypothesis, and use an estimate of input complexity to derive an efficient and parameter-free OOD score, which can be seen as a likelihood-ratio, akin to Bayesian model comparison. We find such score to perform comparably to, or even better than, existing OOD detection approaches under a wide range of data sets, models, model sizes, and complexity estimates.

**Keywords**: OOD, generative models, likelihood

