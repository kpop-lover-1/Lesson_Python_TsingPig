# 🎯 课时3：排序 —— `enumerate` 函数详解

## ✅ 1. `enumerate()` 是什么？

> **`enumerate()` 是 Python 的内置函数**，用于在遍历可迭代对象（如列表、元组、字符串）时，**同时获取元素的索引和值**，无需手动维护计数器。

### 🔧 基本语法：

python

编辑

```
for index, item in enumerate(iterable, start=0):
    # 处理 index 和 item
```

- `iterable`：要遍历的对象（如列表）
- `start`：起始索引，默认是 0，也可以设为其他值（比如 1）

---

## ✅ 2. 示例：遍历水果列表

python

编辑

```
fruits = ['苹果', '香蕉', '橙子']

for idx, fruit in enumerate(fruits):
    print(f"索引: {idx}, 水果: {fruit}")
```

### ✅ 输出：

text

编辑

```
索引: 0, 水果: 苹果
索引: 1, 水果: 香蕉
索引: 2, 水果: 橙子
```

### 💡 解读：

- `enumerate(fruits)` 返回一个生成器，每次返回 `(索引, 元素)` 对
- `idx` 是当前元素的下标（从 0 开始）
- `fruit` 是当前元素的值

👉 这样就不用自己写 `i = 0; i < len(fruits); i += 1`，更简洁！

---

## ✅ 3. `enumerate()` 与 `zip()` 结合使用

### 🌟 场景：同时遍历多个列表，并获取索引

python

编辑

```
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]

for idx, (name, age) in enumerate(zip(names, ages)):
    print(f"用户{idx}: {name}, 年龄: {age}")
```

### ✅ 输出：

text

编辑

```
用户0: Alice, 年龄: 25
用户1: Bob, 年龄: 30
用户2: Charlie, 年龄: 35
```

### 🔍 分析：

- `zip(names, ages)` 将两个列表“打包”成元组对：`[("Alice",25), ("Bob",30), ...]`
- `enumerate(...)` 给每个元组加上索引
- 所以 `(idx, (name, age))` 表示：第 `idx` 个用户，名字叫 `name`，年龄是 `age`

---

## ✅ 4. 在【力扣 406】中如何用 `enumerate`？

题目：[406. 根据身高重建队列](https://leetcode.com/problems/reconstruct-queue/)

输入：`people = [[7,0], [4,4], [7,1], [5,0], [6,1], [5,2]]`

目标：按规则还原队列，使得每个人前面有 `k` 个比他高的人。

### ✅ 正确解法（关键步骤）：

python

编辑

```
def reconstructQueue(self, people: List[List[int]]) -> List[List[int]]:
    # 1. 排序：先按身高降序，再按 k 升序
    people.sort(key=lambda x: (-x[0], x[1]))
    
    res = []
    for i, p in enumerate(people):  # ← 这里用了 enumerate
        h, k = p[0], p[1]
        if k == i:
            res.append(p)
        else:
            res.insert(k, p)
    return res
```

### 🔍 为什么用 `enumerate`？有什么好处？

表格

|优势|说明|
|---|---|
|✅ 自动获取索引|我们不需要手动定义 `i = 0`，也不需要 `i += 1`|
|✅ 简洁清晰|直接知道当前处理的是第几个元素|
|✅ 逻辑清晰|`i` 是排序后的位置，而 `k` 是目标插入位置，我们比较 `k == i` 是否成立|

#### 📌 关键点：

- `i` 是当前人在**排序后的列表中的位置**
- `k` 是这个人希望在最终队列中前面有多少个更高的人
- 因为我们是**从高到低**处理的，所以已经插入的人都比当前人高
- 所以只要把当前人插到 `res[k]` 位置，就能保证前面正好有 `k` 个比他高的人

---

## ✅ 5. 总结：`enumerate` 的三大用途

表格

|用途|示例|说明|
|---|---|---|
|🔹 获取索引和值|`for i, x in enumerate(lst):`|遍历列表时自动带索引|
|🔹 多列表同步遍历|`for i, (a,b) in enumerate(zip(A,B)):`|同时遍历多个列表，还带索引|
|🔹 控制插入位置|如 406 题中用 `i` 判断是否插入|利用索引做逻辑判断|

---

## ✅ 6. 小练习巩固（你可以试试）

### 练习 1：打印每个字母的索引和字符

python

编辑

```
word = "hello"
for idx, char in enumerate(word):
    print(f"位置 {idx}: {char}")
```

### 练习 2：给名单编号

python

编辑

```
students = ["张三", "李四", "王五"]
for i, name in enumerate(students, start=1):
    print(f"{i}. {name}")
```

输出：

text

编辑

```
1. 张三
2. 李四
3. 王五
```

---

## ✅ 7. 记忆口诀

> **`enumerate` = “枚举” + “索引”**  
> 一边走，一边数，每一步都告诉你：“这是第几个，是什么。”

---

## ✅ 8. 笔记建议（可以贴在墙上）

📌 **`enumerate()` 使用模板**

python

编辑

```
for index, value in enumerate(iterable, start=0):
    print(f"第 {index} 个元素是: {value}")
```

📌 **`enumerate + zip` 模板**

python

编辑

```
for idx, (a, b) in enumerate(zip(list1, list2)):
    print(f"第 {idx} 对: a={a}, b={b}")
```