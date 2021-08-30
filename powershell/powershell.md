# powershell

## 运行

```sh
# C:\Windows\System32 下的直接运行

# 路径有空格
& '<path>'
```

## cmdlet 动词-名词结构

```sh
Get-Command
# 帮助,可查看别名
Get-Help
Get-Member
# 历史
Get-History

# 外部调用
Powershell "& '<path>'"

# 执行状态
$lastExitCode
$?

# 计算命令执行时间
Measure-Command {<cmd>}

# 重定向
<cmd> | Out-File <file>
# 或者
<cmd> > <file>

# 记录会话
Start-Transcript -Path <path>
Stop-Transcript
```

## 管道

<https://docs.microsoft.com/zh-cn/powershell/module/microsoft.powershell.core/about/about_pipelines?view=powershell-7.1>

```powershell
Select-Object
Where-Object
Sort-Object
Group-Object
Measure-Object
ForEach-Object
Tee-Object
Compare-Object
Format-List
Format-Table
Get-Member
Format-Wide
```

## example

```powershell
Get-NetFirewallRule | Format-Table

Set-NetFirewallProfile -All -Enabled True

Remove-NetFirewallRule -DisplayName 'mysql'

New-NetFirewallRule -DisplayName 'mysql' -Direction Inbound -Action Allow -Protocol TCP -LocalPort 3306 -RemoteAddress "10.147.18.200-10.147.18.254"
```
