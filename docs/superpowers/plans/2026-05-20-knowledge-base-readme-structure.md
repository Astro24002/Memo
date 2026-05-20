# Knowledge Base README Structure Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Standardize the repository's top-level and core second-level README files so the knowledge base is easier to browse and maintain.

**Architecture:** This is a documentation-only change. README files act as navigation maps, while detailed technical notes remain in topic-specific files. Existing directories and links are preserved unless a link is clearly broken.

**Tech Stack:** Markdown, repository-local relative links, manual link verification with shell checks.

---

## File Structure

- Create: `foundations/README.md` — first-level map for foundational technical knowledge.
- Create: `engineering/README.md` — first-level map for engineering and cloud-native practice.
- Create: `ai-infra/README.md` — first-level map for AI infrastructure topics.
- Create: `research/README.md` — first-level map for research-oriented notes.
- Create: `thinking/README.md` — first-level map for technical thinking and essays.
- Modify: `engineering/devops/README.md` — expand from a one-line placeholder into a structured topic entry.
- Modify: `engineering/kubernetes/README.md` — preserve existing links while reorganizing into the shared README shape.
- Modify: `engineering/docker/README.md` — preserve existing links while reorganizing into the shared README shape.
- Modify: `foundations/linux/README.md` — expand the current installation-guide index into a structured Linux entry.
- Modify: `ai-infra/rag/README.md` — normalize as a core AI infrastructure topic entry.
- Modify: `ai-infra/llmops/README.md` — normalize as a core AI infrastructure topic entry.
- Modify: `ai-infra/gpu-infra/README.md` — normalize as a core AI infrastructure topic entry.
- Modify: `ai-infra/inference-serving/README.md` — normalize as a core AI infrastructure topic entry.

## Task 1: Add First-Level Entry Pages

**Files:**

- Create: `foundations/README.md`
- Create: `engineering/README.md`
- Create: `ai-infra/README.md`
- Create: `research/README.md`
- Create: `thinking/README.md`

- [ ] **Step 1: Create `foundations/README.md`**

Write this file:

```md
# Foundations

## 定位

Foundations 记录系统工程、云原生和 AI 基础设施所依赖的底层知识。

这一部分更关注长期稳定的基础能力，包括操作系统、网络、存储、数据库、分布式系统、算法和常用命令。

## 核心问题

- Linux 系统如何安装、配置和排障？
- 网络、存储和数据库如何支撑上层系统？
- 分布式系统解决了哪些单机系统无法解决的问题？
- 常用命令和基础算法如何提升日常工程效率？

## 学习路线

1. 从 Linux 和常用命令开始，建立基本操作能力。
2. 学习网络、存储和数据库，理解系统运行依赖。
3. 继续学习分布式系统，建立架构层面的理解。
4. 补充算法和数学基础，用于分析复杂系统和工程问题。

## 内容索引

- [Linux](linux/README.md)
- [Commands](commands/README.md)
- [Network](network/README.md)
- [Storage](storage/README.md)
- [Database](database/README.md)
- [Distributed Systems](distributed-systems/README.md)
- [Algorithms](algorithms/README.md)
- [Mathematics](mathematics/README.md)

## 后续计划

- 补齐 Linux 安装和初始化流程。
- 整理网络、存储、数据库的核心概念索引。
- 将常用命令沉淀为可复用的排障手册。
```

- [ ] **Step 2: Create `engineering/README.md`**

Write this file:

```md
# Engineering

## 定位

Engineering 记录面向真实系统交付、部署、运行和维护的工程实践。

这一部分以云原生、DevOps、平台工程、可观测性和故障复盘为主，连接基础知识和实际生产环境。

## 核心问题

- 应用如何从代码变成稳定运行的服务？
- 容器、Kubernetes 和平台工程如何提升交付效率？
- 如何通过可观测性和故障复盘提升系统稳定性？
- 工程团队如何构建可复用的部署、运维和排障能力？

## 学习路线

1. 学习 Docker，理解容器化的基本模型。
2. 学习 Kubernetes，掌握容器编排和云原生基础设施。
3. 学习 DevOps 和平台工程，理解工程效率体系。
4. 学习可观测性、故障排查和复盘方法，提升生产系统治理能力。
5. 补充 Runtime 等底层主题，理解容器运行机制。

## 内容索引

- [Docker](docker/README.md)
- [Kubernetes](kubernetes/README.md)
- [DevOps](devops/README.md)
- [Platform Engineering](platform-engineering/README.md)
- [Runtime](runtime/README.md)
- [Observability](observability/README.md)
- [Troubleshooting](troubleshooting/README.md)
- [Postmortem](postmortem/README.md)

## 后续计划

- 统一 Docker、Kubernetes 和 DevOps 的学习路线。
- 将实验案例整理为可复现的实践手册。
- 补充平台工程和可观测性的系统化内容。
```

- [ ] **Step 3: Create `ai-infra/README.md`**

Write this file:

```md
# AI Infrastructure

## 定位

AI Infrastructure 记录支撑大模型、RAG、推理服务和 AI 工程化的基础设施知识。

这一部分关注模型如何从实验走向可运行、可观测、可扩展的工程系统。

## 核心问题

- RAG、向量数据库和知识库如何支撑 AI 应用？
- LLMOps 如何管理模型、提示词、评测和发布流程？
- GPU、推理服务和 AI Runtime 如何影响模型服务性能？
- AI Native 应用与传统应用在基础设施上有什么差异？

## 学习路线

1. 从 RAG 和向量数据库开始，理解 AI 应用的数据基础。
2. 学习 LLMOps，建立模型应用的工程化流程。
3. 学习推理服务、AI Runtime 和 GPU 基础设施，理解运行时能力。
4. 继续探索 AI Native，把 AI 能力融入工程系统设计。

## 内容索引

- [RAG](rag/README.md)
- [Vector Database](vector-database/README.md)
- [LLMOps](llmops/README.md)
- [Inference Serving](inference-serving/README.md)
- [AI Runtime](ai-runtime/README.md)
- [GPU Infrastructure](gpu-infra/README.md)
- [AI Native](ai-native/README.md)

## 后续计划

- 梳理 RAG 系统的核心组件和数据流。
- 补充向量数据库选型、索引和检索质量相关内容。
- 建立推理服务和 GPU 基础设施的实践索引。
```

- [ ] **Step 4: Create `research/README.md`**

Write this file:

```md
# Research

## 定位

Research 记录偏研究方法、创新网络、专利分析、复杂网络和知识图谱方向的学习材料。

这一部分关注如何组织问题、分析数据、理解知识与人才流动中的结构关系。

## 核心问题

- 如何用系统化方法开展技术和产业研究？
- 创新网络、复杂网络和知识图谱如何刻画真实世界关系？
- 专利、人才流动和知识扩散可以如何建模和分析？

## 学习路线

1. 从研究方法开始，建立问题定义和分析框架。
2. 学习复杂网络和知识图谱，理解关系型数据表达。
3. 进入创新网络、专利分析和人才流动等具体研究主题。

## 内容索引

- [Methodology](methodology/README.md)
- [Complex Network](complex-network/README.md)
- [Knowledge Graph](knowledge-graph/README.md)
- [Innovation Network](innovation-network/README.md)
- [Patent Analysis](patent-analysis/README.md)
- [Talent Mobility](talent-mobility/README.md)

## 后续计划

- 补充研究方法中的问题定义、数据收集和分析流程。
- 将复杂网络与知识图谱内容和 AI Infra 建立关联。
- 整理专利分析和人才流动的案例模板。
```

- [ ] **Step 5: Create `thinking/README.md`**

Write this file:

```md
# Thinking

## 定位

Thinking 记录技术体系、系统思维、软件工程、AI 与 DevOps 关系等偏长期思考的内容。

这一部分不追求操作步骤，而是沉淀判断框架、技术观念和架构理解。

## 核心问题

- 如何建立长期可演进的技术体系？
- 系统思维如何帮助理解复杂工程问题？
- AI、DevOps 和基础设施的发展会如何影响软件工程？
- 技术哲学和工程实践之间如何相互影响？

## 学习路线

1. 从系统思维开始，建立整体视角。
2. 阅读软件工程和技术哲学相关内容，沉淀工程判断。
3. 结合 AI and DevOps、Infrastructure Future，思考技术趋势。

## 内容索引

- [System Thinking](system-thinking/README.md)
- [Software Engineering](software-engineering/README.md)
- [Technical Philosophy](technical-philosophy/README.md)
- [AI and DevOps](ai-and-devops/README.md)
- [Infrastructure Future](infrastructure-future/README.md)

## 后续计划

- 持续沉淀技术判断和架构思考。
- 将实践类内容中的经验上升为方法论。
- 建立工程实践与长期趋势之间的关联。
```

## Task 2: Standardize Engineering Core README Files

**Files:**

- Modify: `engineering/devops/README.md`
- Modify: `engineering/kubernetes/README.md`
- Modify: `engineering/docker/README.md`

- [ ] **Step 1: Replace `engineering/devops/README.md`**

Write this file:

```md
# DevOps

## 定位

DevOps 关注开发、测试、交付和运维之间的协作方式，是把软件稳定交付到生产环境的一套工程实践。

在这个知识库中，DevOps 连接 Docker、Kubernetes、CI/CD、平台工程、可观测性和故障复盘等主题。

## 核心问题

- 如何让代码变更更快、更安全地进入生产环境？
- 如何通过自动化降低部署和运维成本？
- 如何把环境、配置、发布和回滚流程标准化？
- 如何通过度量、监控和复盘持续改进工程效率？

## 学习路线

1. 理解 DevOps 的目标：提升交付效率和系统稳定性。
2. 学习版本控制、CI/CD、制品管理和环境管理。
3. 结合 Docker 和 Kubernetes 实践标准化部署。
4. 引入可观测性、告警和故障复盘，形成闭环改进。
5. 进一步理解平台工程如何把 DevOps 能力产品化。

## 内容索引

- [Docker](../docker/README.md)
- [Kubernetes](../kubernetes/README.md)
- [Platform Engineering](../platform-engineering/README.md)
- [Observability](../observability/README.md)
- [Troubleshooting](../troubleshooting/README.md)
- [Postmortem](../postmortem/README.md)

## 后续计划

- 补充 CI/CD 基础概念和实践路线。
- 整理制品仓库、镜像仓库和发布流程。
- 将现有 Kubernetes 案例纳入 DevOps 实践链路。
```

- [ ] **Step 2: Replace `engineering/kubernetes/README.md` while preserving existing links**

Write this file:

```md
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
  - _TODO_[kubeadm-v1.32.5-offline](preactice/kubeadm/v1.32.5-offline/README.md) `v1.33.5` `online` `20251115`
  - _TODO_[kubeadm-v1.28.15](preactice/kubeadm/v1.28.15/README.md) `v1.28.15` `online` `20251115`
  - [kubadm-v1.25.6](preactice/kubeadm/v1.25.6/README.md) `v1.25.6` `online` `archive`
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
```

- [ ] **Step 3: Replace `engineering/docker/README.md` while preserving existing links**

Write this file:

```md
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
- _TODO_[Docker架构](basic/architecture.md)
- _TODO_[容器与虚拟机对比](basic/container-vs-vm.md)
- _TODO_[镜像与容器](basic/images-and-containers.md)
- _TODO_[网络模式](basic/networking.md)
- _TODO_[存储与卷](basic/storage-and-volumes.md)

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
```

## Task 3: Standardize Foundations and AI Infrastructure Core README Files

**Files:**

- Modify: `foundations/linux/README.md`
- Modify: `ai-infra/rag/README.md`
- Modify: `ai-infra/llmops/README.md`
- Modify: `ai-infra/gpu-infra/README.md`
- Modify: `ai-infra/inference-serving/README.md`

- [ ] **Step 1: Replace `foundations/linux/README.md`**

Write this file:

```md
# Linux

## 定位

Linux 是系统工程、云原生、DevOps 和 AI 基础设施的基础运行环境。

在这个知识库中，Linux 主要记录系统安装、初始化、权限、服务、网络、存储和常见排障经验。

## 核心问题

- 如何安装和初始化不同发行版的 Linux 系统？
- 如何理解用户、权限、服务、进程、网络和存储？
- 如何为 Kubernetes、Docker 和 AI 基础设施准备稳定的操作系统环境？
- 如何沉淀可复用的系统排障命令和流程？

## 学习路线

1. 从发行版安装和基础初始化开始。
2. 学习用户权限、包管理、服务管理和网络配置。
3. 结合 Docker 和 Kubernetes 需求理解内核、存储和网络能力。
4. 持续积累排障命令和系统调优经验。

## 内容索引

### Installation Guides

- Centos
  - _TODO_[Centos 7](installationGuides/centos/7/README.md)
- Fedora
  - _TODO_[Fedora Server 42](installationGuides/fedora/Server/42/README.md)
  - _TODO_[Fedora Cloud 42](installationGuides/fedora/Cloud/42/README.md)
- Ubuntu
  - _TODO_[Ubuntu 18.04](installationGuides/ubuntu/18.04/README.md)
  - _TODO_[Ubuntu 20.04](installationGuides/ubuntu/20.04/README.md)
  - _TODO_[Ubuntu 22.04](installationGuides/ubuntu/22.04/README.md)
  - _TODO_[Ubuntu 24.04](installationGuides/ubuntu/24.04/README.md)

### Automation

- _TODO_[ansible](ansible/check-ssh-sudo.md)

## 后续计划

- 补齐主流发行版安装后的初始化检查清单。
- 整理 Linux 命令、服务管理、网络和磁盘相关内容。
- 将系统初始化和 Kubernetes 节点准备流程关联起来。
```

- [ ] **Step 2: Normalize `ai-infra/rag/README.md`**

Inspect the current file first. If it already contains detailed useful content, preserve it below the new entry sections under a heading named `## Notes`. Ensure the top of the file starts with:

```md
# RAG

## 定位

RAG（Retrieval-Augmented Generation）通过检索外部知识增强大模型回答能力，是 AI 应用落地中的关键架构模式。

在这个知识库中，RAG 连接文档处理、向量数据库、检索策略、提示词编排和结果评测。

## 核心问题

- 如何把非结构化文档转换为可检索知识？
- Chunk、Embedding、索引和召回策略如何影响回答质量？
- 如何评估 RAG 系统的准确性、稳定性和可维护性？
- RAG 与知识图谱、向量数据库和 LLMOps 如何协同？

## 学习路线

1. 理解 RAG 的基本数据流：加载、切分、向量化、检索、生成。
2. 学习向量数据库和 Embedding 模型的基本概念。
3. 研究检索质量、重排、上下文压缩和提示词编排。
4. 建立评测、观测和迭代优化流程。

## 内容索引

- [Vector Database](../vector-database/README.md)
- [LLMOps](../llmops/README.md)
- [Knowledge Graph](../../research/knowledge-graph/README.md)

## 后续计划

- 整理 RAG 系统组件和典型架构图。
- 补充文档切分、Embedding、检索和重排的实践记录。
- 建立 RAG 评测指标和问题排查清单。
```

- [ ] **Step 3: Normalize `ai-infra/llmops/README.md`**

Inspect the current file first. If it already contains detailed useful content, preserve it below the new entry sections under a heading named `## Notes`. Ensure the top of the file starts with:

```md
# LLMOps

## 定位

LLMOps 关注大模型应用从开发、评测、发布到运维的工程化流程。

在这个知识库中，LLMOps 用来连接提示词管理、模型评测、RAG、推理服务、监控和持续迭代。

## 核心问题

- 如何管理提示词、模型版本、数据集和评测结果？
- 如何让大模型应用具备可测试、可发布、可回滚的工程流程？
- 如何监控大模型应用的质量、成本、延迟和稳定性？
- LLMOps 与 DevOps、MLOps 和平台工程之间如何衔接？

## 学习路线

1. 理解大模型应用生命周期和传统 DevOps 的差异。
2. 学习提示词、数据集、评测和实验管理。
3. 结合 RAG 和推理服务建立发布与观测流程。
4. 进一步探索平台化、自动化和治理能力。

## 内容索引

- [RAG](../rag/README.md)
- [Inference Serving](../inference-serving/README.md)
- [AI Runtime](../ai-runtime/README.md)
- [DevOps](../../engineering/devops/README.md)
- [Platform Engineering](../../engineering/platform-engineering/README.md)

## 后续计划

- 梳理 LLMOps 与 DevOps、MLOps 的边界。
- 补充提示词管理、评测集和发布流程实践。
- 建立大模型应用的质量和成本观测指标。
```

- [ ] **Step 4: Normalize `ai-infra/gpu-infra/README.md`**

Inspect the current file first. If it already contains detailed useful content, preserve it below the new entry sections under a heading named `## Notes`. Ensure the top of the file starts with:

```md
# GPU Infrastructure

## 定位

GPU Infrastructure 记录 AI 训练和推理所需的 GPU 资源、驱动、调度、监控和性能优化知识。

在这个知识库中，GPU Infrastructure 是连接硬件资源、容器运行时、Kubernetes 和 AI 推理服务的基础层。

## 核心问题

- GPU 驱动、CUDA、容器运行时和 Kubernetes 调度如何协同？
- 如何管理 GPU 资源的分配、隔离、监控和利用率？
- 推理服务如何受显存、带宽、批处理和并发影响？
- 如何为 AI 平台设计稳定、可观测的 GPU 资源池？

## 学习路线

1. 理解 GPU、CUDA、驱动和容器运行时的关系。
2. 学习 Kubernetes 中 GPU 资源暴露和调度方式。
3. 研究推理服务中的显存、吞吐和延迟优化。
4. 建立 GPU 监控、容量规划和故障排查流程。

## 内容索引

- [AI Runtime](../ai-runtime/README.md)
- [Inference Serving](../inference-serving/README.md)
- [Kubernetes](../../engineering/kubernetes/README.md)
- [Observability](../../engineering/observability/README.md)

## 后续计划

- 补充 GPU 节点初始化和驱动安装流程。
- 整理 Kubernetes GPU 调度和监控实践。
- 沉淀推理场景下的 GPU 性能排查清单。
```

- [ ] **Step 5: Normalize `ai-infra/inference-serving/README.md`**

Inspect the current file first. If it already contains detailed useful content, preserve it below the new entry sections under a heading named `## Notes`. Ensure the top of the file starts with:

```md
# Inference Serving

## 定位

Inference Serving 关注模型如何以在线服务的形式稳定、高效地对外提供推理能力。

在这个知识库中，推理服务连接模型运行时、GPU 基础设施、服务治理、可观测性和 LLMOps。

## 核心问题

- 模型服务如何在延迟、吞吐、成本和稳定性之间取舍？
- 批处理、并发、缓存、量化和模型加载如何影响推理性能？
- 如何在 Kubernetes 或平台环境中部署和治理推理服务？
- 如何观测推理服务的质量、性能和资源使用情况？

## 学习路线

1. 理解在线推理服务的基本请求链路。
2. 学习模型运行时、服务框架和部署形态。
3. 结合 GPU 基础设施分析性能瓶颈。
4. 引入监控、评测和发布流程，形成持续优化闭环。

## 内容索引

- [AI Runtime](../ai-runtime/README.md)
- [GPU Infrastructure](../gpu-infra/README.md)
- [LLMOps](../llmops/README.md)
- [Kubernetes](../../engineering/kubernetes/README.md)
- [Observability](../../engineering/observability/README.md)

## 后续计划

- 梳理常见推理服务框架和部署模式。
- 补充延迟、吞吐、显存和成本优化实践。
- 建立推理服务的发布、监控和排障清单。
```

## Task 4: Verify Links and Review Changed Markdown

**Files:**

- Read: all files changed in Tasks 1-3

- [ ] **Step 1: Check intended changed files**

Run:

```bash
git status --short
```

Expected: changed files include the README files from Tasks 1-3 and the superpowers design/plan documents. Existing unrelated user changes may also appear and should not be modified.

- [ ] **Step 2: Verify key linked paths exist**

Run:

```bash
test -e foundations/linux/README.md && test -e foundations/commands/README.md && test -e foundations/network/README.md && test -e foundations/storage/README.md && test -e foundations/database/README.md && test -e foundations/distributed-systems/README.md && test -e foundations/algorithms/README.md && test -e foundations/mathematics/README.md && test -e engineering/docker/README.md && test -e engineering/kubernetes/README.md && test -e engineering/devops/README.md && test -e engineering/platform-engineering/README.md && test -e engineering/runtime/README.md && test -e engineering/observability/README.md && test -e engineering/troubleshooting/README.md && test -e engineering/postmortem/README.md && test -e ai-infra/rag/README.md && test -e ai-infra/vector-database/README.md && test -e ai-infra/llmops/README.md && test -e ai-infra/inference-serving/README.md && test -e ai-infra/ai-runtime/README.md && test -e ai-infra/gpu-infra/README.md && test -e ai-infra/ai-native/README.md && test -e research/methodology/README.md && test -e research/complex-network/README.md && test -e research/knowledge-graph/README.md && test -e research/innovation-network/README.md && test -e research/patent-analysis/README.md && test -e research/talent-mobility/README.md && test -e thinking/system-thinking/README.md && test -e thinking/software-engineering/README.md && test -e thinking/technical-philosophy/README.md && test -e thinking/ai-and-devops/README.md && test -e thinking/infrastructure-future/README.md
```

Expected: command exits with status `0` and no output.

- [ ] **Step 3: Read changed README files for consistency**

Read these files and verify they use the expected headings and concise navigation style:

```text
foundations/README.md
engineering/README.md
ai-infra/README.md
research/README.md
thinking/README.md
engineering/devops/README.md
engineering/kubernetes/README.md
engineering/docker/README.md
foundations/linux/README.md
ai-infra/rag/README.md
ai-infra/llmops/README.md
ai-infra/gpu-infra/README.md
ai-infra/inference-serving/README.md
```

Expected: each file contains `## 定位`, `## 核心问题`, `## 学习路线`, `## 内容索引`, and `## 后续计划`, unless preserved detailed notes appear after those sections under `## Notes`.

- [ ] **Step 4: Final diff review**

Run:

```bash
git diff -- docs/superpowers/specs/2026-05-20-knowledge-base-readme-structure-design.md docs/superpowers/plans/2026-05-20-knowledge-base-readme-structure.md foundations/README.md engineering/README.md ai-infra/README.md research/README.md thinking/README.md engineering/devops/README.md engineering/kubernetes/README.md engineering/docker/README.md foundations/linux/README.md ai-infra/rag/README.md ai-infra/llmops/README.md ai-infra/gpu-infra/README.md ai-infra/inference-serving/README.md
```

Expected: diff only contains documentation structure updates and no unrelated content deletion.

## Self-Review

- Spec coverage: Tasks cover first-level entry pages, selected second-level README normalization, link preservation, `_TODO_` retention, and verification.
- Placeholder scan: The plan intentionally avoids unresolved `TBD` or implementation gaps. Existing `_TODO_` strings are content markers preserved from the repository, not plan placeholders.
- Type consistency: Not applicable; this is a Markdown-only documentation change.
