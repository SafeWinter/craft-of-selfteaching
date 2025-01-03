## 1.2 布尔运算

深刻理解本书从布尔逻辑开始学习 `Python` 的原因：相比计算器，计算机因为 **可编程** 而更为强大；而 **可编程** 的核心，即 *布尔运算* 及其相应的 *流程控制*。没有布尔运算能力就无法实现流程控制，没有流程控制的代码就只能 “按顺序执行”，这就 “很不智能”（如普通计算器）。


对第一段示例代码的理解：

```python
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all"
# 请暂时忽略以上两行……

1 == 2
1 != 2
```

其中的 `ast_node` 表示 **抽象语法树（Abstract Syntax Tree）节点**，头两句表示对当前单元格的所有表达式求值。

> **ChatGPT（Poe）的回复如下：**
>
> **【问】这两段 Python 代码是什么意思？**
>
> **ChatGPT：** 这两段 `Python` 代码的作用是调整 `IPython`（`Jupyter Notebook` 等环境中的交互式 `Python` 解释器）的行为，具体来说：
>
> 1. `from IPython.core.interactiveshell import InteractiveShell`：
>    - 这一行代码导入了 `InteractiveShell` 类。`InteractiveShell` 是 IPython 的核心组件之一，负责处理交互式输入和输出。
> 2. `InteractiveShell.ast_node_interactivity = "all"`：
>    - 这一行代码设置了 `ast_node_interactivity` 属性为 `"all"`。该设置决定了在交互式环境中，代码块执行后显示哪些结果。
>    - 当设置为 `"all"` 时，代码块中的所有表达式的结果都会被显示，而不仅仅是最后一个表达式的结果。这在调试或检查多个值时非常有用。
>
> 总结来说，这两行代码的目的是让用户在 IPython 环境中执行代码时，能够看到多个表达式的输出结果。
>
> **【问】ast_node 是什么？ast是什么术语的全称吗？**
>
> **ChatGPT：** ast 是 "Abstract Syntax Tree"（抽象语法树）的缩写。抽象语法树是一种数据结构，用于表示源代码的结构和语法。它将代码分解成树形结构，其中每个节点代表代码中的一个基本构造（如变量、操作符、表达式等）。
>
> 在 `Python` 中，ast 模块提供了对抽象语法树的访问和操作功能。通过使用 ast 模块，开发者可以分析、修改或生成 Python 代码。
>
> 在 `InteractiveShell` 中，ast_node_interactivity 是一个属性，用于控制在交互式环境中代码执行后显示的输出内容，基于抽象语法树的节点结构进行管理。



###  1.2.2 逻辑操作符

`Python` 有个特殊的逻辑操作符：`in` ——

```python
print('a' in 'basic');  # True
```

对应地，`JavaScript` 也有 `in` 相关的语法，不过是用于对象属性的判定：

```javascript
console.log('a' in {a: 1, b: 2});  // true
```



## 1.3 流程控制

生成指定序列的随机数：

```python
import random
r = random.randrange(1, 1000)
```

其中，随机数的值域为 `[1, 1000)`



## 1.4 所谓算法

学写代码的门槛貌似很高 —— 这不过是另一个错觉而已。

学写代码如同识字 ——

> 小学初中高中加起来十来年，我们才掌握了基本的阅读能力；可最终，即便是本科毕业、研究生毕业，真的能写出一手好文章的人还是少之又少一样 —— 因为用文字值得写出来的是 **思想**，用代码值得写出来的是 **创造**，或者起码是有意义的问题的有效解决方案。**有思想，能解决问题，是另外一门手艺 —— 需要终生精进的手艺。**



## 1.6 细节补充

- `Python` 拥有一个特殊的算术运算符：求商运算符 `//`，例如：

  ```python
  a = 10
  b = 3
  c = -3
  print(a // b) # 3
  print(a // c) # -4
  ```

- `Python` 最佳实践：

  - 构建语句块时，同一文件内不建议混合使用空格和制表符 —— 要么全用空格，要么全用制表符。
  - `Python` 社区普遍遵循 `PEP 8` 规范：类名通常使用驼峰式命名（`CamelCase`），而变量和方法名使用小写字母加下划线（`snake_case`）。这种命名约定帮助开发者快速区分变量、方法和类，增强了代码的可理解性。