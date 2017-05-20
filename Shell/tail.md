* -n NUM - 后 NUM 行
* -n +NUM - 从 NUM 行之后的内容
* -f - 后 10 行，并且不退出，当文件更新时立即显示


```bash
me@mypc:~/test$ ls -l ~ > f
me@mypc:~/test$ tail -n 5 f
drwxr-xr-x 2 me me 4096 May 15 20:01 Pictures
drwxr-xr-x 2 me me 4096 May 15 20:01 Public
drwxr-xr-x 2 me me 4096 May 15 20:01 Templates
drwxrwxr-x 2 me me 4096 May 20 20:04 test
drwxr-xr-x 2 me me 4096 May 15 20:01 Videos
me@mypc:~/test$ tail -n +5 f
-rw-r--r-- 1 me me 8980 May 15 19:58 examples.desktop
drwxrwxr-x 3 me me 4096 May 16 19:56 GitBook
drwxr-xr-x 2 me me 4096 May 15 20:01 Music
drwxr-xr-x 2 me me 4096 May 15 20:01 Pictures
drwxr-xr-x 2 me me 4096 May 15 20:01 Public
drwxr-xr-x 2 me me 4096 May 15 20:01 Templates
drwxrwxr-x 2 me me 4096 May 20 20:04 test
drwxr-xr-x 2 me me 4096 May 15 20:01 Videos
me@mypc:~/test$ cat f
total 52
drwxr-xr-x 2 me me 4096 May 16 21:13 Desktop
drwxr-xr-x 2 me me 4096 May 15 20:01 Documents
drwxr-xr-x 2 me me 4096 May 15 20:01 Downloads
-rw-r--r-- 1 me me 8980 May 15 19:58 examples.desktop
drwxrwxr-x 3 me me 4096 May 16 19:56 GitBook
drwxr-xr-x 2 me me 4096 May 15 20:01 Music
drwxr-xr-x 2 me me 4096 May 15 20:01 Pictures
drwxr-xr-x 2 me me 4096 May 15 20:01 Public
drwxr-xr-x 2 me me 4096 May 15 20:01 Templates
drwxrwxr-x 2 me me 4096 May 20 20:04 test
drwxr-xr-x 2 me me 4096 May 15 20:01 Videos
me@mypc:~/test$ 
```