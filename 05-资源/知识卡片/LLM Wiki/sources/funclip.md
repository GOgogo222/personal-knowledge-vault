---
title: "FunClip"
type: source
tags: [video-editing, speech-recognition, ai-tools, open-source]
created: 2026-04-12
updated: 2026-04-12
sources: 1
---

# FunClip

> 原始来源：https://github.com/modelscope/FunClip

## 概述

**FunClip** 是阿里巴巴达摩院开源的全自动视频剪辑工具，完全开源且支持本地部署。核心特性是利用 [[../entities/funasr|FunASR]] 的 Paraformer 系列模型进行视频语音识别，用户可以从识别结果中自由选择文本片段或说话人，一键获取对应的视频片段。

## 核心功能

### 1. 语音识别 (ASR)
- 集成 [[../concepts/paraformer|Paraformer-Large]] 模型，ModelScope 下载量超 1300 万次
- 支持中英文识别（运行 `python funclip/launch.py -l en` 切换英文模式）
- 精准的时间戳预测能力
- 支持 [[../concepts/热词定制|热词定制]]（SeACo-Paraformer），可指定实体词、人名等提升识别准确率

### 2. 说话人识别
- 集成 [[../concepts/cam++|CAM++]] 说话人识别模型
- 自动标注说话人 ID（如 spk0, spk1）
- 支持按说话人 ID 剪辑特定人物的片段

### 3. LLM 智能剪辑 (v2.0.0+)
- 集成大语言模型（Qwen 系列、GPT 系列等）
- 工作流程：
  1. 识别后选择 LLM 模型并配置 API key
  2. 点击"LLM Inference"，自动将 prompt + SRT 字幕发送给 LLM
  3. 点击"AI Clip"，根据 LLM 输出的时间戳自动剪辑
  4. 可自定义 prompt 探索不同剪辑策略

### 4. 多段剪辑与字幕
- 支持自由选择多个片段批量剪辑
- 自动生成完整视频 SRT 字幕和目标片段 SRT 字幕
- 可为每个段落配置不同的起止时间偏移量

## 技术架构

- **前端**：Gradio 交互界面，支持浏览器访问
- **ASR 引擎**：[[../entities/funasr|FunASR]] 1.0+
- **说话人识别**：CAM++ 模型
- **视频处理**：moviepy
- **部署方式**：本地部署或服务器部署

## 安装与使用

### 基础安装
```bash
git clone https://github.com/modelscope/FunClip.git
cd FunClip
pip install -r ./requirements.txt
```

### 启动方式
```bash
# Gradio 界面
python funclip/launch.py

# 命令行模式
# Step 1: 识别
python funclip/videoclipper.py --stage 1 \
  --file examples/video.mp4 \
  --output_dir ./output

# Step 2: 剪辑
python funclip/videoclipper.py --stage 2 \
  --file examples/video.mp4 \
  --output_dir ./output \
  --dest_text '目标文本片段' \
  --start_ost 0 \
  --end_ost 100 \
  --output_file './output/res.mp4'
```

## 版本历史

- **v2.0.0 (2024/05/13)**：支持 LLM 智能剪辑
- **v1.1.0 (2024/05/09)**：UI 升级、支持配置输出目录、修复 FunASR 接口升级导致的 bug
- **2024/06/12**：支持英文音频识别
- **2024/02/28**：升级到 FunASR 1.0，支持热词定制
- **2023/10/10**：支持说话人分离识别

## 应用场景

- 会议录音剪辑（按说话人或关键词提取片段）
- 视频内容二创（快速定位并剪辑精彩片段）
- 字幕生成与校对
- 多语言视频处理（中英文）

## 相关链接

- GitHub：https://github.com/modelscope/FunClip
- ModelScope 体验：https://modelscope.cn/studios/iic/funasr_app_clipvideo/summary
- HuggingFace 体验：https://huggingface.co/spaces/R1ckShi/FunClip

## 参考

- [[../entities/funasr|FunASR]]
- [[../concepts/paraformer|Paraformer]]
- [[../concepts/语音识别|语音识别 (ASR)]]
