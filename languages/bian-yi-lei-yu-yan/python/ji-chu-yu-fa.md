# 基础语法

## 编码
默认情况下`python3`源码文件以`utf-8`编码    
所有字符都是`unicode`字符串
可以通过首行指定不同编码

```python
# -*- coding: cp-1252 -*-
```

## 标识符
* 第一个字符必须是字母表中字符或下划线`_`
* 标识符的其他部分由字母、数字和下划线组成
* 标识符对$$\color{red}{大小写敏感}$$
* python3允许中文作变量名，**非ASCII标识符**也是允许的。

#### 一些不在语言内的通用规定
* 大驼峰
* 小驼峰
* 下划线

## 保留字
保留字即关键字
```py
>>> import keyword
>>> keyword.kwlist
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

## 注释
单行注释使用`#`
多行注释使用`''''''`或者`""""""`

```python
'''
print("testz")
'''

#这里是单行注释
#组合起来就是开关注释

'''''''
print("testa")
'''
print("testb")
#'''

'''
print("testac")
'''
print("testd")
#'''


'''''''
print("teste")
#'''

'''
print("testf")
#'''
```

## 行与缩进
python的代码块不再使用`{}`表示代码块    
取而代之的是缩进    
缩进的空格数是可变的    
但是同一个代码块的语句必须包含相同的缩进空格数。    
* tab和四个空格看起来相同，但是不是相同的缩进。
```py
if True:
    print ("True")
else:
    print ("False")


if True:
    print ("Answer")
    print ("True")
else:
    print ("Answer")
  print ("False")    # 缩进不一致，会导致运行错误

```

## 多行语句
Python 通常是一行写完一条语句     
但是如果语句很长的话    
可以使用反斜杠`\`来实现多行语句     
括号内的不需要使用`\`       

```py
total = item_one + \
        item_two + \
        item_three

total = ['item_one', 'item_two', 'item_three',
        'item_four', 'item_five']
```

## 变量类型

### 数字类型
python中数字有四种类型：整数、布尔型、浮点数和复数

| 类型 | 释义 |
| - | - |
| int | 1<br> 只有一种整数类型`int`<br>表示为长整型<br>没有Long这种说法|
| bool (布尔) | True<br>False |
| float (浮点数) | 1.23 <br> 3E-2 |
| complex (复数) | 1 + 2j <br> 1.1 + 2.2j|

### 字符串
* Python 中单引号 ' 和双引号 " 使用完全相同。
* 使用三引号(`'''` 或 `"""`)可以指定一个多行字符串。
* 转义符 `\`。
* 反斜杠可以用来转义，使用 r 可以让反斜杠不发生转义。       
  *  如 `r"this is a line with \n"` 则 `\n` 会显示，    
  并不是换行。
* 字符串可以用 + 运算符连接在一起
  * 用 * 运算符重复。
* Python 中的字符串有两种索引方式，
  * 从左往右以 0 开始，从右往左以 -1 开始。
* Python 中的字符串不能改变。
* Python 没有单独的字符类型
  * 一个字符就是长度为 1 的字符串。
* 字符串的截取的语法格式如下：变量[头下标:尾下标:步长]

```
str='123456789'
 
print(str)                 # 输出字符串
print(str[0:-1])           # 输出第一个到倒数第二个的所有字符
print(str[0])              # 输出字符串第一个字符
print(str[2:5])            # 输出从第三个开始到第五个的字符
print(str[2:])             # 输出从第三个开始后的所有字符
print(str[1:5:2])          # 输出从第二个开始到第五个且每隔一个的字符（步长为2）
print(str * 2)             # 输出字符串两次
print(str + '你好')         # 连接字符串
 
print('------------------------------')
 
print('hello\nrunoob')      # 使用反斜杠(\)+n转义特殊字符
print(r'hello\nrunoob')     # 在字符串前面添加一个 r，表示原始字符串，不会发生转义
```
