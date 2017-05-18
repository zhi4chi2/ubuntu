GNU 提供 info 页面取代 manual, info 页面可以用 info 阅读器显示。


默认 `info info` 显示很简略的信息，其中包括
```
SEE ALSO
       The full documentation for info is provided by the  texinfo-doc-nonfree
       package  as  a  Texinfo  manual.   If this package is installed at your
       site, the command

              info info

       should give you access to the complete manual.  (Or, if you have Emacs,
       M-x info will lead to the manual.)
```

Ubuntu 默认没有安装 texinfo-doc-nonfree ，需要自己安装
```bash
me@mypc:~$ sudo apt-get install texinfo-doc-nonfree
sudo: unable to resolve host mypc
[sudo] password for me:
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages were automatically installed and are no longer required:
linux-headers-4.4.0-21 linux-headers-4.4.0-21-generic linux-headers-4.4.0-31
linux-headers-4.4.0-31-generic linux-headers-4.4.0-34
linux-headers-4.4.0-34-generic linux-headers-4.4.0-36
linux-headers-4.4.0-36-generic linux-headers-4.4.0-43
linux-headers-4.4.0-43-generic linux-headers-4.4.0-62
linux-headers-4.4.0-62-generic linux-headers-4.4.0-64
linux-headers-4.4.0-64-generic linux-headers-4.4.0-66
linux-headers-4.4.0-66-generic linux-headers-4.4.0-71
linux-headers-4.4.0-71-generic linux-headers-4.4.0-72
linux-headers-4.4.0-72-generic linux-image-4.4.0-21-generic
linux-image-4.4.0-31-generic linux-image-4.4.0-34-generic
linux-image-4.4.0-36-generic linux-image-4.4.0-43-generic
linux-image-4.4.0-62-generic linux-image-4.4.0-64-generic
linux-image-4.4.0-66-generic linux-image-4.4.0-71-generic
linux-image-4.4.0-72-generic linux-image-extra-4.4.0-21-generic
linux-image-extra-4.4.0-31-generic linux-image-extra-4.4.0-34-generic
linux-image-extra-4.4.0-36-generic linux-image-extra-4.4.0-43-generic
linux-image-extra-4.4.0-62-generic linux-image-extra-4.4.0-64-generic
linux-image-extra-4.4.0-66-generic linux-image-extra-4.4.0-71-generic
linux-image-extra-4.4.0-72-generic ubuntu-core-launcher
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
texinfo-doc-nonfree
0 upgraded, 1 newly installed, 0 to remove and 51 not upgraded.
Need to get 630 kB of archives.
After this operation, 4,175 kB of additional disk space will be used.
Get:1 http://cn.archive.ubuntu.com/ubuntu xenial/main amd64 texinfo-doc-nonfree all 6.1.0-2 [630 kB]
Fetched 630 kB in 0s (916 kB/s)
Selecting previously unselected package texinfo-doc-nonfree.
(Reading database ... 532767 files and directories currently installed.)
Preparing to unpack .../texinfo-doc-nonfree_6.1.0-2_all.deb ...
Unpacking texinfo-doc-nonfree (6.1.0-2) ...
Processing triggers for install-info (6.1.0.dfsg.1-5) ...
Setting up texinfo-doc-nonfree (6.1.0-2) ...

```
然后再次执行 `info info` 就可以看到完整的文档了。按 H 看到完整的按键列表。例如
- p - 上一个 node
- n - 下一个 node
- u - 上一级
- SPACE - 下一页
- DEL - 上一页


```bash
me@mypc:~$ info coreutils
me@mypc:~$
```



大部分命令行程序都是 GNU coreutils 包的一部分，因此上面的命令可以看到 coreutils 提供的每个程序的文档。