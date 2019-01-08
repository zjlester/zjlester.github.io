---
title: 移动教育应用系列07：Android无线投影的实现
tags:
  - 移动学习
url: 46.html
id: 46
categories:
  - 移动教学
date: 2014-09-04 14:41:27
---

Android 下能用于无线投影的软硬件方案相比之下会丰富得多，这可能也是这一生态的开放性所致，常见的用于实现无线投影的方案包括 MobiShow、MirrorOP等，这里以MirrorOP为例，当然首先需要确认你的投影终端必须支持DLNA，这通常可以在设备的参数表中查阅，另外如果你的系统中有“多屏显示”、“Allshare”（没错，一看这个就是三星的“等设置的，不用怀疑你的设备已经支持无线投影了。

以下是本人实验的环境：

*   发送端：采用Sumgsung Galaxy Tab 7，安装MirrorOP Sender for Android；
*   接收端：由Windows主机代替，安装MirrorOP Receiver for Windows；如果有条件的话，也可以用一些无线接收器的硬件来实现，在性能上会更有保障。
*   当然我们还要不厌其烦的说明一下，发送端与接收端要连续至同一个无线局域网。
<!--More-->
#### 操作步骤

1.  首先还是老规矩，将发送端与接收端的设备接入同一个WIFI热点；
2.  在 Windows中运行MirroOP Recervier，保持开启状态（此时屏幕上会显示开启状态图，并显示监听的IP地址),然后在Galaxy Tab 7中运行MirrorOP Sender，此时软件会自动搜索局域网中的接收端，并显示，如果未显示，那么尝试一下手工添加IP地址（地址去Windows主机的屏幕上看）。
3.  选中或添加接收机，然后单击“播放“按钮，此时终端的画面将镜像输出至计算机。

（完）