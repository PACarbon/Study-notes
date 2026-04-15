# SSH
Secure Shell(SSH) 是由 IETF(The Internet Engineering Task Force) 制定的建立在应用层基础上的安全网络协议。

## 远程登录命令
```shell
ssh root@服务器ip
```
## 传输文件命令
本地文件 → 远程服务器
```shell
scp 本地文件 用户名@远程IP:远程路径
```
例如
```shell
scp test.txt root@192.168.137.81:/root/
把本地 test.txt 传到远程 192.168.137.81 的 /root/ 目录
```
远程服务器 → 本地
```shell
scp 用户名@远程IP:远程文件路径 本地路径
```
例如
```shell
scp root@192.168.137.81:/root/test.txt C:\Users\HP\Desktop\
```
## 传输文件夹
```shell
scp -r 文件夹 用户名@远程IP:远程路径
```
例如
```shell
scp -r myfolder root@192.168.137.81:/root/
```


