# Python
## 注释
```python
'''
这里是多行注释
'''

#这里是单行注释
```

## 各种小函数
### 控制台输出 print
前面是各种函数和字符串   
后面end=""是替换
```python
print("" , end = "")
```
### 数据类型 type
```python
print(type(100))
print(type(3.14))
print(type(True))
print(type('hello python'))
```
### 获得输入 input
等待输入
```python
a = input("wait for input")
```
### 随机数
需要导入一个随机数模块
```python
for i in range(6):
    t = rd.randint(0 , 10)
    print(t , end= "\t")
```

## 类型转换
### 任意类型转int
```python
a = int("1")
```
### 任意类型转float
```python
a = float ("2.123")
```
### 任意类型转str
```python
a = str(123)
```

## 循环
### while循环
```python
i = 0
while i < 5:
    print(i)
    i += 1
```
### for循环
```python
for i in range(1, 9):
    print(i, end="\t")
```

## 字符处理
### 字符串批量替换 format
从零开始计数  
按照编号替换  
```python
print("test1{1}test2{0}test3{2}").format(a,b,c)
```
### 字符串截取
```python
str = "abcdef"
print(str[0])
print(str[0:6])
print(str[0:-1])
```
### 搜索指定字符串
如果搜索不到指定的字符串就返回-1
```python
str = ("thinking In java")
print(str.find('java',0,8)) 
```
### 查找指定字符串在目标字符串中个数
```python
str = ("thinking In java")
print(str.count("ink")) 
print(str.count("in")) 
```
### 替换字符
```python
str = ("thinking In java")
print(str.replace('java','python')) 
```
### 切割字符
会返回一个分割成没有指定字符串的list
```python
str = ("thinking In java")
print(str.split("i"))
```
### 首字母大写
```python
str = ("thinking In java")
print(str.capitalize())
```
### 单词首字母大写
```python
str = ("thinking In java")
print(str.title())
```
### 判断是否以指定字符串开头
```python
str = ("thinking In java")
print(str.startswith("think"))
```
### 判断是否以指定字符串结尾
```python
str = ("thinking In java")
print(str.endswith("java"))
```
### 全转小写
```python
str = ("thinking In java")
print(str.lower())
```
### 全转大写
```python
str = ("thinking In java")
print(str.upper()) 
```
### 去除字符串前后空格
中间的没法去除
```python
s2= "   as  dw   "
print(s2)
print(s2.strip())
```
### 判断字符串里所有字符是否全部是字母
```python
str = ("thinking In java")
s3 = "qwer"
print(str.isalpha())
print(s3.isalpha())
```
### 判断字符串里是否全是数字
```python
s3 = "qwer"
s4 = "1234"
print(s3.isdigit())
print(s4.isdigit())
```
### 判断是否只有数字和英文字母
```python
s5 = "hello123"
s6 = "hello 123"
print(s5.isalnum())
print(s6.isalnum())
```
### 判断字符串里是否全是空格
```python
str = ("thinking In java")
```
### 判断字符串里是否全是空格
```python
s7 = "      "
print(s7.isspace())
print(s6.isspace()) 
```

## 列表/元组/字典
### 区别
元组与列表的区别是元组使用小括号
列表使用方括号
元组使用小括号
列表使用方括号
元组不可修改
列表可修改
### 列表
```python
list = [[11, 22], [33, 44, 55], [66, 77, 88]]
print(list[0][0])
```
### 元组
```python
yz = ("曹操","刘备","孙权")
print(yz[1])
```
### 字典
```python
info = {'name': "吕蒙",
        'id': 36,
        'sex': '男',
        'address': '吴'}            #字典,类型为dist
print( info['name'])
print( info['id'])
print(type(info))                   #字典类型为dist
print(info.get('age'))
print(info.get('name'))             #get会返回一个'None'而不是直接报错
age = info.get("age",18)            #get如果为空会返回定义好的值
print(age)
info ["id"]=110                     #修改元素
info["age"]=30                      #添加元素
print(info)                         #输出info里的内容
del info["age"]                     #删除元素'age'
print(info)

info.clear()                        #删除info里的内容
print(info)

del info                            #删除变量info
print(info)

info = {'name': "吕蒙",
        'id': 36,
        'sex': '男',
        'address': '吴'}

for key in info.keys():             #通过for函数遍历key值
    print(key)
for value in info.values():         #通过for函数遍历value值
    print(value)
for items in info.items():            #遍历所有键值对
    print(items[1] , items [0])
```

## 函数
### def
```python
#无参数,无返回值类型
def show1():
    print("here is a text")

#有参数,无返回值类型
def show2(a,b):
    if a > b :
        a , b = b , a
    print("a = {} , b = {}".format(a,b))

#无参数,有返回值
def show3():
    a = b = c = 3
    d = a*b*c
    return d

#有参数,有返回值
import random as rd
def show4(l,a,b):
    list = []
    for i in range(l):
        list.append(rd.randint(a,b))
    return list
```
### 调用
```python
#函数互相调用
def aoo():
    print("------aoo开始------")
    print("------aoo结束------")

def boo():
    print("------boo开始------")
    aoo()
    print("------boo结束------")
```
### 私有化
#### 私有化函数
```python
if __name__ == '__main__':
    boo()
    show1()
    for i in range(1, 10):
        a, b = rd.randint(0, 100), rd.randint(0, 100)
        show2(a, b)
```
#### 私有化变量
如果局部函数变量和全局函数变量相同的话
优先使用局部变量
除非特殊声明了是全局变量
```python
a1 = 200
a2 = 99
def show1():
    a = 100
    print("a1 = {} , a2 = {}".format(a1, a2))


def show2():
    a = 200
    print("a1 = {} , a2 = {}".format(a1, a2))


def show3():
    global a2       #声明是全局变量
    a2 += 1
    print(a2)

def show4():
    a2 = 999
    a2 += 1
    print(a2)

def show5():
    a2 = 1
    a2 += 1
    print(a2)

show1()
show2()
show3()
show4()
show5()
```
### 导入
导入可以重命名包名
```python
import nullkun02 as d1
d1.show1()
import random as rd
for i in range (1,10):
    a , b = rd.randint(0, 100), rd.randint(0, 100)
    d1.show2(a , b)
print(d1.show3())
print(d1.show4(10,50,100))
d1.boo()
d1.show1()
```

## 文件读写
### 基础文件新建/打开/关闭
```python
file = open('a1.txt','w')
print(file.name)        #文件名字
print(file.mode)        #打开方式
print(file.closed)      #确认是否关闭
print(file.close())     #关闭文件,不需要用print
print(file.closed)      #确认是否关闭
```
### 文件写入
#### 覆盖式打开
```python
file = open('a1.txt','w',encoding="UTF-8")
# 设置为utf-8
file.write('hello python')
file.write("是时候展示真正的技术了")
file.close()
```
#### 追加式打开
```python
file = open('a1.txt','a',encoding="UTF-8")
file.write("\n天地有正气,杂然赋流形")
file.close()
file = open('a1.txt','a',encoding="UTF-8")
file.write("\n水舞龙吟")
file.close()
file = open('a1.txt','a',encoding="UTF-8")
file.write('问心阁')
file.close()
```
### 文件读取
```python
f = open("a1.txt","r",encoding='utf-8')
str = f.read()
f.close()
print(str)
```
### os模块
```python
import  os                          #导入os包
os.rename('a1.txt' , 'b1.txt')      #重命名文件夹
os.remove('b1.txt')                 #删除文件
os.mkdir('aaa')                     #新建文件夹
print(os.getcwd())                  #获取当前路径名称
os.rmdir('aaa')                     #删除文件夹
```

## 时间
### 前置
```py
import time
```
### 获取当前系统时间戳
```py
print(time.time())
```
