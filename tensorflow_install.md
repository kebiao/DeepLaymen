#### 所有资源：https://pan.baidu.com/s/19ZxtLXnNYxjv4eE5uwLbqg 提取码：xpz0

#### 1: GPU环境CUDA和CuDNN安装 （CPU版本忽略）

###### 注意：匹配TensorFlow所支持的版本再下载
[参考安装教程](https://github.com/kebiao/deeplearning/blob/master/cuda_cudnn_install.md)

# Windows:
 
#### 2：Anaconda安装

包含了conda、Python等180多个科学包及其依赖项，功能十分强大

https://www.anaconda.com/distribution/#download-section

#### 3: 创建Python环境

    conda create -n test python=3.7

#### 4: 激活conda

    conda activate test

#### 5: 安装TensorFlow

    python -m pip install --upgrade pip
    CPU版本：pip install --ignore-installed --upgrade tensorflow
    GPU版本：pip install --ignore-installed --upgrade tensorflow-gpu


--------------------------------------------------------------------------

至此，tensorflow的安装完成，测试代码：

    import tensorflow as tf
    hello = tf.constant('Hello, TensorFlow!')
    sess = tf.Session()
    print(sess.run(hello))


# Ubuntu:
