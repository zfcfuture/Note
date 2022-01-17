### memset函数详解

`memset()`函数的作用是<font color=red>初始化内存</font>，通过直接操作内存空间来为新申请的内存进行初始化工作

该函数的原型如下：

```c
#include <string.h>
void *memset(void *s, int c, unsigned long n);
```

函数的功能是：将指针变量s所指向的前n字节的内存单元用一个“整数”c替换



<font color=red>**Note**</font>: 

- c是int型，s是void*型的指针变量，所以他们可以为任何类型的数据进行初始化
- 一般使用“0”进行初始化内存单元，通常是给<font color=green>较大数组或结构体</font>进行初始化，不适用变量
- 如果是对指针变量所指向的内存单元进行清零初始化，那么<font color=green>一定要先对这个指针变量进行初始化</font>，即一定要先让它==指向某个有效的地址==。而且用memset给指针变量如p所指向的内存单元进行初始化时，n 千万别写成 `sizeof(p)`，这是新手经常会犯的错误。因为 p 是指针变量，不管 p 指向什么类型的变量，sizeof(p) 的值都是 4。

