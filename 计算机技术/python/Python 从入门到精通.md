# Python 从入门到精通

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



