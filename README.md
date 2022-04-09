# learn-golang

Golang 学习记录文档

## 构建执行异常

* module *** is not in GOROOT
  1. 修改 Go 环境变量配置 `GO111MODULE="false"`
  1. 将工作路径配置到 GOPATH `go env -w GOPATH=${workspace dir}`
* warning: go env -w **=... does not override confilicting OS environment variable
  1. 重置对应的环境变量 `unset ${env param name}`
  1. 重新执行 `go env -w`
* 

