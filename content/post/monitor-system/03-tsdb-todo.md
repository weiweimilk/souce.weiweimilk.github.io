---
title: "监控系统系列：（三）时间序列存储"
date: 2018-06-02T17:51:02+08:00
lastmod: 2018-06-02T17:51:02+08:00
draft: true
tags: ["monitor"]
categories: ["monitor-system"]
author: "weiweimilk"
autoCollapseToc: true
---


## 背景
时间序列数据


http://www.infoq.com/cn/articles/database-timestamp-03



时间序列数据库

市面上有很多很多的基于时间序列的数据库，不论其底层的数据结构实现是什么样子，时间序列存储的本质数据结构永远都是：
 
Map< METRIC_KEY , sortedMap<timestamp, METRIC_VALUE >>
 
不同的底层实现都是在上面这个数据结构的一些点上有不同的扩展，比如：
 


tsdb选型的考虑点：
s1.在METRIC_KEY的分片逻辑，实现上不同：选取的分片是一致性哈希，还是求余哈希。
s2.SortedMap的实现不同，本质上是一个按Timestamp排序的序列（B＋Tree、SkipList都是很好的实现方式）。
s3.读写的偏好略有不同（这么高频的并发写入需求，一般实用lSM Tree来实现）。
s4.Metrics是否会无限增加？
s5.Metrics保留的时间跨度有多长？
s6.上层的业务报警，有多重要？

* wiki : Time series database
https://blog.outlyer.com/top10-open-source-time-series-databases

