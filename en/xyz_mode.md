## x/y/z mode

### x-mode

#### Description
Single-user mode, the client retains the user's login session information after the user logs in. The next time the user connects to the server, the user's commands are automatically loaded without having to login again
If the client has no activity, the session is valid for 7 days
If the client version information shows `(x-mode)`, it means that the client is installed in x mode

```shell
$ easy -v
easy-client/x.x.x (x-mode)
```

#### Applicable scene
* Each administrator of the server has an account (the client will be installed in the `~ /` folder, which will only take effect for the currently logged in account)
* The server has only one administrator using easy.sh

#### Install
```shell
$ wget easy.sh/x && source x
```

### y-mode

#### Description
In multi-user mode, the client ** will not ** retain the user's login session information after the user logs in. After SSH is disconnected, all commands will be invalid. Each time you reconnect to the server, you will be required to log in again before performing related operations
If the client version information shows `(y-mode)`, it means that the client is installed in y mode

```shell
$ easy -v
easy-client/x.x.x (y-mode)
```

#### Applicable scene
* Multiple administrators share one account on the server, and multiple administrators use easy.sh
* Do not want your command information or client operation permissions to be indirectly exposed to other administrators on the server

#### Install
```shell
$ wget easy.sh/y && source y
```

### z-mode

#### Description
Get the command mode temporarily, ** will not install the client **, get all the commands of the user only once. After SSH is disconnected, all commands will be uninstalled

#### Applicable scene
* Don't want to install a client on the server, just want to use custom commands during this connection

#### Install
```shell
$ wget easy.sh/z && source z
```

---