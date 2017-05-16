用法
- `ln file link` - 创建硬链接，硬链接只能引用文件，不能引用目录
- `ln -s item link` - 创建符号链接， item 可以是文件和目录


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
me@mypc:~/test$ ln -s ./f slink2
me@mypc:~/test$ ls -il
total 0
412126 -rw-rw-r-- 2 me me 0 May 16 20:06 f
412126 -rw-rw-r-- 2 me me 0 May 16 20:06 hard-link
413064 lrwxrwxrwx 1 me me 1 May 16 20:06 slink -> f
413087 lrwxrwxrwx 1 me me 3 May 16 20:09 slink2 -> ./f
me@mypc:~/test$ rm slink2
me@mypc:~/test$ ls -il
total 0
412126 -rw-rw-r-- 2 me me 0 May 16 20:06 f
412126 -rw-rw-r-- 2 me me 0 May 16 20:06 hard-link
413064 lrwxrwxrwx 1 me me 1 May 16 20:06 slink -> f
me@mypc:~/test$ rm slink
me@mypc:~/test$ ls -il
total 0
412126 -rw-rw-r-- 2 me me 0 May 16 20:06 f
412126 -rw-rw-r-- 2 me me 0 May 16 20:06 hard-link
me@mypc:~/test$ 
```


创建符号链接时，即是创建一个文本文件，用于描述目标文件在哪里。例子中 slink 文件大小为 1 ，其中存储的就是链接目标：字符串 "f" ，而 slink2 文件大小为 3 ，其中存储的就是链接目标：字符串 "./f" 。


符号链接的权限固定是 lrwxrwxrwx


大部分文件操作都是操作的链接目标，而 rm 是个例外， rm 删除的只是符号链接，不是实际文件。


与[书中](/Linux Command Line/4.md)所述不同， `ls -l` 看到的链接数目不计算符号链接！
