# C++基于protobuf的分布式RPC通信框架
![result](result.png)
服务提供者：用户服务部署在8000端口下，而好友服务部署在8001端口下。

服务消费者：通过2181端口的下的zookeeper访问对应的服务提供者

## 介绍
* 使用Muduo网络库构建网络模块；
* 使用Protobuf序列化和反序列化协议实现高效RPC通信；
* 基于线程安全的缓冲队列实现异步日志输出；
* 使用ZooKeeper中间件实现分布式协调服务；
* 使用CMake集成编译环境以及一键编译shell脚本


## 使用
1. 编译项目
```bash
./autobuild.sh
```

2. 启动zookeeper
```bash
# 更换自己对应的zookeeper目录
cd ~/package/zookeeper-3.4.10/bin

# 启动
./zkServer.sh start

# 检测是否成功启动，看看2181端口是否启动，或者ps检车有没有zookeeper对应的进程
sudo netstat -tanp

ps -ef | grep zookeeper
```

3. 启动服务
```bash
# 启动提供者
cd bin
./provider -i test.conf

# 启动消费者
./consumer -i test.conf
```