---
title: 本地搜索
date: 2021-10-25 14:36:17
---

本地搜索不需要任何第三方服务，并且可以被搜索引擎额外索引。建议大多数用户使用此搜索方法。

首先，在站点根目录中执行以下命令来安装 hexo-generator-searchdb：

```
npm install hexo-generator-searchdb
```

然后，在 {%label info@站点配置文件%} 中编辑并添加以下内容：

```yml hexo/_config.yml
search:
  path: search.xml
  field: post
  content: true
  format: html
```

最后，在 {%label primary@主题配置文件%} 中编辑以下内容以启用本地搜索：

```yml next/_config.yml
# 本地搜索
# 依赖：https://github.com/next-theme/hexo-generator-searchdb
local_search:
  enable: true
  # 如果为 auto，将通过更改输入来触发搜索。
  # 如果为 manual，按下回车键或者搜索按钮才能触发搜索。
  trigger: auto
  # 显示每篇文章的前 n 个结果，如果为 -1 将显示所有结果。
  top_n_per_article: 1
  # 将 html 字符串解码为可读。
  unescape: false
  # 页面加载时预加载搜索数据。
  preload: false
```
