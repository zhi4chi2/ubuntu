有时候，系统中可能安装了某个程序的多个版本，这时可以用 which 显示可执行程序位置


```bash
me@mypc:~$ which ls
/bin/ls
me@mypc:~$ 
```


which 仅用于可执行程序，不适用于内置命令和 alias 命令。

```bash
type cd
which cd
```
