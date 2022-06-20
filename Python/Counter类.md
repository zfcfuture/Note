### Python中的Counter类

如果当前需求是围绕数据的计数功能展开，那Counter类可以很好地应对该需求

#### 1.  计数

```python
import numpy as np
from collections import Counter

nums = np.random.random_integers(0, 10, 100)
counter = Counter(nums)
print(counter)

# 输出
# Counter({1: 12, 5: 12, 3: 11, 6: 10, 7: 9, 8: 9, 10: 9, 2: 8, 9: 8, 4: 8, 0: 4})
```

#### 2.  显示前n个最多元素

```python
nums = np.random.random_integers(0, 10, 100)
count = Counter(nums)
print(count.most_common(3))

# 输出
# [(0, 13), (1, 13), (8, 12)]
```

#### 3.  循环索引

```python
nums = np.random.random_integers(0, 10, 100)
count = Counter(nums)
for i in count.elements():
    print(i)
```

![image-20220620220356174](C:\Users\zfcfu\AppData\Roaming\Typora\typora-user-images\image-20220620220356174.png)