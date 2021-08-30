# wsl

## 安装

<https://docs.microsoft.com/en-us/windows/wsl/install-win10>

```powershell
# 需要重启
wsl --install

# 卸载
wsl --unregister Ubuntu

# 查看
wsl --list

wsl --list -o

# 手动安装
wsl --install -d Ubuntu-20.04
```

## mirror

<https://mirrors.ustc.edu.cn/help/ubuntu.html>

<https://mirrors.tuna.tsinghua.edu.cn/help/ubuntu/>

```sh
sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list

apt update
apt upgrade
```

## 配置文件

<https://docs.microsoft.com/en-us/windows/wsl/wsl-config#configure-per-distro-launch-settings-with-wslconf>

`vim /etc/wsl.conf`

```vim
[automount]
enabled = true
mountFsTab = true
root = /mnt/
options = "metadata"

[network]
generateHosts = true
generateResolvConf = true
```

重启

`wsl --shutdown`

## 网络配置

```powershell
# wsl 网卡
Get-NetIPInterface
# vEthernet (WSL)

# 开放防火墙
New-NetFirewallRule -DisplayName "WSL" -Direction Inbound -InterfaceAlias "vEthernet (WSL)" -Action Allow

# 主机ip
ip route | grep default | awk '{print $3}'
```

```sh
apt install net-tools

# https://github.com/rofl0r/proxychains-ng
apt install proxychains4
vim /etc/proxychains4.conf
# socks5  172.19.0.1 1080
```

## ssh

<https://devblogs.microsoft.com/commandline/sharing-ssh-keys-between-windows-and-wsl-2/>

```sh
# generate
ssh-keygen -t ed25519 -C "your_email@example.com"

ln -sf /mnt/c/Users/song/.ssh ~/.ssh
```
