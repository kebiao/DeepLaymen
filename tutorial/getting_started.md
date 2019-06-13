# 什么是深度学习？

深度学习（Deep Learning, DL）是机器学习领域的一种技术，通过建立具有多层级（指层数超过三层的神经网络）结构的人工神经网络在计算系统中实现人工智能。
深度学习作为机器学习研究中的一个新兴领域，由Hinton等人于2006年提出。


首先我们了解一下深度学习相关应用的知名案例以便有个初步的理解：

* 能够将视频中任意人的脸换成其他人的脸。

    https://github.com/deepfakes/faceswap

* 通过训练学习，能够由AI自主的玩“Flappy Bird”游戏。

    https://github.com/yenchenlin/DeepLearningFlappyBird

* 还有著名的阿尔法狗(AlphaGo)是第一个击败人类职业围棋选手、第一个战胜围棋世界冠军的人工智能程序。它主要的原理就是深度学习。 
* 自动驾驶、语音识别、图片文字识别等等。

人工智能、机器学习、深度学习这三者的关系？

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/getting_started_1.png">
</p>

（从图中可以看出，人工智能是个很大的概念，机器学习是其中一个子集，而深度学习又是机器学习的子集）


深度学习以及其他所有的机器学习算法本质上都是一种“拟合”机制，深度学习能够在大量的数据基础之上总结出可用的规律。
而这些数据是需要人来提供的，所以说机器学习过程就是让机器学习人类经验的过程。而这个过程与数据有关，与方法无关。


很多年前机器学习需要大量的人工设计并积累各种数据特征，比如一个字“柯”的各种不同情况下的特征，遇到新的情况就可能失效，并且传统的机器学习由于可训练的参数限制，在一些情况下无法形成足够的曲面无法用来拟合数据。
而深度学习能够通过大量的数据自动的找到特征，能够形成足够复杂的曲面用于拟合，在海量的数据下能够获得比较理想的结果。

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/getting_started_2.png">
</p>

（从图中可以看出，机器学习在数据量提升到一定程度时表现无法持续提升，而深度学习则表现更好）

# 神经网络的基本组成

人工神经网络（artificial neural networks) 是一种模仿生物神经网络行为特征，进行信息处理的算法数学模型。
在人工神经网络模型中使用单元节点模拟神经元，通过调整神经网络内部大量节点（神经元）之间相互连接的权重来达到处理信息的目的。人工神经网络的神奇之处在于不需要显示的编程告诉计算机该如何处理信息，它可以像大脑一样从已知数据信息中进行自我学习，然后对全新的输入数据信息输出正确的响应。

从直观上来看看神经网络长什么样呢？

首先来看神经元，通过树突接收各种电信号，然后通过细胞核处理，然后由轴突传递给到相关联的其他神经元。

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/getting_started_3.png">
</p>

对于计算机来说要怎么去表达呢？我们先看一个最简单的神经元(Neuron)：

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/getting_started_5.png">
</p>

多层感知器(MLP-Multi Layer Perceptron)：

一个单一的神经元不能够完成复杂的任务，因此需要将更多的神经元组合起来工作进而产生更有用的输出。

最简单的神经网络包括一个**输入层、一个隐藏层和一个输出层**。每一层都由多个神经元组成，每一层的每个神经元都与下一层中的所有神经元相连。这样的网络可以被称为是**全连接网络**。


<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/getting_started_4.png">
</p>

例如上图，用于手写体识别的神经网络是由一组可能被输入图像的像素激活的输入神经元来限定。后进过加权，并通过一个函数（由网络的设计者确定的）转化，这些神经元的致动被上到其他神经元然后被传递。重复此过程，直到最后，一输出神经元被激活。这决定了哪些字符被读取。

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/getting_started_6.png">
</p>

从上图可以看出，神经网络通过物体的边缘信息组合形成更高层的表达知道能识别出具体的模型。而很多不同类型，如：车、文字、动物甚至声音结构图都具有相同的局部边缘信息。通过深度学习神经网络技术能够很好的识别它们。

