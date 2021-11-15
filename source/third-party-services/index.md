---
title: 第三方服务
date: 2021-10-22 21:07:06
---

静态网站具有一定的局限性，因此我们需要借助于第三方服务来扩展我们的网站。你可以随时使用 NexT 支持的第三方服务扩展所需的功能。

插件可以扩展 NexT 的功能。插件有两种类型：核心插件和第三方插件。核心插件默认从你的站点加载，它们是 NexT 所必须的基本功能；第三方插件提供了大量可选功能，它们默认从 jsDelivr CDN 加载，因为它在任何地方都很快。

配置这些插件非常简单，比如你想在你的站点中使用 pjax，只需在 {%label primary@主题配置文件%} 中将`pjax`选项设置为 true 即可：

```yml next/_config.yml
# 在你的站点中启用 Ajax navigation。
# 更多信息：https://github.com/next-theme/pjax
pjax: true
```

如果想为任意插件指定提供的 CDN，你需要设置或者更新 CDN 的 url。
