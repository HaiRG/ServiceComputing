# 安装go语言开发环境以及第一个包

## 安装golang

###  下载并安装

 首先需要下载安装包

 ![](https://github.com/HaiRG/ServiceComputing/blob/master/img/2.png)

 通过 wget获取

下载完毕后，进行解压

先创建一个文件夹

 ![](https://github.com/HaiRG/ServiceComputing/raw/master/img/3.png)

然后解压到该文件夹中

 ![](https://github.com/HaiRG/ServiceComputing/raw/master/img/5.png)

### 设置环境变量

创建工作空间并且通过vim打开profile文件

![](https://github.com/HaiRG/ServiceComputing/raw/master/img/7.png)

输入相应环境变量并执行配置

![](https://github.com/HaiRG/ServiceComputing/raw/master/img/6.png)

测试安装是否成功并检查配置

![](https://github.com/HaiRG/ServiceComputing/raw/master/img/8.png)

![](https://github.com/HaiRG/ServiceComputing/raw/master/img/9.png)

### 创建hello world！

我采用的是vim进行go的编写

![](https://github.com/HaiRG/ServiceComputing/raw/master/img/10.png)

输入相应语句

![](https://github.com/HaiRG/ServiceComputing/raw/master/img/11.png)

在终端运行

 ![](https://github.com/HaiRG/ServiceComputing/raw/master/img/12.png)

成功显示

### 安装一些插件

安装git

![](https://github.com/HaiRG/ServiceComputing/raw/master/img/13.png)

安装工具

![](https://github.com/HaiRG/ServiceComputing/raw/master/img/15.png)

### 安装gotour

![](https://github.com/HaiRG/ServiceComputing/raw/master/img/14.png)


## 按照官方文档写第一个包

### 创建hello.go文件

该步骤在上文中已经实现，故略过

### 编写第一个库

 首先创建reverse.go文件，填入相应的代码，
```go
// stringutil 包含有用于处理字符串的工具函数。
package stringutil

// Reverse 将其实参字符串以符文为单位左右反转。
func Reverse(s string) string {
	r := []rune(s)
	for i, j := 0, len(r)-1; i < len(r)/2; i, j = i+1, j-1 {
		r[i], r[j] = r[j], r[i]
	}
	return string(r)
}
```
 并且执行
 ```go
 go build
 ```

 ![](/img/16.5.png)

然后修改原来的hello.go文件如下：

```go
package main

import (
	"fmt"

	"github.com/user/stringutil"
)

func main() {
	fmt.Printf(stringutil.Reverse("!oG ,olleH"))
}
```

然后执行
```go
go install hello
hello
```

得到以下的结果

 ![](https://github.com/HaiRG/ServiceComputing/raw/master/img/16.52.png)

 ### 测试

  首先创建reverse_test.go文件

![](https://github.com/HaiRG/ServiceComputing/raw/master/img/16.png)

 然后输入相应的代码

 ![](https://github.com/HaiRG/ServiceComputing/raw/master/img/17.png)

  执行  ```go test```

  得到以下结果

  ![](/img/18.png)

  测试成功

  以上即为本次实验的全部内容

## 心得体会

 本次实验是对go语言的一次初步接触，包括了实验环境的安装以及第一个go语言程序的编写，由于网络环境，安装的过程中遇到了一些麻烦，不过通过实践顺利解决了。通过本次实验，我初步了解了go语言的一些知识，对于go语言的一些基本的语法，有了一定的认识，但仍需要进行进一步深入的了解与掌握。
