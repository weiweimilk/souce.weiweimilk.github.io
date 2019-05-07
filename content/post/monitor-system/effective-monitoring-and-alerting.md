# 总体介绍
在
认为对了解监控和告警是十分有用的
建议报警新人必读科目
重点介绍前5章


# Chapter1: introduction
* proactive: 人工盯屏
* reactive：自动化监测并发送通告

## 定义

monitoring & alerting（规定本书覆盖的范围）

* Monitoring: 包括data collection, data processing, presentation
* Alerting: 监测并通知状态变化

## 功能

1. early problem detection
	* availability
	* performance
2. decision making
	* baseling(SLA, capacity planning, 问题复盘分析)
	* prediction(isp流量，商业趋势）
3. automation
	* admission control(自动降级)
	* 自治计算(自动)
	

## Challenge

* baselining
	* 基线变化太快
* coverage
	* 系统扩容和架构调整，如何保证加全了
* manageability
	* 系统管理方法和丰富的指导文档
* accuracy
	* 
* context
	* 报警了，如何定位问题
	* 业务相关，专家经验（故障定位）
* human nature
	* 忽略核心告警

-----
后面的作为第二次讲解



# Chapter2: Monitoring
讲解指标采集，指标类型、指标含义解释，从趋势图看指标异常pattern，以及异常的解释

## 组成部分

* data collection(with agent)
	* white box
		* log parser
		* log scanner
		* interface reader
	* black box
		* probers(http call)
		* sniffers(tcpdump)

* agentless data collection(snmp)

## coverage(监控项的覆盖范围)
见图2-1

## metrics
* summary statistics
* frequency distribution and percentiles
* metric aggragation

## understanding metrics
??

## timeseries patterns
猜测下是哪种指标类型

## drawing conclusions from timeseries plots
??

## frequently encountered anomalies
* flatterning effect
* warm-up effect
* regular anomlies
* spikes during throughs

## determining causality(如何故障定位)
里面讲解了一个例子来说明如何定位问题（根据什么现象，如何分析等等）


# chapter3: Alerting
trade-off: 时效性 和 准确性

## prerequisites
* monitoring and alerting platform
* audit trail(审查跟踪，可以接入事件流图)
* issue tracking（故障处理跟踪, oncall平台）

## identifying casues
* resource unavailability or saturation
* software problems
* misconfigurations
* hardware defects

## anatomy of an alarm
* metric monitor
* time evaluation
* another alarm as input source（and or count）

Figure 3-2

## suppression
报警依赖是放在异常判断判断

## configuring monitors
* comming up with a threshold
	* static thresholds(utilization limit, sli)
	* data-driven threshold(根据近期的历史数据，计算出阈值，参数化)
* breach and clear delay(TODO: 见例子)
* testing alerting configurations(smoke test)

## alerting suggestions
(TODO:见例子)


# chapter4: At Scale（大规模系统的监控）


# chapter5: Automation(自动化)








		