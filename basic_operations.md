### Basic operations
#### Install

##### Minimal version`(Not supported in Zsh)`
```shell
$ wget easy.sh/x && . x
```

##### Standard version

###### via wget
```shell
$ wget easy.sh/x && source x
```

###### via curl
```shell
$ curl easy.sh/x > x && source x
```

#### Create command
```shell
$ easy say-hi 'echo "Hi! $1!"'
```

#### Create command & Set help text
```shell
$ easy say-hi 'echo "Hi! $1!"' 'Just say hi. usage: say-hi xxx'
```

#### Modify command
```shell
$ easy say-hi 'echo "Hello $1!"'
```

#### Update help text
```shell
$ easy say-hi -h 'Just say hello. usage: say-hi xxx'
```

#### Run command
```shell
$ say-hi World
Hello World!
```

#### Print help text
```shell
$ easy -h say-hi
Just say hello. usage: say-hi xxx
```

#### Delete command
```shell
$ easy say-hi
```

#### Unset commands
```shell
$ easy --unset
```

#### Unset the command with the specified name
```shell
$ easy --unset say-hi
```

#### Sync commands
```shell
$ easy
```

#### Sync commands & Print commands
```shell
$ easy -p
```

#### Sync commands & Print the command with the specified name
```shell
$ easy -p say-hi
say-hi: echo "Hello $1!"
```

#### Print client usage help text
```shell
$ easy -h
```

#### Print client version
```shell
$ easy -v
easy-client/x.x.x (x-mode)
```

#### Print current user
```shell
$ easy -i
easy (L3)
```

#### Change current user
```shell
$ easy --su
```

#### Remove client & Remove commands
```shell
$ easy --rm
```

---