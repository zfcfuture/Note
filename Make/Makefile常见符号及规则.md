### Makefile常见符号及规则

无论是在`Linux`还是在`Unix`环境中，make都是一个非常重要的编译手段。对于一个包括几百个源文件的应用程序，使用make工具及其描述文件makefile就可以简洁明快地理顺各个源文件之间纷繁复杂的相互关系

#### 1.  运行流程

```makefile
all：test1.o test2.o
test1.o:test1.c
    gcc -o test1.o test1.c
 
test2.o:test2.c
    gcc -o test2.o test2.c
```

首先要明确一点的是，==如果没有指定输出项目的时候Make会自动找到makefile中第一个目标中没有通配符的目标进行构造==，所以该makefile的运行流程为：

1.  构造all，发现需要test1.o和test2.o
2.  寻找Makefile文件中能匹配test1.o和test2.o的规则
3.  找到test1.o的规则并且知道test1.c存在，运行下面的命令
4.  同步骤3构造出test2.o
5.  现在构造all的源文件已经齐全，构建all

#### 2.  特殊符号

**$@**：目标的名字

**$^**：构造所需文件列表中所有文件的名字

**$<**：构造所需文件列表

**$?**：构造所需文件列表中更新过的文件



例1：其中 $@ 就是test1.o，$< 就是test1.c

```makefile
test1.o:test1.c
    gcc -o $@ $<
```

例2：其中 $^ 就是test1.c test2.c

```makefile
test.o: test1.c test2.c
	gcc -o $@ $^
```

