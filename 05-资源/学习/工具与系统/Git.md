
[如何将 GitHub 私有仓库（private）转换为公共仓库（public）_github private改为public-CSDN博客](https://blog.csdn.net/qq_41791705/article/details/144076312)

[用 Git 在 Android 和 Windows 间同步 Obsidian 数据库 - 少数派](https://sspai.com/post/68989)
---》手机端连接GitHub
---》搁置

# 1_5

**上午**

5号到9号任务清单：
- 学会到从github上push，commit代码
- 重温git的基本命令
- 复习数据结构第一章和第三章实验内容

本次大作业打算在虚拟机Ubuntu 22.03上完成

[Git 基本操作 | 菜鸟教程](https://www.runoob.com/git/git-basic-operations.html)

**目前会的基本操作**
- git status
- git add .
- git commit -m "<描述你做了什么>"
- git push origin main

"Ctrl+Insert" 有时也会失灵！

[(8 封私信 / 80 条消息) 手把手教你用git上传项目到GitHub（图文并茂，这一篇就够了），相信你一定能成功！！ - 知乎](https://zhuanlan.zhihu.com/p/193140870)
---》为账户配置SSH公匙

学会更改文件后缀名，然后打开原来打不开的文件

### 代码push需要账户名和密码

~~虚拟机（/学校网络）可能会拦截ssh默认的22端口~~

总结一下吧：
反复在尝试如何去关联（remote）一个仓库，目前看来https和ssh两种方式比较流行，但最后仍然没有成功，虚拟机的环境确实不太好用，复制粘贴“时好时坏”，全英文的开发环境，还有那奇奇怪怪的输入法，当然也不是全然没有收获，但是有以下几点需要注意：
- 总是在一个错误上反复纠缠，重复地试错，导致效率很低
- 各种各样开发给我一种错觉，顺的时候一顺百顺，但有时又非常容易糊涂，搞不清楚问题所在，把希望寄托给“玄学”，我们总是要理性分析，大胆尝试，大胆质疑，然后还要小心求索
能玩Linux的都是大神~~~

**下午**

[Diditzh的开源空间](https://digitzh.github.io/posts/GitHub%E6%97%A0%E6%B3%95%E8%BF%9E%E6%8E%A5%E7%9A%84%E5%AE%8C%E5%85%A8%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88/)
---》非常有效，检测到我的名称设置有问题

完成了一个简单的fork和pull request全流程

# 1_6

**上午**

```
git remote add origin git@github.com:wangjiax9/practice.git
//关联远程仓库

git push -u origin master
//推送

git remote rm origin
//删除关联的仓库
//常用于ssh关联，避免反复输入账号名和密码
```

 我们在**clone**的时候可能就会产生一个https的关联，但为了避免反复输入账号名和密码，我们需要删除原先的关联，然后新建一个ssh密匙关联

### Git的branch

[Git - 分支简介](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E7%AE%80%E4%BB%8B)

[(8 封私信 / 80 条消息) 图解git，用手绘图带你理解git中分支的原理和应用 - 知乎](https://zhuanlan.zhihu.com/p/268687184)

**下午**

**常用分支命令**
~~~
git branch dev
//创建分支
git branch -d dev
//删除分支
git checkout dev
//切换到dev分支
git merge dev
//合并分支（当前在master分支）
~~~

**快捷命令**
~~~
git checkout -b dev
//创建分支，并切换到该分支上
~~~

