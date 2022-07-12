---
title: win10の驯服养成企划
top: false
top_img: https://pic.imgdb.cn/item/627233520947543129eaacca.png
cover: https://pic.imgdb.cn/item/627233520947543129eaacca.png
toc: true
mathjax: false
date: 2022-02-15 11:26:54
author: 以西
img:
coverImg:
password:
summary:
categories:
 - 工具
 - pc
tags: 
 - Win10
 - pc
 - 效率
---

随着PC市场不断发展，Win10系统变得更加普及。从第一版Win10发布至今，已然将近7年时间，尽管期间微软官方一直在修改，但实际使用过程中仍存在不少令人恼火的bug

所以为了更高效的~~**摸鱼**~~使用win10，我们就需要一些特殊手段对win10进行驯化

###### 手段包含但不限于系统的优化，软件的选择，外观的美化等等

ps：文中所推荐的软件及应用均不包含下载链接，所用图片侵删

---

# win10系统的安装

## 安装前的准备

- 准备空U盘以及一台可以正常使用的电脑（U盘里的文件自己备份好，要格式化U盘的）
- 用U盘制作WIN10启动盘
  - win10系统镜像的下载
    - 微软官网下载地址：https://www.microsoft.com/zh-cn/software-download/windows10
    - MSDN, 我告诉你 https://msdn.itellyou.cn/
    - 【推荐】吻妻官网 https://www.newxitong.com/
    - 宋永志博客 - 有态度的封装爱好者 http://www.songyongzhi.com/
  - 接着将U盘插入电脑，双击运行刚刚下载的软件。
    - 点击`接受`
    - 选择`为另一台电脑创建安装介质`，然后下一步
    - 选择`U盘`，下一步
    - 选择自己的U盘的路径，下一步
    - 等待系统下载安装完成。
    - 现在点击完成，然后拔出U盘就行。

## 安装时注意事项

### 系统的安装

- 将要安装或重装系统的电脑关机
- 向要安装/重装系统的电脑插入刚刚制作好的U盘
- 进入BIOS设置启动项，或通过快捷键设置启动项
  - **通过快捷键设置启动项的方法：**按下电源键然后不断按快捷键（各品牌启动项设置快捷键：https://wenku.baidu.com/view/362b9e26312b3169a551a472.html）直到出现选择界面，然后通过上下键选择自己的U盘按回车就行。
  - **通过BIOS设置：**按下电源键然后不断按`DEL`或`ESC`键（一般都是这两个键之一），直到出现BIOS界面，国产的一般有中文，设置方法都差不多，实在不会百度搜：自己的主板/电脑型号启动项设置方法。BIOS中通过方向键切换选项，回车键确认。
- 切换到`Boot`选项卡，中文应该是`启动项`，或类似的。
- 找到`Boot Option`将第一个选项设置为你的U盘，中文应该是这些关键词：`设备启动顺序`、`第一启动项`之类的。
- 找到`Boot Option`将第一个选项设置为你的U盘，中文应该是这些关键词：`设备启动顺序`、`第一启动项`之类的。
- 然后电脑会自动重启进安装程序，点击下一步。
- 点击现在安装。
- 点击下面的`我没有产品密钥`
- 点击下面对应的版本
- 点击`自定义：仅安装Windows`
- 选择要安装系统的分区，如果`显示无法在驱动器分区上安装Windows`就将所有分区`删除`，然后点`新建`重新分区，也可以直接点下一步。
- 接着等待安装完成就会自动重启进系统，然后拔出U盘就行。
- 接着按照引导设置系统即可。

### 系统的激活

- HEU_KMS_Activato
- Qwins一键激活

### 驱动的安装

- 驱动人生，驱动精灵，但没有开通会员下载驱动速度极慢
- 360驱动大师 v2.0.0.1670 纯净绿色单文件版

### 系统的优化

- 先卸载McAfee迈克菲全方位实时保护！！！
- win10自带的defender足够抵御外敌
- 利用 Dism++进行系统优化
- 不放心可以安装火绒 https://www.huorong.cn/
- 管理软件的开机自启动
  - 同时按住 Ctrl+Shift+Esc （都在你键盘左侧）调出任务管理器，左键单击『启动』，在你需要禁止的项目上右键调出菜单即可禁用该自启动项目。
  - 或者利用火绒的启动项的安全工具
- Win10 自带的七大类别文件夹默认是在 C 盘的，如果你 C 盘内存小的话，建议修改下：在要修改的文件夹上依次点击“右键”-“属性”-“位置”-“移动”

# win10效率软件的替换

**工具最终还是为人服务的**。不要本末倒置，沉迷于工具本身。

**利用工具优化自身的工作流才是我们的最终目的**。

同时也特别强调

- 电脑软件请尽量**去官网**或者 GitHub下载，小心各种p2p下载站
- 请谨慎选择国产软件安装
- 国产软件请**不要点击**『快速安装』、『极速安装』这类选项
- 电脑软件利用软件自身的更新功能就可以了，**无需使用**软件管家这类产品进行更新管理
- 小众软件尽量选择绿色版

## Clover | QTTabBar - 文件管理器标签

Clover主要是可以让文件管理器拥有多个标签页和目录，简化了文件管理。

QTTabBar也能实现多标签页管理，甚至某些功能更强大，但是缺少 Clover 这样一步到位的目录栏。结合自身需求选择就好。

这里特别提醒，[Clover 官网](http://cn.ejie.me/)新版本已经有很多弹窗和推广内容，非常不建议安装。低版本也会要求强制升级。建议禁止 Clover 联网并且禁止其启动自动更新服务。

## Flux - 护眼

Flux 是一款根据时间、位置、使用模式**自动调节屏幕色温、亮度**的一款护眼应用

有[安装包](https://justgetflux.com/)，也可以从 [Microsoft Store 里面安装](https://www.microsoft.com/zh-cn/p/flux/9n9kdphv91jt#activetab=pivot:overviewtab)

## Ditto Clipboard - 剪贴板管理

一款剪贴板历史管理应用，凡是你复制过的东西，都会在 Ditto 里面留下记录，日后你可以直接从 Ditto 里面粘贴。

配合快捷键 Ctrl+`(调出历史)、键盘上下键还有回车使用更为高效。

同样有[安装包](https://ditto-cp.sourceforge.io/)也有 [UWP 版](https://www.microsoft.com/zh-cn/p/ditto-clipboard/9nblggh3zbjq)

## Snipaste - 截图

Snipaste 操作简单，功能强大。

- F1 即可截图，F3 可贴图与屏幕
- 截图时可直接取色、定位像素点，并且有实用的参考线。
- 截完图可以直接在图像上进行加文字/形状、涂改、马赛克等常用操作
- 回放截图记录
- 像素级控制截取区域

更多高效实用的功能可以参考[官方文档](https://docs.snipaste.com/zh-cn/getting-started)了解

同样也有[安装包](https://zh.snipaste.com/)和 [UWP 版本](https://www.microsoft.com/zh-cn/p/snipaste/9p1wxpkb68kx)，功能上并无区别。

## [EarTrumpet](https://www.microsoft.com/zh-cn/p/eartrumpet/9nblggh516xp) - 音量输出管理

一款小工具，可以单独控制不同软件的输出音量。可以避免出现某一级别系统音量对于 A 软件过低，却对 B 软件过高的情况。

UWP：[EarTrumpet](https://www.microsoft.com/zh-cn/p/eartrumpet/9nblggh516xp)

## [Windows Terminal（preview）](https://www.microsoft.com/zh-cn/p/windows-terminal-preview/9n0dx20hk701) - 代码开发

多标签页/多平台/Emoji 支持..众多实用功能

UWP: [Windows Terminal（preview）](https://www.microsoft.com/zh-cn/p/windows-terminal-preview/9n0dx20hk701) 

## [Captura - 录屏/录音](https://mathewsachin.github.io/Captura/download/)

不到 10M 的开源免费小工具，但是录屏/录音功能非常强大。

- 全屏/区域/窗口/录屏
- 选择音量输入方式
- 可以录制 Gif、截图..

绿色便携版：[Captura - 录屏/录音](https://mathewsachin.github.io/Captura/download/)

## [菲菲更名宝贝 - 批量命名/文件批量处理](http://www.ffhome.com/works/1406.html)

虽然界面上没有那么美观，但是功能上确实没得说..对文件的批量化处理需求基本都可以满足。

绿色便携版：[菲菲更名宝贝 - 批量命名/文件批量处理](http://www.ffhome.com/works/1406.html)

## [Ifranview - 图片浏览](https://www.irfanview.com/)

主力图片浏览器，日常需求基本都能直接满足。可用于替代 Win10 自带的『照片』

- 体积小、运行快、功能强、非商用免费
- 支持众多图像、视频、音频格式、可幻灯片显示
- 批量转换格式/重命名、无损压缩、加文字、调整色彩
- 支持诸多快捷键
- 大量插件可结合自身需求安装

官网：[Ifranview - 图片浏览](https://www.irfanview.com/)

## [Notepad++ - 轻量级代码/记事本](https://notepad-plus-plus.org/)

替代 Win10 自带记事本的最佳选择

- 开源、小巧、免费的代码编辑器，运行便携，体积小、资源占用小
- 支持众多程序语言，比如C++、C#、Java等主流程序语言；
- 支持HTML、XML、ASP，Perl、Python、JS等网页脚本语言。
- 支持语法高亮，语法折叠，宏等编辑器常用功能..

官网：[Notepad++ - 轻量级代码/记事本](https://notepad-plus-plus.org/)

## [PotPlayer - 视频播放器](https://potplayer.daum.net/)

可能是 Windows 平台最好的本地视频播放器

- 免费绿色无广告
- 启动快、占用资源小、解码能力强大
- 多样的自定义皮肤资源（无边框皮肤非常舒服）
- 功能强大到一屏说不下...
- 有直播源的情况下可以直接看电视/WebDav/FTP/HTTP

地址：[PotPlayer - 视频播放器](https://potplayer.daum.net/)

## [QuickLook - 空格预览文件](https://github.com/QL-Win/QuickLook)

Mac 上一个很方便的功能就是选中文件后按下空格即可快速预览文件内容，查看文件不用打开大型软件等几秒，即点即开，非常方便，而QuickLook 就是在 Windows 上实现这个功能的一款软件。

地址：[QuickLook - 空格预览文件](https://github.com/QL-Win/QuickLook)

## [ScreenToGif - Gif 录制、编辑](https://www.screentogif.com/)

Windows 平台上最强的 Gif 录制、编辑工具。

地址：[ScreenToGif - Gif 录制、编辑](https://www.screentogif.com/)

## [ShareX - 截图](https://getsharex.com/)

ShareX 的优势除了在于本身的截图能力，还在于它强大的工作流支持：OCR、图床、上传到云盘/服务器..

如果你还没有找到一款适合自己工作流的截图软件，不妨试试 ShareX。

地址：[ShareX - 截图](https://getsharex.com/)

## [SumatraPDF - 轻量 PDF 处理](https://www.sumatrapdfreader.org/free-pdf-reader.html)

小巧的 PDF 阅读器，启动快，占用资源少。如果不需要对 PDF 进行编辑等操作，SumatraPDF 已经能够满足基本的阅读需求了。

同时还支持ePub、MOBI、DjVu 等主流书籍格式

地址：[SumatraPDF - 轻量 PDF 处理](https://www.sumatrapdfreader.org/free-pdf-reader.html)

## [SpaceSniffer - 磁盘可视化](http://www.uderzo.it/main_products/space_sniffer/)

C 盘满了不知道怎么清理，Windows 文件夹又不能直接显示大小。这时你可以使用 SpaceSniffer 这款软件直观地查看各文件夹占用的空间的大小，为进一步清理电脑做准备。

地址：[SpaceSniffer - 磁盘可视化](http://www.uderzo.it/main_products/space_sniffer/)

## [QtScrcpy - Windows/Mac 操控 Android 手机](https://gitee.com/Barryda/QtScrcpy)

经常需要在 Android 和电脑之间切换的朋友可以考虑尝试一下，让自己的效率高一点。当然，基础的做个投屏工具也是完全 OK 的，Android 端同样无需安装任何第三方软件。

- 支持 macOS / Windows / Linux 平台
- 可通过 USB 或 TCP/IP 无线连接
- 实时显示/控制 Android 设备屏幕
- 支持屏幕录制
- 最多支持16台设备连接（可选自行编译增加上限）
- 支持拖拽安装 APK / 传输文件
- 支持复制粘贴，可双向同步剪贴板

## [Typora - Markdown 输入](https://typora.io/)

Markdown 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档。

用人话讲，就是你只需要**专注于文字图片本身**，无需考虑复杂排版的一种输入方式。如果不是对排版有特别要求，文字图片输入用 Markdown 非常舒服而高效。

相较于 Mac 下争奇斗艳的 Markdown 输入工具，Windows 上能打的 Markdown 输入工具则少得可怜。而 Typora 可能是 Windows 平台下最好的 Markdown 解决方案。

- 高颜值，舒服的所见即所得体验，也可以自定义主题。
- [图片可搭配 PicGo 自动上传到图床](https://juejin.im/post/5e6b2341518825493e535e5f)
- 丰富的快捷键和功能

本博客内容就是收集总结归档于 Typora 

地址：[Typora](https://typora.io/)

## [7zip - （解）压缩](https://juejin.im/post/5e6b2341518825493e535e5f)

`.7z` 相对于常见的`.zip/.rar`压缩格式，压缩率有所提升。甚至在部分 PPT 上，几十 M 的 PPT 可以压缩到不到 5M 。

常见的 `.7z/.zip/.rar` 7zip都支持压缩/解压缩，当然实际上它还支持更多文件格式。

虽然没有 PeaZip 智能解压/密码管理的功能，但是 7zip 自身集成在右键菜单里还是蛮方便的，完全可以胜任主力压缩工具。

地址：[7zip - （解）压缩](https://juejin.im/post/5e6b2341518825493e535e5f)

## [Unlocker - 系统清理](http://www.emptyloop.com/unlocker/)

功能很纯粹，有的时候想删除一个文件。

弹出**该文件被另一个应用程序使用，无法删除**（然后也不告诉我是谁在占用）。甚至重启之后删除时依旧会有这个提醒出现（经常是某些毒瘤弹窗程序）。

此时 Unlocker 就派上用场了，它可以解除程序对于文件的占用，进而删除文件。即使暂时删不掉，也会把删除的命令写到启动里面，下次开机时没等程序占用就将其删除。

地址：[Unlocker - 系统清理](http://www.emptyloop.com/unlocker/)

## [everything - 快速启动器](https://www.voidtools.com/zh-cn/)

快速搜索定位文件

## [DeskPins - 窗口增强](https://efotinis.neocities.org/deskpins/)

这款小工具只有一个功能——让某个窗口置于最前端显示。

有时进行输入工作时，希望输入的窗口能保持在最前端显示，减少来回切换的不便。

地址：[DeskPins - 窗口增强](https://efotinis.neocities.org/deskpins/)

## [Quicker - 自动化神器](https://www.getquicker.net/)

Quicker 是一个可以帮你把常用的操作抽象出来，让你从重复性劳动里解放的一款效率神器，用了就回不去

地址：[Quicker - 自动化神器](https://www.getquicker.net/)

## [RescueTime - 时间管理](https://www.rescuetime.com/)

Rescue Time 可以帮助你统计各个程序、网页的使用时间，形成报表，直观地显示今天你干了啥。

地址：[RescueTime - 时间管理](https://www.rescuetime.com/)

## [PicGo - 图床](https://molunerfinn.com/PicGo/)

Windows 下写 Markdown 文字部分可以用 Typora 解决，图床部分配合 PicGo 就能实现 Typora 插入图片自动上传到图床，极大地提升了 Markdown 的输入体验。

默认支持微博图床、七牛图床、腾讯云COS、又拍云、GitHub、SM.MS、阿里云OSS、Imgur。方便不同图床的上传需求。2.0版本开始更可以自己开发插件实现其他图床的上传需求。

地址：[PicGo - 图床](https://molunerfinn.com/PicGo/)

## [XnConvert - 图片批量操作](https://www.xnview.com/en/xnconvert/)

XnConvert 能够帮助你批量对图片进行操作，包括但不限于：旋转、转换格式、压缩、裁剪、色彩调整。支持多种图片格式，批量化配置可保存复用。

地址：[XnConvert - 图片批量操作](https://www.xnview.com/en/xnconvert/)

# win10的基本美化

## wallpaper engine

都懂都懂，steam19块，只赚不亏

## [TranslucentTB - 任务栏美化](https://github.com/TranslucentTB/TranslucentTB)

一款让 Win10 任务栏透明/磨砂化的小工具，基本不占用资源。

官网之前是便携版，最新版本是安装文件，同时也提供了 [UWP 版本](https://www.microsoft.com/zh-cn/p/translucenttb/9pf4kz2vn4w9)。建议使用新版本，功能做得更完善一些

## [开始菜单图标修改 - 图标美化](https://github.com/hv0905/SaberColorfulStartmenu/releases)

通过这款软件，你可以修改开始菜单里面的背景颜色、文字颜色和图标。

地址：[开始菜单图标修改 - 图标美化](https://github.com/hv0905/SaberColorfulStartmenu/releases)



# **未完待续，内容正在生产中。。。**

#### 
