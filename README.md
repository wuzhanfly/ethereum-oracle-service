# ethereum-oracle-service
以太坊Oracle后端服务

## 1、编译
```
go build
```
编译完成后查看帮助信息

```
./oracle-service -h
oracle_service version: 1.0.0
Usage: oracle_service [-h help] [-v version] [-c config path] [-l log path]
```
## 2、配置

配置信息如下：

```
# 合约地址
OracleContractAddress = ""
# 网络ws地址
NetworkWS = "ws://"
# 调用合约的私钥
PrivateKey = ""
```

## 3、运行
```
./oracle-service -c ./conf/app.conf -l logs/
```
## 4、联调
#### 4.1 部署 Oracle 合约

这里我部署后的合约地址为：0xd0d98905ab4077325115ebf08591935e41965869

#### 4.2 部署抽奖合约

这里我部署后的合约地址为：0x3d8aeb38992b10a6173e166cc8a2e088c8cace64
## 4.3 初始化抽奖合约
调用 setOracle 方法，将 Oracle 合约地址配置到抽奖合约中。

##  5 运行 Oracle 服务
合约部署完成后，配置 Oracle 服务并启动了。

#### 5.1 修改服务配置文件
配置文件需要有三项，分别是：

 OracleContractAddress Oracle 合约地址
NetworkWS 以太坊网络的 ws 地址
PrivateKey Oracle 合约的部署（owner）以太坊账户私钥
#### 5.2 运行 Oracle 服务
服务启动命令：

```
./oracle-service -c ./conf/app.conf -l logs/
```

