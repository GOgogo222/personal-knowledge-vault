# Jim's Plaza 只看这个

你现在不用理解所有文档。只记住一句话：

> 以后让 AI 改 Jim's Plaza，改完只跑一条自动化命令。

## 你真正要用的命令

在 `E:\A-CodexProject` 里运行：

```powershell
python scripts\jim_plaza_auto.py
```

看到 `AUTO CHECK PASSED.` 就说明：

- 静态结构没坏。
- 本地预览能打开。
- 浏览器自动点完了 10 张卡。
- 星点变成了 `10 / 10`。
- 照片奖励能解锁并打开。

## 其他文件是干嘛的

- `jim-plaza-ai-friendly-spec.md`：给 AI 看的项目说明书。
- `jim-plaza-quality-gate.md`：更完整的检查标准。
- `jim-plaza-verification-log.md`：记录现在正确状态，坏了以后方便对照。
- `scripts/jim_plaza_static_check.py`：自动检查脚本。
- `scripts/jim_plaza_auto.py`：一键全自动检查入口。
- `scripts/jim_plaza_auto_check.mjs`：自动打开浏览器并跑完整流程。

## 最推荐你下一步做什么

先别接动画，先把 10 张卡片换成真实内容。

可以直接说：

```text
按 Jim's Plaza 下一步说明开工。
目标：把 10 张卡片从占位文案改成真实个人介绍和项目内容。
要求：保持三层流程、星点解锁、照片奖励不变，改完运行 python scripts\jim_plaza_auto.py。
```
