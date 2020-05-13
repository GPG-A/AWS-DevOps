## 一、Shel脚本编程进阶，常规任务自动化运行

1. Shell基本语法结构

2. 文本处理三剑客最常用的几种场景（grep/ awk/ sed）

   1）练习：一键查看服务器资源利用率

   2）练习：找出占用CPU、内存过高的进程

   3）练习：批量检查网站是否异

## 二、Gitlab代码版本管理系统

1. Docker部署GitLab
2. GitLab常用管理命令
3. GitLab邮件设置
4. GitLab域名绑定
5. GitLab创建用户、群组和项目
6. GitLab分支的创建和使用
7. GitLab两种认证方式
8. Git命令基本使用
9. GitLab CI/CD架构与使用
10. GitLab备份与回复

## 三、Ansible自动化运维工具

1. Ansible介绍
2. Ansible安装与配置
3. Ad-hoc模式工作
4. 7个常用模块
5. Playbook棚述
6. Playbook核心应用
7. Roes核心应用

## 四、Prometheus+ Grafana监控系统

1. Promethues监控系统
   1）Prometheus概述与部署
   2）Prometheus配置文件解析
   3）Prometheus监控 Linux服务器
   4）Prometheus监控 Docker主机
   5）PromQL基本使用
2. Prometheus自动化监控
   1）Ansible自动部署 Agent
   2）Prometheus基于Cosul实现100台主机自动监控
3. Alertmanager告警利器
   1）概述与部署
   2）邮件通知，钉钉通知
   3）告警收敛：分组、抑制、静默
   4）编写告警规则
4. Grafana高逼格可视化展示
   1）Grafana概述与部署
   2）Grafana可视化展示 Prometheus数据
   3）Grafana多环境多项目导航栏制作
   4）Grafana图表制作
   5）Grafana模板使用
5. Prometheus+ Grafana全方位监控 Kubernetes

## 五、ELK Stack企业日志平台

1. ELK Stack架构概述

2. ELK Stack架构搭建

   1）分布式数据库：Elasticsearch概述、集群部署、图形管理

   2）日志处理：Logstash概述、部署、配置

   3）日志可视化：Kibana概述、部署、配置

   4）日志采集：Filebeat概述、部署、配置

3. 深入理解Logstash

   1）Input常用插件

   2）Fileter常用插件

   3）Output常用插件

4. 使用Kibana可视化日志

   1）日志采集

   2）Kibana可视化和仪表盘

5. 收集Kubernetes应用程序日志

6. 日志告警ElastAlert

7. ELK Stack架构性能优化

## 六、Jenkins自动化CI/CD流水线

1. Jenkins基本管理

   1）用户权限管理

   2）参数化构建

   3）GitLab参数化构建

   4）分布式构建

2. Pipeline流水线

   1）Grooy基础

   2）参数化构建代码化

   3）Jenkins与Docker持续集成，流水线构建镜像

   4) Jenkins与Ansible集成，发布多服务器、多环境

3. 发布失败项目回滚

4. Jenkins基于GitLab自动触发发布

5. Jenkins备份与回复

## 七、微服务项目运维管理

1. SpringCloud微服务框架概述
2. 微服务全链路监控系统Pinpoint
3. 基于Jenkins构建微服务自动发布平台