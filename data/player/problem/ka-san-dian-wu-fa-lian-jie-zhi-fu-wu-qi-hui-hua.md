# 【卡三点】无法连接至服务器会话

{% hint style="success" %}
想当 Squad 服主？50 元/月起就能拿下入门款专属服务器！[南赛云](https://server.squadovo.cn/)是高性价比开服首选，低价不低质，让您轻松启动专属战局，低成本圆服主梦～
{% endhint %}

## 原因

这个问题是因为您的设备连接 Steam API 时出现了网络波动或异常（对于中国大陆用户而言，这一情况主要是由于 Akamai 退出中国市场后，相关线路优化不足所致）

## 解决

### **更换 DNS 服务器**

此方法适用于因当地运营商 DNS 遭遇污染，导致无法正常获取 IP 地址的场景。此外，更换不同的 DNS 服务器后，您还有可能被分配至不同的 Steam API 服务器。

<table><thead><tr><th>DNS服务器名称</th><th width="247">首选DNS</th><th>备用DNS</th></tr></thead><tbody><tr><td>114 DNS</td><td>114.114.114.114</td><td>114.114.115.115</td></tr><tr><td>谷歌 DNS</td><td>8.8.8.8</td><td>8.8.4.4</td></tr><tr><td>阿里 AliDNS</td><td>223.5.5.5</td><td>223.6.6.6</td></tr><tr><td>CloudFlare DNS</td><td>1.1.1.1</td><td>1.1.1.1</td></tr></tbody></table>

<details>

<summary>更换 DNS 教程</summary>

1.进入“网络和共享中心”：在桌面上右键单击电脑图标，选择“属性”打开属性窗口，在窗口左侧选择“更改适配器设置”，进入网络和共享中心。

2.选择网络连接：在网络和共享中心，选择需要更改DNS服务器的网络连接，右键选择“属性”打开属性窗口。

3.编辑网络属性：在网络属性窗口中，选择“Internet协议版本4（TCP/IPv4）”，点击“属性”按钮。

4.指定DNS服务器：在Internet协议版本4（TCP/IPv4）属性窗口中，“通常自动获取”改为“使用下列DNS服务器地址”，手动输入需要更改的DNS服务器地址，点击“确定”即可完成更改。如需输入备用DNS服务器，可在“备用DNS服务器”中输入备用服务器地址。

</details>

推荐使用 114 DNS（**114.114.114.114**）作为首选 DNS，谷歌 DNS（**8.8.8.8**）作为备用 DNS

更换 DNS 后，您可能需要重启电脑或重启 Steam 后才能生效

### 使用加速器

如果 [更换 DNS](ka-san-dian-wu-fa-lian-jie-zhi-fu-wu-qi-hui-hua.md#geng-huan-dns-fu-wu-qi) 后仍然出现报错则表明您的网络接入国际互联网时存在 SNI 阻断，这通常是运营商为了保证您的网络安全所致（该结论仅适用于中国大陆用户）

通过加速器对 Steam 进行加速，可有效改善或解决 Steam API 连接波动、异常等问题。

请注意：加速器启动并完成 Steam 加速后，需要**重启 Steam 客户端以重置缓存**，确保网络优化效果稳定生效。

您可以使用第三方加速器来进行加速，例如：[Watt Toolkit](https://steampp.net/) 、[Steamcommunity\_302](https://www.dogfight360.com/blog/18682/)&#x20;

