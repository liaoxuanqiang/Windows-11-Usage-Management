# 在 WSL 上使用 Visual Studio Code

## 1.安装 [VS Code](https://code.visualstudio.com) 软件和[Remote WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) 插件

## 2.更新 Linux 系统并添加证书

```bash
sudo apt-get update
sudo apt-get install wget ca-certificates #添加 wget和 ca 证书
```

## 3.在 WSL 上使用 Visual Studio Code 打开项目文件

```
code .
```
