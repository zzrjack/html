# 一、一级题目

## 1.src与href的区别

href表示超文本引用，指向网络资源所在位置

src目的是要把文件下载到html页面中去       

**作用结果**

1.href 用于在当前文档和引用资源之间确立联系

2.src 用于替换当前内容

3.当浏览器遇到href会并行下载资源并且不会停止对当前文档的处理。(同时也是为什么建议使用 link 方式加载 CSS，而不是使用 @import 方式)

4.当浏览器解析到src ，会暂停其他资源的下载和处理，直到将该资源加载或执行完毕。(这也是script标签为什么放在底部而不是头部的原因)

<hr>

## 2.对HTML语义化的理解

1）为了在没有CSS的情况下，页面也能呈现出很好地内容结构、代码结构
2）用户体验：例如title、alt用于解释名词
3）有利于SEO：利于被搜索引擎收录，更便于搜索引擎的爬虫程序来识别
4）方便其他设备解析（如屏幕阅读器、盲人阅读器、移动设备）以意义的方式来渲染网页
5）便于项目的开发及维护，使HTML代码更具有可读性

<hr>

## 3.script标签中async与defer的区别

![img](HTML.assets/v2-7d7b47e90e160680b868a36bb2f08bb7_720w.jpg)

**async 表示异步**：

1）当浏览器遇到带有 async 属性的 script 时，请求该脚本的网络请求是异步的，**不会阻塞**浏览器解析 HTML，一旦网络请求回来之后，如果此时 HTML 还没有解析完，浏览器会**暂停解析**，**先**让 JS 引擎执行代码，**执行完毕后**再进行解析。

2）执行顺序不确定，完全依赖于网络传输结果，谁先到执行谁。

**defer 表示延迟**

1）当浏览器遇到带有 defer 属性的 script 时，获取该脚本的网络请求也是异步的，**不会阻塞**浏览器解析 HTML，一旦网络请求回来之后，如果此时 HTML 还没有解析完，**浏览器不会暂停解析并执行 JS 代码，而是等待 HTML 解析完毕再执行 JS 代码**

2)  浏览器（IE9及以下除外）会保证它们**按照在 HTML 中出现的顺序执行**，不会破坏 JS 脚本之间的依赖关系。

<hr>

## 4.HTML5有哪些更新

具体可参考https://juejin.cn/post/7116320560929325092

（1）新增语义化标签：nav、header、footer、aside、section、article

（2）音频、视频标签：audio、video

（3）input标签新增属性：placeholder、autocomplete、autofocus、required

（3）DOM查询操作：document.querySelector()

（5）数据存储：localStorage、sessionStorage

（6）history API：go、forward、back、pushstate、replacestate

（7）canvas（画布）、Geolocation（地理定位）、websocket（通信协议）

**移除元素**

（1）纯表现的元素：basefont，big，center，font, s，strike，tt，u;

（2）对可用性产生负面影响的元素：frame，frameset，noframes；

<hr>

## 5.行内元素有哪些？块级元素有哪些？行内块级元素有哪些？

行内元素有：heda meat title lable span br a style em b i strong
块级元素有：body form select textarea h1-h6 html table button hr p ol ul dl center div
行内块元素常见的有： img input td

区别：

1、块级元素会独占一行 默认的宽度占满父级元素，行内元素不会换行

2、**行内元素的width height 无效**

3、块级元素可以设置margin和padding属性，行内元素padding-left、padding-right，margin-left，margin-right（水平方向），有边距效果，padding-top，padding-bottom，margin-top，margin-bototm，（垂直方向）没有边距效果，

**本质（浏览器将块级元素的dispaly属性默认为block，行内元素属性默认为inline，因此行内元素与块级元素的切换可以通过修改display属性实现）**

<hr>

# 二、二级题目

## 1.DOCTYPE文档类型的作用

DOCTYPE是docunment type（文档定义）的简写，用来说明web设计中所用的html或xhtml的类型，指出浏览器或者其他阅读程序按照什么样的规则（W3C所发布的一个文档类型定义即DTD）集去解释文档中的标记.

## 2.常用meta标签有哪些

meta标签由name和content两个属性来定义，来描述一个HTML网页文档的属性，例如作者，日期和时间，网页描述，关键词，页面刷新等，除了一些http标准规定了一些name。
charset：用于描述html文档的编码形式

<!-- 页面标题<title>标签(head 头部必须) -->

<title>your title</title>
<!-- 页面关键词 keywords -->
<meta name="keywords" content="your keywords">
<!-- 页面描述内容 description -->
<meta name="description" content="your description">
<!-- 定义网页作者 author -->
<meta name="author" content="author,email address">
<!-- 定义网页搜索引擎索引方式，robotterms 是一组使用英文逗号「,」分割的值，通常有如下几种取值：none，noindex，nofollow，all，index和follow。 -->
<meta name="robots" content="index,follow">
1
————————————————
版权声明：本文为CSDN博主「伊恬123」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/weixin_53172312/article/details/110704581
## 3.说一下web worker

Web Worker的作用：为单线程的JS创造多线程环境。

Worker是由主线程创建的后台线程，主要用于解决计算密集型和高延迟的任务。然后把结果返回给主线程。主线程主要负责UI交互。这样主线程就会很流畅，不会被阻塞或拖慢。

## 4.head标签有什么用，其中什么必不可少

作用：<head> 标签用于定义文档的头部，**它是所有头部元素的容器**。

<head> 中的元素可以引用脚本、指示浏览器在哪里找到样式表、提供元信息等。

文档的头部描述了文档的各种属性和信息，包括**文档的标题、在 Web 中的位置以及和其他文档的关系等。绝大多数文档头部包含的数据都不会真正作为内容显示给读者**。

可包含的标签：下面这些标签可用在 head 部分：<base>, <link>, <meta>, <script>, <style>, <title>。 其中**只有title是必须的**

## 5.canvas和svg的区别

Canvas 主要是用笔刷来绘制 2D 图形的。
SVG 主要是用标签来绘制不规则矢量图的。
相同点：都是主要用来画 2D 图形的。
不同点：Canvas 画的是位图，SVG 画的是矢量图。
不同点：SVG 节点过多时渲染慢，Canvas 性能更好一点，但写起来更复杂。
不同点：SVG 支持分层和事件，Canvas 不支持，但是可以用库实现。

## 6.title和h1，b和strong ，i和em的区别

1. title与h1的区别

定义：

        title：概括了网站信息，可以告诉搜索引擎或者用户这个网站的内容主题是什么
    
        h1：文章主题内容，告诉蜘蛛我们的网站内容最主要是什么

区别：

        title：显示在网页标题上； h1：显示在网页内容上
    
        title比h1更重要（SEO的角度）

场景：

        网站的logo都是用h1标签包裹的

2. b与strong的区别

定义：

        b：实体标签，是用来给文字加粗的
    
        strong：逻辑标签，用来加强字符语气的（盲人阅读器中）

区别：

        b：只有加粗的样式，没有实际的含义
    
        strong：表示标签内字符比较重要，用以强调的

为了符合CSS3的规范，b尽量少用，改用strong

3. i与em的区别

定义：

        i：实体标签，用来做文字倾斜的
    
        em：逻辑标签，用来强调文字内容的

区别：

        i：只是一个倾斜标签，没有实际含义
    
        em：表示标签内字符重要，用以强调的

场景：

        i：更多用在字体图标
    
        em：术语上（医药、生物）
------------------------------------------------
