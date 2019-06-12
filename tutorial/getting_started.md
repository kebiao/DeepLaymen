# 基础知识

#### 什么是深度学习？

首先我们了解一下深度学习相关应用的知名案例以便有个初步的理解：

* 能够将视频中任意人的脸换成其他人的脸。

    https://github.com/deepfakes/faceswap

* 通过训练学习，能够由AI自主的玩“Flappy Bird”游戏。

    https://github.com/yenchenlin/DeepLearningFlappyBird

* 还有著名的阿尔法狗(AlphaGo)是第一个击败人类职业围棋选手、第一个战胜围棋世界冠军的人工智能程序。它主要的原理就是深度学习。 
* 自动驾驶、语音识别、图片文字识别等等。

人工智能、机器学习、深度学习这三者的关系。

很多人不清楚它们之间的关系，先看图：

![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/1.jpg)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/2.png)

深度学习以及其他所有的机器学习算法本质上都是一种“拟合”机制，在大量的数据基础之上总结出可用的规律。
而这些数据是需要人来提供的，所以说机器学习过程就是让机器学习人类经验的过程。而这个过程与数据有关，与方法无关。
过去传统的机器学习需要大量的人工从数据中找到规律，而深度学习能够通过大量的数据自己找到规律。

#### CNN(卷积神经网络)、RNN(循环神经网络)、DNN(深度神经网络)
