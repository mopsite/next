---
title: 便签
date: 2021-10-25 16:42:21
---

### 设置

```yml next/_config.yml
note:
  # 便签标签样式：
  #  - simple    默认值。bs-callout 旧警告样式。
  #  - modern    bs-callout 新（v2-v3）新警告样式。
  #  - flat      带有背景的扁平标注样式。
  #  - disabled  禁用所有的 CSS 样式导入。
  style: simple
  icons: false
  light_bg_offset: 0
```

### 用法

```
{% note [class] [no-icon] [summary] %}
任意内容（也支持行内标签）。
{% endnote %}
```

- [class]：可选参数。支持的值有：default、primary、success、info、warning 和 danger。
- [no-icon]：可选参数。在便签中禁用图标。
- [summary]：可选参数。便签的摘要。

### 示例

{% note %}
#### 无定义样式
Welcome to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}

```
{% note %}
#### 无定义样式
Welcome to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}
```

{% note default %}
#### Default 样式
Welcome to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}

```
{% note default %}
#### Default 样式
Welcome to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}
```

{% note primary %}
#### Primary 样式
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}

```
{% note primary %}
#### Primary 样式
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}
```

{% note info %}
#### Info 样式
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}

```
{% note info %}
#### Info 样式
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}
```

{% note success %}
#### Success 样式
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}

```
{% note success %}
#### Success 样式
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}
```

{% note warning %}
#### Warning 样式
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}

```
{% note warning %}
#### Warning 样式
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}
```

{% note danger %}
#### Danger 样式
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}

```
{% note danger %}
#### Danger 样式
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}
```

{% note info no-icon %}
#### 无图标便签
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}

```
{% note info no-icon %}
#### 无图标便签
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}
```

{% note primary 这是一条摘要 %}
#### 详情和摘要
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}

```
{% note primary 这是一条摘要 %}
#### 详情和摘要
**Welcome** to [Hexo!](https://mopsite.gitee.io/hexo)
{% endnote %}
```







