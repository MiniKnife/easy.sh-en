### 基本操作
#### 安装

##### 极简版本`(Zsh中不支持)`
```shell
$ wget easy.sh/x && . x
```

##### 标准版本

###### 使用wget
```shell
$ wget easy.sh/x && source x
```

###### 使用curl
```shell
$ curl easy.sh/x > x && source x
```

#### 创建命令
```shell
$ easy say-hi 'echo "你好 $1!"'
```

#### 创建命令并添加帮助信息
```shell
$ easy say-hi 'echo "你好 $1!"' '向指定的对象用中文问好。用例: say-hi xxx'
```

#### 修改命令
```shell
$ easy say-hi 'echo "Hello $1!"'
```

#### 修改帮助信息
```shell
$ easy say-hi -h '向指定的对象用英文问好。用例: say-hi xxx'
```

#### 使用命令
```shell
$ say-hi World
Hello World!
```

#### 查看帮助信息
```shell
$ easy -h say-hi
向指定的对象用英文问好。用例: say-hi xxx
```

#### 删除命令
```shell
$ easy say-hi
```

#### 临时取消所有命令
```shell
$ easy --unset
```

#### 临时取消指定命令
```shell
$ easy --unset say-hi
```

#### 同步所有命令
```shell
$ easy
```

#### 同步并显示所有命令
```shell
$ easy -p
```

#### 同步并显示指定名称的命令
```shell
$ easy -p say-hi
say-hi: echo "Hello $1!"
```

#### 查看客户端使用帮助
```shell
$ easy -h
```

#### 查看客户端版本信息
```shell
$ easy -v
easy-client/x.x.x (x-mode)
```

#### 查看当前用户信息
```shell
$ easy -i
easy (L3)
```

#### 切换当前用户
```shell
$ easy --su
```

#### 卸载客户端(会同时取消所有命令)
```shell
$ easy --rm
```

---