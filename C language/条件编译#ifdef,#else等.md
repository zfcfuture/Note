### 条件编译#ifdef,#else等

#### 情况1：

```c
#ifdef _XXXX
程序段1
#else
程序段2
#endif
    
// 这表明如果标识符_XXXX已被#define命令定义过，则对程序段1进行编译；否则对程序段2进行编译
```

#### 情况2：

```c
#ifndef _XXXX
程序段1
#else
程序段2
#endif
    
// 这里使用的是#ifndef，表示in not define，和前者相反
```

#### 情况3：

```c
#if 常量
程序段1
#else
程序段2
#endif
// 这里表示，如果常量为真，就执行程序段1，否则执行程序段2
```

#### 头文件中的ifdef用法：

头文件的内容建议都放在#ifdef和#endif中。因为如果两个.c文件都include了同一个头文件，在编译时这两个c文件要一同编译成一个可执行文件，会造成大量声明冲突。

例如：

#ifdefine XXX

#define XXX

#endif 

