# 大数据平台的集群管控

> 阿里巴巴：ODPS

- 数据管理
- 任务管理

> Google
> - Map Reduce
> - GFS
> - Bigtable
> - Chubby

## 数据平台的功能

pipline

- **数据管理**

> - 数据的进入
> - 数据的组织、存储、导出

- **数据来源**

> - 网络日志
> - Web点击日志
> - 系统数据集成

- **计算能力**

> - **计算模型**
> - cCloud
> - MapReduce
> - MPI
> - BSP
> - Spark
> - Parameter Server

> - **应用场景**
> - 搜索引擎
> - 推荐引擎
> - 广告引擎
> - 报表

## ODPS (Open Data Processing Service)

基于飞天开放平台实现一套用于海量数据存储和计算的服务。

- 核心能力：存储与计算
- 呈现形式： 服务化
> 对比软件应用的呈现形式
> - 不利于用户的使用
> - 维护代价更大

> 服务化把管理、升级等一系列繁琐的事情，对用户做到透明，给用户一个更友好的界面。

- 特点：多租户与安全
> 权限基本的保障和限制

- 多种计算模型
> - SQL
> - Stream SQL
> - Map Reduce
> - Graph
> - MPI
> - Parameter Server
> - Spark

> - **架构**
> - 控制集群
> - 计算集群 (大规模高负载的运算)

- 多计算集群水平扩展

### 概念

#### Project
类似 DataBase ，用于用户的隔离和访问控制的边界

- Table/Partition
> 用于组织结构化数据（表）

- Volume
> 用于组织非结构化数据（音频／视频／图像）

- UDF/Resource
> 字典文件、jar包、py脚本

- Job/Instance
> 用于抽象可执行实体和运行实例

- Tunnel upload/download

#### User/Role
用于管理用户对Project内实体的访问和授权

### 在飞天应用站的位置
扮演上层应用的角色，给数据工程师提供数据处理日常工作的平台

## 分布式文件系统

### Master Slave

- Master (NameNode 管理目录结构，管理Meta)
> - master 负责缓存文件Meta信息
> - 目录结构

- Chunk
> - Chunk Server 负责维护
> - slave 负责文件切块

- Client
> 提供给应用方，访问文件系统的一个SDK

### 容错机制

- 机器多，故障率高
> - CPU降频
> - 磁盘夯筑
> - 磁盘损坏

- 常见冗余机制
> - 多副本冗余
> - 冗余编码（多项式插值）

### 数据分布策略

- **按照block切分数据**

- **数据冗余策略**

- **同一个block的不同副本分布在**

> - 不同磁盘
> - 不同机器
> - 不同机架
> - 不同交换机
> - 不同IDC

### 分布式计算调度

基于 性能 ＋ 成本 约束

- 数据就近原则

> - 将计算调度到数据所在节点
> - 将计算发送到离数据最近的节点执行
> - 将计算发送到数据所在机房执行



- 单机数据部署
- 跨集群数据部署

## 跨IDC集群规划

跨多个IDC的物理集群，被组织成同一个逻辑上的 Cluster
- 优点：在调度层看来，属于同一个分布式文件系统，方便调度
- 灵活简单
- 规模很大时，扩展困难


在每一个不同的物理的Cluster里面，一个自成体系的集群，有一个自己独立的分布式文件系统
多个集群之间的调度管理等操作，由调度层做

- 缺点：调度层更复杂，会显示的做数据的复制等操作
- 优点：这种架构下的集群规模更大，地域上可以更自由的来做布局
- 复杂性高（调度层、meta管理层）
- 可无限扩展

### ODPS 架构样式

在ODPS中，用户并不是直接面对分布式文件系统中的目录和文件，而是经过加工和整理的视角。

### ODPS 数据的跨集群依赖

- 物理机房的限制
- 业务的演进和发展
- Project在不同集群之间的移动

- 作业可能运行在不同集群
- 数据属于不同的业务部门
- 不同业务部门之间数据有血缘关系
- 不同集群运行的作业需要访问其它集群的数据

### ODPS 整体结构

- 控制集群
- 计算集群

## 跨集群数据复制

- 数据在不断变动

- 目的：保证从不同集群中读取的数据 一致、有效、正确

- Version 版本控制

### 数据复制触发方式

- 基于 Meta 扫描
- 命令触发

### 访问策略

- 死等
- 超时等待
- 直读
