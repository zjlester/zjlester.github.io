---
title: Win004：免费分区管理工具MiniTool Partition Wizard
url: 268.html
id: 268
categories:
  - 应用软件
date: 2014-11-01 15:28:00
tags:
---

### 软件简介

在Windows 9x（包括XP)时代，PowerQuest的Partition Magic（俗称"PQ Magic"）可称为最常用的分区管理与调整工具，但近日在Windows 7/8系统中却发现PQ Magic无法再实现这一功能。一经搜索，发现另有一款分区管理软件可以在Win7中较好地代替PQ，它的名字叫MiniTool Partition Wizard，官方版本包括家庭版、专业版、服务器版、企业版以及技术人员版，其中家庭版是完全免费的，支持的系统包括32和64位的Windows 2000、XP、vista和Windows 7、8，主要功能包括：调整分区大小， 复制分区， 创建分区， 删除分区， 格式化分区， 分区转换， 探索分区， 隐藏分区， 更改驱动器号， 设置活动分区， 分区恢复，等。

此外，专业版提供了更高级的磁盘分区管理选项，服务器版还支持Windows Server 2003/2008等系统，而企业版则提供了面向企业环境的分区管理方案。对于大多数用户而言，免费的家庭版足够使用了。

### 获取与使用

1.  下载： 首先可以到Mini Tool官方站点下载Partition Wizard，家庭版的下载地址是：http://www.partitionwizard.com/free-partition-manager.html。
2.  执行： 下载所得的可执行文件即可进入程序的安装向导，一路点击“Next”即可。
3.  运行： 启动MiniTool Partition Wizard Home Edition，界面似曾相识，实际上分区管理软件的操作界面均大同小异。 [![Minitools_Partition_Wizard](http://www.ilester.net/wp-content/uploads/2014/11/1347f3d39b58e29aa8ec9a3d.jpg-620x264.png)](http://www.ilester.net/wp-content/uploads/2014/11/1347f3d39b58e29aa8ec9a3d.jpg.png) 上方的磁盘分区图示中可以看到主要的NTFS、FAT、Linux Swap等分区格式可以正常地探知与识别，但是遗憾的是我硬盘上的Linux Ext4分区只是被识别为其它（Other）分区，但我想这对大多数用户来说，不会产生影响。
4.  操作 管理分区时，先在磁盘图示中选择需要调整的分区，然后点击相应的图标（或右键菜单选项）即可，等所有的操作设置完毕，运行“General”/“Apply the Change”或者按CTRL+A即可执行设置策略。

说明：

*   涉及到系统盘的分区，大多需要重启系统，并在加载操作系统前以批处理命令的方式自动执行，不要担心，这些操作都是自动，但一定得有耐心，不要自行强制关机中止。
*   MiniTool还提供了这一软件的可启动光盘和可启动闪盘（U盘）的镜像，你也可以烧制内置这一分区调整工具的光盘或制作U盘，这样对于分区调整应该会更加方便（当然话说回来，既然用到可启动盘，那么Pqmagic甚至一些dos工具也是一样可以实现分区调整功能的）。
    *   启动光盘镜像下载站点：[http://www.partitionwizard.com/partition-wizard-bootable-cd.html](http://www.partitionwizard.com/partition-wizard-bootable-cd.html)。
    *   U盘启动盘制作工具：[http://www.partitionwizard.com/bootable-flash-drive.html](http://www.partitionwizard.com/bootable-flash-drive.html)。