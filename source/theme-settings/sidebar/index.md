---
title: 侧边栏
date: 2021-10-24 12:28:18
---

### 整体样式

默认情况下，侧边栏仅在文章页面（拥有目录列表时）才显示，并置于左侧位置。你可以在 {%label primary@主题配置文件%} 中的`sidebar`选项中修改它。

侧边栏有几个选项，包括`position`、`width`、`display`、`padding`和`offset`。

{%tabs style%}
<!-- tab position -->
通过修改`sidebar.position`的值，可以设置侧边栏的位置，该值可以是以下之一：

- left → 放置在屏幕左边。
- right → 放置在屏幕右边。

```yml next/_config.yml
sidebar:
  position: left
  #position: right
```
<!-- endtab -->
<!-- tab width -->
以像素为单位来修改`sidebar.width`的值，可以改变侧边栏的宽度，例如：

```yml next/_config.yml
sidebar:
  width: 300
```
<!-- endtab -->
<!-- tab display -->
通过修改`sidebar.display`的值，可以设置侧边栏显示的条件，可以是以下之一：

- post → 仅在有索引的文章中显示侧边栏。
- always → 在所有页面中显示侧边栏。
- hide → 在所有页面中隐藏侧边栏（但可以由用户手动打开）。
- remove → 完全删除侧边栏。

```yml next/_config.yml
sidebar:
  display: post
  #display: always
  #display: hide
  #display: remove
```
<!-- endtab -->
<!-- tab padding -->
以像素为单位来修改`sidebar.padding`的值，可以设置侧边栏的内边距：

```yml next/_config.yml
sidebar:
  padding: 18
```
<!-- endtab -->
<!-- tab offset -->
以像素为单位来修改`sidebar.offset`的值，可以设置侧边栏的偏移量：

```yml next/_config.yml
sidebar:
offset: 12
```

{%note warning%}
目前只有 NexT 6.0.x 或更高版本中的 Pisces 和 Gemini 方案支持`offset`。
{%endnote%}
<!-- endtab -->
{%endtabs%}

### 配置头像

默认情况下，NexT 不在侧边栏中显示头像。你可以通过 {%label primary@主题配置文件%} 中的`avatar`值来配置它。

{%tabs avatar%}
<!-- tab url -->
对于第一次测试，你可以取消`avatar.url`的注释来查看默认头像：

```yml next/_config.yml
avatar:
  url: /images/avatar.gif
```
<!-- endtab -->
<!-- tab rounded -->
设置`avatar.rounded`的值可以修改头像是否显示为圆形：

```yml next/_config.yml
avatar:
  rounded: true
```
<!-- endtab -->
<!-- tab rotated -->
修改`avatar.rotated`的值可以设置头像是否有鼠标悬停时的旋转效果：

```yml next/_config.yml
avatar:
  rotated: true
```
<!-- endtab -->
{%endtabs%}

### 站点状态

默认情况下，NexT 会在侧边栏中显示文章、类别和标签的数量，你可以修改 {%label primary@主题配置文件%} 中的`site_state`值来配置它：

```yml next/_config.yml
site_state: true
```

### 社交链接

社交链接和 [菜单导航](../#菜单导航) 的结构类似，只是目标链接有区别：指定的链接必须有完整的 url 路径。编辑 {%label primary@主题配置文件%} 中的`social`选项如下：

```yml next/_config.yml
social:
  GitHub: https://github.com/yourname || fab fa-github
  E-Mail: mailto:yourname@gmail.com || fa fa-envelope
  Weibo: https://weibo.com/yourname || fab fa-weibo
  Google: https://plus.google.com/yourname || fab fa-google
  Twitter: https://twitter.com/yourname || fab fa-twitter
  FB Page: https://www.facebook.com/yourname || fab fa-facebook
  StackOverflow: https://stackoverflow.com/yourname || fab fa-stack-overflow
  YouTube: https://youtube.com/yourname || fab fa-youtube
  Instagram: https://instagram.com/yourname || fab fa-instagram
  Skype: skype:yourname?call|chat || fab fa-skype
```

默认情况下，NexT 在侧边栏中显示社交链接的图标。

{%tabs social%}
<!-- tab enable -->
你可以通过修改`social_icons.enable`的值来决定是否显示图标：

```yml next/_config.yml
social_icons:
  enable: true
```
<!-- endtab -->
<!-- tab icons_only -->
将`social_icons.icons_only`的值修改为 true，可以只显示社交图标，不带文字描述：

```yml next/_config.yml
social_icons:
  icons_only: true
```
<!-- endtab -->
<!-- tab transition -->
将`social_icons.transition`的值设置为 true，可以显示社交图标的过渡动画效果：

```yml next/_config.yml
social_icons:
  transition: true
```
<!-- endtab -->
{%endtabs%}

### 链接管理

你可以在 NexT 的侧边栏中添加链接管理器（友情链接）。

{%tabs links%}
<!-- tab links_settings -->
默认情况下，NexT 将 <i class="fa fa-globe"></i> 图标显示在链接管理器的名称之前，你可以通过修改`links_settings.icon`的值来配置它：

```yml next/_config.yml
links_settings:
  icon: fa fa-globe
```

「Links」默认作为链接管理器的名称，你可以通过修改`lins_settings.title`的值来改变该名称：

```yml next/_config.yml
links_settings:
  title: Links
```

链接管理器中的每个链接默认以块级显示。你可以将`links_settings.layout`的值设为`inline`，将所有所有链接以行内样式显示：

```yml next/_config.yml
links_settings:
  layout: block
```
<!-- endtab -->
<!-- tab links -->
你可以在`links`选项中添加你喜欢的任意链接：

```yml next/_config.yml
links:
  Title1: https://example1.com/
  Title2: https://example2.com/
```
<!-- endtab -->
{%endtabs%}

### 文章目录

NexT 默认在侧边栏中显示文章目录（TOC）。

{%tabs toc%}
<!-- tab enable -->
你可以将`toc.enable`设置为 false，以禁止在侧边栏中显示目录：

```yml next/_config.yml
toc:
  enable: true
```
<!-- endtab -->
<!-- tab number -->
NexT 默认自动为目录添加序号，你可以将`toc.number`设置为 false 来禁用该功能：

```yml next/_config.yml
toc:
  number: true
```
<!-- endtab -->
<!-- tab wrap -->
如果目录标题比侧边栏宽度长，你可以将`toc.wrap`设置为 true 来折行显示目录标题：

```yml next/_config.yml
toc:
  wrap: true
```
<!-- endtab -->
<!-- tab expand_all -->
如果你希望将目录中所有层级都显示出来，而不是只显示激活部分，可以将`toc.expand_all`的值设为 true：

```yml next/_config.yml
toc:
  expand_all: true
```
<!-- endtab -->
<!-- tab max_depth -->
默认生成的最大目录层级深度为 6，你也可以将`toc.max_depth`修改为其他数值：

```yml next/_config.yml
toc:
  max_depth: 3
```
<!-- endtab -->
{%endtabs%}
