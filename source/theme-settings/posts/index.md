---
title: 文章
date: 2021-10-24 12:29:29
---

### 文章摘要

通常需要在主页中显示文章的部分内容，然后提供指向完整文章的链接。NexT 提供了两种方法来控制文章在主页中的显示方式，换句话说，你可以使用以下方式来显示文章摘要和阅读更多按钮。

{%tabs preamble%}
<!-- tab Tag more -->
在文章中手动插入`<!-- more -->`标签，该标签之后的内容将会作为文章摘要显示在主页中；该标签之后的内容将会替换为阅读更多按钮。这也是 Hexo 的推荐用法。
<!-- endtab -->
<!-- tab excerpt_description -->
如果你在文章的 Front-matter 部分中设置了`descritption`，并将它的值设置为了你的文章摘要，NexT 会将该值作为主页中的文章摘要。如果没有设置该值，则文章的全部内容都将作为文章摘要。

你可以将 {%label primary@主题配置文件%} 中的`excerpt_description`值修改为 false 来禁用它。

```yml next/_config.yml
excerpt_description: true
```
<!-- endtab -->
{%endtabs%}

{%note info%}
推荐使用`<!-- more -->`（第一种方式），它不仅可以更好地控制你想要展示的内容，还可以让 Hexo 插件轻松使用它。
{%endnote%}

### 头部信息

NexT 支持显示文章创建日期、修改日期及分类等头部信息。

{%tabs meta%}
<!-- tab item_text -->
默认情况下，NexT 显示文章的头部信息。你可以通过将`post_meta.item_text`选项设置为 false 来禁用它：

```yml next/_config.yml
post_meta:
  item_text: true
```
<!-- endtab -->
<!-- tab created_at -->
默认情况下，NexT 在文章的头部信息中显示文章的创建日期。你可以通过将`post_meta.created_at`选项设置为 false 来禁用它：

```yml next/_config.yml
post_meta:
  created_at: true
```
<!-- endtab -->
<!-- tab updated_at -->
{%note warning%}
确保你在 {%label info@站点配置文件%} 中正确设置了`use_date_updated`和`updated_option`，否则该选项不会生效。详见 [日期-时间格式](https://mopsite.gitee.io/hexo/started/configuration/#日期-时间格式)。
{%endnote%}

默认情况下，NexT 在文章的头部信息中显示文章的更新（编辑）日期。你可以通过将`post_meta.updated_at.enable`选项设置为 false 来禁用它：

```yml next/_config.yml
post_meta:
  updated_at:
    enable: true
```

如果更新日期和创建日期相同，则会显示编辑时间。你可以通过将`post_meta.updated_at.another_day`设置为 false 来禁用它：

- 如果为 true，则仅在更新日期和创建日期不同时，才显示更新日期。
- 如果在文章创建的同一天编辑，编辑时间将显示在创建时间的`title`属性中。
- 如果为 false，而编辑时间和创建时间为同一天，则只显示编辑时间。

```yml next/_config.yml
post_meta:
  updated_at:
    another_day: true
```
<!-- endtab -->
<!-- tab categories -->
默认情况下，NexT 在文章的头部信息中显示文章的分类。你可以通过将`post_meta.categories`选项设置为 false 来禁用它：

```yml next/_config.yml
post_meta:
  categories: true
```
<!-- endtab -->
{%endtabs%}

### 文章字数

首先，在站点根目录下执行以下命令安装 hexo-word-counter 插件：

```
npm install hexo-word-counter
hexo clean
```

然后在 {%label info@站点配置文件%} 中通过以下任意选项来激活该插件：

{%tabs word-counter%}
<!-- tab symbols -->
NexT 默认在文章头部信息中显示文章字数。你可以通过在 {%label info@站点配置文件%} 中将`symbols_count_time.symbols`设置为 false 来禁用它：

```yml hexo/_config.yml
symbols_count_time:
  symbols: true
```
<!-- endtab -->
<!-- tab time -->
NexT 默认在文章头部信息中显示文章的大致阅读时间。你可以通过在 {%label info@站点配置文件%} 中将`symbols_count_time.time`设置为 false 来禁用它：

```yml hexo/_config.yml
symbols_count_time:
  time: true
```
<!-- endtab -->
<!-- tab total_symbols -->
NexT 默认在文章头部信息中显示所有文章的字数。你可以通过在 {%label info@站点配置文件%} 中将`symbols_count_time.total_symbls`设置为 false 来禁用它：

```yml hexo/_config.yml
symbols_count_time:
  total_symbls: true
```
<!-- endtab -->
<!-- tab total_time -->
NexT 默认在文章头部信息中显示所有文章的大致阅读时间。你可以通过在 {%label info@站点配置文件%} 中将`symbols_count_time.total_time`设置为 false 来禁用它：

```yml hexo/_config.yml
symbols_count_time:
  total_time: true
```
<!-- endtab -->
<!-- tab awl -->
`awl`表示平均单词长度（单词中的字符数），相关信息你可以在 [这里](https://charactercounttool.com/) 查看。

```yml next/_config.yml
symbols_count_time:
  awl: 4
```
<!-- endtab -->
<!-- tab wpm -->
`wpm`表示每分钟的平均字数，相关信息你可以在 [这里](https://wordcounter.net/) 查看。

```yml next/_config.yml
symbols_count_time:
  wpm: 275
```
<!-- endtab -->
{%endtabs%}

启用插件后，你可以在 {%label primary@主题配置文件%} 的`symbols_count_time`中调整部分选项：

{%tabs count_time%}
<!-- tab separated_meta -->
NexT 默认将文章字数和估计阅读时间分别显示在单独的行。你可以通过将`symbols_count_time.separated_meta`修改为 false 来显示为一行。

```yml next/_config.yml
symbols_count_time:
  separated_meta: true
```
<!-- endtab -->
<!-- tab item_text_total -->
NexT 默认不会在页脚中显示字数和估计阅读时间，你可以将`symbols_count_time.item_text_total`修改为 false 来启用它：

```yml next/_config.yml
symbols_count_time:
  item_text_total: true
```
<!-- endtab -->
{%endtabs%}

### 标签图标

默认情况下，文章底部的标签左边会有一个`#`符号。如果你喜欢图标而不是符号，可以像下面这样配置 {%label primary@主题配置文件%}：

```yml next/_config.yml
tag_icon: true
```

### 打赏功能

越来越多的平台（微信公众平台、简书、知乎等）支持打赏功能。为了抓住付费阅读的趋势，NexT 增加了打赏功能，支持微信支付、支付宝和比特币。你只需要：

1. 将你的微信、支付宝、比特币的收款码图像放到 source/images 目录下，或者上传到云端以获取绝对的 HTTP 地址。
2. 在 {%label primary@主题配置文件%} 中设置所需的值：
  ```yml next/_config.yml
  reward_settings:
    # 如果为 true，打赏功能按钮将会默认出现在每篇文章。
    enable: true
    animation: false
    #comment: Buy me a coffee

  reward:
    wechatpay: /images/wechatpay.png
    alipay: /images/alipay.png
    bitcoin: /images/bitcoin.png
  ```

### 关注我

```yml next/_config.yml
# 通过 Telegram Channel，Twitter 等订阅。
# 格式：`Key: permalink || icon` (Font Awesome)
follow_me:
  #Twitter: https://twitter.com/username || fab fa-twitter
  #Telegram: https://t.me/channel_name || fab fa-telegram
  #WeChat: /images/wechat_channel.jpg || fab fa-weixin
  #RSS: /atom.xml || fa fa-rss
```

### 相关文章

NexT 根据 [hexo-related-popular-posts](https://github.com/tea3/hexo-related-popular-posts) 支持相关文章的功能。

首先，在网站根目录下执行以下命令安装 hexo-related-popular-posts：

```
npm install hexo-related-popular-posts
hexo clean
```

安装完成后，可以在 {%label primary@主题配置文件%} 中设置相关功能：

{%tabs related-popular-posts%}
<!-- tab enable -->
你可以通过将`related_posts.enable`的值设置为 true 来启用它：

```yml next/_config.yml
related_posts:
  enable: true
```
<!-- endtab -->
<!-- tab title -->
NexT 默认使用相关文章的标题来显示，你可以通过编辑`related_posts.title`的值来修改它：

```yml next/_config.yml
related_posts:
  title:
```
<!-- endtab -->
<!-- tab display_in_home -->
NexT 默认不会在主页显示相关文章，你可以通过将`related_posts.display_in_home`的值修改为 true 来启用它：

```yml next/_config.yml
related_posts:
  display_in_home: true
```
<!-- endtab -->
<!-- tab params -->
NexT 默认最多显示 5 个不带日期、图片和摘录的相关文章标题。你可以通过`related_posts.params`来修改：

- 列表的最大数量：
  ```yml next/_config.yml
  related_posts:
    params:
      maxCount: 5
  ```
- 热门文章和相关文章的比例：
  ```yml next/_config.yml
  related_posts:
    params:
      #PPMixingRate: 0.0
  ```
- 显示相关文章的日期：
  ```yml next/_config.yml
  related_posts:
    params:
      isDate: true
  ```
- 显示相关文章的图片：
  ```yml next/_config.yml
  related_posts:
    params:
      isImage: true
  ```
- 显示相关文章的摘要：
  ```yml next/_config.yml
  related_posts:
    params:
      isExcerpt: true
  ```
<!-- endtab -->
{%endtabs%}

### 文章编辑

NexT 支持文章编辑功能。启用该功能后，用户可以在 GitHub（或其它代码托管平台）上快速浏览和编辑文章源代码。

{%tabs post-edit%}
<!-- tab enable -->
你可以将 {%label primary@主题配置文件%} 中的`post_edit.enable`值修改为 true 来启用它：

```yml next/_config.yml
post_edit:
  enable: true
```
<!-- endtab -->
<!-- tab url -->
你应该为你的文章创建一个源码仓库。`url`的设置取决于在 GitHub（或其它代码托管平台） 上的开源项目。

- 站点仓库：
  - 查看源码链接：`url: https://github.com/.../tree/master/source/_posts/`
  - Fork 和编辑链接：`url: https://github.com/.../edit/master/source/_posts/`
- 文章仓库：
  - 查看源码链接：`url: https://github.com/.../_posts/tree/master/`
  - Fork 和编辑链接：`url: https://github.com/.../_posts/edit/master/`
<!-- endtab -->
{%endtabs%}

### 文章导航

如果存在，在文章页脚部分显示「上一篇」和「下一篇」。

```yml next/_config.yml
post_navigation: left
```
