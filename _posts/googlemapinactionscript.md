---
title: Flash中利用ActionScript调用Google Map
tags:
  - ActionScript
  - Flash
url: 282.html
id: 282
categories:
  - 程序与设计
date: 2014-11-02 20:09:40
---

看到一个Flash作品中使用Google Maps，也想自己试一下，发现Google Maps 其实也是有For Flash的组件的，所以真正做起来还是比较简单的，记录了一下，主要步骤如下：

### 下载Google Maps API for Flash

1.  地址是：[http://maps.googleapis.com/maps/flash/release/sdk.zip](http://maps.googleapis.com/maps/flash/release/sdk.zip)。下载解压后有两个SWC，名为“map\_1\_20.swc”用于Flash Professional，名为“map\_flex\_1_20.swc”的用于Flex。
2.  载完毕之后将它们复制到Flash的Components目录，为便于管理，还是在下面建一个Google目录比较好。 在Win7中，Components目录位于：C:\\Users\\Administrator\\AppData\\Local\\Adobe\\Flash CS5\\zh_CN\\Configuration\\Components，用户名与语言不同，路径中相应的目录名会有变化；

### 申请Google Maps API Key

1.  填写Google Maps API的申请表单，地址在[http://code.google.com/apis/maps/signup.html](http://code.google.com/apis/maps/signup.html);
2.  在申请KEY时需要填写一个你最终发布SWF文件的域名，这是比较关键的，申请后，记住你的Key代码（下面要用到）

### 创建使用环境

在Flash中新建一个文档，此时在组件框中会看到多出来一个名为Google的文件夹，将里面的Google Maps Library拖至舞台，舞台上会呈现一个蓝框。

### 编写代码

1.  创建一个新层用来添加ActionScript代码，在需要添加代码的地方，插入关键帧，按F9进入脚本编写窗口；
2.  示例参考代码如下： //调用类 import com.google.maps.LatLng; import com.google.maps.Map; import com.google.maps.MapEvent; import com.google.maps.MapType;
    
    var map:Map = new Map(); map.key = “申请到的KEY”; map.sensor = “true”; map.setSize(new Point(stage.stageWidth, stage.stageHeight)); map.addEventListener(MapEvent.MAP\_READY, onMapReady);this.addChild(map); function onMapReady(event:Event):void { map.setCenter(new LatLng(29.137243,119.640899), 14, MapType.NORMAL\_MAP_TYPE);}
    

最终显示的效果如图所示，这里地图中心的坐标（ 29.137243,119.640899）其实是ZNU正校门进去的那个环路的圆心，要获取一个地方的坐标有一个比较简便的方法，就是在Google Maps上选中那个点，选择右键菜单中的“Where is here”。