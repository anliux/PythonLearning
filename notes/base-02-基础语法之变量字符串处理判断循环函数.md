# 基础篇 02-基础语法
- 变量,字符串处理,判断,循环,函数



## 目录
<!--GFM-TOC-->
* [变量和类型](#变量和类型)
* [常见字符串处理](#常见字符串处理)
* [条件判断](#条件判断)
* [循环控制](#循环控制)
* [函数](#函数)
* [注意点](#注意点)
* [代码参考链接](#代码参考链接)
<!--GFM-TOC-->



# 变量和类型
## 基本变量类型
- ### 罗列
  - 整数
  - 浮点数
  - 字符串
  - 布尔值
  - 空值
  - 函数
  - 模块
  - 类型*
  - 自定义类型

- ### 查看类型
  - 关键字：type
  - 代码示例：
  ```
# 数据类型
print(type(1234))
print(type(12.34))
print(type(123.))
print(type('abc'))

# 结果
<class 'int'>
<class 'float'>
<class 'float'>
<class 'str'>
  ```

  ```
# 容器类型
print(type([1,2,3,'a','b']))
print(type((1,2,'abc')))
print(type(set(['a','b', 3])))
print(type({'a':1, 'b':2}))

# 结果
<class 'list'>
<class 'tuple'>
<class 'set'>
<class 'dict'>
  ```

  ```
# 函数类型：Python中，函数也是对象
def func(a,b,c):
    print(a,b,c)

print(type(func))

# 结果
<class 'function'>
  ```

```
# 模块类型：import的模块
import string
print(type(string))

# 结果
<class 'module'>
```

```
# 自定义的类和实例化的类
class MyClass():
    pass

print(type(MyClass))

my_class = MyClass()
print(type(my_class))

# 结果
<class 'type'>   #type也是类型，用来描述类型的类型
<class '__main__.MyClass'>

```


## 变量定义
- 变量存储在内存中的值。这就意味着在创建变量时会在内存中开辟一个空间。
- 基于变量的数据类型，解释器会分配指定内存，并决定什么数据可以被存储在内存中。
- 变量可以指定不同的数据类型，这些变量可以存储整数，小数或字符。（弱类型）


## 变量赋值
- 每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。（重要！！！）
  - 代码示例：
  ```
try:
    print(x)
except NameError:
    print('NameError: "x" is not defined')

# 结果
NameError: "x" is not defined
  ```
- 等号（=）用来给变量赋值，等号（=）运算符左边是一个变量名，等号（=）运算符右边是存储在变量中的值。

<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 常见字符串处理
### 字符串性质
- 不能被修改，可以通过索引访问
- 代码示例：
```
import string

# 字符串可以通过索引值访问，但不能修改
s1 = 'abc'
s1[0] = 'x'

# TypeError: 'str' object does not support item assignment
```


### 去除空格及特殊符号：
- strip, lstrip, rstrip
- 代码示例：
```
# 去除空格
s = '   abcd efg '
print(s.strip())
print(s.lstrip())
print(s.rstrip())
print(s) 
      # 注：原字符串并没有被修改

# 结果
abcd efg
abcd efg 
   abcd efg
   abcd efg 
```

### 复制字符串：
- str1 = str2


### 连接字符串
- + 加号连接
  - str2 += str1
  - new_str = str2 + str1
- 代码示例：
```
# 连接字符串
s1 = 'abc'
s2 = 'def'
print(s1 + '\n' + s2)

s2 += s1
print(s2+s1)

# 结果
abc
def
defabcabc
```


### 查找字符串
- index：返回子字符串出现的索引值，索引值从0开始计算
  - pos = str1.index(str2)
- 代码示例：
```
s4 = 'abcdefgh'
print(s4.index('fgh'))

try:
    print(s4.index('xyz'))
except ValueError:
    pass

# 结果
5
```


### 比较字符串
- 直接用大于小于等于进行比较：>, <, ==
  - 注：cmp(str1, str2)在Python3里被移除了
- 代码示例：
```
s5 = 'abcdefg'
s6 = 'abxyz'
print(s5 > s6)
print(s5 == s6)
print(s5 < s6)
print('abxyz' >= s6)

# 结果
False
False
True
True
```


### 字符串长度
- len(str)
  - 注：Python中的字符串结尾是`\0`，但len函数求长度时不包括这个结尾。
  - 注：空字符串类似False，不等价于False或None
    - None是空指针，但空字符串是分配了对象的。
- 代码示例：
```
s7 = 'abcde'
print(len(s7))

s8 = ''
print(len(s8))

if not s8:
    print('Empty')
    
if s8 == False:
    print('空字符串==False')

if s8 is None:
    print('空字符串等价于None')

# 结果
5
0
Empty
```

### 大小写转换
- upper，lower，capitalize
  - u_str = str.upper()
  - l_str = str.lower()
  - c_str = str.capitalize()
- 代码示例：
```

# 结果

```

### 首字母大写：
- str.capitalize(); string.capword(str)
- 代码示例：
```
s3 = 'abcdef' 
print(s3.upper())
print(s3.lower())
print(s3.capitalize())

# 结果
ABCDEF
abcdef
Abcdef
```



### 分割与合并字符串：
- split, splitlines, join
  - split中，传入空格时，空格的个数有效，几个空格就按几个空格分隔
  - splitlines：按行分割，与split('\n')相比，末尾换行的处理方式不同，其他情况相同。
    - 注：最后三个引号不换行时，两种按行分割的方法等价；三个引号换行时，`\n`的分割方法有个额外的空格
- 代码示例：
```
s9 = 'abc,,,def,,gh,xyz'
splitted = s9.split(',,') # 严格按照split的参数个数进行分割
print(type(splitted))
print(splitted)

s10 = """abc
def
ghi
"""
print(s10.split('\n'))
print(s10.splitlines())

s11 = ['abc', 'def', 'xyz']
print(''.join(s11))
print('--'.join(s11))
print('\n'.join(s11))

# 结果
<class 'list'>
['abc', ',def', 'gh,xyz']
['abc', 'def', 'ghi', '']
['abc', 'def', 'ghi']
abcdefxyz
abc--def--xyz
abc
def
xyz
```


### 类型转换：
- 数字到字符串：str()
  - 注：不指明小数部分，仅有小数点时，转为字符串自动补0.

- 字符串到十进制数字：
  - 可以用第二个参数指定字符串为什么进制的数字，默认十进制
  - 格式：int(str, i), i = 2 或 8 或 16

- 字符串转为list
  - 格式：list(str)，将str放入字符数组

- 代码示例：
```
# 数字转为字符串：str()

print(str(123))
print(str(123.))
print(str(123.456))
print(str(-123.456))

# 结果
123
123.0
123.456
-123.456
```

```
# 字符串转为数字，可用第二个参数指定转为的进制

print(int('1234'))
print(float('123.345'))

# print(int('123.456'))
    # invalid literal for int() with base 10: '123.456'
    # 浮点型字符串转整型数字时，会报错，不会自动转为int型。
    
print(int('110', 2))
print(int('ffff', 16))
print(int('7777',8))

# 结果
1234
123.345
6
65535
4095
```

```
# 字符串转为list（数组）

l = list('abcd')
print(l)

# 结果
['a', 'b', 'c', 'd']
```



### 格式化字符串




### 常用字符串判断
- 语法格式
  - str.startswith(prefix)	
  - str.endswith(suffix)
  - str.isalnum() # 是否全是字母和数字，并至少有一个字符。
  - str.isalpha() # 是否全是字母，并至少有一个字符。
  - str.isdigit() # 是否全是数字，并至少有一个字符。
  - str.isspace() # 是否全是空白字符，并至少有一个字符。
  - str.islower() # 字母是否全是小写
  - str.isupper() # 字母是否全是大写
  - str.istitle() # 首字母是否大写

- 注意：
  - islower和isupper：当字符串为数字和字母时，忽略数字，按照字母判断；当全为数字时，返回false

- 代码示例：
```
# 字符串判断

print('1234abcd'.isalnum()) # True
print('\t123'.isalnum()) # False

print('abc'.isalpha()) # True

print('123'.isdigit()) # True

print('   '.isspace()) # True

print('abc1234'.islower()) # True
print('ABC123'.isupper()) # True
print('123'.isupper()) # False
print('123'.islower()) # False

print('Hello WorlD'.istitle()) # False

# 结果
True
False
True
True
True
True
True
False
False
False
```

<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 条件判断
## 真值判断
- 格式：
  - if x == True:
  - if x:
  - if not x:

- 代码示例：
```
# if判断
a = 100
b = 200
c = 300
if a==c:
    print(a)
elif b==c:
    print(b)
else:
    print(c)

# 结果
300
```

### 空值判断
- 格式：
  - if x is None: 
    - 注：可以用`x==None`，建议用`is`
  - if not x:
    - 注：可以用`x is not None`，太长了

- 代码示例：
```
# if判断
a = 100
b = 200
c = 300
if a==c:
    print(a)
elif b==c:
    print(b)
else:
    print(c)

# 结果
x is None
== is ok too
not x is ok too
空字符串 相当于 False
```


### 比较
if a == b:
if a > b:
...

### Python中没有switch


<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->






# 循环控制
### for循环
- 格式：for i in range(begin, end, steps): <=> for (i = begin; i < end; i += steps)

- 代码示例：
```
# for循环

for i in range(0,30,5):
    print(i)

# 结果
0
5
10
15
20
25
```



### while循环
- 格式：while xxx: xxx
  - 规则同其他语言

- 代码示例：
```
# while循环

s = 0
i = 1
while i<=100:
    s += i
    i += 1
print(s)

# 结果
5050
```



### 循环嵌套


### 循环控制
- break continue pass
  - break: 跳出循环
  - continue: 直接终止本次循环，直接进入下次循环的判断阶段
  - pass: 什么都不做，只起到占位的作用，比如某条语句下必须有语句时，放个pass防止报错

- 代码示例：
```
# 循环控制

for i in range(0, 100):
    if i < 10:
        pass
    elif i < 30:
        continue
    elif i < 35:
        print(i)

# 结果
30
31
32
33
34
```

```
# pass 和 continue

i = 1
for element in 'python':
    if element == 't':
        pass
        i += 2
print(i)

j = 1
for element in 'python':
    if element == 't':
        continue # 下面放语句不报错，与java区别
        i += 2
print(j)

# 结果
3
1
```


### 作业：打印100000以内的所有素数




<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->




# 函数

## 函数定义格式
### 函数定义与调用
- 格式：`def func_name(arg_1, ..., arg_i):  xxx   return xxx`
  
- 返回值：单个数值时，返回值类型是int；返回多个值时，返回值类型是一个不可变元组
  - 注：用索引值取单个值，可以不用关心返回值类型。

- 代码示例：
```
# 函数定义与返回值

def func_name(arg_1, arg_2):
    print(arg_1, arg_2)
    return arg_1, arg_2

res = func_name(12, 34)
print(type(res))
print(res)
print(res[0], res[1])

# 结果
12 34
<class 'tuple'>
(12, 34)
12 34
```


### 默认参数
- 定义函数时，在形式参数位置指定默认值
  - 调用函数时，若指定实参，按照指定；若不指定实参，按照函数定义的默认值。

- 关键字实参和位置实参：
  - 不指定参数名时，默认为位置实参，按照形参位置对应实参；
  - 指定参数名时，参数的前后位置可以是任意的。
  - 没有这种设定的语言中，可以传入一个字典，实现类似的功能。

- 代码示例：
```
# 默认参数，关键字实参和位置实参

def func(x, y = 500):
    print('x =', x)
    print('y =', y)
    return x+y

print(func(100)) # 使用默认值
print(func(y = 300, x = 200)) # 使用关键字实参
print(func(400, 600)) # 使用位置实参

# 结果
x = 100
y = 500
600
x = 200
y = 300
500
x = 400
y = 600
1000
```

```
# 字典实现类似功能
def func_n(p):
    print('x =', p['x'])
    print('y =', p['y'])
    
print(func_n({'x': 100, 'y': 200}))

# 结果
x = 100
y = 200
None
```


### 可变参数：
- 当参数类型和数量不确定时：定义形参`*args`，可自动组装成tuple
  - 即：将传入的参数放入一个元组后使用。
  - 元组：等价于一个只读数组。

- 需要放入字典时：定义关键字参数：`**args`，自动组装成dict
  - `**args`对应的实参需要写为`key = 'value'`的键值对形式，否则会报错
  - 注：key值不用加引号，value需要加引号。

- 代码示例：
```
# 可变参数：*args

def func_variable(name, *numbers):
    print(type(numbers))
    print(numbers)

func_variable('Tom', 1, 2, 4, 'acd', 'xyx')

# 结果
<class 'tuple'>
(1, 2, 4, 'acd', 'xyx')
```

```
# 可变参数：**args

def func_kvs(name, **kvs): # ** means key/values
    print(name)
    print(type(kvs))
    print(kvs)
    
func_kvs('Tom', china = 'beijing', uk = 'london')

# 结果
Tom
<class 'dict'>
{'china': 'beijing', 'uk': 'london'}
```


### 命名关键字参数
- 函数定义时，参数列表中若有`*`，则星号后的参数在传参时，需要指明变量名，否则报错。
  - 即：星号后的参数必须用关键字实参。

- 格式：`def func(a, b, *, name)`
  - 传参：`func(1,3, name = 'tom')`

- 应用：见到别人的代码要能懂。

- 代码示例：
```
# 命名关键字参数

def func_keyword(a,b,c, *, china, uk):
    print(china, uk)
    
func_keyword(1,2,3,china='BJ', uk='LD')

# 结果
BJ LD
```

### 综合演示
- 形参中同时有参数默认值、可变元组、可变字典时：
  - 可变元组和可变字典没有对应格式的实参时，默认为空元组和空字典
  - 实参可以用星号和两个星号标识，并在小括号中传入相应格式的数据
    - 注：一星元组不变，二星字典由 `key='values'` 的格式改为字典的 `{'key':'values',...}`格式
    - 易错：两星字典在传参时如果标明两星，一定要用花括号。

- 代码示例：
```
# 函数定义：综合演示

def funcfunc(a,b,c=0, *args, **kvs):
    print(a,b,c)
    print(args)
    print(kvs)
    
funcfunc(1,2)
print('\n')

funcfunc(1,2,3)
print('\n')

funcfunc(1,2,3,'a','b','c')
print('\n')

funcfunc(1,3,4, china='BJ', uk='LD')
print('\n')

funcfunc(1,2,4,'a','b', china='BJ', uk='LD')
print('\n')

funcfunc(1,2,3, *('a','b'), **{'china': 'BJ', 'uk': 'LD'})
    # 注：效果同上

# 结果
1 2 0
()
{}


1 2 3
()
{}


1 2 3
('a', 'b', 'c')
{}


1 3 4
()
{'china': 'BJ', 'uk': 'LD'}


1 2 4
('a', 'b')
{'china': 'BJ', 'uk': 'LD'}


1 2 3
('a', 'b')
{'china': 'BJ', 'uk': 'LD'}
```

```
# 打印任意参数

def my_print(*args):
    print(*args)
    
my_print('x =', 100, ', y =', 200)
    # 将每个部分作为一个实参传入打印函数，并依次输出
    # 传入什么参数，就打印什么

# 结果
x = 100 , y = 200
```




## 函数调用
### 概述
- 函数名(参数名)
- 模块名.函数名(参数名)
- 带参数名调用


### 函数作为参数
- Python中，函数也是一个对象，因此可以作为实参进行传递

- 代码示例：
```
# 函数作为参数：示例1

def my_sum(x, y, p = None):
    s = x + y
    if p:
        p(s)
    return s

my_sum(100, 200)
my_sum(100, 200, print)
    # 参数p不为None时，执行传入的p，即print(s)，打印s的值

# 结果
300
```

```
# 函数作为参数：示例2

def cmp(x, y, cp = None):
    if not cp:
        if x > y:
            return 1
        elif x < y:
            return -1
        else:
            return 0
    else:
        return cp(x, y)
    
def my_cp(x, y):
    if x > y:
        return -1
    elif x < y:
        return 1
    else:
        return 0
    
print(cmp(100, 200))
print(cmp(100, 200, my_cp))

# 结果
-1
1
```

```
# 函数作为参数：示例3

def do_sum(data, method):
    return method(data)

print(do_sum([1, 3, 4, 6], sum))

# 结果
# 输出：14

```



## 递归
### 递归求和
- 分解：sum(n) = n + sum(n-1)

- 代码示例：
```
# 递归求和

def my_sum(i):
    if i < 0:
        raise ValueError
    elif i <= 1:
        return i
    else:
        return i + my_sum(i - 1)
    
print(my_sum(100))
print(my_sum(-1))

# 结果
5050
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-132-bdde1cc1e7da> in <module>()
...
...
```

### 斐波那契数列
- 斐波那契数列：f(n) = f(n-1) + f(n-2)
  - 注：1、1、2、3、5、8、13、21、34
  - 以两个1开头，剩余数列按照公式可以推出。

- 用递归求斐波那契数列，当n=40时，速度非常慢

- 代码示例：
```
# 递归求斐波那契数列

def fib(n):
    if n < 1:
        raise ValueError
    elif n <= 2:
        return n
    else:
        return fib(n-1) + fib(n-2)
    
print(fib(1))
print(fib(2))
print(fib(3))
print(fib(4))
print(fib(5))

# 结果
1
2
3
5
8
```

### 汉诺塔
- 借助塔C，将塔A的盘子移动到塔B
  - 若只有1个：直接移动
  - 否则：先将n-1个盘子借助B移动到C，然后将A的最后一个盘子移动到B，最后将n-1个盘子从C借助A移动到B.

- 代码示例：
```
# 递归实现汉诺塔

def hanoi(n, A, B, C):
    if n == 1:
        print(A + '-->' + B)
    else:
        hanoi(n-1, A, C, B)
        print(A + '-->'+ B)
        hanoi(n-1, C, B, A)
        
hanoi(1, 'A', 'B', 'C')
print('\n')
hanoi(4, 'A', 'B', 'C')

# 结果
A-->B


A-->C
A-->B
C-->B
A-->C
B-->A
B-->C
A-->C
A-->B
C-->B
C-->A
B-->A
C-->B
A-->C
A-->B
C-->B
```


<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 注意点

## 关于print的一些规则
- print中，同时打印int型和string型时，不能用+加号直接连接，会报错
  - 与java中的自动类型转换区别

- print同时打印int型和string型，用逗号连接即可，输出时默认在连接位置加一个空格
  - 输入：`print(123,'string')`
  - 输出：123 string


- print中的`\n`：
  - 数字中间换行的方法：
    - print(str(A) + "\n" + str(B))
    - print("%d\n%d" % (A, B))


<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 代码参考链接
- [base-02代码]()

<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->


### END