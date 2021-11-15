---
title: 聊天服务
date: 2021-10-25 14:36:37
---

### Chatra

[Chatra](https://chatra.com/cn/) 是网站的实时聊天应用程序。

{%tabs chatra%}
<!-- tab 启用 Chatra → -->
访问 Chatra 的 [仪表盘](https://app.chatra.io/settings/general) 来获取你的 ChatraID：

```yml next/_config.yml
# 支持 Chatra
# 参见：https://chatra.com
# 仪表盘：https://app.chatra.io/settings/general
chatra:
  enable: true
  async: true
  id: <ChatraID>
```
<!-- endtab -->
<!-- tab 激活侧边栏按钮 -->
启用 Chatra 后，你可以在 {%label primary@主题配置文件%} 中将`chat.enable`设置为 true：

```yml next/_config.yml
# 在侧边栏中打开聊天小部件的按钮。
# 首先，你需要启用激活侧边栏的聊天服务按钮。
chat:
  enable: true
  icon: fa fa-comment
  text: Chat
```
<!-- endtab -->
{%endtabs%}

### Tidio

[Tidio](https://www.tidio.com) 是网站的实时聊天应用程序。

{%tabs tidio%}
<!-- tab 启用 Tidio → -->
访问 Tidio 的 [仪表盘](https://www.tidio.com/panel/dashboard) 来获取你的 Public Key：

```yml next/_config.yml
# 支持 Tidio
# 参见：https://www.tidio.com
# 仪表盘：https://www.tidio.com/panel/dashboard
tidio:
  enable: true
  key: <Publick Key>
```
<!-- endtab -->
<!-- tab 激活侧边栏按钮 -->
启用 Tidio 后，你可以在 {%label primary@主题配置文件%} 中将`chat.enable`设置为 true：

```yml next/_config.yml
# 在侧边栏中打开聊天小部件的按钮。
# 首先，你需要启用激活侧边栏的聊天服务按钮。
chat:
  enable: true
  icon: fa fa-comment
  text: Chat
```
<!-- endtab -->
{%endtabs%}

### Gitter

[Gitter](https://gitter.im) 是网站的实时聊天应用程序。

{%tabs gitter%}
<!-- tab 启用 Gitter → -->
首先你需要创建一个社区，然后在该社区下创建网站应用的房间：

```yml next/_config.yml
# 支持 Gitter
# 更多信息：https://gitter.im
gitter:
  enable: true
  room: <Community>/<Room Name>
```
<!-- endtab -->
<!-- tab 激活侧边栏按钮 -->
启用 Gitter 后，你可以在 {%label primary@主题配置文件%} 中将`chat.enable`设置为 true：

```yml next/_config.yml
# 在侧边栏中打开聊天小部件的按钮。
# 首先，你需要启用激活侧边栏的聊天服务按钮。
chat:
  enable: true
  icon: fa fa-comment
  text: Chat
```
<!-- endtab -->
{%endtabs%}
