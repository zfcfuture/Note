## 列表List

python的内置数据类型，list是一种<font color=red>可变、有序</font>的集合，可以随时添加和删除其中的元素

表现形式如下：`classmates = ['Michael', 'Bob', 'Tracy']`

#### 1.  基本操作

**列表长度**：`len(list_name)`



**列表访问**：可以用索引来访问`list`中每一个位置的元素，如`list[0]  list[1]`等

​				   访问最后一个元素可以使用`list[-1]`，以此类推，倒数第二为`list[-2]`...

**列表增删**：`list`是一个可变的有序表，增删元素方式如下：

- 追加元素到末尾：`list.append('xxx')`
- 插入元素到指定位：`list.insert(1, 'jack')`
- 删除末尾元素：`list.pop()`
- 删除指定位置元素：`list.pop(i)`
- 元素替换：`list[i] = 'xxx'`

#### 2.  列表特性

(1)  列表中元素的数据类型可以不同，比如：

​      `L = ['Apple', 123, True]`

(2)  列表元素可以是另一个`list`

```python
>>> s = ['python', 'java', ['asp', 'php'], 'scheme']
>>> len(s)
4

>>> p = ['asp', 'php']
>>> s = ['python', 'java', p, 'scheme']
# 如果想拿到'php' 可以用 p[1]或者s[2][1]
```

(3)  如果`list`中一个元素也没有，就是一个空的list，它的长度为0
