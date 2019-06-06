#### 所有资源：

https://pan.baidu.com/s/19ZxtLXnNYxjv4eE5uwLbqg    提取码：xpz0

https://developer.nvidia.com/cuda-toolkit-archive

https://developer.nvidia.com/rdp/cudnn-download

# Windows:

将cudnn中的文件拷贝到C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0下

将路径加入到path环境变量:

C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\extras\CUPTI\libx64;C:\tools\cuda\bin;

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

#### 下载CUDA与cuDNN：

选择支持的Linux版本，选择runfile下载。


#### 设置环境变量

vim ~/.bashrc   #打开该用户的配置文件.bashrc

    export CUDA_HOME=/usr/local/cuda-8.0
    export PATH="$PATH:/usr/local/cuda-8.0/bin"
    export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda-8.0/lib64:/usr/local/cuda-8.0/extras/CUPTI/lib64"

https://www.cnblogs.com/zpcdbky/p/9757821.html
