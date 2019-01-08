---
title: 替换Google字体地址为WordPress加速
url: 8.html
id: 8
categories:
  - 杂项其它
date: 2014-09-02 16:13:38
tags:
---

因为大家都懂的原因，Google的很多站点都访问不了了。WordPress很多主题由于引用了Google Fonts也因此躺枪，加载速度变慢了。解决方法不外乎两种：一种是去除Google字体的引用，但这样有可能会影响页面显示效果，另一种方法就是将这些字体保存下来放到可以访问的地方来引用。

不过现在网上也有一些站点提供了公共的引用地址，比如这个“[360网站卫士常用前端公共库](http://libs.useso.com/)”，我觉得这挺好的。在WordPress中主要是修改以下文件：

*   Wordpress_Path/wp-includes/script-loader.php,查找：“ajax.googleapi.com”，替换为 “ajax.useso.com”
*   相应主题下的functions.php，查找“fonts.googleapi.com”，替换为“fonts.useso.com”

2014.9.7补充

有网友反映，上述修改后前台页面确实加载速度快了，但是在注册页面还是一样慢。所以查阅了[资料](http://www.wpdaxue.com/dw-replace-open-sans.html)，在主题的functions中添加以下函数解决：

function wpdx\_replace\_open_sans() {
  wp\_deregister\_style('open-sans');
  wp\_register\_style( 'open-sans', '//fonts.useso.com/css?family=Open+Sans:300italic,400italic,600italic,300,400,600' );
  if(is\_admin()) wp\_enqueue_style( 'open-sans');
}
add\_action( 'init', 'wpdx\_replace\_open\_sans' );