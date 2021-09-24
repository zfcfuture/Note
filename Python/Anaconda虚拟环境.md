### Anaconda虚拟环境

#### 一. Windows下

```shell
# 1.创建python环境
conda create -n environment_name python=X.X

# 2.激活、退出虚拟环境
activate your_env_name
deactivate

# 3.查看已有的虚拟环境
conda env list

# 4.删除环境
conda remove --name your_env_name --all

# 5.查看pip的安装包
pip list
```



#### 二. Linux下

```shell
# 1.进入清华镜像下载对应anaconda文件
https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/

# 2.运行.sh文件
bash Anaconda3-5.3.1-Linux-x86_64.sh

# 3.设置环境变量
export PATH=/home/zfc/anaconda3/bin:$PATH

# 4.进入、退出base环境
conda activate
conda deactivate

# 5.创建虚拟环境
conda create -n env_name python=X.X

# 6.进入、退出自己创建的环境
conda activate env_name
conda deactivate

# 7.删除环境
conda remove -n env_name --all
```

