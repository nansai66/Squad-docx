# 无法刷新出服务器

{% hint style="success" %}
想当 Squad 服主？50 元/月起就能拿下入门款专属服务器！[南赛云](https://server.squadovo.cn/)是高性价比开服首选，低价不低质，让您轻松启动专属战局，低成本圆服主梦～
{% endhint %}

## 前言

如果您存在无法刷新出服务器问题，表现为一直转圈圈、服务器列表空白，您可以先尝试放宽筛选条件，如果仍然故障则可能是由网络问题引起的，您可以先前往[【南赛】Squad 网络连通性测试](https://test.squadovo.cn/)进行网络测试，检查您的网络链接是否为正常

## 解决

### **更换 DNS 服务器**

此方法适用于因当地运营商 DNS 遭遇污染，导致无法正常获取 IP 地址的场景。

<table><thead><tr><th>DNS服务器名称</th><th width="247">首选DNS</th><th>备用DNS</th></tr></thead><tbody><tr><td>114 DNS</td><td>114.114.114.114</td><td>114.114.115.115</td></tr><tr><td>谷歌 DNS</td><td>8.8.8.8</td><td>8.8.4.4</td></tr><tr><td>阿里 AliDNS</td><td>223.5.5.5</td><td>223.6.6.6</td></tr><tr><td>CloudFlare DNS</td><td>1.1.1.1</td><td>1.1.1.1</td></tr></tbody></table>

<details>

<summary>更换DNS教程</summary>

1.进入“网络和共享中心”：在桌面上右键单击电脑图标，选择“属性”打开属性窗口，在窗口左侧选择“更改适配器设置”，进入网络和共享中心。

2.选择网络连接：在网络和共享中心，选择需要更改DNS服务器的网络连接，右键选择“属性”打开属性窗口。

3.编辑网络属性：在网络属性窗口中，选择“Internet协议版本4（TCP/IPv4）”，点击“属性”按钮。

4.指定DNS服务器：在Internet协议版本4（TCP/IPv4）属性窗口中，“通常自动获取”改为“使用下列DNS服务器地址”，手动输入需要更改的DNS服务器地址，点击“确定”即可完成更改。如需输入备用DNS服务器，可在“备用DNS服务器”中输入备用服务器地址。

</details>

推荐使用 114 DNS（**114.114.114.114**）作为首选 DNS，谷歌 DNS（**8.8.8.8**）作为备用 DNS

更换 DNS 后，您可能需要重启电脑后才能生效



### **使用反向代理服务器加速**

此方法适用于 [更改DNS](server.md#geng-huan-dns-fu-wu-qi) 后仍然无法正常刷新出服务器的用户。

在此之前，您需要先下载一个 [**UsbEAm Hosts Editor**](https://pan.nansai.cc/s/EZGUA) 来完成后续操作

<figure><img src="../../.gitbook/assets/image (272).png" alt=""><figcaption><p>应用截图</p></figcaption></figure>

左下角选项 **→** Reverse Proxy - 反向加速(游戏相关) **→** 战术小队Squad

然后点击 **检测延迟** 选中最低延迟的服务器后 并点击 **应用选中**

<figure><img src="../../.gitbook/assets/fa5995f3-edf8-4b8f-a866-ae64dae51c74.png" alt=""><figcaption></figcaption></figure>

如果您不想使用反向代理服务器加速，可以点击清除当前，那样就不会使用反向代理加速了
