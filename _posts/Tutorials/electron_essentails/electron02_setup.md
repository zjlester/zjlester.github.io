---
title: Electron教程翻译2：安装
date: 2018-12-15 14:07:51
tags:
    -Electron
categories: 
    - 电子教程
---

要使用Electron，你首先需要安装Node和npm（Node的包管理器），如果你还没有安装，可以查阅《Node安装》一文（https://www.tutorialspoint.com/nodejs/nodejs_environment_setup.htm ）然后将其安装在你的本地系统上。安装之后可以在终端中运行下列命令来检查node和npm是否已经成功安装。

```
node --version
npm --version
```
正常情况下，上述命令应该会产生如下的输出：
```
v6.9.1
3.10.8
```
<!--More-->
无论何时，要使用npm创建项目，我们都需要配置一个package.json文件，这个文件包含了关于项目的详细信息。npm可以帮我们更轻松地创建这一文件，我们先来设置一下我们的项目：

1. 启动终端或命令提示符，创建一个名为hello-world的新文件夹，然后使用cd命令进行此项目文件夹；
2. 现在使用以下的指令来创建package.json文件；
    ```npm init```
3. 此时它会询问以下的信息：
![Hexo ini](http://img.zjer.cn/uploads1/editor/2018/12/10/15444463913454.jpg)

在这里只需要一路单击回车，但在“author name”项中输入你的姓名。
创建一个新的文件夹并用cd命令进入，现在用以下的命令来安装Electron全局环境：
```
$ npm install -g electron-prebuilt
```
一旦它运行完毕，你可以用以下命令来检查Electron是否已经成功安装：
```
$ electron --version
```
你应该会得到形如下文的输出 ：
```
v1.4.13
```
现在你已经安装好了Electron，接下去我们可以用它来创建第一个项目了。
原文：https://www.tutorialspoint.com/electron/electron_installation.htm