生成螺旋矩阵（Spiral Matrix）是一个经典的算法问题。它的核心逻辑是：**按照“右 -> 下 -> 左 -> 上”的顺序循环遍历，并在每一轮缩小边界。**

这是一个非常直观的 Python 实现方式：

---

## 1. 核心代码实现

```
def generate_spiral_matrix(n):
    # 初始化一个 n x n 的空矩阵
    matrix = [[0] * n for _ in range(n)]
    # 定义四个边界
    top = 0
    bottom =  n - 1
    left = 0
    right = n - 1
    num = 1
    target = n * n    
    while num <= target:
        # 1. 从左到右
        for i in range(left, right + 1):
            matrix[top][i] = num
            num += 1
        top += 1 # 收缩上边界
        # 2. 从上到下
        for i in range(top, bottom + 1):
            matrix[i][right] = num
            num += 1
        right -= 1 # 收缩右边界
        # 3. 从右到左
        for i in range(right, left - 1, -1):
            matrix[bottom][i] = num
            num += 1
        bottom -= 1 # 收缩下边界
        # 4. 从下到上
        for i in range(bottom, top - 1, -1):
            matrix[i][left] = num
            num += 1
        left += 1 # 收缩左边界
    return matrix
# 打印函数
def print_matrix(matrix):
    for row in matrix:
        print(*(f"{x:2d}" for x in row))
# 测试生成 5x5 矩阵
res = generate_spiral_matrix(5)
print_matrix(res)
```
n=5:

|**y \ x**|**0**|**1**|**2**|**3**|**4**|
|---|---|---|---|---|---|
|**0**|**(0,0)**|**(0,1)**|**(0,2)**|**(0,3)**|**(0,4)**|
|**1**|**(1,0)**|**(1,1)**|**(1,2)**|**(1,3)**|**(1,4)**|
|**2**|**(2,0)**|**(2,1)**|**(2,2)**|**(2,3)**|**(2,4)**|
|**3**|**(3,0)**|**(3,1)**|**(3,2)**|**(3,3)**|**(3,4)**|
|**4**|**(4,0)**|**(4,1)**|**(4,2)**|**(4,3)**|**(4,4)**|

| 1   | 2   | 3   | 4   | 5   |
| --- | --- | --- | --- | --- |
| 16  | 17  | 18  | 19  | 6   |
| 15  | 24  | 25  | 20  | 7   |
| 14  | 23  | 22  | 21  | 8   |
| 13  | 12  | 11  | 10  | 9   |

---

## 2. 逻辑拆解

为了让你更清楚代码是怎么运作的，我们可以把整个过程想象成剥洋葱：

- **边界定义：** 我们维护四个变量 `top`, `bottom`, `left`, `right`。它们代表了当前尚未填充数字的区域。
    
- **循环移动：** 1. 在第一行从左往右走到底，结束后这一行就“废了”，所以 `top += 1`。 2. 在最右列从上往下走到底，结束后这一列就“废了”，所以 `right -= 1`。 3. 以此类推，直到 `num` 超过 n2。
    
- **复杂度：** 时间复杂度是 O(n2)，因为我们需要访问矩阵中的每一个格子。
    

---

## 3. 常见变体：读取螺旋矩阵

如果你已经有一个现成的矩阵，想要按螺旋顺序读出数字，逻辑也是一样的：

```
def spiralOrder(matrix):
    res = []
    while matrix:
        # 1. 取出第一行
        res += matrix.pop(0)
        # 2. 旋转矩阵（逆时针旋转 90 度，方便下次取第一行）
        matrix = list(zip(*matrix))[::-1]
    return res
```

> **小贴士：** 这种“旋转取值”的方法虽然代码极简（Pythonic），但在处理超大规模数据时，频繁的 `zip` 和切片操作效率不如第一种边界法。
