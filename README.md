# the Unpublished README

用的主题是：==brewm==

[demosite](https://foxihd.github.io/hugo-brewm/en/) for reference.
[github](https://github.com/foxihd/hugo-brewm) for example configuration.

甚至还支持脚注，太妙了。

## 发布与更新

本地查看预览：gg gg g p
```
hugo server
```

发布 readme 等到 main 分支：
```
cd main对应的文件夹
git add .
git commit -m "更新readme"
git push origin main
```

发布静态文件 (public) 到 gh-pages 分支目前使用 ghp-import

```
hugo
ghp-import -n -p public
```

## 状况与解决

Q: 本地可以预览，但是没看到 test 草稿
A: 一是看文章是否发布，二是看根据文件夹索引能否加载出文章。首先是要注意草稿状态，默认状态下每篇文章前面的 front matters 中 draft 一栏如果写 true 则会被认为是草稿而不予发布，可以调整 archetype 中的设置为默认 false 也可以每次发布前手动调整。其次是注意 content 文件夹下要新建一个名为"_index.md"的文件提醒 hugo 按照文件夹在首页建立索引。

把示例中的文件拉下来了一点，但是还没搞明白首页的那个设置怎么调。

Q: 现在是 main 放源码，gh-pages 放 public 文件夹中的静态文件。部署的时候 github 报错说主题的子模块找不到 url，但是网页成功渲染了。（之前试图只放 public 不放源码没法渲染）

Q: post 导航栏的 en/post/...中 en 应该是无效的，hover 会出现的界面也需要调整，要找下是哪些文件有关

Q: 修改了 rss 设置一会看

Q: 主题设置中有的需要修改
A: 先 fork 一下，然后改主题时推送到子仓库，再更新主仓库

## 配置

### front matter

有点搞明白了，这个主题 [brewm](https://github.com/foxihd/hugo-brewm) 要实现 90% 需要以下 front matter：

```
+++
author = "作者"
title = "标题"
description = "摘要"
date = "yyyy-mm-dd"
type = "post"
draft = false
translationKey = "history"
coffee = 1
tags = ["tag", "tag"]
categories = ["分类"]
stage = "初成型/完稿/草稿/待修订"
history = [
  {date = "yyyy-mm-dd", stage="状态", author = "作者", reviewer = "", note = ""}
]
toot = ""
+++
```

关于博文里 feditoot 的链接，上次七月份更新之后加了个链接进去，等下次更新之后我看下效果。

### 作者介绍（或者其它）

形似以下结构可以用于做作者页介绍：
```
~/content/文件夹/_index.md
```
内容：
```
---
title: ""
---
其它介绍
```
也可以用作其他作用

## 待办

- 当然还是先把文章 front matter 改完
- 调缩进和换行
- 主题模式与主题色设置（进文章页自动变黑？
- 调整作者页&文章页排版，减少右边栏宽度
- 文章能不能显示目录
- 定义 markdown 渲染效果
- 添加网页链接的效果
- 把主页上的东西填满，最好找一组 logo 图
- 调整评论等一时半会用不到的