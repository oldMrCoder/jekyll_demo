---
layout: post
title:  "Welcome to Jekyll! test"
date:   2015-11-13 22:42:11 +0800
categories: jekyll update
---

## 三大区域与版本的回档：

工作区，暂存区，版本头指针是可以独立活动的吗？是的，它们是独立存在。
这里没有是不是空的概念，只有内容是不是保持了一致，如果是，git status执行结果将是空的，如果三者有内容不一致的地方，git status 执行后会显示相应的提示。

1.将分支的时间轴的头指针HEAD回档到指定的版本号，并取其内容覆盖暂存区和工作区的内容：

    git reset —hard 版本号

2.将分支的时间轴的头指针HEAD回档到指定的版本号，但暂存区和工作区的内容保持不变，git status 会显示有新的内容提交（实际上表示暂存区的内容与当前版本的不一致）：

    git reset —soft 版本号

3.如果不加参数：

    git reset 版本号		

将分支的时间轴的头指针HEAD回档到指定的版本号，并取出内容，只覆盖暂存区，工作区内容保持在版本跳转之前，git status 会显示有内容可以add  或 checkout（实际上表示工作区的内容与当前暂存区的不一致）

以上就是工作区＼暂存区＼版本，三者在版本切换时可能发生的互动，当切换新版本时，对另外两者的覆盖程度是不一样的：

    git reset —soft
	git reset 默认（也就是：git reset —mixed）
	git reset —hard
