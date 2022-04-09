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

init 函数是用于程序执行前做包的初始化的函数，比如初始化包里的变量等。每个包可以拥有多个 init 函数，包的每个源文件也可以拥有多个 init 函数，同一个包中多个 init 函数的执行顺序 go 语言没有明确的定义(说明)，不同包的 init 函数按照包导入的依赖关系决定该初始化函数的执行顺序，**init 函数不能被其他函数调用，而是在 main 函数执行之前，自动被调用**；

特点：
- 对同一个 go 文件的 `init()` 调用顺序是从上到下的。
- 对同一个 package 中不同文件是按文件名字符串比较“从小到大”顺序调用各文件中的 `init()` 函数。
- 对于不同的package:
  - 如果不相互依赖的话，按照 main 包中“先 import 的后调用”的顺序调用其包中的 `init()`。
  - 如果 package 存在依赖，则先调用最早被依赖的 package 中的 `init()`，最后调用 main 函数。

### `main()` 主函数

Go 语言的默认入口函数，只能用于 main 包中，且只能定义一个。

## 命令

`go <command> [arguments]`

### command
- bug，start a bug report
-	build，compile packages and dependencies（编译指定的源码文件或代码包以及它们的依赖包）
-	clean，remove object files and cached files（删除执行其它命令时产生的一些文件和目录）
-	doc，show documentation for package or symbol（打印附于 Go 语言程序实体上的文档）
-	env，print Go environment information（打印 Go 语言的环境信息）
-	fix，update packages to use new APIs（把指定代码包的所有 Go 语言源码文件中的旧版本代码修正为新版本的代码）
-	fmt，gofmt (reformat) package sources
-	generate，generate Go files by processing source
-	get，add dependencies to current module and install them（根据要求和实际情况从互联网上下载或更新指定的代码包及其依赖包，并对它们进行编译和安装）
-	install，compile and install packages and dependencies（编译并安装指定的代码包及它们的依赖包）
-	list，list packages or modules（列出指定的代码包的信息）
-	mod，module maintenance
-	run，compile and run Go program（编译并运行命令源码文件）
-	test，test packages（对Go语言编写的程序进行测试）
-	tool，run specified go tool（交互式的访问概要文件的内容）
-	version，print Go version
-	vet，report likely mistakes in packages（检查 Go 语言源码中静态错误的简单工具）

## 运算符

### 赋值运算符

=、+=、-=、*=、/=、%=、<<=、>>=、&=、|=、^=

### 算数运算符

+、-、*、/、%

### 关系运算符

==、!=、>、>=、<、<=、

### 逻辑运算符

&&、||

### 位运算符

&、|、^（异或）、<<（左移）、>>（右移）















