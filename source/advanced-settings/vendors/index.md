---
title: 加速服务
date: 2021-10-25 19:40:36
---

你可以在 {%label primary@主题配置文件%} 的`vendors`选项中设置合适的 CND 地址，这样可以让插件的静态资源加载更快。

```yml next/_config.yml
vendors:
  # NexT 内部脚本的 CDN 提供方。
  # 可用值：local | jsdelivr | unpkg | cdnjs
  # 注意：如果你使用的是 NexT 的最新 master 分支版本，请设置 internal: local。
  internal: local
  # 第三方插件的默认 CDN 提供方。
  # 可用值：local | jsdelivr | unpkg | cdnjs
  # plugins: local 需要依赖：https://github.com/next-theme/plugins
  plugins: jsdelivr
```

### 核心插件

`inernal: local`用于设置如何加载核心插件，例如 source/js/utils.js。这些插件默认从你的站点加载，它们是 NexT 所需的基本功能。将`internal`设置为`jsdelivr`、`unpkg`或者`cdnjs`从相应的 CDN 加载它们。

{%note info%}
如果你的站点部署在免费托管服务（如 GitHub、Gitlab 等），建议核心插件使用 CDN 链接。CDN 通常速度更快，并且没有流量限制。如果你使用的是 NexT 的最新 master 分支版本，请设置为`internal: local`。
{%endnote%}

### 第三方插件

`plugins: jsdelivr`用于设置如何加载第三方插件，例如 anime.js。第三方插件默认从 [jsDelivr](https://www.jsdelivr.com/) CDN 加载，因为 jsDelivr 拥有国内颁发的有效 ICP 许可证，在国内可以很好的访问。

我们还提供其他可选的 CDN，包括著名的 [UNPKG](https://unpkg.com/) 和 [CDNJS](https://cdnjs.com/)。之所以选择这些 CDN 提供方，是因为它们快速可靠。将`plugins`设置为`unpkg`或`cdnjs`从不同的 CDN 加载它们。

{%note danger%}
如果你或你的大部分用户来自国内，不要使用 CDNJS 作为你的 CDN 提供方，因为国内某些地区会屏蔽它。
{%endnote%}

如果你希望从你的站点加载所有第三方插件，请将`plugins`设置为`local`，并安装 [next-theme/plugins](https://github.com/next-theme/plugins) 包。如果你的网站部署在局域网中，那么这将比 CDN 服务具有更快的加载速度。

### 自定义 CDN 链接

有时，你可能需要使用`vendors.plugins`选项的可用值中未包含的其他 CDN。在`vendors`中，你可以为每个库单独配置 CDN 链接。

配置格式为`libname: CDN URL`。这里的`libname`和 _vendors.yml 文件中的一样。`CDN URL`将会覆盖默认的 CDN 链接。

例如，如果你想设置`anime`的 CDN 链接，在 {%label primary@主题配置文件%} 中的`vendors`选项中添加`anime`键名，并将它的值设置为 anime.js 的 CDN 链接。

```yml next/_config.yml
vendors:
  # ...
  # Some contents...
  # ...
  anime: //cdn.jsdelivr.net/gh/juliangarnier/anime@latest/lib/anime.min.js
```

建议使用与 _vendors.yml 文件中相同的版本库，以避免潜在问题。如果你需要其他版本，则需要先对其进行测试。

在你的站点上启用 HTTPS 时，请切记使用 CDN 链接的 HTTPS 协议。

{%note info no-icon%}
可以使用`https://cdn.jsdelivr.net/npm/package@version/file`这样的格式从 jsDelivr 获取文件。 它可以自动缩小 JS 和 CSS 文件，即使没有缩小版本。你只需要使用 filename.min.js 或 filename.min.css 来替换上面的 file 即可。你可以参考 jsDelivr 的 [更多信息](https://www.jsdelivr.com/features)。
{%endnote%}
