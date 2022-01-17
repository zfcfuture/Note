### atoi函数详解

`atoi()`函数用来==将字符串转换成整数==(int)，它的原型为：

```c
#include <stdlib.n>
int atoi(const char *str)
```

【函数说明】`atoi()` 函数会扫描参数 str 字符串，跳过前面的空白字符（例如空格，tab缩进等），直到遇上数字   或正负符号才开始做转换，而再遇到非数字或字符串结束时('\0')才结束转换，并将结果返回。

【返回值】返回转换后的整型数；如果str不能转换成int或者str为空的字符串，那么将返回0

<font color=red>**Note**</font>：ANSI C 规范定义了 [stof()](http://c.biancheng.net/cpp/html/124.html)、[atoi()](http://c.biancheng.net/cpp/html/125.html)、[atol()](http://c.biancheng.net/cpp/html/126.html)、[strtod()](http://c.biancheng.net/cpp/html/128.html)、[strtol()](http://c.biancheng.net/cpp/html/129.html)、[strtoul()](http://c.biancheng.net/cpp/html/130.html) 共6个可以将字符串转换为数字的函数，同时在 C99 / C++11 规范中又新增了5个函数，分别是 `atoll()`、`strtof()`、`strtold()`、`strtoll()`、`strtoull()`

