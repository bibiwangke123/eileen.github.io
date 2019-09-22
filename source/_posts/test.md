---
title: test
date: 2019-09-23 11:23:51
tags:
categroies:
copyright:
---

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

system：**MacOS**  ```看自己的电脑属于什么系统```

Node.js:  **v10.16.3**  ```写作时的版本```

git:  **git version 2.23.0**   ```写作时的版本```

