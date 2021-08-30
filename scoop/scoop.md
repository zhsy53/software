# scoop

<https://github.com/lukesampson/scoop/wiki/Quick-Start>

<https://scoop-docs.vercel.app/docs/>

## install

```powershell
# 检查
$psversiontable.psversion.major # should be >= 5.0

# 权限
set-executionpolicy remotesigned -scope currentuser

# 自定义目录(可选)
$env:SCOOP='D:\scoop\user'
$env:SCOOP_GLOBAL='d:\scoop\global'

# 代理(可选) TODO:没成功
[net.webrequest]::defaultwebproxy = new-object net.webproxy "http://127.0.0.1:1081"

# 安装
Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')
# 或者
# iwr -useb get.scoop.sh | iex
```

## software list

<https://scoop-docs.vercel.app/apps>

```powershell
scoop install sudo
scoop install git vim openssh --global
scoop install maven

# add bucket
scoop bucket add java
scoop install openjdk openjdk11
scoop reset openjdk11
scoop install graalvm-jdk11

# add bucket
scoop bucket add jetbrains

# add bucket
scoop bucket add extras
scoop install postman

# add bucket
# https://github.com/c0re100/qBittorrent-Enhanced-Edition
scoop bucket add dorado https://github.com/chawyehsu/dorado
scoop install qbittorrent-enhanced
```
