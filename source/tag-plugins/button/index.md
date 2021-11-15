---
title: 按钮
date: 2021-10-25 16:40:44
---

### 用法

```
{% button url, text, icon [class], [title] %}

<!-- 标签别名 -->
{% btn url, text, icon [class], [title] %}
```

- url：绝对或相对路径。
- text：按钮文字。如果为指定 icon，则为必需。
- icon：Font Awesome 图标名称。如果为指定 text，则为必需。
- [class]：可选参数。Font Awesome 的类（fa-fw、fa-lg、fa-2x、fa-3x、fa-4x、fa-5x）。
- [title]：可选参数。鼠标悬停时的提示文字。

### 示例

```
{% button #, Text %}
```

{% button #, Text %}

#### 带有文字和标题的按钮

```
{% btn #, Text & Title,, Title %}
```

{% btn #, Text & Title,, Title %}

#### 图标按钮

```
{% btn #,, home fa-5x %}
{% btn #,, home fa-4x %}
{% btn #,, home fa-3x %}
{% btn #,, home fa-2x %}
{% btn #,, home fa-lg %}
{% btn #,, home %}
```

{% btn #,, home fa-5x %}
{% btn #,, home fa-4x %}
{% btn #,, home fa-3x %}
{% btn #,, home fa-2x %}
{% btn #,, home fa-lg %}
{% btn #,, home %}

#### 带有图标和文字的按钮

```
{% btn #, Text & Icon, home fa-fw %}
```

{% btn #, Text & Icon, home fa-fw %}
