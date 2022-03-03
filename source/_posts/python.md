---
title: python基础语法学习归档
top: false
top_img: https://s2.loli.net/2022/02/24/TJX1jfQ7M59np8V.png
cover: false
toc: true
mathjax: false
date: 2022-02-24 17:34:50
author: 以西
img:
coverImg:
password:
summary:
categories:
 - 编程
 - python
tags: 
 - python
 - 学习指南
---

记录下py自学道路上的苦难🐶

# 常用报错类型


```
SyntaxError: unexpected EOF while parsing  
语法错误，多了无法解析的符号，检查一下是否多了或者少了括号

SyntaxError: invalid character in identifier  
#语法错误有无效标识符，检查一下中文符号

IndexError: list index out of range 
#索引错误，超出索引范围，检查一下列表是否为空

TypeError: must be str, not int
#数据类型错误，该数据不是正确的数据类型，比如字符串和数字直接拼接，检查一下数据类型

IndentationError: expected an indented block
#缩进错误，检查一下代码的缩进是否正确

KeyError:  'fond'
#键错误，字典中没有该的key对应的值，检查一下键名或者字典数据是否正确

ValueError: substring not found
#值错误，输入的数据类型跟要求的不符合

NameError: name 'a' is not defined
#未初始化对象，变量没有被定义

AttributeError: 'tuple' object has no attribute 'remove'
#属性错误，该对象没有这个属性、方法，检查一下数据类型

SystemExit    
#解释器请求退出，出现在exit()函数后

IOError    
#输入/输出操作失败

ImportError    
#导入模块/对象失败，检查一下模块是否能够正常使用

UnicodeDecodeError/UnicodeEncodeError/UnicodeTranslateError
#Unicode 解码/编码/转换/时的错误
```

