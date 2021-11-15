---
title: 标签插件
date: 2021-10-22 21:07:14
---

标签插件是 Hexo 提供的一种快速生成特定内容的方式。例如，在标准的 Markdown 语法中，我们无法指定图片的大小，这时我们可以使用标签插件来解决。Hexo 内置许多 [标签插件](https://mopsite.gitee.io/hexo/usage/tag-plugins/)，另外，Hexo 也开放接口给主题，使主题能够创建自己的标签。

比如，居中引用（centerquote）标签，会生成一个带上下分割线的引用，同时引用中的文本将自动居中。如果有多行文本，并且每行的长度不同，视觉上会显得不对称，因此建议在引用单行文本时使用，通常作为文章开篇引用或结束语之前的总结引用。其书写格式为：

```
{% centerquote %}Something{% endcenterquote %}

<!-- 标签别名 -->
{% cq %}Something{% endcq %}
```

下面这段代码：

```
{% cq %}Elegant in code, simple in core{% endcq %}
```

将显示为：

{% cq %}Elegant in code, simple in core{% endcq %}

又比如，视频（video）标签的格式为`{% video url%}`，可以用来显示视频：

```
{% video https://example.com/sample.mp4 %}
{% video /path/to/your/video.mp4 %}
```
