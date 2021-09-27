### Yield的理解

在python中，yield类似return，但是又有所区别，带yield的函数就是一个生成器，而不是一个函数了，具体如下代码：

```shell
def odd(upper):
    n = 1
    while n < upper:
        if n % 2 != 0:
            yield n
        n += 1
    print("some others")
    return 'done'


g = odd(10)

while True:
    try:
        print(next(g))
    except StopIteration as e:
        print('returned value: ', e.value)
        break
        
# 输出结果如下：
1
3
5
7
9
some others
returned value:  done
```



**<font color=red>Note：</font>**==yield就是 return 返回一个值，并且记住这个返回的位置，下次迭代就从这个位置后开始==

