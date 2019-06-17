# 安装

直接到官网选择安装参数，按提示进行安装。

https://pytorch.org/get-started/locally/

例如：conda安装模式

conda install pytorch torchvision cudatoolkit=10.0 -c pytorch

# 下载失败问题

添加清华源

    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
    conda config --set show_channel_urls yes

另外为了保险起见，建议同时添加第三方conda源：

    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/menpo/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/

**注意：去掉-c才会默认从清华源下载相应的包，因此这里用命令行:**

    conda install pytorch torchvision cudatoolkit=10.0 pytorch
