---
title: Electron教程翻译7：Node原生库
categories:
  - 电子教程
date: 2019-01-06 10:25:33
tags:
  - Electron
---

在前面的章节中我们使用了node的fs模块，接下去我们继续看一下Electron中可以使用的其它Node模块。

#### OS模块
使用OS模块，我们可以获取关于应用程序运行的操作系统的大量信息，以下是一些在应用创建时常用的方法，这些方法可以方便应用适配运行的操作系统。

序	功能与描述
1. os.userInfo([options])
  os.userInfo() 方法会返回当前活跃用户，使用这些信息可以用来针对用户提供个性化的程序设置，而不需要向用户询问个人信息。
2. os.platform()
  os.platform() 方法返回标识操作系统的字符串，它可以用来针对不同的操作系统定制应用程序。
3. os.homedir()
  os.homedir() 方法以字符串的形式返回当前用户的家（home）目录。一般的应用程序均会将针对当前用户的个性化配置信息存储在家目录中，因此可使用此方法来为我们的应用程序实现同样的功能。
4. os.arch()
  os.arch() 方法以字符串的形式返回当前操作系统CPU架构的信息，这一信息可用于针对不同的架构定制应用程序来适配操作系统。
5. os.EOL
  这一属性定义了当前操作系统特定的行尾标识符，可以让我们不用关心宿主操作系统中行尾表示的差异，方便地来结束段落。

<!--More-->
使用下列的main.js文件和HTML文件，可以将上述信息显示在屏幕上：
```
<html>
   <head>
      <title>OS Module</title>
   </head>
   
   <body>
      <script>
         let os = require('os')
         document.write('User Info: ' + JSON.stringify(os.userInfo()) + '<br>' + 
            'Platform: ' + os.platform() + '<br>' + 
            'User home directory: ' +  os.homedir() + '<br>' + 
            'OS Architecture: ' + os.arch() + '<br>')
      </script>
   </body></html>
```

同样可以用下列命令来运行程序：`$ electron ./main.js`
上述命令显示的输出信息如下：

```
User Info: {"uid":1000,"gid":1000,"username":"ayushgp","homedir":"/home/ayushgp",
   "shell":"/usr/bin/zsh"}
Platform: linux
User home directory: /home/ayushgp
OS Architecture: x64
```

#### Net模块
Net模块顾名思义用来处理应用中与网络相关的工作，使用这一模块，既可以创建server，也可以创建socket连接。通常情况下，在处理网络相关的任务时，我们推荐用npm中的wrapper模块来搭配net模块使用。下表列出了net模块中最常用的方法：

1. net.createServer([options][, connectionListener])
  创建一个新的TCP server，其中的connectionListener参数会自动注册为连接（connection)事件的侦听器。
2. net.createConnection(options[, connectionListener])
  一个工厂（factory）方法，返回一个新的net.Socket以及一个到给定地址和端口的连接。
3. net.Server.listen(port[, host][, backlog][, callback])
  允许指定的地址和主机上接收请求。如果主机地址未指定，则将接收到发送到本机绑定的任意IP V4地址。
4. net.Server.close([callback])
  当所有连接结束时关闭server,同时触发server的close事件。
5. net.Socket.connect(port[, host][, connectListener])
  开启一个指向给定socket的连接。如果指定了主机和端口，则这个socket将以TCP socket的形式开启。

net模块还有一些其它的方法，要了解更多的信息，可以查询：https://www.tutorialspoint.com/nodejs/nodejs_net_module.htm 。

现在，我们用Election来创建一个应用，并使用net模块来创建到服务器的连接，我们需要新建一个新文件server.js：
```
var net = require('net');var server = net.createServer(function(connection) { 
   console.log('Client Connected');
   
   connection.on('end', function() {
      console.log('client disconnected');
   });
   
   connection.write('Hello World!rn');
   connection.pipe(connection);});server.listen(8080, function() { 
   console.log('Server running on http://localhost:8080');});
```

使用同样的main.js文件，将原先的HTML文件内容替换成以下内容：
```
<html>
   <head>
      <title>net Module</title>
   </head>
   
   <body>
      <script>
         var net = require('net');
         var client = net.connect({port: 8080}, function() {
            console.log('Connection established!');  
         });
         
         client.on('data', function(data) {
            document.write(data.toString());
            client.end();
         });
         
         client.on('end', function() { 
            console.log('Disconnected :(');
         });
      </script>
   </body></html>
```

用以下命令来启动服务器环境：`$ node server.js`

用以下命令来启动应用：`$ electron ./main.js`。

上述命令应该会生成以下的输出信息：
![运行效果](http://yun.zjer.cn/uploads2/post/2018/12/11/1544532016706742.jpg)


你会发现我们自动地连接到了服务器，又自动了断开了连接。

此外，使用Electron我们也可以使用其它一些可以直接用于前端开发的node模块，至于需要用到哪些模块，取决于你自己的应用情境。

原文：https://www.tutorialspoint.com/electron/electron_native_node_libraries.htm