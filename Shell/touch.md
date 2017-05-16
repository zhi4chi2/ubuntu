如果文件不存在则创建，如果存在则更新最后访问时间和最后修改时间


```bash
me@mypc:~/test$ touch f
me@mypc:~/test$ ls -l
total 0
-rw-rw-r-- 1 me me 0 May 15 20:23 f
me@mypc:~/test$ touch f
me@mypc:~/test$ ls -l
total 0
-rw-rw-r-- 1 me me 0 May 15 20:24 f
me@mypc:~/test$ 
```
