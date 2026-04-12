---
title: "FunASR"
type: entity
tags: [speech-recognition, open-source, alibaba]
created: 2026-04-12
updated: 2026-04-12
sources: 1
---

# FunASR

## 概述

**FunASR** 是阿里巴巴通义语音实验室开源的工业级语音识别框架，旨在搭建学术研究与工业应用之间的桥梁。通过支持 ModelScope 上发布的工业级语音识别模型的训练和微调，让研究者和开发者更便捷地进行语音识别模型的研发和生产。

## 核心特性

- **工业级模型**：发布 [[../concepts/paraformer|Paraformer]] 系列模型，性能优异
- **开源生态**：支持模型训练、微调、推理的完整工具链
- **时间戳预测**：原生支持时间戳预测，无需额外对齐模型
- **热词定制**：SeACo-Paraformer 支持热词定制功能
- **易用性**：提供简洁的 API 和命令行工具

## 版本历史

- **v1.0 (2024/02/28)**：重大版本更新，支持 SeACo-Paraformer 热词定制

## 应用

- [[../sources/funclip|FunClip]]：基于 FunASR 的视频剪辑工具
- 语音识别服务
- 字幕生成
- 语音转文字应用

## 相关链接

- GitHub：https://github.com/alibaba-damo-academy/FunASR
- ModelScope：https://modelscope.cn/

## 参考

- [[../concepts/paraformer|Paraformer]]
- [[../concepts/语音识别|语音识别 (ASR)]]
