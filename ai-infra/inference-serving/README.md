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
