---
title: "【translate】a-plain-english-introduction-to-cap-theorem"
date: 2017-08-31T15:43:48+08:00
lastmod: 2017-08-31T15:43:48+08:00
draft: false
tags: ["theory"]
categories: ["distribute system"]
author: "weiweimilk"

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
# comment: false
# toc: false
autoCollapseToc: true
# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
contentCopyright: '<a href="https://github.com/gohugoio/hugoBasicExample" rel="noopener" target="_blank">See origin</a>'
# reward: false
# mathjax: false
---

前言：
> 在理论计算机系统中，CAP理论是指对分布式数据存储，不可能同时满足以下三个提交：
> * consistency(一致性): 每次read，要么能获取到最新的数据，要么获取失败（错误或超时）
> * availability(可用性): 每次请求肯定会有正确的数据（但不保证数据是最新）
> * partition tolerance(分区容忍性): 尽管有部分消息在节点间丢失，但是系统还可以正常运行

正文
----------
当设计分布式系统时，你会经常听到CAP理论指定了某种设计上限。和我的其他入门级文章一样，本篇文章尝试通过真实案例理解CAP理论。

## Chapter 1: 记忆力公司，你的新事业 ##
昨晚当你的妻子感激你记住她的生日并且准备了礼物的时候，一个奇怪的点子戛然而出。通常人们不善于记忆，而你的记忆力却出奇的好。为什么不利用你的天分开启新事业呢？这个点子越想越靠谱。事实上，你已经想好解释新点子的广告语：
> 记忆力公司！ - 无需您记忆也永远不会忘记！
> 经常会忘记事情？没关系，一个电话就能搞定！
> 当你需要记忆事情时，直接拨打555-555-REMEM，告诉我们你需要记忆什么。比如你想记住老板的手机号，直接拨打给我们，当你需要用到时，直接拨打同样号码，我们会告知您老板的手机号码。
> 收费：每次1美分

所以每次电话交流通常是这样的：
* 客户：你好，能帮我存储下邻居的生日吗？
* 公司：好的，什么时候呢？
* 客户：2月2号
* 公司：（在这个用户的主页中写下来）已经存储，当你需要知道邻居的生日时，请随时指点我们。
* 客户：多谢！
* 公司：没问题，此次服务收费1美分。

## chapter 2: 公司扩张 ##
你的工作获取Y孵化器的融资，创业点子如此简单，成本很低（只需笔记本和电话），公司进展蒸蒸日上。每天都有好几百个电话。
你逐渐遇到了一些问题，发现越来越多的客户不得不等待与你通话，许多客户甚至等得不耐烦直接挂电话了。另外假如某天你生病了，那么这天公司就失去了一天的业务，甚至这天不能提供服务还会导致老用户不满意。
所以，你决定让你妻子加入到你的事业来。
你启动了一个建议计划：
* 你和你妻子都有一个分机
* 客户仍然只需要拨打555-555-RMEM
* 电话交换机会将客户的来电分发给空闲的分机

## chapter 3: 

http://ksat.me/a-plain-english-introduction-to-cap-theorem/
