# Solidity-Contract-2023
For 
区块链 智能合约开发 Java

#1 Step 1 区块链平台搭建相关经验 小技巧 

搭建平台 我首推使用Docker容器搭建  全套套件采用Webase Fisco Bcos

手动搭建需要注意Mysql 推荐使用Mysql 5.x 8.x可能有权限问题 会导致JDBC驱动出现异常

JDK版本推荐使用Oracle 官方版本 尽可能不要使用OpenJDK 降低错误率

个人搭建时 使用的Ubuntu系统 22.10版本  JDK版本使用JDK8(随Docker自带) (强烈推荐Ubuntu)

尽量使用物理机搭建 可以大幅度减少性能损耗 物理机推荐在16C 64G内存左右(内存越大越好) 

服务器储存尽量选用NVME SSD 1TB以上(虚拟机，快照 大交易量情况下压测产生的数据)

虚拟化优先推荐Hyper-V(Windows自带 性能损耗最低) 其次Vmware Workstation(最方便,性能损耗大概在14%附近) Vmware Esxi等

详细搭建方式请参考Fisco Bcos官方搭建手册 这里只描述易出错的点位

套件推荐使用Webase v1.5.5 即可

#2 问题解决
Mysql Error(FIXED)

解决方式:调整Mysql8.x权限方面问题,如无要求 尽量使用MYSQL5.x 

！！！请注意 在运行部署套件的时候 一定要配置JDK 一定！！！

配置JDK 方法 

vim /etc/environment 下配置JAVAHOME即可 

使用JAVA_SDK压测工具时 请尽量在ubuntu下使用Root账户复制证书

在正常用户模式下复制可能会导致一些权限问题

java -cp 'conf/:lib/*:apps/*' org.fisco.bcos.sdk.demo.perf.ParallelOkPerf [parallelok] [1] [1] [10000] [1000] [1]

在以上命令中 请把压测数据外的大括号去掉 即可正常进行压力测试 

推荐压力在1K tps  100w 交易量 即可达到压测效果


推


