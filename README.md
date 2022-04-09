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
- comlex 类型
  - real
  - imag
- slice 类型
  - append
  - len
  - copy
  - cap
  - make
- map 类型
  - delete
  - make
  - cap
  - len
- chan 类型
  - make
  - close
  - len
- 内存操作
  - make
  - new
- goroutine
  - panic
  - recover
- print、println
  建议使用 fmt 包进行打印

## [`init()`、`main()`](https://www.topgoer.cn/docs/golang/chapter02-3)

两个函数在定义时不能有任何的参数和返回值，且Go程序自动调用。

### `init()` 包初始化函数

init 函数是用于程序执行前做包的初始化的函数，比如初始化包里的变量等。每个包可以拥有多个 init 函数，包的每个源文件也可以拥有多个 init 函数，同一个包中多个 init 函数的执行顺序 go 语言没有明确的定义(说明)，不同包的 init 函数按照包导入的依赖关系决定该初始化函数的执行顺序，**init函数不能被其他函数调用，而是在main函数执行之前，自动被调用**；

特点：
- 对同一个 go 文件的 `init()` 调用顺序是从上到下的。
- 对同一个 package 中不同文件是按文件名字符串比较“从小到大”顺序调用各文件中的 `init()` 函数。
- 对于不同的package:
  - 如果不相互依赖的话，按照 main 包中“先 import 的后调用”的顺序调用其包中的 `init()`。
  - 如果 package 存在依赖，则先调用最早被依赖的 package 中的 `init()`，最后调用 main 函数。

### `main()` 主函数

Go 语言的默认入口函数，只能用于 main 包中，且只能定义一个。

## 
















