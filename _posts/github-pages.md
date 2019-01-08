---
title: Q&A：Win7中如何用Octopress+Github Pages建立免费个人网站
tags:
  - 建站技术
url: 15.html
id: 15
categories:
  - 问题与解答
date: 2014-09-03 09:44:24
---

### 问

浙江师范大学学生：老师好，我看您介绍了可以利用Octpress和Github Pages搭建免费的个人网站，但您演示系统是Mac，我用的Win7系统也可以操作吗？

### 答

在Windows操作系统中也一样可以搭建，以Windows 7为例，操作的步骤与方法如下，请参考：

### 环境配置（Windows）

#### Git的安装与配置

1.  下载安装Git for windows: [http://msysgit.github.com/](http://msysgit.github.com/)
2.  创建本机使用Git的SSH Key
    
             ssh-keygen -C "username@email.com" -t rsa
        
    
    username@email.com需要更换成你自己的在Github上注册的Email地址 这样会在用户目录(C:\\Documents and Settings\\UserName)下产生一个.ssh文件夹，里面为对应的SSH Keys，其中id\_rsa.pub是Github需要的SSH公钥文件。 在Github的Account Settings里选择SSH Keys，到c:\\Users\\用户名.ssh\\目录找到id\_rsa.pub,复制全部内容。在github网站选择“Account Settings”>>“SSH Public Keys”>>“Add another public key”，将刚才复制的内容粘贴到key文本框内。

#### Ruby安装

1.  安装Ruby 1.9.3, 地址：([http://rubyforge.org/frs/?group_id=167](http://rubyforge.org/frs/?group_id=167))
2.  安装Ruby DevKit 下载地址：([https://github.com/oneclick/rubyinstaller/downloads/](https://github.com/oneclick/rubyinstaller/downloads/)) 解压后执行以下代码
    
             ruby dk.rb init
             ruby dk.rb install
             gem install rdiscount --platform=ruby
        
    

#### 安装Octopress

1.  从Github克隆一份Octopress：
    
             git clone git://github.com/imathis/octopress.git octopress
        
    
    修改目录下的Gemfile，将source改为“[http://ruby.taobao.org](http://ruby.taobao.org) ” (用淘宝网镜像提高安装依赖工具速度)
2.  安装依赖工具
    
             cd octopress
             ruby --version # Should report Ruby 1.9.2
             gem install bundler
             bundle install 
        
    
3.  安装Octopress默认主题（Theme）
    
             rake install
        
    

#### 配置Octopress

1.  修改_config.yml编码为UTF-8，修改以下Blog基本信息，例如：
    
         url: http://zjlester.github.io
         title: My Octopress Blog
         subtitle: A blogging framework for hackers.
         author: Lester Ruan
         simple_search: http://google.com/search
         description:
        
    
2.  到Ruby的安装目次\\lib\\ruby\\gems\\1.9.1\\gems\\jekyll-0.11.2\\lib\\jekyll\\找到convertible.rb这个文件，查找
    
             self.content = File.read（File.join（base， name））
        
    
    更改为：
    
             self.content = File.read（File.join（base， name）， :encoding => "utf-8"）。
        
    

#### 本地测试

1.  用rake new_newpost\[“title”\] 创建新贴
2.  在source/_post下找到生成的markdown文件，编辑博文。 以后要新建博文，也可以直接复制一个markdown文件再修改。
3.  用rake generate 生成静态网页
4.  用rake preview 启动本地服务，用[http://localhost:4000](http://localhost:4000) 预览。

#### 创建Github仓库

在Github网站新建一个Repository,名称为：username.github.io （以前为username.github.com，现在已经用io域名）。

#### 部署Octopress至Github仓库

1.  执行rake setup\_github\_pages，按提示输入仓库URL，可以是SSH方式或HTTPS。
    
         git@github.com:username/username.github.io.git
         https://github.com/username/username.github.io.git
        
    
2.  递交源码入source分支
    
         git add .
         git commit -m 'message'
         git push origin source