# 环境准备

#### Ubuntu:

    sudo apt-get update
    sudo apt-get install build-essential libgtk2.0-dev libavcodec-dev libavformat-dev libjpeg-dev libswscale-dev libtiff5-dev:i386 libtiff5-dev
    sudo apt-get install autoconf automake libtool

#### GPU环境CUDA和CuDNN安装 （CPU版本忽略）

https://pan.baidu.com/s/1JxATR-4poggu1spJxJ-e4A 提取码：gxsy

###### 注意：匹配TensorFlow所支持的版本再下载
[参考安装教程](https://github.com/kebiao/deeplearning/blob/master/install/cuda_cudnn_install.md)


# 开始安装:

#### 1：Anaconda安装

包含了conda、Python等180多个科学包及其依赖项，功能十分强大

https://www.anaconda.com/distribution/#download-section

#### 2: 创建Python环境

    conda create -n test python=3.7

#### 3: 激活conda

    conda activate test

#### 4: 安装TensorFlow

    python -m pip install --upgrade pip
    CPU版本：pip install --ignore-installed --upgrade tensorflow
    GPU版本：pip install --ignore-installed --upgrade tensorflow-gpu


--------------------------------------------------------------------------

至此，tensorflow的安装完成，测试代码：

    import tensorflow as tf
    hello = tf.constant('Hello, TensorFlow!')
    sess = tf.Session()
    print(sess.run(hello))



