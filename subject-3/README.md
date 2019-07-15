# 科目三：构建一个带数据库的 web 应用

## 课程场景

通过域名访问一个 HTTPS 的带数据库可交互动态站点，并提升可维护性和灾备。

对数据库的安全和维护。

## 课程目的

1. 掌握数据库状态
2. 掌握 CloudFormation 依赖的解耦。
3. 掌握数据库的安全访问和关键属性。
4. 掌握数据库的备份和恢复。
5. 采用基础设施流水线部署应用。(链接科目2)
6. 了解 php 技术栈
7. 了解 Docker Image 的优势。

## 课程设计

1. 采用科目二构建的基础设施流水线。
2. CloudFormation 依赖的解耦，RDS 作为独立的配置。
3. 两条流水线：一条应用，一条 RDS。
4. 不同的 Subnet 和 Security Group 隔离策略。
5. RDS 安全策略。
6. 采用 Docker 搭建 PHP 环境。
7. 由于 RDS 的变更周期很长，所以等待时间会很多，内容较少。
8. RDS 的危险操作。
   1. 通过权限避免。
   2. 通过确认避免。
9. RDS 的还原。
   1. 基于 MySQL dump/restore 的还原。
   2. 基于 Snapshot 的还原。
10. 掌握 RDS replication 的使用。
    1. 通过分区和分片提升 RDS 的性能。
    2. 通过不同的集群策略和自动化手段对数据库进行及时维护。

## 相关 AWS 的组件/服务知识点

### RDS

1. RDS Engine

2. Master user 变更会删库。

3. 其它有可能导致数据库 Replace 的情况。

4. 数据库的用户安全级别设计。

   1. Root 用胡
   2. DBA 用户
   3. Power User 用户
   4. APP 用户
   5. Querier 用户

5. 按流水线变更更滑密码的策略

6. RDS Snapshot 的还原。

7. 还原周期和备份策略。

8. RDS republica 读/写分离。

9. RDS cluster

10. RDS 变更的时间窗口

    

