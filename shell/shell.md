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

# shell脚本
Shell 脚本（shell script），是一种为 shell 编写的脚本程序。Shell 是一个用 C 语言编写的程序，它是用户使用 Linux 的桥梁。

# shell环境

Shell 编程跟 JavaScript、php 编程一样，只要有一个能编写代码的文本编辑器和一个能解释执行的脚本解释器就可以了。

Linux 的 Shell 种类众多，常见的有：

Bourne Shell（/usr/bin/sh或/bin/sh）
Bourne Again Shell（/bin/bash）
C Shell（/usr/bin/csh）
K Shell（/usr/bin/ksh）
Shell for Root（/sbin/sh）
……

**Bash 是大多数Linux 系统默认的 Shell**
在一般情况下，人们并不区分 Bourne Shell 和 Bourne Again Shell，所以，像 **#!/bin/sh**，它同样也可以改为 **#!/bin/bash**。

**#!** 告诉系统其后路径所指定的程序即是解释此脚本文件的 Shell 程序。

# 第一个shell脚本

~~~
#!/bin/bash
echo "Hello World!"
~~~

* #! 是一个约定标记，告诉系统这个脚本要用什么解释器执行

## 运行shell脚本的方法

### 1.作为可执行文件

如test.sh

~~~
chmod +x ./test.sh      //使脚本具有执行权限
./test.sh       //执行脚本
~~~

ps：一定要写成 ./test.sh，而不是 test.sh，运行其它二进制的程序也一样，直接写 test.sh，linux 系统会去 PATH 里寻找有没有叫 test.sh 的，而只有 /bin, /sbin, /usr/bin，/usr/sbin 等在 PATH 里，你的当前目录通常不在 PATH 里，所以写成 test.sh 是会找不到命令的，要用 ./test.sh 告诉系统说，就在当前目录找。

### 2.作为解释器参数

这种运行方式是，直接运行解释器，其参数就是 shell 脚本的文件名

~~~
/bin/sh test.sh
/bin/php test.sh
~~~

ps:这种方式运行的脚本，不需要在第一行指定解释器信息，写了也没用。

# shell变量

在shell编程中，变量是用于存储数据值的名称。
定义变量时，变量名不需要加美元符号($,PHP语言中变量需要)

PS: **变量名和等号之间不能有空格**

命名规则
* 只包含字母、数字和下划线： 变量名可以包含字母（大小写敏感）、数字和下划线 _，不能包含其他特殊字符。

* 不能以数字开头： 变量名不能以数字开头，但可以包含数字。

* 避免使用 Shell 关键字： 不要使用Shell的关键字（例如 if、then、else、fi、for、while 等）作为变量名，以免引起混淆。

* 使用大写字母表示常量： 习惯上，常量的变量名通常使用大写字母，例如 PI=3.14。

* 避免使用特殊符号： 尽量避免在变量名中使用特殊符号，因为它们可能与 Shell 的语法产生冲突。

* 避免使用空格： 变量名中不应该包含空格，因为空格通常用于分隔命令和参数


## 语句给变量赋值
~~~
for file in 'ls /etc'
~~~

或

~~~
for file in $(ls /etc)
~~~

## 使用变量

使用一个定义过的变量，只要在变量名前面加美元符号即可
如

~~~
your_name="xue"
echo $your_name
echo ${your_name}
~~~

变量名外面的花括号是可选的，加不加都行，加花括号是为了帮助解释器识别变量的边界

比如下面这种情况：

~~~
for skill in Ada Coffe Action Java; do
    echo "I am good at ${skill}Script"
done
~~~

如果不给skill变量加花括号，写成echo "I am good at $skillScript"，解释器就会把$skillScript当成一个变量（其值为空），代码执行结果就不是我们期望的样子了。

已定义的变量，可以被重新定义

~~~
your_name="tom"
echo $your_name
your_name="alibaba"
echo $your_name
~~~










