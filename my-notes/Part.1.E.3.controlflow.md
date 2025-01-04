# 5.3 流程控制



## 1 关于质数判定函数中平方根加 1 的原因

优化算法中，遍历的上边界可能取到平方根，故不能直接作 `range()` 函数的上边界（左闭又开区间）



## 2 验证 range 中 stop 和 step 反向时的输出结果

```python
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all"

list(range(0, -10, 2)) # []
```



## 3 Python 循环特有的 else 用法

`for` 语句块结尾处的 `else` 语句块（L8），在没有 `break` 发生的情况下才会运行：

```python
for n in range(2, 100):
    if n == 2:
        print(n)
        continue
    for i in range(2, n):
        if n % i == 0:
            break
    else:
        print(n)  # 如果直到整个循环结束都没有发生 break，才执行一次 print(n)
```

对比：

```python
for n in range(2, 100):
    if n == 2:
        print(n)
        continue
    for i in range(2, n):
        if (n % i) == 0:
            break
        print(n)  # 相当于对 range(2, n) 中的每个 i 执行一次 print(n)
```

L8 中的注释不够准确，仅适用于当前 n 为质数的情况；当 n 为合数时，只要 `(n % i) == 0` 不成立，此时的 `n` 都会打印出来，例如 9（`i` 为 2 时）、15（`i` 为 2 时），这样的例外情况还有很多，都是部分执行 `print(n)`。

> [!note]
>
> **正确说法**：（待提 `issue`）
>
> ```python
> print(n)  # 相当于循环到质数 n 时，对 range(2, n) 中的每个 i 执行一次 print(n)；否则可能部分执行 print(n)，如 9、15、21 等
> ```


## 4 

