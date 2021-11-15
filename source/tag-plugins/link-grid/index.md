---
title: 链接网格
date: 2021-10-25 16:41:45
---

### 用法

```
{% linkgrid [image] [delimiter] [comment] %}{% endlinkgrid %}

<!-- 标签别名 -->
{% lg [image] [delimiter] [comment] %}{% endlg %}
```

- [image]：可选参数。默认图片链接。
- [delimite]：可选参数。每行的分隔符。
- [comment]：可选参数。注释该行的符号。

### 示例

```
{% linkgrid %}
Theme NexT | / | 优雅且强大的 Hexo 主题 | /images/logo.svg
Theme NexT | / | 优雅且强大的 Hexo 主题 | /images/logo.svg
Theme NexT | / | 优雅且强大的 Hexo 主题 | /images/logo.svg
Theme NexT | / | 优雅且强大的 Hexo 主题 | /images/logo.svg
{% endlinkgrid %}
```

{% linkgrid %}
Theme NexT | / | 优雅且强大的 Hexo 主题 | ../../images/logo.svg
Theme NexT | / | 优雅且强大的 Hexo 主题 | ../../images/logo.svg
Theme NexT | / | 优雅且强大的 Hexo 主题 | ../../images/logo.svg
Theme NexT | / | 优雅且强大的 Hexo 主题 | ../../images/logo.svg
{% endlinkgrid %}

```
{% lg /images/logo.svg %}
Theme NexT | / | 优雅且强大的 Hexo 主题
Theme NexT | / | 优雅且强大的 Hexo 主题
Theme NexT | / | 优雅且强大的 Hexo 主题
{% endlg %}
```

{% lg ../../images/logo.svg %}
Theme NexT | / | 优雅且强大的 Hexo 主题
Theme NexT | / | 优雅且强大的 Hexo 主题
Theme NexT | / | 优雅且强大的 Hexo 主题
{% endlg %}
