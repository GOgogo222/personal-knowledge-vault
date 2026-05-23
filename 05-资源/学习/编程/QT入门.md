
# 12_20

## QT从入门到实战完整版|传智教育

[【保姆级图文教程】最新Windows系统QT下载、安装、入门、配置VS Qt环境，图文详细、内容充实-CSDN博客](https://blog.csdn.net/qq_62888264/article/details/132645054)

在VS Code中创建Qt项目

Qt教程：
https://www.bilibili.com/video/BV1g4411H78N?t=1072.5&p=4

# 1_4

**主要熟悉了一个Qt程序的创建过程**

**主要学习了main函数的主要内容，为它们写上了简明的注释**

********
- **`QWidget`** 是 Qt 所有界面元素的**基类（祖先）**。
    
- 你的 `MyPro01` 继承自 `QMainWindow`（而 `QMainWindow` 又继承自 `QWidget`）。
    
- **结论：** `QWidget` 才是父类，`MyPro01` 是子类。

# 1_5 

Qt模块的认识。。。(Qt Modules)

- core；gui；widgets
- network；multimedia；networkauth；multimediawidgets（主要用于app联网和媒体播放功能）

.pro文件介绍：
**.pro就是工程文件（project），它是qmake自动生成的用于生产makefile的配置文件**

一个 .pro 文件所包含的东西：
模块（Moudles），生成的 **.exe** 文件的名称，模板（Template），源文件，头文件

“相当于我自己写了一个类（MyPro01），继承了QWidget的窗口类”

**注意，类名和变量名要控制大小写**
### Qt Designer

https://www.bilibili.com/video/BV12B4y1h7QX?t=682.2

**Frame**的布局

**stytleSheet**的基础语法

多个 **Widgets** 的布局

**Ctrl+R**：预览效果

### QT快速入门 | 最简单最简洁的QT入门教程

https://www.bilibili.com/video/BV1N34y1H7x7?t=614.9&p=3

### 3  

用标签（lable），按钮（button），输入框（lineEdit）实现**一个简单的界面**

**右键标签（lable）**->改变格式文本，这里可以非常灵活地设计文本的内容

### 4

信号（点击某个按钮）与槽（做出响应，执行槽函数）

在**帮助**中搜索**QProgress**

[在VS中开发Qt](https://blog.csdn.net/jiratao/article/details/118927622)

输出调试信息：项目属性->连接器->选择控制台

# 12_21

### 4

[02.【Qt开发】Qt Creator介绍及新建项目流程](https://blog.csdn.net/qq_54652195/article/details/148239518)

*暂时把Qt放一放，我的Qt有点坏了。。。*


# 12_22

**关于构建和部署**

- **构建 (Build)：** 源代码 $\rightarrow$ 二进制可执行文件。
    
- **部署 (Deploy)：** 可执行文件 + 依赖库 + 资源 $\rightarrow$ 完整的运行环境。
    
- **运行 (Run)：** 启动那个已经准备好的环境。




