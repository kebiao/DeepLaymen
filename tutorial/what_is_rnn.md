# 循环神经网络（Recurrent Neural Network, RNN）

是一类以序列（sequence）数据为输入，在序列的演进方向进行递归（recursion）且所有节点（循环单元）按链式连接的递归神经网络（recursive neural network）。
对循环神经网络的研究始于二十世纪80-90年代，并在二十一世纪初发展为重要的深度学习（deep learning）算法，其中双向循环神经网络（Bidirectional RNN, Bi-RNN）和长短期记忆网络（Long Short-Term Memory networks，LSTM）是常见的的循环神经网络。

循环神经网络具有记忆性、参数共享并且图灵完备（Turing completeness），因此能以很高的效率对序列的非线性特征进行学习。循环神经网络在自然语言处理（Natural Language Processing, NLP），例如语音识别、语言建模、机器翻译等领域有应用，也被用于各类时间序列预报或与卷积神经网络（Convoutional Neural Network,CNN）相结合处理计算机视觉问题。

为什么使用序列模型（sequence model）？标准的全连接神经网络（fully connected neural network）处理序列会有两个问题：

  1. 全连接神经网络输入层和输出层长度固定，而不同序列的输入、输出可能有不同的长度，选择最大长度并对短序列进行填充（pad）不是一种很好的方式；

  2. 全连接神经网络同一层的节点之间是无连接的，当需要用到序列之前时刻的信息时，全连接神经网络无法办到，一个序列的不同位置之间无法共享特征。而循环神经网络（Recurrent Neural Network，RNN）可以很好地解决问题。



