# Frp Docker

[中文文档](/README_CN.md) | [English Documentation](/README_CN.md)

## 使用

### 服务端

请指定自己的服务端配置文件，默认使用官方配置文件启动。

- 配置挂载路径：`/etc/frp/frps.toml`

```bash
docker run -d -v {你的配置文件}:/etc/frp/frps.toml yinxulai/frp-server
```

### 客户端

请指定自己的客户端配置文件，默认使用官方配置文件启动。

- 配置挂载路径：`/etc/frp/frpc.toml`

```bash
docker run -d -v {你的配置文件}:/etc/frp/frpc.toml yinxulai/frp-client
```

### 时区

当前时区默认为 `Asia/Shanghai`
