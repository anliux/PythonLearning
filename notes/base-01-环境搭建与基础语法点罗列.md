# 基础篇 01-环境搭建与基础语法


## 目录
<!--GFM-TOC-->
* [Python简介](#Python简介)
* [为什么选择Python](#为什么选择Python)
* [环境搭建](#环境搭建)
* [如何学好编程](#如何学好编程)
* [常用关键字](#常用关键字)
* [基本运算符](#基本运算符)
* [基本语法](#基本语法)
* [2.x和3.x的区别](#2.x和3.x的区别)
<!--GFM-TOC-->



# Python简介
- 官网：https://www.python.org/
- 作者：Guido van Rossum
- 名字来源：Monty Python's Flying Circus
- 历史
  - 为什么发明Python？C语言开发效率太低，而shell只是一种胶水语言。作者的目的：创造一种C和shell之间，功能全面，易学易用，可拓展的语言。
- 当前主流版本：2.7.12，3.5.2
- 版本选择
  - 至少选择2.7版本
  - 2和3的主要区别：部分语法不兼容，数据类型的变化，异常的改进......一般情况下可自行百度解决。

- ### 优点：
  - 简单，容易学习。
  - 免费开源
  - 高级语言，细节隐藏。
  - 解释性，可移植。一次编写，到处运行。
  - 面向对象
  - 可扩展。可嵌入C/C++，或者使用C/C++提高性能。
  - 扩展库
- ### 缺点：
  - 慢！
  - shell脚本不友好

<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 为什么选择Python
- 语法简单
- 应用场景丰富
  - 接口测试
  - UI自动化
  - 数据分析处理
- 技术成熟，大量参考/例子代码

<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 环境搭建
- Windows一键安装：2.7.12 (x86-64)，3.5.2 (x86-64)
- Mac系统自带
  - 通过homrbrew和pyenv安装并维护多个Python版本，参考链接。
  - Anaconda集成环境安装（特别针对数据科学），参考链接。
- Linux系统自带
  - 通过pyenv安装并维护多个Python版本，参考链接。

- Windows平台：pip install package

- Mac平台
  - 打开sudo功能，参考链接。
  - sudo pip install package
  - 使用sudo后如果遇到"operation not permitted"的提示，请在后面加上--user参数，命令行为：sudo pip install package --user 具体原因为新版本OSX的SIP机制（System Integrity Protection）。

- 指定源：pip install package -i --trusted-host site（在PowerShell下使用）

- Notebook安装使用
  - pip install ipython
  - pip install notebook
  - pip install tornado
  - 执行：jupyter-notebook（笔记本文件后缀名为.ipynb）
- 新建和打开文件

<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 如何学好编程
- ### 基础部分
  - 基本语法
  - 数据结构
  - 输入输出
  - 异常处理

- ### 进阶提高
  - 常用算法
  - 数据库访问
  - 面向对向
  - 其它

- ### 基本语法
  - 基本数据类型
  - 对象的定义和声明
  - 循环和判断：for, foreach, if, while, do...
  - 逻辑运算
  - 位运算

- ### 数据结构
  - 数组：重要
  - 字符串：重要
  - 系统标准库自带的类型
  - 如何实现常用数据结构：链表、堆栈、二叉树...

- ### 输入输出
  - 标准输出输出：print, echo, input...
  - 文件读写：文本/二进制
    - 文本：行读写
    - 二进制：偏移量+大小
  - 格式化字符串
    - 举例：print("%s, %d", %("aaa", 100))

- ### 异常
  - 抛出和捕获异常：try/catch, try/except...
  - 异常和错误的区别以及应用场合

- ### 常用算法
  - 分治
  - 贪心
  - 动态规划

- ### 数据库访问：重点
  - 建立连接
  - 执行SQL查询
  - 读取查询记录

- ### 面向对象
  - 继承
  - 多态
  - 静态变量与方法

- ### 进阶
  - 多线程/进程
  - 匿名函数
  - 语言相关特定知识
    - Java的反射
    - C++的模板
    - Python的协程...

<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 常用关键字

### 常量
- True
- False
- None


### 对象和容器
- class
- import
- from
- del


### 判断
- if
- elif
- else
- is
- in
- assert


### 循环
- for
- while
- continue
- break
- pass：什么都不做，用在单元测试、跳过歧义语句等；
  - continue：跳出当前循环，并继续下次循环。
  

### 异常
- raise
- try
- except
- finally
- as

<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->




# 基本运算符

### 算术运算
- +-*/
- %
- **：乘方，`x ** y` 表示x的y次方。
- //：除法，结果取整数部分。


### 比较运算
- >, >=
- <, <=
- ==
- !=
  - 注：2.x中用<>表示不等于


### 逻辑运算
- and
- or
- not
- 没有异或：`not(boolean1==boolean2)`


### 位运算
- >>
- <<
- &
- |
- ^

<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 基本语法

- 缩进
  - 区分代码块
  - 用空格或用tab，需要统一

- 注释
  - 单行：井号
  - 多行：两排引号

- 多行代码表示
  - 多行表示单行：文末用右斜杠，表示下一行也是本行内容
  - 字符串中间换行：中间加`\n`，在这个位置换行
  - 字符串中间换行：用三个双引号在字符串开始位置和终止位置来标识所有字符串
    - eg：`str = """hello (换行) world"""`，打印为hello一行，world一行。

- 引号：
  - 在单引号里用双引号，或者在双引号里用单引号，可以不用转义`\"`，直接识别为符号

- 中文支持
  - 如果中文支持不好，可以在代码开始加声明
  - `# -*- coding: utf-8 -*-`
  - 或者新的可以写为：`# coding: utf-8`

<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



# 2.x和3.x的区别
- print函数：3.x必须加()
  - 3.x：`print(2,3,4 )`
  - 2.x不加，可以直接打印：`print 2,3,4`

- unicode: 3.x默认使用unicode编码

- 除法：3.x整数相除也能得到浮点数结果

- 异常：3.x只能抛出继承自BaseException的异常

- xrange：3.x取消了xrange，range和xrange一样为实现为惰性求值

- 二进制八进制：3.x必须强制写成0b1011和0o7236

- 不等式：3.x取消了`<>`，只有`!=`

- "表达式：3.x必须使用repr函数

- 多个模块改名：Queue -> queue, repr -> reprlib..

- 数据类型：
  - 3.x取消了long，统一为int
  - 新增bytes类型，并可与string相互转换
    - `print((1024).to_bytes(2, byteorder = 'big'))` -- 2: 2个字节，16位整数；big：高位在前
      - 显示：`b '\x04\x00`
    - `print((-1024).to_bytes(2, byteorder = 'big', signed = True)`
      - 显示：`b'\xfc/x00`
  - dict的keys/items/values方法返回迭代器，iterkeys函数被废弃，has_key被int取代。

<!--GFM-TOC -->
* ### [返回目录](#目录)
<!--GFM-TOC -->



### END