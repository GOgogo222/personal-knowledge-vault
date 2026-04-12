---
title: "Claude Code"
type: concept
tags: [ai-tools, coding, automation, anthropic]
created: 2026-04-12
updated: 2026-04-12
sources: 1
---

# Claude Code

## 概述

**Claude Code** 是 Anthropic 推出的 AI 编程助手，支持命令行、桌面应用、Web 应用和 IDE 扩展（VS Code、JetBrains）。在知识管理场景中，Claude Code 可以批量处理本地文件、生成问题清单、保存问答记录等。

## 在知识管理中的应用

在[[../entities/longdechen12|观自]]的 [[../concepts/ipo模型|IPO 工作流]]中，Claude Code 扮演关键角色：

### 1. 批量生成问题清单
- 读取 `raw/` 目录下的所有 Markdown 文档
- 基于文档内容生成 100 个深度问题
- 解决"不会提问"的痛点

### 2. 本地化知识沉淀
- 将 [[../concepts/notebooklm|NotebookLM]] 的问答结果保存到本地 `wiki/` 目录
- 形成可持续积累的个人知识库
- 支持随时调用、扩展、二次创作

### 3. 自动化工具开发
- 开发抖音博主视频逐字稿批量导入工具
- 搭建 RPA 程序批量剪藏网页内容
- 定制化自动化脚本

## 与 NotebookLM 的分工

| 工具 | 职责 | 优势 |
|------|------|------|
| Claude Code | 提问、本地化存储、自动化 | 编程能力强、本地文件操作 |
| NotebookLM | 基于知识库回答 | 无幻觉、可溯源、长文本处理 |

## 核心价值

1. **降低成本**：通过 NotebookLM 接口处理大量文档，避免直接消耗大量 token
2. **知识沉淀**：将问答永久保存在本地，形成个人知识资产
3. **自动化**：批量处理重复性任务，提升效率

## 参考

- [[../sources/00后ai沙龙能力来源|00 后 AI 沙龙：能力来源方法论]]
- [[../concepts/notebooklm|NotebookLM]]
- [[../concepts/obsidian|Obsidian]]
