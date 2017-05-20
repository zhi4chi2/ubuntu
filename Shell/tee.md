为了与管道的隐喻保持一致而提供的命令。就好像个 T 字形管道。

tee 读取标准输入，然后将内容复制到标准输出和一个或多个文件中。

常用于捕捉中间结果

```bash
me@mypc:~/test$ ls ~ | tee f | grep Do
Documents
Downloads
me@mypc:~/test$ cat f
Desktop
Documents
Downloads
examples.desktop
GitBook
Music
Pictures
Public
Templates
test
Videos
me@mypc:~/test$ 
```