有时候，系统中可能安装了某个程序的多个版本，这时可以用 which 显示可执行程序位置


```bash
me@mypc:~$ which ls
/bin/ls
me@mypc:~$ 
```


which 仅用于可执行程序，不适用于内置命令和 alias 命令。


例如对于内置命令 cd 不起作用
```bash
me@mypc:~/test$ type cd
cd is a shell builtin
me@mypc:~/test$ which cd
me@mypc:~/test$ 
```

# Reference

- [Linux Command Line](/Linux Command Line/5.md) - P39

