# scoop

<https://scoop-docs.vercel.app/docs/>

## install

```powershell
# 检查  should be >= 5.0
$psversiontable.psversion.major

# 权限
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# 自定义目录(可选,好像不行=>直接编辑环境变量)
$env:SCOOP='D:\scoop\user'
$env:SCOOP_GLOBAL='d:\scoop\global'

# 安装
Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')
# 或者
# iwr -useb get.scoop.sh | iex
```

## 常见命令

```powershell
scoop help

scoop checkup

scoop update
scoop update <app>
scoop update *

scoop bucket known
scoop bucket add <app>

scoop search <app>
scoop install [-g] <app>
```

## software list

<https://scoop-docs.vercel.app/apps>

```powershell
scoop bucket known
scoop bucket add extras
scoop bucket add versions
scoop bucket add nerd-fonts
scoop bucket add java
scoop bucket add jetbrains

scoop install sudo
scoop install git

scoop install aria2
# https://scoop-docs.vercel.app/docs/misc/Multi-connection-downloads-with-aria2.html
scoop config aria2-enabled false

scoop install maven

# font
sudo scoop install SarasaGothic

# java
scoop install openjdk openjdk11
scoop install graalvm-jdk11
scoop reset openjdk11

# postman
scoop install postman-canary

# add bucket
# https://github.com/c0re100/qBittorrent-Enhanced-Edition
scoop bucket add dorado https://github.com/chawyehsu/dorado
scoop install qbittorrent-enhanced

# tools
scoop install wget

scoop install ffmpeg
scoop install vcredist2010
```
