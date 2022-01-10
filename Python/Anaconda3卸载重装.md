### Anaconda3卸载重装

Linux下，Anaconda3的卸载安装都比较便捷

#### 彻底删除anaconda3

- 删除anaconda3文件夹
- 删除有关anaconda的环境变量

#### 重装anaconda3

- 输入命令`sh Anaconda3-5.3.1-Linux-x86_64.sh`即可安装，一路默认
- 安装过程中会提示是否加载环境变量，选择yes，继续安装
- 安装完毕后，设置的环境变量并未激活，所以无法识别conda命令，需要手动在终端输入命令激活，有两种方式：1）`source ~/.bashrc` ；2）`export PATH=~/anaconda3/bin:$PATH`
- 至此，可以正常使用anaconda