# 基础篇 03-



## 目录
<!--GFM-TOC-->
* [容器](#容器)
* [切片](#切片)
* [列表推导](#列表推导)
* [生成器](#生成器)
* [迭代器](#迭代器)
* [注意点](#注意点)
* [代码参考链接](#代码参考链接)
<!--GFM-TOC-->



# 容器
## 概述
- list 列表
  - 序列是Python中最基本的数据结构。序列中的每个元素都分配一个数字 
    - 索引：第一个索引是0，第二个索引是1，依此类推。
  - 列表的数据项不需要具有相同的类型

- tuple 元组（只读列表）

- dict 字典
  - 字典的每个键值(key=>value)对用冒号(:)分割，每个对之间用逗号(,)分割，整个字典包括在花括号({})中。

- set 集合
  - 是一个无序不重复元素集, 基本功能包括关系测试和消除重复元素. 
  - 集合对象还支持union(联合), intersection(交), difference(差)和sysmmetric difference(对称差集)等数学运算。



## list/tuple基本操作
### 基本操作：创建、访问、查找元素索引
- 创建：可以装入任意类型元素

- 访问元素：方括号索引值
  - 提供负数索引，可以从末尾向前数
  - 注：没有提供负数索引时，需要先求长度，然后按照长度值减去某个数来取
    - 示例：`print(li[len(li)-1])`

- 查找元素：listname.index('xxx')
  - 没有index函数时：for循环遍历并依次比较来查找。
  - 注：找不到元素时，抛出异常；因此不确定元素是否在list中时，用try-except

- 代码示例：
```
# list的创建、访问、查找元素位置

# 创建
li = [1,2,4, '456', [1,3,5], {1:'one', 2: 'two'}] # 可以存入任意类型元素
print(type(list)) # 内置类型：对应type class
print(type(li)) # 类型实例：对应list class

# 访问元素
print(li[0])
print(li[-1])

# 查找元素：index函数
print(li.index('456'))
print(li.index([1,3,5]))
# print(li.index(-1)) # 找不到，会抛出异常；不确定是否存在时，将语句用try-except括起来

# 结果
<class 'type'>
<class 'list'>
1
{1: 'one', 2: 'two'}
3
4
```

### 添加元素（list only）
- 添加任意单个元素：append
  - 如果用append添加list到list，则后面append的list会直接作为一个元素添加入原list

- 添加list并将list中的元素依次添加到列表：extend

- 代码示例：
```
# list添加元素：append， extend

l_a = [1,2,3]
l_a.append(4)
l_a.append(5)
print(l_a)

l_a.extend([6,7,8])
print(l_a)

l_a.append([9,10,11])
print(l_a)

# 结果
[1, 2, 3, 4, 5]
[1, 2, 3, 4, 5, 6, 7, 8]
[1, 2, 3, 4, 5, 6, 7, 8, [9, 10, 11]]

```

### 判断容器是否为空
- 判空: if not xx; if len(xx)==0

- xxx is None：不用来判空，因为空list和None不是一回事

- 注意：
  - list变量可以赋值为None，但list=[] 和 list=None不是一回事

- 代码示例：
```
# list判空

l_a = []
if not l_a:
    print('Empty: not xx') # 注：not xx和is None不是一回事
    
if len(l_a)==0:
    print('Empty: len')
    
if l_a is None:
    print('Empty: None')

# 结果
Empty: not xx
Empty: len
```


### 遍历
- 两种for循环：
  - Python特色：`for i in listname: xxx`
  - 普适的通过长度控制for循环，并使用循环变量对应的索引值取元素：`for i in range(len(listname)): print(listname[i])`

- 代码示例：
```
# list循环

for i in li:
    print(i)
    
print('\n')

for i in range(len(li)):
    print(li[i])

# 结果
1
2
4
456
[1, 3, 5]
{1: 'one', 2: 'two'}


1
2
4
456
[1, 3, 5]
{1: 'one', 2: 'two'}
```


### 删除元素（list only）：
- del

- pop

- 代码示例：
```



```



### 根据索引读写（tuple只读）





### 字符串转换


### 容器元素数量	



### 练习
- 两数之和
  - 代码示例：
  ```


  ```

## dict基本操作
初始化
访问
添加元素
修改元素	
删除元素
判断key是否存在	
判断容器是否为空
容器元素数量	
遍历
参考代码：lesson_03_dict.py


## set基本操作
并/交/差集：|/union, &/intersection, -/difference
对称差集：^/symmetric_difference（不同时出现在2个集合中的项）
包含关系：>=/issuperset
添加元素
更新元素
删除元素
元素是否存在
容器元素数量
遍历
参考代码：lesson_04_set.py




<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 切片


<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 列表推导


<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->





# 生成器




<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->





# 迭代器





<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



### END