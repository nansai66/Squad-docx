# 边缘区域 Ping

{% hint style="success" %}
想当 Squad 服主？50 元/月起就能拿下入门款专属服务器！[南赛云](https://server.squadovo.cn/)是高性价比开服首选，低价不低质，让您轻松启动专属战局，低成本圆服主梦～
{% endhint %}

**边缘区域Ping** 是决定您的服务器在服务器列表筛选延迟的关键

您可以通过 RCON 查询您的服务器链接至 **边缘区域Ping** 延迟

如果您发现无法连接至 **边缘区域Ping** 服务器，您可以进行 [可达性测试](http://ec2-reachability.amazonaws.com/)

<details>

<summary>标识符（地区代码）一览</summary>

* ap-southeast-1 ：新加坡 （东南亚）
* ap-east-1 ：中国 香港 （亚州）
* us-west-1 ：美国 旧金山（美国西部）
* us-east-1 ：美国 阿什本（美国东部）
* me-central-1 ：阿联酋 迪拜（中东）
* eu-central-1 ：德国 法兰克福（欧洲中部）
* eu-west-2 ：英国 伦敦（欧洲西部）
* eu-north-1 ：瑞典 斯德哥尔摩（欧洲北部）
* ap-southeast-2 ：澳大利亚 悉尼 （大洋洲）

</details>

## 边缘Ping服务器列表

### 亚洲地区 <a href="#ya-zhou-di-qu-ci-qu-yu-dui-guo-nei-you-hao-tui-jian" id="ya-zhou-di-qu-ci-qu-yu-dui-guo-nei-you-hao-tui-jian"></a>

新加坡(ap-southeast-1):

```
https://apigateway.ap-southeast-1.amazonaws.com/ping
```

中国 香港特别行政区(ap-east-1)：

```
https://apigateway.ap-east-1.amazonaws.com/ping
```

### 美洲地区 <a href="#mei-zhou-di-qu-ci-qu-yu-yan-chi-170ms-bu-tui-jian" id="mei-zhou-di-qu-ci-qu-yu-yan-chi-170ms-bu-tui-jian"></a>

美国 加利福尼亚 旧金山(us-west-1)：

```
https://apigateway.us-west-1.amazonaws.com/ping
```

美国 弗吉尼亚州 阿什本(us-east-1)：

```
https://apigateway.us-east-1.amazonaws.com/ping
```

### 中东地区

阿联酋 迪拜酋长国 迪拜(me-central-1)：

```
https://apigateway.me-central-1.amazonaws.com/ping
```

### 欧洲区域 <a href="#ou-zhou-qu-yu-ci-qu-yu-yan-chi-200ms-bu-tui-jian" id="ou-zhou-qu-yu-ci-qu-yu-yan-chi-200ms-bu-tui-jian"></a>

德国 法兰克福(eu-central-1)：

```
https://apigateway.eu-central-1.amazonaws.com/ping
```

英国 伦敦(eu-west-2)：

```
https://apigateway.eu-west-2.amazonaws.com/ping
```

瑞典 斯德哥尔摩(eu-north-1)：

```
https://apigateway.eu-north-1.amazonaws.com/ping
```

### 大洋洲区域 <a href="#da-yang-zhou-qu-yu-ci-qu-yu-yan-chi-180ms-bu-tui-jian" id="da-yang-zhou-qu-yu-ci-qu-yu-yan-chi-180ms-bu-tui-jian"></a>

澳大利亚 悉尼(ap-southeast-2)：

```
https://apigateway.ap-southeast-2.amazonaws.com/ping
```



目前 Squad SDK 仅采用了 **9 个区域**的服务器作为验证延迟的关键
