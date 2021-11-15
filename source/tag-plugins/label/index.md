---
title: 标记
date: 2021-10-25 16:41:25
---

### 用法

```
{% label [class]@text %}
```

- [class]：可选参数。支持的值有：default、primary、success、info、warning 和 danger。如果不指定，将使用浏览器的默认样式，不同浏览器可能会有所不同。
- text：标记文本。`@text`前面带不带空格都可以。例如`success @text`和`success@text`效果一样。

### 示例

- 这是 {% label default@default %} 标记。
  ```
  {% label default@default %}
  ```
- 这是没有指定 class 的 {% label @默认 %} 标记。
  ```
  {% label @默认 %}
  ```
- 这是 {% label primary@primary %} 标记。
  ```
  {% label primary@primary %}
  ```
- 这是 {% label success@success %} 标记。
  ```
  {% label success@success %}
  ```
- 这是 {% label info@info %} 标记。
  ```
  {% label info@info %}
  ```
- 这是 {% label warning@warning %} 标记。
  ```
  {% label warning@warning %}
  ```
- 这是 {% label danger@danger %} 标记。
  ```
  {% label danger@danger %}
  ```
