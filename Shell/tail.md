* -n - 后 n 行
* +n - 从 n 行之后的内容
* -f - 后 10 行，并且不退出，当文件更新时立即显示


```bash
me@mypc:~/test$ ls -l ~ > f
me@mypc:~/test$ tail -n 5 f
drwxr-xr-x 2 me me 4096 May 15 20:01 Pictures
drwxr-xr-x 2 me me 4096 May 15 20:01 Public
drwxr-xr-x 2 me me 4096 May 15 20:01 Templates
drwxrwxr-x 2 me me 4096 May 20 20:04 test
drwxr-xr-x 2 me me 4096 May 15 20:01 Videos
me@mypc:~/test$ 

tail -5 file
tail +5 file
tail -f file
```