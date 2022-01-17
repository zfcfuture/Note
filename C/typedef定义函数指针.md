### typedef定义函数指针

使用typedef定义函数指针更加直观方便；函数指针通常用来实现回调，也可以用来对模块调用以函数表的形式进行优化

例：定义一个原型为`int Fun(int a);`的函数指针：

`typedef int (*PTRFUN)(int aPara);`

<font color=red>typedef的功能是定义新的类型</font>：这里定义了一种PTRFUN的类型，并定义这种类型为指向某种函数的指针，这种函数以一个int为参数并返回int类型。后面就可以像使用int，char一样使用PTRFUN了。

