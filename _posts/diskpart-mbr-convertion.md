---
title: 用Diskpart命令快速将硬盘转换为GPT分区
tags:
  - Windows
url: 1701.html
id: 1701
categories:
  - 教育软件
date: 2017-12-08 14:50:06
---

前段时间电脑上磁盘吃紧，所以紧急购置了两个4T的硬盘，挂上之后在Windows的磁盘管理中初始化时，习惯性地将它创建为了MBR分区，然后问题就出现了——因为MBR最高只能认到2T的空间，因为磁盘是空的，所以打算直接将它转换为GPT。 本来打算用可视化工具的方式来操作，后来发现还是用命令行工具diskpart来操作比较省事。以下是操作方法。 首先在命令提示符中输入diskpart，加载此命令。或者在Cortana、搜索等栏目中直接搜索diskpart命令并用管理员身份运行也是一样的。 然后在diskpart中输入list disk获取当前的磁盘列表，此时会列出当前系统挂载的硬盘（因为那个硬盘其实是挂在另一个电脑上，所以我这里只显示了一个）。再接着用select disk =编号的格式来选择磁盘。 Diskpart界面![](http://upload-images.jianshu.io/upload_images/32597-9d46332dbab50497.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/693) 之后就是关键的一步，先用clean清除当前的分区记录，然后用convert gpt来创建新的分区表。再接着就可以在磁盘管理中去创建新分区了，顺便说一下，移动硬盘之类的我推荐还是创建extFat的格式，这样在不同的系统里都可以直接使用（选择NTFS之类的话，有可能会在Mac等系统中多折腾一番）。