---
title: 安装
date: 2021-10-23 14:01:05
---

### 选择版本

每个月都会发布一个新版本的 NexT。你可以选择安装最新版本或选择稳定的旧版本。

{%tabs 版本%}
<!-- tab 最新 Master 分支 -->
下载 [最新 Master 分支](https://github.com/next-theme/hexo-theme-next/archive/master.zip)。

可能不稳定，但包括最新功能。在大多数情况下，对高级用户和开发人员有用。
<!-- endtab -->
<!-- tab 最新发布版本 -->
下载 [最新发布版本](https://github.com/next-theme/hexo-theme-next/releases/latest)。

大多数情况下是稳定的，推荐给入门用户。
<!-- endtab -->
<!-- tab 指定发布版本 -->
下载 [指定发布版本](https://github.com/next-theme/hexo-theme-next/releases)。

在极少数情况下有用，但不推荐。你必须指定版本号，用 [Tags 列表](https://github.com/next-theme/hexo-theme-next/tags) 中的任意版本替换即可。
<!-- endtab -->
{%endtabs%}

### 获取 NexT

有两种推荐的下载方法：npm 和 git，你只需选择其中之一。其他安装方式，如从 GitHub 下载并解压 zip 格式的主题源代码等方式，不再推荐，因为这样安装的主题难以管理和升级。

首先在命令行中将目录更改为网站根目录，然后继续以下步骤。

#### 使用 npm

如果你使用的是 Hexo 5.0 或更高版本，可以通过 npm 安装 hexo-theme-next。

{%tabs 安装 by npm%}
<!-- tab 最新发布版本 -->
```
npm install hexo-theme-next@latest
```
<!-- endtab -->
<!-- tab 指定发布版本 -->
```
npm install hexo-theme-next@8.0.0
```
<!-- endtab -->
{%endtabs%}

#### 使用 git

{%tabs 安装 by git%}
<!-- tab 最新 Master 分支 -->
```
git clone https://github.com/next-theme/hexo-theme-next themes/next
```

或通过 GitLab 上的镜像下载：

```
git clone https://gitlab.com/hexo-theme-next/hexo-theme-next themes/next
```

该命令将安装整个仓库（包括 .git 目录）。任何时候你都可以用 Git 更新当前版本并切换到任何版本或更新的 master 分支或其他分支。

获取标签列表：

```
cd themes/next
git tag -l
...
v8.0.0-rc.1
v8.0.0-rc.2
v8.0.0-rc.3
...
```

例如，如果你想切换到 v8.0.0 发布版，输入以下命令即可：

```
git checkout tags/v8.0.0
Note: switching to 'tags/v8.0.0'.
...
HEAD is now at f27e45b Release v8.0.0
```

如果想在不指定 tag 的情况下切换到最新发布版本，输入以下命令：

```
git checkout $(git describe --tags $(git rev-list --tags --max-count=1))
```

如果想要切换回 master 分支，输入以下命令：

```
$ git checkout master
```
<!-- endtab -->
<!-- tab 指定发布版本 -->
```
git clone --branch v8.0.0 https://github.com/next-theme/hexo-theme-next themes/next
```

或通过 GitLab 上的镜像下载：

```
git clone --branch v8.0.0 https://gitlab.com/hexo-theme-next/hexo-theme-next themes/next
```

此命令将安装指定的发布版本（包含 .git 目录）。你可以随时切换到任何标记版本，但是仅限于指定发布版。
<!-- endtab -->
{%endtabs%}

### 设置

当 NexT 下载完成后，我们需要按照 [启用 NexT](../#启用-NexT) 说明进行操作。
