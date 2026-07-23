# 安装部署日志解析器

## 下载

当前稳定发行版本：V1.5.1

* [SquadLogParser\_v1.5.1\_windows \_amd64\_V1.5.1.zip](https://pan.nansai.cc/s/7jTo)
* [SquadLogParser\_v1.5.1\_linux \_amd64\_V1.5.1.zip](https://pan.nansai.cc/s/w8ce)

## 安装

将下载解压好的 **Squad ovo Manage** 及 **config.ini** 文件存放到 SquadGame 目录下

（确保该目录下有**Binaries、Content、Plugins、Saved、ServerConfig**文件夹）

如果您有存在其他文件夹的需求，我们建议您参考 [进阶](install.md#jin-jie) 配置教程

## 配置

{% hint style="danger" %}
该文档中均为<mark style="color:$danger;">【</mark><mark style="color:red;">**示例值】需删除并替换为自身实际信息**</mark>
{% endhint %}

在 config.ini 中您需要配置您的服务器信息，以确保它可以正常建立通信：

```ini
[Account]
# 服务器在 Squad ovo Manage 中的唯一ID（必填，整数）
id = 8888
# 服务器 Rcon 密码（必填，需与 Squad ovo Manage 平台配置一致）
password = 123456
```

### 进阶

如果您需要指定日志文件路径以及主程序路径等，可以参考以下配置：

```ini
[Account]
# 服务器在 Squad ovo Manage 中的唯一ID（必填，整数）
id = 8888
# 服务器 Rcon 密码（必填，需与 Squad ovo Manage 平台配置一致）
password = 123456

[System]
# 日志文件路径：Windows 用反斜杠 \，Linux 用正斜杠 /
# Windows 示例：D:/Server1/SquadGame/Saved/Logs/SquadGame.log
# Linux 示例：/root/squad/server1/SquadGame/Saved/Logs/SquadGame.log
log_file = SquadGame.log
# 服务器程序路径：格式规则同上
process = SquadGameServer.exe
# 是否启动 NTP 时间同步（on 为启动，off 为关闭）
ntp_time_synchronization = on
# 本地保存程序运行日志 on=开启 off=关闭
save_log = on
# 本地日志存放文件夹
log_dir = ./logs
# 本地日志保留天数，过期自动删除（单位为天）
log_retention_days = 7
```

## **启用**

### **Windows**

#### 常规运行方式

直接双击 **Squad ovo Manage.exe** 即可启动程序（以**管理员身份**运行）

#### 命令行运行方式

基础启动（配置文件与程序同目录）：

```cmd
"Squad ovo Manage.exe"
```

指定配置文件路径启动（适用于多实例管理）：

```cmd
"Squad ovo Manage.exe" --config D:\manage\server1\config.ini
```

### Linux

如果您想要测试程序是否可以正常运行：

```
./"Squad ovo Manage"
```

如果您想要将程序作为常驻进程运行：

```
nohup "Squad ovo Manage" &
```

当前，Linux 也支持指定配置文件路径启动：

```
./"Squad ovo Manage" --config /home/squad/squad1/manage/config.ini
```

```
nohup "Squad ovo Manage" --config /home/squad/squad1/manage/config.ini &
```
