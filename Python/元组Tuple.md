### 元组Tuple

Tuple也是有序的列表，和list非常累死，但是tuple<font color=red>一旦初始化就不能修改</font>,比如：

`classmates = ('Michael', 'Bob', 'Tracy')`

但是，元组是不可更改的，也就意味着它没有`append(), insert()`这样的方法，其它获取元素的方法和`list`是一样的，可以使用`classmates[0], classmates[1]`，但不能赋值成另外的元素

<font color=red>**Notice**</font>: 

- `tuple`虽然不可变，但是它更安全，所以如果可能，建议用`tuple`代替`lsit`
- 当定义一个`tuple`的时候，它的元素就必须被确定下来

- `tuple`可以为空，可以写成：`t = ()`
- 当定义只有一个元素的`tuple`的时候，为了避免和数学运算产生歧义，在定义时必须加一个逗号来进行区分，可以写成 `t = (1,)`



可以使用`tuple + list`来实现 “可变的” 元组，如下：

表面上看，`tuple`的元素确实变了，但其实变的不是`tuple`的元素，而是`list`的元素。`tuple`一开始指向的`list`并没有改成别的`list`，所以，`tuple`所谓的“不变”是说，`tuple`的每个元素，指向永远不变。即指向`'a'`，就不能改成指向`'b'`，指向一个`list`，就不能改成指向其他对象，但指向的这个`list`本身是可变的！

```python
>>> t = ('a', 'b', ['A', 'B'])
>>> t[2][0] = 'X'
>>> t[2][1] = 'Y'
>>> t
('a', 'b', ['X', 'Y'])
```

![tuple-0](https://www.liaoxuefeng.com/files/attachments/923973516787680/0)

![tuple-1](https://www.liaoxuefeng.com/files/attachments/923973647515872/0)

