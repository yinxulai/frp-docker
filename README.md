# Frp Docker

## Usage

### Server

Please specify your own server configuration file, the default is to use the official configuration file to start.

- Configuration mount path: `/etc/frp/frps.toml`

```bash
docker run -d -v {your configuration file}:/etc/frp/frps.toml yinxulai/frp-server
```

### Client

Please specify your own client configuration file, the default is to use the official configuration file to start.

- Configuration mount path: `/etc/frp/frpc.toml`

```bash
docker run -d -v {your configuration file}:/etc/frp/frpc.toml yinxulai/frp-client
```
