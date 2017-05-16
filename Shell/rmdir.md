rmdir 被删除的目录必须是空目录


# -p {#p}
rmdir -p 删除多级目录
```bash
me@mypc:~/test$ mkdir -p 1/2
me@mypc:~/test$ ls -R
.:
1

./1:
2

./1/2:
me@mypc:~/test$ rmdir -p 1/2
me@mypc:~/test$ ls
me@mypc:~/test$ 
```
