
# 连接测试网络

这篇文章向我们详细展示如何连接到EOS Cochain测试网络。最终我们可以通过这个测试网络连接到EOS主链。

## 连接指南

跟随以下说明，这个说明可以指导开发者在通过本地安装EOS Cochain，运行一个全节点连接到EOS Cochain测试网络中。


### 获取EOS Cochain

通过github下载 EOS Cochain源码和一些子模块。

```
git clone https://github.com/eoscochain/eoscochain --recursive
```

如果你没有使用 `--recursive`标签，你也可以通过以下命令继续下载EOS
 Cochain子模块。
```
git submodule update --init --recursive
```

## 构建EOS Cochain

我们建议使用最简单的方法编译EOS Cochain，即使用自动化脚本编译。

构建文件存放在 `eos/build`中，可执行文件放在它的子目录 `eos/build/programs`中。

后面我们会继续更新手动化创建EOS Cochain的文档。

#### 自动化构建脚本

使用自动化脚本可以自动安装EOS Cochain使用到的所有依赖并自动构建EOS Cochain。自动化脚本支持以下操作系统，未来我们会支持更多操作系统。

1. Amazon 2017.09 and higher
2. Centos 7
3. Fedora 25 and higher (Fedora 27 recommended)
4. Mint 18
5. Ubuntu 16.04 LTS (Ubuntu 16.10 recommended)
6. Ubuntu 18.04 LTS
7. MacOS Darwin 10.12 and higher (MacOS 10.13.x recommended)

#### 系统配置要求

* 8GB RAM 空间
* 20GB DiSK 空间
Run the build script
Run the build script from the eos folder.

#### 运行自动化构建脚本

```
cd eos
./eosio_build.sh
```
#### 验证构建文件

你可以选择运行一系列的测试文件验证有没有正确构建EOS Cochain，你需要开启mongod去运行测试文件。

**Linxu系统**

` ~/opt/mongodb/bin/mongod -f ~/opt/mongodb/mongod.conf & `

**MacOS**:

`/usr/local/bin/mongod -f /usr/local/etc/mongod.conf &`

接下来运行测试文件：
```
cd build
make test
```
#### 安装可执行文件
为了方便开发智能合约，你可以使用 `make install` 指令把EOS Cochain可执行文件放入 `/usr/local` 目录下，这一步需要在 `build` 目录下执行。为了避免出现权限管理问题，使用 `sudo` 权限是很有必要的。

```
cd build
sudo make install
```

#### 创建一个单节点测试网络
成功构建完项目之后，你可以在 `build/programs/nodeos` 目录下找到EOS
Cochain客户端可执行文件，你可以通过运行以下命令开启开启单节点测试网络：

```angular2html
cd build/programs/nodeos
./nodeos -e -p eosio --plugin eosio::chain_api_plugin --plugin eosio::history_api_plugin 
When running nodeos you should get log messages similar to below. It means the blocks are successfully produced.

1575001ms thread-0   chain_controller.cpp:235      _push_block          ] initm #1 @2017-09-04T04:26:15  | 0 trx, 0 pending, exectime_ms=0
1575001ms thread-0   producer_plugin.cpp:207       block_production_loo ] initm generated block #1 @ 2017-09-04T04:26:15 with 0 trxs  0 pending
1578001ms thread-0   chain_controller.cpp:235      _push_block          ] initc #2 @2017-09-04T04:26:18  | 0 trx, 0 pending, exectime_ms=0
1578001ms thread-0   producer_plugin.cpp:207       block_production_loo ] initc generated block #2 @ 2017-09-04T04:26:18 with 0 trxs  0 pending
...
eosio generated block 046b9984... #101527 @ 2018-04-01T14:24:58.000 with 0 trxs
eosio generated block 5e527ee2... #101528 @ 2018-04-01T14:24:58.500 with 0 trxs
...

```

#### 使用Docker构建

使用Docker简单快速的创建EOS Cochain也是可行的，你可以在Docker README里面看到EOS Cochain的关于Docker的最新信息。 

**构建EOS Cochian Docker 镜像**

```angular2html
$ git clone https://github.com/EOSIO/eos.git --recursive
$ cd eos/Docker
$ docker build . -t eosio/eos
```

**在 Docker 容器中运行 EOS Cochain 节点**

```angular2html
$ docker run --name nodeos -p 8888:8888 -p 9876:9876 -t eosio/eos nodeosd.sh arg1 arg2
```

你也可以直接将主机目录挂载到Docker容器中。

```angular2html
$ docker run --name nodeos -v /path-to-data-dir:/opt/eos/bin/data-dir -p 8888:8888 -p 9876:9876 -t eosio/eos nodeosd.sh arg1 arg2
```

**获取链的信息**
```angular2html
$ curl http://127.0.0.1:8888/v1/chain/get_info
```

**启动nodeos和keosd容器
```angular2html
docker-compose up
```

在使用 `docker-compose up` 之后，nodeos和keosd都会同时被启动，nodeos服务将把端口8888和9876暴露给主机，keosd将不会暴露任何端口，之后通过执行 cleos 命令行选项才能调用keosd服务。

**执行 cleos 命令行选项**

```angular2html
$ alias cleos='docker-compose exec keosd /opt/eos/bin/cleos -H nodeos'
$ cleos get info
$ cleos get account inita
```

**上传一个合同案例**
```angular2html
$ cleos set contract exchange contracts/exchange/exchange.wast contracts/exchange/exchange.abi
```

**关闭keosd服务**
```angular2html
$ docker-compose stop keosd
```