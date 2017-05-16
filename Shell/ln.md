示例
```bash
#创建硬链接，硬链接只能引用文件，不能引用目录
ln file link
#创建符号链接， item 可以是文件和目录
ln -s item link
```

例子
```bash
me@mypc:~/test$ touch f
me@mypc:~/test$ ln f hard-link
me@mypc:~/test$ ls -il
total 0
412126 -rw-rw-r-- 2 me me 0 May 16 20:06 f
412126 -rw-rw-r-- 2 me me 0 May 16 20:06 hard-link
me@mypc:~/test$ ln -s f slink
me@mypc:~/test$ ls -il
total 0
412126 -rw-rw-r-- 2 me me 0 May 16 20:06 f
412126 -rw-rw-r-- 2 me me 0 May 16 20:06 hard-link
413064 lrwxrwxrwx 1 me me 1 May 16 20:06 slink -> f
me@mypc:~/test$ 
```


创建符号链接时，即是创建一个文本文件，用于描述目标文件在哪里。


符号链接的权限固定是 lrwxrwxrwx


大部分文件操作都是操作的链接目标，而 rm 是个例外， rm 删除的只是符号链接，不是实际文件。