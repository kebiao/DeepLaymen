#### 所有资源：https://pan.baidu.com/s/19ZxtLXnNYxjv4eE5uwLbqg 提取码：xpz0

# Windows:

将cudnn中的文件拷贝到C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0下
https://developer.nvidia.com/rdp/cudnn-download

https://developer.nvidia.com/cuda-toolkit-archive

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

选择支持的Linux版本，选择runfile下载：

https://developer.nvidia.com/cuda-toolkit-archive

https://developer.nvidia.com/rdp/cudnn-download
