---
title: Sublime Text 4 配置指北
date: 2024-10-02 12:32:00
tags: []
categories:
  - 科技
---
# 前言

Sublime Text 是一款轻量化编辑器，本篇文章将手把手教你使用 Sublime Text 配置出一个可用的信息学竞赛环境。

本文编写于 2024/10/2，Sublime 的最新稳定版是 4180，不保证未来版本的通用性。

# Part. 1 安装

从[官网](https://www.sublimetext.com/)下载 Sublime Text。Sublime 需要许可证注册，不过有一个无限期试用，就是时不时会有弹窗提醒你激活。至于激活，网上有许多歪门邪道，请自行搜索。

打开 Sublime，选择 Tools --> Install Package Control...，或打开命令面板（Win/Linux：ctrl+shift+p Mac：cmd+shift+p）并键入 `Install Package Control` 来安装插件管理器。

# Part. 2 配置基本环境

打开命令面板，选择 `Package Control: Install Package`，视网速等待一段时间后，将出现一个插件菜单。我们接下来的大部分安装操作都将基于这个菜单进行。

安装 `ChineseLocalizations` 来汉化 Sublime Text。

（可选）安装 `ayu` 及 `A File Icon` 美化 Sublime。

安装 `BracketHighlighter` 获得括号高亮显示。

安装 `ConvertToUTF8` 以应对不同编码的文件。

安装 `SideBarEnhancements` 以获得侧边栏的文件浏览。

安装 `SyncedSideBar` 使切换文件时同步侧边栏。

安装 `Terminus` 以获得一个内嵌终端。（注意：该插件与 clink 不兼容，若你的cmd）

TODO。。。
