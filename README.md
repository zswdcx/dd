# 萌咖大佬的一键DD脚本

## 注意:

全自动安装默认root密码:```MoeClub.org```,安装完成后请立即更改密码.

能够全自动重装Debian/Ubuntu/CentOS系统.

同时提供dd安装镜像功能,例如: 全自动无救援dd安装windows系统

全自动安装CentOS时默认提供VNC功能,可使用VNC Viewer查看进度,

VNC端口为``` 1``` 或者``` 5901``` ,可自行尝试连接.(成功后VNC功能会消失.)

特别注意:OpenVZ构架不适用.

## 快速一键脚本

DD debian 10示例：

```
wget -N --no-check-certificate https://raw.githubusercontent.com/zswdcx/dd/master/InstallNET.sh && chmod +x InstallNET.sh && ./InstallNET.sh -d 10 -v 64 -p "自定义root密码" -port "自定义ssh端口"
```

## 关于debian8源报错

在脚本中可以添加 --mirror 参数切换源。
目前可用的源:

```
--mirror 'http://cpgs.fdcservers.net/debian/'
--mirror 'http://proyectos.uls.edu.sv/debian/'
--mirror 'http://debian.cabletel.com.mk/debian/'
--mirror 'http://komo.padinet.com/debian/'
--mirror 'http://www.debian.uz/debian/'
```

安装debian8 示例:

```
bash InstallNET.sh -d 8 -v 64 -a --mirror 'http://debian.cabletel.com.mk/debian/'
```

安装dd镜像 示例:

```
bash InstallNET.sh -dd "[URL]" --mirror 'http://debian.cabletel.com.mk/debian/'
```

## 确保安装了所需软件:

```
#Debian/Ubuntu:
apt install -y xz-utils openssl gawk file
 
#RedHat/CentOS:
yum install -y xz openssl gawk file
```

## 如果出现了错误,请运行:

```
#Debian/Ubuntu:
apt update
 
#RedHat/CentOS:
yum update
```

## 下载及说明:

```
wget --no-check-certificate -qO InstallNET.sh 'https://raw.githubusercontent.com/zswdcx/dd/master/InstallNET.sh' && chmod +x InstallNET.sh
```

```
Usage:
        bash InstallNET.sh      -d/--debian [dist-name]
                                -u/--ubuntu [dist-name]
                                -c/--centos [dist-version]
                                -v/--ver [32/i386|64/amd64|arm64/aarch64]
                                --ip-addr/--ip-gate/--ip-mask
                                -apt/-yum/--mirror
                                -dd/--image
                                -a/-m
 
# dist-name: 发行版本代号
# dist-version: 发行版本号
# -apt/-yum/--mirror : 使用定义镜像
# -a/-m : 询问是否能进入VNC自行操作. -a 为不提示(一般用于全自动安装), -m 为提示.
```

## 使用示例:

```
#使用默认镜像全自动安装
bash InstallNET.sh -d 8 -v 64 -a
bash InstallNET.sh -d 9 -v 64 -a
bash InstallNET.sh -d 10 -v 64 -a
分别表示自动安装Debian 8x64  9x64 10x64
 
#使用自定义镜像全自动安装
bash InstallNET.sh -c 6.9 -v 64 -a --mirror 'http://mirror.centos.org/centos'
 
 
# 以下示例中,将X.X.X.X替换为自己的网络参数.
# --ip-addr :IP Address/IP地址
# --ip-gate :Gateway   /网关
# --ip-mask :Netmask   /子网掩码
 
#使用自定义镜像自定义网络参数全自动安装
#bash InstallNET.sh -u 16.04 -v 64 -a --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x --mirror 'http://archive.ubuntu.com/ubuntu'
 
#使用自定义网络参数全自动dd方式安装
#bash InstallNET.sh --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd 'https://moeclub.org/get-win7embx86-auto'
 
```

## 一些提示:

特别注意:

在dd安装系统镜像时:

在你的机器上全新安装,如果你有VNC,可以看到全部过程.

在dd安装镜像的过程中,不会走进度条(进度条一直显示为0%).完成后将会自动重启.

分区界面标题一般显示为: “Starting up the partitioner“

在全自动安装CentOS时:

如果看到 “Starting graphical installation” 或者类似表达,则表示正在安装.

正常情况下只需要耐心等待安装完成即可.

如果需要查看进度,使用VNC Viewer(或者其他VNC连接工具)

连接提示中的IP地址:端口进行连接.(端口一般为```1```或者```5901```)

转载于萌咖https://moeclub.org/2018/04/03/603/
