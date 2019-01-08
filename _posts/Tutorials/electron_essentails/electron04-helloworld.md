---
title: Electron教程翻译4： Hello World
categories:
  - 电子教程
date: 2019-01-06 09:34:19
tags:
  - Electron

---

现在我们已经创建了package.json文件，现在就可以用Electron来创建第一个桌面应用程序了。现在创建一个名为main.js的新文件，并输入以下代码：
```
const {app, BrowserWindow} = require('electron') 
const url = require('url') 
const path = require('path')  

let win 

function createWindow() { 
   win = new BrowserWindow({width: 800, height: 600}) 
   win.loadURL(url.format ({ 
      pathname: path.join(__dirname, 'index.html'), 
      protocol: 'file:', 
      slashes: true 
   })) 
}  

app.on('ready', createWindow)
```

<!--More-->

接着创建了一个名为index.html的HTML文件，并输入以下代码：

```
<!DOCTYPE html>
<html>
   <head>
      <meta charset = "UTF-8">
      <title>Hello World!</title>
   </head>
   
   <body>
      <h1>Hello World!</h1>
      We are using node <script>document.write(process.versions.node)</script>,
      Chrome <script>document.write(process.versions.chrome)</script>,
      and Electron <script>document.write(process.versions.electron)</script>.
   </body>
</html>
```

之后就可以用以下代码来运行此程序了：
$ electron ./main.js
运行之后，应该会有一个新窗口打开，界面如下图所示：
![运行结果 ](http://img.zjer.cn/uploads1/editor/2018/12/11/15445001751687.jpg)

说一下运行原理。我们创建了一个主文件和一个HTML文件，主文件使用了两个模块：app和BrowserWindow。app模块用于控制应用程序中事件的生命周期，而BrowserWindow模块用来创建和控制浏览器窗口。
同时我们定义了一个名为createWindow的函数，这一函数用于创建一个BrowserWindow，并通过URL加载一个HTML文件，这一文件用于渲染和展示应用程序的界面。
我们在此HTML文件中使用了Electron的原生对象过程（object process），为一对象拓展了Node.js中的进程对象，继承了所有的t=its函数功能，并增加新的功能。
原文：https://www.tutorialspoint.com/electron/electron_hello_world.htm