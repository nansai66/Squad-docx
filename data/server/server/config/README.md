---
description: 服务器部分相关文档
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
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

# 服务器配置

{% hint style="success" %}
想当 Squad 服主？50 元/月起就能拿下入门款专属服务器！[南赛云](https://server.squadovo.cn/)是高性价比开服首选，低价不低质，让您轻松启动专属战局，低成本圆服主梦～
{% endhint %}

## 启动命令参数

可以将以下参数加到您的启动命令行中来配置你的服务器，添加这些参数时要注意错别字。

* &#x20;**Port =** 游戏端口
* &#x20;**QueryPort =** Steam 查询端口
* &#x20;**RANDOM** = 地图循环方式（ALWAYS, FIRST, NONE）
* &#x20;**FIXEDMAXPLAYERS** = 最大玩家数量（可选，如没有则采用 [server.cfg](./#server.cfg) 中的数量）
* &#x20;**FIXEDMAXTICKRATE** = 服务器刷新率【Tick】
* &#x20;**Beaconport =** EOS链接端口
* &#x20;**RconPort =** Rcon通讯端口
* &#x20;**-log** = 显示日志窗口

可参考以下示例：

```
start SquadGameServer.exe Port=7787 QueryPort=27165 Beaconport=15000 FIXEDMAXPLAYERS=100 FIXEDMAXTICKRATE=50 RANDOM=ALWAYS -log
```

以上参数均非必填，如不填写将按照示例提供的值运行。

## 配置文件

服务器的配置文件目录位于 SquadGame\ServerConfig 文件夹，列表：

```
Admins.cfg                     # 权限组[管理员]
Bans.cfg                       # 封禁玩家列表
ExcludedFactions.cfg           # 禁止阵营列表
ExcludedLayers.cfg             # 禁止图层列表
ExcludedLevels.cfg             # 禁止地图列表
LayerRotation.cfg              # 地图池（图层型）
LayerVoting.cfg                # 投票系统地图池（图层型）
LayerVotingLowPlayers.cfg      # 低玩家投票系统地图池（图层型）
LayerVotingNight.cfg           # 指定时间投票系统地图池（图层型）
LevelRotation.cfg              # 地图池（地图型）
License.cfg                    # 许可证
MOTD.cfg                       # 服务器介绍[每日消息]
Rcon.cfg                       # 远程管理配置
RemoteAdminListHosts.cfg       # 远程权限组[管理员]列表
RemoteBanListHosts.cfg         # 远程封禁玩家列表
Server.cfg                     # 服务器配置
ServerMessages.cfg             # 服务器循环[红字]公告
VoteConfig.cfg                 # 投票配置文件
```

### **Admins.cfg**

* 这个文件的作用是这是设置服务器权限的文件夹
* 可以创建一个 权限组，并将管理员分配到该组中。您可以创建 任意类型，任意数量 的权限组。这些文件在更新时将不会被覆盖。

{% hint style="warning" %}
必须使用 Steam ID 或 EOS ID
{% endhint %}

```
Group=SuperAdmin:changemap,cheat,private,balance,chat,kick,ban,config,cameraman,debug,pause
Group=Admin:changemap,balance,chat,kick,ban,cameraman,pause
Group=Moderator:changemap,chat,kick,ban
Group=Whitelist:reserve

//实习管理员
Admin=76561115695178:Moderator //玩家 5
Admin=8915618948911:Moderator //玩家 4

//管理员
Admin=7894591951519:Admin //玩家 3
Admin=7895365435431:Admin //玩家 8792

//超级管理员
Admin=7984591565611:SuperAdmin //玩家 2
Admin=7917236241624:SuperAdmin //玩家 1 

//白名单 - VIP&SVIP
Admin=7984591565611:Whitelist //玩家 123
Admin=7984591565523:Whitelist //玩家 156
```

<details>

<summary>权限列表</summary>

```
changemap                      # 更换/预设地图              
pause                          # 暂停游戏
cheat                          # 使用作弊命令
private	                       # 设置服务器密码
balance	                       # 忽略服务器阵营平衡
chat                           # 管理员聊天/服务器公告
kick                           # 踢出玩家
ban                            # 封禁玩家
config                         # 更改服务器配置
cameraman                      # 摄影机 - 管理员视角
immunity                       # 无法被 踢出/封禁
manageserver                   # 关闭服务器
reserve                        # 预留位
debug                          # 调试
teamchange                     # 忽略更换阵营时间限制
forceteamchange                # 允许执行强制更换阵营命令
canseeadminchat                # 查看 管理员聊天/友军击杀/管理员加入 消息
```

</details>

### **Bans.cfg**

* 这个文件储存的是封禁玩家列表，格式为：`SteamID64:封禁时间戳 //备注`

```
76561198039509812:0 //永久封禁-使用作弊程序
7862895148978485:1623366856 //击杀友军
```

手动添加封禁玩家时，请使用 换行符 作为每条封禁玩家的分割。

如果要检查封禁玩家的封禁时间或创建一个限时的玩家封禁，请使用此工具转换时间戳：

{% embed url="https://tool.chinaz.com/tools/unixtime.aspx" %}

### CustomOptions.cfg

* 这个文件通常用于管理 **MOD** 的配置

```
# 在此处，你可以控制特定于模组的服务器设置。模组可以使用蓝图节点 “获取自定义服务器设置” 来收集此文件的内容。
# 这一部分以前存在于 server.cfg 文件中。

// 开始游戏倒计时所需的玩家数量，为整数。默认值是 50。
#SeedPlayersThreshold=50

// 达到 “SeedPlayersThreshold”（Seed模式下玩家阈值）后，如果有一些玩家断开连接，但当前玩家数量仍保持在该值或高于该值时，不要停止
// 开始倒计时，为整数。该值应大于零且小于 “SeedPlayersThreshold”（Seed模式下玩家阈值）才会被视为已启用。默认值是 45。
#SeedMinimumPlayersToLive=45

// 比赛时长（以秒为单位），为整数。默认值是 21600（6 小时）
#SeedMatchLengthSeconds=21600

// 在准备阶段启用或禁用所有装备包的可用性，为布尔值（有效值为 0 和 1），默认值是 1
#SeedAllKitsAvailable=1

// 两支队伍的初始票数，为整数。默认值是 100
#SeedInitialTickets=100

// 开始倒计时的时长，为浮点数。默认值是 60.0
#SeedSecondsBeforeLive=60.0

// Seed阶段的目标玩家数量。将使用机器人来使服务器的玩家数量达到这个目标数量。
// 队伍将被平衡，以便两支队伍的玩家与机器人数量总和相等。
// 当 “SeedTargetPlayerCount”（Seed目标玩家数量）为 40 时，你会看到以下情况：
// 在一个玩家人数较少的服务器上 // 在一个玩家人数较多的服务器上
// 队伍 1 3 名玩家 17 个机器人 // 队伍 1 16 名玩家 4 个机器人
// 队伍 2 5 名玩家 15 个机器人 // 队伍 2 18 名玩家 2 个机器人
// 当Seed比赛进入开始状态时，所有机器人都会被消灭（且不会再生成新的机器人）。
#SeedTargetPlayerCount=40

// 如果配置文件中不存在相应的设置项或该项被注释掉了，将使用上面列出的所有默认值。
```

### ExcludedFactions.cfg

* 这个文件的作用是从游戏中排除派系，在此文件中添加派系名称即可排除该派系
* 被排除的派系必须列为派系 ID

```
//ADF
//BAF
//CAF
//USA
//USMC
//TLF
//PLA
//PLANMC
//PLAAGF
//RGF
//VDV
//MEA
//INS
//IMF
//WPMC
```

### ExcludedLayers.cfg

* 可以在此处设置服务器禁止游玩的图层，设置后服务器将不会允许这些图层运行
* 此列表使用层ID名称，这与UI显示名称不同。
* 当“MapRotationMode=LayerList”时 此图层设置的禁止图层才生效
* 当使用“adminchangelayer”或“adminsetnextlayer”命令时，这个禁止图层才生效。

```
AlBasrah_TA_v1
Tallil_TA_v1
Narva_TA_v1
Yehorivka_TA_v1

LashkarValley_TC_v3

JensensRange_GB-MIL
JensensRange_US-RUS
JensensRange_USMC-MEA
JensensRange_CAF-INS
JensensRange_AUS-RUS

PacificProvingGrounds_USMC-RUS
PacificProvingGrounds_USMC-MEA

Tutorial_Helicopter
Tutorial_Infantry
```

### ExcludedLevels.cfg

* 可以在此处设置不允许服务器运行的地图，设置后服务器将不会运行此地图。
* 此列表使用层ID名称，这与UI显示名称不同。
* 当“MapRotationMode=LevelList”时 此图层设置的禁止图层才生效

```
AlBasrah
Anvil
Belaya
BlackCoast
Chora
Fallujah
FoolsRoad
GooseBay
Gorodok
Harju
Kamdesh
Kohat
Kokan
Lashkar
Logar
Manicouagan
Mestia
Mutaha
Narva
PacificProvingGrounds
Skorpo
Sumari
Tallil
Yehorivka
```

### LayerRotation.cfg

* 这是图层地图池，在这里可以设置服务器游玩顺序的地图
* 当“MapRotationMode=LayerList”时 这个地图池才能生效
* 地图池是逐行顺序读取的，也就是说行数靠前的图层将优先被录取

以下列出了所有图层，您可将不需要的图层删除（或打上//），这样他们就被移除了。

```
AlBasrah_AAS_v1
AlBasrah_Insurgency_v1
AlBasrah_Invasion_v1
AlBasrah_Invasion_v2
AlBasrah_RAAS_v1
AlBasrah_Seed_v1
AlBasrah_Skirmish_v1
AlBasrah_Skirmish_v2
AlBasrah_TC_v1

Anvil_AAS_v1
Anvil_Invasion_v1
Anvil_RAAS_v1
Anvil_RAAS_v2
Anvil_Skirmish_v1
Anvil_TC_v1

Belaya_AAS_v1
Belaya_AAS_v2
Belaya_AAS_v3
Belaya_Invasion_v1
Belaya_Invasion_v2
Belaya_RAAS_v1
Belaya_Skirmish_v1
Belaya_TC_v1

BlackCoast_AAS_v1
BlackCoast_AAS_v2
BlackCoast_Invasion_v1
BlackCoast_Invasion_v2
BlackCoast_RAAS_v1
BlackCoast_RAAS_v2
BlackCoast_Seed_v1
BlackCoast_Skirmish_v1

Chora_AAS_v1
Chora_AAS_v2
Chora_AAS_v3
Chora_Insurgency_v1
Chora_Invasion_v1
Chora_Invasion_v2
Chora_RAAS_v1
Chora_Skirmish_v1
Chora_TC_v1

Fallujah_AAS_v1
Fallujah_Insurgency_v1
Fallujah_Invasion_v1
Fallujah_Invasion_v2
Fallujah_RAAS_v1
Fallujah_RAAS_v2
Fallujah_Seed_v1
Fallujah_Skirmish_v1
Fallujah_Skirmish_v2
Fallujah_TC_v1

FoolsRoad_AAS_v1
FoolsRoad_AAS_v2
FoolsRoad_Destruction_v1
FoolsRoad_Invasion_v1
FoolsRoad_RAAS_v1
FoolsRoad_Skirmish_v1
FoolsRoad_Skirmish_v2
FoolsRoad_TC_v1

GooseBay_AAS_v1
GooseBay_Invasion_v1
GooseBay_RAAS_v1
GooseBay_RAAS_v2
GooseBay_Seed_v1
GooseBay_Skirmish_v1

Gorodok_AAS_v1
Gorodok_Destruction_v1
Gorodok_Insurgency_v1
Gorodok_Invasion_v1
Gorodok_Invasion_v2
Gorodok_RAAS_v1
Gorodok_RAAS_v2
Gorodok_Skirmish_v1
Gorodok_TC_v1

Harju_AAS_v1
Harju_AAS_v2
Harju_AAS_v3
Harju_Invasion_v1
Harju_Invasion_v2
Harju_Invasion_v3
Harju_RAAS_v1
Harju_RAAS_v2
Harju_TC_v1
Harju_Seed_v1
Harju_Skirmish_v1
Harju_Skirmish_v2

// 以下是训练地图。不适用于常规服务器。
// JensensRange_ADF-PLA
// JensensRange_BAF-IMF
// JensensRange_CAF-INS
// JensensRange_PLANMC-VDV
// JensensRange_USA-RGF
// JensensRange_USMC-MEA
// JensensRange_WPMC-TLF

Kamdesh_AAS_v1
Kamdesh_Insurgency_v1
Kamdesh_Invasion_v1
Kamdesh_RAAS_v1
Kamdesh_Skirmish_v1
Kamdesh_TC_v1

Kohat_AAS_v1
Kohat_RAAS_v1
Kohat_RAAS_v2
Kohat_Skirmish_v1
Kohat_Insurgency_v1
Kohat_Invasion_v1
Kohat_Invasion_v2
Kohat_TC_v1

Kokan_AAS_v1
Kokan_AAS_v2
Kokan_Insurgency_v1
Kokan_Invasion_v1
Kokan_RAAS_v1
Kokan_Skirmish_v1
Kokan_TC_v1

Lashkar_AAS_v1
Lashkar_AAS_v2
Lashkar_Insurgency_v1
Lashkar_Invasion_v1
Lashkar_RAAS_v1
Lashkar_Skirmish_v1
Lashkar_TC_v1
Lashkar_TC_v2

Logar_AAS_v1
Logar_Insurgency_v1
Logar_RAAS_v1
Logar_Seed_v1
Logar_Skirmish_v1
Logar_TC_v1

Manicouagan_AAS_v1
Manicouagan_AAS_v2
Manicouagan_AAS_v3
Manicouagan_RAAS_v1
Manicouagan_RAAS_v2
Manicouagan_Invasion_v1
Manicouagan_Invasion_v2
Manicouagan_Seed_v1
Manicouagan_Skirmish_v1
Manicouagan_Skirmish_v2
Manicouagan_Skirmish_v3

Mestia_AAS_v1
Mestia_AAS_v2
Mestia_Invasion_v1
Mestia_RAAS_v1
Mestia_Skirmish_v1
Mestia_TC_v1

Mutaha_AAS_v1
Mutaha_AAS_v2
Mutaha_Invasion_v1
Mutaha_RAAS_v1
Mutaha_RAAS_v2
Mutaha_Seed_v1
Mutaha_Skirmish_v1
Mutaha_TC_v1

Narva_AAS_v1
Narva_AAS_v2
Narva_AAS_v3
Narva_Destruction_v1
Narva_Invasion_v1
Narva_Invasion_v2
Narva_RAAS_v1
Narva_Skirmish_v1
Narva_TC_v1

PacificProvingGrounds_AAS_v1
PacificProvingGrounds_Seed_v1

// 以下是训练地图。不适用于常规服务器。
// PacificProvingGrounds_PLANMC-VDV
// PacificProvingGrounds_USMC-PLA
// PacificProvingGrounds_USMC-RGF

Sanxian_AAS_v1
Sanxian_AAS_v2
Sanxian_AAS_v3
Sanxian_Invasion_v1
Sanxian_Invasion_v2
Sanxian_RAAS_v1
Sanxian_RAAS_v2
Sanxian_Seed_v1
Sanxian_Skirmish_v1

Skorpo_Invasion_v1
Skorpo_Invasion_v2
Skorpo_RAAS_v1
Skorpo_Skirmish_v1

Sumari_AAS_v1
Sumari_AAS_v2
Sumari_AAS_v3
Sumari_Insurgency_v1
Sumari_Invasion_v1
Sumari_RAAS_v1
Sumari_Seed_v1
Sumari_Skirmish_v1
Sumari_TC_v1

Tallil_AAS_v1
Tallil_Invasion_v1
Tallil_RAAS_v1
Tallil_RAAS_v2
Tallil_Seed_v1
Tallil_Skirmish_v1
Tallil_Skirmish_v2
Tallil_Skirmish_v3
Tallil_TC_v1

// 以下是教练地图，不适用于常规服务器
// Tutorial_Helicopter
// Tutorial_Infantry

Yehorivka_AAS_v1
Yehorivka_AAS_v2
Yehorivka_Destruction_v1
Yehorivka_Invasion_v1
Yehorivka_Invasion_v2
Yehorivka_Skirmish_v1
Yehorivka_Skirmish_v2
Yehorivka_RAAS_v1
Yehorivka_RAAS_v2
Yehorivka_TC_v1
Yehorivka_TC_v2
```

### LayerVoting.cfg

* 这是投票系统地图池，在这里可以设置投票系统允许选择的地图
* 当“MapRotationMode=LayerList\_Vote”时 这个投票系统才能生效

以下列出了所有图层，您可将不需要的图层删除（或打上//），这样他们就被移除了。

```
AlBasrah_AAS_v1
AlBasrah_Insurgency_v1
AlBasrah_Invasion_v1
AlBasrah_Invasion_v2
AlBasrah_RAAS_v1
//AlBasrah_Seed_v1
//AlBasrah_Skirmish_v1
//AlBasrah_Skirmish_v2
AlBasrah_TC_v1

Anvil_AAS_v1
Anvil_Invasion_v1
Anvil_RAAS_v1
Anvil_RAAS_v2
//Anvil_Skirmish_v1
Anvil_TC_v1

Belaya_AAS_v1
Belaya_AAS_v2
Belaya_AAS_v3
Belaya_Invasion_v1
Belaya_Invasion_v2
Belaya_RAAS_v1
//Belaya_Skirmish_v1
Belaya_TC_v1

BlackCoast_AAS_v1
BlackCoast_AAS_v2
BlackCoast_Invasion_v1
BlackCoast_Invasion_v2
BlackCoast_RAAS_v1
BlackCoast_RAAS_v2
//BlackCoast_Seed_v1
//BlackCoast_Seed_v2
//BlackCoast_Skirmish_v1

Chora_AAS_v1
Chora_AAS_v2
Chora_AAS_v3
Chora_Insurgency_v1
Chora_Invasion_v1
Chora_Invasion_v2
Chora_RAAS_v1
//Chora_Skirmish_v1
Chora_TC_v1

Fallujah_AAS_v1
Fallujah_Insurgency_v1
Fallujah_Invasion_v1
Fallujah_Invasion_v2
Fallujah_RAAS_v1
Fallujah_RAAS_v2
//Fallujah_Seed_v1
//Fallujah_Skirmish_v1
//Fallujah_Skirmish_v2
Fallujah_TC_v1

FoolsRoad_AAS_v1
FoolsRoad_AAS_v2
FoolsRoad_Destruction_v1
FoolsRoad_Invasion_v1
FoolsRoad_RAAS_v1
FoolsRoad_RAAS_v2
FoolsRoad_RAAS_v3
//FoolsRoad_Skirmish_v1
//FoolsRoad_Skirmish_v2
FoolsRoad_TC_v1

GooseBay_AAS_v1
GooseBay_Invasion_v1
GooseBay_RAAS_v1
GooseBay_RAAS_v2
//GooseBay_Seed_v1
//GooseBay_Skirmish_v1

Gorodok_AAS_v1
Gorodok_Destruction_v1
Gorodok_Insurgency_v1
Gorodok_Invasion_v1
Gorodok_Invasion_v2
Gorodok_RAAS_v1
Gorodok_RAAS_v2
//Gorodok_Skirmish_v1
Gorodok_TC_v1

Harju_AAS_v1
Harju_AAS_v2
Harju_AAS_v3
Harju_Invasion_v1
Harju_Invasion_v2
Harju_Invasion_v3
Harju_RAAS_v1
Harju_RAAS_v2
//Harju_Skirmish_v1
//Harju_Skirmish_v2
//Harju_Seed_v1
Harju_TC_v1

Kamdesh_AAS_v1
Kamdesh_Insurgency_v1
Kamdesh_Invasion_v1
Kamdesh_RAAS_v1
//Kamdesh_Skirmish_v1
Kamdesh_TC_v1

Kohat_AAS_v1
Kohat_Insurgency_v1
Kohat_Invasion_v1
Kohat_RAAS_v1
//Kohat_Skirmish_v1
Kohat_TC_v1

Kokan_AAS_v1
Kokan_AAS_v2
Kokan_Insurgency_v1
Kokan_Invasion_v1
Kokan_RAAS_v1
Kokan_RAAS_v2
//Kokan_Skirmish_v1
Kokan_TC_v1

Lashkar_AAS_v1
Lashkar_AAS_v2
Lashkar_Insurgency_v1
Lashkar_Invasion_v1
Lashkar_RAAS_v1
//Lashkar_Skirmish_v1
Lashkar_TC_v1
Lashkar_TC_v2

Logar_AAS_v1
Logar_Insurgency_v1
Logar_RAAS_v1
//Logar_Seed_v1
//Logar_Skirmish_v1
Logar_TC_v1

Manicouagan_AAS_v1
Manicouagan_AAS_v2
Manicouagan_AAS_v3
Manicouagan_Invasion_v1
Manicouagan_RAAS_v1
Manicouagan_RAAS_v2
//Manicouagan_Seed_v1
//Manicouagan_Skirmish_v1
//Manicouagan_Skirmish_v2
//Manicouagan_Skirmish_v3

Mestia_AAS_v1
Mestia_AAS_v2
Mestia_Invasion_v1
Mestia_RAAS_v1
//Mestia_Skirmish_v1
Mestia_TC_v1

Mutaha_AAS_v1
Mutaha_AAS_v2
Mutaha_Invasion_v1
Mutaha_RAAS_v1
Mutaha_RAAS_v2
//Mutaha_Seed_v1
//Mutaha_Skirmish_v1
Mutaha_TC_v1

Narva_AAS_v1
Narva_AAS_v2
Narva_AAS_v3
Narva_Destruction_v1
Narva_Invasion_v1
Narva_Invasion_v2
Narva_RAAS_v1
//Narva_Skirmish_v1
Narva_TC_v1

PacificProvingGrounds_AAS_v1
//PacificProvingGrounds_Seed_v1

Sanxian_AAS_v1
Sanxian_AAS_v2
Sanxian_AAS_v3
Sanxian_Invasion_v1
Sanxian_Invasion_v2
Sanxian_RAAS_v1
Sanxian_RAAS_v2
//Sanxian_Seed_v1
//Sanxian_Skirmish_v1

Skorpo_Invasion_v1
Skorpo_Invasion_v2
Skorpo_RAAS_v1
//Skorpo_Skirmish_v1

Sumari_AAS_v1
Sumari_AAS_v2
Sumari_AAS_v3
Sumari_Insurgency_v1
Sumari_Invasion_v1
Sumari_RAAS_v1
//Sumari_Seed_v1
//Sumari_Skirmish_v1
Sumari_TC_v1

Tallil_AAS_v1
Tallil_Invasion_v1
Tallil_RAAS_v1
Tallil_RAAS_v2
//Tallil_Seed_v1
//Tallil_Skirmish_v1
//Tallil_Skirmish_v2
//Tallil_Skirmish_v3
Tallil_TC_v1

Yehorivka_AAS_v1
Yehorivka_AAS_v2
Yehorivka_Destruction_v1
Yehorivka_Invasion_v1
Yehorivka_Invasion_v2
Yehorivka_RAAS_v1
Yehorivka_RAAS_v2
//Yehorivka_Skirmish_v1
//Yehorivka_Skirmish_v2
Yehorivka_TC_v1
Yehorivka_TC_v2
```

### LayerVotingLowPlayers.cfg

* 这是低玩家投票系统地图池，在这里可以设置低玩家时投票系统允许选择的地图
* 当“MapRotationMode=LayerList\_Vote”时 这个低玩家投票系统才能生效
* 当游戏内玩家小于“LowPlayerCountThreshold”值时，低玩家投票系统才生效

以下列出了所有图层，您可将不需要的图层删除（或打上//），这样他们就被移除了。

```
//AlBasrah_AAS_v1
//AlBasrah_Insurgency_v1
//AlBasrah_Invasion_v1
//AlBasrah_Invasion_v2
//AlBasrah_RAAS_v1
AlBasrah_Seed_v1
AlBasrah_Skirmish_v1
AlBasrah_Skirmish_v2
//AlBasrah_TC_v1

//Anvil_AAS_v1
//Anvil_Invasion_v1
//Anvil_RAAS_v1
//Anvil_RAAS_v2
Anvil_Skirmish_v1
//Anvil_TC_v1

//Belaya_AAS_v1
//Belaya_AAS_v2
//Belaya_AAS_v3
//Belaya_Invasion_v1
//Belaya_Invasion_v2
//Belaya_RAAS_v1
Belaya_Skirmish_v1
//Belaya_TC_v1

//BlackCoast_AAS_v1
//BlackCoast_AAS_v2
//BlackCoast_Invasion_v1
//BlackCoast_Invasion_v2
//BlackCoast_RAAS_v1
//BlackCoast_RAAS_v2
BlackCoast_Seed_v1
BlackCoast_Seed_v2
BlackCoast_Skirmish_v1

//Chora_AAS_v1
//Chora_AAS_v2
//Chora_AAS_v3
//Chora_Insurgency_v1
//Chora_Invasion_v1
//Chora_Invasion_v2
//Chora_RAAS_v1
Chora_Skirmish_v1
//Chora_TC_v1

//Fallujah_AAS_v1
//Fallujah_Insurgency_v1
//Fallujah_Invasion_v1
//Fallujah_Invasion_v2
//Fallujah_RAAS_v1
//Fallujah_RAAS_v2
Fallujah_Seed_v1
Fallujah_Skirmish_v1
Fallujah_Skirmish_v2
//Fallujah_TC_v1

//FoolsRoad_AAS_v1
//FoolsRoad_AAS_v2
//FoolsRoad_Destruction_v1
//FoolsRoad_Invasion_v1
//FoolsRoad_RAAS_v1
//FoolsRoad_RAAS_v2
//FoolsRoad_RAAS_v3
FoolsRoad_Skirmish_v1
FoolsRoad_Skirmish_v2
//FoolsRoad_TC_v1

//GooseBay_AAS_v1
//GooseBay_Invasion_v1
//GooseBay_RAAS_v1
//GooseBay_RAAS_v2
GooseBay_Seed_v1
GooseBay_Skirmish_v1

//Gorodok_AAS_v1
//Gorodok_Destruction_v1
//Gorodok_Insurgency_v1
//Gorodok_Invasion_v1
//Gorodok_Invasion_v2
//Gorodok_RAAS_v1
//Gorodok_RAAS_v2
Gorodok_Skirmish_v1
//Gorodok_TC_v1

//Harju_AAS_v1
//Harju_AAS_v2
//Harju_AAS_v3
//Harju_Invasion_v1
//Harju_Invasion_v2
//Harju_Invasion_v3
//Harju_RAAS_v1
//Harju_RAAS_v2
Harju_Skirmish_v1
Harju_Skirmish_v2
Harju_Seed_v1
//Harju_TC_v1

//Kamdesh_AAS_v1
//Kamdesh_Insurgency_v1
//Kamdesh_Invasion_v1
//Kamdesh_RAAS_v1
Kamdesh_Skirmish_v1
//Kamdesh_TC_v1

//Kohat_AAS_v1
//Kohat_Insurgency_v1
//Kohat_Invasion_v1
//Kohat_RAAS_v1
Kohat_Skirmish_v1
//Kohat_TC_v1

//Kokan_AAS_v1
//Kokan_AAS_v2
//Kokan_Insurgency_v1
//Kokan_Invasion_v1
//Kokan_RAAS_v1
//Kokan_RAAS_v2
Kokan_Skirmish_v1
//Kokan_TC_v1

//Lashkar_AAS_v1
//Lashkar_AAS_v2
//Lashkar_Insurgency_v1
//Lashkar_Invasion_v1
//Lashkar_RAAS_v1
Lashkar_Skirmish_v1
//Lashkar_TC_v1
//Lashkar_TC_v2

//Logar_AAS_v1
//Logar_Insurgency_v1
//Logar_RAAS_v1
Logar_Seed_v1
Logar_Skirmish_v1
//Logar_TC_v1

//Manicouagan_AAS_v1
//Manicouagan_AAS_v2
//Manicouagan_AAS_v3
//Manicouagan_Invasion_v1
//Manicouagan_RAAS_v1
//Manicouagan_RAAS_v2
Manicouagan_Seed_v1
Manicouagan_Skirmish_v1
Manicouagan_Skirmish_v2
Manicouagan_Skirmish_v3

//Mestia_AAS_v1
//Mestia_AAS_v2
//Mestia_Invasion_v1
//Mestia_RAAS_v1
Mestia_Skirmish_v1
//Mestia_TC_v1

//Mutaha_AAS_v1
//Mutaha_AAS_v2
//Mutaha_Invasion_v1
//Mutaha_RAAS_v1
//Mutaha_RAAS_v2
Mutaha_Seed_v1
Mutaha_Skirmish_v1
//Mutaha_TC_v1

//Narva_AAS_v1
//Narva_AAS_v2
//Narva_AAS_v3
//Narva_Destruction_v1
//Narva_Invasion_v1
//Narva_Invasion_v2
//Narva_RAAS_v1
Narva_Skirmish_v1
//Narva_TC_v1

//PacificProvingGrounds_AAS_v1
PacificProvingGrounds_Seed_v1

//Sanxian_AAS_v1
//Sanxian_AAS_v2
//Sanxian_AAS_v3
//Sanxian_Invasion_v1
//Sanxian_Invasion_v2
//Sanxian_RAAS_v1
//Sanxian_RAAS_v2
Sanxian_Seed_v1
Sanxian_Skirmish_v1

//Skorpo_Invasion_v1
//Skorpo_Invasion_v2
//Skorpo_RAAS_v1
Skorpo_Skirmish_v1

//Sumari_AAS_v1
//Sumari_AAS_v2
//Sumari_AAS_v3
//Sumari_Insurgency_v1
//Sumari_Invasion_v1
//Sumari_RAAS_v1
Sumari_Seed_v1
Sumari_Skirmish_v1
//Sumari_TC_v1

//Tallil_AAS_v1
//Tallil_Invasion_v1
//Tallil_RAAS_v1
//Tallil_RAAS_v2
Tallil_Seed_v1
Tallil_Skirmish_v1
Tallil_Skirmish_v2
Tallil_Skirmish_v3
//Tallil_TC_v1

//Yehorivka_AAS_v1
//Yehorivka_AAS_v2
//Yehorivka_Destruction_v1
//Yehorivka_Invasion_v1
//Yehorivka_Invasion_v2
//Yehorivka_RAAS_v1
//Yehorivka_RAAS_v2
Yehorivka_Skirmish_v1
Yehorivka_Skirmish_v2
//Yehorivka_TC_v1
//Yehorivka_TC_v2
```

### LayerVotingNight.cfg

* 这是指定时间投票系统地图池，在这里可以设置指定时间时投票系统允许选择的地图
* 当“MapRotationMode=LayerList\_Vote”时 这个指定时间投票系统才能生效
* 此文件仅在 **Server.cfg-NightTime** 中定义的选定时间内使用

<mark style="color:red;">**此处将不列出全部图层，您可参考“**</mark>[<mark style="color:red;">**LayerRotation.cfg**</mark>](./#layerrotation.cfg)<mark style="color:red;">**”下列出的图层**</mark>

### LevelRotation.cfg

* 这是地图池，在这里您可以设置服务器可游玩的地图
* 当“MapRotationMode=LevelList”时 这个地图池才能生效
* 地图池是逐行顺序读取的，也就是说行数靠前的图层将优先被录取

以下列出了所有地图，您可将不需要的地图删除（或打上//），这样他们就被移除了。

```
AlBasrah
Anvil
Belaya
BlackCoast
Chora
Fallujah
FoolsRoad
GooseBay
Gorodok
Harju
Kamdesh
Kohat
Kokan
Lashkar
Logar
Manicouagan
Mestia
Mutaha
Narva
PacificProvingGrounds
Sanxian
Skorpo
Sumari
Tallil
Yehorivka
```

### **MOTD.cfg**

* 这是服务器规则文件，在此文件的内容将会在游戏内服务器规则显示。
* 这非常适合显示服务器信息、简单规则或其他消息。但请注意，输入到此文件中的文本不会在游戏中换行，并且会溢出视图。

以下列出了允许在 **MOTD.cfg** 中使用的HTML命令：

```
<a>黄色字体</a>
<a href="https://squadovo.cn">黄色字体链接</a>
```

### **Rcon.cfg**

* 如果您不想使用 **远程管理\[Rcon]**，请将密&#x7801;**（Password）**&#x8BBE;置为空。
* 如果**IP**为 0.0.0.0，那么即为本机上的所有IP

```
// 远程管理[Rcon] IP
// 或者，在命令行中使用以下参数来设置：
//   RCONIP=0.0.0.0
IP=0.0.0.0

// 远程管理[Rcon] 端口
// 或者，在命令行中使用以下参数来设置：
//   RCONPORT=21114
Port=21114

// 远程管理[Rcon] 密码
// 如果为空，则关闭 远程管理[Rcon]。
// 或者，在命令行中使用以下参数来设置：
Password=

// 远程管理[Rcon] 并发数量
// 同时使用 Rcon 连接到服务器的最大数量
MaxConnections=5

// 远程管理[Rcon] 超时时间（秒）
// 可选值为：30 - 3600
SecondsBeforeTimeoutCheck=120
```

### RemoteAdminListHosts.cfg

* 如果您运行多个服务器并希望为所有服务器使用一个 admin 文件，则应使用此方法。
* 如果玩家在多个文件中列出，则他们的权限将合并
* 每行应包含指向 admin 文件的 URL

### RemoteBanListHosts.cfg

* 如果您运行多个服务器并希望为所有服务器使用一个 ban 文件，则应使用此方法。
* 此方法还适用于联合封禁。
* 每行应包含指向 ban 文件的 URL。

### **Server.cfg**

* 这是通用的服务器配置文件。每个变量都应该在自己的行上。
* 此 wiki 将添加新内容。由于我们不会覆盖配置文件，因此如果您想更改默认值，则需要手动将它们添加到现有的服务器配置中。
* 如果服务器名称的特殊字符在 **服务器列表** 中显示为 "?????"，解决方法：将特殊字符粘贴到文本编辑器，然后再复制到配置文件。示例：`ServerName="Test Server Λ"`
* **AutoTkBanTime：**&#x6B64;功能为自带TK封禁系统，当一局超过限定TK数量后将被服务器封禁，<mark style="color:red;">并且管理员无法解除此封禁</mark>

```
// 在这里设置你的服务器名字
ServerName=""

// 设置服务器密码，为空则无密码
ServerPassword=

// 控制在服务器浏览器中的可见性
ShouldAdvertise=true

// 将服务器设置为局域网模式
IsLANMatch=false

// 服务器上的最大玩家数
MaxPlayers=100

// 预留位数量
NumReservedSlots=2

// 允许最大的排队人数
PublicQueueLimit=25

// 允许加入服务器的时间，如果超出你设置的值将会被不允许加入服务器
JoiningPlayerTimeout=120

// 服务器标签
// 使用空格作为分隔符，例如：
// Tags=language_en language_nl mode_aas mode_raas
// 有关更多信息和完整的标签列表，请参考 https://docx.squadovo.cn/docx/server/server/config/label
Tags=

// 服务器规则的标签形式
// 使用空格作为分隔符，例如：
// Rules=rule_vehicle_name_claim rule_play_objective rule_no_main_camping rule_no_soloing_vehicle
// 有关更多信息和完整的规则标签列表，请参考 https://docx.squadovo.cn/docx/server/server/config/rules
Rules=

// 地图旋转模式：它可以是
// LevelList（使用级别旋转配置文件中的顺序）
// LayerList（使用图层旋转配置文件中的顺序）
// LayerList_Vote（在比赛结束时投票选择）
// 或者
// LevelList_Randomized
// LayerList_Randomized
// 这些是前面选项的随机化版本
MapRotationMode=LayerList_Vote

// 是否应该在开始时随机化地图/图层旋转列表？
RandomizeAtStart=true

// 是否应该在通用图层上为阵营进行投票？如果为假，则随机化。
UseVoteFactions=false

// 是否应该在回合结束时为下一个地图进行投票？
UseVoteLevel=false

// 是否应该在回合结束时为下一个图层进行投票？
UseVoteLayer=false

// 完全允许或禁止所有玩家更换队伍。只有具有Level_Balance访问级别的用户可以绕过此标志
AllowTeamChanges=true

// 如果设置为false，玩家可以不考虑队伍平衡情况下更换队伍。否则，将使用NumPlayersDiffForTeamChanges值
PreventTeamChangeIfUnbalanced=true

// 队伍之间允许的最大玩家数量差异。这考虑了玩家离开的队伍和玩家加入的队伍
NumPlayersDiffForTeamChanges=1

// 被踢出小队后重新加入小队的延迟时间
RejoinSquadDelayAfterKick=180 
// 禁用录制演示功能
RecordDemos=false

// 是否允许公共客户端进行录制。
// 如果你不希望公共客户端进行录制，但你想允许某些客户端进行录制，你可以给予他们"ClientDemos"的管理员访问级别。
// "ClientDemos"和"Demos"之间有区别。"Demos"允许访问服务器命令来录制服务器端的演示，而"ClientDemos"只允许客户端演示（没有管理员命令）
AllowPublicClientsToRecord=false

// 服务器消息间隔时间，单位为秒。
ServerMessageInterval=120

// 强制服务器每X秒进行非无缝旅行（更换地图时断开连接）
// 如果注释掉这个参数则不会进行非无缝旅行
// ForceNonSeamlessTravelIntervalSeconds=43200

// 以下是许可服务器所需的，但对于非许可服务器可以更改
// 启用自动踢出队友伤害者功能
TKAutoKickEnabled=true
// 自动禁止玩家的队友伤害次数阈值
AutoTKBanNumberTKs=10
// 禁止玩家因队友伤害的时间（单位为秒）
AutoTKBanTime=300
// 禁用车辆套件要求功能，为假即启用车辆套件要求
VehicleKitRequirementDisabled=false
// 允许社区管理员访问权限
AllowCommunityAdminAccess=true

// Offworld Industries的开发者是管理员
AllowDevProfiling=true

AllowQA=true

// 下面的命令对所有服务器都是可选的
VehicleClaimingDisabled=false
```

### **ServerMessages.cfg**

* 这是服务器红字提醒文件，每行则为一条信息。
* 决定消息发送间隔时间的参数为“ServerMessageInterval”（在 server.cfg 中）

### VoteConfig.cfg

* 这是投票系统配置文件，当“MapRotationMode=LayerList\_Vote”时 才能生效

```
// 当使用投票系统时，此值让你控制显示的地图选项。可能的值范围从2-6
LayerOptionsNumber=6

// 下一层的投票阶段的持续时间（单位为秒）
LayerVoteDuration=25

// 每个派系/团队的投票阶段持续时间（单位为秒）
TeamVote_Duration=20

// 在投票期间，团队/派系选择屏幕上将展示多少选项。可能的值范围从2-6
TeamVoteOptionsNumber=4

// 如果比赛结束时玩家数量少于此数字，则下一轮投票将使用“LayerVotingLowPlayers.cfg”中的特殊地图池
LowPlayerCountThreshold=30

// 为了在下一场比赛投票中延迟重复选项的特殊规则
// 在连续的投票中，同一张地图被跳过的轮数。这里的值为1，意味着一旦某个地图被选中，下一轮投票中该地图将被跳过。
MapSkipRounds=1
// 在连续的投票中，同一游戏模式被跳过的轮数。这里的值为1，表示一旦某个游戏模式被选中，下一轮投票中该模式将被跳过。
GameModeSkipRounds=0
// 在连续的投票中，同一层级（Layer）被跳过的轮数。这里的值为1，表示一旦某个层级被选中，下一轮投票中该层级将被跳过。
LayerSkipRounds=1
// 在连续的投票中，同一派系被跳过的轮数。这里的值为1，表示一旦某个派系被选中，下一轮投票中该派系将被跳过。
FactionSkipRounds=1
// 在连续的投票中，同一派系配置被跳过的轮数。这里的值为1，表示一旦某个派系配置被选中，下一轮投票中该配置将被跳过。
FactionSetupSkipRounds=1

// 是否允许地图投票时可以刷新选项
CanRegenerateLayerList=true

// 是否允许阵营投票时可以刷新选项
CanRegenerateFactionList=true

// 投票时是否显示详细的投票信息（每个选项的票数）
DisplayVotes=true

// 投票时是否显示对方的投票信息情况
DisplayEnemyInfo=true

// 投票模式下开始的第一层。这一层将在每次服务器启动时作为默认加载
FirstLayer=AlBasrah_AAS_v1
```



