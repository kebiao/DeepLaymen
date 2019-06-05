## 1.前提准备

EasyBCD：https://pan.baidu.com/s/1E_XNf0RUOsPGgGc_h1UNUQ 提取码：uus2 

Ubuntu系统镜像: https://www.ubuntu.com/download/desktop

## 2.可用空间准备

开始+R打开运行，输入diskmgmt.msc打开磁盘管理，右键一个不使用的磁盘删除，得到一块可用空间。
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/1.png)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/2.png)
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/3.png)

## 3.配置引导

将ubuntu**.iso中的initrd.lz、vmlinuz.efi 解压出来与iso一同放在C盘或D盘根目录（必须根目录）下。
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/4.png)

打开EasyBCD，添加新条目->NeoGrub->安装：
![image](https://github.com/kebiao/deeplearning/blob/master/screenshots/win_linux_install/5.png)

点击配置，修改文件内容如下：

注意：
（1）上面的文件放在C盘根目录则为 hd0,0，D盘则为hd0,4。
（2）（hdx,y）x代表对应磁盘，y代表对应分区。
（3一般情况下C盘为主分区，DEF盘为逻辑盘，感兴趣可自行了解。

    # NeoSmart NeoGrub Bootloader Configuration File
    #
    # This is the NeoGrub configuration file, and should be located at C:\NST\menu.lst
    # Please see the EasyBCD Documentation for information on how to create/modify entries:
    # http://neosmart.net/wiki/display/EBCD/

    title Install Ubuntu 
    root (hd0,4) 
    kernel (hd0,4)/vmlinuz.efi boot=casper iso-scan/filename=/ubuntu-16.04.2-desktop-amd64.iso ro quiet splash locale=zh_CN.UTF-8 
    initrd (hd0,4)/initrd.lz


