# Linear Regression（线性回归）

机器学习（尤其是监督学习），主要围绕分类和回归两类问题展开，而线性回归模型作为最简单的回归模型，与大多数监督学习算法具有相同的建模思路，包括建立损失函数、优化参数、模型评估。
可谓麻雀虽小五脏俱全，了解线性回归的建模思想能够有助于理解复杂的深度学习模型。

#### 什么是线性回归：

import numpy as np
from numpy import random
import matplotlib.pyplot as plt

# 随机生成在[0,30]区间内服从均匀分布的100个数
X = random.uniform(0, 30, 100)

# 对X乘以固定系数后加上随机扰动
y = 1.85 * X + random.normal(2, 5, 100)

plt.scatter(X, y)
plt.xlabel('X')
plt.ylabel('y')
plt.show()

* 假设X和y之间存在线性关系，即y=w∗X+b
* y^=wX+b，其中y^y^表示根据线性方程计算得到的yy值（称为估计值），为尽可能准确的表达样本中X和y之间的关系，我们需要找到最优的w∗w∗和b∗b∗，使得yy的实际值和估计值之间的误差|y−y^||y−y^|最小化。


