## Best practices

### Simplify complex commands
```shell
$ easy py-httpserver 'python -c "import SimpleHTTPServer;import SocketServer;SERVER_ADDRESS = \"$2\";PORT = int(\"$1\") if \"$1\" else 8000;print \"serving at\", SERVER_ADDRESS, \":\", PORT;Handler = SimpleHTTPServer.SimpleHTTPRequestHandler;httpd = SocketServer.TCPServer((SERVER_ADDRESS, PORT), Handler);httpd.serve_forever();"' 'start a http server. $1=port(default is 8000) $2=address'
$ py-httpserver 8001 0.0.0.0
```

### Take a command name that is easy to remember and maintain a uniform naming logic
```shell
$ easy dk 'docker'
$ easy dk-ps 'if [ -n "$1" ]; then dk ps -a | g $1; else dk ps -a; fi'
$ easy dk-logs 'dk logs --tail 200 -f'
$ easy dk-rm 'dk rm -f'
```
 
### Single responsibility to keep the logic of each command as simple as possible
```shell
$ easy c 'cat'
$ easy g 'grep --color=auto'
$ easy c-g 'c $1 | g $2'
```

### Passing a command script with a single quoted string
```shell
$ easy double-echo 'echo "$1" && echo "$2"'
```

---
