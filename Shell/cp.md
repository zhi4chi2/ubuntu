用法
* cp file1 file2 - 复制文件 file1 到文件 file2, 如果 file2 存在则会覆盖，否则创建 file2
* cp file dir - 复制文件 file 到目录 dir, dir 需要事先存在
* cp file1 file2 dir - 复制多个文件 file1 file2 到目录 dir, dir 需要事先存在
* cp -r dir1 dir2 - 复制目录 dir1 到目录 dir2, dir2 如果不存在则创建
* cp -r file1 dir1 dir2 - 复制多个文件或目录到目录 dir2, dir2 如果不存在则创建


如果 cp 源中有目录，则必须使用 -r ！否则出错(omitting directory)

---
复制文件 file1 到文件 file2, 如果 file2 存在则会覆盖，否则创建 file2
```bash
me@mypc:~/test$ touch f1
me@mypc:~/test$ ls
f1
me@mypc:~/test$ cp f1 f2
me@mypc:~/test$ ls -l
total 0
-rw-rw-r-- 1 me me 0 May 16 06:57 f1
-rw-rw-r-- 1 me me 0 May 16 06:57 f2
me@mypc:~/test$ date
Tue May 16 06:58:07 CST 2017
me@mypc:~/test$ cp f1 f2
me@mypc:~/test$ ls -l
total 0
-rw-rw-r-- 1 me me 0 May 16 06:57 f1
-rw-rw-r-- 1 me me 0 May 16 06:58 f2
me@mypc:~/test$ 
```

---
复制文件到目录，目录必须已经存在（如果不存在，认为是复制文件到文件）
```bash
me@mypc:~/test$ mkdir 1
me@mypc:~/test$ touch f
me@mypc:~/test$ cp f 1
me@mypc:~/test$ ls -l 1
total 0
-rw-rw-r-- 1 me me 0 May 15 20:44 f
me@mypc:~/test$ cp f 2
me@mypc:~/test$ ls -l
total 4
drwxrwxr-x 2 me me 4096 May 15 20:44 1
-rw-rw-r-- 1 me me    0 May 15 20:45 2
-rw-rw-r-- 1 me me    0 May 15 20:44 f
me@mypc:~/test$ 
```

---
使用通配符复制多个文件到目录，目录必须已经存在
```bash
me@mypc:~/test$ mkdir 1
me@mypc:~/test$ touch 1/f1 1/f2
me@mypc:~/test$ ls 1
f1  f2
me@mypc:~/test$ cp 1/* 2
cp: target '2' is not a directory
me@mypc:~/test$ mkdir 2
me@mypc:~/test$ cp 1/* 2
me@mypc:~/test$ ls 2
f1  f2
me@mypc:~/test$ 
```

---
复制目录到目录，必须使用 -r 选项，否则出错(omitting directory)
```bash
me@mypc:~/test$ mkdir 1 2
me@mypc:~/test$ ls -F
1/  2/
me@mypc:~/test$ cp 1 2
cp: omitting directory '1'
me@mypc:~/test$ ls -F 2
me@mypc:~/test$ cp -r 1 2
me@mypc:~/test$ ls -F 2
1/
me@mypc:~/test$ 
```

---
复制目录，递归(-r)复制子目录，此时目标目录不必事先存在
```bash
me@mypc:~/test$ mkdir 1
me@mypc:~/test$ ls
1
me@mypc:~/test$ touch 1/f
me@mypc:~/test$ ls 1
f
me@mypc:~/test$ cp -r 1 2
me@mypc:~/test$ ls
1  2
me@mypc:~/test$ ls 2
f
me@mypc:~/test$ 
```

---
复制多个文件或目录到目录 dir2, dir2 需要事先存在。必须使用 -r 选项，否则出错(omitting directory)
```bash
me@mypc:~/test$ mkdir 1
me@mypc:~/test$ touch f
me@mypc:~/test$ ls -F
1/  f
me@mypc:~/test$ cp 1 f 2
cp: target '2' is not a directory
me@mypc:~/test$ mkdir 2
me@mypc:~/test$ cp 1 f 2
cp: omitting directory '1'
me@mypc:~/test$ ls -F 2
f
me@mypc:~/test$ cp -r 1 f 2
me@mypc:~/test$ ls -F 2
1/  f
me@mypc:~/test$ 
```

---
选项：
* [-a](#a)/--archive - 复制时包括属性，包括所有权和权限（好像不是）。
* [-i](#i)/--interactive - 如果目标已经存在，需要用户确认，输入 y 覆盖，输入其它任何字符保留原文件。默认会直接覆盖。
* -r/--recursive - 递归复制。复制目录时使用。
* [-u](#u)/--update
* -v/--verbose
* -p - 保持文件原来的属性
* -R - 将源目录的子目录及子目录下的文件都复制到目标目录


# -a {#a}
```bash
me@mypc:~/test$ cp /etc/passwd pw
me@mypc:~/test$ ls -l
total 4
-rw-r--r-- 1 me me 2325 May 16 07:18 pw
me@mypc:~/test$ cp -a /etc/passwd pw
me@mypc:~/test$ ls -l
total 4
-rw-r--r-- 1 me me 2325 May 15 20:13 pw
me@mypc:~/test$ ls -l /etc/passwd
-rw-r--r-- 1 root root 2325 May 15 20:13 /etc/passwd
me@mypc:~/test$ 
```


加 -a 后复制结果的时间不更改。


# -u {#u}
```bash
me@mypc:~/test$ cp /etc/passwd pw
me@mypc:~/test$ ls -l
total 4
-rw-r--r-- 1 me me 2325 May 15 20:39 pw
me@mypc:~/test$ cp /etc/passwd pw
me@mypc:~/test$ ls -l
total 4
-rw-r--r-- 1 me me 2325 May 15 20:40 pw
me@mypc:~/test$ date
Mon May 15 20:41:31 CST 2017
me@mypc:~/test$ cp -u /etc/passwd pw
me@mypc:~/test$ ls -l
total 4
-rw-r--r-- 1 me me 2325 May 15 20:40 pw
me@mypc:~/test$ 
```


加 -u 在没有更新时不复制。


# -i {#i}
```bash
me@mypc:~/test$ cp -i /etc/passwd pw
cp: overwrite 'pw'? y
me@mypc:~/test$ 
```


# Reference
* [Linux 命令行大全/操作文件和目录](Linux Command Line/README.md) P26
* [Linux 初步/文件和目录](Linux Start/README.md)
