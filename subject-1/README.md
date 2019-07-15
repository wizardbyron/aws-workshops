# 科目一：构建一个静态 Web 应用

## 课程场景

- 申请一个新的 AWS 账号。
- 掌握 AWS 账号的安全。
- 通过域名访问一个静态站点。

## 课程目的

1. 针对 0 基础的学员。
2. 学员需要掌握基本的 Web 访问知识，从域名到取到内容。
3. 学员掌握基本的 AWS 安全实践。
4. 掌握设计架构安全的思考方式。

## 课程设计

1. 讲解 HTTP 访问的基本知识
   1. HTTP 协议
   2. HTTP 请求到 DNS
   3. DNS 到 IP
   4. IP 到主机，端口
   5. HTTP 响应
   6. 通过 curl / dig / nslookup 来理解 http 的请求-响应过程。
2. 掌握 AWS 的基本知识
   1. IAM
   2. S3
   3. Route 53
   4. CloudFormation
3. AWS 相关服务的计费方式。
4. 了解静态站点生成。



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
