# 在Windows上安装Python

## 1.1下载安装pyhton

根据你的Windows版本（64位还是32位）从Python的官方网站下载Python 3.7对应的64位安装程序或32位安装程序

1. 选择install Now

2. 特别要注意勾上Add Python 3.7 to PATH，然后点“Install Now”即可完成安装。

## 1.2 运行python

```py
C:\Users\care>python
Python 3.7.0 (v3.7.0:1bf9cc5093, Jun 27 2018, 04:59:51) [MSC v.1914 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information
```

## 1.3 相关操作

1. 退出命令行

```
>>>exit()
```

  2. 计算

```
>>> 100+200
300
```

3. 打印指定文字 \`print\(\)\`函数

```
>>> print('hello, world')
hello, world
```

1. 可以直接运行文件

```
C:\work>python calc.py
```

1. 命令行是输入一行执行一行，直接运行.py代码是执行该文件的所有代码

```
C:\Users\care\Desktop\python>python hello.py
hello world
```

1. 只能以\`.py\`结尾

2. 文件名只能是英文字母、数字和下划线的组合

3. mac或者linux直接运行.py

直接运行py文件

有同学问，能不能像.exe文件那样直接运行.py文件呢？在Windows上是不行的，但是，在Mac和Linux上是可以的，方法是在.py文件的第一行加上一个特殊的注释：

```py
#!/usr/bin/env python3
print('hello, world')
然后，通过命令给hello.py以执行权限：
$ chmod a+x hello.py
```

## 1.4 执行环境代码

```py
C:\Users\care\Desktop\python> python learning.py
```

## 1.5 输出

1. print\(\)函数也可以接受多个字符串，用逗号“,”隔开，就可以连成一串输出、输出整数、计算结果

```py
>>> print('hello world')
hello world
>>> print('i','love','python3.0')
i love python3.0
>>> print(300)
300
>>> print(100+200)
300
>>> print('100+200=',100+200)
100+200= 300
>>>
```

## 1.6 输出input（）

input\(\)，可以让用户输入字符串，并存放到一个变量里

```py
>>> name=input()
zhangsan
>>> name
'zhangsan'
>>> print(name)
zhangsan
```

TIPS:

```py
name=input('please enter your name')
print('hello',name)
C:\Users\care\Desktop\python>python hello.py
please enter your namezhangsan
hello zhangsan
print("1024*768=",1024*768)//注意必须是双引号
```

---

1. pycharm破解地址：

[http://idea.liyang.io/](http://idea.liyang.io/)

1. 进入桌面文件dir \`C:\Users\care\Desktop\python&gt;\`

2. 


