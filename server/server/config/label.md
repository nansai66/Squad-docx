---
description: 这里给服主提供如何配置服务器标签教程
---

# 标签设置

{% hint style="success" %}
想当 Squad 服主？50 元/月起就能拿下入门款专属服务器！[南赛云](https://server.squadovo.cn/)是高性价比开服首选，低价不低质，让您轻松启动专属战局，低成本圆服主梦～
{% endhint %}

* 标签可以在 server.cfg 中配置
* 它们被添加到“标签”行中，并用空格分隔
* 默认情况下，所有客户端过滤器都设置为显示“任何”标记，这将显示所有服务器，包括未标记的服务器。在客户端上按标记进行筛选会将搜索结果范围缩小到与筛选器中使用的标记匹配的服务器。
* 我们建议您使用适用于您的服务器的每个类别的标签，因为它可以帮助玩家根据他们的游戏风格和偏好过滤服务器列表。不添加标签意味着玩家只有在没有过滤特定标签类别的情况下才会在服务器浏览器中看到您的服务器。

#### 例如：

```
Tags= language_zh mode_aas mode_raas mode_invasion playstyle_relaxed exp_experience maprot_voting
```

<details>

<summary>关于“查找匹配”工作原理的说明</summary>

* 仅当玩家安装了这些模组时，才会显示修改后的服务器
* 不显示已满的服务器
* 服务器浏览器筛选器使用游戏模式标记来缩小服务器选择范围。“查找匹配”将改为按活动游戏模式进行搜索。

</details>

## 语言标签

* 您最多可以添加 2 个语言标签  注意：我们使用的是 ISO-639-1 双字母编码

| 显示的标签  | 命令           |
| ------ | ------------ |
| 英语     | language\_en |
| 中文     | language\_zh |
| 俄语     | language\_ru |
| 德语     | language\_de |
| 土耳其语   | language\_tr |
| 乌克兰语   | language\_uk |
| 法语     | language\_fr |
| 葡萄牙语   | language\_pt |
| 波兰语    | language\_pl |
| 瑞典语    | language\_sv |
| 泰语     | language\_th |
| 荷兰语    | language\_nl |
| 芬兰语    | language\_fi |
| 朝鲜语    | language\_ko |
| 西班牙语   | language\_es |
| 挪威语    | language\_no |
| 日语     | language\_ja |
| 丹麦语    | language\_da |
| 意大利语   | language\_it |
| 捷克语    | language\_cs |
| 塔加洛语   | language\_tl |
| 印度尼西亚语 | language\_id |
| 哈萨克语   | language\_kk |
| 阿拉伯语   | language\_ar |
| 希伯来语   | language\_he |

## 游戏模式

* 您最多可以添加 3 个游戏模式标签。

| 模式名称   | 命令                |
| ------ | ----------------- |
| AAS    | mode\_aas         |
| RAAS   | mode\_raas        |
| 摧毁（破坏） | mode\_destruction |
| 区域控制   | mode\_tc          |
| 叛乱     | mode\_insurgency  |
| 暖服     | mode\_seed        |
| 遭遇战    | mode\_skirmish    |
| 训练     | mode\_training    |
| 入侵     | mode\_invasion    |

## 游戏风格

* 您可以添加 1 个 风格标签 此标签旨在帮助您更好地定义服务器身份和想要吸引的玩家类型

| 风格名字 | 命令                  |
| ---- | ------------------- |
| 休闲模式 | playstyle\_relaxed  |
| 竞技模式 | pplaystyle\_focused |
| 军事模拟 | playstyle\_milsim   |

## 经验

* 您可以添加 1 个经验标签

| 名字 | 命令              |
| -- | --------------- |
| 萌新 | exp\_newplayer  |
| 老兵 | exp\_experience |

## 地图选择方式

* 您可以添加 1 个地图旋转标签

| 名字   | 命令               |
| ---- | ---------------- |
| 固定地图 | maprot\_rotation |
| 投票选择 | maprot\_voting   |
|      |                  |
