# 项目地址：

https://github.com/CMU-Perceptual-Computing-Lab/openpose/releases/latest

# GPU方式编译请安装环境

[参考安装教程](https://github.com/kebiao/deeplearning/blob/master/install/cuda_cudnn_install.md)

# Ubuntu

#### caffe安装：

如果是自己下载安装编译，目前需要下载指定的版本，否则会产生错误，原因是新caffe中增加了一些layer，老的pose_iter_584000.caffemodel不匹配。

Can't parse message of type "caffe.NetParameter" because it is missing required fields: layer[0].clip_param.min, layer[0].clip_param.max

    git clone https://github.com/BVLC/caffe.git
    git reset --hard f019d0dfe86f49d1140961f8c7dec22130c83154

[相关安装参考。](https://github.com/kebiao/deeplearning/blob/master/install/caffe_install.md)

非默认的caffe需要修改cmake选项：

![img](https://github.com/CMU-Perceptual-Computing-Lab/openpose/blob/master/doc/media/cmake_installation/im_5.png)

#### 编译：

    cd build/
    make -j`nproc`

# Windows

直接用CMake-gui打开，源码目录设置为：“D:\openpose-1.5.0”，编译目录设置为：“D:\openpose-1.5.0/build”， 然后直接Configure等待下载和安装第三方库资源，接着Generate，打开VS开始编译。