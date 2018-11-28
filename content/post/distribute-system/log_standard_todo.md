---
title: "日志规范"
date: 2018-06-02T17:51:02+08:00
lastmod: 2018-06-02T17:51:02+08:00
draft: true
tags: ["overview"]
categories: ["monitor-system"]
author: "weiweimilk"
autoCollapseToc: true

---

# 日志的作用
定位问题：
trace调用问题：OpenTracing

# 日志级别
服务分析
INFO
CRITICAL
FATAL

# 日志规范
日志中，应该包括以下内容
uuid
current_timestamp
time_cost



对于api等请求类接口，一定要贯穿一个全局的uuid


https://zhuanlan.zhihu.com/p/27363484


glog.Info
glog.Warning
glog.Error
glog.Fatal


对于info级别的日志，还可以区分不同的等级，
V 2: 很全面的info日志，仅仅用于某些实例的定位问题使用，不可全量放开
V 1: 稍微多的info日志，可以在线上全量放开。
V 0: 最基本的info日志，需要在县上常态放开


一个思路：如何快速根据日志定位线上问题
# go-ff
* data
* judge
* incident
* configure
* namespace


http://wiki.baidu.com/pages/viewpage.action?pageId=462796263