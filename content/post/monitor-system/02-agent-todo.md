---
title: "监控系统系列：（二）数据采集"
date: 2018-06-02T17:51:02+08:00
lastmod: 2018-06-02T17:51:02+08:00
draft: true
tags: ["monitor"]
categories: ["monitor-system"]
author: "weiweimilk"
autoCollapseToc: true
---



## 背景

## 业务场景分析
从业务上考虑，采集数据需要覆盖的场景：

### 本机agent采集（推模式）
* 日志采集
* 进程采集
* 机器监控项采集
* 端口监控项采集
* 自定义http数据采集（/monitor）
* 自定义脚本采集(lua, python, shell)

### 外部agent采集（拉模式）
根据外部agent所属地域不同（比如不同机房、不同省份、不同运营商等维度），采集配置和采集出来的数据也是不一样的，需要详细设计

* 基于各种协议的监控（IPMI, http, https， tcp, ucp等）
* 端口监控项采集


## 采集的指标类型： 参考: https://prometheus.io/docs/concepts/metric_types/
* couter
* gauge
* histogram
* summary


## 采集配置


## 采集指标的方式：参考：http://blog.51cto.com/zlong37/1400819

* push
* pull


## 常见开源方案
* flume
* statsd


## 架构设计
### 重点和难点

https://codeascraft.com/2011/02/15/measure-anything-measure-everything/?utm_source=tuicool&utm_medium=referral

《Measure Anything，Measure Everything》
应该尽可能采集数据，并图形化展示，方便用户决策





实现难点：
1、agent设计
如何设计一个稳定安全的agent？Unix的一个哲学，便是一个程序只做一件事，保持简单。当程序保持简单，足够的内聚，便可将复杂度降至最低，易于维护，最大可能地避免BUG。基于这个原则，我们对agent基于功能进行拆分，把agent拆分成一组高内聚，低耦合的进程，包括：
1）主控进程：提供上报通道，负责数据上报，升级管理。
2）采集进程：负责性能数据采集与原始告警检测。
3）调度进程：负责对agent插件的调度。

2、agent的管理
包括agent的存活性统计、版本更新、采集配置下发



参考文档：

https://codeascraft.com/2011/02/15/measure-anything-measure-everything/?utm_source=tuicool&utm_medium=referral

https://codeascraft.com/2010/12/08/track-every-release/
这边文档的思路是将所有变化的量按照时间维度联系起来，可以辅助快速定位问题


