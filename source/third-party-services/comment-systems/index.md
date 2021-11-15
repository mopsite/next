---
title: 评论系统
date: 2021-10-25 14:35:57
---

NexT 允许你同时启用多个评论系统。你可以修改以下配置来调整多个评论系统的样式或行为：

```yml next/_config.yml
# 支持多个评论系统
comments:
  # 可用值：tabs | buttons
  style: tabs
  # 选择一个评论系统用于默认显示。
  # 可用值：disqus | disqusjs | changyan | livere | gitalk | utterances | isso
  active:
  # 设置为 true，将会记住评论系统的来访者。
  storage: true
  # 懒加载所有的评论系统。
  lazyload: false
  # 为任意样式修改图标和文本，这里是一些例子。
  nav:
    #disqus:
    #  text: Load Disqus
    #  order: -1
    #gitalk:
    #  order: -2
```

{%note danger%}
NexT 使用 IntersectionObserver 来实现评论懒加载，IE 和大部分 2017 年之前的浏览器不支持。
{%endnote%}

当你启用评论后，所有页面都会自动提供评论服务。如果你想在某页中禁用它，只需在该页面的 Front-matter 中将`comments`设置为 false 即可：

```yml your-post.md
title: All tags
type: "tags"
comments: false
---
```

对于国内用户而言，[畅言](https://changyan.kuaizhan.com/) 是国内最大、操作简单且完全免费的智能评论管理平台，它支持 PC 端和手机端访问。同时，它还拥有多种常用账号登录、三重过滤机制、数据实时统计、数据快速导出等功能。完全满足各大网站用户登录、评论、分享等需求。

1. 创建账户或登录畅言，然后添加你的站点以获取 APP ID 和 APP KEY。
2. 在 {%label primary@主题配置文件%} 的`changyan`选项中，将`enable`值设为 true，并添加`appid`和`appkey`。

```yml next/_config.yml
# 畅言评论系统
changyan:
  enable: false
  appid:
  appkey:
```
