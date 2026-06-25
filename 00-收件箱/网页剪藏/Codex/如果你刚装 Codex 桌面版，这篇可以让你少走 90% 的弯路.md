---
title: "如果你刚装 Codex 桌面版，这篇可以让你少走 90% 的弯路"
source: "https://x.com/qi_wang6241/status/2068711501976764875"
author:
  - "[[@qi_wang6241]]"
published: 2026-06-21
created: 2026-06-23
description: "很多人把 Codex 桌面版当成聊天框用，所以只发挥了 20%真正的 Codex 桌面版，不只是“问 AI 写代码”。它是一个可以读项目、改文件、开终端、跑测试、看网页、做 Git、连插件、开自动化、甚至操作桌面应用的 AI 工作台这篇给刚入门的小白讲清楚：Codex 桌面版到底..."
tags:
  - "clippings"
---
![图像](https://pbs.twimg.com/media/HLWKGLJXAAA8eJv?format=jpg&name=large)

很多人把 Codex 桌面版当成聊天框用，所以只发挥了 20%

真正的 Codex 桌面版，不只是“问 AI 写代码”。它是一个可以读项目、改文件、开终端、跑测试、看网页、做 Git、连插件、开自动化、甚至操作桌面应用的 AI 工作台

这篇给刚入门的小白讲清楚：Codex 桌面版到底有哪些功能，以及每个功能该怎么用

## 1\. Codex 桌面版到底是什么？

你可以把它理解成一个AI 开发工作台

普通聊天工具只能回答你，Codex 可以进入你的项目目录，理解代码结构，修改文件，运行命令，查看报错，再根据结果继续修。

它适合做这些事：

- 读懂一个陌生项目
- 修 bug
- 加功能
- 写测试
- 重构代码
- 做代码审查
- 跑本地服务并检查页面
- 写文档、脚本、配置
- 处理表格、PDF、PPT、图片等非代码资产
- 定时做重复任务

## 2\. 第一次打开 Codex，该怎么开始？

新手建议按这个顺序：

1. 安装 Codex 桌面版

macOS 和 Windows 都支持。Windows 用户可以直接用原生 app，不一定非要 WSL。

1. 登录账号

可以用 ChatGPT 账号，也可以用 OpenAI API key。但有些功能在 API key 登录下可能不可用，所以普通用户优先用 ChatGPT 账号

1. 选择项目文件夹

Codex 的核心能力来自“进入项目”，你选中的文件夹，就是它能读取、修改和运行命令的工作区

1. 发第一条消息

不要一上来就说“帮我优化项目”，先让它理解项目：

先不要改代码。请阅读这个项目，告诉我： 1. 这个项目是做什么的 2. 主要目录结构 3. 启动命令、测试命令、构建命令分别是什么 4. 如果我要加一个新功能，应该从哪些文件开始看

这一步很重要！你是在让 Codex 建立地图

## 3\. Codex 桌面版界面怎么理解？

你会看到几个核心区域：

- 左侧项目和线程：一个项目可以有多个线程，每个线程是一段独立任务
- 中间对话区：你和 Codex 协作的地方
- 底部输入框：写需求、贴错误、调用命令、提反馈
- Review / Diff 面板：看 Codex 改了哪些文件
- Terminal 终端：跑测试、启动服务、执行 Git 命令
- Browser 浏览器：预览网页、标注页面问题
- Sidebar / Artifacts：看计划、来源、任务总结、生成的文件预览
- Settings 设置：调权限、模型、插件、浏览器、MCP、外观等

新手不用一次全学，先会“项目、线程、终端、Review、浏览器”这五个，就能完成大部分工作

## 4\. 三种运行模式：Local、Worktree、Cloud

开新线程时，你会看到不同模式：

Local

直接在当前项目目录里工作。适合小修改、快速修 bug、你想立刻看到文件变化的任务。

Worktree

Codex 会基于 Git worktree 创建一个隔离工作区。适合让它在后台做新功能、重构、试验方案，不打扰你当前代码。

Cloud

在配置好的云环境里远程运行。适合更长、更重、可以离开本机执行的任务。

小白建议：

- 小 bug 用 Local
- 新功能用 Worktree
- 长任务或并行任务再考虑 Cloud

## 5\. 提示词怎么写，效果最好？

给 Codex 四样东西：

目标：我要做什么 上下文：哪些文件、报错、页面、需求重要 约束：不要改哪里，保持什么风格，不能引入什么依赖 完成标准：什么结果算完成

比如：

目标：修复登录页在手机端按钮溢出的问题。 ​ 上下文： - 入口页面是 /login - 我已经在浏览器里看到按钮超出卡片 - 相关组件可能在 src/pages/Login.tsx 和 src/styles/auth.css ​ 约束： - 不要重构登录逻辑 - 不要引入新 UI 库 - 只改布局和样式 ​ 完成标准： - 移动端 375px 宽度不溢出 - 桌面端原布局不变 - 运行 lint 通过

这比“帮我修一下页面”强太多。

## 6\. 终端：让 Codex 自己验证结果

Codex 桌面版每个线程都有集成终端。你可以让它运行：

请运行测试并根据失败信息修复，直到测试通过。

或者：

启动本地开发服务，然后告诉我访问哪个 localhost 地址。

终端的关键价值是：Codex 不只是猜，它可以看真实报错。

常用命令包括：

```text
npm install
npm run dev
npm test
npm run lint
git status
git diff
```

如果一个任务需要反复运行命令，可以在 Local Environments 里配置 Actions，比如一键启动项目、一键跑测试。

## 7\. Review 面板：一定要学会看 diff

Codex 改完代码后，不要直接信。打开 Review 面板，看它改了什么。

Review 面板能做几件事：

- 查看所有未提交修改
- 只看最近一轮 Codex 修改
- 查看当前分支相对主分支的变化
- 暂存或撤回某些文件/代码块
- 对具体代码行留下 inline comment
- 让 Codex 根据你的评论继续修改

很好用的反馈方式：

我在 Review 面板留下了几条 inline comments。请只处理这些评论，不要扩大修改范围。

如果你要做代码审查，可以直接用：

```text
/review
```

它会把问题以内联评论的方式展示出来。

## 8\. Git 功能：从修改到 PR

Codex 桌面版内置 Git 工作流。

你可以在 app 里：

- 看 diff
- stage 文件
- revert 代码块
- commit
- push
- 创建 PR
- 处理 PR review comments

如果你接了一个 GitHub PR 反馈，可以这样说：

请读取当前 PR 的 review comments，按最小改动修复所有未解决问题。修完后运行测试，并总结每条反馈如何处理

前提是你的 GitHub / gh CLI / 插件权限配置好了。

## 9\. In-app Browser：前端开发神器

如果你在做网页，Codex 的内置浏览器非常关键

它可以打开：

- localhost 页面
- 本地 file 预览
- 不需要登录的公开页面

你可以在页面上直接标注问题：

我已经在浏览器里标注了几个页面问题，请修复这些视觉问题，并保持现有组件结构不变。

注意：内置浏览器不适合登录态页面。它不使用你的 Chrome cookies、扩展、已有标签页或登录状态。

如果要处理登录后的网页，用 Chrome Extension。

## 10\. Browser Use 和 Chrome Extension 怎么选？

简单记：

- 本地网页、localhost、无需登录：用 In-app Browser / [@Browser](https://x.com/@Browser)
- 要登录的网站、Gmail、Salesforce、LinkedIn、内部系统：用 Chrome Extension
- 浏览器也不够，需要操作桌面软件：用 Computer Use

例子：

[@Browser](https://x.com/@Browser) 打开 http://localhost:3000/pricing，检查移动端布局，修复所有溢出问题。

或者：

[@Chrome](https://x.com/@Chrome) 打开我的后台页面，根据这份说明更新设置。

Chrome Extension 会涉及网站权限。第一次访问某个站点时，Codex 会问你是否允许。敏感站点不要随手 Always allow。

## 11\. Computer Use：让 Codex 操作桌面应用

Computer Use 可以让 Codex 看见并操作 macOS / Windows 图形界面。

适合：

- 测试桌面 app
- 点设置页面
- 复现只有 GUI 才出现的问题
- 操作没有插件的数据源
- 跨多个 app 执行流程

Windows 上要注意：Computer Use 会在当前桌面前台操作，可能移动鼠标、输入文字。所以跑这类任务时最好别同时操作电脑。

提示词示例：

请使用 Computer Use 打开这个桌面应用，复现 onboarding 卡住的问题。每次修改后重新走一遍流程验证。

## 12\. Skills：把重复工作变成可复用能力

Skills 是 Codex 的“专业技能包”。

一个 skill 通常包含：

- 什么时候触发
- 该怎么做
- 参考资料
- 脚本
- 模板
- 资产文件

你可以显式调用：

[$skill-creator](https://x.com/search?q=%24skill-creator&src=cashtag_click) 帮我创建一个用于写产品发布推文的 skill

也可以让 Codex 自动匹配，比如你让它处理 PDF、PPT、表格、图片、GitHub PR，它会根据任务选择对应技能。

我建议新手把常用工作做成 skill：

- 写 X 长文
- 写产品介绍页
- 做代码审查
- 生成周报
- 处理 Excel
- 生成 PPT
- 复盘 PR
- 写 SEO 文章

这会让 Codex 越用越像你的私人工作流系统。

## 13\. Plugins、Apps、MCP：让 Codex 连接外部世界

插件是比 Skill 更大的扩展包。

一个 Plugin 可以包含：

- Skills
- App 连接器
- MCP server
- 工具配置
- 模板和资产

常见用途：

- 连接 GitHub
- 连接 Google Drive / Docs / Sheets / Slides
- 连接 Slack
- 连接 Gmail
- 使用 Browser
- 使用 Computer Use
- 创建和部署网站

MCP 可以理解为“让 Codex 接入外部工具和上下文的协议”。比如接第三方文档、内部工具、Figma、数据库、浏览器等。

新手不用先学 MCP 配置。先在 Plugins 页面装官方或团队已有插件。

## 14\. Automations：让 Codex 定时干活

Automations 是定时任务。

你可以让 Codex 每天、每周、每隔一段时间做事：

每天早上 9 点检查这个项目最近 24 小时的错误日志，如果有新问题，归类并提出修复建议。

或者：

每周五生成本周代码变更总结，包含新增功能、风险点、需要补测试的地方。

自动化结果会进入 Triage inbox。有发现就提醒你；没发现可以自动归档。

还有 Thread Automations，适合让同一个线程定期醒来，保留上下文继续检查。

## 15\. AGENTS.md：给 Codex 写长期工作规则

如果你每次都要重复说：

- 用 pnpm
- 不要引入新依赖
- 修改后跑测试
- PR 描述要包含风险
- 遵守某种代码风格

那就写进 AGENTS.md。

它相当于“给 Codex 的项目说明书”。

推荐内容：

\## Project Commands - Install: pnpm install - Dev: pnpm dev - Test: pnpm test - Lint: pnpm lint ​ ## Rules - Do not add production dependencies without asking. - Keep changes scoped. - After frontend changes, verify in browser. - Prefer existing components and utilities.

新手很容易忽略它，但这是让 Codex 稳定变强的核心。

## 16\. 权限和沙盒：不要一上来给满权限

Codex 会根据权限和沙盒设置决定它能做什么。

常见模式：

- read-only：只能读，不能改
- workspace-write：能在项目内读写和跑常规命令
- danger-full-access：几乎不限制，风险更高

建议：

- 学习和分析项目：read-only
- 正常开发：workspace-write
- 特殊维护任务：谨慎使用 full access

不要为了省一次确认，把所有权限都开满。你要的是高效，不是失控。

## 17\. 图片、文件和非代码资产

Codex 桌面版不只处理代码。

它可以处理：

- 图片输入
- 截图
- 图片生成和编辑
- PDF
- Word 文档
- Excel / CSV
- PPT
- 本地文件预览
- 生成 artifact

比如：

请根据这个 CSV 生成一个带图表的 Excel，并解释你做了哪些校验。

或者：

请根据这张截图还原一个 React 页面，并用浏览器验证移动端效果。

做内容、运营、设计、产品的人也能用，不只是程序员。

## 18\. 语音、弹窗、快捷命令

几个小功能也很实用：

- 语音输入：按住 Ctrl + M 说需求
- Pop-out window：把线程弹出，放在浏览器或编辑器旁边
- Command menu：Ctrl/Cmd + K
- Slash commands：输入 / 调命令
- $：调用 skills
- /plan：进入计划模式
- /review：代码审查
- /status：看线程状态
- /init：生成 AGENTS.md 脚手架
- /mcp：查看 MCP 状态
- /goal：设置持续目标

新手最该先学 /plan 和 /review。

## 19\. Appshots、远程连接、Memories

还有几个进阶功能：

Appshots

macOS 上可以把最前面的窗口截图和可用文本发给 Codex。适合“这个界面我说不清，你直接看”。

Remote connections

可以用手机或另一台设备连接 Codex 主机，继续线程、审批命令、看 diff、看结果。适合长任务和远程检查。

Memories

开启后，Codex 可以记住稳定偏好、常用技术栈、项目习惯和已知坑点。团队硬规则仍然应该写进 AGENTS.md，不要只靠记忆。

## 20\. 新手最稳的工作流

我建议你按这个流程训练自己：

1. 先让 Codex 读项目，不改代码
2. 让它给计划
3. 确认范围
4. 让它实现最小版本
5. 让它跑测试
6. 用 Review 看 diff
7. 用 Browser 看页面
8. 留 inline comments
9. 让它修第二轮
10. commit / push / PR

这才是 Codex 的正确打开方式：不是一次性许愿，而是多轮协作。

## 21\. 可以直接复制的提示词模板

了解项目：

先不要改代码。请阅读项目并总结架构、启动方式、测试方式、主要目录、关键依赖和潜在风险。

修 bug：

请根据这个报错定位根因，给出修复计划。确认后再改代码。修完后运行相关测试。

加功能：

我要添加 \[功能\]。请先找出相关文件，给出最小实现方案。不要引入新依赖，保持现有代码风格。

前端验证：

请启动开发服务器，用浏览器打开页面，检查桌面端和移动端。如果发现布局问题，修复并再次验证。

代码审查：

请 review 当前未提交修改，重点看 bug、回归风险、安全问题和缺失测试。先列问题，不要直接改。

自动化：

每周一上午检查这个项目上周的提交，总结主要变化、风险点、需要补测试的模块，并生成一份报告。

Codex 桌面版最强的地方，不是写代码很快

而是它把代码、终端、浏览器、Git、文档、插件、自动化放进了同一个协作空间。

新手真正要学的不是某个按钮，而是这套工作方式：

给清楚上下文、让它先计划、让它小步修改、让它自己验证、你再用 Review 和浏览器把关、重复几轮，直到交付。

一旦你这样用，Codex 就不再是AI 工具

它会变成你电脑里第一个真正能一起干活的开发搭档。