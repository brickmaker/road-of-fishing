# Python bisect使用

Bisect是一个处理有序数组的库，用二分查找找到想要定位的index，在实际使用中还是非常好用的，也有一小点点坑。

文档：https://docs.python.org/3/library/bisect.html

源码：https://github.com/python/cpython/blob/3.8/Lib/bisect.py

****

## `bisect_left(a, x)`

找到可以把x插入的地方的index，如果a中存在x，则返回x左侧的index

不考虑边界情况的话，`a[index] < x`, `a[index] = x`, `a[index] < x` 都有可能

```py
In [12]: a
Out[12]: [1, 3, 5]

In [13]: bisect.bisect_left(a, 0)
Out[13]: 0

In [14]: bisect.bisect_left(a, 1)
Out[14]: 0

In [15]: bisect.bisect_left(a, 2)
Out[15]: 1

In [16]: bisect.bisect_left(a, 3)
Out[16]: 1

In [18]: bisect.bisect_left(a, 5)
Out[18]: 2

In [19]: bisect.bisect_left(a, 6)
Out[19]: 3
```

## `bisect(a, x)` / `bisect_right(a, x)`

找到可以把x插入的地方的index，如果a中存在x，则返回x右侧的index

不考虑边界情况的话，`a[index] < x`, `a[index] > x` 都有可能

```py
In [5]: a
Out[5]: [1, 3, 5]

In [6]: bisect.bisect(a, 0)
Out[6]: 0

In [7]: bisect.bisect(a, 1)
Out[7]: 1

In [8]: bisect.bisect(a, 2)
Out[8]: 1

In [9]: bisect.bisect(a, 3)
Out[9]: 2

In [10]: bisect.bisect(a, 5)
Out[10]: 3

In [11]: bisect.bisect(a, 6)
Out[11]: 3
```

可以发现，两者只有在处理已有元素的查找时有差异：

```py
In [20]: b = [1, 2, 2, 3]

In [21]: bisect.bisect(b, 2)
Out[21]: 3

In [22]: bisect.bisect_left(b, 2)
Out[22]: 1

# [1, 2, 2, 3]
#     |     |
#   left  right
```

## 使用 `bisect` 二分查找

eq：

```py
def find(a, x):
    i = bisect_left(a, x)
    if i < len(a) and a[i] == x:
        return i
    else:
        return -1
```

lt:

```py
def find_lt(a, x):
    i = bisect_left(a, x) - 1
    if i >= 0:
        return i
    else:
        return -1
```

gt:

```py
def find_gt(a, x):
    i = bisect_right(a, x)
    if i < len(a):
        return i
    else:
        return -1
```

lte:

```py
def find_lte(a, x):
    i = bisect_right(a, x) - 1
    if i >= 0:
        return i
    else:
        return -1
```

gte:

```py
def find_gte(a, x):
    i = bisect_left(a, x)
    if i < len(a):
        return i
    else:
        return -1
```

### 多元素比较

在实际使用时，有时候会排序数组，本来跟单个元素没有什么两样，但是当只想比较第一个key而忽略后续比较的时候，就比较难受。

例如，我们希望有的效果是：`[3, 0] = [3, 1]` 而不是 `[3, 0] < [3, 1]`，因此在考虑比较的时候会与上述的有些不同。

一种解决方法是，把要比较的key拿出来，得到index之后再定位指定元素。这也是比较推荐的方法，比较踏实，没有trick。

另一种是，可以对key做改动，比如我们想lte搜索lte`key=3`, 可以通过搜索lt`key=4`，转变之后就不存在问题了，不过不推荐使用。