## 并行链和跨链

#### 并行链

EOS Cochain仓库，从<a href="https://github.com/EOSIO/eos" target="_blank">EOS仓库</a>fork而来，将基于EOS Cochain的宪法和理念，做适当定制和增强。包括但不限于，系统参数修改、系统合约增强、增加插件、安全补丁。EOS Cochain将成为EOS同构跨链的标杆，并在不远的将来，参与到Cochain异构跨链生态中，为EOS打开通往价值互联网的大门。

- <a href="https://github.com/eoscochain/eoscochain" target="_blank">EOS Cochain <i class="fab fa-github"></i></a>

#### 跨链合约

ICP(Inter-Chain Protocol)跨链合约，同时部署到EOS Cochain并行链和EOS主链中，接收跨链中继的调用，跟踪来源链的区块（头），解析跨链交易，执行并状态持久化。安全是跨链合约最需要保证的要素。

- <a href="https://github.com/eoscochain/eos-contracts/tree/master/icp" target="_blank">ICP Contract <i class="fab fa-github"></i></a>

#### 跨链中继

跨链中继将以插件的形式，同时部署到EOS Cochain并行链节点和EOS主链节点中，实时接收检查每个区块中的跨链交易，并中继给目标链。

- <a href="https://github.com/eoscochain/eos-relay" target="_blank">ICP Relay <i class="fab fa-github"></i></a>

## 插件、合约、DAPP

EOS Cochain将持续为EOS生态贡献以下插件、智能合约、DAPP。

#### 插件

这里列出的插件位于EOS Cochain仓库中，可以很容易地将其移植并编译到EOS中。由于EOS一体化的CMake编译工程的限制，我们目前无法将插件放到单独的仓库中，但后续不排除通过git submodule的方式来管理。

- <a href="https://github.com/eoscochain/eoscochain/tree/develop/plugins/mysql_db_plugin" target="_blank">MySQL Plugin <i class="fab fa-github"></i></a> (Compatible with MySQL and TiDB)

#### 智能合约

EOS Cochain试图为EOS生态打造一整套经过安全审计和生产环境验证的智能合约集，满足各种现在或未来的应用场景的需要。

- <a href="https://github.com/eoscochain/eos-contracts/tree/master/token" target="_blank">Token Contract <i class="fab fa-github"></i></a>
- <a href="https://github.com/eoscochain/eos-contracts/tree/master/crowdsale" target="_blank">CrowdSale Contract <i class="fab fa-github"></i></a>
- <a href="https://github.com/eoscochain/eos-contracts/tree/master/nameauction" target="_blank">Name Auction Contract <i class="fab fa-github"></i></a>

#### DAPP

我们为EOS Cochain并行链和EOS主链量身打造的DAPP，将既拥有很容易访问的网页版，又在<a href="https://cochain.io" target="_blank">Cochain钱包</a>中拥有最显著的入口。
