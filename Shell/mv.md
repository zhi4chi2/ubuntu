用法
* 移动文件 f1 到文件 f2, 如果 f2 存在，则覆盖
* 移动文件 f 到目录 d, d 需要事先存在
* 移动目录 d1 到目录 d2, 如果 d2 不存在，则是重命名，如果 d2 存在，则将目录 d1 作为 d2 的子目录
* 移动多个文件和目录到目录 d, d 需要事先存在


选项：
* -i/--interactive - 如果目标已经存在，需要用户确认。默认会直接覆盖。
* -u/--update
* -v/--verbose

---
文件改名
```bash
me@mypc:~/test$ touch f1
me@mypc:~/test$ ls
f1
me@mypc:~/test$ mv f1 f2
me@mypc:~/test$ ls
f2
me@mypc:~/test$
```

---
移动文件 f1 到文件 f2, 如果 f2 存在，则覆盖
```bash
me@mypc:~/test$ touch f1 f2
me@mypc:~/test$ ls
f1  f2
me@mypc:~/test$ mv f1 f2
me@mypc:~/test$ ls
f2
me@mypc:~/test$ 
```

---
移动文件到目录
```bash
me@mypc:~/test$ mkdir 1
me@mypc:~/test$ touch f
me@mypc:~/test$ ls -F
1/ f
me@mypc:~/test$ mv f 1
me@mypc:~/test$ ls -FR
.:
1/

./1:
f
me@mypc:~/test$
```

---
目录改名
```bash
me@mypc:~/test$ mkdir 1
me@mypc:~/test$ ls -F
1/
me@mypc:~/test$ mv 1 2
me@mypc:~/test$ ls -F
2/
me@mypc:~/test$ cp 2 3
cp: omitting directory '2'
me@mypc:~/test$
```


注意，这时与 cp 不同， cp 要求目标目录必须已经存在，而 mv 是目录改名。

---
移动文件到目录，目录必须已经存在
```bash
me@mypc:~/test$ touch f1 f2
me@mypc:~/test$ mv f1 f2 1
mv: target '1' is not a directory
me@mypc:~/test$ mkdir 1
me@mypc:~/test$ mv f1 f2 1
me@mypc:~/test$ ls 1
f1 f2
me@mypc:~/test$
```

---
移动目录到目录，目标目录必须已经存在
```bash
me@mypc:~/test$ mkdir 1 2
me@mypc:~/test$ mv 1 2 3
mv: target '3' is not a directory
me@mypc:~/test$ mkdir 3
me@mypc:~/test$ mv 1 2 3
me@mypc:~/test$ ls -F 3
1/ 2/
me@mypc:~/test$
```

