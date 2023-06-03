# Few-shot-Learning-Project
This code is a reimplementation for few-shot learning to instrument classes to environmental sound classification on urbanksound8k datset.

1 Introduction
This document covers the methodology and approach used to perform few-shot learning for instrument classification and acoustic scene classification for unseen classes during training by using just few examples of the new class and finally perform a comparison study on different K-way N-shot classification combinations.

1.1 Few-shot learning for instrument classification and audio classification:

This document is related to classification of instruments from two different data- sets. First dataset was replicated from previous work and the other dataset is a follow on to the first assignment where I had used to the same dataset using supervised learning approach as an additional analysis and comparison for different methodologies for same dataset in this work I have attempted to perform few shot learning.

Few shot learning is a technique where the machine learning model is trained to perform well on novel classes by using few labelled examples quickly, based on just a handful of labelled examples (few-shot).
This approach is also quite different from the standard supervised learning, where the model is trained to recognize classes that it has already ‘seen’ while in case of few-shot learning the goal during test it’s performance on ‘unseen’ class by providing a very small number of examples. An important problem that is addressed with Few-shot learning(FSL) is that we are no longer limited to a pre-defined and fixed set of classes that we have enough labelled data for.
Instead, we can generalise to any class of interest at the cost of a little human intervention.

1.1 Few-shot learning for instrument classification and audio classification:

This document is related to classification of instruments from two different data- sets. First dataset was replicated from previous work and the other dataset is a follow on to the first assignment where I had used to the same dataset using supervised learning approach as an additional analysis and comparison for different methodologies for same dataset in this work I have attempted to perform few shot learning.

Few shot learning is a technique where the machine learning model is trained to perform well on novel classes by using few labelled examples quickly, based on just a handful of labelled examples (few-shot).
This approach is also quite different from the standard supervised learning, where the model is trained to recognize classes that it has already ‘seen’ while in case of few-shot learning the goal during test it’s performance on ‘unseen’ class by providing a very small number of examples. An important problem that is addressed with Few-shot learning(FSL) is that we are no longer limited to a pre-defined and fixed set of classes that we have enough labelled data for. Instead, we can generalise to any class of interest at the cost of a little human intervention.

2 Methodology

2.1 Metric based few shot learning

Typically, in few-shot learning two subset of data is used for training and eval- uation. Support set is a small collection of labelled examples that are used to help the model learn a new task. It typically consists of a few examples from each class that the model will need to recognize. For example, if the model is being trained to recognize environmental sounds then the support set contains a few examples of ‘birds chirping in the forest’, a few examples of ‘rustling of leaves’ etc.
Query set on the other hand, is a set of examples that has the same examples from the same classes as in the support set but they are not used during training. The concept of support set and query set are similar to that of training set and evaluation set used in traditional machine learning, however the difference is that support set is much smaller in size and is used to help the model learn a new task quickly and efficiently.

2.1.1 Prototypical Networks

Among the most popular metric-based approaches I have chosen Prototypical Networks to perform this task. In the domain of sound event recognition some research has explored the prototypical networks. Prototypical networks work by creating a single embedding vector for each class in the support set, called the prototype. The prototype for a class is the mean of the embeddings of all the examples in the support set for that class. After creating the prototype for each class in the support set, euclidean distance between the query example and each prototype to determine which class the query belongs to. A technique called episodic training is used in few-shot learning to effectively leverage a large training dataset. It involves splitting each training iteration into a self-contained learning task, known as an episode, which simulates a few-shot learning scenario with a small number of labelled examples for a set of classes.
2.1.2 Episodic training
During episodic training, the model is presented with a completely new N-shot, K-way classification task at each step, where N represents the number of small labelled examples provided and K represents the number of classes that the episode is being trained on. This way since the model is being trained in small chunks of N-shots for K-way classification tasks, the model effectively is learning the process of learning from a small set of labelled examples and adapting quickly to new tasks quickly.

3 Datasets 

3.1 TinySol
TinySOL [2]is a dataset of 2913 samples, each containing a single musical note from one of 14 different instruments. Bass Tuba, French Horn, Trombone, Trum- pet in C, Accordion, Contrabass, Violin ,Viola, Violoncello, Bassoon, Clarinet in B-flat, Flute, Oboe, Alto Saxophone. Audios are sampled at 44.1 kHz, with a single channel (mono), at a bit depth of 16.

3.2 Urbansound8k
This dataset[2] contains 8732 labeled sound excerpts (¡=4s) of urban sounds from 10 classes. Air conditioner, Car horn, Children Playing, Dog bark, Drilling, Engine Idling, Gun Shot, Jackhammer, Siren and Street Music. The classes are drawn from the urban sound taxonomy and audio are sampled at 16kHz, with a mono channel and bit depth of 16.

4 Results
Tinysol dataset[1] was evaluated for 5 unseen classes listed in the graph below and trained in a 5-way, 5-shot training method gave an accuracy of 0.74. On the other hand, This part of the task was a replication of the original code provided through the reference [3]
For the UrbanSound8k dataset using prototypical networks below is the plot showing the distribution of the points according to what it was being classified into. The first figure below is for 5way 5shot classification task where the training data and test data was split as 50:50 each containing 5 classes. This methodology gave an accuracy of 0.38.


References
[1] Carmine Emanuele, Daniele Ghisi, Vincent Lostanlen, Fabien L ́evy, Joshua Fineberg, and Yan Maresz. TinySOL: an audio dataset of isolated musical notes. Zenodo, January 2020.
[2] Justin Salamon, Christopher Jacoby, and Juan Pablo Bello. UrbanSound8K. Zenodo, November 2014.
[3] Yu Wang, Hugo Flores Garc ́ıa, and Jeong Choi. Few-Shot and Zero-Shot Learning for Music Information Retrieval. https://music-fsl- zsl.github.io/tutorial, 2022.
