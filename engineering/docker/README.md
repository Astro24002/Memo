# Docker

## 为什么学
Docker是容器化技术的代表，是现代应用开发和部署的基础设施。掌握Docker能够提升开发效率，实现环境一致性，简化应用部署和运维。

## 学什么
- Docker核心概念与架构
- Dockerfile编写最佳实践
- 镜像构建与优化
- 容器网络与存储
- Docker Compose多容器编排

## 核心问题
- 如何构建轻量高效的容器镜像？
- 如何管理容器间的网络和通信？
- 如何实现容器的持久化存储？
- 如何优化容器资源使用？

## 推荐路线
1. 理解容器化技术原理
2. 学习Docker基本命令和操作
3. 掌握Dockerfile编写技巧
4. 实践多阶段构建和镜像优化
5. 探索Docker在CI/CD中的应用

## 相关文章


## Docker
* [命令速查](/engineering/docker/commands.md)

### 基础知识
* _TODO_[Docker架构](basic/architecture.md)
* _TODO_[容器与虚拟机对比](basic/container-vs-vm.md)
* _TODO_[镜像与容器](basic/images-and-containers.md)
* _TODO_[网络模式](basic/networking.md)
* _TODO_[存储与卷](basic/storage-and-volumes.md)

### 部署与安装
* [安装指南](deployment/installation.md)
* [多架构支持](deployment/multi-architecture.md)
* [Docker Compose](deployment/docker-compose.md)

### 镜像构建
* [语法指南](builder/dockerfile.md)
* [多阶段构建](builder/multi-stage-builds.md)
* [最佳实践](builder/best-practices.md)

### 实验案例
* [NFS服务](case/nfs/README.md)
* [Nginx服务](case/nginx/README.md)
* [HAProxy负载均衡](case/haproxy/README.md)
* _TODO_[APT镜像服务](case/mirror-apt/README.md)

### Other
* [image-init](other/image-init.md)
