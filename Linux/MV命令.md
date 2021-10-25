### MV命令

Linux中，mv可以移动文件到指定目录下

#### 1.  移动多个文件

现有一种情况，如果需要移动多个文件到指定目录，可以使用如下方式：

```shell
# a.py b.py c.py d.c f.c g.txt test.sh移动至test目录下

$ mv a.py b.py c.py d.c f.c g.txt test.sh -t ~/test/
```

