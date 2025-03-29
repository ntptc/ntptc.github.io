---
share: true
tags:
  - DIY
date: 2025-03-26
layout: single
---


无需安装任何技术类软件。纯线上操作。

# Github Pages配置

1.注册Github。了解基本概念。
参见：https://www.youtube.com/watch?v=ARU-ZD9pfO4
2.挑选一个网站模板，用它生成一个自己的仓库。
https://maximevaillancourt.com/blog/setting-up-your-own-digital-garden-with-jekyll
3.做好设置。有个关键设置：设置-选择Github actions（工作流），然后要选择Deploy Jekyll with GitHub Pages这个workflow（需要搜索下，当时我做完前几步默认显示是Jekyll，结果总是部署不成功）。
4.去Code页面修改文档，会自动触发action。
5.静态博客发布成功。

# Obsidian同步

1.安装Obsidian，设置仓库。
2.获取个人token，
https://dg-docs.ole.dev/advanced/fine-grained-access-token/
3.安装Enveloppe插件。
https://enveloppe.ovh/
4.开始在obsidian里写作。
5.设置元数据。share: true
6.ctrl+p，调用Upload single current active note 命令，发布。

主要参考资料：
https://leoz2050.github.io/DigitalGarden/2023/09/03/Build-Blog-Online.html

https://lazyjack.12123123.xyz/%E5%85%B6%E5%AE%83%E8%B5%84%E6%BA%90/Obsidian/Quartz%E4%B8%8EEnveloppe%E6%8F%92%E4%BB%B6%E7%BB%93%E5%90%88%E5%8A%A9%E5%8A%9BObsidian%E6%90%AD%E5%BB%BA%E6%95%B0%E5%AD%97%E8%8A%B1%E5%9B%AD

https://stephango.com/

官方提供模板
https://pages.github.com/themes/
https://jekyllrb.com/resources/


其他模板
https://jekyllthemes.io/theme/just-the-docs

文档参数
https://jekyllrb.com/docs/front-matter/