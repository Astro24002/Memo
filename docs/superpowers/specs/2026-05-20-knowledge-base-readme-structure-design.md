# Knowledge Base README Structure Design

## Goal

Improve the knowledge base from a collection of topic notes into a browsable, maintainable technical system. The first pass focuses on entry pages and core topic README files, not deep article content.

## Scope

This work will standardize first-level and selected second-level README files.

First-level entry pages:

- `foundations/README.md`
- `engineering/README.md`
- `ai-infra/README.md`
- `research/README.md`
- `thinking/README.md`

Core second-level entry pages:

- `engineering/devops/README.md`
- `engineering/kubernetes/README.md`
- `engineering/docker/README.md`
- `foundations/linux/README.md`
- `ai-infra/rag/README.md`
- `ai-infra/llmops/README.md`
- `ai-infra/gpu-infra/README.md`
- `ai-infra/inference-serving/README.md`

## README Template

Entry pages should generally use this structure:

```md
# Topic

## 定位

## 核心问题

## 学习路线

## 内容索引

## 后续计划
```

The template may be shortened when a page is intentionally lightweight, but the page should still clearly explain what the topic is for and where readers should go next.

## Editing Principles

- Preserve existing directories and links unless a link is clearly broken.
- Do not rename large directory trees in this pass.
- Preserve existing useful content and reorganize it into the shared structure.
- Keep `_TODO_` markers for now, but make unfinished areas easier to identify from the entry pages.
- Prefer concise, navigational text over long explanatory articles in README files.
- Use README files as maps. Detailed notes should stay in topic-specific files.

## Expected Result

After this pass, a reader should be able to start from the repository root and understand:

- The major knowledge domains in the repository.
- The role of each first-level domain.
- The main questions each core topic tries to answer.
- A reasonable learning path through Kubernetes, Docker, Linux, DevOps, and AI infrastructure topics.
- Which areas are mature and which are planned for future completion.

## Out of Scope

- Deep rewriting of individual technical articles.
- Large-scale directory renaming.
- Removing historical notes or archived content.
- Validating every Kubernetes or Docker manifest.
- Replacing all `_TODO_` markers with finished content.

## Verification

Verification should include:

- Reading changed README files for clear structure and consistent headings.
- Checking that newly added links point to existing paths.
- Running a lightweight repository status check to confirm only intended files changed.
