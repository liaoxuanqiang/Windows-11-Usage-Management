# Windows 11 使用管理
## Windows 系统安装
1.查询最新版 Windows11 系统信息
```
https://changewindows.org/timeline
```
2.下载[Windows11](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewiso)安装镜像

3.下载[EasyU](https://www.itsk.com/forum.php?mod=viewthread&tid=422456)制作PE启动盘

4.电脑插入U盘进入PE系统，利用磁盘工具对磁盘进行分区，之后安装系统
## Windows 系统优化
1.电源管理启动卓越性能模式
```powershell
powercfg -duplicatescheme e9a42b02-d5df-448d-aa00-03f14749eb61
```
2.关闭休眠
```powershell
powercfg -h off
```
3.关闭 VBS
```powershell
bcdedit /set hypervisorlaunchtype off
bcdedit /set hypervisorlaunchtype auto
```
4.关闭虚拟内存
5.修改组策略(gpedit.msc)禁用宽带预留
## Windows 开发环境配置
### 设置WSL开发环境
1.安装WSL
```bash
wsl --install
```
2.设置你的 Linux 用户名和密码

3.更新软件索引及安装软件包
```bash
sudo apt update && sudo apt upgrade
```
### 在WSL上使用 Visual Studio Code
1.安装 [VS Code](https://code.visualstudio.com/) 软件和[Remote WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) 插件
2.更新 Linux 系统并添加证书
```bash
sudo apt-get update
sudo apt-get install wget ca-certificates #添加 wget和 ca 证书
```
3.在 WSL 上使用 Visual Studio Code 打开项目文件
```bsah
code .
```

