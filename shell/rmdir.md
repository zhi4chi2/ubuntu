rmdir 被删除的目录必须是空目录
```bash
me@mypc:~/test$ mkdir 1
me@mypc:~/test$ touch 1/f
me@mypc:~/test$ rmdir 1
rmdir: failed to remove '1': Directory not empty
me@mypc:~/test$ 
```



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
