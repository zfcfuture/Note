### puts与fputs函数

#### 1.  puts

`puts`函数的原型如下：

```c
int puts(const char *str)
```

`puts`函数的主要功能是：向标准的输出设备（屏幕）写入字符串并换行，与`printf("%s\n", str)`作用相同，不同的是，==`puts`只能输出字符串，输出时遇到`'\0'`字符才停止==。故非字符串或无`'\0'`字符的字符数组最好不要使用该打印函数，否则无法正常结束。



#### 2.  fputs

`fputs`函数的原型如下：

```c
int fputs(const char *str, FILE *stream)
```

不同于`puts`函数，`fputs`函数的主要是==用来向指定的文件写入一个字符串==（不换行）。当然，给它指定`stdout`参数则会将字符串输出到屏幕，如下代码所示：

```c
int main(void)
{
    char str[] = {'H', 'E', 'L', 'L', 'O', '\0'};
    fputs(str, stdout);
    return 0;
}

输出:  HELLO
```

输出显示只是使用`fputs`函数功能的一种特例，其主要功能还是将字符串写入文件，如下：

```c
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
    FILE *fp = NULL;
    fp = fopen("myfile.txt", "wb");
    if (fp == NULL)
    {
        printf("can not access this file\n");
        exit(1);
    }
    fputs("this is a test", fp);
    fclose(fp);
    fp = NULL;
    return 0;
}
```

运行上述代码会将字符串"this is a test"写入myfile.txt中