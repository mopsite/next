---
title: PDF
date: 2021-10-25 16:42:36
---

### 设置

```yml next/_config.yml
pdf:
  enable: true
  # 默认高度
  height: 500px
```

### 用法

```
{% pdf url [height] %}
```

- url：PDF 文件的链接（绝对路径）。
- [height]：可选参数。显示 PDF 的元素的高度，例如 800px。

{%note warning%}
加载 pdf.js 或 pdf 文件时，可能会被 CORS（Cross-origin resource sharing 跨域资源共享）标准阻止。如果你想从其他站点加载资源，确保在服务器端的 header 中正确设置了 Access-Control-Allow-Origin。也可以参阅 [Access-Control-Allow-Origin - HTTP | MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin)。
{%endnote%}

### 示例

```
{% pdf https://example.com/sample.pdf %}
{% pdf /path/to/your/file.pdf 600px %}
```
