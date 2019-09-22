---
title: Hexo-Next-github搭建个人博客
date: 2019-09-23 10:51:43
tags:
- Hexo
- 博客
categroies: 博客
copyright: true
---

> 之前在国内的时候曾经一度心血来潮想搭建自己的博客来着，无奈之前自己的笔记都发布在了网易博客上了！最令人尴尬的是网易博客关！掉！了！心碎💔！于是转战成为知笔记。之前一直发现为知笔记挺好用，现在在国外交流，有很多笔记储存在云端，需要同步到本地！巨烦琐！
>
> Anyway，我突然想到之前因为瞎搞搞过Hexo加GitHub搭建个人博客，既然这段时间无心科研，何不再重新操作一下，顺便记录下作为新博客的开端呢！那我们就开始吧～～～

[TOC]

## 参考大佬的blog

1. [Hexo博客+Next主题深度优化与定制](https://bestzuo.cn/posts/blog-establish.html)
2. [GitHub+Hexo 搭建个人网站详细教程](https://zhuanlan.zhihu.com/p/26625249)
3. [hexo: (一)基于 github 托管的 hexo 个人博客搭建](https://chentging.github.io/2018/05/14/hexo：（一）基于 github 托管的 hexo 个人博客搭建/)
4. [Hexo-NexT配置超炫网页效果](https://www.jianshu.com/p/9f0e90cc32c2)

<img align="right" width="50%" src="https://pic2.zhimg.com/v2-70bb9e331eaa44a64ef703075bc5c522_1200x500.jpg">参考了很多的博客教程，自己也是一点点在摸索，不会就Google或者百度！

边摸索边学习嘛！

事情都会解决的！
大家动起来！
搞一搞自己的小博客吧！



## 前言

一些拓展阅读～

有兴趣就点击，没兴趣直接看下一部分哦！❤️

[什么是hexo]([https://hexo.io](https://hexo.io/))

> Hexo是一款基于Node.js的静态博客框架，依赖少易于安装使用，可以方便的生成静态网页托管在GitHub和Heroku上，是搭建博客的首选框架。这里我们选用的是GitHub，你没看错，全球最大的同性恋交友网站（逃……）。Hexo同时也是GitHub上的开源项目，参见：[hexojs/hexo](https://link.zhihu.com/?target=https%3A//github.com/hexojs/hexo) 如果想要更加全面的了解Hexo，可以到其官网 [Hexo](https://link.zhihu.com/?target=https%3A//hexo.io/) 了解更多的细节，因为Hexo的创建者是台湾人，对中文的支持很友好，可以选择中文进行查看。这里，默认各位猿/媛儿都知道GitHub就不再赘述。

## 准备工作

### 查看环境

system：**MacOS** ```看自己的电脑属于什么系统```

Node.js:  **v10.16.3** ```写作时的版本```

git:  **git version 2.23.0**  ```写作时的版本```

### 安装Git

git是凯源的分布式版本控制系统，用于敏捷高效地处理项目，bulabula～～有兴趣的小伙伴可以直接Google或者百度。在这里我想说的是：我们的网站在本地搭建好了,如果想同步到GitHub上，这时候git就发挥作用了。安装 Git 的话，如果是 windows 系统，可以直接去[windows的Git下载地址](https://gitforwindows.org/)去下载，如果是 macOS 的话，也可以在[这里下载](https://www.git-scm.com/download/)。当这些环境都部署好之后，就可以开始我们的 Hexo 博客安装啦！

``` git --version```        检验下你的git安装成功了没有吧

### 安装node.js

Hexo是基于node.js渲染的，所以在正式开始之前，下载起来！[Node.js中文官网](http://nodejs.cn/download/) 选择好对应版本和系统的安装包！

安装后看看node是否安装成功 ``` node -v```

别忘了检测npm是否安装成功， 在terminal或者命令行中输入```npm -v```

### 安装Hexo

在自己的电脑新建一个文件夹（在这里Eileen创建的是一个叫做MyBlog的文件夹），之后Hexo和以后自己发布的网页都在这个文件夹中。进入文件夹``` cd MyBlog```

``` npm install -g hexo-cli```	使用npm命令安装Hexo

```hexo init ```   初始化hexo（这个步骤会有点慢，初始化完成后你会发现我们刚才创建的文件夹里有如下文件夹）

![Mac终端显示](Hexo-Next-github搭建个人博客-1/WX20190920-110811.png)

这个里面有一个`_config.xml`文件，这个我们叫做 ：<font color="#dd0000">站点根目录配置文件</font> ，里面的初始内容如下：（附上中文介绍）

```xml
# Hexo Configuration
## Docs: https://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/

# Site 站点主配置
title: Hexo  # 网站标题
subtitle:    # 网站副标题
description:   # 网站描述
keywords:      # 可以不填写保持默认
author: John Doe  # 网站拥有者昵称
language:    # 网站语言设置，一般根据依赖的主题而定
timezone:    # 网站时区设置，一般不填写保持默认

# URL地址链接设置
url: http://yoursite.com   # 网站url设置
root: /                    # 网站根目录链接
permalink: :year/:month/:day/:title/   # 文章链接，默认是按照 /年/月/日/文章标题 设置的链接
permalink_defaults:                    # 默认链接形式

# Directory  网站主要目录，这里一般不做改动
source_dir: source
public_dir: public
tag_dir: tags
archive_dir: archives
category_dir: categories
code_dir: downloads/code
i18n_dir: :lang
skip_render:

# Writing  网站文章设置，同样一般不做改动
new_post_name: :title.md  # File name of new posts
default_layout: post
titlecase: false # Transform title into titlecase
external_link: true # Open external links in new tab
filename_case: 0
render_drafts: false
post_asset_folder: false
relative_link: false
future: true
highlight:
  enable: true
  line_number: true
  auto_detect: false
  tab_replace:
  
# Home page setting  主页设置，一般不做改动
index_generator:
  path: ''
  per_page: 10
  order_by: -date  # 首页文章排序，默认是按照文章日期递减
  
# Category & Tag  分类设置，一般不做改动
default_category: uncategorized
category_map:
tag_map:

# Date / Time format  日期设置，一般不做改动
date_format: YYYY-MM-DD
time_format: HH:mm:ss

# Pagination  导航页设置，一般不做改动
per_page: 10   # 设置每页展示多少文章
pagination_dir: page

# Extensions  使用的主题名称，可以在这里切换
theme: next  # 此处切换主题名称

# Deployment  部署，一般选择部署到Github上
deploy:
  type:
```

到这里，我们的hexo的雏形已经搞定了！让我们一起来瞅瞅吧～

```//cd Myblog
hexo clean && hexo g && hexo s
```

![image-20190920114951291](Hexo-Next-github搭建个人博客-1/image-20190920114951291.png)

当然这是我已经处理过主题设置的网页了，你们也可以根据自己的要求去设计自己的网页。

## 将hexo博客部署到GitHub上

在部署到GitHub上之前，我们需要准备好自己的GitHub账号，[官网在这儿!](https://github.com/)

### 创建GitHub仓库

首先，我们需要在GitHub创建一个repository，在登陆账号之后，点击右上角的new，创建新的仓库。![image-20190923094625181](Hexo-Next-github搭建个人博客-1/image-20190923094625181.png)

![image-20190923095337061](Hexo-Next-github搭建个人博客-1/image-20190923095337061.png)

**注意这里名字可以为```GitHub用户名.github.io```**，这样设置好以后，我们在不绑定域名的前提下，可以直接使用http://xxxxx.github.io 来直接访问自己博客。（这里Eileen因为之前打过一个以用户名创建的网页，后来因为出国，所有的配置都有所改变，这里并没有直接用自己的用户名搭建，后面会专门出一个帖子说明怎么在不同的电脑上进行切换发布）。

### 配置SSH Key

如果是首次在自己的电脑上使用Git上传到GitHub，那么必须配置```SSH Key```，表示GitHub允许这台机器有权限使用git上传代码到远程仓库。这里Eileen用的实验室的Mac，所以就按照Mac的程序来啦😊～

打开终端，然后输入：

``` ssh-keygen -t rsa -C “GitHub注册邮箱地址” ```

在提示后连续回车，最终会生成一个文件夹```.ssh```，里面存放了密钥，然后我们把id_rsa.pub密钥的全部内容复制，打开[GitHub_Settings_keys](https://link.zhihu.com/?target=https%3A//github.com/settings/keys) 页面，新建new SSH Key

![image-20190923100738043](Hexo-Next-github搭建个人博客-1/image-20190923100738043.png)

title可以随意填写一个，然后将复制好的id_rsa.pub内容粘贴进去，最后点击Add SSH Key。![image-20190923101053626](Hexo-Next-github搭建个人博客-1/image-20190923101053626.png)

使用``` ssh git@github.com```来检测是否设置成功。

### 配置Git提交的用户信息

上面配置成功后，我们就可以设置Git的全局用户信息了，这个信息设置当前git命令上传代码的用户信息。使用以下命令：

```
git config --global user.name "Sanarous" // 你的github用户名，非昵称
git config --global user.email  "xxx@qq.com" // 填写你的github注册邮箱
```

配置完成之后，以后提交代码都是使用的这个用户信息进行提交的。

### 将hexo博客部署到GitHub上

首先打开hexo站点的配置文件，找到deploy部分，并填写以下配置信息：

![image-20190923101744983](Hexo-Next-github搭建个人博客-1/image-20190923101744983.png)

接着下载安装一个插件```hero-deployer-git```, 进入博客的根目录下用以下命令进行安装：

```npm install hexo-deployer-git --save```

然后我们就可以使用```hexo clean && hexo g && hexo d```来完成一键部署到GitHub上了。现在试试结果如何吧～

