# easy.sh
轻松自定义shell命令/别名，并在任意服务器上使用。

## 简化你的shell脚本
以下命令创建了一个名为`gitbook-server`的命令，执行该命令并指定gitbook项目地址，即可自动获取代码、配置gitbook并启动gitbook服务:

```shell
$ easy gitbook-server 'echo "这是一个例子"\
 && echo "1.获取代码" && git clone $1\
 && echo "2.初始化gitbook" && gitbook init\
 && echo "3.安装gitbook插件" && gitbook install\
 && echo "4.启动服务" && gitbook serve'
$ gitbook-server https://git.easy.sh/xxx
...
```

## 主要特性
* 极简操作
* 像**alias**一样简化复杂脚本
* 支持参数化命令，让命令更强大
* 支持多种常见的shell：Bash、Zsh
* 随时在任意服务器上同步并使用你的命令


## 开始使用
### 安装
#### 使用wget
```shell
$ wget easy.sh/x && source x
```

#### 使用curl
```shell
$ curl easy.sh/x > x && source x
```

### 创建命令
```shell
$ easy say-hi 'echo "Hello $1!"'
```

### 使用命令
```shell
$ say-hi World
Hello World!
```

---
