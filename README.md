# learn-golang

Golang 学习记录文档

## 编译

### 编译异常问题

- module *** is not in GOROOT
  1. 修改 Go 环境变量配置 `GO111MODULE="false"`
  1. 将工作路径配置到 GOPATH `go env -w GOPATH=${workspace dir}`
- warning: go env -w **=... does not override confilicting OS environment variable
  1. 重置对应的环境变量 `unset ${env param name}`
  1. 重新执行 `go env -w`


## 基础

Golang 的主要特征：
- 

### 内置数据类型

值类型
- bool
- int
- unit
- float
- string
- complex
- array，固定长度数组

引用类型
- slice，序列数组
- map，映射
- chan，管道

### 内置函数

不需要显示导入就可以使用的函数


