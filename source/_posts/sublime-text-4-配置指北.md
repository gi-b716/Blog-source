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

安装 `AdvancedNewFile` 以获得增强的新建文件功能。

安装 `BracketHighlighter` 获得括号高亮显示。

安装 `Clickable URLs` 以获得可点击的 URL。

安装 `Compare Side-By-Side` 以对比两个文件。

安装 `ConvertToUTF8` 以应对不同编码的文件。

安装 `SideBarEnhancements` 以获得侧边栏的文件浏览。

安装 `SyncedSideBar` 使切换文件时同步侧边栏。

安装 `Terminus` 以获得一个内嵌终端。（注意：该插件与 clink 不兼容，若你的 cmd 注入了 clink，后续有教程解决相关问题。）

（可选）安装 `Toggle the View Read-Only` 让一个文件变得只读。

安装 `TrailingSpaces` 显示多出来的空格。

# Part. 3 配置 C++ 环境

首先安装 C++ 环境，由于 Sublime Text 的自动补全需要 Clangd，所以使用 Mingw 的用户也需要按照这一步操作。我们使用 MSYS2 安装所需的 C++ 环境。

打开 [MSYS2 官网](https://www.msys2.org/)，下载并安装。如果安装过程卡在了 50%，请尝试断网后重新安装。

安装完成以后，打开 MSYS2，输入 `pacman -Su` 更新软件包。若更新缓慢，可以在 `C:\msys64\etc\pacman.d` 下设置镜像。在此期间 MSYS2 提示你输入 `y` 之后会关闭，重新打开再输入一遍` pacman -Su` 即可。

接下来，使用
```
pacman -S mingw64/mingw-w64-x86_64-make mingw64/mingw-w64-x86_64-gdb mingw64/mingw-w64-x86_64-clang
pacman -S mingw64/mingw-w64-x86_64-clang-tools-extra
```
完成剩余的安装，并将 `C:\msys64\mingw64\bin` 添加至 path 中。请保证你的 Python 环境位于此条上面，不然 MSYS2 会覆盖你已有的 Python 环境。

回到 Sublime，我们安装 `LSP` 及 `LSP-clangd` 获得 C++ 补全支持，你也可自行安装其他语言的补全支持，均已 `LSP-` 开头，部分需要 `Node.js`。
