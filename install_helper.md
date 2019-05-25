1. 打开 WSL，没啥好说的
使用管理员权限打开 powershell,执行 
```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```
或者在程序和功能选中 WSL。
 
2.  下载 Centos 7 的docker 镜像
可以参考 https://github.com/RoliSoft/WSL-Distribution-Switcher  来下载。
或者直接下载 下面的链接给出的镜像。
https://raw.githubusercontent.com/CentOS/sig-cloud-instance-images/a77b36c6c55559b0db5bf9e74e61d32ea709a179/docker/centos-7-docker.tar.xz
 
3. 安装 chocolatey
参考 ：https://chocolatey.org/install
使用管理员权限打开 powershell,执行 
```
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
4.  安装LxRunOffline
```
choco install lxrunoffline
```
5. 使用 LxRunOffline 部署 Centos 到WSL
```
LxRunOffline.exe  install -n centos -d E:\ProgramData\Microsoft\Windows\WSL\CentOS -f  E:\ProgramData\Microsoft\Windows\WSL\centos-7-docker.tar.xz
```
其中 -d 后面是要安装到的目录，-f 是前面下载的镜像， -n 用来指定名称。
然后使用  LxRunOffine 来开启 Centos
```
LxRunOffline  run  -n centos
```
当然，如果你只安装了这一个WSL，那直接输入bash 也可以进行WSL.
