---
title: "IPO 模型"
type: concept
tags: [methodology, workflow, knowledge-management]
created: 2026-04-12
updated: 2026-04-12
sources: 1
---

# IPO 模型

## 概述

**IPO 模型**（Input - Process - Output）是[[../entities/longdechen12|观自]]提出的知识变现工作流框架，用于在 3 小时内摸透一个领域的核心内容并快速转化为商业产品。

## 三个阶段

### I - Input（输入/喂料）：打破信息壁垒

**目标**：将所有信息源转化为 AI 可理解的 [[../concepts/markdown|Markdown]] 格式。

**耗时**：0.5~1 小时

**核心工具**：
- 网页类：[[../concepts/youtube-to-notebooklm|YouTube to NotebookLM]]、[[../concepts/obsidian剪藏助手|Obsidian 剪藏助手]]、[[../concepts/cloud-document-converter|Cloud Document Converter]]
- 视频类：[[../concepts/get笔记|Get 笔记]]、[[../concepts/通义听悟|通义听悟]]

**关键洞察**：打破平台壁垒、付费壁垒、媒介壁垒（视频/文章），统一转化为 Markdown。

### P - Process（处理/消化）：NotebookLM × Claude Code 联动

**目标**：基于真实材料生成可信的问答，并沉淀到本地知识库。

**耗时**：1~2 小时

**工作流程**：
1. 将 Markdown 文档上传到 [[../concepts/notebooklm|NotebookLM]] 知识库
2. 用 [[../concepts/claude-code|Claude Code]] 批量生成 100 个问题清单
3. 在 NotebookLM 中批量提问
4. 用 Claude Code 将所有问答保存到本地 `wiki/` 目录

**解决的痛点**：
- 不会提问 → AI 帮你生成问题
- 答案不可信 → NotebookLM 基于真实材料，可溯源
- 知识没有沉淀 → 本地化存储，持续积累

### O - Output（输出/表达）：人机协作内容创作

**目标**：保持"活人味"，输出符合个人风格的内容。

**耗时**：0.5~1 小时

**工作流程**：
1. 用 [[../concepts/xmind|Xmind]] 手搓思维导图（框架）
2. 用语音输入法（[[../concepts/闪电说|闪电说]]）或语音转文字（[[../concepts/千问录音|千问录音]]）输出逐字稿
3. 手搓 [[../concepts/keynote|Keynote]] 幻灯片

**核心原则**：
> **用 AI 做研究，用人做表达。**

## 应用场景

- 线下培训课程准备
- 咨询方案快速产出
- 内容创作（文章、视频脚本、演讲稿）
- 领域研究与对标分析

## 核心价值

1. **速度**：3 小时摸透一个领域
2. **可信**：基于真实材料，不产生幻觉
3. **沉淀**：知识永久保存在本地，可持续积累
4. **人性化**：保持个人表达风格，避免 AI 生成的僵硬感

## 参考

- [[../sources/00后ai沙龙能力来源|00 后 AI 沙龙：能力来源方法论]]
- [[../entities/longdechen12|观自（@longdechen12）]]
- [[../concepts/notebooklm|NotebookLM]]
- [[../concepts/claude-code|Claude Code]]
