---
title: 'Q&A: 为什么PowerPoint中找不到Camtasia Studio加载项？'
tags:
  - Camtasia
  - 微课
url: 418.html
id: 418
categories:
  - 工作室动态
date: 2015-01-21 20:25:08
---

### 问

浙江交通职业技术学院老师问：为什么我的PowerPoint加载项中找不到Camtasia的图标？

### 答

默认情况下，在安装Camtasia Studio（以下简称CS）时，会默认安装CS的PowerPoint加载项，利用它不仅录制PPT录屏更加方便，而且在录制的视频中，每次幻灯片换页都会加上相应的标记（Mark），所以在后续编辑的过程中也会比较方便定位。 对您提到的未发现加载项的问题，可能存在的原因有：

*   检查一下，你的PPT播放软件是否是PowerPoint？这个回答有点怪，但事实是不少老师确实是将WPS等之类的软件都称作是PowerPoint的。请记住，此加载只针对微软的PowerPoint；
*   是否安装时取消了PowerPoint加载项的选项？完整版本的CS软件安装时，安装向导中会有一个组件选择页面，确保在此页面中已经选择加载项；
*   安装过程中，PowerPoint软件是否没有关闭？如果是这样，建议关闭PowerPoint，重新安装CS，在Win7以上系统中，建议右键，选择“以管理员身份运行”；
*   如果上述操作均无误，请在PowerPoint软件的选项中，找到加载项，看看是否有启用Camtasia Studio加载项这一项。正常的应该是如下图： [![Camtasia Studio PowerPoint Addin](http://www.ilester.net/wp-content/uploads/2015/01/PPT_Camtasia_Addin.png)](http://www.ilester.net/wp-content/uploads/2015/01/PPT_Camtasia_Addin.png) 如果此列中找不到Camtasia Studio项目，可以重新安装。或者单击下方的“转到”，手动添加加载项的文件，以64位操作系统为例，默认是C:\\Program Files (x86)\\TechSmith\\Camtasia Studio 8\\Win64\\CamtasiaOfficeAddin.dll。

假设，尝试上述所有的办法都无法找回，那也别纠结了。用CS的屏幕录制器先录制，再播放PowerPoint并开始授课，后期编辑时去掉头尾就可以了。