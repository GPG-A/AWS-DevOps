## 一、Ansible自动化部署 Kubernetes集群

1. Ansible基本使用
2. Playbook
3. Roles
4. 二进制部署步骤及核心组件
5. 编写 Roles部署各个组件
6. 一键部署 Kubernetes高可用集群

## 二、Kubernetes弹性伸缩

1. Nodes资源扩容

   1）Cluster autoscaler

   2）Ansible

2. Pod资源扩容

   1）HPA原理推进

   2）基于Metrics Server的HPA

   3）基于Promethues的HPA

## 三、Kubernetes应用包管理器Helm

> 未什么要用Helm？

1. Helm介绍

2. Helm基本使用

3. Chart模板

   1）模板概述

   2） 内置对象

   3）Values

   4）管道与函数

   5）流程控制

   6）变量

   7）命名模板

4. 使用Harbor作为Chart仓库

## 四、Kubernetes集群网络

1. 网络基础知识

   1）交换技术、路由技术

   2）OSI七层模型

   3）TCP/UDP协议

2. Kubernetes网络方案之 Flannel剖析

   1）Docker网络模型与K8S网络模型

   2）Flanne概述与部署

   3）Flannel VLAN模式及原理解析

   4）Flannel Host-GW模式及原理解析

3. Kubernetes网络方案之 Calico剖析

   1）Calico概述与部署

   2）Calico bgp模式及原理解析

   3）IPIP隧道模式及原理解析

   4）Route Elector（RR）方案

   5）办公网络与K8S内部网络互通方案

   6）CNI网络方案优缺点及最终选择

4. Pod网络隔离

   1）为什么需要网络隔离？

   2）网络策略概述

   3）入站、出站网络流量访问控制案例

## 五、Kubernetes存储之Ceph分布式存储系统

1. Ceph系统架构及核心组件

2. 生产环境Ceph集群服务器规划

3. Ceph三大客户端介绍

4. Ceph核心概念（ Crush、Pool、PG、OSD、 Object）

5. 部署Ceph集群

   1）Ceph版本选择

   2）安装 Ceph-deploy工具

   3）Ceph. conf配置文件

   4）MON/OSD/MDS/MGR组件部署

6. RBD客户端安装与使用

   1）RBD的工作原理与配置

   2）RBD的常用命令

   3）客户端挂载RBD的几种方式

7. CephFS客户端安装与使用

   1）CephFS的工作原理与配置

   2）挂载 CephFS的几种方式

8. K8S使用Ceph作为存储

   1）PV，PVC概述

   2）PV自动供给

   3）Pod使用RBD作为持久数据卷

   4）Pod使用 CephFS作为持久数据卷

9. Ceph监控

   1）内置 Dashboard

   2）Prometheus+ Grafana监控Ceph

10. Ceph日常运维管理及常见问题