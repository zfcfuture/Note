### PyQT报错之“xcb”问题

<font color=red>问题背景</font>：

环境（Ubuntu20.04 Anaconda3 Python3.9 pyQT5）；代码加载ui文件后运行出现以下报错：==qt.qpa.plugin:Could not load the Qt platform plugin "xcb"==

<font color=red>解决办法</font>：

1. 设置环境变量查看具体报错信息，具体如下：

```shell
$ vim ~/.bashrc
# 这句话会在qtcreator启动时，列出详细的错误信息
$ export QT_DEBUG_PLUGINS=1
$ source ~/.bashrc
```

2. 通过错误信息排查发现缺少动态库，当加载libqxcb.so库的时候，还需要加载libxcb-xinerama库
3. 接着切换到报错libxcb.so所在目录，具体操作如下：

```shell
$ cd /home/.../platforms/
# 查看关联内容
$ ldd libxcb.so
```

4. ldd后发现不存在libxcb-xinerama.so.0库
5. 则在对应环境下安装该依赖库，如env39，具体如下：

```shell
(env39)$ sudo apt-get install libxcb-xinerama0

# 安装完成后，再次查看关联内容，发现已经修复问题
(env39)$ ldd libqxcb.so
```

6. 再次启动程序，ok