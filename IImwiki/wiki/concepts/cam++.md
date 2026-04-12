---
title: "CAM++"
type: concept
tags: [speaker-recognition, model, deep-learning]
created: 2026-04-12
updated: 2026-04-12
sources: 1
---

# CAM++

## 概述

**CAM++** 是阿里巴巴通义语音实验室开源的说话人识别（Speaker Recognition）模型，集成在 [[../entities/funasr|FunASR]] 框架中。该模型能够自动识别并标注音频中不同说话人的身份。

## 功能

- **说话人分离**：自动区分音频中的不同说话人
- **说话人标注**：为每个语音片段分配说话人 ID（如 spk0, spk1, spk2）
- **多说话人场景**：支持会议、访谈等多人对话场景

## 应用

在 [[../sources/funclip|FunClip]] 中，用户可以：
1. 启用"识别说话人"功能
2. 获取带有说话人 ID 的识别结果
3. 按说话人 ID 剪辑特定人物的视频片段（如只剪辑 spk0 或 spk0#spk3 的片段）

## 应用场景

- **会议记录**：区分不同发言人的内容
- **访谈剪辑**：提取特定嘉宾的发言片段
- **多人对话分析**：统计各说话人的发言时长和频次
- **字幕标注**：为不同说话人生成带标识的字幕

## 参考

- [[../entities/funasr|FunASR]]
- [[../sources/funclip|FunClip]]
- [[../concepts/语音识别|语音识别 (ASR)]]
