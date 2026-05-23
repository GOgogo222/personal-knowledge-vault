---
title: "Paraformer"
type: concept
tags: [speech-recognition, model, deep-learning]
created: 2026-04-12
updated: 2026-04-12
sources: 1
---

# Paraformer

## 概述

**Paraformer** 是阿里巴巴通义语音实验室开源的工业级中文语音识别（ASR）模型，属于 [[../entities/funasr|FunASR]] 模型家族的核心成员之一。Paraformer-Large 是其中性能最强的版本，在 ModelScope 上的下载量超过 1300 万次，是目前最佳的开源中文 ASR 模型之一。

## 特点

- **准确率高**：在多个中文 ASR 基准测试上达到领先水平
- **时间戳预测**：原生集成时间戳预测能力，无需额外的强制对齐步骤
- **非自回归架构**：推理速度更快
- **热词定制**：SeACo-Paraformer 变体支持指定热词提升特定词汇的识别准确率

## 变体

| 模型 | 特点 |
|------|------|
| Paraformer-Large | 通用中文大模型，高精度 |
| SeACo-Paraformer | 支持热词（实体词、专有名词等）定制 |

## 应用

集成在 [[../sources/funclip|FunClip]] 中用于视频语音识别，支持精准定位文本片段对应的视频时间段。

## 参考

- [[../entities/funasr|FunASR]]
- [[../concepts/语音识别|语音识别 (ASR)]]
