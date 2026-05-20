# Kubernetes

## 为什么学
Kubernetes是容器编排的事实标准，是云原生技术的核心。掌握K8s能够构建高可用、可扩展的分布式系统，实现应用的自动化运维。

## 学什么
- K8s架构与核心组件
- Pod、Service、Ingress等资源对象
- 工作负载管理(Deployment、StatefulSet等)
- 配置管理与服务发现
- 集群安全与权限控制

## 核心问题
- 如何设计高可用的应用架构？
- 如何实现应用的自动扩缩容？
- 如何管理复杂的微服务依赖？
- 如何保障集群的安全性和稳定性？

## 推荐路线
1. 理解容器编排的基本概念
2. 学习K8s核心资源和API
3. 掌握Helm包管理工具
4. 实践服务网格和可观测性
5. 探索GitOps和持续交付实践

## 相关文章

## Kubernetes
* [命令速查](commands.md)

### Knowledge
* _TODO_[Helm](knowledge/helm/README.md)

### Deploy
* [minikube](preactice/minikube/README.md)
* kubeadm
    + _TODO_[kubeadm-v1.32.5](preactice/kubeadm/v1.32.5/README.md) `v1.32.5` `online` `251115`
    + _TODO_[kubeadm-v1.32.5-offline](preactice/kubeadm/v1.32.5-offline/README.md) `v1.33.5` `online` `20251115`
    + _TODO_[kubeadm-v1.28.15](preactice/kubeadm/v1.28.15/README.md) `v1.28.15` `online` `20251115`
    + [kubadm-v1.25.6](preactice/kubeadm/v1.25.6/README.md) `v1.25.6` `online` `archive`
    + [kubeadm-v1.23.3](preactice/kubeadm/v1.23.3/README.md) `v1.23.3` `online` `archive`
* kubespray
    + _TODO_[kubespray-v2.24.3](preactice/kubespray/v2.24.3/README.md) `v1.28.14` `online`
    + _TODO_[kubespray-v2.24.3-offline](preactice/kubespray/v2.24.3-offline/README.md) `v1.28.14` `offline`
    + _TODO_[kubespray-v2.29.0](preactice/kubespray/v2.29.0/README.md) `v1.33.5` `online` `20251115`

### Case
* basic-components
    + _TODO_[ingress-nginx](case/basic-components/ingress-nginx/README.md)
    + _TODO_[cert-manager](case/basic-components/cert-manager/README.md)
    + _TODO_[docker-registry](case/basic-components/docker-registry/README.md)
    + _TODO_[pureLB](case/basic-components/pureLB/README.md)
    + _TODO_[SSHD](case/basic-components/sshd/README.md)
* databases
    + _TODO_[mariadb](case/databases/mariadb/README.md)
    + _TODO_[redis](case/databases/redis/README.md)
    + _TODO_[neo4j-standalone](case/databases/neo4j-standalone/README.md)
* application
    + _TODO_[resources-nginx](case/application/resources-nginx/README.md)
    + _TODO_[kubernetes-dashboard](case/application/kubernetes-dashboard/README.md)
    + _TODO_[chart-museum](case/application/chart-museum/README.md)
    + _TODO_[phpmyadmin](case/application/phpmyadmin/README.md)
    + _TODO_[minio](case/application/minio/README.md)
    + _TODO_[nexus](case/application/nexus/README.md)
    + _TODO_[gitea](case/application/gitea/README.md)
    + _TODO_[tekton](case/application/tekton/README.md)
* storage
    + _TODO_[local static provisioner](case/storage/local-static-provisioner/README.md)
    + _TODO_[rook ceph](case/storage/rook-ceph/README.md)
    + _TODO_[nfs-provisioner](case/storage/nfs-provisioner/README.md)
* monitor
    + _TODO_[kube-prometheus-stack](case/monitor/kube-prometheus-stack/README.md)

### Other
* [extra-ops](other/extra-ops/README.md)
* [kubernetes share](other/share/README.md)
