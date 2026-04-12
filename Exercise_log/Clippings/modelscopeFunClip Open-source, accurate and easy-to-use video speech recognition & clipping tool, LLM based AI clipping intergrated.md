---
title: "modelscope/FunClip: Open-source, accurate and easy-to-use video speech recognition & clipping tool, LLM based AI clipping intergrated."
source: "https://github.com/modelscope/FunClip"
author:
published:
created: 2026-04-12
description: "Open-source, accurate and easy-to-use video speech recognition & clipping tool, LLM based AI clipping intergrated. - modelscope/FunClip"
tags:
  - "clippings"
---
[![SVG Banners](https://camo.githubusercontent.com/b36c7c5e2f51c6301b1aba04d5b689f3d993b5bb44a854e3f92755086f1959e5/68747470733a2f2f7376672d62616e6e6572732e76657263656c2e6170702f6170693f747970653d7261696e626f772674657874313d46756e436c69702532302532302546302539462541352539322677696474683d383030266865696768743d323130)](https://github.com/Akshay090/svg-banners)

### 「简体中文 | English」

**⚡ Open-source, accurate and easy-to-use video clipping tool**

**

🧠 Explore LLM based video clipping with FunClip

**

[![](https://github.com/modelscope/FunClip/raw/main/docs/images/interface.jpg)](https://github.com/modelscope/FunClip/blob/main/docs/images/interface.jpg)

[![alibaba-damo-academy%2FFunClip | Trendshift](https://camo.githubusercontent.com/862cd30040105022e53a4f4b9ebaa1e590be647033122a48b2abe8beabe0232f/68747470733a2f2f7472656e6473686966742e696f2f6170692f62616467652f7265706f7369746f726965732f3130313236)](https://trendshift.io/repositories/10126)

**FunClip** is a fully open-source, locally deployed automated video clipping tool. It leverages Alibaba TONGYI speech lab's open-source [FunASR](https://github.com/alibaba-damo-academy/FunASR) Paraformer series models to perform speech recognition on videos. Then, users can freely choose text segments or speakers from the recognition results and click the clip button to obtain the video clip corresponding to the selected segments (Quick Experience [Modelscope⭐](https://modelscope.cn/studios/iic/funasr_app_clipvideo/summary) [HuggingFace🤗](https://huggingface.co/spaces/R1ckShi/FunClip)).

## Highlights🎨

- 🔥Try AI clipping using LLM in FunClip now.
- FunClip integrates Alibaba's open-source industrial-grade model [Paraformer-Large](https://modelscope.cn/models/iic/speech_paraformer-large_asr_nat-zh-cn-16k-common-vocab8404-pytorch/summary), which is one of the best-performing open-source Chinese ASR models available, with over 13 million downloads on Modelscope. It can also accurately predict timestamps in an integrated manner.
- FunClip incorporates the hotword customization feature of [SeACo-Paraformer](https://modelscope.cn/models/iic/speech_seaco_paraformer_large_asr_nat-zh-cn-16k-common-vocab8404-pytorch/summary), allowing users to specify certain entity words, names, etc., as hotwords during the ASR process to enhance recognition results.
- FunClip integrates the [CAM++](https://modelscope.cn/models/iic/speech_campplus_sv_zh-cn_16k-common/summary) speaker recognition model, enabling users to use the auto-recognized speaker ID as the target for trimming, to clip segments from a specific speaker.
- The functionalities are realized through Gradio interaction, offering simple installation and ease of use. It can also be deployed on a server and accessed via a browser.
- FunClip supports multi-segment free clipping and automatically returns full video SRT subtitles and target segment SRT subtitles, offering a simple and convenient user experience.

## What's New🚀

- 2024/06/12 FunClip supports recognize and clip English audio files now. Run `python funclip/launch.py -l en` to try.
- 🔥2024/05/13 FunClip v2.0.0 now supports smart clipping with large language models, integrating models from the qwen series, GPT series, etc., providing default prompts. You can also explore and share tips for setting prompts, the usage is as follows:
	1. After the recognition, select the name of the large model and configure your own apikey;
		2. Click on the 'LLM Inference' button, and FunClip will automatically combine two prompts with the video's srt subtitles;
		3. Click on the 'AI Clip' button, and based on the output results of the large language model from the previous step, FunClip will extract the timestamps for clipping;
		4. You can try changing the prompt to leverage the capabilities of the large language models to get the results you want;
- 2024/05/09 FunClip updated to v1.1.0, including the following updates and fixes:
	- Support configuration of output file directory, saving ASR intermediate results and video clipping intermediate files;
		- UI upgrade (see guide picture below), video and audio cropping function are on the same page now, button position adjustment;
		- Fixed a bug introduced due to FunASR interface upgrade, which has caused some serious clipping errors;
		- Support configuring different start and end time offsets for each paragraph;
		- Code update, etc;
- 2024/03/06 Fix bugs in using FunClip with command line.
- 2024/02/28 [FunASR](https://github.com/alibaba-damo-academy/FunASR) is updated to 1.0 version, use FunASR1.0 and SeACo-Paraformer to conduct ASR with hotword customization.
- 2023/10/17 Fix bugs in multiple periods chosen, used to return video with wrong length.
- 2023/10/10 FunClipper now supports recognizing with speaker diarization ability, choose 'yes' button in 'Recognize Speakers' and you will get recognition results with speaker id for each sentence. And then you can clip out the periods of one or some speakers (e.g. 'spk0' or 'spk0#spk3') using FunClipper.

## On Going🌵

- FunClip will support Whisper model for English users, coming soon (ASR using Whisper with timestamp requires massive GPU memory, we support timestamp prediction for vanilla Paraformer in FunASR to achieving this).
- FunClip will further explore the abilities of large langage model based AI clipping, welcome to discuss about prompt setting and clipping, etc.
- Reverse periods choosing while clipping.
- Removing silence periods.

## Install🔨

### Python env install

FunClip basic functions rely on a python environment only.

```
# clone funclip repo
git clone https://github.com/alibaba-damo-academy/FunClip.git
cd FunClip
# install Python requirments
pip install -r ./requirements.txt
```

### imagemagick install (Optional)

If you want to clip video file with embedded subtitles

1. ffmpeg and imagemagick is required
- On Ubuntu
```
apt-get -y update && apt-get -y install ffmpeg imagemagick
sed -i 's/none/read,write/g' /etc/ImageMagick-6/policy.xml
```
- On MacOS
```
brew install imagemagick
sed -i 's/none/read,write/g' /usr/local/Cellar/imagemagick/7.1.1-8_1/etc/ImageMagick-7/policy.xml
```
- On Windows

Download and install imagemagick [https://imagemagick.org/script/download.php#windows](https://imagemagick.org/script/download.php#windows)

Find your python install path and change the `IMAGEMAGICK_BINARY` to your imagemagick install path in file `site-packages\moviepy\config_defaults.py`

1. Download font file to funclip/font
```
wget https://isv-data.oss-cn-hangzhou.aliyuncs.com/ics/MaaS/ClipVideo/STHeitiMedium.ttc -O font/STHeitiMedium.ttc
```

## Use FunClip

### A. Use FunClip as local Gradio Service

You can establish your own FunClip service which is same as [Modelscope Space](https://modelscope.cn/studios/iic/funasr_app_clipvideo/summary) as follow:

```
python funclip/launch.py
# '-l en' for English audio recognize
# '-p xxx' for setting port number
# '-s True' for establishing service for public accessing
```

then visit `localhost:7860` you will get a Gradio service like below and you can use FunClip following the steps:

- Step1: Upload your video file (or try the example videos below)
- Step2: Copy the text segments you need to 'Text to Clip'
- Step3: Adjust subtitle settings (if needed)
- Step4: Click 'Clip' or 'Clip and Generate Subtitles'

[![](https://github.com/modelscope/FunClip/raw/main/docs/images/guide.jpg)](https://github.com/modelscope/FunClip/blob/main/docs/images/guide.jpg)

Follow the guide below to explore LLM based clipping:

[![](https://github.com/modelscope/FunClip/raw/main/docs/images/LLM_guide.png)](https://github.com/modelscope/FunClip/blob/main/docs/images/LLM_guide.png)

### B. Experience FunClip in Modelscope

[FunClip@Modelscope Space⭐](https://modelscope.cn/studios/iic/funasr_app_clipvideo/summary)

[FunClip@HuggingFace Space🤗](https://huggingface.co/spaces/R1ckShi/FunClip)

### C. Use FunClip in command line

FunClip supports you to recognize and clip with commands:

```
# step1: Recognize
python funclip/videoclipper.py --stage 1 \
                       --file examples/2022云栖大会_片段.mp4 \
                       --output_dir ./output
# now you can find recognition results and entire SRT file in ./output/
# step2: Clip
python funclip/videoclipper.py --stage 2 \
                       --file examples/2022云栖大会_片段.mp4 \
                       --output_dir ./output \
                       --dest_text '我们把它跟乡村振兴去结合起来，利用我们的设计的能力' \
                       --start_ost 0 \
                       --end_ost 100 \
                       --output_file './output/res.mp4'
```

## Community Communication🍟

FunClip is firstly open-sourced bu FunASR team, any useful PR is welcomed.

You can also scan the following DingTalk group or WeChat group QR code to join the community group for communication.

| DingTalk group | WeChat group |
| --- | --- |
| [![](https://github.com/modelscope/FunClip/raw/main/docs/images/dingding.png)](https://github.com/modelscope/FunClip/blob/main/docs/images/dingding.png) | [![](https://github.com/modelscope/FunClip/raw/main/docs/images/wechat.png)](https://github.com/modelscope/FunClip/blob/main/docs/images/wechat.png) |

## Find Speech Models in FunASR

[FunASR](https://github.com/alibaba-damo-academy/FunASR) hopes to build a bridge between academic research and industrial applications on speech recognition. By supporting the training & finetuning of the industrial-grade speech recognition model released on ModelScope, researchers and developers can conduct research and production of speech recognition models more conveniently, and promote the development of speech recognition ecology. ASR for Fun！

📚FunASR Paper:

📚SeACo-Paraformer Paper:

🌟Support FunASR: