---
title: 配置
date: 2021-10-23 14:02:05
---

如何配置 Hexo 和 NexT？传统的方法是将一些选项存储在 {%label info@站点配置文件%} 和 {%label primary@主题配置文件%}，但是这种方法通过拉取或下载新版本来更新 NexT 主题并不顺利。

目前，NexT 鼓励用户使用备用主题配置。

### _config.[name].yml

使用这种方法，你所有配置都位于 _config.[name].yml 配置文件中。将`[name]`替换成 {%label info@站点配置文件%} 中`theme`的选项值，例如 next。

1. 请确保你使用的是 Hexo 5.0 或更高版本。
2. 在站点的根目录中创建一个配置文件，例如 _config.next.yml。
3. 从 {%label primary@主题配置文件%} 中复制你所需的 NexT 主题选项到上面创建好的配置文件中。如果你是第一次安装 NexT，那就通过以下命令复制整个 {%label primary@主题配置文件%}：
  ```
  # Installed through npm
  cp node_modules/hexo-theme-next/_config.yml _config.next.yml
  # Installed through Git
  cp themes/next/_config.yml _config.next.yml
  ```

### theme_config

通过这种方式，你的所有配置都位于 {%label info@站点配置文件%}，你不需要编辑 {%label primary@主题配置文件%} 或创建任何新文件，但是你需要在`theme_config`选项中保留缩进。

1. 请确认 /source/_data/next.yml 文件不存在（如果存在请备份并删除）。
2. 从 {%label primary@主题配置文件%} 中复制所需的 NexT 主题选项到 {%label info@站点配置文件%}。
3. 在 {%label info@站点配置文件%} 中添加`theme_config`选项，并将复制过来的主题选项粘贴到其下，保持向右缩进两个空格。

