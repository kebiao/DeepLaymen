# 项目地址：

https://github.com/ildoonet/tf-pose-estimation

# GPU方式编译请安装环境

[参考安装教程](https://github.com/kebiao/deeplearning/blob/master/install/cuda_cudnn_install.md)

# 项目附带数据资源

链接：链接：https://pan.baidu.com/s/138owJ3OXjnSAUigI4z5ZqA 提取码：e1k6 

# 安装资源

models文件夹直接在tf-pose-estimation\覆盖下解压放置。

# 编译C++模块：

 先安装swig，将swig设置到环境变量path中
 
    $ cd tf-pose-estimation/tf_pose/pafprocess
    $ swig -python -c++ pafprocess.i && python3 setup.py build_ext --inplace

# 测试：

单张图片测试

    $ python run.py --model=mobilenet_thin --resize=432x368 --image=./images/p1.jpg

摄像机测试

    $ python run_webcam.py --model=mobilenet_thin --resize=432x368 --camera=0
