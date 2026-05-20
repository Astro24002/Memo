# Docker

## 定位

Docker 是容器化技术的代表，是现代应用开发、测试和部署的基础设施。

在这个知识库中，Docker 是学习 Kubernetes、DevOps 和云原生实践之前的基础主题。

## 核心问题

- 容器和虚拟机的边界与差异是什么？
- 镜像、容器、网络和卷如何共同组成容器运行环境？
- 如何编写可维护、可复用、体积合理的 Dockerfile？
- 如何通过 Docker Compose 和实验案例理解多容器应用？

## 学习路线

1. 理解容器化技术原理和 Docker 基本架构。
2. 学习镜像、容器、网络、存储和常用命令。
3. 掌握 Dockerfile、多阶段构建和镜像优化。
4. 使用 Docker Compose 组织多容器应用。
5. 通过 NFS、Nginx、HAProxy 等案例理解实际部署。

## 内容索引

### 基础

- [命令速查](commands.md)
- _TODO_Docker架构
- _TODO_容器与虚拟机对比
- _TODO_镜像与容器
- _TODO_网络模式
- _TODO_存储与卷

### 部署与安装

- [安装指南](deployment/installation.md)
- [多架构支持](deployment/multi-architecture.md)
- [Docker Compose](deployment/docker-compose.md)

### 镜像构建

- [语法指南](builder/dockerfile.md)
- [多阶段构建](builder/multi-stage-builds.md)
- [最佳实践](builder/best-practices.md)

### 实验案例

- [NFS服务](case/nfs/README.md)
- [Nginx服务](case/nginx/README.md)
- [HAProxy负载均衡](case/haproxy/README.md)
- _TODO_[APT镜像服务](case/mirror-apt/README.md)

### 其他

- [image-init](other/image-init.md)

## 后续计划

- 补齐 Docker 基础知识中的架构、网络和存储内容。
- 将实验案例整理成统一的部署、验证和清理格式。
- 补充 Docker 与 Kubernetes 之间的衔接说明。
