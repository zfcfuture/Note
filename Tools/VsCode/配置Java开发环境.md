#### 1. 环境配置

参考该博客https://blog.csdn.net/weixin_40448140/article/details/105904836

配置Java所需的插件，安装jdk等

#### 2. 乱码问题

https://blog.csdn.net/Xminyang/article/details/124329844

主要就是在code runner插件中新增uft-8编码以及 `runInTerminal`等

#### 3. 权限问题

在终端可以javac，在vscode终端出现“无法将“***”项识别为 cmdlet、函数、脚本文件或可运行程序的名称

解决方法：原因是权限不够，找到vs code的exe，也就是：code.exe，右键属性，在兼容性中选中【以管理员权限运行此程序】即可