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

GitHub 是非常棒的工具，通过 GitHub 的客户端、命令行和网页版版，现在我们能越加方便地使用基于 GitHub 的各种功能。

当然，在追求效率的时候，还是可以对于日常操作进行优化的：

使用客户端的方案：

1. 打开 GitHub Desktop
2. 切换到对应博客仓库，添加更新描述，点击确认
3. 点击同步





合成的「添加-提交和推送」.

在任意目录为博客仓库执行快速更新命令集：

```
# 添加新博文
alias pst="cd ~/Your_Blog_Path && git add . ; git commit -m 'Add a new post' ; git push ; sleep 0.5s ; open Your_blog_Website" 
```


```
# 更新博客设定
alias blg="cd ~/Your_Blog_Path && git add . ; git commit -m 'update the files' ; git push" 
```

在任意仓库内执行快速更新命令集：

```
alias nuts="git add . ; git commit -m 'update the files' ; git push"
```

---
cd ~/Pages && git add . ; git commit -m 'Add a new post' ; git push

cd ~/Pages && git add . ; git commit -m "Add a new post" ; sleep 0.3s ; git push