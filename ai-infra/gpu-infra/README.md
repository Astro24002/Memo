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
