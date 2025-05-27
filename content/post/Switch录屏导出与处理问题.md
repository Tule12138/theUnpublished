+++
author = ["小林"]
title = "Switch 录屏导出与处理问题"
description = "非常小的一个问题，非常小的一个解决方案。"
date = "2025-02-20"
type = "post"
draft = false
translationKey = "history"
coffee = 1
tags = ["Macbook","游戏","Switch","工具"]
categories = ["记录"]
stage = "完稿"
history = [
  {date = "2025-02-20", stage="完稿", author = "小林", reviewer = "", note = ""},
]
toot = ""
+++

> Macbook 用户，Switch 使用繁体中文。因此部分描述可能与简体中文使用者看到的稍有不同，但大体上应当可以理解。因为是 Macbook 用户所以主要写的是 Macbook 特有的问题，会稍微提及 Windows 系统的情况。

Switch 提供较为便捷的 30 秒录屏。以下是在保存、编辑、分享录屏时可能遇到的问题的解决方法。

## Switch 录屏导出

导出录屏与截图时，最容易想到的是相册界面里“传送到智慧型手机”的功能。但是这一功能一次智能传送 10 张图片或一个视频，而且只能传送到手机，在游玩一段时间后想起来导出资料时非常不便。批量导出视频与截图的方法是：
```
设定>资料管理>管理画面照片和影片>以 USB 连接方式复制到电脑
```
对支持 MTP 的 windows 电脑来说，只要用 USB 连接主机和电脑就可以开始批量导出。但是对于 Macbook 等电脑本身不支持 MTP 的情况，就需要：

### Android File Transfer

搜索 $\uparrow$ 这个软件并下载。打开后连接就可以批量导出 Switch 截图和视频了。在下载 Android File Transfer 之前我尝试了 openMTP，Macdroid，都连接不上。

## Switch 录屏导入 Davinci Resolve

Switch 录屏虽然是 mp4 格式，但是直接导入 Davinci Resolve 没法被正确识别。请下载：

### ffmpeg

可以通过 Homebrew 安装也可以访问官网安装。完成后打开终端：

```
cd /录屏文件所在的文件夹/
ffmpeg -i 你的录屏文件.mp4 -c copy 你的录屏文件（处理后）.mp4
```
依次如此处理你需要处理的录屏文件（也可以利用 BASH 循环、PYTHON 等实现，*只是一般没有那么多文件需要处理*）后，录屏就可以被 Davinci Resolve 正确识别了。
