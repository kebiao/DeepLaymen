# 逻辑回归(logistics regression)

逻辑回归就可以用来完成分类任务，适合用来例如做：物体分类、垃圾邮件检测等。

 要说逻辑回归，我们得追溯到[线性回归](https://github.com/kebiao/deeplearning/blob/master/tutorial/linear_regression.md)，想必大家对线性回归都有一定的了解，即对于多维空间中存在的样本点，我们用特征的线性组合去拟合空间中点的分布和轨迹。如下图所示：

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/getting_started_7.png">
</p>

既然逻辑回归是解决分类问题，那么为什么要叫回归呢？ 逻辑回归就是用回归的办法来做分类。

考虑最简单的二分类,结果是正例或者负例的任务，按照线性回归的思路，我们可以先对这个任务进行线性回归，找出事务的规律。比如根据人的饮食、作息、工作和生存环境等条件预测一个人“有”或者“没有”得恶性肿瘤。可以先通过回归任务来预测人体内肿瘤的大小,取一个平均值作为阈值，如平均值为y，肿瘤大小超过y为恶心肿瘤，无肿瘤或大小小于y的为非恶性。这样通过线性回归加设定阈值的办法，就可以完成一个简单的二分类任务。如下图:

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/getting_started_8.png">
</p>

上图中，红色的x轴为肿瘤大小，粉色的线为回归函数拟合图像，绿色的线为阈值。


预测肿瘤大小还是一个回归问题，得到的结果(肿瘤的大小)也是一个连续型变量。通过设定阈值，就成功将回归问题转化为了分类问题。

但是这样做还存在一个问题，我们上面的假设，依赖于所有的肿瘤大小都不会特别离谱，如果有一个超大的肿瘤在我们的例子中，阈值就很难设定。如果还是取平均大小为阈值，则会出现下图的情况：

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/getting_started_9.png">
</p>

从上边的例子可以看出，使用线性的函数来拟合规律后取阈值的办法是不行的，原因在于拟合的函数是线性的直线。离群值（也叫异常值）对结果的影响过大，但是我们的整体思路是没有错的，错的是用了太“直”的拟合函数。

在这样的场景下，逻辑回归就诞生了。它的核心思想是，如果线性回归的结果输出是一个连续值，而值的范围是无法限定的，那我们有没有办法把这个结果值映射为可以帮助我们判断的结果呢？而如果输出结果是0到1之间的一个概率值，这个问题就很清楚了。
逻辑回归用到的映射函数为sigmoid函数，函数图像和公式如下图所示：

<p align="center">
  <img src="https://github.com/kebiao/deeplearning/blob/master/screenshots/tutorial/getting_started_10.png">
</p>

这样一个函数它不再像线性回归函数一样受离群值影响，他的输出结果是样本预测为正例的概率(0到1之间的小数)。

