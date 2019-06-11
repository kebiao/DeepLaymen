# 资源下载：

#### 官方下载（有些版本无法成功下载）：

https://developer.nvidia.com/cuda-toolkit-archive

https://developer.nvidia.com/rdp/cudnn-download

#### 网盘直接下载：
https://pan.baidu.com/s/1JxATR-4poggu1spJxJ-e4A 提取码：gxsy

# Windows:

将cudnn\下面所有的文件和文件夹拷贝到C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0下

将路径加入到path环境变量:

C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\extras\CUPTI\libx64;

# Ubuntu:

#### 显卡检查

查看系统当前使用的显卡是否是独立显卡，如果是集成显卡输出如下：

$ glxinfo|egrep "OpenGL vendor|OpenGL renderer*"

    OpenGL vendor string: Intel Open Source Technology Center
    OpenGL renderer string: Mesa DRI Intel(R) Sandybridge Mobile*
  
独立显卡如下：

$ optirun glxinfo|egrep "OpenGL vendor|OpenGL renderer"

    OpenGL vendor string: NVIDIA Corporation
    OpenGL renderer string: GeForce GT 555M/PCIe/SSE2

#### 下载安装CUDA与cuDNN：

CUDA选择支持的Linux版本，选择runfile下载。

    sudo chmod +x cuda_10.0.130_410.48_linux.run 
    sudo ./cuda_10.0.130_410.48_linux.run
 
    sudo chmod +x cuda_10.0.130.1_linux.run 
    sudo ./cuda_10.0.130.1_linux.run


如果出错ERROR: An NVIDIA kernel module 'nvidia-drm' appears to already be loaded in your kernel.
       
        # 禁用图形目标
        sudo systemctl isolate multi-user.target

        # 卸载Nvidia驱动程序
        sudo modprobe -r nvidia-drm
        
        卸载旧的驱动
        sudo apt-get purge nvidia-cuda*
        sudo apt-get purge nvidia-*
        
        安装驱动完成之后再次启动图形环境，可以使用此命令：
        sudo systemctl start graphical.target

重启后继续上面的步骤安装CUDA。


CUDNN选择支持的Linux版本，选择如cuDNN Library for Linux下载。
    
    tar -xzvf cudnn-10.0-linux-x64-v7.6.0.64.tgz
    sudo cp cuda/include/cudnn.h /usr/local/cuda/include
    sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64 
    sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*


#### 设置环境变量

vim ~/.bashrc   #打开该用户的配置文件.bashrc

    export CUDA_HOME=/usr/local/cuda-10.0
    export PATH="$PATH:/usr/local/cuda-10.0/bin"
    export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda/lib64:/usr/local/cuda-10.0/lib64:/usr/local/cuda-10.0/extras/CUPTI/lib64"

#### 测试是否安装成功：

    nvcc -V


