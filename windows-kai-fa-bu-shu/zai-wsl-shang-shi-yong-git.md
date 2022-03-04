# 在 WSL 上使用Git

Git 能安装在Window系统，也能安装在WSL。

## 1.安装 Git

```bash
sudo apt-get install git
```

## 2.配置 Git

```bash
git config --global user.name "liaoxuanqiang"
git config --global user.email "liaoxuanqiang@live.com"
```

## 3.设置 Git 凭据管理器

```
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager-core.exe"
```
