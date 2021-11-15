---
title: 自定义文件
date: 2021-10-25 19:41:04
---

[Pull Request #868](https://github.com/theme-next/hexo-theme-next/pull/868) 调整了自定义布局或样式的方式，取消了原主题目录下的自定义文件（如 _custom/custom.styl），只保留了在 {%label primary@主题配置文件%} 中指定自定义文件的方式。

将自定义文件与主题文件分开是一个很好的做法，这样你就可以在不修改主题源代码的情况下添加自定义内容，并能避免由于`git merge`引起的冲突。

与 [数据文件](https://mopsite.gitee.io/hexo/usage/data-files/) 一样，你可以将所有自定义布局或样式放在特定位置（例如，hexo/source/_data），并将 {%label primary@主题配置文件%} 中`custom_file_path`的内容注释掉。

### 修改布局示例

#### Live2d 部件

编辑站点根目录中的 source/_data/head.njk 文件，并添加以下内容：

```html hexo/source/_data/head.njk
<script src="https://cdn.jsdelivr.net/gh/stevenjoezhang/live2d-widget@latest/autoload.js"></script>
```

然后取消 {%label primary@主题配置文件%} 中`custom_file_path`选项下的`head`注释：

```yml next/_config.yml
custom_file_path:
  head: source/_data/head.njk
```

#### 侧边栏中的 Netlify 标志

编辑网站根目录中的 source/_data/sidebar.njk 文件，并添加以下内容：

```html hexo/source/_data/sidebar.njk
<div class="cc-license animated" itemprop="sponsor">
  <a href="https://www.netlify.com" class="cc-opacity" title="Deploy with Netlify → https://www.netlify.com" target="_blank"><img width="80" src="https://www.netlify.com/img/global/badges/netlify-dark.svg" alt="Netlify"></a>
</div>
```

然后取消 {%label primary@主题配置文件%} 中`custom_file_path`选项下的`sidebar`注释：

```yml next/_config.yml
custom_file_path:
  head: source/_data/sidebar.njk
```

### 修改样式示例

#### 如何更改内容宽度

NexT 默认具有以下内容宽度的设置：

- 700px：当屏幕宽度小于 1200px 时。
- 800px：当屏幕宽度大于等于 1200px 时。
- 900px：当屏幕宽度大于等于 1600px 时。
- 在移动设备或平板中，将使用响应式宽度。

你可以通过编辑网站根目录中的 source/_data/_variables.styl 文件，并在其中添加变量，来覆盖默认的内容宽度。

{%tabs width%}
<!-- tab Muse / Mist -->
Muse 和 Mist 的默认变量都位于 source/css/_variables/base.styl 中，并定义为：

```styl next/source/css/_variables/base.styl
$content-desktop         = 700px
$content-desktop-large   = 800px
$content-desktop-largest = 900px
```

例如，你想要更宽的内容宽度，可以使用百分比重新定义此变量：

```styl hexo/source/_data/variables.styl
$content-desktop         = 90%
$content-desktop-large   = 90%
$content-desktop-largest = 90%
```
<!-- endtab -->
<!-- tab Pisces / Gemini -->
Pisces 和 Gemini 的默认变量都位于 source/css/_variables/Pisces.styl 中，并定义为：

```styl next/source/css/_variables/Pisces.styl
$content-desktop         = 'calc(100% - %s)' % unit($content-desktop-padding / 2, 'px')
$content-desktop-large   = 1160px
$content-desktop-largest = 73%
```

`$content-desktop`默认自动响应，它也可以修改为任何值，但为了获得更好的阅读性，建议保持不变。

{%note info%}
实际上 Gemini 只是一个在风格上做了些修改的 Pisces 分支。因此，几乎所有的 Pisces 变量都会导入到 Gemini 中。如果你想为 Pisces 和 Gemini 添加变量或样式，只需在 Pisces.styl 中修改即可。
{%endnote%}
<!-- endtab -->
{%endtabs%}

然后取消 {%label primary@主题配置文件%} 中`custom_file_path`选项下的`variable`注释：

```yml next/_config.yml
custom_file_path:
  variable: source/_data/variables.styl
```

#### 移动端隐藏侧边栏

在网站根目录中编辑 source/_data/styles.styl 文件，并添加以下样式：

```styl hexo/source/_data/styles.styl
+tablet-mobile() {
  .sidebar-toggle, .sidebar {
    display: none;
  }
}
```

然后取消 {%label primary@主题配置文件%} 中`custom_file_path`选项下的`style`注释：

```yml next/_config.yml
custom_file_path:
  style: source/_data/styles.styl
```

#### 隐藏归档页中的「继续努力」

在网站根目录中编辑 source/_data/styles.styl 文件，并添加以下样式：

```styl hexo/source/_data/styles.styl
.archive .collection-title {
  display: none !important;
}
```

然后取消 {%label primary@主题配置文件%} 中`custom_file_path`选项下的`style`注释：

```yml next/_config.yml
custom_file_path:
  style: source/_data/styles.styl
```


