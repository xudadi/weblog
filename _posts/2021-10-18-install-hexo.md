---
title: 'install-hexo'
date: 2021-10-18 11:39:51
tags: [hexo]
published: true
hideInList: false
feature: 
isTop: false
---

## 环境要求

1.首先安装Nodejs和Git

nodejs 下载地址 https://www.nodejs.org

git 下载地址 https://www.git-scm.com

推荐使用腾讯软件中心下载

Nodejs：https://pc.qq.com/search.html#!keyword=nodejs

Git：https://pc.qq.com/search.html#!keyword=git

安装默认路径就可以了

安装好Nodejs和Git后
<!-- more -->
## 2.安装Hexo

在D盘创建一个blog文件夹，或者其他盘都可以

在blog文件夹内，按住shift+鼠标右键，选择在此处打开命令窗口。

输入命令

```
npm install hexo-cli g
```

国内安装可能很慢，修改镜像源，输入命令

1.临时使用
```
npm --registry https://registry.npm.taobao.org install express
```

2.持久使用
```
npm config set registry https://registry.npm.taobao.org
```

配置后可通过下面方式来验证是否成功
```
npm config get registry 或 npm info express
```

3.通过cnpm使用
```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

Hexo下载完成后，需要在blog文件夹内初始化Hexo，执行命令
```
hexo init
```

## 3.获取博客主题
```
npm install hexo -renderer-scss --save
```

## 4.Hexo安装swig
```
npm i hexo-renderer-swig
```

## 5.克隆主题
```
git clone https://gitee.com/xudadi/hexo-theme-even themes/even
```

克隆完成后，在/Hexo/themes目录下，可以看到.gitkeep和even 两个文件夹。
我们所要使用的主题都是放在这个目录下，Hexo默认使用的是landscape主题，由于第二步Hexo初始化时主题没有clone成功，所以我们这一步克隆了even主题，接下来会使用even主题进行演示。
想获取更多主题，可在网站：https://hexo.io/themes/ 选择自己喜欢的主题，按照此步的步骤clone下来。

## 6._config.yml进行博客基础配置

title: 博客名字

subtitle: 标题

description: 描述

keywords: 关键词

author: 作者

language: 语言

timezone: 时区

## 7.在_config.yml中配置Git

注意空格（type，repo，branch）

```
deploy:
  type: git
  repo: https://github.com/xudadi/blog.git
  branch: master
```

## 7.本地预览博客

清除缓存
```
hexo clean
```

编译项目，输入命令：
```
hexo g
```

运行项目，输入命令：
```
hexo s
```

## 8.在_config.yml中配置博客地址和路径
```
url: https://xudadi.cn/blog/
root: /blog
```

## 9.发布到github
输入命令,安装自动部署发布工具
```
npm install hexo-deployer-git --save
```

输入命令,发布博客，首次发布需要在shell中输入账号和密码。
```
hexo clean && hexo g && hexo d
```

至此，我们的博客就搭建完成啦！！！
在/Hexo/source/_posts目录下就可以写我们的博客啦！！！
