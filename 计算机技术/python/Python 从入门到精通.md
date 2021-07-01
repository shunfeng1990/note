# Python 从入门到精通

## 基础知识：

输出语句print

```python
print('hello world')
```

输出多行字符串

```python
print("""这是第一行
这是第二行
这是第三行
可以输出多行""")
```



文件编码声明注释：(不声明的话在python2x中执行中文会乱码)

```pyth
#coding=utf8
```



如何查看python中的保留字

```python
import keyword
keyword.kwlist
```



> python 中定义变量是区分大小写的

如何定义变量

```python
user = 'andy'
age = 20
```

查看变量类型

```python
print(type(user))
print(type(age))
```

> 内置函数id可以返回变量所指的内存地址

```python
id(user)
id(age)
```



常用的数据类型转换函数

```python
int(x)  # 转换成整数
str(x)  # 转换成字符串
float(x)  # 转换成浮点数
eval(str)  # 计算在字符串中的有效的python表达式，并返回有个对象
chr(x)  # 将整数转换为一个对应的字符串
ord(x)  # 将一个字符转换为对应的整数
hex(x)  # 将一个整数转换为十六进制的字符串
oct(x)  # 将一个整数转换为八进制的字符串
bin(x)  # 将一个整数转为二进制的字符串
```



> 内置函数 input() 接收用户键盘的输入内容

```python
content = input('请输入内容:')
```



算数运算符（有括号先算括号内部）

```python
+ - * /
9 % 2  # % 取余数 1
9 // 2  # 取整除，返回整数 4
10**3  # 幂运算 10的3次幂 10*10*10
```



赋值运算符

```python
a = 100  # 最简单的赋值
a += 5  # a+5 结果赋值给a 105 其他的减 乘 除 一个样

b = 100
b %= 30  # 取余数的结果赋值给b 等于10 **= 和 //= 一个样

```



比较运算符

```python
> < == != >= <=
```



逻辑运算符

```python
and  # 逻辑与 两个表达式都为True 才为True
or  # 逻辑或 两个表达式有一个为True 就为True
not  # 逻辑非 取反 not False 返回True
```



位运算符

```python
&  # 按位与运算符：参与运算的两个值,如果两个相应位都为1,则该位的结果为1,否则为0
|  # 按位或运算符：只要对应的二个二进位有一个为1时，结果位就为1。
^  # 按位异或运算符：当两对应的二进位相异时，结果为1
~  # 按位取反运算符：对数据的每个二进制位取反,即把1变为0,把0变为1 。~x 类似于 -x-1
<<  # 左移动运算符：运算数的各二进位全部左移若干位，由 << 右边的数字指定了移动的位数，高位丢弃，低位补0。
>>  # 右移动运算符：把">>"左边的运算数的各二进位全部右移若干位，>> 右边的数字指定了移动的位数
```

```python
a = 60            # 60 = 0011 1100 
b = 13            # 13 = 0000 1101 
c = 0
 
c = a & b;        # 12 = 0000 1100
print "1 - c 的值为：", c
 
c = a | b;        # 61 = 0011 1101 
print "2 - c 的值为：", c
 
c = a ^ b;        # 49 = 0011 0001
print "3 - c 的值为：", c
 
c = ~a;           # -61 = 1100 0011
print "4 - c 的值为：", c
 
c = a << 2;       # 240 = 1111 0000
print "5 - c 的值为：", c
 
c = a >> 2;       # 15 = 0000 1111
```

位运算判断奇数和偶数（奇数二进制末尾肯定是1 偶数二进制末尾肯定是0）

```python
sum = 101
if sum & 1:
    print('奇数')
else:
    print('偶数')
```



### 流程控制

```python
if 10 > 5:
    print('yes')
```

```python
if 10 > 5:
    print('yes')
else:
    print('no')
```

```python
a = 10
if a > 100:
    print('a>100')
elif a > 50:
    print('a>50')
elif a < 100:
    print('a<100')
else:
    print('都不对')
```



```python
# 死循环
while True:
    print('为真一直循环输出')
```

```python
# 循环输出1 ~ 9
sum = 1
while sum < 10:
    print(sum)
    sum += 1
```

```python
# continue 和 break 用法

i = 1
while i < 10:
    i += 1
    if i%2 > 0:  # 不是偶数就跳过当前循环 继续从头循环
        continue
    print(i)  

i = 1
while 1:
    print(i)
    i += 1
    if i > 10:  # 当i大于10的时候跳出整个循环
        break
```

> python 3.x 中，使用print() 函数时，如果想要实现输出的内容在一行上显示，就需要加上 ,end = ' '

```python
for i in range(1,10,2):
    print(i,end = ' ')  # 输出1 3 5 7 9
```

> range() 内置函数是生成一个连续的整数，有两个参数表示开始和结束，第三个参数表示步长

```python
range(5)  # 得到 0 1 2 3 4
range(1,7)  # 得到1 2 3 4 5 6
range(1,10,2)  # 得到1 3 5 7 9
```

用for循环遍历字符串

```python
str = '我是中国人'
for ch in str:
    print(ch)
```

用for循环计算1+2+3..+100总和

```python
result = 0
for i in range(101):
    result += i
print(result)    
```

用for循环输出九九乘法表

```python
for i in range(1,10): 
    for j in range(1,i+1): 
        print('%d*%d=%2d\t' % (j,i,i*j), end='')
    print()  # 换行
```

用while循环输出九九乘法表

```python
i = 1
while i <= 9:
    j = 1
    while j <= i:
        print('%d*%d=%2d\t' % (j,i,j*i), end='')
        j += 1
    print()
    i += 1
```

> pass 语句用于先占位，来保证代码块的完整性

```python
if 10 > 9:
    pass
```



### 列表和元组

创建一个列表（索引从0开始）

```python
num = []  # 创建空列表
num = [1,2,3,4,5]
tile = ['python','php','c','java']
```

获取列表中的某个元素

```python
tile[1]  # 得到php
```

查看一个值是否包含在列表内

```python
print('php' in tile)  # 返回True 说明包含
```

查看列表的长度

```python
print(len(tile))  # 打印4
```

查看列表中最大的值

```python
print(max(num))  # 打印5
```

查看列表中最小的值

```python
print(min(num))  # 打印1
```

> list() 方法用于将元组转换为列表。

```python
new_list = list(range(10,20,2))
print(new_list)  # 打印 [10, 12, 14, 16, 18]
```

列表排序（升序）

```python
num = [9,5,2,1,8,7]
num.sort()
print(num)
```

列表排序（降序）

```python
num = [9,5,2,1,8,7]
num.sort(reverse=True)
print(num)
```

遍历列表

```python
num = [9,5,2,1,8,7]
for i in num:
    print(i)
    
# 使用 enumerate 函数，遍历索引和值
for index,i in enumerate(num):
    print(index,i)
```

列表中添加一个元素

```python
num = [1,2,3]
num.append(4)
print(num)
```

两个列表合并

```python
num = [1,2,3]
num2 = [4,5,6]
num.extend(num2)
print(num)

# 或者直接 num + num2 也可以
```

列表修改元素

```python
num[2] = 10
```

列表删除元素

```python
# 根据索引删除
del num[2]  # -1 是删除最后一个

# 根据值删除
num.remove(2)

# 如果要删除的值不存在，则报错 最好做一个判断
list_a = ['python','php','java']
val = 'php'  # 要删除的元素
if list_a.count(val) > 0:
    list_a.remove(val)
print(list_a)
```

> count() 方法用于判断指定元素出现的次数，返回结果为0，说明该元素不存在。



获取指定元素首次出现的下标

```python
listname.index(obj)
```

统计数值列表元素的总和

```python
result = [10,20,30]
total = sum(result)
print('总和是：%d' % total)
```



列表推导式

> 使用列表推导式可以快速生成一个列表，或者根据某个条件生成指定的列表

```python
# 生成指定范围的数值列表
# 生成3个随机数，要求数的范围是0~9
import random
number = [random.randint(0,9) for i in range(3)]
print(number)
```

```python
根据列表生成指定需求的列表
# 语法 newlist = [Expression for var in list]
# 生成一个商品列表打5折的新列表
price = [1200,5000,2000,1000]
sale = [int(x*0.5) for x in price]
print('打5折后的价格:',sale)
```

```python
# 从列表选择符合条件的元素，组成新的列表
# 语法 newlist = [Expression for var in list if condition]
# 生成一个价格高于1000的列表
price = [1200,5000,2000,1000]
sale = [x for x in price if x > 1000]
print(sale)
```

二维列表（列表中的列表）

```python
arr = [[1,2,3],[4,5,6]]
# 二维列表访问元素
arr[1][0]  # 访问结果是4
```

```python
# 列表推导式创建(4组 每组5个值) 4行5列
arr = [[j for j in range(5)] for i in range(4)]
print(arr)
```

------

> 元组和列表类似，只是元组的类型可以不同，序列不可变，元素不可以单独修改

创建元组

```python
num = (1,2,3,4)
python = ('爬虫',)  # 如果只有一个值，要加一个逗号, 不加的话就是字符串类型了
emptytuple = ()  # 空元组

# 创建数值元组可以直接使用 tuple函数
tuple(range(10,20,2))  # 创建10到20 步长为2的一些数值
```

查看元组中的某个值

```python
num = (1,2,3,4)
num[1]  # 根列表一个样
```

```python
# 切片方式查看前3个
num[:3]
```

遍历元组

```python
python = ('简单','好学','强大')
for index,item in enumerate(python):
    print(index,item)
```

修改元组

```python
python = ('简单','好学','强大')
python[1] = '难学'  # 这样是错误的，因为元组是不可变序列的 所以不能单独修改某个元素
python = ('简单','难学','强大')  # 只能通过重新赋值修改
# 两个元组组合成一个新的元组使用 + 号
```

> 元组推导式和列表推导式类似，只是把列表的[]换成()

###### 元组和列表的区别

简单理解：列表好比用铅笔写字，写错了可以改；元组好比用钢笔写字，写错了只能换张纸再写。

###### 官方区别

1. 列表可变序列，元组不可变
2. 列表可以使用append() extend() insert() remove() pop() 等方法，元组不可以
3. 列表和元组都支持使用切片查看，但是列表可以修改，元组只能查看
4. 元组的访问速度比列表要快，如果不修改的值 建议使用元组
5. 列表不能作为字典的建，而元组可以



### 字典和集合

> 字典类似其他语言的对象，键值对的方式呈现，是无序的。

创建字典

```python
test = {}  # 空字典
test = {'name':'张三','age':22}
```

```python
# 两个列表合并成一个字典（列表1是键 列表2是值）
list_a = ['name','age']
list_b = ['张三',22]
test = dict(zip(list_a, list_b))
```

删除或清除字典

```python
del test  # 删除字典test
test.clear()  # 清除字典里的全部内容
```

访问查看字典

```python
# 通过字典的键来查看对应的内容
test = {'name1':'张三','name2':'李四','name3':'王五'}
test['name1']  # 查看张三

# 以上访问如果字典内不存在该键 将会报错，解决这个问题如下方式
print(test['name4'] if 'name4' in test else '字典内不存在')  # 使用判断方式
print(test.get('name4','字典内不存在'))  # 使用get()方法 推荐使用
```

遍历字典

```python
test = {'name1':'张三','name2':'李四','name3':'王五'}
for item in test.item():
    print(item)
    
for key, val in test.items():
    print(key,val)
```

字典的增删改

```python
test = {'name1':'张三','name2':'李四','name3':'王五'}
test['name4'] = '马六'  # 增加 当该键存在则修改
del test['name2']  # 删除

# 删除一个不存在的键，避免报错如下操作
if 'name2' in test:
    del test['name2']
else:
    print('要删除的不存在')
```

> 集合最大的用处就是去重复，集合是无序，不可重复的一组数据，如果重复只保留一个

创建集合

```python
set1 = {1,2,2,3}  # 逗号分隔 方式一
set2 = set(1,2,2,3)  # 这是错误的，set() 只能接收一个参数
set2 = set([1,2,3])  # set()函数创建 方式二 推荐
```

把元组和列表转换成集合

```python
tuple_a = (1,2,3,4,4)  # 元组
list_a = [5,6,7,8,8]  # 列表
set(tuple_a)  # 把元组转换成集合 去重复
set(list_a)  # 把列表转换成集合 去重复
```

集合的添加和删除

```python
set1 = {1,2,2,3}
set1.add(4)  # 添加
set1.remove(1)  # 删除一个元素
set1.pop(3)  # 删除一个元素
del set1  # 删除整个集合
set1.clear()  # 清空
```

```python
# 同样的删除一个不存在的元素时，防止报错 做个判断
if 4 in set1: set1.pop(4)
```

集合的交集、并集和差集运算

```python
# 交集运算：&
# 并集运算：|
# 差集运算：-
set1 = set(['a','b','c','d'])
set2 = set(['e','f','g','h','b','c'])
print(set1 & set2)  # 两组哪些内容有交集
print(set1 | set2)  # 两组一共有哪些内容 去重
print(set2 - set1)  # 从set2去掉和set1重复的
print(set1 - set2)  # 从set1去掉和set2重复的
```

------

### 字符串

字符串编码转换

```python
str1 = '中国人'
str1.encode()  # 编码 默认utf-8
str1.decode()  # 解码
```

字符串的拼接

```python
# 拼接使用 + 
# 但是不允许拼接其他类型，除非使用str() 函数进行转换成字符串在拼接
str1 = 'abc'
str2 = 100
str3 = str1 + str2  # 错误的
str3 = str1 + str(str2)  # 正确的
```

计算字符串的长度

```python
str1 = 'python'
len(str1)  # 使用len
```

截取字符串

```python
# 字符串的索引是从0开始，每个字符占一个位置，可以使用切片方式截取
str1 = '人生苦短,我用python'
str1[1]  # 截取的第2个
str1[5:]  # 从第6个字符开始截取
str1[:5]  # 从所边开始截取5个
str1[2:5]  # 截取3到第5个字符
```

分割合并字符串

```python
str1 = 'abc 22  33'
str1.split()  # 分割字符串 返回一个列表
```

```python
list_a = ['张三','李四','王五']
' @'.join(list_a)  # 使用join 合并 @拼接
```

检索字符串

```python
str_a = 'abcdd'
str_a.count('a')  # count() 检索指定字符串出现的次数，不存在返回0
```

```python
str_a = 'abcdd'
str_a.find('b')  # find() 检索是否包含指定的子字符串 不存在则返回-1，存在返回首次出现的位置
str_a.index('b')  # 与上面类似 只是如果不存在会抛出异常
```

```python
# 如果只想判断指定字符串是否存在 可以直接使用 in
'a' in str_a  # 包含a 则返回True
```

```python
# startswith() 检索字符串是否以 指定的子字符串开头 是 返回True 不是 返回Falsh
# endswith() 检索字符串是否以 指定的子字符串结尾 是 返回True 不是 返回Falsh
str1 = 'www.baidu.com'
str1.startswith('www')
str1.endswith('com')
```

字母的大小写转换

```python
str1 = 'WWW.baidu.Com'
str1.lower()  # 大写转小写
str1.upper()  # 小写转大写
```

去除字符串中的空格和特殊字符

```python
# strip() 去除左右两测的空格和特殊字符
# lstrip() 只去除左侧
# rstrip() 只去除右侧
str1 = ' www.baidu.com  \t\n\r'
str1.strip()
```

格式化字符串

```python
# %s 字符串占位 %d 整数数值占位 %f 浮点数占位（保留2位要加 .2）
str1 = '我叫%s,今年%d岁,体重%.2f斤' % ('张三',23,120.053)
print(str1)
```

```python
# format() 方法格式化字符串 推荐使用
s = "{} is a {}".format('Tom', 'Boy')  # {} 占位
print(s) # Tom is a Boy
```

```python
# 通过索引来指定内容 索引0开始
s1 = "{1} is a {2}".format('Tom', 'Lily', 'Girl')
print(s1) # Lily is a Girl
```

```python
# 通过参数名来匹配
s = "{name} is a {sex}".format(name='Tom', sex='Boy')
print(s) # Tom is a Boy
```

```python
如果参数已经确定，可以直接利用{}进行格式化引用
name = 'Tom'
sex = 'Girl'
# 以f开头表示在字符串中支持大括号内的python表达式
s = f"{name} is a {sex}"
print(s) # Tom is a Girl
```

```python
# 对参数的部分进行引用
s = "我是{s},我来自{s[0]}国".format(s='中国人')
print(s)  # 我是中国人，我来自中国
```

```python
# 保留小数2位数
s = 'π is {:.2f}'.format(3.1415926)
print(s) # π is 3.14
```

```python
# 还可以用于字符串截取
s = "{:.1}".format('Hello')
print(s) # H
```

```python
# 给数字加千位
s = "{:,}".format(1000000)
print(s) # 1,000,000
```

```python
# 数字转换成二进制
s = "{:b}".format(8)
print(s) # 1000

# b: 输出整数的二进制方式；
# c: 输出整数对应的 Unicode 字符；
# d: 输出整数的十进制方式；
# o: 输出整数的八进制方式；
# x: 输出整数的小写十六进制方式；
# X: 输出整数的大写十六进制方式；
```

```python
# 字符串中数字左边补0, 0>5表示数据总显示宽度为5，以０补齐
print('{:0>5d}'.format(3))
# 00003

# 可以补齐其它数字，例如８，输出总宽度为５
print('{:8>5d}'.format(3))
# 88883
```

```python
# list、tuple的拆分
# 在format格式化时，可使用* 或者 ** 进行对list、tuple拆分
foods = ['fish', 'beef', 'fruit']
s = 'i like eat {} and {} and {}'.format(*foods)
print(s)  # i like eat fish and beef and fruit

foods = ['fish', 'beef', 'fruit']
s = 'i like eat {2} and {0} and {1}'.format(*foods)
print(s)  # i like eat fruit and fish and beef

dict_temp = {'name': 'Lily', 'age': 18} 
# 字典需要用 ** 进行拆分
s = 'My name is {name}, i am {age} years old'.format(**dict_temp)
print(s) # My name is Lily, i am 18 years old
```

------

## 进阶提高：

### python使用正则

[正则表达式教程](https://www.runoob.com/regexp/regexp-metachar.html)

匹配字符串

```python
# 使用match() 是从开始位置进行匹配

import re  # 引入re模块
pattern = r'my'
string = 'My is Chinese'
match = re.match(pattern, string, re.I)  # 匹配字符串不区分字母大小写
print(match)

match.start()  # 匹配值的起始位置
match.end()  # 匹配值的结束位置
match.span()  # 匹配位置的元组
match.string  # 要匹配的字符串
match.group()  # 匹配到的数据

```

```python
# 使用search() 是在整个字符串中匹配第一次出现的值

import re  # 引入re模块
pattern = r'(黑客)|(抓包)|(Trojan)'
string = '我是程序员，我喜欢看黑客方面的图书，想研究一下 Trojan'
match = re.search(pattern, string)
print(match)
match.group()  # 黑客
```

```python
# findall() 在整个字符串中搜索所有符合条件的字符串，并以列表的形式返回

import re  # 引入re模块
pattern = r'tiger_\w+'  # 匹配tiger_ 开头的  前面加小 r 意思声明后面的字符是原生字符串
string = 'My is Tiger_a, is tiger_b'
match = re.findall(pattern, string, re.I)  # 不区分大小写
print(match)
```

```python
# compile 编译
import re
c = re.compile('\d+')  # compile 编译
string = '我的手机号：13188888888'
c.findall(string)
```

```python
# 小括号的用处，匹配出想要的那部分就扩起来
import re
string = 'www.baidu.com'
c = re.compile('\.(.*)\.')  # compile 编译
c.findall(string)  # 匹配baidu
```

```python
# 如果要匹配到d:\ 暂时能解决的办法就是先取 d: 在拼接一个 /
# 还有就是注意：字符串最后不允许出现一个\如果想显示\ 要写成\\

import re
string = r'd:\test\test'
pattern = 'd:'
match = re.findall(pattern, string)
print(match)  # 需要匹配出 d:\
```

替换字符串

```python
# sub() 实现字符串的替换

import re
string = '我们都喜欢在天猫或者淘宝上买东西，当当也不错啊'
c = re.compile(r'[淘宝|天猫|当当]')
str1 = c.sub('*',string)
print(str1)  # 我们都喜欢在**或者**上买东西，**也不错啊

string = '电话：15088888888'
match = re.sub('\d+', '不详', string)
print(match)  # 电话：不详
```

正则分割字符串

```python
# split() 根据正则分割 列表形式返回

import re
pattern = r'[?|&]'
url = 'http://www.baidu.com/login.asp?name=mr&age=18'
result = re.split(pattern, url)
print(result)

```

### 函数

```python
# 创建函数使用 def 关键字
def test():
    print('这是一个函数')
    
test()  # 调用函数
```

```python
# 带参数的
def test(x, y):  # 形参
    result = x + y
    print(result)
    
test(10, 20)  # 实参
```

```python
# 关键字参数
def test(name, age):
    print('名字是：' + name,'年龄是：' + age)
    
test(age='30',name='张三')  # 位置不相同 不会影响

```

```python
# 参数的默认值
def test(age, name='路人'):
    print('名字是：{} 年龄是：{}'.format(name, age))
    
test(30)  # 只传一个年龄 名字就用默认的值    
```

> 默认参数必须指向不可变的对象

```python
# 可变参数 *（实际参数可以随意个）并将其放到一个元组中
def test(*args):
    print('我喜欢吃的水果:')
    for item in args:
        print(item)

test('apple','banana','orange')  # 根据需求可写多个参数

# 同理，可以将元组当成参数传递进去
def test(*args):
    print('我喜欢吃的水果:')
    for item in args:
        print(item)

tuple1 = ('apple', 'banana', 'orange')
test(*tuple1)  # 效果一样 推荐这种
```

```python
# 可变参数 ** (也是接收任意多个实际参数) 但是实际参数是类似 关键字参数一样的显示赋值的实际参数
# 并将其放到一个字典中
def test(**kwargs):
    print()
    for key,value in kwargs.items():
        print(key, value)
        
test(name='andy', age=23, height=180)

# 同理 可以把字典当成一个参数传递进去
def test(**kwargs):
    print()
    for key,value in kwargs.items():
        print(key, value)
        
dict1 = {'name':'andy','age':23, 'height':180}
test(**dict1)  # 效果一样 推荐这种
```

```python
# 函数返回值 return
def test(x, y):
    return x + y  # 返回x+y的结果

test(10,20)
```

> python中一个py文件就是一个模块，当我们写好一个py文件后想要测试这个文件就可以使用 __name__

```python
# 比如这是1.py文件
def main():
    print('测试')

if __name__ == "main":
    main()
    
# 以上：如果单独执行这个1.py文件 main()就会被执行，但是如果把这个文件当成一个模块被使用的时候就不会执行，这就是作用，就是调试使用而已。    
```

> 局部变量只能在函数内部使用， 全局变量可以在函数的内外使用，两者最好不要重名。

```python
# 匿名函数
func = lambda x,y:x*y
func(2,3)
```



### 面向对象（oop）

> 面向对象的三大特征：封装  继承  多态

```python
# 创建类使用 class 关键字
class Animal:
    """类的帮助信息"""
    pass

monkey = Animal()  # 创建类的实例
print(monkey)
```

```python
# __init__() 方法 类似其他语言的构造方法，就是初始化成员信息的
class Animal:
    """动物类"""
    def __init__(self):  # 构造方法 self 不能缺少 否则抛异常
        print('我是动物类')
        
monkey = Animal()  # 创建动物类的实例
print(monkey)
```

```python
class Animal:
    """动物类"""
    def __init__(self, name, age):  # 初始化
        self.name = name
        self.age = age

monkey = Animal('悟空',500)
print(monkey)
print(monkey.name)  # 悟空
print(monkey.age)  # 500
```

```python
class Cat:
    def __init__(self, new_name):
        self.name = new_name

    def eat(self):  # 成员方法
        print("{}爱吃鱼".format(self.name))


tom = Cat("tom")
tom.eat()  # 调用方法

tom2 = Cat("tom2")
tom2.eat()  # 调用方法
```

```python
class Person:
    def __init__(self, name, weight):
        self.name = name
        self.weight = weight

    def __str__(self):  # 返回一个字符串 对象的描述信息

        return '我的名字叫 %s 体重 %.2f ' % (self.name, self.weight)

    def run(self):
        print("跑步锻炼身体")
        self.weight -= 0.5

    def eat(self):
        print("吃东西容易长胖")
        self.weight += 1


ming = Person("小明", 75.0)
ming.run()
ming.eat()
print(ming)
```

一个对象的 **属性** 也可以是 **另外一个类创建的对象**

```python
class Gun:

    def __init__(self, model):

        # 枪的型号
        self.model = model
        # 子弹数量
        self.bullet_count = 0

    def add_bullet(self, count):

        self.bullet_count += count

    def shoot(self):

        # 判断是否还有子弹
        if self.bullet_count <= 0:
            print("没有子弹了...")

            return

        # 发射一颗子弹
        self.bullet_count -= 1
        
        print("%s 发射子弹[%d]..." % (self.model, self.bullet_count))
```

```python
class Soldier:

    def __init__(self, name):

        # 姓名
        self.name = name
        # 枪，士兵初始没有枪 None 关键字表示什么都没有
        self.gun = None

    def fire(self):

        # 1. 判断士兵是否有枪
        if self.gun is None:
            print("[%s] 还没有枪..." % self.name)

            return

        # 2. 高喊口号
        print("冲啊...[%s]" % self.name)

        # 3. 让枪装填子弹
        self.gun.add_bullet(50)

        # 4. 让枪发射子弹
        self.gun.shoot()
```

```python
# 创建枪对象
ak47 = Gun("ak47")

# 创建士兵对象
xusanduo = Soldier("许三多")
xusanduo.gun = ak47
xusanduo.fire()
```



> 身份运算符用于 **比较** 两个对象的 **内存地址** 是否一致 —— **是否是对同一个对象的引用**

- 在 `Python` 中针对 `None` 比较时，建议使用 `is` 判断

| 运算符 | 描述                                      | 实例                            |
| ------ | ----------------------------------------- | ------------------------------- |
| is     | is 是判断两个标识符是不是引用同一个对象   | x is y，类似 id(x) == id(y)     |
| is not | is not 是判断两个标识符是不是引用不同对象 | x is not y，类似 id(a) != id(b) |

is 与 == 区别：

`is` 用于判断 **两个变量 引用对象是否为同一个**
`==` 用于判断 **引用变量的值** 是否相等



#### python私有属性和私有方法

**应用场景**

- 在实际开发中，**对象** 的 **某些属性或方法** 可能只希望 **在对象的内部被使用**，而 **不希望在外部被访问到**
- **私有属性** 就是 **对象** 不希望公开的 **属性**
- **私有方法** 就是 **对象** 不希望公开的 **方法**

**定义方式**

- 在 **定义属性或方法时**，在 **属性名或者方法名前** 增加 **两个下划线**，定义的就是 **私有** 属性或方法

```python
class Women:

    def __init__(self, name):

        self.name = name
        # 不要问女生的年龄
        self.__age = 18

    def __secret(self):
        print("我的年龄是 %d" % self.__age)


xiaofang = Women("小芳")
# 私有属性，外部不能直接访问
# print(xiaofang.__age)

# 私有方法，外部不能直接调用
# xiaofang.__secret()
```

`python` 中，并没有 **真正意义** 的 **私有**

- 在给 **属性**、**方法** 命名时，实际是对 **名称** 做了一些特殊处理，使得外界无法访问到
- **处理方式**：在 **名称** 前面加上 `_类名` => `_类名__名称`

```python
# 私有属性，外部可以如下调用
print(xiaofang._Women__age)

# 私有方法，外部可以如下调用
xiaofang._Women__secret()
```

> dir 内置函数 可以查看对象的方法列表

```python
def demo():
    """测试函数"""
    print('测试')
dir(demo)  # 查看该函数对应的方法列表
```



```python
# 定义只包含方法的类
class 类名:
    def 方法1(self, 参数):
        pass
    def 方法2(self, 参数)：
    	pass
    
# 创建对象
对象变量 = 类名()

# 调用方法
对象变量.方法1()
```

```python
# __del__ 方法 对象销毁前调用
# __str__ 方法 返回对象的描述信息 print 函数输出使用
```



#### python 继承

```python
# 单继承
class 类名(父类名):

    pass
```

##### 关于 `super`

- 在 `Python` 中 `super` 是一个 **特殊的类**
- `super()` 就是使用 `super` 类创建出来的对象
- **最常** 使用的场景就是在 **重写父类方法时**，调用 **在父类中封装的方法实现**

**也就是既要调用父类的方法，又要对该方法进行重写 则使用。**

 ```python
 # 比如下面重写父类的 bark 方法
 def bark(self):
     # 针对子类需求重写父类的bark方法
     print('重写父类的方法')
     # 同时又想保留父类的方法 就要使用super()
     super().bark()
     # 下面还可以编写其他的代码
     print('其他的代码')
 ```



**在 `Python 2.x` 时，如果需要调用父类的方法，可以使用以下方式：**(Python3中 不推荐)

```python
父类名.方法(self)
```



### 父类的 私有属性 和 私有方法

1. **子类对象** **不能** 在自己的方法内部，**直接** 访问 父类的 **私有属性** 或 **私有方法**
2. **子类对象** 可以通过 **父类** 的 **公有方法** **间接** 访问到 **私有属性** 或 **私有方法**

> - **私有属性、方法** 是对象的隐私，不对外公开，**外界** 以及 **子类** 都不能直接访问
> - **私有属性、方法** 通常用于做一些内部的事情

```python
# 多继承
class 子类名(父类名1, 父类名2...)
    pass
```

- **子类** 可以拥有 **多个父类**，并且具有 **所有父类** 的 **属性** 和 **方法**

**提示：\**开发时，应该尽量避免这种容易产生混淆的情况！\** —— 如果 \**父类之间\** 存在 \**同名的属性或者方法\**，应该 \**尽量避免\** 使用多继承**

 

- `Python` 中针对 **类** 提供了一个 **内置属性** `__mro__` 可以查看 **方法** 搜索顺序
- MRO 是 `method resolution order`，主要用于 **在多继承时判断 方法、属性 的调用 路径**

```python
print(C.__mro__)
```



#### python 新式类与旧式类

> `object` 是 `Python` 为所有对象提供的 **基类**，提供有一些内置的属性和方法，可以使用 `dir` 函数查看

- **新式类**：以 `object` 为基类的类，**推荐使用**
- **经典类**：不以 `object` 为基类的类，**不推荐使用**
- 在 `Python 3.x` 中定义类时，如果没有指定父类，会 **默认使用** `object` 作为该类的 **基类** —— `Python 3.x` 中定义的类都是 **新式类**
- 在 `Python 2.x` 中定义类时，如果没有指定父类，则不会以 `object` 作为 **基类**

> **新式类** 和 **经典类** 在多继承时 —— **会影响到方法的搜索顺序**

为了保证编写的代码能够同时在 `Python 2.x` 和 `Python 3.x` 运行！
今后在定义类时，**如果没有父类，建议统一继承自 `object`**

```python
class 类名(object):
    pass
```



> 方法重写就是派生类创建了一个和基类（父类）同名的方法，重新编写了父类方法 就是方法重写。



#### python 多态

**多态** 不同的 **子类对象** 调用相同的 **父类方法**，产生不同的执行结果

1. - **多态** 可以 **增加代码的灵活度**
   - 以 **继承** 和 **重写父类方法** 为前提
   - 是调用方法的技巧，**不会影响到类的内部设计**

```python
class Dog(object):

    def __init__(self, name):
        self.name = name

    def game(self):
        print("%s 蹦蹦跳跳的玩耍..." % self.name)


class XiaoTianDog(Dog):

    def game(self):
        print("%s 飞到天上去玩耍..." % self.name)


class Person(object):

    def __init__(self, name):
        self.name = name

    def game_with_dog(self, dog):

        print("%s 和 %s 快乐的玩耍..." % (self.name, dog.name))

        # 让狗玩耍
        dog.game()


# 1. 创建一个狗对象
# wangcai = Dog("旺财")
wangcai = XiaoTianDog("飞天旺财")

# 2. 创建一个小明对象
xiaoming = Person("小明")

# 3. 让小明调用和狗玩的方法
xiaoming.game_with_dog(wangcai)
```



#### python 类属性 和 类方法

- **类属性** 就是给 **类对象** 中定义的 **属性**（类也是一个对象）
- 通常用来记录 **与这个类相关** 的特征
- **类属性** **不会用于**记录 **具体对象的特征**

```python
class Tool(object):

    # 使用赋值语句，定义类属性，记录创建工具对象的总数
    count = 0

    def __init__(self, name):
        self.name = name

        # 针对类属性做一个计数+1
        Tool.count += 1


# 创建工具对象
tool1 = Tool("斧头")
tool2 = Tool("榔头")
tool3 = Tool("铁锹")

# 知道使用 Tool 类到底创建了多少个对象?
print("现在创建了 {} 个工具".format(Tool.count))
```



```python
# 定义类方法的语法
@classmethod
def 类方法名(cls):
    pass
```

```python
# 定义静态方法的语法
@staticmethod
def 静态方法名():
    # 不访问实例属性和类属性 就定义一个静态方法
    pass

# 通过类名.调用静态方法 不需要创建对象
```

**小结：**

1. **实例方法** - 方法内部需要访问实例属性，就可以定义实例方法
2. **类方法** - 方法内部只需要访问类属性，就可以定义类方法
3. **静态方法** - 方法内部，不需要访问实例属性和类属性，就可以定义静态方法



#### python 单例模式

- 单例设计模式

- - **目的** —— 让 **类** 创建的对象，在系统中 **只有** **唯一的一个实例**
  - 每一次执行 `类名()` 返回的对象，**内存地址是相同的**

- ```python
  class MusicPlayer(object):
  
      # 记录第一个被创建对象的引用
      instance = None
      # 记录是否执行过初始化动作
      init_flag = False
  
      def __new__(cls, *args, **kwargs):
  
          # 1. 判断类属性是否是空对象
          if cls.instance is None:
              # 2. 调用父类的方法，为第一个对象分配空间
              cls.instance = super().__new__(cls)
  
          # 3. 返回类属性保存的对象引用
          return cls.instance
  
      def __init__(self):
  
          if not MusicPlayer.init_flag:
              print("初始化音乐播放器")
  
              MusicPlayer.init_flag = True
  
  
  # 创建多个对象
  player1 = MusicPlayer()
  print(player1)
  
  player2 = MusicPlayer()
  print(player2)
  ```

- > python天生就是单例模式  把功能写到一个py文件，import 导入该模块 其实就是单例模式



### python 模块











