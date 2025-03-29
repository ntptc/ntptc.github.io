---
share: true
tags:
  - DIY
layout: single
date: 2025-03-29
github: true
---
我从2024年底开始用Obsidian写笔记，接触到 file over app [本地文件优先](https://stephango.com/file-over-app)这个口号，感觉他们这种反对完全依赖互联网巨头公司生产内容的理念，和早期朋克运动强调的DIY精神有些相似，有些抵抗主流建制的意味。

同时发现Github Pages现在已经十分易用，无需再学习Git、Ruby这些对我这种非计算机专业人士来说过于复杂的软件，只需简单在线配置就可以生成个人网站。

于是，Obsidian和Github Pages两者一结合，已经可以让写博客变得十分自主：我在本地用Obsidian写笔记，写完后如果觉得想公开发布，把本地的Markdown文件上传到Github的仓库里即可，内容会自动发布到个人网站。

以下是一些个人配置经验：

# 一、基础概念

1. **Github Pages:** ​**GitHub 官方提供的免费静态网站托管服务**，允许用户直接从 **GitHub 仓库**直接部署静态网页。
2. **Jekyll**: 是一款流行的 **静态网站生成器**，由 GitHub 联合创始人 Tom Preston-Werner 创建。它可以将纯文本（如 Markdown、HTML 等）转换为静态网页，适合构建个人网站等。
3. **Obsidian:** 一款以 ​**本地优先、Markdown 驱动** 的笔记工具，所有笔记以纯文本（Markdown 文件）存储在本地，无需依赖云端。主打 ​**双向链接** 和 ​**知识图谱** 功能。它通过网状结构组织笔记，帮助用户构建个人化的知识库。

简单来说，就是Github提供免费空间，Jekyll社区有大量的网站模板，可以直接应用Jekyll模板在Github生成个人网页。网页搭建好后，主要工作就是更新内容。而这实质就是上传一些Markdown文件即可，Obsidian是便于你编写Markdown文件的工具。

# 二、基本流程

## 网站发布

1. 注册github
2. 挑选Jekyll网站模板，我用的是[minimal-mistakes/](https://mmistakes.github.io/minimal-mistakes)
3. 把模板复制fork到自己仓库Repository。**注意**要把分支branch名称从master改为main，因为受BLM运动感召，从 2020 年 10 月 1 日开始，GitHub 上的所有新库都用中性词「main」命名，取代原来的「master」，如果不改后面会出现兼容性问题。
4. 在仓库Settings-Pages里，启用Github actions，我用的是Deploy Jekyll with GitHub Pages。
5. 网站发布成功。在仓库的Actions里可以看到运行情况。
6. 结合网站模板的官方介绍文档以及google大法，完成网站个性化配置。我只修改了网站名、简介、地区和字体大小等。

## 使用Obsidian联动更新内容

1. 安装[Obsidian](https://obsidian.md/)，并启用[Enveloppe插件](https://enveloppe.ovh/)。
2. 按此[流程](https://dg-docs.ole.dev/advanced/fine-grained-access-token/) 配置Github的个人token，完成Enveloppe插件参数设置。
3. 按照Markdown语法写笔记，同时设置笔记YAML，我设置了四个元数据：share、tags、layout和date
4. 通过Enveloppe插件功能推送笔记到Github仓库，网页内容随后会自动更新。

# 三、踩过的坑

## 网站模板选择

[Jekyll网站模板](https://jekyllrb.com/resources/)实在太多，试过四五个。最后还是选择了最热门的Minimal Mistakes，因为它的介绍文档最为详细，且因用的人多，遇到问题比较容易搜到答案。

## Markdown 文件名称

按照[Jekyll官方文档](https://jekyllrb.com/docs/posts/)，上传的Markdown文件名必须为："YYYY-MM-DD-标题”格式，否则无法识别。这个限制我觉得比较无聊。

## 繁琐细节太多

在配置过程中觉得还是隔行如隔山，哪怕是一个这么简单的网站，背后实际也有大量的文件，比如下面这些：
 ```
  .
  ├── _posts/       # 博客文章（Markdown 文件）
  ├── _layouts/     # HTML 模板
  ├── _includes/    # 可复用的代码片段
  ├── _config.yml   # 配置文件（设置站点标题、主题等）
  ├── assets/       # 静态资源（CSS、JS、图片）
  
  ```

至于Obsidian，除了要熟悉基础[Markdown语法](https://www.markdownguide.org/getting-started/)之外，也需要花时间去熟悉理解它的使用逻辑。

最后，对于整个设置流程，推荐这篇更为详细的介绍：[Quartz与Enveloppe插件结合助力Obsidian搭建数字花园](https://lazyjack.12123123.xyz/%E5%85%B6%E5%AE%83%E8%B5%84%E6%BA%90/Obsidian/Quartz%E4%B8%8EEnveloppe%E6%8F%92%E4%BB%B6%E7%BB%93%E5%90%88%E5%8A%A9%E5%8A%9BObsidian%E6%90%AD%E5%BB%BA%E6%95%B0%E5%AD%97%E8%8A%B1%E5%9B%AD) 差别在于他用的是Quartz作为静态网站生成器，而不是Jekyll，但整体逻辑一致。