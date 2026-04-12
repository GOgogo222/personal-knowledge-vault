---
title: "NotebookLM"
type: concept
tags: [ai-tools, knowledge-management, rag, google]
created: 2026-04-12
updated: 2026-04-12
sources: 1
---

# NotebookLM

## 概述

**NotebookLM** 是 Google 推出的 AI 知识管理工具，允许用户上传文档作为知识库，并基于这些文档进行问答。核心特点是**完全基于用户提供的真实材料生成回答，不产生幻觉**，每个答案都有可追溯的原文来源。

## 核心特性

1. **无幻觉**：所有回答完全基于上传的材料生成，每个答案右上角标注原文位置，点击可跳转查看
2. **大容量**：支持上传最多 300 个文档
3. **长文本处理**：底层接入 Gemini 模型，长文本处理效果优异
4. **多格式输出**：支持音频概要、视频脚本、幻灯片等多种输出格式

## 使用场景

- **领域研究**：上传某领域的大量资料，快速提炼核心知识点
- **博主分析**：导入博主全部视频/文章，研究其内容体系
- **内容创作**：基于知识库生成可信的内容素材
- **对标研究**：分析竞品或行业标杆的全部内容

## 与其他工具的联动

在[[../entities/longdechen12|观自]]的 [[../concepts/ipo模型|IPO 工作流]]中：
- **NotebookLM 与 [[../concepts/claude-code|Claude Code]] 联动**：Claude Code 批量生成问题 → NotebookLM 基于知识库回答 → Claude Code 将答案保存到本地
- **分工**：NotebookLM 保证回答的可信度和溯源，Claude Code 负责提问和本地化存储
- **省钱**：相比直接让 Claude Code 读取数百篇文档，通过 NotebookLM 接口大幅降低 token 消耗

## 局限性

- 自动生成的幻灯片过于僵硬，不适合直接用于演讲（[[../entities/longdechen12|观自]]建议手搓 Keynote）
- 需要科学上网（Google 产品）

## 参考

- [[../sources/00后ai沙龙能力来源|00 后 AI 沙龙：能力来源方法论]]
- [[../concepts/claude-code|Claude Code]]
- [[../concepts/obsidian|Obsidian]]
