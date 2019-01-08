---
title: Electron教程翻译5：创建UI
categories:
  - 电子教程
date: 2019-01-06 09:55:41
tags:
  - Eletron
---

在Electron应用中，我们使用HTML、CSS和JS来创建用户界面（User Interface, UI）,因此前端开发的一切技术在这里都可以用上，例如我们可以使用Angular、Backbone、React、Bootstrap和Foundation等来构建应用。

你可以使用Bower来管理这些前端开发依赖库，可以用以下命令来安装bower:`$ npm install -g bower`。
现在就可以用它来安装前端开发需要的JS和CSS框架、库和插件了，例如，如果要安装最新版的bootstrap，只需要用以下命令就可以了：`$ bower install bootstrap`。

这一命令会在bower_components中下载bootstrap，然后你就可以在HTML文件中来引用这个库。现在我们来创建一个使用这些库的简单页面，这里，我们先使用npm来安装jquery库：`$ npm install --save jquery`。

<!--More-->
接下去，我们需要在view.js文件中用required来标记引用，我们已经有了一个形如下文的main.js文件：

```
const {app, BrowserWindow} = require('electron')const url = require('url')const path = require('path')let winfunction createWindow() {
   win = new BrowserWindow({width: 800, height: 600})
   win.loadURL(url.format ({
      pathname: path.join(__dirname, 'index.html'),
      protocol: 'file:',
      slashes: true
   }))}app.on('ready', createWindow)
```
打开index.html，输入以下代码：
```
<!DOCTYPE html><html>
   <head>
      <meta charset = "UTF-8">
      <title>Hello World!</title>
      <link rel = "stylesheet" 
         href = "./bower_components/bootstrap/dist/css/bootstrap.min.css" />
   </head>
   
   <body>
      <div class = "container">
         <h1>This page is using Bootstrap and jQuery!</h1>
         <h3 id = "click-counter"></h3>
         <button class = "btn btn-success" id = "countbtn">Click here</button>
         <script src = "./view.js" ></script>
      </div>
   </body></html>
```
创建一个view.js，在其中创建一个点击按钮计数的逻辑：
```
let $ = require('jquery')  // jQuery now loaded and assigned to $let count = 0$('#click-counter').text(count.toString())$('#countbtn').on('click', () => {
   count ++ 
   $('#click-counter').text(count)})
```
用以下命令来运行程序：`$ electron ./main.js`。

上述命令执行后，应该会产生以下的输出界面：
![运行效果](http://yun.zjer.cn/uploads2/post/2018/12/11/1544500881374699.jpg)


所以你可以像创建网站一样来创建桌面应用，如果你不想让用户界面限制在一个固定的尺寸里，你可以使用响应式设计（responsive design），这样用户使用应用时会更加灵活。

原文：https://www.tutorialspoint.com/electron/electron_building_uis.htm