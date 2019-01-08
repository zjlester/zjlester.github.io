---
title: Electron教程翻译6：文件处理
categories:
  - 电子教程
date: 2019-01-06 10:09:51
tags:
  - Electron
---
                             
文件处理是桌面应用构建非常重要的一个部分，几乎所有的桌面程序都会涉及文件操作。在这个案例中我们将创建一个表单来接受用户输入信息——姓名和电子邮件地址，表单的内容将会存储到文件中，并显示在列表中作为输出信息。

首先，在main.js文件中输入以下代码来创建一个主进程：
```
const {app, BrowserWindow} = require('electron')const url = require('url')const path = require('path')let winfunction createWindow() {
   win = new BrowserWindow({width: 800, height: 600})
   win.loadURL(url.format ({
      pathname: path.join(__dirname, 'index.html'),
      protocol: 'file:',
      slashes: true
   }))}app.on('ready', createWindow)
```
现在打开index.html，并输入以下代码：
<!--More-->

```
<!DOCTYPE html><html>
   <head>
      <meta charset = "UTF-8">
      <title>File System</title>
      <link rel = "stylesheet" 
         href = "./bower_components/bootstrap/dist/css/bootstrap.min.css" />
      
      <style type = "text/css">
         #contact-list {
            height: 150px;
            overflow-y: auto;
         }
      </style>
   </head>
   
   <body>
      <div class = "container">
         <h1>Enter Names and Email addresses of your contacts</h1>
         <div class = "form-group">
            <label for = "Name">Name</label>
            <input type = "text" name = "Name" value = "" id = "Name" 
               placeholder = "Name" class = "form-control" required>
         </div>
         
         <div class = "form-group">
            <label for = "Email">Email</label>
            <input type = "email" name = "Email" value = "" id = "Email" 
               placeholder = "Email" class = "form-control" required>
         </div>
         
         <div class = "form-group">
            <button class = "btn btn-primary" id = "add-to-list">Add to list!</button>
         </div>
         
         <div id = "contact-list">
            <table class = "table-striped" id = "contact-table">
               <tr>
                  <th class = "col-xs-2">S. No.</th>
                  <th class = "col-xs-4">Name</th>
                  <th class = "col-xs-6">Email</th>
               </tr>
            </table>
         </div>
         
         <script src = "./view.js" ></script>
      </div>
   </body></html>
```

现在我们在view.js文件来处理这一额外的事件。首先创建一个loadAndDisplayContacts()函，用它来读取文件中的初始联系人信息。创建loadAndDisplayContacts()函数之后，我们将创建一个点击事件处理函数到“add to list”按钮，以此作为文件和表格处理的入口。要做的就是在view.js文件中，输入以下代码：
```
let $ = require('jquery')let fs = require('fs')let filename = 'contacts'let sno = 0$('#add-to-list').on('click', () => {
   let name = $('#Name').val()
   let email = $('#Email').val()

   fs.appendFile('contacts', name + ',' + email + 'n')

   addEntry(name, email)})function addEntry(name, email) {
   if(name && email) {
      sno++
      let updateString = '<tr><td>'+ sno + '</td><td>'+ name +'</td><td>' 
         + email +'</td></tr>'
      $('#contact-table').append(updateString)
   }}function loadAndDisplayContacts() {  
   
   //Check if file exists
   if(fs.existsSync(filename)) {
      let data = fs.readFileSync(filename, 'utf8').split('n')
      
      data.forEach((contact, index) => {
         let [ name, email ] = contact.split(',')
         addEntry(name, email)
      })
   
   } else {
      console.log("File Doesn't Exist. Creating new file.")
      fs.writeFile(filename, '', (err) => {
         if(err)
            console.log(err)
      })
   }}loadAndDisplayContacts()
```

现在使用以下命令来运行此程序：`$ electron ./main.js`。

当你添加一些联系人之后，这个程序看上去应该如下图所示：

![运行效果](http://yun.zjer.cn/uploads2/post/2018/12/11/1544501488966291.jpg)

如果要了解更多的fs模块的API调用，可以查询Node文件系统的教程（https://www.tutorialspoint.com/nodejs/nodejs_file_system.htm  ）。现在你可以用Electron来处理文件了，在后面的内容中，我们将会介绍如何用文件对话框（原生）来打开和保存文件。

原文：https://www.tutorialspoint.com/electron/electron_file_handling.htm


                