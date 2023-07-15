# 萌咖大佬的一鍵DD腳本

## 注意:

全自動安裝默認root密碼:```MoeClub.org```,安裝完成後請立即更改密碼.

能夠全自動重裝Debian/Ubuntu/CentOS系統.

同時提供dd安裝鏡像功能,例如: 全自動無救援dd安裝windows系統

全自動安裝CentOS時默認提供VNC功能,可使用VNC Viewer查看進度,

VNC端口為``` 1``` 或者``` 5901``` ,可自行嘗試連接.(成功後VNC功能會消失.)

特別注意:OpenVZ構架不適用.

## 快速一鍵腳本

DD debian 10示例：

```
wget -N --no-check-certificate https://raw.githubusercontent.com/zswdcx/dd/master/InstallNET.sh && chmod +x InstallNET.sh && ./InstallNET.sh -d 10 -v 64 -p "自定root密碼" -port "自定ssh端口"
```

## 關於debian8源報錯

在腳本中可以添加 --mirror 參數切換源。
目前可用的源:

```
--mirror 'http://cpgs.fdcservers.net/debian/'
--mirror 'http://proyectos.uls.edu.sv/debian/'
--mirror 'http://debian.cabletel.com.mk/debian/'
--mirror 'http://komo.padinet.com/debian/'
--mirror 'http://www.debian.uz/debian/'
```

安裝debian8 示例:

```
bash InstallNET.sh -d 8 -v 64 -a --mirror 'http://debian.cabletel.com.mk/debian/'
```

安裝dd鏡像 示例:

```
bash InstallNET.sh -dd "[URL]" --mirror 'http://debian.cabletel.com.mk/debian/'
```

## 確保安裝了所需軟體:

```
#Debian/Ubuntu:
apt install -y xz-utils openssl gawk file
 
#RedHat/CentOS:
yum install -y xz openssl gawk file
```

## 如果出現了錯誤,請運行:

```
#Debian/Ubuntu:
apt update
 
#RedHat/CentOS:
yum update
```

## 下載及說明:

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
 
# dist-name: 發行版本代號
# dist-version: 發行版本號
# -apt/-yum/--mirror : 使用定義鏡像
# -a/-m : 詢問是否能進入VNC自行操作. -a 為不提示(一般用於全自動安裝), -m 為提示.
```

## 使用示例:

```
#使用默認鏡像全自動安裝
bash InstallNET.sh -d 8 -v 64 -a
bash InstallNET.sh -d 9 -v 64 -a
bash InstallNET.sh -d 10 -v 64 -a
分別表示自動安裝Debian 8x64  9x64 10x64
 
#使用自定義鏡像全自動安裝
bash InstallNET.sh -c 6.9 -v 64 -a --mirror 'http://mirror.centos.org/centos'
 
 
# 以下示例中,將X.X.X.X替換為自己的網絡參數.
# --ip-addr :IP Address/IP地址
# --ip-gate :Gateway   /網關
# --ip-mask :Netmask   /子網掩碼
 
#使用自定義鏡像自定義網絡參數全自動安裝
#bash InstallNET.sh -u 16.04 -v 64 -a --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x --mirror 'http://archive.ubuntu.com/ubuntu'
 
#使用自定義網絡參數全自動dd方式安裝
#bash InstallNET.sh --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd 'https://moeclub.org/get-win7embx86-auto'
 
```

## 一些提示:

特別注意:

在dd安裝系統鏡像時:

在你的機器上全新安裝,如果你有VNC,可以看到全部過程.

在dd安裝鏡像的過程中,不會走進度條(進度條一直顯示為0%).完成後將會自動重啟.

分區界面標題一般顯示為: “Starting up the partitioner“

在全自動安裝CentOS時:

如果看到 “Starting graphical installation” 或者類似表達,則表示正在安裝.

正常情況下只需要耐心等待安裝完成即可.

如果需要查看進度,使用VNC Viewer(或者其他VNC連接工具)

連接提示中的IP地址:端口進行連接.(端口一般為```1```或者```5901```)

轉載於萌咖https://moeclub.org/2018/04/03/603/