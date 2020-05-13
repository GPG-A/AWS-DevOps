## 一、重新认识Docker

> 为什么要用容器？

1. Docker基本使用
   1) 基础概念
   2) 理解容器镜像
   3）创建应用容器并作资源限制
   4）让外部访问容器应用
2. Dockerfile
   1) 企业容器镜像制作
   2）Dockerfile编写
   3）使用制作的镜像容器部署LNMP平台
3. 企业级Harbor镜像仓库集中管理镜像
4. 基于Docker构建企业Jenkins CI平台
5. Promethues+Grafana监控Docker

## 二、Kubernets概述

> 有了Docker，为什么还要K8s?

1. Kubernetes简介及其发展历史
2. Kubernetes核心概念
3. Kubernetes核心组件

## 三、Kubernetes集群搭建与实践

1. 企业容器平台架构设计
2. 机器选型&资源规划
3. 搭建生产级K8s高可用集群
4. 使用kubeadm工具快速搭建K8s集群
5. 常用插件部署：Flannel、Dashboard、CoreDNS

## 四、Kubectl命令行管理工具

1. kubectl常用命令及常用技巧
2. kubectl工具管理应用程序
3. kubectl工具远程链接K8s集群

## 五、资源编排

1. YAML文件格式说明
2. YAML文件创建资源对象

## 六、深入理解Pod对象

1. Pod存在的意义与设计模式
2. 镜像拉取策略
3. 资源限制
4. 重启策略
5. 健康检查
6. 调度策略
7. 故障排查

## 七、深入理解常用控制器

1. 无状态应用部署：Deplyment（升级、回滚、扩容）
2. 容器化守护进程的意义：DaemonSet
3. 撬动离线业务：Job与CronJob

## 八、深入理解Service（统一访问入口）

1. Service存在的意义
2. Service三种类型
3. Service代理模式只Iptables工作原理
4. Service代理模式只IPVS工作原理
5. Iptables和IPVS选择及优缺点
6. Service DNS名称访问：CoreDNS

## 九、Ingress（从外部访问应用最佳方式）

1. Ingres介绍
2. 部署Ingress Controller（Nginx）
3. 使用Ingress发布HTTP/HTTPS网站
4. 通过Annotations对Ingress做定制化配置
5. Ingress Controller高可用方案

## 十、管理应用程序配置

1. Secret
2. Configmap
3. 容器应用配置资源的两种方式及应用案例

## 十一、Pod数据持久化（数据卷与数据持久化卷）

1. 数据卷描述
2. 临时存储卷，节点存储卷，网络存储卷
3. PV 与 PVC的关系
4. PV生命周期
5. PV静态供给
6. PV动态供给（StorageClass）

## 十二、再谈有状态应用部署

1. Headless Service
2. StatefulSet控制器
3. 使用StatefulSet部署有状态应用
4. 有状态应用身份之网络ID
5. 有状态应用身份之存储

## 十三章、Kubernets鉴权框架与用户权限分配

1. Kubernetes 安全框架
2. API访问过三关：认证、授权、准入控制
3. 基于角色的权限访问控制：RBAC

## 十四章、使用Promethues全方位监控K8S

1. Kubernetes监控指标及实现思路
2. 在Kubernetes平台部署Promethues
3. 基于Kubernetes服务发现的配置解析
4. 在Kubernetes平台部署Grafana
5. 监控Kubernetes集群中的Pod、Node、资源对象等资源
6. 使用Grafana可视化展示Promethues监控数据
7. 在Kubernets平台部署Alertmanager
8. 监控告警规则及告警通知

## 十五、使用EKL Stack手机Kubernetes平台日志

1. K8s平台日志采集三种方案
2. ELK Stack日志平台部署
3. 容器日志标准输出、日志文件采集方式
4. Kubernetes组件日志收集
5. Kubernetes平台Pod中应用日志收集

## 十六、基于Kubernetes构建企业Jenkins CI.CD平台

1. 发部流程设计及注意事项
2. 使用Gitlab作为代码仓库及使用Harbor作为镜像仓库
3. 在Kubernetes中部署Jenkins
4. Jenkins Pipeline基本使用
5. Jenkins Pipeline参数化构建
6. Jenkins在Kubernetes中动态创建代理
7. 定制Jenkins Slave镜像
8. Jenkins Pipeline构建流水线发布
9. Jenkins在Kubernetes中持续部署

