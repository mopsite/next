---
title: 其它设置
date: 2021-10-24 12:30:25
---

### 预连接

NexT 支持添加预连接资源提示以建立字体和插件源的前期连接。你可以通过设置 {%label primary@主题配置文件%} 中的`preconnet: true`来启用它：

```yml next/_config.yml
# 字体和插件的预连接。
# 更多信息：https://www.w3.org/TR/resource-hints/#preconnect
preconnect: true
```

### 文本对齐

NexT 支持自定义文章或页面中的文本对齐。

```yml next/_config.yml
# 设置文章中的文本对齐。
text_align:
  # 可用值：start | end | left | right | center | justify | justify-all | match-parent
  desktop: justify
  mobile: justify
```

{%note info%}
其中`match-parent`与 CSS 中的 inherit 属性类似，但是起始方向是根据父级的方向决定的。
{%endnote%}

### 适配移动端

如果你想在宽度较窄的设备上减少内外边距的缩进，可以通过将 {%label primary@主题配置文件%} 中的`mobile_layout_economy`设置为 true 来启用：

```yml next/_config.yml
mobile_layout_economy: true
```

### 主题颜色

NexT 默认使用深黑色作为标题面板的背景色，你可以通过使用十六进制颜色值作为 {%label primary@主题配置文件%} 中`theme_color`的选项值来改变它：

```yml next/_config.yml
theme_color:
  light: "#222"
  dark: "#222"
```

### 滚动条

```yml next/_config.yml
# 覆盖浏览器的默认行为。
body_scrollbar:
  # 将滚动条放置在内容上。
  overlay: false
  # 即使内容没有溢出，也显示滚动条。
  stable: false
```

### 代码块样式

{%tabs code%}
<!-- tab theme -->
NexT 使用 Highlight.js 和 Prism 来支持代码高亮。请先阅读 Hexo 的 [代码高亮](https://mopsite.gitee.io/hexo/customization/syntax-highlight/) 文档，并在 {%label info@站点配置文件%} 中设置。

你可以在 [此处](https://theme-next.js.org/highlight/) 预览所有的代码高亮主题，并通过修改`theme`和`prism`的值来选择你喜欢的高亮样式：

```yml next/_config.yml
codeblock:
  # 代码高亮主题
  # 所有可用的主题：https://theme-next.js.org/highlight/
  theme:
    light: default
    dark: tomorrow-night
  prism:
    light: prism
    dark: prism-dark
```
<!-- endtab -->
<!-- tab copy_button -->
NexT 支持代码块的复制和粘贴功能。你可以通过将 {%label primary@主题配置文件%} 中的`copy_button.enable`值设置为 true 来启用它：

```yml next/_config.yml
codeblock:
  copy_button:
    enable: true
```

使用`style`选项，可以改变复制按钮的样式。`default`（只需留白）、`flat`和`mac`：

```yml next/_config.yml
codeblock:
  copy_button:
    style: flat
```
<!-- endtab -->
{%endtabs%}

### 返回顶部

{%tabs b2t%}
<!-- tab enable -->
将 {%label primary@主题配置文件%} 中的`back2top.enable`设置为 true，可以显示返回顶部按钮：

```yml next/_config.yml
back2top:
  enable: true
```
<!-- endtab -->
<!-- tab sidebar -->
将`back2top`设置为 true，可以将返回顶部按钮放入侧边栏：

```yml next/_config.yml
back2top:
  # 将返回顶部按钮放置到侧边栏。
  sidebar: true
```
<!-- endtab -->
<!-- tab scrollpercent -->
将`back2top.scrollpercent`设置为 true，可以在返回顶部按钮中显示百分比：

```yml next/_config.yml
back2top:
  # 返回顶部按钮中显示滚动百分比。
  scrollpercent: true
```
<!-- endtab -->
{%endtabs%}

### 阅读进度

NexT 支持显示页面滚动时的阅读进度条。你可以在 {%label primary@主题配置文件%} 中将`reading_progress.enable`设置为 true 来启用它：

```yml next/_config.yml
reading_progress:
  enable: true
  # 可用值：eft | right
  start_at: left
  # 可用值：top | bottom
  position: top
  reversed: false
  color: "#37c6c0"
  height: 2px
```

### 书签

书签是一个插件，允许用户保存他们的阅读进度。启用后，用户只需点击页面左上角的书签图标，就可以保存文章的滚动位置，并且当他们下次打开网站时，可以自动恢复每个页面的最后滚动位置。

```yml next/_config.yml
bookmark:
  enable: false
  # 自定义书签颜色。
  color: "#222"
  # 如果设为 auto，在关闭页面或点击书签图标时保存阅读进度。
  # 如果设为 manual，只能通过点击书签图标来保存。
  save: auto
```

### GitHub 横幅

NexT 可以在右上角提供「在 GitHub 关注我」的横幅：

```yml next/_config.yml
# 右上角GitHub横幅。
github_banner:
  enable: true
  permalink: https://github.com/yourname
  title: Follow me on GitHub
```

其中`premalink`是指定的链接，必须有完整的 url 路径。`title`是鼠标悬在横幅上方浮时弹出的标签内容。

### 自定义字体

NexT 为你提供了 5 种特定的字体设置，它们是：

- global：整个站点使用的字体。
- title：站点标题使用的字体。
- headings：文章标题使用的字体（h1 - h6）。
- posts：文章使用的字体。
- codes：文章内代码块使用的字体。

各项所指定的字体将作为首选字体。当它们不可用时，会自动退回到 NexT 设定的基础字体组：

- 非代码字体：退回到`"PingFang SC", "Microsoft YaHei", sans-serif`。
- 代码字体：退回到`consolas, Menlo, "PingFang SC", "Microsoft YaHei", monospac`。

另外，每一项都有一个额外的`external`属性，该属性用来控制是否使用外链字体库，可以方便你设定那些已经安装在系统中的字体，减少不必要的请求。

{%note info no-icon%}
NexT 支持通过设定`font.host`选项来自定义字体库的 url，以解决在某些国家或地区使用 [Google Fonts API](https://fonts.google.com/) 不稳定的问题。

另外，对于某些网站的请求，Google Fonts 会返回 403，这时候就需要使用`fonf.host`设置镜像站点了。

相关问题：[#613](https://github.com/theme-next/hexo-theme-next/issues/613)，[#1333](https://github.com/theme-next/hexo-theme-next/issues/1333)。
{%endnote%}

```yml next/_config.yml
font:
  # 是否使用自定义字体族。
  # 相关选项： external 和 family。
  enable: true

  # 字体镜像站点，例如 https://fonts.googleapis.com （默认）。
  host:

  # 字体选项：
  # external: true 将从上面的 host 加载字体系列。
  # family: Times New Roman 无需引号包裹。
  # size: x.x 使用 em 为单位，默认是 1（16px）。

  # 全局字体作用于body中的所有元素。
  global:
    external: true
    family: Monda
    size: 1.125

  # 站点标题的字体设定。
  title:
    external: true
    family: Lobster Two
    size:

  # 文章标题的字体设定。
  headings:
    external: true
    family: Amita
    size:

  # 文章内的字体设定。
  posts:
    external: true
    family: Montserrat

  # 代码字体设定。
  codes:
    external: true
    family: PT Mono
```

你可以为每个选项应用多个字体系列，这对经常同时写中文和英文的人来说尤其有用：

```yml next/_config.yml
font:
  ...
  title:
    external: true
    family: Roboto Slab, Noto Serif SC
    size:
```

如果你仍需要更多的自定义，以下更改将覆盖字体自定义功能。编辑站点根目录中的 source/_data/variables.styl 文件，并添加两个变量：

```
// Title Font, set it to font family you want.
$font-family-headings = Georgia, sans

// Set it to font family you want.
$font-family-base = "Microsoft YaHei", Verdana, sans-serif

// Code Font.
$code-font-family = "Input Mono", "PT Mono", Consolas, Monaco, Menlo, monospace

// Font size of articles.
$font-size-base = 16px

// Font size of table and code.
$table-font-size = 13px
```

然后取消 {%label primary@主题配置文件%} 中`custom_file_path`下的`variable`注释。
