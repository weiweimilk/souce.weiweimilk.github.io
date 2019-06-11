---
title: "thinkings about code review"
date: 2019-06-11T17:51:02+08:00
lastmod: 2019-06-11T17:51:02+08:00
draft: false
tags: ["code-review"]
categories: ["code"]
author: "weiweimilk"
autoCollapseToc: true

---

# Preface
* 感想：自己工作近4年了，一直不注意code review，踩过很多坑，吃过很多亏
* 痛定思痛，觉得这是程序员的基本功，需要自己多修炼
* 自己code review自己的代码是可行的（分不同时间段）
* code review和写代码是一样重要，时间比例为1:1
* code review的目标：提高代码质量

# Aims
* 提高代码质量（code quality）
* 尽早发现bug（save money in the long run）
* 知识共享，学习和熟悉业务流程（share knowledge）
* 统一代码风格，提供可读性和可维护性
* 代码的可扩展性和性能
* 帮助新人成长（mentor）

# Steps
1. 系统全貌：模块划分的逻辑，模块间的关系
2. 模块级别：看清模块内的逻辑，关键数据，关键的类、函数
3. 类、函数内部的逻辑
4. 细节：layout, naming...

# Review Points
* 功能检查
    * 是否实现了预期的功能
    * 如果是较大的变更，需要提供详细设计文档，了解改动的背景和目标、主要设计思路等等
* 浅层次正确性检查
    * 代码里的格式、符号、命名等风格是否保持一致
    * 所有的注释是否正确
* 深层次正确性检查
    * 是否陷入死循环
* 健壮性检查
    * 是否避免运行时错误
* 可读性检查
    * 是否使用了不明确或不必要的复杂代码
    * 代码格式是否统一（缩进用4个空格）
    * 变量和函数的命名是否便于理解
    * 代码本身是否可读？好的代码不需要注释
    * 注释是否足够清晰
* 代码结构检查
    * 类和函数的耦合度和重复度检查
    * API设计是否合理？参数和返回值是否合理？
* 性能检查
    * 实现是否是性能最优？
    * 是否存在不必要的拷贝
    * 锁的粒度是否是最优的？
* 可扩展性检查
    * 类和函数的设计是否便于后期需求的实现

# Notices
* 在必要的时候，review的双方做面对面的沟通
* 对关键模块，建立owner制度
* 对review中发现的问题，一追到底
* 小步快跑：一次review的时候，不要提交太多代码量
* 为code review预留出足够多的时间

# Beyond the code
* review系统需求分析的质量
* review接口/函数定义的合理性
* review模块划分的合理性
* review系统关键机制的合理性
* you can challenge everything!

# References
* 左耳朵耗子谈code review
    * https://coolshell.cn/articles/11432.html
* Golang code style:
    * https://golang.org/doc/effective_go.html
* 推荐书籍
    * 《编写可读代码的艺术》
    * 《代码整洁之道》




