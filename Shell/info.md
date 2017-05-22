GNU 提供 info 页面取代 manual, info 页面可以用 info 阅读器显示。


默认 `info info` 显示很简略的信息，其中包括
```
SEE ALSO
The full documentation for info is provided by the texinfo-doc-nonfree
package as a Texinfo manual. If this package is installed at your
site, the command

info info

should give you access to the complete manual. (Or, if you have Emacs,
M-x info will lead to the manual.)
```

如果要查看 info reader 的使用方法，需要自己安装 texinfo-doc-nonfree

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
me@mypc:~$ info info
```

然后再次执行 `info info` 就可以看到 info reader 的使用文档了。

按 H 看到完整的按键列表。

按 h 得到的是安装 texinfo-doc-nonfree 之前的文档。


---
info 使用示例
```bash
me@mypc:~$ info coreutils
me@mypc:~$
```

大部分命令行程序都是 GNU coreutils 包的一部分，因此上面的命令可以看到 coreutils 提供的每个程序的文档。


# 术语

- dir - 默认 /usr/share/info/dir 文件，是最顶级的文件，使用 `info` 默认显示此文件
- file - info 文档，例如 coreutils.info.gz
- node - 每个 node 是文档中一个节点，用 Prev/Next/Up 将 node 串起来
- top node - 每个 info 文档都有一个 Top Node
- index entry - 例如 `info coreutils 'Concept index'` 可以看到 index 列表
- cross references/Xrefs - 即 info 文档中引用 node 的字符串。例如 "\* Foo Commands::", "\* Foo Label: Foo target." 包括 menu references 和 note references
- menu entry/menu item - 即作为行开头的 cross references


# 选项
- -n - 指定 node
- -a - 搜索所有匹配的文件
- -x=NUMBER - NUMBER 可以是 1/2/3 分别表示不同的日志级别， NUMBER 越高日志越细致。 -1 表示所有（最细）
- -w - 输出文件名字


指定 node 有两种方式
- -n - 例如 `info coreutils -n 'cp invocation'`
- 使用 info 交叉引用(cross reference)方式，即例如 `info '(coreutils)cp invocation'`


# 命令

node 间
- p - Prev node
- n - Next node
- u - Up node
- l - last history node, 上一个浏览的 node
- d - dir node
- < - file 中 first node
- \> - file 中 last node
- ] - 依次尝试 Next, first menu item, Up
- [ - 依次尝试 Prev, Up, last menu item

menu 间
- 1-9 - 选择 1-9 个菜单项
- 0 - 选择最后一个菜单项
- m+menu_name - 选择指定菜单项
- Alt-x find-menu - 光标移动到菜单开始处
- Tab - 移动到下一个 cross reference
- Shift-Tab - 移动到上一个 cross reference


index 搜索
* i - 在 index 中搜索，按 , 搜索下一个


移动光标
- 下一行 - ^n
- 上一行 - ^p
- 行首 - ^a
- 行尾 - ^e
- 下一字符 - ^f
- 上一字符 - ^b
- 下一字 - Alt-f
- 上一字 - Alt-b
- Node 开始 - b
- Node 结尾 - e
- 下一页 - SPACE
- 上一页 - DEL
- 下一页 - ^v, 与 SPACE 不同在于不会跳到下个 node
- 上一页 - Alt-v, 与 DEL 不同在于不会跳到上个 node


# Reference

- [Linux Command Line](/Linux Command Line/5.md) - P42
- `info info`