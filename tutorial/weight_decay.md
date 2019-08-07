# 权重衰减法（Weight Decay）

我们了解了过拟合现象，即模型的训练误差远小于它在测试集上的误差。虽然增大训练数据集可能会减轻过拟合，但是获取额外的训练数据往往代价高昂。
权重衰减（weight decay）是应对过拟合问题的常用方法。
L2正则化的目的就是为了让权重衰减到更小的值，而惩罚大的权值，在一定程度上减少模型过拟合的问题，所以权重衰减也叫L2正则化。

### 观察过拟合：

让我们训练并测试高维线性回归模型。当lambd设为0时，我们没有使用权重衰减。结果训练误差远小于测试集上的误差。这是典型的过拟合现象。

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/weight_decay_1.png">
</p>

**L2 norm of w: 11.611942**


### 使用权重衰减

可以看出，训练误差虽然有所提高，但测试集上的误差有所下降，过拟合现象得到一定程度的缓解。另外权重参数的L2范数比不使用权重衰减时的更小，此时的权重参数更接近0。

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/weight_decay_2.png">
</p>

**L2 norm of w: 0.04141709**

