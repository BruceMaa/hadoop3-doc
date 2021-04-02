
# Apache Hadoop 3.2.2

Apache Hadoop 3.2.2在以前的主要发行版本（hadoop-3.2）上进行了许多重大改进。

# 概述

我们鼓励用户阅读全套的发行说明。 此页面概述了主要更改。

## ABFS: 修复服务名称指示 (SNI)

ABFS：错误修复，以支持服务器名称指示（SNI）。

## 在不符合posix的文件系统上设置名称目录的权限失败

修复了Windows系统上的namenode / journal启动。

## 将HDFS持久存储读缓存回传支持到分支3.2**

HDFS缓存中支持非易失性存储类内存（SCM，也称为持久性内存）。要启用SCM缓存，用户只需在`hdfs-site.xml`中为属性"dfs.datanode.cache.pmem.dirs"配置SCM卷。并且所有HDFS缓存指令均保持不变。 HDFS SCM缓存有两种实现，一种是纯Java代码实现，另一种是基于本机PMDK的实现。后一种实现可以在缓存写入和缓存读取方面为用户带来更好的性能提升。如果可以加载PMDK本机库，它将使用基于PMDK的实现，否则将回退到Java代码实现。要启用基于PMDK的实现，用户应通过参考官方网站[http://pmem.io/](http://pmem.io/）来安装PMDK库。然后，通过参考源代码“ BUILDING.txt”中的“ PMDK库构建选项”部分，构建具有PMDK支持的Hadoop。如果配置了多个SCM卷，则使用循环策略来选择用于缓存块的可用卷。与DRAM高速缓存一致，SCM高速缓存也没有高速缓存逐出机制。当DataNode收到来自客户端的数据读取请求时，如果将相应的块缓存到SCM中，则DataNode将使用SCM上的块位置路径（纯Java实现）或SCM上的缓存地址（基于PMDK的实现）实例化InputStream。创建InputStream后，DataNode会将缓存的数据发送到客户端。请参阅“集中式缓存管理”指南以了解更多详细信息。

## 从备用节点读取一致

观察者是除HA设置中的活动节点和备用节点外的一种新型NameNode。 观察者节点维护与备用节点相同的名称空间的副本。 此外，它还允许执行客户端读取请求。 为了确保单个客户端中的写后读取一致性，在RPC头中引入了状态ID。 观察者仅在其自身的状态赶上了它先前从活动NameNode接收到的客户机的状态ID后，才对客户机请求作出响应。

客户端可以显式调用新的客户端协议msync()，以确保此客户端从Observer进行的后续读取是一致的。

引入了新的客户端ObserverReadProxyProvider，以提供Active和Observer NameNode之间的自动切换，以分别提交写入和读取请求。

## 将checkstyle更新为8.26，并将maven-checkstyle-plugin更新为3.1.0

将checkstyle更新为8.26，并将maven-checkstyle-plugin更新为3.1.0

## ZKFC忽略`dfs.namenode.rpc-bind-host`并使用`dfs.namenode.rpc-address`绑定到主机地址

如果已经配置，ZKFC将主机地址绑定到`dfs.namenode.servicerpc-bind-host`。否则，它将绑定到`dfs.namenode.rpc-bind-host`。 如果两者均未配置，则ZKFC会将其自身绑定到NameNode RPC服务器地址（有效的`dfs.namenode.rpc-address`）。

## ViewFS根目录（ls“ /”）上的ListStatus应该列出linkFallBack根目录（已配置的目标根目录）。

如果可用，根目录("/")上的ViewFS＃listStatus通过fallbackLink列出。如果在配置的安装路径和回退链接中存在相同的目录名称，则返回的结果中仅列出配置的安装路径。

## NameNode在向ResourceManager注册时，需要提供健康状态

改进了具有节点运行状况的节点注册。

# 入门

Hadoop文档包含开始使用Hadoop所需的信息。从[单节点设置](https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html)开始，向您展示如何设置单节点Hadoop安装。然后转到[集群设置](https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/ClusterSetup.html)，了解如何设置多节点Hadoop安装。