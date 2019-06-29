---
title: "restful api design pattern"
date: 2018-06-02T17:51:02+08:00
lastmod: 2018-06-02T17:51:02+08:00
draft: true
tags: ["template"]
categories: ["writer"]
author: "weiweimilk"
autoCollapseToc: true
---

# 例子
* 请求

	* Method: `GET`
	* Header:
		* `content-type`: application/json
		* `X-TRACE-ID`: klsfl-skjflsd-fsdljkfsdl
		* `X-TRACE-TIMESTAMP`: 1452509878
		* `X-TRACE-SRC-IP`: 192.168.0.1
	* Path
* 1.2 参数含义
 
| Name | Type  | 取值范围| 是否必须 | 含义 | 例子 |
|:----:|:---:|:----:|:----:|:----:|:----:|
| name | String  | ? | 是 | 产品线 | name1 |

* 1.3 返回结果
	* http head
		json
	* json body
 
 
```json
{
	"status": 0, // 0表示无错误
	"msg": "xxxx",
	"data": {
		"content": [
		],
		"pagination": {
			"pageNumber": 1,
			"pageSize": 10,
			"pageElements": 1,
			"last": true,
			"first": true,
			"totalPages": 23,
			"totalElements": 221
		}
	}
}
```


# HTTP code

* 200 OK - [GET]：服务器成功返回用户请求的数据，该操作是幂等的（Idempotent）。
* 201 CREATED - [POST/PUT/PATCH]：用户新建或修改数据成功。
* 202 Accepted - [*]：表示一个请求已经进入后台排队（异步任务）
* 204 NO CONTENT - [DELETE]：用户删除数据成功。
* 400 INVALID REQUEST - [POST/PUT/PATCH]：用户发出的请求有错误，服务器没有进行新建或修改数据的操作，该操作是幂等的。
* 401 Unauthorized - [*]：表示用户没有权限（令牌、用户名、密码错误）。
* 403 Forbidden - [*] 表示用户得到授权（与401错误相对），但是访问是被禁止的。
* 404 NOT FOUND - [*]：用户发出的请求针对的是不存在的记录，服务器没有进行操作，该操作是幂等的。
* 406 Not Acceptable - [GET]：用户请求的格式不可得（比如用户请求JSON格式，但是只有XML格式）。
* 410 Gone -[GET]：用户请求的资源被永久删除，且不会再得到的。
* 422 Unprocesable entity - [POST/PUT/PATCH] 当创建一个对象时，发生一个验证错误。
* 500 INTERNAL SERVER ERROR - [*]：服务器发生错误，用户将无法判断发出的请求是否成功。


# 编写工具
swagger

# reference
* http://www.ruanyifeng.com/blog/2014/05/restful_api.html

* http://wiki.baidu.com/pages/viewpage.action?pageId=246290669

* go-swagger: https://goswagger.io/use/spec/allOf.html

