# 单元二：构建一个动态 Web 应用

## 课程场景

- 通过域名访问一个 HTTPS 的可交互动态站点。

- 当应用出问题的时候，可以通过 ASG 自动恢复。

- 通过 Security Group 限制访问。

- 通过 S3 作为可靠存储源。(连接单元一)

## 课程目的

1. 针对有单元1 基础的学员。
2. 掌握基于 Java 的动态应用的搭建方法。
3. 了解基本的 HTTP 原理。
4. 采用 ASG 做高可用设计。
   1. 采用 ASG 做高可用设计
   2. ASG 和 ELB 的识别和关联。
   3. ASG 的 Launch Configuration。
   4. 了解 AZ。
5. 掌握采用jenkins构建基础设施流水线并搭建应用。
6. Jenkins 的基本知识
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
13. AWS 相关服务的计费方式。
14. 了解 Java 应用技术栈。

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

### Route 53

1. Alias
2. A 记录
3. TTL

### Security Group

1. Inbound / outbund
2. 地址 / SG / MyIP
3. 端口号。
4. Security Group 的组合和继承。

### ALB

1. 什么是 ALB
2. ALB 的端口映射
3. ALB 的证书绑定
4. ALB 和 ASG 的绑定

### EC2

1. 最小配置，哪些是 Required 参数。
2. 默认 AMI。
3. 自动初始化脚本。
4. EC2 的配置。
5. GiB 和 GB 的区别。
6. Security Group
7. EC2 的生命周期
8. 通过已经存在的 EC2 构建 AMI 镜像

### ASG

1. Launch Configuration
2. ASG policy
3. ASG 的日志

### ASG policy

1. 检测端口
2. 检测周期
3. 检测协议

### Launch Configuration

1. 自动初始化 EC2 的配置。
2. EC2 的 Provision 脚本。

### Certificate Manager

1. HTTPS 证书分Region。
2. HTTPS 证书有效期。
3. 手动/自动更新 HTTPS 证书。
4. HTTPS
