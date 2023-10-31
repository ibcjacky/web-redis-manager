# web-redis-manager #

redis的web管理客户端, 支持同时管理多个redis实例, 慢日志, 服务器信息, 配置信息, CLI模式.

> 演示案例: <http://rdm.xiusin.cn>
>
> 账号: admin 密码:123456

## 特性 ##

- basicauth
- 支持redis常用数据类型管理: `list`, `string`, `hashmap`, `set`, `sorted set`, `stream`等.
- CLI
- 慢日志
- 服务信息
- 发布订阅模式
- 图表监控

## TODO ##

- 窗口模式 frameless
- 命令行窗口每次打开时优先执行一次 `select DB` 切换当前数据库
- 发布订阅问题处理
- 图标监控进度条取消
- 大list/set/map造成页面卡顿优化

## 使用方法 ##

```shell
git clone --depth=1 https://github.com/xiusin/web-redis-manager.git
cd web-redis-manager
git checkout develop

yarn # 安装前端依赖
yarn build # 打包前端代码

cd server

go mod tidy # 下载go依赖包

go build -o rdm.exe # 编译 windows
go build -o rdm # *nix

# 非basic auth启动
./rdm.exe

# basic auth启动 (用于web端授权密码登录)
./rdm.exe --username=admin --password=123456

```

## 示意图 ##

### 入口页面 ###

![./images/1-min.png](./images/1-min.png)

### 连接实例 ###

![./images/2-min.png](./images/2-min.png)

### 管理键 ###

![./images/3-min.png](./images/3-min.png)

### 操作值 ###

![./images/4-min.png](./images/4-min.png)

### 配置信息 ###

![./images/5-min.png](./images/5-min.png)

### 服务器信息 ###

![./images/6-min.png](./images/6-min.png)

### 慢日志 ###

![./images/7-min.png](./images/7-min.png)

### CLI管理 ###

![./images/8-min.png](./images/8-min.png)
