## 最佳实践

### 简化复杂命令
```shell
$ easy py-httpserver 'python -c "import SimpleHTTPServer;import SocketServer;SERVER_ADDRESS = \"$2\";PORT = int(\"$1\") if \"$1\" else 8000;print \"serving at\", SERVER_ADDRESS, \":\", PORT;Handler = SimpleHTTPServer.SimpleHTTPRequestHandler;httpd = SocketServer.TCPServer((SERVER_ADDRESS, PORT), Handler);httpd.serve_forever();"' 'start a http server. $1=port(default is 8000) $2=address'
$ py-httpserver 8001 0.0.0.0
```

### 取一个便于记忆的命令名称，保持统一的命名逻辑
```shell
$ easy dk 'docker'
$ easy dk-ps 'if [ -n "$1" ]; then dk ps -a | g $1; else dk ps -a; fi'
$ easy dk-logs 'dk logs --tail 200 -f'
$ easy dk-rm 'dk rm -f'
```
 
### 单一职责，让每个命令的逻辑尽量简单
```shell
$ easy c 'cat'
$ easy g 'grep --color=auto'
$ easy c-g 'c $1 | g $2'
```

### 使用单引号字符串传递命令脚本
```shell
$ easy double-echo 'echo "$1" && echo "$2"'
```

---
