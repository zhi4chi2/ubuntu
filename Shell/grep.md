# 选项

- -i - 不区分大小写，默认是区分大小写的
- -v 输出和模式不匹配的行


```bash
me@mypc:~$ ls
Desktop    Downloads         GitBook  Pictures  Templates  Videos
Documents  examples.desktop  Music    Public    test
me@mypc:~$ ls | grep Te
Templates
me@mypc:~$ ls | grep -i te
Templates
test
me@mypc:~$ ls | grep -v te
Desktop
Documents
Downloads
examples.desktop
GitBook
Music
Pictures
Public
Videos
me@mypc:~$ 
```

# Reference

- [Linux Command Line](/Linux Command Line/6.md) - P54