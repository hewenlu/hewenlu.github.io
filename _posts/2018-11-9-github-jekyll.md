---
layout: post 
title: '博客搭建心得' 
date: 2018-11-9 
author: Wendu 
color: '#eaf4fc'
cover: 'http://47.95.121.201/uploads/jekyll/wener1.jpg'
tags: git github jekyll markdown
---

# 通过安装jekyll在github部署自己的博客

首先到我的[github][1]下查看教程，fork到你的仓库，找到settings更改名称为你的github用户名.github.io
> 具体是怎么fork到自己的仓库，跟着这篇博客走[徐代龙的博客][2]

我再简明一下步骤：
一 ：安装Ruby
二 ：安装RubyGems
三：用RubyGems安装Jekyll
四：cd到博客文件夹，开启服务器
五：访问 http://localhost:4000/
六：提交代码到远程GitHub上

安装jekyll的目的就是可以在本地通过http://localhost:4000/访问自己的博客，实时更改，以便查看效果。即使不安装也可以，直接通过git，clone到本地，修改配置文件_config.yml改成自己的博客。具体配置信息修改参考[github][3]

## 下面说一下怎么安装jekyll

> 参考这篇博客 https://643435675.github.io/2015/02/15/create-my-blog-with-jekyll/


主要环节有：安装Ruby，安装RubyGems，安装jekyll（我这里是windows系统）
### 1.安装ruby
下载安装 https://rubyinstaller.org/downloads/
在命令提示符中输入 
```
ruby -v
```
得到版本号表示安装成功

--------

### 2.安装RubyGems

官网下载 https://rubygems.org/pages/download  最新版本的zip文件
用命令提示符cd 到安装目录
执行安装 
```
ruby setup.rb
```

------

### 3.用RubyGems安装Jekyll
还是用cmd执行安装
```
gem install jekyll
```
安装完成会出现很多代码表示安装成功

## 到此jekyll就安装成功了！

可以测试一下，如在D盘新建一个文件夹
执行ruby的命令提示符工具cd到这个文件夹下
```
jekyll new name （随便起一个项目新名字）
```
如果成功的话文件夹下面会出现很多的文件
接着还是用ruby命令提示符工具开启服务器
```
cd 到你的博客项目文件夹下
jekyll serve --watch
```
watch为了检测文件夹内的变化，即修改后不需要重新启动jekyll
第二次就可以直接启动
```
jekyll serve
```
访问 http://localhost:4000/
就看到新建的博客了

----------
同样的道理在你clone的博客下面安装jekyll
通过git或者[githubDesktop][4]将你github上的博客项目clone到本地
用ruby的命令提示符cd 到你的博客文件夹下
安装jekyll
```
gem install jekyll
```
然后再开启服务器
```
jekyll serve --watch
或 jekyll serve
或 bundle exec jekyll serve  这个肯定可以开启，我这里前面那样会报错
```
访问 http://localhost:4000/ 就看到你的博客了
再通过编辑器改一些配置信息成为你自己的博客。
最后上传到github
简单记录一下git常用命令
```
git remote add origin 项目链接   关联远程仓库

git config --global '你的名字'

git config --global '你的邮箱'

ssh -T git@github.com       查看当前是否连接成功

git clone 项目链接       克隆到本地

git status               查看当前状态

git init               创建仓库

git add .              添加文件到仓库

git commit -m "提交信息"                提交文件到仓库必须填写提交信息

git push -u origin master           首次上传到github远程仓裤

git push origin master             非首次次可以直接这样

```
书写博客就是用markdown在线编写，写好导出一个md文件
文件名命名2018-11-9-文件名.md  后面还可以继续-

-------
最后感谢博客主题提供者[徐金琦][5]，应该叫鸡哥/斜眼笑/


  [1]: https://github.com/hewenlu/hewenlu.github.io
  [2]: https://blog.csdn.net/xudailong_blog/article/details/78762262
  [3]: https://github.com/hewenlu/hewenlu.github.io
  [4]: https://desktop.github.com/
  [5]: http://xseven.me/