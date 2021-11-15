---
title: 外部库
date: 2021-10-25 14:37:00
---

### PJAX

[Pjax](https://github.com/MoOx/pjax) 是一个独立的 JavaScript 模块，它使用 AJAX（XmlHttpRequest）和 pushState() 来提供快速的浏览体验。它彻底改变标准网站的用户体验，让用户感觉他们正在浏览应用程序，特别是对于那些低带宽的用户而言。

{%note warning%}
请在你的文章中使用图片的绝对路径或 Hexo 的`asset_img`标签，否则在 Pjax 刷新时图片可能无法加载。
{%endnote%}

你可以通过将 {%label primary@主题配置文件%} 中的`pjax`值设为 true 来启用它：

```yml next/_config.yml
# 在你的网站上轻松启用快速 Ajax 导航。
# 更多信息：https://github.com/next-theme/pjax
pjax: true
```

### Fancybox

NexT 支持 fancybox 插件，它是一款基于 jQuery 的弹出框脚本插件，用于显示图片、视频等。

你可以通过将 {%label primary@主题配置文件%} 中的`fancybox`值设为 true 来启用它：

```yml next/_config.yml
fancybox: true
```

### Medium Zoom

[Medium Zoom](https://github.com/francoischalifour/medium-zoom) 是一个 JavaScript 库，用于像 Medium 那样缩放图片。

你可以通过将 {%label primary@主题配置文件%} 中的`mediumzoom`值设为 true 来启用它：

```yml next/_config.yml
mediumzoom: true
```

{%note danger%}
不要同时开启`fancybox`和`mediumzoom`。
{%endnote%}

### 懒加载

[Lozad.js](https://github.com/ApoorvSaxena/lozad.js) 是 Vanilla JavaScript 框架中的一款懒加载插件，它会延迟加载长网页中的图像，不会加载视口之外的图像。这与图像预加载相反。

你可以通过将 {%label primary@主题配置文件%} 中的`lazyload`值设为 true 来启用它：

```yml next/_config.yml
# 用于懒加载图片的 Vanilla JavaScript 库插件。
lazyload: true
```

在网站根目录下执行`hexo clean`命令，确保`lazyload`可以正确启用或禁用。

### 盘谷之白

[pangu.js](https://github.com/vinta/pangu.js) 会在页面上的所有汉字和半角英文、数字、符号之间自动插入一个空格。

你可以通过将 {%label primary@主题配置文件%} 中的`pangu`值设为 true 来启用它：

```yml next/_config.yml
pangu: true
```

### 快速链接

Quicklink 是一个 JavaScript 插件，通过在空闲时间预读取窗口中的链接，以加快后续页面的加载。

你可以通过将 {%label primary@主题配置文件%} 中的`quicklink.enable`值设为 true 来启用它：

```yml next/_config.yml
...
quicklink:
  enable: true
  home: true
  archive: true
  delay: true
  timeout: 3000
  priority: true
...
```

### 动画效果

NexT 默认启用 Anime.js 和 Animate.css 支持的动画效果，所以会等待 JavaScript 加载后显示内容。

如果你需要快速加载内容，你可以将 {%label primary@主题配置文件%} 中的`motion.enable`设置为 false 来禁用动画效果。

你还可以在`motion`选项下设置合适的值来满足你的需求。在 [此处](https://theme-next.js.org/animate/) 预览所有过渡动画效果。

```yml next/_config.yml
# 动画效果使用 Animate.css。
# 更多信息：https://animate.style
motion:
  enable: true
  async: false
  transition:
    # 所有可用的动画效果：https://theme-next.js.org/animate/
    post_block: fadeIn
    post_header: fadeInDown
    post_body: fadeInDown
    coll_header: fadeInLeft
    # 仅 Pisces | Gemini 有效。
    sidebar: fadeInUp
```

### 进程条

[Pace](https://codebyzach.github.io/pace/) 将自动监控你的 Ajax 请求、事件循环延迟、文档就绪状态和页面上的元素，从而来决定进程。

你可以将 {%label primary@主题配置文件%} 中的`pace.enable`设置为 true 来显示进程条：

```yml next/_config.yml
pace:
  enable: true
```

可以通过修改`pace.color`的值来改变进程条的颜色：

```yml next/_config.yml
pace:
  color: orange
```

Pace 包含了许多主题，NexT 默认采用 minimal 主题。你可以通过设置`pace.theme`的值来更改主题：

```yml next/_config.yml
pace:
  theme: minimal
```

### 背景彩带

[canvas-ribbon.js](https://github.com/hustcc/ribbon.js) 是一款背景彩带插件。你可以将 {%label primary@主题配置文件%} 中的`canvas_ribbon`设置为 true 来启用它。你还可以编辑`canvas_ribbon`中的其他值来配置彩带。

```yml next/_config.yml
canvas_ribbon:
  enable: true
  size: 300
  alpha: 0.6
  zIndex: -1
```

- size：彩带的宽度。
- alpha：彩带的透明度。
- zIndex：彩带的显示层级。
