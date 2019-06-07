# nvidia显卡兼容问题

### 1. 安装时

需要把NVIDIA的显卡禁掉，在安装的过程中，选中install ubuntu那一选项，按‘e'编辑将：

    quite splash ---

改为：

    quite splash nomodeset

再按F10就可以顺利安装了。

由于显卡被禁掉所以它默认的分辨率是800×600，有时候可能按不到底下的按钮，但是按住alt+s就可以随意拖动。


### 2.安装完成后

重启后进入系统引导选项，按’e'编辑大概在倒数第二行将：

    quite splash $vt_handoff

改为：

    quite splash nomodeset_$vt_handoff

再按F10这样你会发现这样就可以启动了。

### 3.安装显卡驱动

##### 方法一:
其实很简单，在设置里点开“软件与更新”，先换源（推荐换成中国的源），并更新。
再到“附加驱动”里找nvidia独显，安装驱动，再重启（不需要再按‘e’进行编辑），一般分辨率就会恢复正常，电脑也不会卡死，如果分辨如还不能恢复，在网站上查一下，如何切换分辨率。

##### 方法二:
    add-apt-repository ppa:graphics-drivers/ppa
    apt-get update
    
    寻找合适的驱动版本
    ubuntu-drivers devices
    apt-get install nvidia-430
    
 安装完驱动后还要安装依赖

    apt-get install mesa-common-dev
    apt-get install freeglut3-dev

最后重启，然后再终端中输入:

    nvidia-smi
    nvidia-setting

如果有显卡的信息输出就说明成功安装了.

    
    

