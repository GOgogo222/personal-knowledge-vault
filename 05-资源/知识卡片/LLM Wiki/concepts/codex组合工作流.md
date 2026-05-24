---
title: "Codex 组合工作流"
type: concept
tags: [codex, workflow, multi-agent, automation]
created: 2026-05-24
updated: 2026-05-24
sources: 1
---

# Codex 组合工作流

## Overview

Codex 组合工作流指把 Codex 与其他 agent、模型、工具或知识库连接起来，而不是单独把它当作一个聊天式代码助手。

## Patterns

### Claude Code 里调用 Codex

`codex-plugin-cc` 这类方案让 Claude Code 终端中出现 Codex slash commands。典型用法是：Claude Code 写实现，Codex 做 review、安全审计、bug investigation 或第二意见。

风险是两个 agent 可能互相推动，形成长循环，快速消耗额度。

### Codex + Ollama / Open Models

`codex --oss` 代表另一条路线：让 Codex CLI 作为本地 agent 外壳，底层模型换成开放权重模型。这适合低成本实验，但复杂任务质量要单独验证。

### Codex + Obsidian

在本仓库里，Codex 适合做：

- 抓取来源并生成摘要页。
- 更新 `index.md` 和 `log.md`。
- 修复 Obsidian 链接和附件路径。
- 按 PARA 结构移动资料。
- 自动检查 GitHub 同步状态。

## Guardrails

- 每次组合只给一个明确目标。
- 指定谁负责实现、谁负责审查。
- 限制循环轮数。
- 保留原始来源链接和操作日志。
- 涉及 shell/Git/网络权限时优先小步提交。

## Related

- [[codex]]
- [[codex-vs-claude-code]]
- [[本地知识库]]

