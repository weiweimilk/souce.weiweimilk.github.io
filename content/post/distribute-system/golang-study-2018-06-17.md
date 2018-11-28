---
title: "新语言的学习 - golang"
date: 2018-06-17T22:45:00+08:00
lastmod: 2018-06-17T22:45:00+08:00
draft: false
tags: ["golang", "skill"]
categories: ["monitor-system"]
author: "weiweimilk"
autoCollapseToc: true

---

# 背景
程序员生涯，会学多门计算机语言，从c/c++到java，再到最新的golang，平时还有使用python写写处理脚本等等，那么学习一门新语言正确的姿态是什么样的呢？本文是作者自己的思考历程。


# 踏出第一步
学习一门语言，首先要学习这门语言的官方文档，把官方的文档全部通读一遍，同时执行编写遇到的每一个例子，这个是很重要的，在这个过程中，你会逐渐熟悉这门语言的语法、惯用方法、周边的工具链等信息，达到入门的目的，比如在学习golang语言的过程中，你需要学习以下信息：

* 官方文档：https://golang.org/
	* 其中包括工具链，并发支持（goroutine）， 内存模式（https://golang.org/ref/mem），GC问题，问题定位和性能优化。

在学习上面的一些信息后，我们要思考一个问题：学习的这门语言和之前遇到的语言有什么不同，为什么会出现这门语言，他们各自适用的领域分别是什么？比如golang相对c/c++,java,python的优势和劣势是什么（比如golang缺少泛型）。

# 检验学习成果
学习一门语言最重要的是应用，语言是否熟悉了，应该写个代理或网络爬虫等练手项目。

# 更深入学习
最后，应该去阅读这门语言一些经典的开源项目，看别人是如何利用这门语言来解决一些问题的。
根据左耳朵耗子大神的说法，**Go 语言能吞食的一定是 PaaS 上的项目，比如一些消息缓存中间件、服务发现、服务代理、控制系统、Agent、日志收集等等，没有复杂的业务场景，也到不了特别底层（如操作系统）的中间平台层的软件项目或工具**，所以我们可以看下以下开源代码：


* 监控系统prometheus：https://github.com/prometheus
* tsdb：https://github.com/prometheus/tsdb
* 监控系统采集agent：https://github.com/cloudinsight/cloudinsight-agent
* 服务发现：
	* https://raft.github.io/
	* https://github.com/hashicorp/consul
* 服务代理（正向代理和反向代理）：https://medium.com/@mlowicki/http-s-proxy-in-golang-in-less-than-100-lines-of-code-6a51c2f2c38c
* gRPC: https://github.com/grpc/grpc-go
* web系统：https://beego.me/

-----
上面这些，作者自己也在不停的学习当中，希望对读者能有一定的启发。

