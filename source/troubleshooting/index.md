---
title: 故障排除
date: 2021-10-22 21:07:34
---

### 快速调试

**在 GitHub 上提交问题之前，你可以按照以下步骤进行调试：**

如果你从 Hexo 或浏览器收到错误消息：

- 如果错误来自 Hexo 插件，例如 hexo-word-counter，请向其 GitHub 仓库提交问题。
- 如果错误来自第三方服务，例如 Gitalk 评论系统，请向其 GitHub 仓库提交问题。
- 其他问题请在 Google、Stackoverflow、GitHub Issuer 中搜索。

以下步骤将帮助你确定问题的原因：

- 执行`hexo clean`，清除浏览器缓存和 CDN 缓存（或禁用所有 CDN 服务）。这可能需要一些时间才能生效。
- 禁用浏览器插件，或使用其他设备和浏览器进行测试，因为错误可能只出现在特定浏览器中。
- 切换到另一个主题并检查错误是否存在。换句话说，证明这是 NexT 的 bug，而不是 Hexo。
- 将 NexT 主题升级到最新版本。
- 将 Hexo 和所有 Hexo 插件升级到最新版本。
- 将 Node.js 升级或降级到最新的 LTS 版本。
- 卸载所有非必要的 Hexo 插件，或删除 node-modules 目录后使用`npm install --force`重新安装所需依赖。

### 保持缩进

当你编辑任何 YAML 配置时，始终需要保持缩进。目前，在所有 Hexo 和 NexT 配置文件中，父选项下的参数都使用 2 个空格缩进。

例如，如果我们想通过备用主题配置将 NexT 的 scheme 从 Muse 改为 Gemini：

首先打开 {%label primary@主题配置文件%}，复制 Scheme Settings 部分下的参数：

```yml next/_config.yml
# ---------------------------------------------------------------
# Scheme Settings
# ---------------------------------------------------------------

scheme: Muse
#scheme: Mist
#scheme: Pisces
#scheme: Gemini
```

然后打开 {%label info@站点配置文件%}，并在`theme_config`选项下粘贴这些参数：

```yml hexo/_config.yml
theme_config:
#scheme: Muse
#scheme: Mist
#scheme: Pisces
scheme: Gemini
```

这不会起作用，因为父选项`theme_config`下粘贴过来的参数没有使用缩进。Hexo 会认为这些参数不存在而无法读取。正确的配置写法应该是：

```yml hexo/_config.yml
theme_config:
  #scheme: Muse
  #scheme: Mist
  #scheme: Pisces
  scheme: Gemini
```

这时，Hexo 就能以`theme_config.scheme: Gemini`这种方式读取参数，也就是说，NexT 能读取`scheme: Gemini`这个参数。所以，父选项下使用 2 个空格的缩进，能使 NexT 读取参数并按预期工作。

### 目录问题

不要在文章中跳级使用标题。例如，不建议在四级标题后使用三级标题。如果你使用 hexo-renderer-markdown-it，建议你安装 markdown-it-named-headings 使 TOC 正确工作。

### 图标无效

将你的 favicon 放入站点的 source 目录中。如果你发现图标无效，请先清理你的浏览器缓存，然后访问图标链接，这个地址应该是：http(s)://your-domain.com/favicon.ico 。

{%note warning%}
如果你的站点在子目录中，请设置为 `favicon: favicon.ico`。
{%endnote%}
