#### 环境准备

依赖库安装：

    sudo apt-get install build-essential

    sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev

    sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev

Python2.7 or python3.x：

    sudo apt-get install python3
    
numpy：

    sudo apt-get install python-numpy

安装opencv：

https://opencv.org/releases.html
  
    cd  opencv-3.4.3
    mkdir release
    cd release
    cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local ..
    make
    sudo make install

#### 下载caffe与配置

先clone

    git clone https://github.com/BVLC/caffe.git
  
进入clone的caffe文件夹，执行以下命令，把Makefile.config.example复制更名为Makefile.config

    sudo cp Makefile.config.example Makefile.config
  
修改此文件（很关键）相当于caffe编译配置文件：

     sudo vim Makefile.config
   
  
使用cudnn:

    #USE_CUDNN := 1
    
    修改成： 
    USE_CUDNN := 1
    
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
 
