---
title: 自定义页面
date: 2021-10-24 12:29:52
---

NexT 允许用户在菜单中添加自定义页面。

{%tabs custom1%}
<!-- tab 添加新页面 → -->
在终端切换到网站根目录，使用 `hexo new page custom-name` 命令来创建一个新的自定义页面：

```
cd hexo-site
hexo new page custom-name
```
<!-- endtab -->
<!-- tab 设置 Front-matter → -->
你可以在 custom-name/index.md 文件中修改或添加 Front-matter 的内容，参见 [Front-matter](https://mopsite.gitee.io/hexo/usage/front-matter/)。

```yml title: custom-name
date: 2014-12-22 12:39:04
---
```
<!-- endtab -->
<!-- tab 编辑菜单 -->
在 {%label primary@主题配置文件%} 的`menu`选项中添加 custom-name，例如添加「关于」页面：

```yml next/_config.yml
menu:
  home: / || fa fa-home
  archives: /archives/ || fa fa-archive
  about: /about/ || fa fa-user
```
<!-- endtab -->
{%endtabs%}

### 将「归档」页面作为首页

你可以在 {%label info@站点配置文件%} 中配置「归档」页面的路径和索引生成器。

```yml hexo/_config.yml
archive_dir: /

index_generator:
  path: archives
  per_page: 10
  order_by: -date
```

### 添加「标签」页面

新建「标签」页面，并在菜单中显示「标签」链接。「标签」页面将展示网站的所有标签，如果文章没有标签，此页面将为空。

{%tabs custom2%}
<!-- tab 添加新页面 → -->
在终端中切换到网站根目录，使用`hexo new page tags`命令创建一个新的「标签」页面：

```
cd hexo-site
hexo new page tags
```
<!-- endtab -->
<!-- tab 设置页面类型 → -->
编辑新页面，并将类型改为`tags`，主题将在此页面中自动显示标签云：

```yml
title: Tags
date: 2014-12-22 12:39:04
type: tags
---
```
<!-- endtab -->
<!-- tab 编辑菜单 -->
将`tags`添加到 {%label primary@主题配置文件%} 的`menu`选项中，如下所示：

```yml next/_config.yml
menu:
  home: / || fa fa-home
  archives: /archives/ || fa fa-archive
  tags: /tags/ || fa fa-tags
```
<!-- endtab -->
{%endtabs%}

{%note warning no-icon%}
如果有集成评论服务，页面也会带有评论。如果要关闭，在 Front-matter 中添加`comments`，并设置为 false。

```yml
title: 标签
date: 2014-12-22 12:39:04
type: "tags"
comments: false
---
```
{%endnote%}

NexT 默认已在「标签」页面中设置了标签云的字体大小和颜色，从 NexT v7.0.2 开始，你可以自定义它们：

```yml next/_config.yml
# 「标签」页面中设置标签云
tagcloud:
  min: 12 # 最小字号，以px为单位
  max: 30 # 最大字号，以px为单位
  amount: 200 # 标签总数
  orderby: name # 标签顺序
  order: 1 # 标签排序
```

### 添加「分类」页面

添加「分类」页面与添加「标签」页面方法一样，只是名称不同。只需将 tags 替换成 categories 即可。

### 自定义 404 页面

在终端中切换到网站根目录，新建一个名叫 404 的页面：

```
cd hexo-site
hexo new page 404
```

确保禁用了 {%label info@站点配置文件%} 中的`relative_link`：

```yml hexo/_config.yml
relative_link: false
```

{%note warning%}
用户是否可以重定向到 404 页面，取决于网站托管服务或 Web 服务器的设置，而不是 Hexon。比如你使用 Nginx 作为服务器，还需要在 nginx.conf 文件中配置 404 页面。
{%endnote%}

如果你想启用腾讯提供的公益 404 服务，可以像下面这样在 404/index.md 中编辑：

```yml
---
title: '404'
date: 2014-12-22 12:39:04
comments: false
---
<script src="//qzonestyle.gtimg.cn/qzone/hybrid/app/404/search_children.js"
        charset="utf-8" homePageUrl="/" homePageName="Back to home">
</script>
```

你也可以添加任何你想要的内容。

最后，在 {%label primary@主题配置文件%} 的`menu`选项中添加`404`即可：

```yml next/_config.yml
menu:
  home: / || fa fa-home
  archives: /archives/ || fa fa-archive
  commonweal: /404/ || fa fa-heartbeat
```
