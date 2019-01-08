---
title: Electron教程翻译3：Electron如何工作？
date: 2018-12-15 14:08:29
tags:
    -Electron
categories: 
    - 电子教程
---
#### Hexo的应用架构
Electron会查阅package.json文件中指定的主文件（main file）然后执行它。主文件通过一个渲染后的网页文件来创建应用程序，并用可以与你当前操作系统的图形化界面进行互动。
当你运行一个Electron应用时，会创建一个主进程。这一主进程负责与操作系统的原生GUI进行交互，它也负责创建你的应用程序界面。
仅仅启动主进程并不会为用户提供任何程序窗口，窗口需要由主文件中配置的BrowserWindow模块来创建。每个浏览器窗口通过一个渲染进程（renderer process）来运行，渲染进程顾名思义可以渲染HTML文件以及引用的CSS、Javascript、图像等文件，并渲染出应用程序的窗口。
<!--More-->
主进程可以通过Electron的内置模块来访问本地操作系统的GUI，这一桌面系统可以访问所有Nodes模块，例如用文件系统模块来处理文件，request模块来发行HTTP请求，等等。
#### 主进程与渲染进程的区别
主进程通过创建BrowserWindow实例来创建网页，每个BrowserWindow实例在自己的渲染进程中运行网页。当BrowserWindow实例被销毁时，相应的渲染进程也将被终止。
主进程管理所有的网页以及它们对应的渲染进程。每个渲染进程彼此独立，并且只负责运行其内部的网页。

原文：https://www.tutorialspoint.com/electron/how_electron_works.htm
                


            
