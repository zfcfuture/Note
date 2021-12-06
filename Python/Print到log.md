### Print到log

在某些情况下，我们需要将print输出到控制台或者终端的内容打印到<font color=red>*Log*</font>日志中，具体如下：

```python
mylog = open('recode.log', mode = 'a',encoding='utf-8')
for i in range(10):
    print("sdjlahjljag", file=mylog)
mylog.close()
```

或者，也可以使用下面这种方式：

```python
import sys
 
sys.stdout = open('recode.log', mode = 'w',encoding='utf-8')
 
for i in range(10):
    print("sdjlahjljag")
```

