## 1.前提准备

EasyBCD：https://pan.baidu.com/s/1E_XNf0RUOsPGgGc_h1UNUQ 提取码：uus2 

Ubuntu系统镜像: https://www.ubuntu.com/download/desktop

## 2.可用空间准备

开始+R打开运行，输入diskmgmt.msc打开磁盘管理，右键一个不使用的磁盘删除，得到一块可用空间。

## 3.配置引导

将ubuntu**.iso中的initrd.lz、vmlinuz.efi 解压出来与iso一同放在C盘或D盘根目录（必须根目录）下。
打开EasyBCD，添加新条目->NeoGrub->安装：
