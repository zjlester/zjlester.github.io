---
title: Q&A：Github Pages如何绑定独立域名？
tags:
  - 建站技术
url: 11.html
id: 11
categories:
  - 问题与解答
date: 2014-09-03 09:41:19
---

### 问

浙江师范大学学生：老师好，我按您的方法在Github Pages上创建了一个自己的站点，请问有没有办法将它绑定自己申请的独立域名？

### 答

Github Pages支持绑定自己的域名，既可以是独立域名，也可以是子域名。操作方法如下：

1、 新建一个无后缀的文件，内容为需要绑定的域名，例如ict.zjnuoverseas.net。

2、将CNAME文件添加并推送至到master分支（个人站点）或gp-pages分支的根目录下。如果采用的是Octopress的话，则放到source目录下，再部署一遍。

3、获取Pages的解析IP，在Mac下可以用 dig domainname.com的形式查询，例如dig ict.zjnuoverseas.net，你将得到以下信息（如果在Windows下，可以ping或者tracert）

        ; <<>> DiG 9.8.3-P1 <<>> ict.zjnuoverseas.net
        ;; global options: +cmd
        ;; Got answer:
        ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 30103
        ;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 2, ADDITIONAL: 4
    
        ;; QUESTION SECTION:
        ;ict.zjnuoverseas.net.      IN  A
    
        ;; ANSWER SECTION:
        ict.zjnuoverseas.net.   218 IN  A   103.245.222.133
    
        ;; AUTHORITY SECTION:
        zjnuoverseas.net.   3218    IN  NS  ns68.domaincontrol.com.
        zjnuoverseas.net.   3218    IN  NS  ns67.domaincontrol.com.
    
        ;; ADDITIONAL SECTION:
        ns67.domaincontrol.com. 83372   IN  A   216.69.185.44
        ns67.domaincontrol.com. 39980   IN  AAAA    2607:f208:206::2c
        ns68.domaincontrol.com. 41756   IN  A   208.109.255.44
        ns68.domaincontrol.com. 67911   IN  AAAA    2607:f208:302::2c
    
        ;; Query time: 125 msec
        ;; SERVER: 192.168.1.1#53(192.168.1.1)
        ;; WHEN: Sun Feb 23 22:08:44 2014
        ;; MSG SIZE  rcvd: 197      
    

在Answer一栏中得到A记录的目标地址，例如这里显示的IP是103.245.222.133（本来应该在开始操作前用xxx.github.io地址来试的）。

4、在域名注册商的操作面板中新建一个与CNAME中记录域名相匹配的A记录，指向Github的解析服务器地址。