# 什么是（神经元）激活函数？

在神经网络中，我们会对所有的输入进行加权求和，之后我们会在对结果施加一个函数，这个函数就是我们所说的激活函数。如下图所示：

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/activeation_function_1.png">
</p>

#### 为什么使用激活函数？

每个激活函数的输入都是一个数字，然后对其进行某种固定的数学操作。激活函数给神经元引入了非线性因素，当加入多层神经网络时，就可以让神经网络拟合任何线性函数及非线性函数，从而使得神经网络可以适用于更多的非线性问题，而不仅仅是线性问题。

#### 有哪些激活函数？

比较常用的三种激活函数：Sigmoid函数、Tanh函数、ReLU函数。

激活函数的发展经历了Sigmoid -> Tanh -> ReLU -> Leaky ReLU -> Maxout这样的过程，还有一个特殊的激活函数Softmax，因为它只会被用在网络中的最后一层，用来进行最后的分类和归一化。
