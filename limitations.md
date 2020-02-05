## Limitations

### Client supported shell
* Bash
* Zsh

### Client-dependent software
**curl、echo、mktemp、cat、grep、sed、rm、mkdir**

### Command name restrictions
* The following names cannot be used：easy
* Name needs to meet the following requirements:
	* Only letters, numbers, and underscores can be used as the first character
	* Use only letters, numbers, and some symbols(**_+-*%=#@~^:**)
	* Cannot exceed 48 characters

### Cannot quote yourself directly or indirectly in a command
If you reference yourself in a command, the execution of the **command may not end** because of an endless loop.

As the following command:

```shell
$ easy grep 'grep --color=auto'

```

You can use the following command instead:
   
```shell
$ easy grep '/usr/bin/grep --color=auto'
```

### Custom commands cannot be used in the following scenarios
You cannot use `easy` and `the commands customized by easy` in the following commands: `nohup`, `xargs`, and other similar commands

### Restrictions on the use of different user levels
Under different user levels, there are certain restrictions on the number of commands and the length of a single command. See [User level description](vip.md)

### Limitations of command help information
* The maximum supported length is 8192 characters
* Does not support newline content, if there is newline content, it will automatically merge into one line

---