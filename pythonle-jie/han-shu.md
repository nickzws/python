# 调用函数

abs\(\)  求绝对值,参数必须是一个数值

max\(\)  取最大值

min\(\)   取最小值

help\(abs\)  查看用法

报错：TypeError\(\)

## 数据类型转换

1. int\(\)
2. float\(\)
3. str\(\)
4. bool\(\)

函数名其实就是指向一个函数对象的引用，完全可以把函数名赋给一个变量，相当于给这个函数起了一个“别名”：

```
>>> a = abs # 变量a指向abs函数
>>> a(-1) # 所以也可以通过a调用abs函数
1
```

# 定义函数

在Python中，定义一个函数要使用def语句，依次写出函数名、括号、括号中的参数和冒号:，然后，在缩进块中编写函数体，函数的返回值用return语句返回。

```
def my_abs(x):
    if x >= 0:
        return x
    else:
        return -x
```

果没有return语句，函数执行完毕后也会返回结果，只是结果为None。return None可以简写为return。

### 空函数

如果想定义一个什么事也不做的空函数，可以用pass语句：目的是为了占位，程序走下去

```
def nop():
    pass
```

### 参数检查

调用函数时，如果参数个数不对，Python解释器会自动检查出来，并抛出**TypeError,**但是如果参数类型不对，Python解释器就无法帮我们检查.

所以在开发过程中，我们可以先判断类型：数据类型检查可以用内置函数**isinstance\(\)**实现

```
def my_abs(x):
    if not isinstance(x, (int, float)):
        raise TypeError('bad operand type')
    if x >= 0:
        return x
    else:
        return -x
```

### 返回多个值

import math语句表示导入math包，并允许后续代码引用math包里的sin、cos等函数。

```
import math

def move(x, y, step, angle=0):
    nx = x + step * math.cos(angle)
    ny = y - step * math.sin(angle)
    return nx, ny
```

来看看返回值

```
>>> x, y = move(100, 100, 60, math.pi / 6)
>>> print(x, y)
151.96152422706632 70.0
```

实际返回的值

```
>>> r = move(100, 100, 60, math.pi / 6)
>>> print(r)
(151.96152422706632, 70.0)
```

返回值实际上是一个tuple！语法上返回一个tuple可以省略括号，而多个变量可以同时接收一个tuple，按位置赋给对应的值，所以，Python的函数返回多值其实就是返回一个tuple，但写起来更方便。

计算平方根可以调用math.sqrt\(\)函数：

```
>>> import math
>>> math.sqrt(2)
1.4142135623730951
```





Python的函数定义非常简单，但灵活度却非常大。除了正常定义的必选参数外，还可以使用默认参数、可变参数和关键字参数，使得函数定义出来的接口，不但能处理复杂的参数，还可以简化调用者的代码。

### 位置参数





