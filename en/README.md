# easy.sh
Easily define shell commands/alias and use it on any server. 

## Simplify your shell script
The following command creates a command named `gitbook-server`, Execute the command and specify the gitbook project address, you can automatically obtain the code, configure the gitbook, and start the gitbook service:

```shell
$ easy gitbook-server 'echo "This is an example"\
 && echo "1.Get code" && git clone $1\
 && echo "2.Init gitbook" && gitbook init\
 && echo "3.Install plugins" && gitbook install\
 && echo "4.Startup" && gitbook serve'
$ gitbook-server https://git.easy.sh/xxx
...
```

## [中文说明](https://www.easy.sh/zh)

## Features
* Any operation is so easy
* Simplify your shell script like **alias**
* Supports parameterized commands
* Supports multiple shells: Bash、Zsh
* Use your commands on any server at any time

## Get started
### Install
#### via wget
```shell
$ wget easy.sh/x && source x
```

#### via curl
```shell
$ curl easy.sh/x > x && source x
```

### Create command
```shell
$ easy say-hi 'echo "Hello $1!"'
```

### Run command
```shell
$ say-hi World
Hello World!
```

---
