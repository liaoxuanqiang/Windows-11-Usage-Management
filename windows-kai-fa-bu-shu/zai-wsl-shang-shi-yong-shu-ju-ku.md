# 在 WSL 上使用数据库

## 安装 MySQL

```
sudo apt update #更新 Ubuntu 包
sudo apt install mysql-server #安装 MySQL
mysql --version #确认安装并获取版本号

sudo /etc/init.d/mysql start #启动 MySQL 服务器
sudo mysql_secure_installation #启动安全脚本提示符
sudo mysql #打开 MySQL 提示符
SHOW DATABASES; # 在MySQL 提示符查看可用的数据库
CREATE DATABASE database_name; #在MySQL 提示符创建新数据库
DROP DATABASE database_name; #在MySQL 提示符删除数据库
```

## 安装 PostgreSQL

```
sudo apt update #更新 Ubuntu 包
sudo apt install postgresql postgresql-contrib #安装 PostgreSQL（和 -contrib 包，其中包含一些有用的实用程序）
psql --version #确认安装并获取版本号

sudo service postgresql status #检查数据库的状态
sudo service postgresql start #开始运行数据库
sudo service postgresql stop #停止运行数据库

sudo passwd postgres #为默认管理员用户 postgres 分配的密码
```

## 安装 MongoDB

```bash
cd ~ #转到主目录
sudo apt update #更新linux软件索引
wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add - #导入 MongoDB 包管理系统使用的公钥
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list #为 MongoDB 创建一个列表文件
sudo apt-get update #重新加载本地包数据库
sudo apt-get install -y mongodb-org #安装MongoDB包
mongod --version #确认安装并获取版本号
mkdir -p ~/data/db #创建用于存储数据的目录
sudo mongod --dbpath ~/data/db #运行Mongo实例
ps -e | grep 'mongod' #检查MongoDB实例是否正在运行
若要退出MongoDB Shell，请使用快捷键：Ctrl + C

https://raw.githubusercontent.com/mongodb/mongo/master/debian/init.d | sudo tee /etc/init.d/mongodb >/dev/null #下载 MongoDB 的 init.d 脚本
sudo chmod +x /etc/init.d/mongodb #分配该脚本可执行权限
sudo service mongodb status #检查数据库的状态
sudo service mongodb start #开始运行数据库
sudo service mongodb stop #停止运行数据库
mongo --eval 'db.runCommand({ connectionStatus: 1 })' #诊断命令验证你是否已连接到数据库服务器
```

## 安装 Microsoft SQL Server

## 安装 SQLite

```bash
sudo apt update #更新linux软件索引
sudo apt install sqlite3 #安装 SQLite3
sqlite3 --version #确认安装并获取版本号

sqlite3 example.db #创建名为“example.db”的测试数据库
.databases #查看 SQLite 数据库列表
.dbinfo ?DB? #查看数据库的状态
.exit #退出 SQLite 提示符
```

## 安装 Redis

```bash
sudo apt update #更新linux软件索引
sudo apt install redis-server #安装 Redis
redis-server --version #确认安装并获取版本号

sudo service redis-server start #开始运行 Redis 服务器
redis-cli ping #检查 redis 是否正常工作（redis-cli 是与 Redis 对话的命令行接口实用程序）
sudo service redis-server stop #停止运行 Redis 服务器
```
