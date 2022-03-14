---
title: Enscape
top: false
top_img: https://s2.loli.net/2022/03/05/HG31O9FdyPTiS8v.jpg
cover: false
toc: true
mathjax: false
date: 2022-03-05 15:06:38
author: 以西
img:
coverImg:
password:
summary:
categories:
 - 建筑学
 - 软件
tags:
 - 渲染
 - 软件
 - pc
 - 效率
 - 学习指南
---

# 常用操作

w a s d负责窗口视角的移动		e q上升 / 下降

按住shift快速移动		按住ctrl飞速移动

按住鼠标左键视窗转动		按住鼠标右键围绕某一件物体进行转动		鼠标中键平滑移动

按空格切换飞行模式&行走模式（飞行模式可以穿透物体）

m 进入地图点击相关地点即可快速进入		左键双击亦可快速到达

调节时间按住shift + 右键		ctrl + u/i来调节阴影的角度

# 灯光设置

enscape对象选项即enscape的灯光及代理物体面板

球形灯光分为两点，第一点确定对象的xy坐标值，第二点来确定z坐标值

发光强度越高，空间里就越亮，光源半径即光斑的范围

射灯分为四点，前两点确定灯的位置，后两点确定给灯光照射的方向

线性灯，两点来确定大小，灯管的两侧是不发光的，即光照强度最弱

矩形灯，前两点确定灯的位置，后两点确定给灯光照射的方向

圆盘灯更多的使用在照射植物

灯光颜色的修改可以直接通过油漆桶来赋予颜色

# 代理物体

先点击物体，然后右键创建组件，再次右键另存为enscape的外部模型即可生成一种代理模型，提高电脑的运行速度，优化sketchup的模型体积

布置植物或者家时可以使用代理物体

在enscape对象选项里可以选择代理模型来载入之前的物体

# 材质调整

点击enscape材质

选中某个物体，在类型里会有

## 默认

可调节粗糙度、凹凸、颜色等参数

凹凸贴图和法线贴图，法线贴图更加逼近于现实，凹凸贴图和反射贴图都可以选择自己的贴图来增强效果

通用材质一般只需要调节粗糙度和凹凸数量（部分使用反射）

## 草

- 可设置颜色以及草的高度及高度的变化程度
- 纯色贴图的草缺乏变化及光影关系
- **草的贴图一定要选择明暗界限清晰的**
- 将消隐调低，可使上下两颜色所融和

## 水

- 贴图可直接使用su里自带的材质（推荐）
- 也可以选择颜色后将类型改为水（不推荐）
- 水的清晰程度及颜色大部分有周围环境所定
- 透彻的水
  - 类型回到默认
  - 添加水纹的贴图
  - 加上透明度，将不透明度降低，折射率拉低，粗糙度垃低
  - 透明度的着色（根据画面来定）
  - 点击凹凸，可以增加数量来使波纹增大
  - 折射率来控制水面反设的水底更多还是地面更多
  - 调节镜面来调整水的清晰程度

## 树叶&清漆

- 导入的树木可以改类型为树叶增加透光率

- 较为有质感的材质可以调整为清漆改变参数来增加效果

## 玻璃

- 先贴上透明的材质，或者填上颜色降低不透明度
- 镜面拉到最低，不发生反射，只有透明的效果；镜面拉到最高，呈现镜子的效果
- 粗糙度反应材质的光滑程度
- 镜子
  - 将不透明度下的着色调为黑色
  - 镜面拉到最高，粗糙度拉到最低

## 自发光体  

将材质选项里的自发光勾选上，可以更改颜色（本质上是更改发光反射的颜色）

  # 图像设置

轮廓线只能显示边缘线，内部的线无法显示

输出分辨率自定义的场景下勾选`使用视口宽高比`不是enscape的视口，而是su里的视口

# 完整出图流程

测试渲染可以先将渲染质量调低一些

先对各个材质进行调节

点油漆桶里的吸管吸取材质后进入到enscape材质里调节

对于水

- 类型选择默认
- 在su中添加材质
- 降低不透明度，拉高镜面
- 增加凹凸，点击使用反照率（通过调节材质贴图的大小来调节他的波纹的大小 ），同时可以适当降低凹凸的数量然建筑可以在水中产生倒影

对于草地

- 将材质类型选择草
  - 调整高度以及高度变化
  - 更改草地的颜色，可以降低消隐（将明度降低），然后混合黑色
- 如果发现草地材质的变化不够明显，需要换材质
  - 先将草地的材质类型改为默认
  - 进到草地的组中，更换明暗变化大的材质

对于玻璃

- 玻璃本身感觉来良好就不需要进一步调节
- 微调不透明度以及折射率，然后将粗糙度降到最低，镜面按照感觉来

对于木头

- 粗糙度先降低一些，加上凹凸里的反照率（凹凸数量增加，木纹的颗粒感越明显）

然后加入灯光

分别根据空间来添加不同的灯光类型，并且可以用油漆桶来适当修改颜色

更改完毕后先定好角度，然后开始布景

打开资源库（资源库打开后不要关闭）

找几种高度形状大小不同的树木来填充建筑的背景

可以使用插件`组件喷雾`来快速种树

- 在空选的状态下打击插件
- 选择好对应的组件
- 设置好最大以及最小缩放比例
- 设置不允许碰撞
- 设置完点击喷雾即可
- 喷完一组树可以换另一种

种完树在进行进一步调整大小等

进入图像设置里的地平线选择合适的预设做后景（尽量能将背景反射到玻璃上去）

再在前景部分加上些石头或花束等，可以用喷雾喷点草（草的高度及形状要出现变化）

卡的话可以加入代理植物防止su卡顿

调节时间按住shift + 右键		ctrl + u/i来调节阴影的角度		调节出正侧面的关系

打开图像设置，调节太阳的亮度及阴影的清晰度，以及人造光的大小

在图像里调节高光、阴影、饱和度、环境亮度、炫光、柔光等

调节完毕后选择好场景，使用视口高宽比，导出对象id材质id深度通道，调节景深

最后将渲染质量提高后开始渲染

渲染完毕后将图纸丢进ps里开始调整

重点调节建筑的层次感
