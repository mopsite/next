---
title: 数学公式
date: 2021-10-25 14:35:18
---

### 设置

```yml next/_config.yml
# 支持数学公式渲染
math:
  # 默认（false）按需加载 mathjax / katex 脚本。
  # 当文章的 Front-matter 中含有 `mathjax: true` 选项时渲染页面。
  # 如果改为 true，将会在所有的页面中加载 mathjax / katex 脚本。
  every_page: false

  mathjax:
    enable: true
    # 可用值：none | ams | all
    tags: none

  katex:
    enable: false
    # 参见：https://github.com/KaTeX/KaTeX/tree/master/contrib/copy-tex
    copy_tex: false
```

`every_page`选项控制是否在每一页都呈现数学公式。

- false → 按需处理。数学公式只会呈现在那些在 Front-matter 中设置了`mathjax: true`的文章内。
- true → 在每一页中处理。即使在这一页中没有数学公式。

`mathjax`和`katex`用于设置渲染引擎。请阅读下面的详细文档。

### 渲染引擎

目前，NexT 提供了两个渲染引擎来显示数学公式：[MathJax](https://www.mathjax.org/) 和 [KaTeX](https://katex.org/)。

- MathJax 是一个 JavaScript 数学显示引擎，适用于所有浏览器。它在输入和输出上高度模块化。使用 MathML、TeX 和 ASCIImath 作为输入并生成 HTML + CSS，SVG 或者 MathML 作为输出。
- 与 MathJax 相比，KaTeX 是一个更快的数学渲染引擎。它可以在没有 JavaScript 的情况下存在。但是，KaTeX 支持的功能比 MathJax 少。这是 KaTeX 支持的 [函数列表](https://katex.org/docs/supported.html)。

首先，你必须选择一个渲染引擎并在 {%label primary@主题配置文件%} 中开启`enable`选项。然后，你必须安装相应的 Hexo 渲染器才能完全支持数学公式的显示——只是开启`enable`可能无法正确看到显示的公式。

{%tabs math%}
<!-- tab MathJax -->
如果你使用 MathJax 来渲染数学公式，推荐使用 [hexo-renderer-pandoc](https://github.com/wzpan/hexo-renderer-pandoc)，因为它可以完美处理 Markdown 文档中的数学公式。

首先，在 {%label primary@主题配置文件%} 中将`mathjax`设置为渲染引擎：

```yml next/_config.yml
math:
  ...
  mathjax:
    enable: true
```

然后，你需要写在原来的渲染器 hexo-renderer-marked，然后安装 hexo-renderer-pandoc：

```
npm un hexo-renderer-marked
npm i hexo-renderer-pandoc
```

hexo-renderer-pandoc 需要 [pandoc](https://github.com/jgm/pandoc)，这里是 [如何安装 pandoc](https://github.com/jgm/pandoc/blob/master/INSTALL.md)。

MathJax 自动加载所有扩展。例如，mhchem 是一个轻松编写漂亮 [化学方程式](https://mhchem.github.io/MathJax-mhchem/) 的工具。
<!-- endtab -->
<!-- tab KaTeX -->
如果你使用 KaTeX 渲染数学公式，你可以选择以下 Markdown 渲染器之一：

- [hexo-renderer-markdown-it](https://github.com/hexojs/hexo-renderer-markdown-it)
- [hexo-renderer-markdown-it-plus](https://github.com/CHENXCHEN/hexo-renderer-markdown-it-plus)

首先，在 {%label primary@主题配置文件%} 中将`katex`设置为渲染引擎：

```yml next/_config.yml
math:
  ...
  katex:
    enable: true
```

然后，你需要卸载原来的渲染器 hexo-renderer-marked，并安装上述渲染器中的任意一个：

```
npm un hexo-renderer-mark
npm i hexo-renderer-markdown-it-plus
```

如果使用 hexo-renderer-markdown-it，还需要安装 markdown-it-katex：

```
npm un hexo-renderer-mark
npm in hexo-renderer-markdown-it
npm i markdown-it-katex
```

并且需要在 {%label info@站点配置文件%} 中添加 markdown-it-katex 作为 hexo-renderer-markdown-it 的插件：

```yml hexo/_config.yml
# 配置 hexo-renderer-markdown-it
markdown:
  render:
    html: true
    xhtmlOut: false
    breaks: true
    linkify: true
    typographer: true
    quotes: '“”‘’'
  plugins:
    - markdown-it-katex
```
<!-- endtab -->
{%endtabs%}

{%note warning no-icon%}
设置数学渲染引擎或者安装、卸载 Markdown 渲染器后，请执行`hexo clean`运行标准的 Hexo 生成、部署流程或启动服务器来测试插件是否正常工作：

```
hexo clean && hexo g -d
```

或：

```
hexo clean && hexo s
```
{%endnote%}

{%note danger%}
除了需要的渲染器外，不需要任何其他 Hexo 数学插件，无需手动导入任何 CSS 或 JS 文件。如果你安装了 hexo-math 或 hexo-katex，它们可能会与 NexT 内置的渲染引擎产生冲突。
{%endnote%}
