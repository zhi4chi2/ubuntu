du -ah --max-depth=1 查看文件夹下的文件和子文件夹大小。

```bash
me@mypc:~/test$ mkdir d
me@mypc:~/test$ cp /usr/bin/zip d
me@mypc:~/test$ cp /usr/bin/xterm .
me@mypc:~/test$ ls -Rl
.:
total 536
drwxrwxr-x 2 me me   4096 Jun 10 08:47 d
-rwxr-xr-x 1 me me 543232 Jun 10 08:50 xterm

./d:
total 192
-rwxr-xr-x 1 me me 192520 Jun 10 08:47 zip
me@mypc:~/test$ du -ah --max-depth=1
196K	./d
532K	./xterm
732K	.
me@mypc:~/test$ 
```

# Reference
- http://www.cnblogs.com/kobe8/p/3825461.html
- http://www.cnblogs.com/iconfig/p/4863063.html
