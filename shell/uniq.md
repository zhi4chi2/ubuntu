uniq 默认删除列表中重复的行，使用 -d 选项则只显示重复的行。

```bash
me@mypc:~/test$ touch f
me@mypc:~/test$ echo hello > f
me@mypc:~/test$ echo hello >> f
me@mypc:~/test$ echo world >> f
me@mypc:~/test$ cat f | uniq
hello
world
me@mypc:~/test$ cat f | uniq -d
hello
me@mypc:~/test$ cat f
hello
hello
world
me@mypc:~/test$ 
```

# Reference

- [Linux Command Line](/Linux Command Line/6.md) - P54