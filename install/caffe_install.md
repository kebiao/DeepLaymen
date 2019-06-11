# Ubuntu环境准备

#### GPU环境CUDA和CuDNN安装 （CPU版本忽略）

https://pan.baidu.com/s/1JxATR-4poggu1spJxJ-e4A 提取码：gxsy


#### 依赖库安装：

    sudo apt-get install build-essential
    sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
    sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev


#### Python2.7 or python3.x：

    sudo apt-get install python3
    
#### numpy：

    sudo apt-get install python-numpy

#### protobuf:

    sudo apt-get install python-protobuf

#### gflags:

    sudo apt-get install libgflags-dev
    
也可以自己编译https://github.com/gflags/gflags/releases：

    cd gflags-2.2.2
    mkdir build
    cd build
    cmake -DCMAKE_INSTALL_PREFIX=/usr/local -DBUILD_SHARED_LIBS=ON -DGFLAGS_NAMESPACE=google -G"Unix Makefiles" ../
    make 
    sudo make install 
    sudo ldconfig 


#### 安装opencv：

默认版本安装：

    sudo apt-get install python-opencv

需要安装制定版本需要自己编译：https://opencv.org/releases.html
  
    cd  opencv-3.4.3
    mkdir release
    cd release
    cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local ..
    make
    sudo make install

#### python中测试是否安装成功:

    import cv2
    import numpy

# 开始安装

#### 下载caffe与配置

先clone

    git clone https://github.com/BVLC/caffe.git
  
进入clone的caffe文件夹，执行以下命令，把Makefile.config.example复制更名为Makefile.config

    sudo cp Makefile.config.example Makefile.config
  
修改此文件（很关键）相当于caffe编译配置文件：

     sudo vim Makefile.config
   
  
有GPU支持则使用cudnn:

    #USE_CUDNN := 1
    
    修改成： 
    USE_CUDNN := 1
    
    只有CPU可以只开
    CPU_ONLY := 1
    
修改python路径:

    INCLUDE_DIRS := $(PYTHON_INCLUDE) /usr/local/include
    LIBRARY_DIRS := $(PYTHON_LIB) /usr/local/lib /usr/lib 

    修改为： 
    INCLUDE_DIRS := $(PYTHON_INCLUDE) /usr/local/include /usr/include/hdf5/serial
    LIBRARY_DIRS := $(PYTHON_LIB) /usr/local/lib /usr/lib /usr/lib/x86_64-linux-gnu /usr/lib/x86_64-linux-gnu/hdf5/serial  


修改opencv版本（如果使用opencv3的话）:

    #OPENCV_VERSION := 3

    修改为： 
    OPENCV_VERSION := 3
    
 #### 编译
 
    make all
 
 一些其他库可能需要proto协议：
 
    protoc src/caffe/proto/caffe.proto --cpp_out=.
    mkdir include/caffe/proto
    mv src/caffe/proto/caffe.pb.h include/caffe/proto


### 相关错误

#### nvcc fatal   : Unsupported gpu architecture 'compute_20'

问题在于CUDA在CUDA architecture setting有版本兼容问题，修改Makefile.config:

    CUDA_ARCH := -gencode arch=compute_20,code=sm_20 \
            -gencode arch=compute_20,code=sm_21 \
            -gencode arch=compute_30,code=sm_30 \
            -gencode arch=compute_35,code=sm_35 \
            -gencode arch=compute_50,code=sm_50 \
            -gencode arch=compute_52,code=sm_52 \
            -gencode arch=compute_60,code=sm_60 \
            -gencode arch=compute_61,code=sm_61 \
            -gencode arch=compute_61,code=compute_61
改为:

    CUDA_ARCH := #-gencode arch=compute_20,code=sm_20 \
            #-gencode arch=compute_20,code=sm_21 \
            -gencode arch=compute_30,code=sm_30 \
            -gencode arch=compute_35,code=sm_35 \
            -gencode arch=compute_50,code=sm_50 \
            -gencode arch=compute_52,code=sm_52 \
            -gencode arch=compute_60,code=sm_60 \
            -gencode arch=compute_61,code=sm_61 \
            -gencode arch=compute_61,code=compute_61

#### /usr/bin/ld: 找不到 -lcudnn

进入cudnn解压得到的cudn文件夹lib64文件夹内：

    sudo cp libcudnn.so /usr/local/cuda/lib64/
    sudo cp libcudnn.so.7 /usr/local/cuda/lib64/
    sudo cp libcudnn.so.7.4.1 /usr/local/cuda/lib64/
    sudo cp libcudnn_static.a /usr/local/cuda/lib64/

#### tools/convert_imageset.cpp:56:3: error: ‘gflags’ has not been declared

由于gflags2.1之后将命名空间由google改为了gflags，所以这里暂时可以这样解决

* include/caffe/common.hpp
* examples/mnist/convert_mnist_data.cpp

在以上文件中注释掉#ifndef、#endif

    // #ifndef GFLAGS_GFLAGS_H_
    namespace gflags = google;
    // #endif  // GFLAGS_GFLAGS_H_
