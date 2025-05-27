# the Unpublished README

用的主题是：==brewm==

[demosite](https://foxihd.github.io/hugo-brewm/en/) for reference.
[github](https://github.com/foxihd/hugo-brewm) for example configuration.

甚至还支持脚注，太妙了。

## 状况与解决

状况：本地可以预览，但是没看到 test 草稿
解决：一是看文章是否发布，二是看根据文件夹索引能否加载出文章。首先是要注意草稿状态，默认状态下每篇文章前面的 front matters 中 draft 一栏如果写 true 则会被认为是草稿而不予发布，可以调整 archetype 中的设置为默认 false 也可以每次发布前手动调整。其次是注意 content 文件夹下要新建一个名为"_index.md"的文件提醒 hugo 按照文件夹在首页建立索引。

把示例中的文件拉下来了一点，但是还没搞明白首页的那个设置怎么调。

## 配置

### front matter

有点搞明白了，这个主题 [brewm](https://github.com/foxihd/hugo-brewm) 要实现 90% 需要以下 front matter：
```
+++
author = ["作者名字"]
title = "文章标题"
description = "简介"
date = "日期"
type = "post"
draft = false
translationKey = "history"
coffee = 1
tags = ["标签1", "标签2", "标签3"]
categories = ["分类"]
stage = "文章阶段（写作与修订进度），设置了一下晚点测试"
history = [
  {date = "2025-02-01", stage="草稿", author = "Author Name", reviewer = "Reviewer Name", note = "Example"},
  {date = "2025-02-02", stage="初成型", author = "Author Name", editor = "Editor Name", note = "Addendum (example)"},
  {date = "2025-02-03", stage="完稿/待修订", note = "Errata (example)"},
]
toot = "https://fediversepost/"
+++
```

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