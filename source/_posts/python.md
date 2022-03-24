---
title: python基础语法学习归档
top: false
top_img: https://s2.loli.net/2022/02/24/TJX1jfQ7M59np8V.png
cover: false
toc: true
mathjax: false
date: 2022-03-09 17:34:50
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

# 数据处理

## print( )函数

```python
print(*objects, sep = ' ', end = '\n', file = sys.stdout, flush = False)

print('金枪鱼', '三文鱼', '鲷鱼')
print('金枪鱼', '三文鱼', '鲷鱼', sep = '+')
# sep控制多个值之间的分隔符，默认是空格
print('金枪鱼', '三文鱼', '鲷鱼', sep = '+', end = '=?')
# end控制打印结果的结尾，默认是换行)
>>>金枪鱼 三文鱼 鲷鱼
金枪鱼+三文鱼+鲷鱼
金枪鱼+三文鱼+鲷鱼=?
```

```python
#无引号 计算机识别括号中的内容后打印结果
print(1+1)
>>>2

#单引号 计算机无需理解内容,原样复述引号中的内容
print('1+1')
>>>1+1

#双引号 计算机无需理解,原样复述引号中的内容，可以输出内容中的单引号
print("let's go")
>>>let's go

#三引号 计算机无需理解,原样复述引号中的内容，可以保留引号内原格式
print('''黑夜给了我黑色的眼睛，
我却用它寻找光明。''')
>>>黑夜给了我黑色的眼睛，
我却用它寻找光明。
```

print( )函数里有个参数'end'是用来控制换行行数和结尾字符，在print( )结尾加入`end=''`可实现输出不换行

```python
print('hello',end='')
print('world')
>>>helloworld

print('hello',end='  ')
print('world')
>>>hello  world

print('hello',end='!')
print('world')
>>>hello!world
```

`print('')` 用来换行

##  变量与赋值

变量的命名

- 只能是一个词
- 只能包含字母、数字和下划线
- 不能出现操作符 + - 等
- 不能以数字开头
- 尽量描述包含的数据内容
- 不要使用Python函数名或关键字

赋值符号`=`不是左边等于右边的意思。仅仅表示赋值动作

运算符`= =`代表左右两边相等的符号	

```python
#赋值
name = '以西'
#等于
name = = '以西'
```

## 常用转义字符

【\】+ 转义内容英文缩写首字母

| 转义字符 |                 意义                  |
| :------: | :-----------------------------------: |
|    \a    |               响铃(BEL)               |
|    \b    |     退格(BS),将当前位置移到前一列     |
|    \f    |    换页(FF),将当前位置移到下页开头    |
|    \n    | 换行(LF),将当前位置移到下一行开头回车 |
|    \r    |    回车(CR),将当前位置移到本行开头    |
|    \t    |    水平制表(HT)(跳到下一个TAB位置)    |
|    \v    |             垂直制表(VT)              |
|   \\\    |         代表一个反斜线字符“\”         |
|   \\'    |          代表一个单引号字符           |
|   \\"    |          代表一个双引号字符           |
|    \0    |             空字符（NUL）             |
|   \ddd   |      1到3八进制所代表的任意字符       |
|   \xhh   |    1到2位十六进制所代表的任意字符     |

## 数据类型与转换

### 数据类型

- 字符串（str）
  - 有层名为【引号】的皮，只要是被【单/双/三引号】这层皮括起来的内容，不论内容是中文、英文、数字甚至火星文。只要是被括起来的，就表示是字符串类型。
- 整数（int）
  - 整数即正整数、负整数和零的统称，是没有小数点的数字。
  - 摆脱了引号的马甲
- 浮点数（float）
  - 比整数多了一个小数点『.』
  - 浮点数的运算是不精确的（计算机在计算时，会将数字转换为二进制数，转换的过程中出现了误差）

### type( )函数

```python
print(type(1))
>>> <type 'int'>
print(type('runoob'))
>>> <type 'str'>
print(type([2]))
>>> <type 'list'>
print(type({0:'zero'}))
>>> <type 'dict'>
```

用来判断数据类型

### 运算符

| 运算符 |           表示            |   案例   |
| :----: | :-----------------------: | :------: |
|   +    |            加             | 1+1>>>2  |
|   -    |            减             | 1-1>>>0  |
|   *    |            乘             | 2*2>>>4  |
|   /    |            除             | 2/2>>>1  |
|   %    |    取模 - 返回除的余数    | 5%2>>>1  |
|   //   | 取整除 - 返回商的整数部分 | 5//2>>>2 |
|   **   |     幂 - 返回x的y次幂     | 2**3>>>8 |

运算顺序：从左到右、括号里的优先、先乘除后加减

tips：

- '/'为浮点数除法，返回的为浮点结果，print( 16/4 ) >>> 4.0

### 字符串的拼接

- 直接用【 + 】将数据进行拼接
- 不同类型的数据要经过转换后才可以拼接

### 数据转换

负责转换数据类型的函数一共有3种：

- str( )
  - 将其他数据类型转成字符串
-  int( )
  - 将其他数据类型转成整数
  - 只有符合整数规范的**字符串类**数据，才能被int( )强制转换
  - 文字形式，比如中文、英文或者标点符号，不可以被int( )函数强制转换
  - 小数形式的**字符串**，由于Python的语法规则，也不能使用int( )函数强制转换
    - 对于小数类型的字符串的转化，需要先将其转换为浮点数，再转换为整数
  - int( )函数的本质是将数据转换为整数。所以对于浮点数，int()函数会做取整处理，即直接输出整数部分。
- float( )
  - 将其他数据类型转成浮点数
  - float( )函数也可以将**整数**和**字符串**转换为浮点类型。如果括号里面的数据是**字符串**类型，那这个数据一定得是数字形式

### 格式化字符串

我们在用`+`拼接字符串和变量的时候，常常需要考虑变量是什么类型的数据，如果不是字符串类型，还先需要str()函数转换

为了更方便地实现不同数据类型的拼接，用【格式符`%`】是更常用更便利的一种方式

```python
print('我把'+str(22)+'块钱放在'+str(2)+'个口袋里')
print('我把%s块钱放在%s个口袋里' % (22,2))
```

格式符`%`后面有一个字母s，这是一个类型码，用来控制数据显示的类型。`%s`就表示先占一个字符串类型的位置

其他常见的类型码：

| 格式符+类型码 |    含义    |
| :-----------: | :--------: |
|      %s       | 字符串显示 |
|      %f       | 浮点数显示 |
|      %d       |  整数显示  |

`%`后面的类型码用什么，取决于希望这个`%`占住的这个位置的数据以什么类型展示出来，如果你希望它以字符串形式展示，那就写`%s`，如果你希望它以整数形式展示，那就写`%d`

`%f`的意思是格式化字符串为`浮点型`，`%.1f`的意思是格式化字符串为`浮点型`，并`保留1位小数`。

ps：

```python
print('我的幸运数字是%d' % (8)  #8以整数展示
print('我的幸运数字是%s' % (8)  #8以字符串展示

print(8) #整数8与字符串'8'打印出来的结果是一样的
print('8')
```

选用了不同的类型码，打印出的结果却是一样，原因也已经在代码注释中写清楚了：因为整数8与字符串'8'的打印结果是一样的，所以选两种类型码都OK。但这种“都OK”的情况仅限于整数，对文字是行不通的

#### format( )函数

format()函数用来占位的是大括号{}，不用区分类型码（%+类型码）
具体的语法是：`str.format()`

```python
# % 格式化：str % ()
print('%s%d'%('数字：',0))
print('%d，%d'%(0,1))
print('%d，%d，%d'%(0,1,0))

name1 = 'Python'
print('I am learning %s'% name1)  # 注：当只跟一个数据时，%后可不加括号，format()一定要有。

# format()格式化函数：str.format()
print('{}{}'.format('数字：',0))  # 优势1：不用担心用错类型码。
print('{}，{}'.format(0,1))  # 不设置指定位置时，默认按顺序对应。
print('{1}，{0}'.format(0,1))  # 优势2：当设置指定位置时，按指定的对应。
print('{0}，{1}，{0}'.format(0,1))  # 优势3：可多次调用format后的数据。

name2 =  'Python基础语法'
print('我正在学{}'.format(name2))  # format()函数也接受通过参数传入数据。

```

## 条件判断与条件嵌套

### 条件判断

- 单向判断
  - if...
- 双向判断
  - if...else...
  - else后边不需要跟限制条件
  - if和else为互斥关系，即不满足**if条件**，就执行**else其他条件**
- 多向判断
  - if...elif...elif...else...
  - elif后可不接else

对于Python而言，冒号和缩进是一种语法。它会帮助Python区分代码之间的层次，理解条件执行的逻辑及先后顺序。【注：**缩进**是四个空格或一个Tab键】

### if嵌套

条件套条件，在原有的基础条件上附件一个额外条件

- 根据缩进判断层级
- 根据层级按行执行
- 根据赋值判断是否适合条件，适合则执行条件下命令，不适合则进入下一判断
- if嵌套涉及多个条件判断，并且是条件套条件的判断，所以为了理清逻辑，可采用**扒洋葱**大法写**if嵌套**
  - 写基础条件代码
  - 写基础条件1的额外条件
  - 写基础条件2的额外条件
  - ...

## input( )函数

input()函数是输入函数，当你在函数的括号内写出问题时，input()函数会将此问题原样显示在屏幕上，并在终端区域等待针对此问题的回答，即输入值。

同时，为了能随时且方便地提取**输入值**，需要把input( )函数的结果赋给变量

`xxx = input()`

不管在终端区域输入任何数据类型，input( )函数的输入值一定会强制转换为字符串类型

```python
choice = input('请输入1或2:')
print(type(choice))
>>> <class 'str'>
```

所以在利用输入值进行条件判断时，注意 = = 前后的数据类型

```python
choice = input('请输入您的选择：')
#变量赋值

if choice == 1: #（此处会出现报错，因为 choice 和 1 的数据类型不同） 
#条件判断:条件1
    print('xxxxxxx')
#条件1的结果

else:
#条件判断：其他条件
    print('xxxxxxxx')
#其他条件的结果
```

当整数数据类型较多时，可以进行input( )函数结果的强制转换

即`choice = int(input('请输入您的选择：'))`

## 数据的储存

### 列表

#### 什么是列表

列表（list）的代码格式：`number = [1,2.5,'3'] `

一个列表需要用中括号`[ ]`把里面的各种数据框起来，里面的每一个数据叫作“元素”。每个元素之间都要用英文逗号隔开

列表可以容纳各种类型的数据（整数/浮点数/字符串/列表/元组/字典）

#### 从列表提取单个元素

每个元素都有自己的位置编号（即偏移量）

- 偏移量是从0开始
- 列表名后加带偏移量的中括号，就能取到相应位置的元素。
- 通过偏移量来对列表进行索引（可理解为搜索定位），读取我们所需的元素。
-  列表可通过正负索引来取值，正索引是第一个元素为**0**，负数索引表示从右边往左数，最右边的元素的索引为-1，倒数第二个元素为-2，同样遵循列表切片规律

```python
number = [1,2.5,'3']
print(number[0])
>>>1
print(number[2])
>>>3
```

#### 从列表提取多个元素

下列`:`左右两边的数字指的是列表中元素的偏移量，记住偏移量始终是从0开始的

```python
list = [5,6,7,8,9]
print(list[:])
print(list[2:])
print(list[:2])
print(list[1:3])
print(list[2:4])
print(list[-3:-1])
>>>[5, 6, 7, 8, 9]
[7, 8, 9]
[5, 6]
[6, 7]
[7, 8]
[7, 8]
```

列表切片规律：左右空，取到头；左要取。右不取（冒号左边空，就要从偏移量为0的元素开始取；右边空，就要取到列表的最后一个元素。冒号左边数字对应的元素要拿，右边的不动）

偏移量取到的是列表中的元素，而切片则是截取了列表的某部分，所以还是数据类型还是列表

#### 给列表增加元素

##### append函数

`list.append()`

用append( )给列表增加元素，每次只能增加一个元素

append函数并不生成一个新列表，而是让列表末尾新增一个元素

```python
list = [1,2,3]
list.append(4,5)
print(list)
>>>TypeError: append() takes exactly one argument (2 given)
list.append([4,5])
print(list)
>>>[1, 2, 3, [4, 5]]

```

append函数没有返回值（或者说返回值是：None）

a.appent(i) 本身就是对列表a进行增加值，并返回一个None

所以a=a.append(i) 这个是错误的，a.append（i） 已满足你的需求了。

```python
a=[]
for i in range(7):
	a=a.append(i)
print(a)
>>>AttributeError: 'NoneType' object has no attribute 'append'

a=[]
for i in range(7):
	a.append(i)
print(a)
>>>[0, 1, 2, 3, 4, 5, 6]
```

##### pop( )函数

用于移除列表中的一个元素（默认最后一个元素），并且返回该元素的值

- 提取：取到元素，对列表没有影响
- 删除：删除列表的元素。

```python
list1 = ['0','1','2','3']
print(list1.pop())  # 默认删除最后一个元素，并返回该元素的值。
>>>3
print(list1)
>>>['0', '1', '2']
print(list1.pop(0))  # 也可指定删除某个元素，并返回该元素的值。
>>>0
print(list1)
>>>['1', '2']
```

#### 给列表删除元素

##### del语句

`del list[ ]`

既能删除一个元素，也能一次删除多个元素（原理和切片类似，左取右不取）

#### 复制列表

`list.copy()`

#### 合并列表

- append( )
  - a.append(b) 将b作为一个整体（数据项）加到a的最后

```python
a = [1, 2, 3]
b = ['A', 'B', 'C']
a.append(b)
print a
>>>[1, 2, 3, ['A', 'B', 'C']]
```

- extend( )
  - a.extend(b) 将b中的元素逐个（数据集合）加到a的最后

```python
a = [1, 2, 3]
b = ['A', 'B', 'C']
a.extend(b)
print a
>>>[1, 2, 3, 'A', 'B', 'C']
```

- insert( )
  - a.insert(i，b) 将b作为一个整体（数据项）加到a中第i个位置

```python
a = [1, 2, 3]
b = ['A', 'B', 'C']
a.insert(1,b)
print a
>>>[1, ['A', 'B', 'C'], 2, 3]
```

- a+b 两个list直接相加（按原list中元素顺序合并）

```python
a = [1, 2, 3]
b = ['A', 'B', 'C', 1]
c = a + b
print c
>>>[1, 2, 3, 'A', 'B', 'C', 1]
```

- a[i:i]=b 切片操作

```python
a = [1, 2, 3]
b = ['A', 'B', 'C', 1]
a[len(a):len(a)] = b
c = a
print c
>>>[1, 2, 3, 'A', 'B', 'C', 1]  #b合并到a的位置由a[i:i]=b中的i决定
```

#### 列表排序

**sort()** 函数用于对原列表进行排序，如果指定参数，则使用比较函数指定的比较函数，该方法没有返回值

sort()方法语法：

`list.sort(cmp=None, key=None, reverse=False)`

- cmp -- 可选参数, 如果指定了该参数会使用该参数的方法进行排序。
- key -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。
- reverse -- 排序规则，**reverse = True** 降序， **reverse = False** 升序（默认）。

#### index函数

index( ) 函数用于找出列表中某个元素第一次出现的索引位置。
语法为：`list.index(obj)`

```python
num = [0,1,0,1,2]
print(num.index(1))  # 数字1首先出现的索引位置是list[1]（索引位置从0开始）。
print(num.index(2))  # 数字2首先出现的索引位置是list[4]。
>>>1
4
```

### 字典

#### 什么是字典

`scores = {'同学1':100,'同学2':95,'同学3':88,'同学4':59}`

字典和列表有3个地方是一样的：

- 有名称
- 要用`=`赋值
- 用逗号作为元素间的分隔符

而不一样的有两处：

- 列表外层用的是中括号`[ ]`，字典的外层是大括号`{ }`
- 列表中的元素是自成一体的，而字典的元素是由一个个键值对构成的，用英文冒号连接。如`'同学1':100`，`'同学1'`叫键（key），`100`叫值(value)
- 唯一的键和对应的值形成的组合，我们就叫做【键值对】
- 字典中的键具备唯一性，而值可重复
  - 即如果不小心声明了两个以`'同学1'`为键的【键值对】，后出现的【键值对】会覆盖前面的【键值对】
  - 字典中键是唯一的，如果重复最后的一个键值对会替换前面的。

```python
dict = {'a': 1, 'b': 2, 'b': '3'}
print(dict)
print(dict['b'])
>>> {'a': 1, 'b': '3'}
```



#### 从字典提取元素

从字典中提取对应的值的用法。和列表相似的是要用`[ ]`，不过因为字典没有偏移量，所以在中括号中应该写键的名称

即`dict['同学1']`

#### 给字典增加元素

新增键值对要用到赋值语句`dict[key] = value`

#### 给字典删除元素

删除字典里键值对的代码是del语句`del dict[key]`

### 元组

元组和列表很相似，不同之处在于元组的元素不能修改。

`tuple = ('A','B')`

元组和列表都是序列,提取的方式也是偏移量，如 tuple[1]、tuple[1:]，另外，元组也支持任意的嵌套

元组中只包含一个元素时，需要在元素后面添加逗号

`tup1 = (50,)`

### 列表和字典的异同

#### 异

```python
students1 = ['小明','小红','小刚']
students2 = ['小刚','小明','小红']
print(students1 == students2)
>>>False

scores1 = {'小明':95,'小红':90,'小刚':100}
scores2 = {'小刚':100,'小明':95,'小红':90}
print(scores1 == scores2)
>>>True
```

- 一个很重要的不同点是列表中的元素是有自己明确的“位置”的，所以即使看似相同的元素，只要在列表所处的位置不同，它们就是两个不同的元素，但字典调动顺序则不影响。
- 因为列表中的数据是有序排列的，而字典中的数据是随机排列的。
- 列表有序，要用偏移量定位；字典无序，便通过唯一的键来取值。

#### 同

- 在列表和字典中，如果要**修改**元素，都可用赋值语句来完成

```python
list1 = ['1','2','3','4']
list1[1] = '100'
print(list1)
>>> ['1', '100', '3', '4']

dict1 = {'小明':'男'}
dict1['小明'] = '女'
print(dict1)
>>> {'小明': '女'}
```

- 支持任意嵌套
  - 列表可嵌套其他列表和字典，字典也可嵌套其他字典和列表。

```python
#列表的嵌套类型
number = [['1','2','3','4'],['5','6','7','8']]
print(students[1][3])
>>>8
```

```python
#字典的嵌套类型
scores = {
    '第一组':{'小明':95,'小红':90,'小刚':100,'小美':85},
    '第二组':{'小强':99,'小兰':89,'小伟':93,'小芳':88}
    }
print(scores['第二组']['小芳'])
>>> 88
```

```python
#列表和字典相互嵌套
# 最外层是大括号，所以是字典嵌套列表，先找到字典的键对应的列表，再判断列表中要取出元素的偏移量
students = {
    '第一组':['小明','小红','小刚','小美'],
    '第二组':['小强','小兰','小伟','小芳']
    }
print(students['第一组'][3])
#取出'第一组'对应列表偏移量为3的元素，即'小美'

# 最外层是中括号，所以是列表嵌套字典，先判断字典是列表的第几个元素，再找出要取出的值相对应的键
scores = [
    {'小明':95,'小红':90,'小刚':100,'小美':85},
    {'小强':99,'小兰':89,'小伟':93,'小芳':88}
    ]
print(scores[1]['小强'])
#先定位到列表偏移量为1的元素，即第二个字典，再取出字典里键为'小强'对应的值，即99。
```

## 循环

### for...in...循环

```python
for i in [0,1,2,3,4,5]:
   print(i)
>>>0
1
2
3
4
5
```

- i即item
- [1,2,3,4,5]即循环的对象，也可以是列表，字典，字符串
- 循环的过程为`遍历`

#### range( )函数

```python
for i in range(6):
    print(i)
>>>0
1
2
3
4
5
```

使用`range(x)`函数，就可以生成一个从`0`到`x-1`的整数序列

使用`range(a,b)` 函数，就可以生成一个从`a`到`b-1`的整数序列

想实现把一段代码固定重复n次时，就可以直接使用`for i in range(n)`

```python
for i in range(3):
    print('重要的事情说三遍')

>>>重要的事情说三遍
重要的事情说三遍
重要的事情说三遍
```

`range(a,b,c)`

- a：计数从a开始。不填时，默认从0开始
- b：计数到b 结束，但不包括b
- c：计数的间隔，不填时默认为1

```python
for i in range(0,10,3):
    print(i)
>>>0
3
6
9
```

### while循环

```python
a = 0
#执行子句的必备条件
while a < 5:
#while子句
    a=a+1
    print(a)
```

### 两种循环的应用场景

for循环和while循环最大的区别在于【循环的工作量是否确定】

for循环的逻辑是把【所有工作做完】才停止。

while循环就像哨卡放行，【满足条件就一直运行】，直到不满足条件就停止循环

所以当【工作量确定】时，就可以让for循环来完成重复性工作。反之，要【工作量不确定】时可以让while循环来工作

## 布尔值

计算机的逻辑判断，只有两种结果，就是`True`（英文意思是“真”）和`False`（英文意思是“假”），没有灰色地带。这个计算真假的过程，叫做【布尔运算】，而`True`和`False`，也就叫做【布尔值】

- 用数据做逻辑判断的过程叫做【布尔运算】
- 【布尔运算】会产生【布尔值】
- 【布尔值】分为True (判断为真)和False (判断为假)
- True和False就像【开关】一样，决定if语句和while循环语句是否运行

布尔运算的三种方式：

- 两个数值作比较

  - 用两个数值做比较的【布尔运算】，主要包含以下情况：

  - |   等于   |  ==  |
    | :------: | :--: |
    |  不等于  |  !=  |
    |   大于   |  >   |
    |   小于   |  <   |
    | 大于等于 |  >=  |
    | 小于等于 |  <=  |

- 直接用数值做运算

  - |      假      |        真        |
    | :----------: | :--------------: |
    |    False     |       True       |
    |      0       | 任意整数及浮点数 |
    | ''(空字符串) |      字符串      |
    |  [](空列表)  |     [1,2,3]      |
    |  {}(空字典)  |    {1:1,2:1}     |
    |     None     |                  |

- 布尔值之间的运算
  - `and`、`or`、`not`、`in`、`not in`五种运算
  - `a==1 and b==1`的意思是【a=1并且b=1】，要两个条件都满足，才能判断为True，而`a==1 or b==1`的意思是【a=1或者b=1】，只要两个条件满足一个，就能判断为True
  - `not`运算。这个运算很简单，表示翻转的意思。`not True`就等于`False`，`not False`就等于`True`。
  - `in`的意思是“判断一个元素是否在一堆数据之中”，`not in`反之。
    - 如果涉及到的数据集合是字典的话，【in】和【not in】就可以用来判断字典中是否存在某个【键】：

### bool( )函数

可以使用`bool()`函数来查看一个数据会被判断为真还是假。这个函数的用法与`type()`函数相似，在`bool()`函数括号中放入我们想要判断真假的数据，然后print出来即可。

```python
print('以下数据判断结果都是【假】：')
print(bool(False))
print(bool(0))
print(bool(''))
print(bool(None))
>>>False

print('以下数据判断结果都是【真】：')
print(bool(True))
print(bool(1))
print(bool('abc'))
>>>True
```

## break语句

break语句,是用来结束循环的

```python
# break语句搭配for循环
for...in...:
    ...
    if ...:
        break

# break语句搭配while循环
while...(条件):
    ...
    if ...:
        break
```

`if...break`的意思是如果满足了某一个条件，就提前结束循环。这个只能在循环内部使用。

## continue语句

continue的意思是“继续”。这个子句也是在循环内部使用的。当某个条件被满足的时候，触发continue语句，将跳过之后的代码，直接回到循环的开始

```python
# continue语句搭配for循环
for...in...:
    ...
    if ...:
        continue
    ...

# continue语句搭配while循环
while...(条件):
    ...
    if ...:
        continue
    ...
```

## pass语句

pass语句意思是“跳过”

```python

if ...:
    ...
else:
    pass
```

## else语句

else不但可以和if配合使用，它还能跟for循环和while循环配合使用

for循环和while循环执行完毕或者中断后，就执行循环后面的else语句

当循环中触发了break语句，就**不会**执行循环后面的else语句

```python
for i in ...:
	...
else:
    ...

while...(条件):
    ...
else:
    ...
```

# 实战思索

完成一个项目的流程：

- 明确项目目标
- 分析过程，拆解项目
- 逐步执行，代码实现
  

瓶颈：

- 知识学完就忘
- 缺乏解题能力

解决途径：

- 知识管理

  - 【掌握】知识和【记住】知识是两个概念：【掌握知识】是知道有这个知识点，并了解它该往哪用，而【记住知识】只是强行记忆知识点，但不一定知道怎么用，用在哪。

  - 在初期，很多知识只需要在使用的时候有个印象，遇到不明确的，就去翻看学习记录，找到知识点的具体用法，再运行代码检验

  - 较为有效的学习方法：【案例笔记法】。它包括了两种类型的笔记：【用法查询笔记】和【深度理解笔记】。
    - 【用法查询笔记】就是记录知识点的基础用法，即学习记录，方便快速查阅，加深对知识的印象
      - 【深度理解笔记】重在“理解”，所以笔记内容主要是记录对知识的理解
      - 【用法查询笔记】解决的是“知识点是什么”的问题，【深度理解笔记】更侧重解决“为什么要用”以及“怎么用这个知识点”的问题。

- 解题思路

  - 分析问题，明确结果
  - 思考需要的知识，或搜索新知识
  - 思考切入点
  - 尝试解决问题的一部分
  - 重复1-4步

# 函数

## 参数

函数后面都跟了个括号

括号里放的东西，也就是需要输入给函数的数据，它在函数中被称作【参数】

【参数】指向的是函数要接收、处理怎样的数据（可以把它理解成自变量）。

比如**len( )**函数会根据括号里放的参数的不同，输出（返回）不同的值。

### 参数类型

- 位置参数

  - 位置参数】当有多个参数的时候，如果不进行其他操作，就会按照顺序和数量传递，这也是最常见的参数类型。

- 默认参数

  - 【默认参数】直接在定义函数的时候给参数赋值
  - 默认参数必须放在位置参数之后
  - 如果一个函数的某个参数值总是固定的，那么设置默认参数就免去了每次都要传递的麻烦。不过默认参数也可以改变参数值

- 不定长参数

  - 格式比较特殊，是一个星号`*`加上参数名，它的返回值也比较特殊

```python
def menu(ap,*barbeque):
    return ap,barbeque
    
order = menu('烤鸡翅','烤茄子','烤玉米')
    
print(order)
print(type(order))
>>>('烤鸡翅', ('烤茄子', '烤玉米'))
<class 'tuple'>
```

- 返回元组类型数据

## 定义和调用函数

### 定义函数

```python
# 定义函数基本语法
# 函数名：1. 名字最好能体现函数的功能，一般用小写字母和单下划线、数字等组合
#       2. 不可与内置函数重名（内置函数不需要定义即可直接使用）

def 函数名(参数):
# 参数：根据函数功能，括号里可以有多个参数，也可以不带参数，命名规则与函数名相同
# 规范：括号是英文括号，后面的冒号不能丢
    函数体
# 函数体：函数的执行过程，体现函数功能的语句，要缩进，一般是四个空格
    return 语句
# return语句：后面可以接多种数据类型，如果函数不需要返回值的话，可以省略
# 没有return语句的函数，Python也会在末尾隐性地加上return None，即返回None值。
# 在函数定义语法中， return语句是函数的最后一行代码，执行到 return 语句便会停止，即： return 语句下方的语句将不再执行。
```

### 调用函数

输入函数名和参数所对应的值，这个过程在函数里叫作参数的传递(pass)。

`name(self)`

### 返回多个值

要返回多个值，只需将返回的值写在return语句后面，用英文逗号隔开即可。

同样会返回元组的数据类型

## 多个函数间的配合

### 变量作用域

当多个函数同时运行时，就涉及函数中一个非常重要的概念 —— 变量作用域。

- 一个在函数内部赋值的变量仅能在该函数内部使用（局部作用域），它们被称作【局部变量】
- 在所有函数之外赋值的变量，可以在程序的任何位置使用（全局作用域），它们被称作【全局变量】

“局部变量”和”全局变量“的解决方法：

- 把局部变量都放在函数外，变成全局变量
- 利用global语句将局部变量声明为全局变量

#### 局部变量和全局变量同名处理

- 内部函数，不修改全局变量可以访问全局变量
- 内部函数，修改同名全局变量，则python会认为它是一个局部变量
- 在内部函数修改同名全局变量之前调用变量名称（如print sum），则引发Unbound-LocalError

在程序中设置的 sum 属于全局变量，而在函数中没有 sum 的定义，根据python访问局部变量和全局变量的规则：当搜索一个变量的时候，python先从局部作用域开始搜索，如果在局部作用域没有找到那个变量，那样python就在全局变量中找这个变量，如果找不到抛出异常(NAMEERROR或者Unbound-LocalError，这取决于python版本。)

如果内部函数有引用外部函数的同名变量或者全局变量，并且对这个变量有修改.那么python会认为它是一个局部变量，又因为函数中没有sum的定义和赋值，所以报错。

从下面两个程序看单独的访问或者修改全局变量，并不报错~

访问全局变量:

```python
import sys

sum=5
def add(a=1,b=3):
    print(a,b)
    print(sum)   #仅仅访问 
add(4,8)
print(sum)

>>>4 8
5
5
```

修改同名的全局变量，则认为是一个局部变量:

```python
import sys
sum=5
def add(a=1,b=3):
    print(a,b)
     #内部函数有引用外部函数的同名变量或者全局变量,并且对这个变量有修改.那么python会认为它是一个局部变量
    sum=b+a #在函数内部修改
    print(sum)
add(4,8)

>>>4 8
12
```

下面的程序就会因为"如果内部函数有引用外部函数的同名变量或者全局变量，并且对这个变量有修改。那么 python 会认为它是一个局部变量,又因为函数中没有 sum 的定义和赋值，所以报错：

```python
import sys
sum=5
def add(a=1,b=3):
    print(a,b)
    print(sum)  #内部函数引用同名变量，并且修改这个变量。python会认为它是局部变量。因为在此处print之前，没有定义sum变量，所以会报错（建议与情况一比较，备注：此处只是比上例先print sum）
    sum=b+a
    print(sum)
add(4,8)
print(sum)

>>>
Traceback (most recent call last):
...
...
...
UnboundLocalError: local variable 'sum' referenced before assignment
```

遇到在程序中访问全局变量并且要修改全局变量的值的情况可以使用：**global** 关键字，在函数中声明此变量是全局变量。

```python
import sys

sum=5
print('改变之前：sum=',sum)
def add(a=1,b=3):
    global sum
    print('add 函数中:sum=',sum)
    sum=b+a
    print('函数中改变之后:sum= ',sum)
add(4,8)
print('改变之后 sum=',sum)

>>>
改变之前：sum= 5
add 函数中:sum= 5	
函数中改变之后:sum=  12
改变之后 sum= 12
```

```python
# 对比示范
x = 100
def func():
    print(x)
    x = 1000
    print(x)
func()


sum=5
def add(a=1,b=3):
    print(a,b)
    print(sum)   
add(4,8)
print(sum)

>>>上面会报错
下面输出：4 8
5
5

# 因为上边的函数内的局部变量x与外边的全局变量名称一样，并且修改这个变量。python会认为它是局部变量。因为在此处print之前，没有定义x变量，所以会报错
```



### 函数的嵌套

最简单的例子就是print(len('cool'))，这里就是print( )嵌套了len( )，Python会先执行len( )函数，得到一个返回值，再由print( )打印出来。

嵌套的逻辑：def语句后的代码块只是封装了函数的功能，如果没有被调用，那么def语句后面的代码永远不会被执行。

```python
def 函数a():		#某个功能独立的函数a
	...
def 函数b():		# 某个功能独立的函数b
	...
def 函数c():		#某个功能独立的函数c
	...
...
def 主函数()∶		#将各个功能打包到一起的函数，形成“程序入口”
	函数a()		#调用a函数
	函数b()		#调用b函数
	函数c()		#调用c函数
	...
主函数()
```

# 如何debug

```python
a = input('请输入密码：')
if a == '123456'
    print('通过')

>>># 报错
line 2
    if a == '123456'
                   ^
SyntaxError: invalid syntax
```

报错里通常包含三个关键信息

- `line 2`代表这个bug出现在第2行，所以，我们在Debug的时候，可以优先从第2行开始检查。
- `^`代表bug发生的位置，这里指出的位置是第二行末尾。
- `SyntaxError`指的是语法错误。

## 常用报错类型

| 异常名称                  | 描述                                               |
| :------------------------ | :------------------------------------------------- |
| BaseException             | 所有异常的基类                                     |
| SystemExit                | 解释器请求退出                                     |
| KeyboardInterrupt         | 用户中断执行(通常是输入^C)                         |
| Exception                 | 常规错误的基类                                     |
| StopIteration             | 迭代器没有更多的值                                 |
| GeneratorExit             | 生成器(generator)发生异常来通知退出                |
| StandardError             | 所有的内建标准异常的基类                           |
| ArithmeticError           | 所有数值计算错误的基类                             |
| FloatingPointError        | 浮点计算错误                                       |
| OverflowError             | 数值运算超出最大限制                               |
| ZeroDivisionError         | 除(或取模)零 (所有数据类型)                        |
| AssertionError            | 断言语句失败                                       |
| AttributeError            | 对象没有这个属性                                   |
| EOFError                  | 没有内建输入,到达EOF 标记                          |
| EnvironmentError          | 操作系统错误的基类                                 |
| IOError                   | 输入/输出操作失败                                  |
| OSError                   | 操作系统错误                                       |
| WindowsError              | 系统调用失败                                       |
| ImportError               | 导入模块/对象失败                                  |
| LookupError               | 无效数据查询的基类                                 |
| IndexError                | 序列中没有此索引(index)                            |
| KeyError                  | 映射中没有这个键                                   |
| MemoryError               | 内存溢出错误(对于Python 解释器不是致命的)          |
| NameError                 | 未声明/初始化对象 (没有属性)                       |
| UnboundLocalError         | 访问未初始化的本地变量                             |
| ReferenceError            | 弱引用(Weak reference)试图访问已经垃圾回收了的对象 |
| RuntimeError              | 一般的运行时错误                                   |
| NotImplementedError       | 尚未实现的方法                                     |
| SyntaxError               | Python 语法错误                                    |
| IndentationError          | 缩进错误                                           |
| TabError                  | Tab 和空格混用                                     |
| SystemError               | 一般的解释器系统错误                               |
| TypeError                 | 对类型无效的操作                                   |
| ValueError                | 传入无效的参数                                     |
| UnicodeError              | Unicode 相关的错误                                 |
| UnicodeDecodeError        | Unicode 解码时的错误                               |
| UnicodeEncodeError        | Unicode 编码时错误                                 |
| UnicodeTranslateError     | Unicode 转换时错误                                 |
| Warning                   | 警告的基类                                         |
| DeprecationWarning        | 关于被弃用的特征的警告                             |
| FutureWarning             | 关于构造将来语义会有改变的警告                     |
| OverflowWarning           | 旧的关于自动提升为长整型(long)的警告               |
| PendingDeprecationWarning | 关于特性将会被废弃的警告                           |
| RuntimeWarning            | 可疑的运行时行为(runtime behavior)的警告           |
| SyntaxWarning             | 可疑的语法的警告                                   |
| UserWarning               | 用户代码生成的警告                                 |

## 自检清单

- 漏了末尾的冒号，如if语句、循环语句、定义函数
- 缩进错误，该缩进的时候没缩进，不该缩进的时候缩进了
- 把英文符号写成中文符号，如（）、：。。
- 字符串拼接的时候，把字符串和数字拼在一起
- 没有定义变量
- '=='和’=’混用

## 解决思路不清的两个工具

- print( )函数
- 用“#”暂时注释部分代码
  - 多行注释有两种快捷操作：1、在需要注释的多行代码块前后加一组三引号''' 2、选中代码后使用快捷键操作：Windows快捷键是`ctrl+/`，Mac为`cmd+/`，适用于本地编辑器）

## 异常处理机制

为了不让一些无关痛痒的小错影响程序的后续执行，Python提供了一种异常处理的机制，可以在异常出现时即时捕获，然后内部消化掉，让程序继续运行。

这就是`try…except…`语句，具体用法如下：

```python
try:
    fh = open("testfile", "w")
    fh.write("这是一个测试文件，用于测试异常!!")
except IOError:
    print("Error: 没有找到文件或读取文件失败")
else:
    print("内容写入文件成功")
    fh.close()
```

try下面可以包含多个except，针对不同的报错，类似多个 elif

如果在try子句执行时没有发生异常，python将执行else语句后的语句（如果有else的话），然后控制流通过整个try语句。

```python
# 将两个（或多个）异常放在一起，只要触发其中一个，就执行所包含的代码。
except(ZeroDivisionError,ValueError):
	print('你的输入有误，请重新输入！')
    
# 常规错误的基类，假设不想提供很精细的提示，可以用这个语句响应常规错误。
except Exception:
	print('你的输入有误，请重新输入！')
```

# 类与对象

## 面向对象编程

与面向对象编程(Object Oriented Programming)相对应的是**面向过程编程**

面向过程编程：首先分析出解决问题所需要的步骤（即“第一步做什么，第二步做什么，第三步做什么”），然后用函数实现各个步骤，再依次调用。

而面向对象编程，会将程序看作是一组对象的集合

用这种思维设计代码时，考虑的不是程序具体的执行过程（即先做什么后做什么），而是考虑先创建某个类，在类中设定好属性和方法，即是什么，和能做什么

接着，再以类为模版创建一个实例对象，用这个实例去调用类中定义好的属性和方法即可。

## 类

其实从开始就在接触类（class），比如整数、字符串、浮点数等，不同的数据类型就属于不同的类。

类之所以为类是因为每一个类之下都包含无数相似的不同个例。你我他，都属于人类。

编程世界中，每个类也会有众多实际的个例。比如数字1和2，都属于整数类；'第一个栗子'和'第二个栗子'，都属于字符串类。在Python的术语里，把类的个例就叫做**实例** (instance)，可理解为“实际的例子”。

Python中的对象等于类和实例的集合，即类可以看作是对象，实例也可以看作是对象

“电脑很强大”，“我的电脑卡了”。前者说的是电脑类（类对象），后者说的是我的电脑（实例对象）。

**万事万物，皆为对象**

### 类的创建和调用

类有两种特性

- 第一种是描述事物是怎样的，有什么特征，比如黑眼睛、黄皮肤。
- 第二种是描述事物能做什么，有哪些行为和作用，比如能用筷子吃饭、会讲汉语。

第一种叫作属性（attribute），第二种叫作方法（method）

例如列表的属性有：外层有中括号，元素之间用英文逗号隔开，方法有：都可以做增删改操作（如 append、del等）

**类的创建和调用**

- 类的创建:class语句

- 类的属性创建:赋值语句

- 实例方法的创建:def method1(self):

- 类的实例化:实例名=类名( )  

- 调用类的属性:`实例名.属性`调用类的方法:`实例名.方法()`

#### 类的创建

格式：

```python
class Computer:						# 类的创建：class 类名+冒号，后面的语句要缩进

    screen = True					# 类的属性的创建：通过赋值语句

    def start(self):				# 实例方法的创建：def + 方法名(self)
        print('电脑正在开机中……')		# 执行过程

# 在类中赋值的变量叫作属性，类中定义的函数叫作方法（以此和普通函数区分)
# 实例方法是指类中参数带self 的函数，是类方法的一种形式，也是最常用的用法
# 类名的首字母要大写
```

##### 创建类的两个关键点

###### 特殊参数：self

self会接收实例化过程中传入的数据，当实例对象创建后，实例便会代替 self，即self 是所有实例的替身

可见，`self`的作用相当于先给实例占了个位置，等到实例创建好就“功成身退，退位让贤”。

同理，如果想在类的方法内部调用其他方法时，我们也需要用到`self`来代表实例。

- 只要在类中用`def`创建方法时，就必须把**第一个参数**位置留给 self，并在调用方法时忽略它（不用给self传参）。
- 当在类的方法**内部**想调用类属性或其他方法时，就要采用`self.属性名`或`self.方法名`的格式。
- 这个特殊参数的名字可以被修改，但是作用不会改变。但是依旧建议使用 self作为特殊参数的名字，使用一个标准的名称有很多优点，比如其他程序员可以迅速识别它，有些IDE（集成开发环境）也可以迅速识别出来它的用处。

###### 特殊方法：初始化方法

定义初始化方法的格式是`def __init__(self)`，是由init加左右两边的【双】下划线组成（ initialize “初始化”的缩写）

初始化方法的作用在于：当每个实例对象创建时，该方法内的代码无须调用就会自动运行。

利用这个特性，在编写习惯上，会在初始化方法内部完成类属性的创建，为类属性设置初始值，这样类中的其他方法就能直接、随时调用

如此一来，类的其他方法就能通过`self.属性名`的形式调用传入的数据了

```python
class Chinese:

    def __init__(self, name, birth, region):
        self.name = name   # self.name = '以西' 
        self.birth = birth  # self.birth = 'NewYork'
        self.region = region  # self.region = '洛阳'

    def born(self):
        print(self.name + '出生在' + self.birth)

    def live(self):
        print(self.name + '居住在' + self.region)    

person = Chinese('以西','NewYork','洛阳') # 传入初始化方法的参数
person.born()
person.live()
```

#### 类的调用

格式：

```python
class Computer:
    screen = True

    def start(self):
        print('电脑正在开机中……')

my_computer = Computer()
print(my_computer.screen)
my_computer.start()
```

`my_computer = Computer()`。这个过程叫作：类的实例化，即在某个类下创建一个实例对象

`实例名 = 类名( )`

当实例`my_computer`一被创建出来，就可以调用类中的属性和方法。一句话概括就是：类有的实例都会有调用的语法是`实例名.属性`和`实例名.方法`

### 类的继承

A类属于B类，即A类也拥有了B类的所有属性和方法，即A类继承了B类。

在Python中，习惯表述为：A类是B类的子类，B类是A类的父类（或超类）。

类的继承的语法：` class A(B)`

A为子类，B为父类

`class B:`在运行时相当于`class B(object):`。object，是所有类的父类，将其称为根类

**子类创建的实例同时也属于父类**

**父类创建的实例不属于子类**

#### 多层继承

继承不仅可以发生在两个层级之间（即父类-子类），还可以有父类的父类、父类的父类的父类……

子类创建的实例可调用所有层级父类的属性和方法

多层继承，属于继承的深度拓展

#### 多重继承

一个类，可以同时继承多个类，语法为`class A(B,C,D):`

`class A(B,C,D):`括号里B、C、D的顺序是有讲究的。和子类更相关的父类会放在更左侧

就近原则，A类创建的实例在调用属性和方法时，会先在左侧的父类中找，找不到才会去右侧的父类找

```python
class B:
	...

    def diet(self):
        print('b')

class C:
 	...

    def diet(self):
        print('c')

class A(B,C):
    pass

a = A()
A.diet()

>>>b
```

就近原则中多重继承和多层继承混合使用时，若某父类还有父类的话，就会优先先继续往上找到顶。

```python
class C0:
    name = 'C0'

class C2(C0):
    num = 2

class C1:
    num = 1

class C3:
    name = 'C3'

class C4(C1,C2,C3):
    pass

ins = C4()
print(ins.name)
print(ins.num) 

>>>C0
1	
```

多重继承，属于继承的宽度拓展

#### isinstance( )函数

函数`isinstance()`，可以用来判断某个实例是否属于某个类

具体用法是输入两个参数（第一个是实例，第二个是类或类组成的元组），输出是布尔值（True 或 False）。

```python
print(isinstance(1,int))
# 判断1是否为整数类的实例
print(isinstance(1,str))
# 判断1是否为字符串类的实例
print(isinstance(1,(int,str)))
# 判断实例是否属于元组里几个类中的一个

>>>True
False
True
```

### 类的定制

类的定制的前提是继承

子类可以在继承父类的基础上进行个性化的定制，包括：

#### 创建新属性、新方法

可以直接在子类下新建属性或方法，让子类可以用上父类所没有的属性或方法。这种操作，属于定制中的一种：新增代码。

#### 修改继承到的属性或方法

重写代码，是在子类中，对父类代码的修改

```python
class Chinese:

    def land_area(self,area):
        print('我们居住的地方，陆地面积是%d万平方公里左右。'% area)

class Cantonese(Chinese):
    # 间接对方法进行重写
    def land_area(self, area, rate = 0.0188):
        Chinese.land_area(self, area * rate)
        # 直接继承父类方法，再调整参数。

gonger = Chinese()
yewen = Cantonese()
gonger.land_area(960)
yewen.land_area(960)
```

子类继承并修改父类方法的操作是在`def`语句后接`父类.方法（参数）`

# 中场休息（一）：编写一个图书管理系统

```markdown
需求： 
 - 查询书籍:可以一键查询系统里所有书籍的基本信息和借阅状态
 - 添加书籍:往系统添加书籍时，需要输入书籍的基本信息（书名、作家、推荐语)。
 - 借阅书籍:当书籍的借阅状态是'未借出3的时候，书籍才可出借，借出后状态变成'已借出'
 - 归还书籍:归还成功后书籍的借阅状态会更改成'未借出'，可再次被借阅
```

- 处理对象是每本具体的书，而每本书都有自己的属性信息，所以可以定义一个**Book**类，利用Book类创建一个个书的实例，绑定属性

- 这个管理系统的运行主体，是多个可供选择的功能的叠加，所以可以创建一个系统运行类**BookManager**，将查询书籍、添加书籍等功能封装成类中的方法以供调用

  - 预期效果是当实例化这个系统运行类的时候，会出现一个菜单，能让用户选择不同的功能

  - ```markdown
    1、查询所有书籍
    2、添加书籍
    3、借阅书籍
    4、归还书籍
    5、退出
    请输入数字选择对应的功能:
    ```

  - ```python
    # 初步框架
    class Book:
    	def _init_(self):
    		...
    	#对实例属性进行初始化
    class BookManager:
    	def menu(self):
    		...
    	#显示选择菜单，根据不同的选项调用不同的方法
    	def show_all_book(self):
    		...
    	#显示每本书籍的信息
    	def add_book(self):
    		...
    	#添加书籍
    	def lend_book(self):
    		...
    	#借阅书籍
    	def return_book(self):
    		...
    	#归还书籍
    ```



`__str__(self)`只要在类中定义了`__str__(self)`方法，那么当使用`print`打印实例对象的时候，就会直接打印出在这个方法中`return`的数据

```python
class Book:

    def __init__(self, name, author, comment, state = 0):
        self.name = name
        self.author = author
        self.comment = comment
        self.state = state

    def __str__(self):
        if self.state == 0:
            status = '未借出'
        else:
            status = '已借出'
        return '名称：《%s》 作者：%s 推荐语：%s\n状态：%s ' % (self.name, self.author, self.comment, status)
book1 = Book('像自由一样美丽','林达','你要用光明来定义黑暗，用黑暗来定义光明')
print(book1)
# 直接打印对象即可，不能写成print(book1.__str__())
```

- `menu()`是与用户互动的界面

  - ```python
    1.查询所有书籍
    # 调用方法show_all_book()
    
    2.添加书籍
    # 调用方法add_book()
    
    3.借阅书籍
    # 调用方法lend_book()
    
    4.归还书籍
    # 调用方法return_book()
    
    5.退出系统
    
    请输入数字选择对应的功能:
    ```

  - 这里用多层条件判断语句即可

- `show_all_book()`

  - ```python
    class BookManager:
    
        books = []
    
        def __init__(self):
            book1 = Book('惶然录','费尔南多·佩索阿','一个迷失方向且濒于崩溃的灵魂的自我启示，一首对默默无闻、失败、智慧、困难和沉默的赞美诗。')
            book2 = Book('以箭为翅','简媜','调和空灵文风与禅宗境界，刻画人间之缘起缘灭。像一条柔韧的绳子，情这个字，不知勒痛多少人的心肉。')
            book3 = Book('心是孤独的猎手','卡森·麦卡勒斯','我们渴望倾诉，却从未倾听。女孩、黑人、哑巴、醉鬼、鳏夫的孤独形态各异，却从未退场。',1)
            self.books.append(book1)
            self.books.append(book2)
            self.books.append(book3)
    
        def menu(self):
    		...
    
        def show_all_book(self):
            for book in self.books:
                print(book)
                print('')
    ```

- `add_book()`

  - ```python
    class Book:   
    
        def __init__(self, name, author, comment, state = 0):
            self.name = name
            self.author = author
            self.comment = comment
            self.state = state
    
    class BookManager:
    
        books = [] 
    
        def add_book(self):
            new_name = input('请输入书籍名称：')
            new_author =  input('请输入作者名称：')
            new_comment = input('请输入书籍推荐语：')
            # 获取书籍相应信息，赋值给属性
    
            new_book = Book(new_name, new_author, new_comment)
            # 传入参数，创建Book类实例new_book 
            self.books.append(new_book)
            # 将new_book添加到列表books里
            print('书籍录入成功！\n')
    
    manager = BookManager()
    manager.add_book()
    ```

- `lend_book()`

  - ```python
        def check_book(self,name):
            for book in self.books:
                if book.name == name:
                     return book 
            else:
                return None
    
        def lend_book(self):
            name = input('请输入书籍的名称：')
            res = self.check_book(name)
    
            if res != None:
                if res.state == 1:
                    print('你来晚了一步，这本书已经被借走了噢')
                else:
                    print('借阅成功，借了不看会变胖噢～')
                    res.state = 1
            else:
                print('这本书暂时没有收录在系统里呢')
    ```

  - 将`lend_book()`方法中检测书名的代码抽出来，封装成一个函数。这样就可以在借书和还书的代码里直接调用，不用两处重复写同样的代码

- `return_book`

  - ```python
    def return_book(self):
        name = input('请输入归还书籍的名称：')
        res = self.check_book(name)
        # 调用check_book方法，将返回值赋值给变量res
        if res == None:
        # 如果返回的是空值，即这本书的书名不在系统里
            print('没有这本书噢，你恐怕输错了书名～')
        else:
        # 如果返回的是实例对象
            if res.state == 0:
             # 如果实例属性state等于0，即这本书的借阅状态为'未借出'
                print('这本书没有被借走，在等待有缘人的垂青呢！')
            else:
            # 如果实例属性state等于1，即状态为'已借出'
                print('归还成功！')
                res.state = 0
                # 归还后书籍借阅状态为0，重置为'未借出'
    ```

最后将个部分代码整理到一起

```python
class Book:
 
    def __init__(self, name, author, comment, state = 0):
        self.name = name
        self.author = author
        self.comment = comment
        self.state = state
 
    def __str__(self):
        status = '未借出'
        if self.state == 1:
            status = '已借出'
        return '名称：《%s》 作者：%s 推荐语：%s\n状态：%s ' % (self.name, self.author, self.comment, status)
 
class BookManager:

    books = []
    
    def __init__(self):
        book1 = Book('惶然录','费尔南多·佩索阿','一个迷失方向且濒于崩溃的灵魂的自我启示，一首对默默无闻、失败、智慧、困难和沉默的赞美诗。')
        book2 = Book('以箭为翅','简媜','调和空灵文风与禅宗境界，刻画人间之缘起缘灭。像一条柔韧的绳子，情这个字，不知勒痛多少人的心肉。')
        book3 = Book('心是孤独的猎手','卡森·麦卡勒斯','我们渴望倾诉，却从未倾听。女孩、黑人、哑巴、醉鬼、鳏夫的孤独形态各异，却从未退场。',1)
        self.books.append(book1)
        self.books.append(book2)
        self.books.append(book3)
 
    def menu(self):
        print('欢迎使用流浪图书管理系统，每本沉默的好书都是一座流浪的岛屿，希望你有缘发现并着陆，为精神家园找到一片栖息地。\n')
        while True:
            print('1.查询所有书籍\n2.添加书籍\n3.借阅书籍\n4.归还书籍\n5.退出系统\n')
            choice = int(input('请输入数字选择对应的功能：'))
            if choice == 1:
                self.show_all_book()
            elif choice == 2:
                self.add_book()
            elif choice == 3:
                self.lend_book()
            elif choice == 4:
                self.return_book()
            else:
                print('感谢使用！愿你我成为爱书之人，在茫茫书海里相遇。')
                break
 
    def show_all_book(self):
        print('书籍信息如下：')
        for book in self.books:
            print(book)
            print('')

    def add_book(self):
        new_name = input('请输入书籍名称：')
        new_author =  input('请输入作者名称：')
        new_comment = input('请输入书籍推荐语：')
        new_book = Book(new_name, new_author, new_comment)
        self.books.append(new_book)
        print('书籍录入成功！\n')

    def check_book(self,name):
        for book in self.books:
            if book.name == name:
                 return book 
        else:
            return None

    def lend_book(self):
        name = input('请输入书籍的名称：')
        res = self.check_book(name)

        if res != None:
            if res.state == 1:
                print('你来晚了一步，这本书已经被借走了噢')
            else:
                print('借阅成功，借了不看会变胖噢～')
                res.state = 1
        else:
            print('这本书暂时没有收录在系统里呢')
    
    def return_book(self):
        name = input('请输入归还书籍的名称：')
        res = self.check_book(name)
        if res == None:
            print('没有这本书噢，你恐怕输错了书名～')
        else:
            if res.state == 0:
                print('这本书没有被借走，在等待有缘人的垂青呢！')
            else:
                print('归还成功！')
                res.state = 0
 
manager = BookManager()
manager.menu()
```

# 编码

编码的本质就是让只认识0和1的计算机，能够理解人类使用的语言符号，并且将数据转换为二进制进行存储和传输。

## 二进制

世界上有10种人，懂二进制和不懂二进制的。。。。

```
00000000 - 0
11111111 - 255 （1×2**7 + 1×2**6 + ... + 1×2**1 + 1×2**0)
```

用来存放一位0或1，就是计算机里最小的存储单位，叫做【位】，也叫【比特】（bit）。我们规定8个比特构成一个【字节】（byte），这是计算机里最常用的单位。







































