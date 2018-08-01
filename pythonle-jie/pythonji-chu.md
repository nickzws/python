## 基础知识

1. 以 \# 开头的语句是注释
2. 语句以冒号 ：结尾时，缩进的语句视为代码块。
3. 4个空格 缩进
4. Python程序是大小写敏感的

```
a = -1
if a >= 0:
    print(a)
else:
    print(-a)
```

## 数据类型

在Python中，能够直接处理的数据类型有以下几种：

### 整数

任意大小的整数（负整数）、十六进制：

```
1，100，-8080，0
0xff00，0xa5b4c3d2
```

### 浮点数

表示小数，四舍五入可能有误差

```
1.23，3.14，-9.01
1.23e9  1.2e-5
```

### 字符串

字符串是以单引号'或双引号"括起来的任意文本，比如'abc'，"xyz"等等。请注意，''或""本身只是一种表示方式，不是字符串的一部分，因此，字符串'abc'只有a，b，c这3个字符。

如果`'`本身也是一个字符，那就可以用`""`括起来，比如`"I'm OK"`包含的字符是6个字符

字符串内部既包含'又包含"

```
print('I\'m \"ok\" !')     I'm "ok" !
```

#### 字符串的转义问题

转义字符\可以转义很多字符，比如\n表示换行，\t表示制表符，字符\本身也要转义，所以\表示的字符就是\，r' '原样输出，比较多的\n很影响阅读，建议简化成 \`\`\`````...```的格式````

```
# print('I\'m learning \n python ')  # \n
# print('\\\n\\') #\\ \n
print('\\\t\\')  #\    \
print(r'\\\t\\') #\\\t\\

print(
   '''
    line1 
    line2 
    line3 
   '''
)

print(r'''hello,\n
world ''')
```

## 布尔值

* 两种（True、False），严格区分大小写

```
>>> True
True
>>> False
False
>>> 3>2
True
>>> 5<3
False
>>>
```

* 布尔值可以用and、or和not运算。

* and运算，所有都为True才是 True

* or运算是或运算，只要其中有一个为True，or运算结果就是True

* not运算是非运算，它是一个单目运算符，把True变成False，False变成True：

## 空值

None，特殊的值，特殊的空值，不是0，0还是有意义的。此外，Python还提供了列表、字典等多种数据类型，还允许创建自定义数据类型，我们后面会继续讲到。

## 变量

可以是数字也可以是任意数据类型。

变量在程序中就是用一个变量名表示了，变量名必须是大小写英文、数字和`_`的组合，且不能用数字开头，比如：

```
a = 1
t_007 = 'T007'
Answer = True
```

**在Python中，等号**`=`**是赋值语句,Python同样是从右到左运行。**

```
x = 10
x = x + 2
```

**从内存角度看Python解释器a = 'ABC'**

1. 在内存中创建了一个`'ABC'`的字符串；
2. 在内存中创建了一个名为`a`的变量，并把它指向`'ABC'`。

## 常量

1. 常量就是不能变的变量
2. 在Python中，通常用全部大写的变量名表示常量

Python中除法有两种：整除`/`和地板除`//`

```
     整数的除法是精确的，/得到的是浮点数，即使是整除  9/3  3.0   9//3 3
```

取余数 %   ，得到两个整数相除的余数   10 % 3  1

## 字符编码

因为计算机只能处理数字，如果要处理文本，就必须先把文本转换为数字才能处理。最早的计算机在设计时采用8个比特（bit）作为一个字节（byte），所以，一个字节能表示的最大的整数就是255（二进制11111111=十进制255），如果要表示更大的整数，就必须用更多的字节。比如两个字节可以表示的最大整数是65535，4个字节可以表示的最大整数是4294967295。

由于计算机是美国人发明的，因此，最早只有127个字符被编码到计算机里，也就是大小写英文字母、数字和一些符号，这个编码表被称为ASCII编码，比如大写字母A的编码是65，小写字母z的编码是122。

但是要处理中文显然一个字节是不够的，至少需要两个字节，而且还不能和ASCII编码冲突，所以，中国制定了`GB2312`编码，用来把中文编进去。

你可以想得到的是，全世界有上百种语言，日本把日文编到`Shift_JIS`里，韩国把韩文编到`Euc-kr`里，各国有各国的标准，就会不可避免地出现冲突，结果就是，在多语言混合的文本中，显示出来会有乱码

ASCII编码  美国

GB2312编码 中国

因为中文已经超过了ASCII的长度（8位），需要两个字节  ，01001110 00101101，如此一来，如果把ASCII编码的A用Unicode编码，只需要在前面补0就可以，因此，A的Unicode编码是00000000 01000001。这样会导致存储空间增加，

utf-8  可变长编码   字母一个字节，汉子三个字节，生僻字4-6字节

### Python的字符串

在最新的Python 3版本中，字符串是以Unicode编码的，也就是说，Python的字符串支持多语言

* `ord()`函数获取字符的整数表示，
* `chr()`函数把编码转换为对应的字符：
* `str`

```
>>> ord('A')
65
>>> ord('中')
20013
>>> chr(66)
'B'
>>> chr(25991)
'文'

>>> '\u4e2d\u6587'
'中文'
>>> str('\u4e2d\u6587')
'中文'
```

由于Python的字符串类型是str，在内存中以Unicode表示，一个字符对应若干个字节。如果要在网络上传输，或者保存到磁盘上，就需要把str变为以字节为单位的bytes。

**Python对bytes类型的数据用带b前缀的单引号或双引号表示：**

```
x = b'ABC'
```

**要注意区分'ABC'和b'ABC'，前者是str，后者虽然内容显示得和前者一样，但bytes的每个字符都只占用一个字节。**

以Unicode表示的`str`通过`encode()`方法可以编码为指定的`bytes`，例如：

```
>>> 'ABC'.encode('ascii')
b'ABC'
>>> '中文'.encode('utf-8')
b'\xe4\xb8\xad\xe6\x96\x87'
>>> '中文'.encode('ascii')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
UnicodeEncodeError: 'ascii' codec can't encode characters in position 0-1: ordinal not in range(128)
```

纯英文的str可以用ASCII编码为bytes，内容是一样的，含有中文的str可以用UTF-8编码为bytes。含有中文的str无法用ASCII编码，因为中文编码的范围超过了ASCII编码的范围，Python会报错。

在`bytes`中，无法显示为ASCII字符的字节，用`\x##`显示。

反过来，如果我们从网络或磁盘上读取了字节流，那么读到的数据就是`bytes`。要把`bytes`变为`str`，就需要用`decode()`方法：

```
>>> b'ABC'.decode('ascii')
'ABC'
>>> b'\xe4\xb8\xad\xe6\x96\x87'.decode('utf-8')
'中文'
```

如果bytes中包含无法解码的字节，decode\(\)方法会报错：

```
>>> b'\xe4\xb8\xad\xff'.decode('utf-8')
Traceback (most recent call last):
  ...
UnicodeDecodeError: 'utf-8' codec can't decode byte 0xff in position 3: invalid start byte
```

如果bytes中只有一小部分无效的字节，可以传入errors='ignore'忽略错误的字节

```
>>> b'\xe4\xb8\xad\xff'.decode('utf-8', errors='ignore')
'中'
```

要计算str包含多少个字符，可以用**len\(\)**函数：

```
>>> len('ABC')
3
>>> len('中文')
2
```

en\(\)函数计算的是str的字符数，如果换成bytes，len\(\)函数就计算字节数：

```
>>> len(b'ABC')
3
>>> len(b'\xe4\xb8\xad\xe6\x96\x87')
6
>>> len('中文'.encode('utf-8'))
6
```

可见，1个中文字符经过UTF-8编码后通常会占用3个字节，而1个英文字符只占用1个字节

由于Python源代码也是一个文本文件，所以，当你的源代码中包含中文的时候，在保存源代码时，就需要务必指定保存为UTF-8编码。当Python解释器读取源代码时，为了让它按UTF-8编码读取，我们通常在文件开头写上这两行：

```
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
```

申明了UTF-8编码并不意味着你的.py文件就是UTF-8编码的，必须并且要确保文本编辑器正在使用UTF-8 without BOM编码：

# 格式化

| 占位符 | 替换内容 |
| :--- | :--- |
| %d | 整数 |
| %f | 浮点数 |
| %s | 字符串 |
| %x | 十六进制整数 |

```
>>> 'hello ,%s' % 'world'
'hello ,world'
>>> 'hi ,%s,you have $ %d 。' % ('zhang',100)
'hi ,zhang,you have $ 100 。'
```

```py
从上面的例子可以看出，  
%运算符就是用来格式化字符串的
在字符串内部，
%s表示用字符串替换，
%d表示用整数替换，有几个%?占位符，后面就跟几个变量或者值，顺序要对应好。
如果只有一个%?，括号可以省略。
```

其中，格式化整数和浮点数还可以指定是否补0和整数与小数的位数：

```
print('%2d-%02d' % (3,1))   3-01
print('%.2f' % 3.1415926) 3.14
```

如果不确定用什么，%s转成字符串不会出错，字符串里面的%是一个普通字符用%%转义

### format\(\)

另一种格式化字符串的方法是使用字符串的format\(\)方法，它会用传入的参数依次替换字符串内的占位符{0}、{1}……，不过这种方式写起来比%要麻烦得多：

```
>>> 'Hello, {0}, 成绩提升了 {1:.1f}%'.format('小明', 17.125)
'Hello, 小明, 成绩提升了 17.1%'
```

## 使用list和tuple

## list

1. Python内置的一种数据类型是列表：list。list是一种有序的集合，可以随时添加和删除其中的元素。

\`\`\` classmates = \['Michael', 'Bob', 'Tracy'\]\`\`\`

1. len\(\)函数获取list元素的个数

2. list元素相对于PHP中的数据，从0开始，取出最后一个classmate\[-1\],len\(classmates\) - 1

3. 从最后添加元素 \` classmate.append\('4'\)\`

4. 插入知道位置 \`classmate.insert\(1,'care'\)\`

5. 删除末尾的元素 pop\(\) \`classmate.pop\(\)\`，返回的是插入 弹出后的元素

6. 删除指定位置的元素 pop\(i\) \` classmate.pop\(1\)\`，返回的是弹出的元素

7. 替换：就是重新赋值 \` classmate\[1\] = 0\`

8. 元素里可以是字符串、整数、布尔值，也可以是另一个list（二维数组）、空元素的长度是0

## tuple

回忆一下list的赋值：classmate = \['care','zhang','wei','shuang'\]

现在tuple的赋值是：classmate = \('care','zhang','wei','shuang'\)

1. tuple与list相比的区别有：

   **  一旦定义不能更改，没有增删改，只能读classmate\[0\]，相对比较安全。**

2. tuple还要注意的是：

    **     当tuple元素里只有一个值，需要在值后面加一个逗号，否则默认当小括号进行计算得到的是对应的值而不是元素**

        **思考，为什么不直接定义t= \(1\),因为（）既可以表示tuple，又可以表示数学公式中的小括号这就产生了歧义**

```
>>> t = (1,)
>>> t
(1,)
```

        **当定义空的tuple**

```
>>> t = ()
>>> t
()
```





tuple元素不变具体指的是指向永远不变，比如tuple有个元素是list，list的内容可变。

\#\#\#\# 4-流程控制

1. 条件判断

\#\#\#\#\#\# if-else

\`\`\`

a = 3

if age &gt;= 18:

```
print\('adult'\)
```

else:

```
print\('kid'\)
```

\`\`\`

\#\#\#\#\#\# if-elif-else

\`\`\`

a = 3

if age &gt;= 18:

```
print\('adult'\)
```

elif age &gt;=6:

```
print\('teenager'\)
```

else:

```
print\('kid'\)
```

\`\`\`

\#\#\#\#\#\# if的缩写

只要x是非零数值、非空字符串、非空list等，就判断为True，否则为False。

\`\`\`

if x:

```
print\('True'\)
```

\`\`\`

\#\#\#\#\# inptu默认输入的是字符串

\`\`\`

&gt;&gt;&gt; age = input\(\)

20

&gt;&gt;&gt; if age &lt;18:

```
print\('未成年'\)
```

else:

```
print\('成年人'\)
```

Traceback \(most recent call last\):

File "&lt;pyshell\#39&gt;", line 1, in &lt;module&gt;

```
if age &lt;18:
```

TypeError: '&lt;' not supported between instances of 'str' and 'int'

\`\`\`

需要做一个操作：

ages = int\(age\)

如果输入的abc呢？需要用到错误和调试

\#\#\#\# 5-Python中的循环

循环有两种：for...in循环和while循环，只要条件满足，就不断循环，条件不满足时退出循环

1. for...in循环

\`\`\`

names = \['Michael', 'Bob', 'Tracy'\]

for name in names:

```
print\(name\)
```

\`\`\`

\`\`\`

sum = 0

for x in \[1, 2, 3, 4, 5, 6, 7, 8, 9, 10\]:

```
sum = sum + x
```

print\(sum\)

\`\`\`

求1到100之和，range\(101\)

1. while循环

\`\`\`

sum = 0

n = 99

while n &gt; 0:

```
sum = sum + n

n = n - 2
```

print\(sum\)

\`\`\`

1. break和continue  

break是退出循环

\`\`\`

&gt;&gt;&gt; n = 1

&gt;&gt;&gt; while n&lt;=100:

```
if n&gt; 10:

    break

print\(n\)

n = n+1

print\('END'\)
```

\`\`\`

continue的作用是提前结束本轮循环，并直接开始下一轮循环

\`\`\`

&gt;&gt;&gt; n = 0

&gt;&gt;&gt; while n&lt;10:

```
n = n +1

if n%2 == 0:

    continue

print\(n\)
```

1

3

5

7

9

&gt;&gt;&gt;

\`\`\`

\#\#\#\# 6-使用dict和set

\#\#\#\#\# 1. dict： \(类似json\)

Python内置了字典：dict的支持，dict全称dictionary，在其他语言中也称为map，使用键-值（key-value）存储，具有极快的查找速度。

产生原由：为了可以快速找出键值对，否则用两个list存储key和value，要找出key-value就得全部遍历很慢，通过key值准确快速定位出value的位置

特性：

1. key只能对应一个value

2. 重复赋值会被覆盖（\`&gt;&gt;&gt; d\['zhangsan'\] =20\`）

3. key不存在会报错，避免错误的两种办法

4. 删除key用pop\(key\)，对应value一起删除\` d.pop\('zhangsan'\)\`

5. dict内部存放的顺序和key放入的顺序是没有关系的

6. dictd的key必须是不可变对象

7. 通过key找value：key计算位置的算法称为哈希算法（Hash）。

1. 通过in判断key是否存在 \`'zhangsan' in d\` 返回布尔值

2. 通过get（）判断\`d. get\('zhangsan'\)\`不存在返回None（不显示），或者指定返回内容\`d. ger\('zhangsan',-1\)\`返回-1

\`\`\`

&gt;&gt;&gt; d = {'zhangsan':12,'li':15,'wangwu':18}

&gt;&gt;&gt; d\['zhangsan'\]

12

\`\`\`

\#\#\#\#\#\# dict和list的对比：

dict特点：  （空间换时间）

1. 查找和插入的速度极快，不会随着key的增加而变慢；

2. 需要占用大量的内存，内存浪费多。

list特点：

1. 查找和插入的时间随着元素的增加而增加；

2. 占用空间小，浪费内存很少。

\#\#\#\#\# 2-set

特点：存key不存value，key不能重复,重复的key会被过滤，通过add（key）添加，可以重复添加但是不会生效\`s.add\(1\)\` ，可以删除key，remove\(key\)，\`s.remove\(1\)\`

要创建一个set，需要提供一个list作为输入集合：

\`\`\`

&gt;&gt;&gt; s = set\(\[1,2,3\]\)

&gt;&gt;&gt; s

{1, 2, 3}

\`\`\`

set和dict的唯一区别仅在于没有存储对应的value，但是，set的原理和dict一样，所以，同样不可以放入可变对象，因为无法判断两个可变对象是否相等，也就无法保证set内部“不会有重复元素”。

\#\#\#\# 7-不可变变量

str是不变对象，list是可变对象

\`\`\`

&gt;&gt;&gt; a = \['c','b','a'\]

&gt;&gt;&gt; a.sort\(\)

&gt;&gt;&gt; a

\['a', 'b', 'c'\]

&gt;&gt;&gt; a = 'abc'

&gt;&gt;&gt; a.replace\('a','A'\)

'Abc'

&gt;&gt;&gt; a

'abc'

\`\`\`

分析：a是变量，'abc'是字符串的对象，replace\(\)作用在字符串的对象上，replace\(\)知识创建了一个新的字符串，并没有改变对象，对于不变对象来说，调用对象自身的任意方法，也不会改变该对象自身的内容。相反，这些方法会创建新的对象并返回，这样，就保证了不可变对象本身永远是不可变的。

