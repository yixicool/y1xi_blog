---
title: Drawing_Style
top: false
top_img: https://pic.imgdb.cn/item/627f95b80947543129036ad0.png
cover: https://pic.imgdb.cn/item/627f95b80947543129036ad0.png
toc: true
mathjax: false
date: 2022-05-14 19:25:16
author: 以西
img:
coverImg:
password:
summary:
categories:
 - 建筑学
 - 软件
tags: 
 - 工具
 - 效率
 - 软件
 - pc
 - 学习指南
 - photoshop
 - illustrator
---
# 平面图

## 平面图绘制准则

- 线条要细

  - 调整好图纸对应的比例后
  - 在右侧栏选择acad.ctb
  - 点击后面的编辑，把所有的打印样式给勾选上后，颜色选为黑色，线宽选择0.0000mm
  - 以媒体框拖进ps
  - 加入白底背景
  - 多复制几层增强线稿效果

- 墙体要明显

- 道路&路径要清晰

- 贴图要符合比例

- 材质要有明暗过度

- 建筑要有阴影、投影（或者轮廓的虚化）

- 材质要叠加纹理（线条、波点、混凝土等）

- 标注要规范  指北针！比例尺！图名信息！房间名称&标高！设计说明！

  

## 水墨风平面图

先拍出水墨底

- 调整笔尖的设置
- 笔尖形状，间距拉开
- 形状动态，大小抖动，角度抖动，
- 散布

然后用滤色将墙体和线稿ctrl + i反黑色为白色

线稿双击进入图层样式，勾选描边，将位置改为居中，大小调整为合适，然后颜色调成白色

将室外的道路勾选出来新建图层给ctrl+ delete填充白色

建筑内部同上操作后，填充图案于道路所区分开来，然后栅格化图层，ctrl + i反转后滤色

周围的环境如水质也是同上操作，主要是几个部分间要有所区分

阴影部分选中蚂蚁线后新建图层给ctrl+ delete填充黑色拉低透明度

添加植物树，将饱和度拉到最低，色阶中使白的部分更白，黑的更黑，调至合适的颜色

如果边界过亮就将图层里的去边工具调小像素

之后给树加投影，双击进入图层样式，勾选最下边的投影，选择正片叠底，调整距离和大小，调整投影方向与建筑的投影方向相一致

树木的摆放采用三角形摆放法,然后先按住alt键，再移动鼠标进行复制移动

摆放好后通过调节不透明度，加蒙版等方式使整体产生变化

最后可以加入相关的轴线或透视的线条或者道路的延伸线来丰富画面

## 线稿风平面图

导入线稿后先加粗墙体

打开模型，选择合适的位置进行剖切，然后选择平行投影，风格选择消隐，顶视图，需要墙的剖面线，所以将边线隐藏，建模设置里将剖面宽度改为1，后导出即可

导入后将墙体内的窗户抠出来后新建个图层置入

之后导入带有颗粒感的混凝土作背景的素材

- 导入为灰色需在图像设置里将模式改为rgb颜色

- 选择魔棒工具容差调到10-20后，将连续取消选择，用魔棒选中黑色的颗粒点，新建图层填充黑色，再次新建图层将背景填充为白色，生成斑点背景（如果密度不够可以多复制一层，ctrl+t水平和垂直各翻转下）
- 之后编辑-定义图案-保存

之后双击进入草地的图层样式，填充好刚刚的图案

在草地的图层中再用套索工具沿着建筑的轮廓进行选择，选择后按住alt键只对当下图层有影响，如果效果不见了则需要将下面对应的图层进行栅格化

给轮廓添加完图案后也需要进行栅格化并进行正片叠底来增强效果，**可多次添加几层来增强效果**

添加树木同样是图案添加然后多复制几层进行水平和垂直反转后栅格化及正片叠底

之后就把剩下的几块室外道路及室内家具等等给填充完成即可

室外道路可以用滤镜-杂色-添加杂色-勾选单色来增强效果

不要忘记加上家具

阴影可以将阴影里添加斜线条做成蚂蚁线的形式

## 写实风平面图

先划分好区块,并用不同的颜色进行区分

打开模型，选择合适的位置进行剖切，然后选择平行投影，风格选择消隐，顶视图，需要墙的剖面线，所以将边线隐藏，建模设置里将剖面宽度改为1，后导出即可剖面线

将划分好的空间选好贴图进行添加蒙版贴图

材质贴图要添加纹理，产生不均质的感觉，从而增加写实效果

- 用减淡工具进行提亮（人群活动频繁的地方一般都是亮的）
- 再用加深工具进行适当调节（角落地方）
- 调节完后用不同材质的纹理之间的相互叠加
  - 先找不同纹理颜色的材质
  - 导入后调节大小
  - 按住alt键对下面的图层进行叠加影响
  - 对其创建蒙版
  - 用画笔工具通过调节不透明度等等对其进行柔滑
  - 将交接边缘的硬边给柔滑
  - 还可以ctrl + u改变饱和度
 - 可将最外边的草地添加落叶的贴图，然后添加蒙版，填充黑色遮罩，后将变角涂白即可

室内外的材质选择要有稍微明显的区别（室内可叠加一些图案，如直线斜线等）

三角形种树法

导出阴影

- 阴影把多余的线都去除后，剖面填充的线改为白色，建模设置里将剖面宽度改为1，导出阴影
- 写实风的阴影尽量不要过于锋利生硬，要柔和一些
- 可以利用vray来调整
  -  先到设置里将材质覆盖打开，颜色为白色，质量调大
  -  输出的尺寸先调为800——450
  -  打开太阳（sunlight），将尺寸倍增改为80（测试为较柔和的阴影即可）
  -  再将渲染输出的高宽比调大（1200）
  -  渲染出导入ps，选择正片叠底，对齐
  -  栅格化阴影后打开色阶，点击右边的吸管，再点白色的地方，将图片变白，再正片叠底

- 同时注意树的阴影同样不能过于实，也要虚一些，阴影的颜色也要一致

之后加入家具及顶视人物

同样沿着建筑周围加如较为细腻的背景后，用橡皮擦去多余的部分来凸显建筑的边界

最后ctrl+shift+alt+e（将可见图层合并到新图层里去，不影响其他原图层，方便修改 ctrl+ e则是合并图层后原图层没有了，不方便修改）打开camera 滤镜按图纸风格来调色就行

# 立面图

先打开su模型，侧边栏选择消隐模式，编辑中将轮廓线勾上，相机的平行投影打开，选择对应得立面，打开太阳投影，调整好角度导出jpg

打开vray，添加材质id，改变渲染尺寸后导出材质通道图（可以将材质覆盖打开，调为白色拉高后再渲染，速度会加快）(将渲染输出长宽比改为匹配视图，或打开安全框再导出上边步骤得jpg将上下两张图给对齐)

将线稿图纸导入ps中，再导入材质通道图，然后魔棒选中有杂线的部分进行新建图层填充白色（或者直接擦掉）

砖墙纹理案例：

先找到砖墙的贴图纹理，通过调色阶增强黑白纹理质感，将其定义为图案，选中材质通道中的墙面部分，然后填充刚刚添加的砖墙图案 ，模式选择正片叠底

之后选中草地部分填充合适的颜色，地面线一定是最深的颜色（用套索工具选中地面部分，填充黑色后，ctrl+ i反向后双击图层，添加内阴影，颜色为黑色，大小距离调合适，等高线选择第一个平直线即可，下边还可以增加斜线条）

选择立面植物，ctrl u将饱和度降低，明度拉高。然后复制多个通过调整透明度及大小来增强质感，尽量要选几种不同形状的树

窗户选择对应的材质通道后，可以添加透明度低的图案以及增加内阴影调整到合适的角度上，模式改为正片叠底，为窗户怎加厚度

加入剪影小人在不同位置

同时如果有前后楼，则后边与前边楼交接的部分在后楼的边角上加入阴影

最后可以给建筑背后添加个背景，用套索工具选出远山的形状或者给天空加上横线条降低透明度后抠出云朵填充白色

标注标高

# 效果图

## 插画风效果图

插画风效果的好坏取决于配色的选取

所以可先找张插画风案例进行模仿

选好角度后，视图 - 动画 - 添加场景

插画风舍弃了原有的贴图材质，只保留了颜色作为代表符号

打开vray，先恢复下默认参数

将图像输出的参数调为6000，然后渲染图层将反射去掉，保留材质id及几何法线

将安全框打开，自定义2：1

得到材质通道图和几何法线图

右侧选择调为消隐模式，编辑里将边线去掉，将轮廓线勾上（或者将边线勾上，轮廓线去掉，或者都选中）（合适为止）

导出轮廓线后打开阴影,调整好角度后导出阴影图

先进入材质通道图里面，选中要重点突出的地方，然后ctrl + J将其但单独复制出来，按住ctrl点击图层来选中刚刚复制的图层，新建新的图层后，用吸管工具将案例中的颜色提取后进行填充,然后给其一个白色的背景

接下来来处理立体关系，打开法线图

同样ctrl加选和上边同样的蚂蚁线，然后ctrl j复制一层，然后ctrl shift u去色，然后ctrl L色阶，将黑色更黑，白的更白，模式选择**正片叠底**

然后将阴影图层导入后，打开正片叠底

然后调色阶调到合适的位置

注意前后建筑的阴影遮挡关系

先用钢笔工具将后边的建筑给勾选出来，选完后右键建立选区，新建空白图层，然后填充颜色标记

将阴影图用魔棒工具选中，吸取案例图中的阴影颜色，适当调节透明度使效果更明显

同时也可以叠加原来渲染的材质，将其正片叠底增加质感

进行到此，图纸大概的色调已经定下

加入线稿，ctrl + i反色，然后魔棒选中黑色部分（将连续选项给去掉），delete后调色阶，使白线更加明显些，然后加一层蒙版，将不想要的地方盖住即可(可以ctrl + j多复制几层)

然后对环境进行处理(天空、雪景、远山等)

以雪景为例

可以在屋檐和地面上用白色画笔画出一点雪的感觉，加入的植物需要调下色阶以适应雪景，然后利用不规则的画笔画出下雪的感觉，记得调节透明度（亦可加入人物小动物等）

## 拼贴风

在做之前需要找张案例图来对比着做

拼贴风讲究叙事感

将vary恢复默认

先选好对应的角度，将vray的安全框调到合适的位置

选好角度后，视图 - 动画 - 添加场景

拼贴风的透视感没必要过强，所以可以按住Z然后调节下视野

然后开始测试渲染，先将渲染输出宽度该为800，将材质通道图和几何法线图等等各种图层都删除掉

第一件事先调光影关系（太阳的强度倍增及尺寸倍增），将画面整体调亮一些

然后加入材质id图以及几何法线图和特殊材质图（AO图）（在右侧的纹理棋盘格里输入污垢纹理，半径改为50，双面勾上）（特殊材质图会得到垂直方法和竖直方法会将其抹黑处理，从而形成侧面的阴影关系）

先选中最外层正面墙面位置，新建图层填充颜色

将所填充的颜色附上材质，然后调颜色到合适的颜色

通过图案叠加的方式来填充（前提是先将材质贴图定义为图案）

逐渐处理侧面的的部分（注意处理的透视）

**正侧面的光影关系注意区分**

其他的部分也是如此处理（注意光影的处理）（近大远小 近实远虚 近亮远暗）

注意颜色的变化，植物得放置要合乎尺度，注重故事的营造

最后新建图层ctrl+shift+alt+e 进入camera raw调色

## 写实风

### 日景

先在模型里找到合适的角度，然后通过调太阳光找到合适的**光影关系**

- 可以通过`太阳北极`插件来设置合适的角度

设置该角度为场景

选择合适的材质拖到su中，然后吸管工具吸取后填充到模型里

首先开始进行测试渲染，将参数都改为默认即可

测试完开始vray渲染

首先将太阳强度倍增提高，使画面亮度增强，尺寸倍增也增强，使阴影更加柔和

点颜色将偏黄的太阳调成偏蓝色，颜色选择过滤

渲染输出调制合适的尺寸

渲染输出框里选择左下角调整面板（或者后期在ps里调）

开始正式出图

现在图层面板里将所有图层删掉，删掉后加入材质id、几何法线、反射

渲染时将互动模式和渐进模式给关掉，长宽比3000

上ps，将几张图都拖进来

先将反射图改为滤色或者颜色减淡，然后给他加个蒙版，将太亮的地方用黑笔刷去

然后对底图进行CR滤镜处理

接下来处理正侧面

在材质id或者几何法线里选中

先选中侧面（暗面），将其亮度降低，部分过暗的地方可以在蒙版里将其削弱些

再选中正面（亮面），将其亮度提升，部分过亮的地方可以加些透明度

加入背景（天空、植物、人物、建筑物等）（溢出来或者被遮挡的地方加上对应的蒙版）（注意光影关系）

最后新建图层ctrl+shift+alt+e 进入camera raw调色

靠感觉来调色，注意光影关系的变化

### 夜景

并非全黑，而是一种明亮的黑，即黑暗中透出一点微亮的灯光光点的氛围感

打开模型，先复原vray的参数，将渲染通道里的几个图层先删去

定角度，然后添加此为场景

先测试渲染

先将太阳的颜色调为深蓝色使画面暗下来（在阴影里移动时间来转走光斑）将强度倍增降低

接下来开始打灯（仰视或者平视将灯光放下边向上打）（地面过白可勾选不可见选项）（将颜色调为暖色如米黄色）（将强度增加使画面增亮）（将灯光排布在建筑合适的位置中）

添加积水的质感，先用油漆桶的吸管吸一下地面，然后对vray材质球进行编辑，反射拉高，菲涅耳去掉，颜色选白色，棋盘格里选喷溅，尺寸稍微拉大，迭代多一些，入口也稍微增加一些，平滑微调（参数按照整体感觉来）

开始正式出图

输出宽度3000，图层里选择材质图层以及几何法线以及反射图层

将几个图层都丢进ps，先将反射通道改为滤色模式（或者颜色减淡），然后将背景置入（天空以及背景），做进一步处理（给前景加上蒙版，可以用草的笔刷给前景刷一些草）

给建筑加cr滤镜，尽量使建筑更清晰些，加入人物，注意光影关系

在法线通道里选中侧边，来到底图将亮度拉高一些（过高的部分用画笔工具给擦去）

先新建空白图层，打开滤镜 - 渲染 - 树里边可以填充植物，ctrl + b 色彩平衡（先将中间调和阴影都偏蓝）ctrl + u调下饱和度使其偏暗些，同是用画笔工具吸取和灯光类似的颜色将植物底部刷的亮一些，新建图层按住alt只对当下图层有影响，将树的上半部分刷暗一些（模式改为柔光或者叠加，透明度降低一些，调一调饱和度及色相）注意透视关系

最后ctrl alt shift e合并图层，进入cr滤镜里调色（可以在建筑部分提亮一些，前景部分稍微压暗）

### 雪景

先选好角度，在vray里将材质的参数先调节完成

导出材质id几何法线反射图，先将反射改为滤色模式，点击底图，CTRL j复制一层进入cr滤镜进行调节（调至明亮通透）

导入雪景的素材，然后用选中外景部分盖上蒙版，在道路与雪景的交界处用白色柔边笔适当擦除，使雪景有一种溢出来的感觉，以及屋檐，道路上池边等地方都要适当加上点雪景，背景可加入些远山及带雪的松树

植物先选一棵植物，双击进入图层，添加白色的内阴影，调节角度及距离，使其产生雪景，然后加入人物（注意人物的影子）（注意窗玻璃的处理）

一定要注意正侧面的处理，使光影效果更加明显，可以在空中点一些小白点，然后滤镜 - 模糊 - 动感模糊产生一些残影，可以适当怎加第二层雪（白点增大一些）然后滤镜 - 模糊 - 动感模糊产生一些残影，在靠近有顶的部分加入一些透明度

最后ctrl alt shift e合并图层，进入cr滤镜里调色（整体调亮，前景色压暗一些，透视原点提亮）
