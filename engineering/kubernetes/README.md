# Kubernetes

## 定位

Kubernetes 是容器编排的事实标准，是云原生技术体系的核心。

在这个知识库中，Kubernetes 既是学习对象，也是承载存储、数据库、应用组件、监控和 CI/CD 案例的主要实践环境。

## 核心问题

- Kubernetes 如何通过声明式 API 管理应用生命周期？
- Pod、Service、Ingress、Deployment、StatefulSet 等资源如何协同工作？
- 如何设计高可用、可扩展、可观测的集群和应用架构？
- 如何管理复杂微服务依赖、配置、安全和存储？

## 学习路线

1. 理解容器编排和 Kubernetes 控制面基本概念。
2. 学习核心资源对象和常用命令。
3. 掌握 kubeadm、kubespray、minikube 等部署方式。
4. 学习 Helm、Ingress、证书、存储、监控等基础组件。
5. 通过数据库、应用和 CI/CD 案例理解生产环境实践。

## 内容索引

### 基础

- [命令速查](commands.md)
- _TODO_[Helm](knowledge/helm/README.md)

### 集群部署

- [minikube](preactice/minikube/README.md)
- kubeadm
  - _TODO_[kubeadm-v1.32.5](preactice/kubeadm/v1.32.5/README.md) `v1.32.5` `online` `251115`
  - _TODO_[kubeadm-v1.32.5-offline](preactice/kubeadm/v1.32.5-offline/README.md) `v1.32.5` `offline` `20251115`
  - _TODO_[kubeadm-v1.28.15](preactice/kubeadm/v1.28.15/README.md) `v1.28.15` `online` `20251115`
  - [kubeadm-v1.25.6](preactice/kubeadm/v1.25.6/README.md) `v1.25.6` `online` `archive`
  - [kubeadm-v1.23.3](preactice/kubeadm/v1.23.3/README.md) `v1.23.3` `online` `archive`
- kubespray
  - _TODO_[kubespray-v2.24.3](preactice/kubespray/v2.24.3/README.md) `v1.28.14` `online`
  - _TODO_[kubespray-v2.24.3-offline](preactice/kubespray/v2.24.3-offline/README.md) `v1.28.14` `offline`
  - _TODO_[kubespray-v2.29.0](preactice/kubespray/v2.29.0/README.md) `v1.33.5` `online` `20251115`

### 基础组件

- _TODO_[ingress-nginx](case/basic-components/ingress-nginx/README.md)
- _TODO_[cert-manager](case/basic-components/cert-manager/README.md)
- _TODO_[docker-registry](case/basic-components/docker-registry/README.md)
- _TODO_[pureLB](case/basic-components/pureLB/README.md)
- _TODO_[SSHD](case/basic-components/sshd/README.md)

### 数据库

- _TODO_[mariadb](case/databases/mariadb/README.md)
- _TODO_[redis](case/databases/redis/README.md)
- _TODO_[neo4j-standalone](case/databases/neo4j-standalone/README.md)

### 应用案例

- _TODO_[resources-nginx](case/application/resources-nginx/README.md)
- _TODO_[kubernetes-dashboard](case/application/kubernetes-dashboard/README.md)
- _TODO_[chart-museum](case/application/chart-museum/README.md)
- _TODO_[phpmyadmin](case/application/phpmyadmin/README.md)
- _TODO_[minio](case/application/minio/README.md)
- _TODO_[nexus](case/application/nexus/README.md)
- _TODO_[gitea](case/application/gitea/README.md)
- _TODO_[tekton](case/application/tekton/README.md)

### 存储

- _TODO_[local static provisioner](case/storage/local-static-provisioner/README.md)
- _TODO_[rook ceph](case/storage/rook-ceph/README.md)
- _TODO_[nfs-provisioner](case/storage/nfs-provisioner/README.md)

### 监控

- _TODO_[kube-prometheus-stack](case/monitor/kube-prometheus-stack/README.md)

### 其他

- [extra-ops](other/extra-ops/README.md)
- [kubernetes share](other/share/README.md)

## 后续计划

- 补齐 Helm、Ingress、证书、存储和监控的基础说明。
- 将部署实践区分为在线、离线和归档版本。
- 为常用案例补充部署目标、依赖、验证方式和清理方式。
