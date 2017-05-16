* ls - 当前目录
* ls /usr - 指定目录
* ls /usr /var - 指定多个目录


```bash
me@mypc:~$ ls
Desktop  Documents  Downloads  examples.desktop  Music  Pictures  Public  Templates  test  Videos
me@mypc:~$ ls /
bin   cdrom  etc   initrd.img      lib    lost+found  mnt  proc  run   snap  sys  usr  vmlinuz
boot  dev    home  initrd.img.old  lib64  media       opt  root  sbin  srv   tmp  var  vmlinuz.old
me@mypc:~$ ls ~ /
/:
bin   cdrom  etc   initrd.img      lib    lost+found  mnt  proc  run   snap  sys  usr  vmlinuz
boot  dev    home  initrd.img.old  lib64  media       opt  root  sbin  srv   tmp  var  vmlinuz.old

/home/me:
Desktop  Documents  Downloads  examples.desktop  Music  Pictures  Public  Templates  test  Videos
me@mypc:~$ 
```


---
ls 常用选项
* -a/--all - 列出所有文件
* -d/--directory - 列出目录的信息，而不是目录中的内容
* -F/--classify - 在每个条目后加上类型指示符，比如对目录加上 "/"
* -h/--human-readable - 可读性更好的格式
* [-l](#l) - 长格式
* -r/--reverse - 默认按照字母序排列条目，这个选项反转顺序
* -S - 按文件大小排序
* -t - 按文件修改时间排序
* -R - 包括子目录下的文件
* --color - 默认目录蓝色，可执行文件绿色，特殊文件黄色。默认颜色可通过 LS_COLORS 或者 LS_COLOURS 改变。
* -i - 显示 inode 信息


---
```bash
me@mypc:~$ ls
Desktop  Documents  Downloads  examples.desktop  Music  Pictures  Public  Templates  test  Videos
me@mypc:~$ ls -dl
drwxr-xr-x 19 me me 4096 May 15 20:23 .
me@mypc:~$ ls -F
Desktop/  Documents/  Downloads/  examples.desktop  Music/  Pictures/  Public/  Templates/  test/  Videos/
me@mypc:~$ ls -hl
total 48K
drwxr-xr-x 2 me me 4.0K May 15 20:01 Desktop
drwxr-xr-x 2 me me 4.0K May 15 20:01 Documents
drwxr-xr-x 2 me me 4.0K May 15 20:01 Downloads
-rw-r--r-- 1 me me 8.8K May 15 19:58 examples.desktop
drwxr-xr-x 2 me me 4.0K May 15 20:01 Music
drwxr-xr-x 2 me me 4.0K May 15 20:01 Pictures
drwxr-xr-x 2 me me 4.0K May 15 20:01 Public
drwxr-xr-x 2 me me 4.0K May 15 20:01 Templates
drwxrwxr-x 2 me me 4.0K May 15 20:28 test
drwxr-xr-x 2 me me 4.0K May 15 20:01 Videos
me@mypc:~$ ls -r
Videos  test  Templates  Public  Pictures  Music  examples.desktop  Downloads  Documents  Desktop
me@mypc:~$ ls -S
examples.desktop  Desktop  Documents  Downloads  Music  Pictures  Public  Templates  test  Videos
me@mypc:~$ ls -t
test  Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos  examples.desktop
me@mypc:~$ 
```

# -l {#l}
```bash
me@mypc:~$ ls -l
total 48
drwxr-xr-x 2 me me 4096 May 15 20:01 Desktop
drwxr-xr-x 2 me me 4096 May 15 20:01 Documents
drwxr-xr-x 2 me me 4096 May 15 20:01 Downloads
-rw-r--r-- 1 me me 8980 May 15 19:58 examples.desktop
drwxr-xr-x 2 me me 4096 May 15 20:01 Music
drwxr-xr-x 2 me me 4096 May 15 20:01 Pictures
drwxr-xr-x 2 me me 4096 May 15 20:01 Public
drwxr-xr-x 2 me me 4096 May 15 20:01 Templates
drwxrwxr-x 2 me me 4096 May 15 20:28 test
drwxr-xr-x 2 me me 4096 May 15 20:01 Videos
me@mypc:~$ 
```


其中
* -/d/l - 表示是普通文件/目录/符号链接文件
* rwx - 文件所有者的访问权限
* r-x - 文件所属组中成员的访问权限
* r-x - 其它所有人的访问权限
* 2 - 文件硬链接数量
* me - 文件所有者
* me - 文件所属组
* 4096 - 文件大小（字节）
* 5月  14 17:16 - 最后修改时间
* Desktop - 文件名
