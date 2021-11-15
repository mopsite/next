---
title: 页脚
date: 2021-10-24 12:29:11
---

### 开始时间

NexT 默认在页脚显示当前年份，例如`© 2020`。你可以通过修改 {%label primary@主题配置文件%} 中`footer`的`since`值来显示类似`© 2015 - 2020`的时间间隔。

```yml next/_config.yml
footer:
  since: 2020
```

### 页脚图标

NexT 默认在页脚的年份和版权信息之间显示 <i class="fa fa-heart"></i> 图标。你可以通过修改 {%label primary@主题配置文件%} 中`footer`选项的`icon`值来改变它：

{%tabs footer-icon%}
<!-- tab name -->
页脚的图标名称可以在 Font Awesome 中找到，推荐使用 heart。

```yml next/_config.yml
footer:
  icon:
    name: fa fa-user
```
<!-- endtab -->
<!-- tab animated -->
设置`footer.icon.animated`的值可以启用或关闭页脚图标的动画效果：

```yml next/_config.yml
footer:
  icon:
    animated: false
```
<!-- endtab -->
<!-- tab color -->
设置`footer.icon.color`的值可以修改页脚图标的颜色。请使用十六进制颜色代码，heart 图标推荐使用红色。

```yml next/_config.yml
footer:
  icon:
    color: "#808080"
```
<!-- endtab -->
{%endtabs%}

### 版权名称

NexT 默认显示的`author`名称来自 {%label info@站点配置文件%}，你可以通过修改 {%label primary@主题配置文件%} 来配置它。

```yml next/_config.yml
footer:
  copyright:
```

{%note warning%}
该选项只能定义页脚中的作者姓名，每篇文章末尾的知识共享许可部分中的名称不受影响。
{%endnote%}

### 平台信息

NexT 默认在页脚显示 Hexo 和主题及方案（Scheme）信息，如`Powered by Hexo & NexT.Muse`。你可以通过修改 {%label primary@主题配置文件%} 中的`footer.powered`选项来决定是否显示它。

```yml next/_config.yml
footer:
  powered: true
```

### 备案信息

备案信息面向中国用户。默认情况下，NexT 不会显示备案信息，你可以通过编辑 {%label primary@主题配置文件%} 中的`footer.beian`选项来配置它。

```yml next/_config.yml
footer:
  beian:
    enable: true
    icp: 京ICP备 1234567890号-1
    gongan_id: 1234567890
    gongan_num: 京公网安备 1234567890号
    gongan_icon_url: /uploads/beian.png
```
