---
title: 这样设置，让Moodle支持移动学习
url: 465.html
id: 465
categories:
  - 杂项其它
date: 2015-07-10 11:37:48
tags:
---

要实现使用手机等移动终端访问Moodle，主要是两种方式：配置移动访问主题或者是使用专用的客户端。 由于Moodle本身就是一个利用浏览器来访问的应用系统，所以采用第一种方法十分简单，利用移动设备上的浏览器访问Moodle的地址就可以了。需要注意的是选用的主题风格对移动设备（通常是小屏幕）是否友好，如果你已经安装了比较符合移动访问的主题，可以采用以下方法进行选择： 选择“站点管理”/“外观”/“主题风格”/“主题选择器”，然后在页面中分别为“Mobile”（手机）和“Tablet”（平板）选择合适的主题。

另外Moodle官方也提供了针对各个主流平台的移动客户端Moodle Mobile，经过简单的配置也可以使用客户端来实现访问Moodle。 [![Moodle Mobile App](http://www.ilester.net/wp-content/uploads/2015/07/mobile-app.png)](http://www.ilester.net/wp-content/uploads/2015/07/mobile-app.png) 客户端访问配置方法如下： 1\. 首先，为了确保访问方便，最好确保Moodle系统可以一个公网可以直接访问的域名或IP地址。如果你没有这类条件，可以采用动态域名技术，这类服务中国内用得比较多的比如“花生壳”：[http://hsk.oray.com/](http://hsk.oray.com/)； 2\. 启动Moodle手机客户端访问，设置页面位于“站点管理”/“插件”/“网络服务”/“手机”，选中其中的“为移动设备启动网络服务”； 3. 安装Moodle Mobile，iOS客户端位于：[https://itunes.apple.com/app/moodle-mobile/id633359593?mt=8](https://itunes.apple.com/app/moodle-mobile/id633359593?mt=8)，Android在Google Play上的地址位于：[https://play.google.com/store/apps/details?id=com.moodle.moodlemobile](https://play.google.com/store/apps/details?id=com.moodle.moodlemobile)，国内的一些应用市场上大多也能找到这一应用，Windows Mobile版本的客户端位于：[http://www.windowsphone.com/en-us/store/app/moodlemobile/d0732b88-3c6d-4127-8f24-3fca2452a4dc](http://www.windowsphone.com/en-us/store/app/moodlemobile/d0732b88-3c6d-4127-8f24-3fca2452a4dc)。 4\. 启动客户端，首次登录会显示添加站点，输入你的Moodle服务器地址。然后会出现登录框，输入你在Moodle系统上的帐户就可以了。