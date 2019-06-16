# 项目地址：

https://github.com/una-dinosauria/3d-pose-baseline

# GPU方式编译请安装环境

[参考安装教程](https://github.com/kebiao/deeplearning/blob/master/install/cuda_cudnn_install.md)

# 项目附带数据资源

链接：https://pan.baidu.com/s/1rjWM7zxrcO7u7P81Furl0g 提取码：bjrg 

# 安装资源

h36m.zip直接在3d-pose-baseline\data下解压放置。

    cd 3d-pose-baseline
    mkdir data
    cd data
    unzip h36m.zip
    rm h36m.zip
    cd ..

experiments.tar.gz直接解压放到根目录下。

    cd 3d-pose-baseline
    tar -zxvf experiments.tar.gz

如果是Windows系统最好在Linux使用tar解压或者Windows下的tar工具解压，Windows下很多解压软件解压有问题。


# 测试：

单张图片测试

    $ python run.py --model=mobilenet_thin --resize=432x368 --image=./images/p1.jpg

摄像机测试

    $ python run_webcam.py --model=mobilenet_thin --resize=432x368 --camera=0
