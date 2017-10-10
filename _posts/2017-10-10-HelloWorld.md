---
layout:     post                    # 使用的布局（不需要改）
title:      My First Post               # 标题 
subtitle:   Hello World             #副标题
date:       2017-10-10              # 时间
author:     BY                      # 作者
header-img: img/post-bg-2015.jpg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - 生活
---

#字符串
java字符串就是Unicode字符序列。java没有内置的字符串类型，而是提供了一个预定义的类String。
##字串
substring方法可以提取出字串。例如：<br>
String greeting = “Hello”；<br>
String s = greeting.substring(0,3);<br>
创建一个由字符“Hel”组成的字符串。参数一表示字符串的起始字符（从0开始计数），参数二表示不想被复制的第一个位置且不包括此位置。
##拼接
使用+号连接两个字符串。<br>
将一个字符串与一个非字符串的值进行拼接时，后者被转换成字符串。
##不可变字符串
String类没有提供用于修改字符串的方法。修改=提取子串+拼接上替换的字符串。<br>
这样做是否会降低运行效率？<br>
的确，通过拼接两个字符串来创建一个新字符串的效率确实不高，但是，不可变字符串有个优点：编译器可以让字符串共享。
##检测字符串是否相等
使用equals方法检测两个字符串是否相等。只有字符串常量是共享的，所以不要使用==判断测试字符串的相等性。（C++是我string类重载了==运算符以便检测字符串内容的相等性。）
##空串与Null串
空串“”是长度为0的字符串；不过，String变量还可以存放一个特殊的值，名为Null，这表示目前没有任何对象与该变量关联，即它不是对象。
<br>
检查一个字符串既不是null也不为空串：<br>
if(str != null && str.length() != 0) 
##代码点与代码单元
char数据类型是一个采用UTF-16编码表示Unicode代码点的代码单元。大多数的常用Unicode字符使用一个代码单元就可以表示，而辅助字符需要一对代码单元表示。<br>
length方法将返回采用UTF-16编码表示的给定字符串所需要的代码单元数量，想要的到实际的长度，即代码点数量（多少个char）可以调用：<br>
int cpCount = str.codePointCount(0,greeting.length());
##字符串API
Java中的String类包含了50多个方法。......
##构建字符串
StringBuilder解决每次连接字符串都会构建一个新的String对象带来的低效率问题。<br>
适用场景：需要用许多小段的字符串构建一个字符串。<br>
当每次需要添加一部分内容时，就调用append方法。在需要构建字符串时就调用toString方法，得到一个String对象。
