## 字典dict与集合set

### 一.  dict

使用<font color=red>**K-V键值对**</font>的形式存储，具有极快的查找速度，具体实现如下：

```python
>>> d = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
>>> d['Michael']
95
```

#### 1.  存取数据

```python
#1. K-V是一一对应的
>>> d['Adam'] = 67
>>> d['Adam']
67

#2. 如果key不存在，dict就会报错
>>> d['Thomas']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'Thomas'
    
#3. 要避免key不存在的错误，有两种办法
# 第一种办法
>>> 'Thomas' in d
False

# 第二种办法，使用get()，不存在就返回None或者指定值
>>> d.get('Thomas')
>>> d.get('Thomas', -1)
-1
```

#### 2.  删除数据

要删除一个key，用`pop(key)`方法，对应的value也会从dict中删除

```python
>>> d.pop('Bob')
75
>>> d
{'Michael': 95, 'Tracy': 85}
```

#### 3.  注意事项

- dict内部存放的顺序和key的放入顺序无关
- dict查找和插入速度快，但是占用内存更大，空间换时间
- dict是K-V键值对形式存储，所以要确保key的唯一性，==key就必须要是不可变==的，在python中，字符串、整数等都是不可变的，可以作为key，而list是可变的，就不能作为key



### 二.  Set

set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key，要创建一个set，需要提供一个list作为输入集合：

```python
>>> s = set([1, 2, 3])
>>> s
{1, 2, 3}
```

 重复的元素在set中自动过滤：

```python
>>> s = set([1, 1, 2, 2, 3, 3])
>>> s
{1, 2, 3}
```

插入删除：

```python
# 插入
>>> s.add(4)
>>> s
{1, 2, 3, 4}
>>> s.add(4)
>>> s
{1, 2, 3, 4}

# 删除
>>> s.remove(4)
>>> s
{1, 2, 3}
```

