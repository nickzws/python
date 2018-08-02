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

   ```
    **思考，为什么不直接定义t= \\(1\\),因为（）既可以表示tuple，又可以表示数学公式中的小括号这就产生了歧义**
   ```

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

**可变的”tuple**

```
>>> t = ('a', 'b', ['A', 'B'])
>>> t[2][0] = 'X'
>>> t[2][1] = 'Y'
>>> t
('a', 'b', ['X', 'Y'])
```

**原因：中间是list，tuple元素不变具体指的是指向永远不变，比如tuple有个元素是list，list的内容可变。**

## 条件判断

## if

```
age = 20
if age >= 18:
    print('your age is', age)
    print('adult')
```

## if-else {#test}

```
age = 3
if age >= 18:
    print('your age is', age)
    print('adult')
else:
    print('your age is', age)
    print('teenager')
```

## if-elif-else \(可以多个elif\)

```
age = 3
if age >= 18:
    print('adult')
elif age >= 6:
    print('teenager')
else:
    print('kid')
```

## if的缩写

**只要x是非零数值、非空字符串、非空list等，就判断为True，否则为False。**

```
if x:
   print('True')
```

## inptu默认输入的是字符串

```
age = 3
if age >= 18:
    print('your age is', age)
    print('adult')
else:
    print('your age is', age)
    print('teenager')
Traceback (most recent call last):
File "<pyshell#39>", line 1, in <module>
if age &lt;18:
TypeError: '<' not supported between instances of 'str' and 'int'
```

需要做一个操作：

ages = int\(age\)

如果输入的abc呢？需要用到错误和调试

# 5-Python中的循环

**循环有两种：for...in循环和while循环，只要条件满足，就不断循环，条件不满足时退出循环**

## for...in循环

**ython的循环有两种，**

**一种是for...in循环，依次把list或tuple中的每个元素迭代出来，看例子：**

```
names = ['Michael', 'Bob', 'Tracy']
for name in names:
    print(name)
```

```
sum = 0
for x in [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]:
    sum = sum + x
print(sum)
```

**第二种循环是while循环，只要条件满足，就不断循环，条件不满足时退出循环。比如我们要计算100以内所有奇数之和，可以用while循环实现：**

**while**

```
sum = 0
n = 99
while n > 0:
    sum = sum + n
    n = n - 2
print(sum)
```

**breake     **break是提前结束循环。

**continue  **continue语句会直接继续下一轮循环

```
n = 0
while n < 10:
    n = n + 1
    if n % 2 == 0: # 如果n是偶数，执行continue语句
        continue # continue语句会直接继续下一轮循环，后续的print()语句不会执行
    print(n)
```

# 6-使用dict和set

## 1. dict： \(类似json\)

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

8. 通过in判断key是否存在 \`'zhangsan' in d\` 返回布尔值

9. 通过get（）判断\`d. get\('zhangsan'\)\`不存在返回None（不显示），或者指定返回内容\`d. ger\('zhangsan',-1\)\`返回-1

\`\`\`

&gt;&gt;&gt; d = {'zhangsan':12,'li':15,'wangwu':18}

&gt;&gt;&gt; d\['zhangsan'\]

12

\`\`\`

## dict和list的对比：

dict特点：  （空间换时间）

1. 查找和插入的速度极快，不会随着key的增加而变慢；

2. 需要占用大量的内存，内存浪费多。

list特点：

1. 查找和插入的时间随着元素的增加而增加；

2. 占用空间小，浪费内存很少。

## 2-set

特点：存key不存value，key不能重复,重复的key会被过滤，通过add（key）添加，可以重复添加但是不会生效\`s.add\(1\)\` ，可以删除key，remove\(key\)，\`s.remove\(1\)\`

要创建一个set，需要提供一个list作为输入集合：

\`\`\`

&gt;&gt;&gt; s = set\(\[1,2,3\]\)

&gt;&gt;&gt; s

{1, 2, 3}

\`\`\`

set和dict的唯一区别仅在于没有存储对应的value，但是，set的原理和dict一样，所以，同样不可以放入可变对象，因为无法判断两个可变对象是否相等，也就无法保证set内部“不会有重复元素”。

# 7-不可变变量

str是不变对象，list是可变对象

```
>>> a = ['c','b','a']
>>> a.sort()
>>> a
['a', 'b', 'c']
>>> a = 'abc'
>>> a.replace('a','A')
'Abc'
>>> a
'abc'
```

分析：a是变量，'abc'是字符串的对象，replace\(\)作用在字符串的对象上，replace\(\)知识创建了一个新的字符串，并没有改变对象，对于不变对象来说，调用对象自身的任意方法，也不会改变该对象自身的内容。相反，这些方法会创建新的对象并返回，这样，就保证了不可变对象本身永远是不可变的。

