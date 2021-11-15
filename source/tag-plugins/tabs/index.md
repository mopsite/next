---
title: 选项卡
date: 2021-10-25 16:42:52
---

### 设置

```yml next/_config.yml
tabs:
  # 可以切换内容的选项卡。
  sticky: false
  transition:
    tabs: false
    labels: true
```

### 用法

```
{% tabs Unique name, [index] %}
<!-- tab [Tab caption] [@icon] -->
任意内容（也支持行内标签）。
<!-- endtab -->
{% endtabs %}
```

- Unique name：标签块的唯一名称，不能带有逗号。将用作每个标签的 id 及其索引号的前缀。如果名称中含有空格，将会在 id 中把空格替换为短横线。仅对文章或页面的当前链接必须是唯一的。
- [index]：可选参数。激活选项卡的索引号。如果未指定，默认选中第一个选项卡。如果设置为 -1，则不会选中任何选项卡。
- [Tab caption]：可选参数。当前选项卡的标题。如果未指定，则将后缀带有索引号的 Unique name 作为标题。如果没有指定标题，而是指定了图标，标题将为空。
- [@icon]：可选参数。Font Awesome 图标名称。与其他参数不受空格影响，例如`Tap caption @icon`和`Tab caption@icon`相同。

### 示例

#### 默认选项卡标题

```
{% tabs First unique name %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```

{% tabs First unique name %}

<!-- tab -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}

#### 默认选中第三个选项卡

```
{% tabs Second unique name, 3 %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```

{% tabs Second unique name, 3 %}

<!-- tab -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}

#### 默认不选中任何选项卡

```
{% tabs Third unique name, -1 %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```

{% tabs Third unique name, -1 %}

<!-- tab -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}

#### 自定义选项卡标题

```
{% tabs Fourth unique name %}
<!-- tab Solution 1 -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab Solution 2 -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab Solution 3 -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```

{% tabs Fourth unique name %}

<!-- tab Solution 1 -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab Solution 2 -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab Solution 3 -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}

#### 仅有图标的选项卡

```
{% tabs Fifth unique name %}
<!-- tab @text-width -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab @font -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab @bold -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```

{% tabs Fifth unique name %}

<!-- tab @text-width -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab @font -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab @bold -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}

#### 选项卡的锚点链接

```
Permalink for > [Tab one](#tab-one).
Permalink for > [Tab one 1](#tab-one-1).
Permalink for > [Tab one 2](#tab-one-2).
Permalink for > [Tab one 3](#tab-one-3).

Permalink for > [Tab two](#tab-two).
Permalink for > [Tab two 1](#tab-two-1).
Permalink for > [Tab two 2](#tab-two-2).
Permalink for > [Tab two 3](#tab-two-3).

{% tabs Tab one %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}

{% tabs Tab two %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```

Permalink for > [Tab one](#tab-one).
Permalink for > [Tab one 1](#tab-one-1).
Permalink for > [Tab one 2](#tab-one-2).
Permalink for > [Tab one 3](#tab-one-3).

Permalink for > [Tab two](#tab-two).
Permalink for > [Tab two 1](#tab-two-1).
Permalink for > [Tab two 2](#tab-two-2).
Permalink for > [Tab two 3](#tab-two-3).

{% tabs Tab one %}

<!-- tab -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}

{% tabs Tab two %}

<!-- tab -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}
