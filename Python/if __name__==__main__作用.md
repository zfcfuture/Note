在python中，经常会用到一句话：`if __name__ == "__main__"`，这句话的主要作用是什么呢？

它和C语言以及java中的main函数长的很像，甚至在功能上也很类似，但终归是有所区别

先说结论：它的作用就是为了区分“自己”和“他人”，让本文件中的部分功能不对其它引用自己的文件直接暴露

例如对于文件test1.py，直接运行它的话，结果应当如下：

```python
def func1():
    print("here is function one")

def func2():
    print("here is function two")

print("i am test1")

if __name__ == "__main__":
    func1()
    func2()
    
# 输出结果
# i am test 1
# here is function one
# here is function two
```

但如果此时有个test2.py的文件，引用了test1.py再运行的话，结果就变成了下面这样：

```python
import test1

print("i am test2")

# 输出结果
# i am test1
# i am test2
```

