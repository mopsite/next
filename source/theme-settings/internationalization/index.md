---
title: 国际化
date: 2021-10-24 12:31:07
---

### 选择语言

NexT 目前支持 21 种语言。编辑 {%label info@站点配置文件%}，将`language`的值设为你想要的语言。例如，设置简体中文如下：

```yml hexo/_config.yml
language: zh-CN
```

{%note info no-icon%}
`language`的值可以参考 NexT 主题目录中 languages 文件夹中的文件名。

另外，laguaes 目录下的文件是自动生成的，不需要直接修改。如果你想为 NexT 主题添加或改进翻译，请通过 [Crowdin](https://crowdin.com/project/hexo-theme-next) 提交。
{%endnote%}

### 多语言切换

首先，在 {%label info@站点配置文件%} 中设置多语言如下：

```yml hexo/_config.yml
language:
  - zh-CN
  - en
```

然后，在 {%label primary@主题配置文件%} 中开启`language_switcher`：

```yml next/_config.yml
# 在页脚中显示多语言切换。
language_switcher: true
```

### 覆盖默认翻译

如果你想自定义默认翻译，无需修改 languages 目录中的翻译文件，你可以使用 [数据文件](https://mopsite.gitee.io/hexo/usage/data-files/) 覆盖所有翻译。

1. 在 source/_data 目录下创建一个 languages.yml 文件。
2. 插入以下代码（注意两个空格的缩进）：
  ```yml languages.yml
  # 语言
  zh-CN:
    # 项目
    post:
      copyright:
        # 自定义翻译
        author: 本文博主
  en:
    menu:
      schedule: Calendar
  ```
