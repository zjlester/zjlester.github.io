---
title: 'Win008: 虚拟机软件VirtualBox V5.0'
tags:
  - VirtualBox
  - 虚拟机
url: 498.html
id: 498
categories:
  - 应用软件
date: 2015-07-12 23:18:45
---

VirtualBox是一款开源的虚拟机软件，简单地说它可以在物理计算机中（Host）划出一部分的运算资源，虚拟出一台“计算机”（Guest），在Guest计算机上安装上相应的操作系统之后，可以像正常的物理计算机一样使用。比如：你可以在Windows 7环境里安装VirtualBox，然后分配几个Guest计算机器，分别安装上Ubuntu、Windows XP等不同的操作系统，只要你的物理计算机足够强大，分配多个Guest计算机也是完全可以的。 [![tm_Fedora_21_on_OSX](http://www.ilester.net/wp-content/uploads/2015/07/tm_Fedora_21_on_OSX.png)](http://www.ilester.net/wp-content/uploads/2015/07/tm_Fedora_21_on_OSX.png)

### 主要应用领域

*   学习操作系统：比如你想了解一款新的操作系统的使用，比如学习Ubuntu，但又担心在物理机上安装会不慎损坏磁盘分区，丢失文件（很多学Linux系统的同学都经历过这一遭），但如果你用虚拟机，就完全没有这个危险，因为Guest机的搞什么不会影响Host
*   进行网络实验：比如要学习Windows AD的操作配置，我们就需要AD控制器、普通计算机等不同的角色，也就是说你至少需要两台计算机才可以实现，这个时候，如果使用虚拟机的话就可以在一台计算机上实现了。
*   长期使用试用软件：很多共享软件都有试用期限，比如Storyline、Flash Pro等只有一个月的试用期，如果你不想买正版，也不想找破解软件（或者找不到），那么不如创建一个Guest系统，在里面安装试用软件。在试用期结束之后再安装一个Guest系统就搞定了。

当然还有很多其它的应用情境，就取决于你发挥创意了。

### VirtualBox V5.0下载地址

Virtual Box有面向Windows、Mac OS、Linux等常用操作系统的版本，可以针对性地选择，建议去官方网站下载： * VirtualBox 5.0 for Windows hosts ：[http://download.virtualbox.org/virtualbox/5.0.0/VirtualBox-5.0.0-101573-Win.exe](http://download.virtualbox.org/virtualbox/5.0.0/VirtualBox-5.0.0-101573-Win.exe) \* VirtualBox 5.0 for OS X hosts :[http://download.virtualbox.org/virtualbox/5.0.0/VirtualBox-5.0.0-101573-OSX.dmg](http://download.virtualbox.org/virtualbox/5.0.0/VirtualBox-5.0.0-101573-OSX.dmg) \* VirtualBox 5.0 for Linux hosts有针对常见发行版的版本，可以到官网相应选择：[https://www.virtualbox.org/wiki/Linux_Downloads](https://www.virtualbox.org/wiki/Linux_Downloads) \* VirtualBox 5.0 for Solaris hosts :[http://download.virtualbox.org/virtualbox/5.0.0/VirtualBox-5.0.0-101573-SunOS.tar.gz](http://download.virtualbox.org/virtualbox/5.0.0/VirtualBox-5.0.0-101573-SunOS.tar.gz)