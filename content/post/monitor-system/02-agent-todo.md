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
日志采集
进程指标采集
自定义脚本采集
用户
采集数据的类型


## 常见开源方案
* flume

## 重点和难点





《Measure Anything，Measure Everything》
https://www.tuicool.com/articles/A3AFvu6
让一切人的决策基于数据。

应用数据收集采集标准：Statsd

从业务上考虑，采集数据需要覆盖的场景：



机器监控项采集
进程采集（各种类型进程，存活性监控）
日志采集（多维度数据采集能力）
业务监控（端口，语义，http 监控）？
另外，支持自定义脚本采集
自定义 http 监控

实现难点：
1、agent设计
如何设计一个稳定安全的agent？Unix的一个哲学，便是一个程序只做一件事，保持简单。当程序保持简单，足够的内聚，便可将复杂度降至最低，易于维护，最大可能地避免BUG。基于这个原则，我们对agent基于功能进行拆分，把agent拆分成一组高内聚，低耦合的进程，包括：
1）主控进程：提供上报通道，负责数据上报，升级管理。
2）采集进程：负责性能数据采集与原始告警检测。
3）调度进程：负责对agent插件的调度。

2、agent 的管理
