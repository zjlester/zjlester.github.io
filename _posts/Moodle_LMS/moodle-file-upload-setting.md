---
title: 'Q&A:Moodle中如何突破文件上传限制？'
tags:
  - Moodle
url: 690.html
id: 690
categories:
  - 工作室动态
date: 2016-04-22 09:42:21
---

### 问：

网友hgtang:"阮老师，在用Moodle时为什么我已经设置服务器的上传限制了（修改PHP.ini文件），但是布置文件提交作业时，上传限制最大只有1M？百度了一晚上，整个人都不好了。。反正没有解决。"

### 答

Moodle是用PHP语言开发的一套开源学习管理系统，所以它的文件上传受到两个条件的限制，一是服务器环境中的文件上传限制，这在PHP.ini中限定；其次是Moodle系统中的环境配置，与文件上传相关的配置分别有全局级（面向整个系统）、课程级（面向所在课程）以及活动级（仅限向涉及文件上传的具体活动，例如作业）的配置。这几者的限制条件是：

> 服务器环境>Moodle全局配置>课程级配置>活动级配置。（也就是说，后面的配置值不应高于前面的配置值）

以下依次说明配置的方法：

#### 1、服务器环境配置：

用文字编辑工具打开PHP.ini，与上传相关的配置选项包括upload\_max\_filesize（默认为2M）、post\_max\_size（默认为8M），注意post\_max\_size的选项值不应该小于upload\_max\_filesize，否则文件上传时递交的post数据和文件大小为0。我通常时将这两者设为一个比较大的值，另外，建议这两个值最好小于PHP环境运行内存上限值，即memory_limit。例如：

> upload\_max\_filesize=200M post\_max\_size=200M

#### 2、全局设置

用管理员帐户登录Moodle系统，在“网站管理”/“安全”/“网站策略”下，找到“上传文件大小的最大值”，选择一个合适的值，这里值的上限是服务器环境中的配置值。 [![Moodle Global Upload Setting](http://www.ilester.net/wp-content/uploads/2016/04/system-1024x179.png)](http://www.ilester.net/wp-content/uploads/2016/04/system.png) 另外，一些涉及文件上传功能的模板往往也有相关的全局设定，这就需要自己分别去查找并更改了，以“作业”为例，可以在“网站管理”/“插件”/“活动模块”/“作业”/“文件提交”（曲径幽深呀）中找到“最大提交大小”这一选项，进行修改就可以了。

#### 3、课程级设置

首先，建议管理员针对服务器的配额，给每个课程设置一个缺省的上传限制，这样以后每次新建的课程都会沿用这一配置，方法是进入“网站管理”/“课程”/“课程缺省设置”，在设置页面中找到“文件上传”，设置“最大上传文件”的值，这一值受到全局设置值的限制。 [![Moodle default course upload setting](http://www.ilester.net/wp-content/uploads/2016/04/Moodle_Default_CourseUpload-300x60.png)](http://www.ilester.net/wp-content/uploads/2016/04/Moodle_Default_CourseUpload.png) 如果你的课程已经创建，那么也可以由具有权限的帐号，在课程设置中来调整这一选项。方法是先进入课程，然后单击“课程管理”/“更改设置”，在设置页面中找到“文件上传”，设置是否允许文件上传以及最大文件上传限制。 [![Moodle Single Course upload setting](http://www.ilester.net/wp-content/uploads/2016/04/Moodle_SingleCourse_uploadSetting-300x207.png)](http://www.ilester.net/wp-content/uploads/2016/04/Moodle_SingleCourse_uploadSetting.png)

#### 4、活动级

另外，在上述各个配置值的限制下，也可以针对具体活动进行上传文件的限制，可以由具有编辑权限的帐户（例如课程的教师角色）登录后，编辑此项活动的设置，在相应的选项中进行操作，以“作业”为例，是在“作业类型”选项卡下操作，如图。 [![Moodle Single Activity Upload Setting](http://www.ilester.net/wp-content/uploads/2016/04/Moodle_Activity_upload_setting-300x203.png)](http://www.ilester.net/wp-content/uploads/2016/04/Moodle_Activity_upload_setting.png)

* * *

问答是我们自2016年起开设的新栏目，如果您有教育信息化应用方面的疑惑与问题，欢迎递交。我们会协调我们的专家网络，尽力给您解答。咨询方式：

*   电子邮件：limx@ilester.net （李同学）
*   新浪微博：请用[@iLester](http://weibo.com/zjlester) 或 [@ICT教育应用](http://weibo.com/TechStar?is_all=1) 向我们提问（恕不接受私信咨询，请谅解）。
*   微信公众号：您可以查找搜索以下微信公众号：mlearning（或扫描以下二维码），关注后以留言方式向我们提问。 [![Mlearning QR Code](http://www.ilester.net/wp-content/uploads/2016/04/qrcode_for_gh_183840cb2661_258.jpg)](http://www.ilester.net/wp-content/uploads/2016/04/qrcode_for_gh_183840cb2661_258.jpg)