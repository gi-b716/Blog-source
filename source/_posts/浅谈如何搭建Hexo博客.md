---
title: 浅谈如何搭建Hexo博客
date: 2024-07-22 22:04:53
categories:
  - 科技
---

## 前言

    由于老博客年久失修且文件杂乱不易于维护，笔者意将老博客存档并部署了新博客，开一个文章与大家分享部署过程。

## 部署Hexo博客

### 1. 环境准备

    安装  node.js ，并装载 `hexo-cli`  包。

```bash
npm install -g hexo-cli
```

    建立 Github 仓库 `username.github.io` 。

### 2. 初始化项目

    在任意目录下执行：

```bash
hexo init hexo-blog
```

    若要检查是否成功初始化，可尝试运行：

```bash
cd hexo-blog
hexo g
hexo server
```

### 3. 更改主题（可选）

#### NexT 主题

    **笔者未使用 NexT 主题，故下方内容为网上信息整合而成。**

    使用 git 安装 NexT 主题：

```bash
cd hexo-blog
git clone https://github.com/iissnan/hexo-theme-next themes/next
```

    打开 `_config.yml` ，将主题修改为 NexT：

```yml
theme: next
```

    NexT 主题拥有丰富的插件，[洛谷日报 hexo+next搭建博客 ](https://www.luogu.com.cn/article/j7j5m2a3#:~:text=next%20%E4%B8%AD%E8%AE%B2%E8%A7%A3%E3%80%82-,next,-next%20%E6%98%AF%E4%B8%80%E4%B8%AA) 有更多介绍。

#### Fluid 主题

    下载 [最新 Release 版本](https://github.com/fluid-dev/hexo-theme-fluid/releases) 并解压至  `themes`  目录，并将解压出的文件夹重命名为 `fluid` 。

##### 创建「关于页」

    首次使用主题的「关于页」需要手动创建：

```bash
hexo new page about
```

    创建成功后，编辑博客目录下 `/source/about/index.md`，添加 `layout` 属性。

    修改后的文件示例如下：

```markdown
---
title: about
date: 2020-02-23 19:20:33
layout: about
---

这里写关于页的正文，支持 Markdown, HTML
```

### 4. 创建文章

    在博客目录下执行以下命令即可：

```bash
hexo new post 测试文章
```

    若要为每个文章建立专门的资源文件夹，请在配置中打开：

```yml
post_asset_folder: true
```

### 5. 个性化配置

    TODO...

## 部署

### 部署至Github

    在博客目录下执行：

```bash
hexo g
```

    然后将 `Public` 上传至 Github 即可。

    也可以使用 `hexo-deployer-git` 自动部署：

```bash
npm install hexo-deployer-git --save
```
