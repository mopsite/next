---
title: Front Matter
date: 2021-10-25 19:41:32
---

{%note default no-icon%}
Front-matter 是文件开头的 YAML 或 JSON 块，用于为你的文章设置配置。
{%endnote%}

{%tabs front-matter%}
<!-- tab YAML -->
```yml
---
title: Hello World
date: 2013/7/13 20:46:25
---
```
<!-- endtab -->
<!-- tab JSON -->
```json
"title": "Hello World",
"date": "2013/7/13 20:46:25"
;;;
```
<!-- endtab -->
{%endtabs%}

NexT 对其提供了扩展并提供更多变量，它允许用户配置单个页面。

|设置|类型|描述|默认值|
|--|--|--|--|
|author|string|文章版权的作者姓名||
|post_link|string|发布链接|无|
|description|string|文章描述|无|
|direction|string|书写方向，可用值`rtl`|无|
|header|boolean|是否在首页显示文章标题|true|
|mathjax|boolean|是否支持 MathJax|主题配置文件中的`math.every_page`|
|sidebar|boolean|是否显示侧边栏|主题配置文件中的`sidebar.display`|
|copyright|boolean|是否在文章下方显示版权信息|true|
|sticky|number|是否将文章固定在首页顶部|0|
|quicklink|object|支持快速链接|取决于主题配置文件|
|reward_settings|object|打赏设置|取决于主题配置文件|
|toc|object|侧边栏中的目录|取决于主题配置文件|

{%note warning no-icon%}
object 类型的结构与主题配置文件中的选项相同。如：

```yml toc:
  enable: true
  number: false
  max_depth: 3
reward_settings:
  enable: true
  comment: Buy me a coffee
quicklink:
  enable: true
  delay: true
  timeout: 3000
  priority: true
```
{%endnote%}

以下变量在 Hexo 文档中未提及，它们需要 [hexo-theme-unit-test](https://github.com/hexojs/hexo-theme-unit-test)。

|设置|类型|示例|
|---|---|---|
|link|string|[link-post](https://github.com/hexojs/hexo-theme-unit-test/blob/master/source/_posts/link-post.md)|
|photos|array|[gallery-post](https://github.com/hexojs/hexo-theme-unit-test/blob/master/source/_posts/gallery-post.md)|
