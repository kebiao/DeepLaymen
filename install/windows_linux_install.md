
## 1.前提准备

EasyBCD：链接：https://pan.baidu.com/s/1E_XNf0RUOsPGgGc_h1UNUQ 提取码：uus2 

Ubuntu系统镜像： https://www.ubuntu.com/download/desktop

## 2.可用空间准备

开始+R打开运行，输入diskmgmt.msc打开磁盘管理，右键一个不使用的磁盘删除，得到一块可用空间。
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/1.png)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/2.png)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/3.png)

## 3.配置引导

将ubuntu**.iso中casper目录的initrd.lz、vmlinuz.efi 解压出来与iso一同放在C盘或D盘根目录（必须根目录）下。
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/4.png)

打开EasyBCD，添加新条目->NeoGrub->安装：
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/5.png)

点击配置，C盘中会多出一个“NST”文件夹和一个NeoGrub文件，修改编辑C:\NST\menu.lst文件内容如下（其中iso文件改为你自己的）：

（1）上面的文件放在C盘根目录则为 hd0,0，D盘则为hd0,4。

（2）（hdx,y）x代表对应磁盘，y代表对应分区。

（3一般情况下C盘为主分区，DEF盘为逻辑盘，感兴趣可自行了解。


    # NeoSmart NeoGrub Bootloader Configuration File
    #
    # This is the NeoGrub configuration file, and should be located at C:\NST\menu.lst
    # Please see the EasyBCD Documentation for information on how to create/modify entries:
    # http://neosmart.net/wiki/display/EBCD/

    title Install Ubuntu 
    root (hd0,0) 
    kernel (hd0,0)/vmlinuz boot=casper iso-scan/filename=/ubuntu-19.04-desktop-amd64.iso ro quiet splash locale=zh_CN.UTF-8 
    initrd (hd0,0)/initrd


在EasyBCD编辑引导菜单可看到NeoGrub引导加载器，记得勾选等待用户选择，保存设置:
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/6.png)

## 4.进入引导

配置完成后重启计算机，选择NeoGrub引导加载器，若上诉配置无误即可进入ubuntu界面的引导：
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/7.png)

[引导后黑屏问题请看这里。](https://github.com/kebiao/deeplearning/blob/master/install/ubuntu_install_blackscreen.md)

## 5.开始Ubuntu系统安装

使用ctrl+alt+T打开终端，输入以下命令卸载分区：

    sudo umount -l /isodevice

![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/8.png)

然后点击桌面的安装程序进行安装，前几步的选项如图：

![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/9.png)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/10.png)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/11.png)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/12.png)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/13.png)

分配空间时需要注意：

交换空间    : 逻辑分区   8000MB

/                 : 逻辑分区   20480MB (一般为机器内存的一到两倍)

/home        : 逻辑分区   腾出200M左右的空间后的大小

/boot          :  主分区     200MB左右 （这个分区必须最后分配，否则可能为出现其他分区无法分配的情况）

![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/14.png)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/15.png)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/16.png)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/17.png)

最后选择/boot 所在分区进行安装：

![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/18.png)

之后按照提示step by step就可以了。


## 6.Clear()

安装完之后，重启进入Windows界面，打开EasyBCD，添加Ubuntu启动项，顺便删除NeoGrub引导项，删除根目录下的iso等三个文件：

![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/19.png)

引导菜单大概是这样的：

![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/20.png)

当时选择的是中文安装Ubuntu，但是因为在终端操作时，中文的路径非常之难用，可在语言支持中把English 拖动到中文之上，注销登出一下即可，然后再update一下就ok了：

![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/21.png)

END~
