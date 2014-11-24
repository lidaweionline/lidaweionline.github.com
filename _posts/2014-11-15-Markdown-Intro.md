---
layout: post
title: Markdown语言
category: 技术
tags: markdown
keywords:
description:
---
#markdown简介
markdown是轻量级的标记语言。部分不完善的图片或者文本可以采用插入html标记解决。
#参考文章
[图灵社区markdown语法简介](www.ituring.com.cn/article/23)
[图灵社区markdown其他文章](www.ituring.com.cn/article/tagged/214)
[liquid documentation](http://www.shopify.com/sitemap)
#基本markdown语法
##文字格式
单个回车
视作空格

连续回车

视作分段

行尾连续两个空格,视作段内换行  
斜体：\*文字\*  

加粗：\*\*文字\*\*

##段落格式
引用：\>文字
示例：  
> 引用文字

标题：
一级标题：\#一级标题  
示例：
#一级标题

二级标题：\#\#二级标题 
 示例：
##二级标题

三级标题：\#\#\#三级标题 
示例：
###三级标题

或者使用=和\-来标注

大标题
=

示例：
大标题
=

小标题
-

示例：
小标题
-

##排序整理
分割线：\-\-\-
示例：

-------------

无序列表：

\*,\+，\- 后加上空格

\- 条目1

\- 条目2

\- 条目3

示例：
* 条目1
* 条目2
* 条目3

有序列表：

1. 条目1
2. 条目2
3. 条目3

嵌套列表:
\- 外层条目1
 \+ 内层条目1
 \+ 内层条目2
 \+ 内层条目3
\- 外层条目2

##插入代码
行开头加入4空格
程序:
{% highlight c++%}
    #include<iostream>
    int main()
    {
      return 0;
    }
{% endhighlight %}
##插入网址和图片
将文字显示为超链接，可以使用索引。
网址：\[网站名字\]\(网站url\)或者\[网站名字\]\[索引号\]
示例：[本站地址](lidaweionline.com)

图片：\!\[替代文本\]\(图片地址\)

图片大小不能设置。如果需要设置需要插入html标记img。

示例：\<img src="图片地址" alt="替代文字" width="宽度"\>

###试验区
双下划线：__双下划线__

罗马数字：
I.  
II.  
III. 
IV. 
V. 	
