# 单元四：构建一个可自动水平伸缩的 Web 应用

## 课程场景

在业务访问压力增大的情况下可以自动水平扩展或者CDN降低负载，体现智能运维。

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

1. 基于单元三的应用继续，由于 CloudFront 的变更周期很长，所以等待时间会很多，内容较少。
2. 了解应用的无状态（镜像）、状态的版本化（基础设施即代码）和高可用服务（RDS）。
3. 如何设计性能测试。
   1. 什么是性能测试
   2. 制定基线
   3. 理解应用的性能周期
4. 如何设计性能策略。
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
2. Alarm 的状态、策略和渠道


