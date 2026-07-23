---
layout:
  width: default
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
---

# 服务器安装

{% hint style="success" %}
想当 Squad 服主？50 元/月起就能拿下入门款专属服务器！[南赛云](https://server.squadovo.cn/)是高性价比开服首选，低价不低质，让您轻松启动专属战局，低成本圆服主梦～
{% endhint %}

## **Windows**

### 使用搭建包搭建

先下载一键搭建包：[战术小队 Win 一键搭建包](https://pan.nansai.cc/s/q0sk)

**然后直接运行搭建包内一键安装脚本：**<mark style="color:green;">一键安装.bat</mark>

### 使用 MCSManager 快速搭建

先前往 [MCSManager Github](https://github.com/MCSManager/MCSManager)，下载并安装 MCSManager&#x20;

前往应用市场，选择 Squad，找到 Windows 版的 Squad 点击安装即可快速部署

<figure><img src="../../.gitbook/assets/image (6).png" alt="" width="563"><figcaption></figcaption></figure>

## **Linux**

### 一键安装脚本

当前脚本仅支持 **Centos、Ubuntu、Debian** 系统

```
sudo curl -sSL https://download.nansai.cc/squad/linux_install.sh | bash
```

执行路劲就是您的安装路径，如有需要自行 **cd** 切换安装路径

**确保您是 root 最高权限用户，等待安装完毕即可！！！**

## Docker

### 使用 MCSManager 快速搭建

先前往 [MCSManager Github](https://github.com/MCSManager/MCSManager)，下载并安装 MCSManager&#x20;

前往应用市场，选择 Squad，找到 Docker 版的 Squad 点击安装即可快速部署

<figure><img src="../../.gitbook/assets/image (277).png" alt="" width="563"><figcaption></figcaption></figure>



## 温馨提示

{% hint style="danger" %}
启动服务器前请确保 Steam Client 已关闭，否则服务端无法运行。
{% endhint %}

{% hint style="info" %}
有关于战术小队服务器相关问题，请访问 Offworld Industries Hosting

Discord 频道：[https://discord.gg/VmUwR7J](https://discord.gg/VmUwR7J)
{% endhint %}

{% hint style="warning" %}
当 战术小队 **服务端** 与 **客户端** 在同一主机时，请先关闭 Steam 再启动服务器。

服务器启动后再登录 Steam 启动游戏，否则服务端会出错。
{% endhint %}
