# 12_23


**从这里开始**
https://www.bilibili.com/video/BV1d54y1g7db?t=161.9&p=3


**HTTP的知识**


**爬虫三步走：**
1. 发送请求
2. 选择数据类型
3. 选择存储方式


**具体到代码就是：**
~~~
import requsets  // 引入库文件
if requests.ok:  // 判断是否请求成功
	print(reponse.txt) // 打印网页HML源码
else 
	print("请求失败！")
~~~



**加入一个headers，让你的爬虫伪装成浏览器！**


**一个网页的三大基本要素：**
1. HTML - 骨架
2. CSS - 衣服
3. JavaScript - 动作


# 12_24

HTML常见的标签：
- 标题：hn(n=1,2...6)
- 文本段落：p
- 斜体，下划线：/i  /u
- 换行：br
- 图片：img
- 连接：a
- 容器：div/span
- 列表：ol
- 无序表（圆点符）：ul
- 表格：table

**大致的格式是：**<>... ... < />

# 12_29

**BeautifulSoup解析HTML内容。** 课程里面讲的主要是怎么通过一些库函数(findAll(),BeautifulSoup()等) 找到HTML中特定的内容。

# 1_5

practice01:
简单来说，三行代码就能完成爬取动作，然后再在“检查”里面随机抓取一个“User Agent”让爬虫伪装一下就能获取HTML数据了

practice02:
HTML只是源码，我们要使用BeautifulSoup的特定解析器对它进行解析，要明确你所要的数据在哪一个标签的哪一个具体元素（比如span标签的string）
换页的原理就是改变起始页“start”的值

