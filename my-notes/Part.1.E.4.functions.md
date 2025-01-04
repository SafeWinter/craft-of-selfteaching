# 5.4 函数入门



## 1 print 函数

语法：

```python
import sys
print(*object, sep=' ', end='\n', file=sys.stdout, flush=False)
```

其中 `*object` 前的 `*` 表示 **能够接收很多值的位置参数**。

## 2 关键字参数 Keyword Arguments

`Python` 中的参数主要有两大类：

- 位置参数（Positional Argument）：官方文档中缩写为 `arg`
- 关键字参数（Keyword Argument）：官方文档中缩写为 `kwarg`

概念：在函数定义中，带有 `=` 的是设定了默认值的参数，即 **关键字参数（Keyword Argument）**。其他参数则属于 **位置参数（Positional Argument）**。



## 3 位置参数 Positional Arguments

例如 `divmod(a, b)`：

```python
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all"

divmod(11, 3) # (3, 2)
a, b = divmod(11, 3)
a # 3
b # 2

divmod(3, 11) # (0, 3)
a, b = divmod(3, 11)
a # 0
b # 3
```



## 4 可选位置参数 Optional Positional Arguments

例如 `pow()` 函数：

```python
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all"

# pow(x, y[, z])
pow(2, 3) # 8
pow(2, 3, 4) # 0
```

其中 `z` 为模数，性能较 `pow(x, y) % z` 更优。

另一个例子是 `exec(object[, globals[, locals]])`



## 5 Class 类也是函数

本质上讲，`Class` 类是一种特殊的函数。

`bool` 类是 `int` 的一个子类（The `bool` class is a subclass of int (See Numeric Types -- int, float, complex).），且不可再继承其他子类。