# 管理指令集（管理命令）

{% hint style="success" %}
想当 Squad 服主？50 元/月起就能拿下入门款专属服务器！[南赛云](https://server.squadovo.cn/)是高性价比开服首选，低价不低质，让您轻松启动专属战局，低成本圆服主梦～
{% endhint %}

## 查询玩家信息

命令：**ListPlayers**

RCON：允许

返回：ID：0 | SteamID：…… | Name：stellar | team ID：1 | Squad ID：N/A | Is Leader：False | Role：……

意味玩家ID为0，SteamID为……，玩家名称为stellar，阵营ID为1，没有小队，不是队长，当前阵营国家为……&#x20;

## 查找小队信息

命令：**ListSquad**

RCON：允许

返回：ID：1 | Name：小队1 | Size：1 | Locked：False | Creator Name：stellar | Creator Steam ID：……

意味1队，队伍名称是小队1，队内玩家一人，没有锁队，创造者名称stellar，创造者Steam ID为……&#x20;

## 踢出玩家 <a href="#adminkick" id="adminkick"></a>

命令：**AdminKick**

所需权限：kick

RCON：允许

参数：Adminkick <昵称或SteamID或EOSID> <踢出理由>

示例：`AdminKick nansai TK`

## 踢出玩家（编号） <a href="#adminkickbyid" id="adminkickbyid"></a>

命令：**AdminKickById**

所需权限：kick

RCON：允许

参数：AdminKickById <玩家编号> <踢出理由>

示例：`AdminKickById 1 TK`

## 封禁玩家 <a href="#adminban" id="adminban"></a>

命令：**AdminBan**

所需权限：ban

RCON：允许

封禁时长格式：0=永久，1d=一天，1M=一月。

参数：AdminBan <昵称或SteamID或EOSID> <封禁时长> <封禁理由>

示例：`AdminBan nansai 0 tk`

## 封禁玩家（编号） <a href="#adminbanbyid" id="adminbanbyid"></a>

命令：**AdminBanById**

所需权限：ban

RCON：允许

封禁时长格式：0=永久，1d=一天，1M=一月。

参数：AdminBanById <玩家编号> <封禁时长> <封禁理由>

示例：`AdminBan 75 0 tk`

## 发送广播信息 <a href="#adminbroadcast" id="adminbroadcast"></a>

命令：**AdminBroadcast**

所需权限：chat

RCON：允许

参数：AdminBroadcast <广播信息>

示例：`AdminBroadcast TK后请道歉！`

## 发送 Admin 信息 <a href="#chattoadmin" id="chattoadmin"></a>

命令：**ChatToAdmin**

所需权限：chat

RCON：允许

参数：ChatToAdmin <信息>

示例：`ChatToAdmin example`

## 立即结束对局 <a href="#adminendmatch" id="adminendmatch"></a>

命令：**AdminEndMatch**

所需权限：pause

RCON：允许

示例：`AdminEndMatch`

## 暂停对局 <a href="#adminpausematch" id="adminpausematch"></a>

命令：**AdminPauseMatch**

所需权限：pause

RCON：允许

示例：`AdminPauseMatch`

## 继续对局 <a href="#adminunpausematch" id="adminunpausematch"></a>

命令：**AdminUnpauseMatch**

所需权限：pause

RCON：允许

示例：`AdminUnpauseMatch`

## 切换地图 <a href="#adminchangelayer" id="adminchangelayer"></a>

命令：**AdminChangeLayer**

所需权限：changemap

RCON：允许

参数：AdminChangeLayer <地图名称>

示例：`AdminChangeLayer Albasrah_AAS_v1`

## 预设下一张地图 <a href="#adminsetnextlayer" id="adminsetnextlayer"></a>

命令：**AdminSetNextLayer**

所需权限：changemap

RCON：允许

参数：AdminSetNextLayer <地图名称>

示例：`AdminSetNextLayer Albasrah_AAS_v1`

## 设置服务器玩家最大人数 <a href="#adminsetmaxnumplayers" id="adminsetmaxnumplayers"></a>

命令：**AdminSetMaxNumPlayers**

所需权限：config

RCON：允许

参数：AdminSetMaxNumPlayers <最大玩家数量>

示例：`AdminSetMaxNumPlayers 95`

## 更改服务器密码 <a href="#adminsetserverpassword" id="adminsetserverpassword"></a>

命令：**AdminSetServerPassword**

所需权限：config

RCON：允许

描述：参数为空时即设置为无密码

参数：AdminSetServerPassword <服务器密码>

示例：`AdminSetServerPassword 112233`

## 设置时间流速 <a href="#adminslomo" id="adminslomo"></a>

命令：**AdminSlomo**

所需权限：cheat

RCON：允许

描述：基础倍率为 1

参数：AdminSlomo <时间倍率>

示例：`AdminSlomo 1`

## 强制玩家跳边 <a href="#adminforceteamchange" id="adminforceteamchange"></a>

命令：**AdminForceTeamChange**

所需权限：forceteamchange

RCON：允许

参数：AdminForceTeamChange <昵称或SteamID或EOSID>

示例：`AdminForceTeamChange nansai`

## 强制玩家跳边（编号） <a href="#adminforceteamchangebyid" id="adminforceteamchangebyid"></a>

命令：**AdminForceTeamChangeById**

所需权限：forceteamchange

RCON：允许

参数：AdminForceTeamChangeById <玩家编号>

示例：`AdminForceTeamChangeById 75`

## 设置是否忽略部署物生成规则 <a href="#adminforcealldeployableavailability" id="adminforcealldeployableavailability"></a>

命令：**AdminForceAllDeployableAvailability**

所需权限：cheat

RCON：允许

描述：0 为关闭，1 为开启

参数：AdminForceAllDeployableAvailability <0>|<1>

示例：`AdminForceAllDeployableAvailability 0`

## 取消载具认领权限 <a href="#admindisablevehicleclaiming" id="admindisablevehicleclaiming"></a>

命令：**AdminDisableVehicleClaiming**

所需权限：cheat

RCON：允许

描述：0 为关闭，1 为开启

参数：AdminDisableVehicleClaiming <0>|<1>

示例：`AdminDisableVehicleClaiming 0`

## 飞天状态传送

命令：**AdminTeleportToPlayer**

RCON：不允许

参数：AdminTeleportToPlayer <目标人物名称>

示例：`AdminTeleportToPlayer nansai`

## 飞天状态传送（编号）

命令：**AdminTeleportToPlayerById**

RCON：不允许

参数：AdminTeleportToPlayerById <目标人物ID>&#x20;

示例：`AdminTeleportToPlayerById 1`

## 取消兵种限制 <a href="#adminforceallroleavailability" id="adminforceallroleavailability"></a>

命令：**AdminForceAllRoleAvailability**

所需权限：cheat

RCON：允许

描述：0 为关闭，1 为开启

参数：AdminForceAllRoleAvailability <0>|<1>

示例：`AdminForceAllRoleAvailability 1`

## 开启网络测试并显示客户端日志 <a href="#adminnetteststart" id="adminnetteststart"></a>

命令：**AdminNetTestStart**

所需权限：debug

RCON：不允许

示例：`AdminNetTestStart`

## 结束网络测试并显示客户端日志 <a href="#adminnetteststop" id="adminnetteststop"></a>

命令：**AdminNetTestStop**

所需权限：debug

RCON：不允许

示例：`AdminNetTestStop`

## 列出最近断开连接的玩家 <a href="#adminlistdisconnectedplayers" id="adminlistdisconnectedplayers"></a>

命令：**AdminListDisconnectedPlayers**

所需权限：kick

RCON：允许

示例：`AdminListDisconnectedPlayers`

## 取消复活时间

命令：**AdminNoRespawnTime**r

RCON：允许

所需权限：cheat

描述：0 为关闭，1 为开启

参数：AdminNoRespawnTimer <0>|<1>

示例：`AdminNoRespawnTimer 0`

## 生成载具 <a href="#admincreatevehicle" id="admincreatevehicle"></a>

命令：**AdminCreateVehicle**

所需权限：featuretest

RCON：不允许

参数：AdminCreateVehicle <[载具路径](zai-ju-shua-xin-ming-ling.md)>

示例：`AdminCreateVehicle /Game/Vehicles/Minsk_motorbike/BP_minsk.BP_minsk_C`

错误提示：若显示 "<mark style="color:$danger;">I</mark><mark style="color:$danger;">nvalid Class! (Did you forget the '\_C'?)</mark>"，表示路径末尾缺少`_C`或拼写错误

## 生成部署物 <a href="#admindemotecommander" id="admindemotecommander"></a>

命令：AdminCreateDeployable

所需权限：featuretest

RCON：不允许

参数：AdminCreateDeployable <[部署物路径](bu-shu-wu-shua-xin-ming-ling.md)>

示例：`AdminCreateDeployable /Game/Gameplay/Deployables/Emplacements/BP_2b14podnosmortar_Deployable.BP_2b14podnosmortar_Deployable_C`

## 卸任指挥官 <a href="#admindemotecommander" id="admindemotecommander"></a>

命令：**AdminDemoteCommander**

所需权限：kick

RCON：允许

参数：AdminDemoteCommander <玩家昵称>

示例：`AdminDemoteCommander nansai`

## 卸任指挥官（编号） <a href="#admindemotecommanderbyid" id="admindemotecommanderbyid"></a>

命令：**AdminDemoteCommanderById**

所需权限：kick

RCON：允许

参数：AdminDemoteCommanderById <玩家编号>

示例：`AdminDemoteCommanderById 75`

## 解散小队 <a href="#admindisbandsquad" id="admindisbandsquad"></a>

命令：**AdminDisbandSquad**

所需权限：kick

RCON：允许

参数：AdminDisbandSquad <阵营编号=\[1|2]> <队伍编号>

示例：`AdminDisbandSquad 1 3`

## 将玩家从小队中移除 <a href="#adminremoveplayerfromsquad" id="adminremoveplayerfromsquad"></a>

命令：**AdminRemovePlayerFromSquad**

所需权限：kick

RCON：允许

参数：AdminRemovePlayerFromSquad <玩家昵称>

示例：`AdminRemovePlayerFromSquad nansai`

## 将玩家从小队中移除（编号） <a href="#adminremoveplayerfromsquadbyid" id="adminremoveplayerfromsquadbyid"></a>

命令：**AdminRemovePlayerFromSquadById**

所需权限：kick

RCON：允许

参数：AdminRemovePlayerFromSquadById <玩家编号>

示例：`AdminRemovePlayerFromSquad 75`

## 警告玩家 <a href="#adminwarn" id="adminwarn"></a>

命令：**AdminWarn**

所需权限：kick

RCON：允许

参数：AdminWarn <玩家昵称或SteamID> <警告信息>

示例：`AdminWarn nansai 不要伤害队友！`

## 警告玩家（编号） <a href="#adminwarnbyid" id="adminwarnbyid"></a>

命令：**AdminWarnById**

所需权限：kick

RCON：允许

参数：AdminWarnById <玩家编号> <警告信息>

示例：`AdminWarnById 75 不要伤害队友！`

## 在服务器上开始分析 <a href="#adminprofileserver" id="adminprofileserver"></a>

命令：**AdminProfileServer**

所需权限：debug

RCON：允许

参数：AdminProfileServer <记录时长> <\[0|1]>

示例：`AdminProfileServer 1 1`

## 重新开始对局 <a href="#adminrestartmatch" id="adminrestartmatch"></a>

命令：**AdminRestartMatch**

所需权限：pause

RCON：允许

示例：`AdminRestartMatch`

## 设置服务器最大排队人数 <a href="#adminsetpublicqueuelimit" id="adminsetpublicqueuelimit"></a>

命令：AdminSetPublicQueueLimit

所需权限：config

RCON：允许

参数：AdminSetPublicQueueLimit <最大排队人数>

示例：`AdminSetPublicQueueLimit 25`

## 关闭更换阵营冷却时间

RCON：允许

描述：0 为关闭，1 为开启

参数：AdminNoTeamChangeTimer <0>|<1>

示例：`AdminNoTeamChangeTimer 0`
