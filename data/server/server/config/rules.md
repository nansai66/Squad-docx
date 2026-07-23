---
description: 这里给服主提供如何配置服务器规则教程
---

# 规则设置

{% hint style="success" %}
想当 Squad 服主？50 元/月起就能拿下入门款专属服务器！[南赛云](https://server.squadovo.cn/)是高性价比开服首选，低价不低质，让您轻松启动专属战局，低成本圆服主梦～
{% endhint %}

* 规则可以在 server.cfg 中配置
* 它们被添加到 'Rules' 行中，并用空格分隔
* 我们建议您使用应用于服务器的规则
* 规则标记仅显示在服务器预览卡上。它们不适用于过滤器和匹配功能。

例如：

```
Rules=rule_vehicle_name_claim rule_play_objective rule_no_main_camping rule_no_soloing_vehicle rule_mech_inf_restrictions rule_lock_restrictions
```

| 命令                            | 名字        |
| ----------------------------- | --------- |
| rule\_vehicle\_name\_claim    | 有载具申请规则   |
| rule\_vehicle\_fcfs           | 先到先得      |
| rule\_play\_objective         | 围绕当前目标交战  |
| rule\_no\_main\_camping       | 不允许压家     |
| rule\_no\_soloing\_vehicle    | 装甲载具不允许单载 |
| rule\_mech\_inf\_restrictions | 机械化步兵规定   |
| rule\_lock\_restrictions      | 小队队锁规则    |
