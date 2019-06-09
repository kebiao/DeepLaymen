#### 下载caffe

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
