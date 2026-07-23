# 如何优化连接性能

## 优化 RCON 性能

为避免 RCON 通信产生不必要的资源开销，建议修改 `ServerConfig/Rcon.cfg` 中的超时参数。

该文件内有一个控制 RCON 连接超时 的参数：

```
SecondsBeforeTimeoutCheck=3600
```

将 SecondsBeforeTimeoutCheck 的值提升至 `3600` ，更长的超时时间可以让服务器减少无用的连接开销，从而**降低资源占用、提升 RCON 指令的响应速度**。
