+++
author = ["小林"]
title = "Macbook 录屏声音处理"
description = "自用解决方案"
date = "2025-03-29"
type = "post"
draft = false
translationKey = "history"
coffee = 1
tags = ["Macbook","工具"]
categories = ["记录"]
stage = "完稿"
history = [
  {date = "2025-03-29", stage="完稿", author = "小林", reviewer = "", note = ""},
]
toot = ""
+++

Macbook 戴耳机打游戏想录屏。但是用 Quick Time Player 的默认选项时，不管选择哪个麦克风选项都无法在录屏文件中正确听到游戏声音。于是查询油管后采用了这个方案。主要参考视频：[Screen Record Mac with INTERNAL AUDIO Including Mouse Clicks & Keyboard Sounds](https://www.youtube.com/watch?v=75q-gO2oiC0)

Quick Time Player 选择：File>New Screen Recording，或快捷键 shift+command+5，按照需要选择屏幕大小，录制类型，倒计时等。
Quick Time Player 自带选项无法解决内建声音的问题，因此需要下载 [BlackHole Audio](https://github.com/ExistentialAudio/BlackHole)

下载安装后打开 Audio MIDI Setup。
添加 Aggregate Device，重命名为 BlackHole Input（按需重命名，本文按照这种命名方式便于理解），在右边的 Audio Device 中选择 BlackHole 16ch。
添加 Multi-Output Device，重命名为 Screen Recording with Audio，在右边选择 BlackHole 16ch 和相应的输出设备，如果戴耳机打游戏选择连接的耳机，注意取消其它选项以免出错。
在系统设置中打开声音，输出选择刚刚添加的 Multi-Output Device, 即名为 Screen Recording with Audio 的输出。
在 Quick Time Player 的录屏选项中，麦克风选择 BlackHole Input.
