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

#### 



