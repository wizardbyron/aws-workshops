# AWS Workshops

AWS 架构师执照。AWS 架构师要基于安全的框架实践下，采用自动化的方式来设计一个应用程序的架构。

# 科目一：构建一个静态 Web 应用

## 课程场景

通过域名访问一个静态站点。



## 课程目的

1. 针对 0 基础的学员。
2. 学员需要掌握基本的 Web 访问知识，从HTTP请求到响应的过程。
3. 学员掌握基本的 AWS 服务及其安全实践。


## 课程设计

1. 讲解 HTTP 访问的基本知识
   1. HTTP 协议
   2. HTTP 请求到 DNS
   3. DNS 到 IP
   4. IP 到主机，端口
   5. HTTP 响应
   6. 通过 curl / dig / nslookup 来理解 http 的请求-响应过程。
2. 掌握 AWS 的基本知识和计费方式
   1. IAM
   2. S3
   3. Route 53
   4. CloudFormation
   5. AWS Cli
   6. EC2
3. AWS 相关服务的安全实践及案例分析。
4. 了解静态站点生成，通过AWS Cli部署到EC2上。



## 相关 AWS 的组件/服务知识点

### IAM

1. Root 用户的安全实践
2. 密码规则
3. Group
   1. 为了安全起见，可以指定用户初始没有policy，根据使用场景设置policy
4. Policy
   1. 最小权限原则
   2. 相关服务的 policy
      1. IAM
      2. S3
      3. Route53
      4. CloudFormation
5. MFA
   1. 什么是 MFA
   2. MFA如何保证安全
6. no password 的用户
   1. 为了安全
7. accesskey 
   1. 只有两个
   2. 删除
   3. 注销
   4. 安全性(不要传到github里)



### Route 53

1. 53 代表什么？
2. CNAME
   1. 什么是CNAME?
   2. 什么是A 记录?
3. Alias
   1. dual-stack 是什么？
4. nslookup
   1. 用来做什么
5. dig
   1. 用来做什么
6. 关联 S3



### S3

1. AWS 全球唯一
2. 对象存储
3. Static Web Hosting
   1. S3 配置



### AWS-CLI

1. cli 配置 - 关联 accesskey
2. 采用 cli 操作用户
3. 采用 cli 上传下载文件
4. 采用 cli 操作 cloudformation


### CloudFormation

1. 通过上传 cloudformation template 应用。
2. 通过带参数的 cloudformation 生成模板。哪些内容可以参数化？
3. 通过 cli 上传 cloudformation
4. Stack 的管理。
5. 用 cloudformation 构建完整的基础设施


### EC2

1. 最小配置，哪些是 Required 参数。
2. 默认 AMI。
3. EC2 的配置, Instance Type。
4. GiB 和 GB 的区别。
5. Security Group
6. EC2 的生命周期


# 科目二：构建一个动态 Web 应用

## 课程场景

通过域名访问一个 HTTPS 的可交互动态站点（Jenkins应用）。

当应用出问题的时候，可以通过 ASG 自动恢复。

通过 Security Group 限制访问。

通过 S3 作为可靠存储源。(连接科目一)

## 课程目的

1. 针对有科目1 基础的学员。
2. 掌握基于 Java 的动态应用的搭建方法。
3. 了解基本的 HTTP 原理。
4. 采用 ASG 做高可用设计。
   1. 采用 ASG 做高可用设计
   2. ASG 和 ELB 的识别和关联。
   3. ASG 的 Launch Configuration。
   4. 了解 AZ。
5. 掌握采用jenkins构建基础设施流水线并搭建应用。
6. Jenkins 的基本知识（粗略）
   1. Jenkins 的配置
   2. Jenkins 的插件
   3. Jenkins 的备份还原。
7. 掌握 HTTPS 的知识
8. 利用 Certificate Manager 启用 HTTPS
9. 给 ELB 绑定证书。
10. 通过 Cloudformation 实现以上的内容
    1. EC2 的 Template 和 Launch Configuration 的转化。
    2. 识别哪些可以抽成参数。
    3. 识别服务之间的依赖关系，AWS 服务之间的依赖注入。
11. 应用基础设施流水线，避免了 AWS 用户的操作，提升了安全性和人为故障。
12. 备份/还原应用。
    1. 备份数据到S3 Bucket
    2. 恢复Jenkins应用时读取备份数据
13. AWS 相关服务的计费方式。
14. 使用Ansible部署。

## 课程设计

1. 讲解 HTTPS 访问的基本知识。
2. HTTPS 和 HTTP 的联系和区别。
3. 创建一个 EC2。
4. 在 EC2 上安装一个 Jenkins。
5. 通过配置 Jenkins 在互联网上得到一个服务器。
6. 自动化实现 EC2 的配置。
7. 通过 Route53 访问 ELB 访问 EC2。
8. 多个 EC2 实例状态的不一致问题。
9. 如果 EC2 挂了如何快速恢复。
10. Jenkins 的状态和应用隔离。(插件、配置存储)
11. 采用 CRON Job 备份 Jenkins 配置。
12. Jenkins 的自恢复。
    1. 自动化脚本，获取配置。
    2. 通过 AMI。
    3. 比较优劣
13. 了解 Security Group 往往不可访问的原因。
14. 如何通过 Security Group 安全的访问。

## 相关 AWS 的组件/服务知识点

## EC2 - 扩展

1. 自动初始化脚本。
2. 通过已经存在的 EC2 构建 AMI 镜像

## Route 53 - 扩展

1. Alias 
2. A 记录
3. TTL

## Security Group

1. Inbound / outbund
2. 地址 / SG / MyIP
3. 端口号。
4. Security Group 的组合和继承。

## ALB

1. 什么是 ALB
2. ALB 的端口映射
3. ALB 的证书绑定
4. ALB 和 ASG 的绑定

## ASG

1. Launch Configuration
2. ASG policy
3. ASG 的日志

## ASG policy

1. 检测端口
2. 检测周期
3. 检测协议

## Launch Configuration

1. 自动初始化 EC2 的配置。
2. EC2 的 Provision 脚本。

## Certificate Manager

1. HTTPS 证书分Region。
2. HTTPS 证书有效期。
3. 手动/自动更新 HTTPS 证书。
4. HTTPS

# 科目三：构建一个带数据库的 web 应用

## 课程场景

通过Jenkins部署一个带数据库可交互动态站点（WordPress），并提升可维护性和灾备。 

对数据库的谨慎操作。

## 课程目的

1. 掌握数据库状态
2. 掌握 CloudFormation 依赖的解耦。
3. 掌握数据库的安全访问和关键属性。
4. 掌握数据库的备份和恢复。
5. 采用基础设施流水线部署应用。(链接科目2)
6. 了解 Docker Image 的优势。

## 课程设计

1. 采用科目二构建的基础设施流水线。
2. CloudFormation 依赖的解耦，RDS 作为独立的配置。
3. 两条流水线：一条应用，一条 RDS。
4. 不同的 Subnet 和 Security Group 隔离策略。
5. RDS 安全策略。
6. 采用 Docker 搭建 PHP 环境。
7. 由于 RDS 的变更周期很长，所以等待时间会很多，内容较少。

## 相关 AWS 的组件/服务知识点

### RDS

1. RDS Engine

2. Master user 变更会删库。

3. 其它有可能导致数据库 Replace 的情况。

4. 数据库的用户安全级别设计。

   1. Root 用户
   2. DBA 用户
   3. Power User 用户
   4. APP 用户
   5. Querier 用户

5. 按流水线变更更换密码的策略

6. RDS Snapshot 的还原。

7. 还原周期和备份策略。

8. RDS Replicas 读/写分离。

9. RDS cluster

10. RDS 变更的时间窗口

    

# 科目四：构建一个可自动水平伸缩的 Web 应用

## 课程场景

在业务访问压力增大的情况下可以自动水平扩展或者CDN降低负载，体现智能运维，仍使用WordPress站点。

## 课程目的

1. 理解应用的性能问题。
   1. EC2 性能。
   2. 数据库性能。
   3. 缓存服务。
2. 了解应用程序的状态分离。
3. 了解自动化水平扩展。
4. CDN 的 HTTPS。
5. CDN 到 ALB 的 HTTPS 转发。
6. 了解性能测试，性能低于某个值被视作不可用。
7. CloudFormation 按依赖、职责、变更频率和影响范围隔离。
8. 采用 Flood.io 做性能设计。
9. 通过 ALB / EC2 /CloudWatch / docker status / htop/top 命令观测应用程序和数据库的性能。

## 课程设计

1. 基于科目三的应用继续，由于 CloudFront 的变更周期很长，所以等待时间会很多，内容较少。
2. 了解应用的无状态（镜像）、状态的版本化（基础设施即代码）和高可用服务（RDS）。
3. RDS 的危险操作。
   1. 通过权限避免。
   2. 通过确认避免。
4. RDS 的还原。
   1. 基于 MySQL dump/restore 的还原。
   2. 基于 Snapshot 的还原。
5. 如何设计性能测试。
   1. 什么是性能测试
   2. 制定基线
   3. 理解应用的性能周期
6. 如何设计性能策略。
   1. 快速伸展，慢速伸缩。
   2. 应用类型：
      1. 运算消耗
      2. 内存消耗

## 相关 AWS 的组件/服务知识点

1. 和所有 AWS 服务都相关的服务是关键服务。
   1. IAM
   2. CloudFormation
   3. CloudWatch

## CloudFront

1. CDN 的基本原理
2. Edge Server 同步
3. Origin 的类别
   1. S3
   2. ALB
   3. 自动定义
4. 属于 us-east-west1
5. 证书需要新建

## ASG Policy

1. 了解不同的 Policy
2. 采用 CloudWatch Policy

## CloudWatch

1. 了解 CloudWatch 和 Alarm
2. Alarm 的状态、策略和渠道。

