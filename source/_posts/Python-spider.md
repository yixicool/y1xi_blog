---
title: python爬虫学习归档
top: false
top_img: https://pic.imgdb.cn/item/627231530947543129e687bb.jpg
cover: https://pic.imgdb.cn/item/627231530947543129e687bb.jpg
toc: true
mathjax: false
date: 2022-03-27 17:27:44
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
 - webspider
---
爬虫，从本质上来说，就是利用程序在网上拿到对自身有价值的数据

以百度为例，在搜索的时候仔细看，会发现每个搜索结果下面都有一个百度快照

点击百度快照，会发现网址的开头有baidu这个词，也就是说这个网页属于百度

这就是因为百度会源源不断地把千千万万个网站爬取下来，存储在自己的服务器上

而在百度搜索的本质就是在它的服务器上搜索信息，搜索到的结果是一些超链接，在超链接跳转之后就可以访问其它网站了

一般来说，传统的拿数据的做法是：通过浏览器上网，手动下载所需要的数据。其实在这背后，浏览器帮助我们做了很多看不见的工作

# 浏览器的工作原理

客户端的请求➡浏览器➡服务器➡返回给浏览器➡客户端

在客户端和浏览器交流的过程中，浏览器的交流对象不只有客户端，还有【服务器】。可以服务器理解为一个超级电脑，它可以计算和存储大量数据，并且在互联网中互相传输数据。

- 首先，在浏览器的地址栏输入网址（也可以叫URL(统一资源定位符)）
- 然后，浏览器向服务器传达了想访问某个网页的需求，这个过程就叫做【请求】
- 紧接着，服务器把目标网站数据发送给浏览器，这个过程叫做【响应】

- 当服务器把数据响应给浏览器之后，浏览器并不会直接把数据丢返还给客户端，因为这些数据是用计算机的语言写的，浏览器还要把这些数据转译成客户端能看得懂的样子，这是浏览器做的另一项工作【解析数据】
- 我们就可以在客户端拿到的数据中，挑选出有用的数据，这是【提取数据】
- 最后把这些有用的数据保存好，这是【存储数据】

即浏览器对服务器的请求，服务器对浏览器的响应

# 爬虫的工作原理

- 首先，爬虫可以模拟浏览器去向服务器发出请求，等待服务器响应，【获取数据】
- 其次，等服务器响应后，爬虫程序还可以代替浏览器帮我们解析数据，【解析数据】
- 接着，爬虫可以根据我们设定的规则批量提取相关数据，而不需要我们去手动提取，【提取数据】
- 最后，爬虫可以批量地把数据存储到本地，【存储数据】

即爬虫程序对服务器的请求，服务器对爬虫程序的响应

# 爬虫的红线

通常情况下，服务器不太会在意小爬虫，但是，服务器会拒绝频率很高的大型爬虫和恶意爬虫，因为这会给服务器带来极大的压力或伤害

不过，服务器在通常情况下，对搜索引擎是欢迎的态度（谷歌和百度的核心技术之一就是爬虫）。当然，这是有条件的，通常这些条件会写在`robots`协议里

`robots`协议是互联网爬虫的一项公认的道德规范，它的全称是“网络爬虫排除标准”（robots exclusion protocol），这个协议用来告诉爬虫，哪些页面是可以抓取的，哪些不可以

截取了一部分淘宝的robots协议 （ http://www.taobao.com/robots.txt）

```
User-agent:  Baiduspider # 百度爬虫
Allow:  /article # 允许访问 article 
Allow:  /oshtml # 允许访问 oshtml 
Allow:  /ershou # 允许访问 ershou 
Allow: /$ # 允许访问根目录，即淘宝主页
Disallow:  /product/ # 禁止访问product文件夹下面的所有文件，但是product文件夹本身允许被访问
Disallow:  / # 禁止访问除 Allow 规定页面之外的其他所有页面

User-Agent:  Googlebot # 谷歌爬虫
Allow:  /article
Allow:  /oshtml
Allow:  /product # 允许访问product文件夹及product文件夹下面的所有文件
Allow:  /spu
Allow:  /dianpu
Allow:  /oversea
Allow:  /list
Allow:  /ershou
Allow: /$
Disallow:  / # 禁止访问除 Allow 规定页面之外的其他所有页面

User-Agent:  * # 其他爬虫
Disallow:  / # 禁止访问所有页面
```

目前通用的规范就是`robots`协议，所以在爬取网络中的信息时，应该有意识地去遵守这个协议。

# 获取数据

## requests模块

`requests`库可以帮我们下载网页源代码、文本、图片，甚至是音频。“下载”本质上是向服务器发送请求并得到响应。

### requests.get( )

`requests.get()`的具体用法如下

```python
# 引入requests库
import requests

# requests.get是在调用requests库中的get()方法，它向服务器发送了一个请求，括号里的参数是你需要的数据所在的网址，然后服务器对请求作出了响应。
# 我们把这个响应返回的结果赋值给变量res
res = requests.get('URL')
```

### Response对象的常用属性

Python是一门面向对象编程的语言，而在爬虫中，理解数据是什么对象是非常、特别、以及极其重要的一件事

因为只有知道了数据是什么对象，才知道对象有什么属性和方法可供后续操作

```python
import requests 

res = requests.get('https://res.pandateacher.com/2018-12-18-10-43-07.png') 
# 打印变量res的数据类型
print(type(res))

>>> <class 'requests.models.Response'>
```

res是一个对象，属于`requests.models.Response`类

|         属性         |              作用              |
| :------------------: | :----------------------------: |
| response.status_code |        检查请求是否成功        |
|   response.content   | 将response对象转换成二进制数据 |
|    response.text     | 将response对象转换成字符串数据 |
|  response.encoding   |     定义response对象的编码     |

#### response.status_code

```python
import requests 

res = requests.get('https://res.pandateacher.com/2018-12-18-10-43-07.png') 
# 打印变量res的响应状态码，以检查请求是否成功
print(res.status_code)
# 它可以用来检查requests请求是否得到了成功的响应，终端结果显示了200，即代表服务器同意了请求，并返回了数据给客户端

>>> 200
```

##### 常用响应状态码解释

| 响应状态码 |     说明     | 举例 |      说明      |
| :--------: | :----------: | :--: | :------------: |
|    1xx     |   请求收到   | 100  |  继续提出请求  |
|    2xx     |   请求成功   | 200  |      成功      |
|    3xx     |    重定向    | 305  | 应使用代理访问 |
|    4xx     |  客户端错误  | 403  |    禁止访问    |
|    5xx     | 服务器端错误 | 503  |  服务器不可用  |

#### response.content

```python
# 引入requests库
import requests

# 发出请求，并把返回的结果放在变量res中
res = requests.get('https://res.pandateacher.com/2018-12-18-10-43-07.png')
# 把Reponse对象的内容以二进制数据的形式返回
pic = res.content
# 新建了一个文件ppt.jpg，这里的文件没加路径，它会被保存在程序运行的当前目录下。
# 图片内容需要以二进制wb读写,学习open()函数已经接触
photo = open('ppt.jpg','wb')
# 获取pic的二进制内容
photo.write(pic) 
# 关闭文件
photo.close()
```

#### response.text

```python
# 引用requests库
import requests

# 下载《三国演义》第一回，得到一个对象，它被命名为res
# https://localprod.pandateacher.com/python-manuscript/crawler-html/sanguo.md《三国演义》内容
res = requests.get('https://localprod.pandateacher.com/python-manuscript/crawler-html/sanguo.md')
# 把Response对象的内容以字符串的形式返回
novel=res.text
print(novel)
```

#### response.encoding

```python
# 引用requests库
import requests

# 下载《三国演义》第一回，我们得到一个对象，它被命名为res
res = requests.get('https://localprod.pandateacher.com/python-manuscript/crawler-html/sanguo.md')
# 定义Response对象的编码为utf-8
res.encoding='utf-8'
# 编解码要共享同一种编码类型
# 总的来说，遇到乱码问题，才考虑用res.encoding
# 把Response对象的内容以字符串的形式返回
novel=res.text
print(novel)
```

# HTML基础

HTML是用来描述网页的一种语言，英文全称是Hyper Text Markup Language，也叫超文本标记语言

**标记语言**就是把**文本**和文本以外的相关**信息**（例如大小，高度，颜色，位置等）组合在一起的语言

用`url`向服务器发出请求的时候，服务返回的是一个带有`HTML`文档的数据包，经过浏览器解析，网页才能在窗口上正常呈现

## HTML的组成

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">    # 网页头具体内容
    </head>
    <body>
        test		# 网页体具体内容
    </body>
</html>
```

- 第一行`<!DOCTYPE html>`是一个全局声明，目的是告诉浏览器，现在处理的这个文档是`HTML`文档
- 声明过后，迎来了HTML代码的主框架，一共有**三组**基本元素，分别是html元素（`<html></html>`），head头元素（`<head></head>`），和body主体元素（`<body></body>`）
- 它们成对出现，都带有尖括号（`<>`&`</>`），分别代表着元素的**起点**和**终点**
- 最外层是`<html>`(**文档起点**)`</html>`（**文档终点**），它的作用是标记文档的起始位置和终止位置，从层级上来看，显然是老大，将`<head></head>`（头部）和`<body></body>`（主题）包裹了起来

## 层级结构

HTML和python一样，**【有缩进】**，这缩进将文档之间的**结构层级**安排地明明白白

譬如，头部元素（`<head></head>`）内，一般会被用来设置网页的编码，添加网页标签的小logo，小标题，外部文件引用（就好像python会用`import`引用别的模块）等。

其次，HTML文档的主体元素（`<body></body>`）负责定义网页窗口内的所有内容

主体元素（`<body></body>`）的内部有div元素（`<div></div>`），div元素（`<div></div>`）内部也有其他元素：图片元素（`<img/>`）和表单元素（`<form></form>`），表单元素（`<form></form>`）也有其他元素，分别是input元素(`<input/>`)和按钮元素(`<button>`)。

除了尖括号的英文外，其中还有许多"赋值语句"（如`width='200px'`）

总结起来就两类东西：**标签**和**属性**

## 标签

**标签**用于标记文本信息，指用尖括号（`<>`和`</>`）括起来的字母和英文，形式有两种：**闭合标签**和**空标签**

- **闭合标签**，它们绝大多数成对出现（有开始标签`<>`,也有结束标签`</>`），如：`<title>和</title>`是标题标签，`<div>和</div>`是块标签，`<form>和</form>`是表单标签。
- **空标签**，即指单标签，只有一个尖括号`<>`（斜杠`/`可省略），标签开始即结束，比如上面的`<img />`是图片标签，`<link />`是链接标签，`<input />`是input标签。
- 同时需要注意的是标签和**元素**的不同，元素其实是包含了**开始标签**与**结束标签**内的所有代码。如html元素是指`<html></html>`包括标签内的所有代码。
- 标签的作用：**给浏览器介绍文本的结构**
- HTML文档含有许多标签，了解几个常用的即可，其余可以翻阅相关的文档（[HTML标签](https://www.w3school.com.cn/tags/index.asp)）

### HTML常用标签

|    标签     |     作用     |       标签       |       作用       |
| :---------: | :----------: | :--------------: | :--------------: |
|   <html>    | 定义html文档 | <h1>、<h2>、<h3> |     定义标题     |
|   <head>    | 定义文档头部 |       <p>        |     定义段落     |
|   <body>    | 定义文档主体 |      <img>       |     定义图片     |
|     <a>     |  定义超链接  |       <ol>       |   定义有序列表   |
|   <audio>   |   定义音频   |       <ul>       |   定义无序列表   |
|  <button>   |   定义按钮   |       <li>       | 定义单个列表条目 |
|    <div>    |  定义块区域  |       <br>       |       分行       |
| <!--    --> |     注释     |                  |                  |

## 属性

用**标签**给文本标记好了之后

想更加详细生动地描述乏味的标签，需要向标签注入点“形容词”，大的还是小的？长的还是高的？红色还是蓝色？

总而言之，**属性**就是去刻画元素的，给`html`的骨架增添点漂亮的“衣服”。

例如**width属性**可以描述图片的宽。**height属性**能控制图片的高度，两相结合，图片的大小即可随意调整

除此之外，还有设置图片链接的**src属性**（`src='xx'`），**alt属性**可编辑当图片无法显示时的替代文本

它们的独有的特征是：都由**赋值语句**构成

`属性名 = "属性值"`

例如name = “value”、style = “color:#20b2aa”

属性让人一目了然，但若一个标签具有多个属性（如大小、颜色、间距、对齐方式），结构就会变得十分冗杂，严重影响阅读体验，可以用通用的`style`属性把所有的样式以**键值对**的形式收集起来，像这样：

`<h1 style="font-weight:bold;text-align:center;letter-spacing:2px;color: #20b2aa;">tset</h1>`

或者：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <style>
            /*h1 {}的内容，是h1元素样式的具体描述*/
            h1 {
                font-weight: bold;/*控制元素字体粗细*/
                text-align: center;/*控制元素对齐方式*/
                letter-spacing: 2px;/*控制文本字符的间距*/
                color: #20b2aa;/*控制元素的颜色*/
            }
        </style>
    </head>
    <body>
        <h1>tset</h1>
    </body>
</html>
```

但这样设置后，h1元素都一个模样，倘若第二个h1元素想换成其他样式就不太方便

为了解决这个问题，`HTML`文档诞生了两个最为特殊的**元素**：`class`和`id`

### 属性：class&id

#### class属性

在HTML文档中，有一个关键词为`class`的属性，`class`属性值相同的元素可复用同一套样式。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
    </head>
    <style>
        /*定义了class属性为style_1的样式*/
        .style_1 {
            width: 100px;
        }
        /*定义了class属性为style_2的样式*/
        .style_2 {
            width: 50px;
        }
    </style>
    <body style="background:#a8c7e2">
        <!-- 第一行图片 -->
        <img class='style_1' src="https://res.pandateacher.com/风变科技logo1.png" >
        <img class='style_2' src="https://res.pandateacher.com/forchange_blue_logo.png" >
        <img class='style_2' src="https://res.pandateacher.com/forchange_black_logo.png" >
        <br>
        <!-- 第二行图片 -->
        <img class='style_1' src="https://res.pandateacher.com/风变科技logo2.png" >
        <img class='style_2' src="https://res.pandateacher.com/panda_black_logo.png" >
        <img class='style_2' src="https://res.pandateacher.com/panda_white_logo.png" >
    </body>
</html>
```

在上面的代码中，创建了两套样式，图片`class`属性值为`style_1`，获得`<style>`标签中的`.style_1`样式，其余`class`属性值为`style_2`的图片抱走`.style_2`的样式

`class`属性的作用是给元素增添类名，多个元素可配置一个类名，类名相同的元素沿袭同一套样式

#### id属性

`id`属性则刚好和`class`属性相反，整个HTML文档，它是独一无二的标识，每个`id`值只能定义一个元素。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <style>
            .book {
                padding: 0px;
                margin: 0px;
            }
            #book_info {
                width: 450px;
                font-size: 13px;
            }
        </style>
    </head>
    <body>
        <h1 align='center' style='color: #20b2aa;'>这个书苑不太冷</h1>
        <h2 style=" font-weight: bold;padding-bottom: 3px;margin-bottom: 16px;border-bottom: 1px solid #ddd;">喜欢的书:</h2>
        <div class="book">
            <img style='float: left;margin-right: 20px;height: 200px;' src="https://res.pandateacher.com/book_qidianyimin.jpg" alt="奇点遗民">
            <div class='book' id="book_info">
                <h4>《奇点遗民》</h4>
                <p style='color:#4c4a4a;'>本书精选收录了刘宇昆的科幻佳作共22篇
                </p>
                <a href="https://wordpress-edu-3autumn.localprod.oc.forchange.cn/">点这里看看</a>
            </div>
        </div>
    </body>
</html>
```

重点关注第18行和第20行代码，显然，两个div元素含有同一个`class`属性值`book`，两个元素都可以使用`.book`的样式，但只有`id="book_info"`的元素可以使用`#book_info`的样式

在`<style>`标签中定义class属性的样式用点`.`，id属性用井号键`#`

`id`就像是学生的学生证号码，每个人都是唯一的，而学生们可以属于同一个班级，班级就像`class`

## HTML文档总结

- 层级结构

  - 由元素组成

  - 缩进代表html的层级

  - ```html
    <html>
        <head></head>
        <body></body>
    </head>
    ```

- 标签
  - 空标签（</>或<>）
  - 闭合标签（<>和</>）

- 属性
  - 标签内的赋值语句(width = '20px')
  - class属性可定义相同类型的元素
  - id是定义元素的唯一标识

- 开始标签和结束标签在内的所有代码

## HTML分析

### 开发者工具

使用谷歌浏览器随机打开一个网页，右键点击【**检查**】选项，或者直接按F12，随后网页弹出一个子窗口，这便是浏览器的开发者工具。

HTML的层级关系可通过其中的小三角形进行查阅，每一个可以展开和合上的小三角形里包含的内容，都是一个层级，就像电脑中一层一层的文件夹

善用定位工具来定位所要查找的网页内容的源代码，可以进行进一步修改

当然，这样的修改只是在**本地的修改**，而服务器上的源文件是修改不了的，可以使用这个方法来调试HTML代码。

### Network

`Network`的功能是：记录在当前页面上发生的所有请求。`Network`记录的是实时网络请求

刷新网络界面后，浏览器会重新访问网络，这样就会有记录。

在最下面会显示：此处共有xx个请求，xxMB项资源，耗时 xx s完成。

这个，正是浏览器每时每刻工作的真相：它总是在向服务器，发起各式各样的请求。当这些请求完成，它们会一起组成`Elements`中的网页源代码

一般来说，都是这种第0个请求先启动了，其他的请求才会关联启动，一点点地将网页给填充起来。做一个比喻，第0个请求就好比是人的骨架，确定了这个网页的结构。在此之后，众多的请求接连涌入

有一些网页，直接把所有的关键信息都放在第0个请求里，尤其是一些比较老（或比较轻量）的网站，直接用`requests`和`BeautifulSoup`就能解决它们。

![1](https://pic.imgdb.cn/item/626e6714239250f7c595fac1.jpg)

第0行的左侧，红色的圆钮是启用`Network`监控（默认高亮打开），灰色圆圈是清空面板上的信息。右侧勾选框`Preserve log`，它的作用是“保留请求日志”。如果不点击这个，当发生页面跳转的时候，记录就会被清空。所以，在爬取一些会发生跳转的网页时，会点亮它

第1行，是对请求进行分类查看

- ALL - 查看全部
- XHR - 一种不借助刷新网页即可传输数据的对象
- Doc - Document，第0个请求一般在这里
- lmg - 仅查看图片
- Media - 仅查看媒体文件
- Other - 其他
- JS和CSS - 前端代码,负责发起请求和页面实现
- Font - 字体

### XHR

在`Network`中，有一类非常重要的请求叫做`XHR`（把鼠标在XHR上悬停，可以看到它的完整表述是XHR and Fetch）

使用浏览器上网的时候，经常有这样的情况：浏览器上方，它所访问的网址没变，但是网页里却新加了内容。

典型代表：购物网站，下滑自动加载出更多商品。在线翻译网站，输入中文实时变英文。

这种技术叫做Ajax技术。应用这种技术，好处是显而易见的——更新网页内容，而不用重新加载整个网页。又省流量又省时间的，何乐而不为，富加载文本数据

这种技术在工作的时候，会创建一个`XHR`（或是Fetch）对象，然后利用`XHR`对象来实现，服务器和浏览器之间传输数据。在这里，`XHR`和`Fetch`并没有本质区别，只是`Fetch`出现得比`XHR`更晚一些，所以对一些开发人员来说会更好用，但作用都是一样的。

## json

`json`是一种数据交换的格式

```python
# 定义一个字典  
a = {'name':'以西'}
# 定义一张列表
b = [1,2,3,4]
# 定义一个json
c = {
        "people": 
        [
            { "name":"A" , "gender":"male"}, 
            { "name":"B" , "gender":"female"}, 
            { "name":"C" , "gender":"male"},
        ]
    }
```

这种特殊的写法决定了，`json`能够有组织地存储信息。

`json`是另一种组织数据的格式，长得和Python中的列表/字典非常相像。它和`html`一样，常用来做网络数据传输。刚刚在`XHR`里查看到的列表/字典，严格来说其实它不是列表/字典，是`json`。如此，`json`数据才能实现，跨平台，跨语言工作。

`json`和`XHR`之间的关系：`XHR`用于传输数据，它能传输很多种数据，`json`是被传输的一种数据格式

### json数据解析

requests.get( )请求得到了`json`数据，可以在`requests`库的官方文档中查看解析方法

Requests 中也有一个内置的 JSON 解码器，来处理 JSON 数据：

```python
import requests

r = requests.get('https://api.github.com/events')
r.json()
>>> [{u'repository': {u'open_issues': 0, u'url': 'https://github.com/...
```

如果 JSON 解码失败， `r.json()` 就会抛出一个异常。例如，响应内容是 401 (Unauthorized)，尝试访问 `r.json()` 将会抛出 `ValueError: No JSON object could be decoded` 异常。

需要注意的是，成功调用 `r.json()` 并**不**意味着响应的成功。有的服务器会在失败的响应中包含一个 JSON 对象（比如 HTTP 500 的错误细节）。这种 JSON 会被解码返回。要检查请求是否成功，请使用 `r.raise_for_status()` 或者检查 `r.status_code` 是否和你的期望相同。

# 解析数据

## BeautifulSoup模块

`requests`库搞定了爬虫第0步——获取数据

解析和提取的部分就交给灵活又方便的**网页解析库**`BeautifulSoup`

`BeautifulSoup`解析数据的用法：

```python
from bs4 import BeautifulSoup
bs对象 = BeautifulSoup(要解析的文本,'解析器')
```

- 第1个参数是要被解析的文本，它必须必须必须是字符串
- 第2个参数用来标识解析器，要用的是一个Python内置库：`html.parser`。（它不是唯一的解析器，却是简单的那个）
- `response.text`和`bs解析`打印出的内容表面上看长得一模一样，但它们属于不同的类：`<class 'str'>` 与`<class 'bs4.BeautifulSoup'>`。前者是字符串，后者是已经被解析过的`BeautifulSoup`对象。之所以打印出来的是一样的文本，是因为BeautifulSoup对象在直接打印它的时候会调用该对象内的**str**方法，所以直接打印 bs 对象显示字符串是**str**的返回结果。

# 提取数据

使用`BeautifulSoup`来提取数据

## find( )与find_all( )

`find()`与`find_all()`是`BeautifulSoup`对象的两个方法，它们可以匹配html的标签和属性，把BeautifulSoup对象里符合要求的数据都提取出来

`find()`**只提取首个满足要求的数据**。`find()`方法将代码从上往下找，找到符合条件的第一个数据，不管后面还有没有满足条件的其他数据，停止寻找，立即返回。

`find_all()`提取出的是**所有满足要求的数据**。代码从上往下找，一直到代码的最后，把所有符合条件的数据揣好，一起打包返回。

|    方法     |          作用          |                 用法                  |                示例                |
| :---------: | :--------------------: | :-----------------------------------: | :--------------------------------: |
|   find( )   | 提取满足要求的首个数据 |   BeautifulSoup对象.find(标签,属性)   |   soup.find('div',class_='book')   |
| find_all( ) | 提取满足要求的所有数据 | BeautifulSoup对象.find_all(标签,属性) | soup.find_all('div',class_='book') |

- 示例中括号里的`class_`有一个下划线，是为了和python语法中的类 `class`区分，避免程序冲突。当然，除了用`class`属性去匹配，还可以使用其它属性，比如`style`属性等
- find( )其次，括号中的参数：标签和属性可以任选其一，也可以两个一起使用，这取决于在网页中提取的内容
- `bs_bookstore.find('ul',class_='nav').find('ul').find_all('li')`提取多个层级 

```python
import requests
from bs4 import BeautifulSoup
url = 'https://localprod.pandateacher.com/python-manuscript/crawler-html/spder-men0.0.html'
res = requests.get (url)
print(res.status_code)
soup = BeautifulSoup(res.text,'html.parser')
# 使用find()方法提取首个<div>元素，并放到变量item里。
item = soup.find('div') 
# 打印item的数据类型
print(type(item))
# 打印item  
print(item)    

>>>200
<class 'bs4.element.Tag'>
# 这是一个Tag类标签对象
<div>大家好，我是一个块</div>
# 运行结果是首个div元素
```

### find_all( )

```python
import requests
from bs4 import BeautifulSoup
url = 'https://localprod.pandateacher.com/python-manuscript/crawler-html/spder-men0.0.html'
res = requests.get (url)
print(res.status_code)
soup = BeautifulSoup(res.text,'html.parser')
# 用find_all()把所有符合要求的数据提取出来，并放在变量items里
items = soup.find_all('div') 
# 打印items的数据类型
print(type(items))
# 打印items
print(items)

>>>200
<class 'bs4.element.ResultSet'>
# 得到的是一个ResultSet类的对象。其实是Tag对象以列表结构储存了起来，可以把它当做列表来处理。
[<div>大家好，我是一个块</div>, <div>我也是一个块</div>, <div>我还是一个块</div>]
# 运行结果是全部的div元素，它们一起组成了一个列表结构
```

## 	Tag对象

`Tag`类对象的常用属性和方法

|         属性/方法          |              作用               |
| :------------------------: | :-----------------------------: |
| Tag.find()和Tag.find_all() |         提取Tag中的Tag          |
|          Tag.text          |         提取Tag中的文字         |
|       Tag['属性名']        | 输入参数后提取Tag中这个属性的值 |

```python
# 调用requests库
import requests 
# 调用BeautifulSoup库
from bs4 import BeautifulSoup 
# 返回一个response对象，赋值给res
res =requests.get('https://localprod.pandateacher.com/python-manuscript/crawler-html/spider-men5.0.html')
# 把res解析为字符串
html=res.text
# 把网页解析为BeautifulSoup对象
soup = BeautifulSoup( html,'html.parser')
# 通过匹配属性class='books'提取出我们想要的元素
items = soup.find_all(class_='books')  
# 遍历列表items
for item in items:       
    # 在列表中的每个元素里，匹配标签<h2>提取出数据               
    kind = item.find('h2')     
    #  在列表中的每个元素里，匹配属性class_='title'提取出数据          
    title = item.find(class_='title')  
    # 在列表中的每个元素里，匹配属性class_='info'提取出数据   
    brief = item.find(class_='info')      
    # 打印书籍的类型、名字、链接和简介的文字
    print(kind.text,'\n',title.text,'\n',title['href'],'\n',brief.text) 
```

用`text`获取Tag类数据的纯文本时，获取的是该标签内的所有纯文本信息，不论是直接在这个标签内，还是在它的子标签内。

需要强调的一点是，`text`可以这样做，但如果是要提取属性的值，是不可以的。父标签只能提取它自身的属性值，不能提取子标签的属性值，不然就是会报错

## 对象的变化过程

操作对象从`URL`链接用`requests.get(url)`到了`Response`对象,又通过`response.text`转化为字符串格式，再通过`BeautiflSoup(字符串，'html.parser')`转换成BS对象

我操作对象是这样的：`Response对象`——`字符串`——`BS对象`。到这里，又产生了两条分岔：一条是`BS对象`——`Tag对象`；另一条是`BS对象`——`列表`——`Tag对象`

# 带参数请求数据

一个url的完整格式

在豆瓣搜索“海边的卡夫卡”，它的网址会是这样：

https://www.douban.com/search?q=%E6%B5%B7%E8%BE%B9%E7%9A%84%E5%8D%A1%E5%A4%AB%E5%8D%A1

在知乎搜索“宇宙大爆炸”，它的网址会是这样：

https://www.zhihu.com/search?type=content&q=%E5%AE%87%E5%AE%99%E5%A4%A7%E7%88%86%E7%82%B8

上面每个`url`都由两部分组成。前半部分大多形如：https://xx.xx.xxx/xxx/xxx

后半部分，多形如：xx=xx&xx=xxx&xxxxx=xx&……

两部分使用`?`来连接

这前半部分是需要请求的地址，它告诉服务器，我想访问这里。而后半部分，就是请求所附带的参数，它会告诉服务器想要**什么样**的数据。

这参数的结构，会和字典很像，有键有值，键值用`=`连接；每组键值之间，使用`&`来连接。

例如豆瓣。请求的地址是https://www.douban.com/search

而`q=%E6%B5%B7%E8%BE%B9%E7%9A%84%E5%8D%A1%E5%A4%AB%E5%8D%A1`则是请求所附带的参数











































































































































































































 
