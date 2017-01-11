---
layout: post
title: 
excerpt: ""
tags: [book, ]
image:
  feature: windows.jpg
  credit: Azeril
  creditlink: http://azeril.com
---



使用命令行将日常博客使用中的一些繁琐操作半自动化。

## 快速进入写作环境


日常，一般情况下使用 GitHub Pages 博客都不免是这样的流程：

1. Finder 上点点点，打开博客仓库；
2. 进入 _posts 目录， 复制一个文档作为新博文文档使用；
3. 清理文档，删除博文内容，修改 YAML；
4. 开始写作。


或者：

1. 打开编辑器，开始写作；
2. 保存文档，将文档移动到对应的博客仓库 _posts 目录；
3. 打开 Finder，进入仓库 _posts 目录;
4. 复制文档 YAML 信息，粘贴到新博文并修改；

如果借助命令行工具创建的脚本，可以让整个步骤变得非常迅捷。像这样：

1. 唤出 iTerm，输入短命令.进入命令自动执行状态。自动在仓库中完成附带 YAML 信息的模板文档的创建，同时一并打开 _posts 目录，以及用个人自定义的 Markdown 编辑器打开新创建的模板文档。
2. 在自动弹出的编辑器界面，开始写作；
3. 修改 YAML 信息和文档标题（只涉及日期字段后的 Title 部分），保存。

命令集：

使用 Sublime Text 作为默认编辑器：cd ~/Your_blog_Path/_posts/ ; open . ; cp Template.md ` date +20%y-%m-%d`-Title.md ; sleep 0.3s ; open -a MacDown ` date +20%y-%m-%d`-Title.md


使用 MacDown 作为默认编辑器：cd ~/Your_blog_Path/_posts/ ; open . ; cp Template.md ` date +20%y-%m-%d`-Title.md ; sleep 0.3s ; Sublime ` date +20%y-%m-%d`-Title.md

## 快速推送博文更新


alias pagespost="cd ~/Pages && git add . ; git commit -m "Add a new post" ; git push"

alias pgs="pagespost ; git push"


alias uppages="cd ~/Pages && git add . ; git commit -m "update the files" | git push"


alias upp="uppages ; git push"


alias nuts="git add . ; git commit -m "update the files" | git push"

alias nut="nuts ; git push"


---
cd ~/Pages && git add . ; git commit -m "Add a new post" ; git push

cd ~/Pages && git add . ; git commit -m "Add a new post" ; sleep 0.3s ; git push