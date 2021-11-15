---
title: 图片组
date: 2021-10-25 16:41:07
---

### 用法

```
{% grouppicture [number]-[layout] %}{% endgrouppicture %}

<!-- 标签别名 -->
{% gp [number]-[layout] %}{% endgp %}
```

- [number]：可选参数。要添加到图片组中的图片总数量。
- [layout]：可选参数。布局的索引号，可以根据下图获取。例如，如果要将第二个布局应用于 4 张图片，则使用`{% grouppicture 4-2 %} {% endgrouppicture %}`。

![](../../images/next03.png)
![](../../images/next04.png)

### 示例

```
{% grouppicture 6-3 %}
![](/images/next.svg)
![](/images/next.svg)
![](/images/next.svg)
![](/images/next.svg)
![](/images/next.svg)
![](/images/next.svg)
{% endgrouppicture %}
```

{% grouppicture 6-3 %}
![](../../images/next05.svg)
![](../../images/next05.svg)
![](../../images/next05.svg)
![](../../images/next05.svg)
![](../../images/next05.svg)
![](../../images/next05.svg)
{% endgrouppicture %}

```
{% gp 5-2 %}
![](/images/next.svg)
![](/images/next.svg)
![](/images/next.svg)
![](/images/next.svg)
![](/images/next.svg)
{% endgp %}
```

{% gp 5-2 %}
![](../../images/next05.svg)
![](../../images/next05.svg)
![](../../images/next05.svg)
![](../../images/next05.svg)
![](../../images/next05.svg)
{% endgp %}
