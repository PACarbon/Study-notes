nps-npc
nps是一款轻量级、高性能、功能强大的内网穿透代理服务器。目前支持 tcp、udp 流量转发，可支持任何tcp、udp 上层协议（访问内网网站、本地支付接口调试、ssh访问、远程桌面，内网dns解析等等……），此外还支持内网 http 代理、内网 socks5 代理、p2p 等，并带有功能强大的web管理端。
```shell
/usr/M1808/bin/npc -server=kangetsu.online:8003 -vkey=HTREMOTE_PRIVATE -type=tcp &
```
启动 npc内网穿透客户端，通过 TCP协议 连接到 kangetsu.online:8003 的NPS服务器，使用验证密钥 HTREMOTE_PRIVATE 进行认证，并在 后台运行。
```shell
kangetsu.online:8003
```
服务器域名：kangetsu.online
服务器端口：8003
```shell
-vkey=HTREMOTE_PRIVATE
```
验证密钥

验证密钥
连接协议类型
TCP连接
```shell
[tcp]
mode=tcp
target_addr=127.0.0.1:8080
server_port=10000
```
公网访问服务器IP:10000会转发到127.0.0.1:8080
