可以同时创建多个目录
```bash
me@mypc:~/test$ mkdir 1 2
me@mypc:~/test$ ls -l
total 8
drwxrwxr-x 2 me me 4096 May 15 20:25 1
drwxrwxr-x 2 me me 4096 May 15 20:25 2
me@mypc:~/test$ rmdir 1 2
me@mypc:~/test$ ls
me@mypc:~/test$ 
```


# -p
mkdir -p 创建多级目录
```bash
me@mypc:~/test$ mkdir -p 1/2
me@mypc:~/test$ ls -R
.:
1

./1:
2

./1/2:
me@mypc:~/test$ 
```

# Reference

- [Linux Command Line](/Linux Command Line/4.md) - P26