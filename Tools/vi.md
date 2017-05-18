大部分 Linux 发行版配备的是 vim(Vi Improved)。通常 vi 硬链接（或别名）到 vim

```bash
me@mypc:~$ vi
me@mypc:~$
```
可以看到版本，当前是 VIM version 7.4.1689


```bash
me@mypc:~$ which vi
/usr/bin/vi
me@mypc:~$ ls -l /usr/bin/vi
lrwxrwxrwx 1 root root 20 Jun 21 2016 /usr/bin/vi -> /etc/alternatives/vi
me@mypc:~$ ls -l /etc/alternatives/vi
lrwxrwxrwx 1 root root 17 Jun 21 2016 /etc/alternatives/vi -> /usr/bin/vim.tiny
me@mypc:~$ ls -l /usr/bin/vim.tiny
-rwxr-xr-x 1 root root 1064592 Nov 25 04:51 /usr/bin/vim.tiny
me@mypc:~$
```
所以在 Ubuntu 中是 vi 通过符号链接链接到 vim.tiny 的。


# 启动和退出 vi

- :q - 退出
- :q! - 强制退出

如果不能确定 vi 所处的状态，按 Esc 两次返回初始状态。


# 编辑模式

每行开始的 ~ 表示该行没有内容。

- Normal mode - 按 Esc 进入，特殊情况下需要按两次 Esc 。这种模式下，每个按键都是命令。
- Command-line mode - 在 Normal mode 按 : 进入
- 插入模式(Insert mode) - 按 i/I 进入插入模式，如果 ":set showmode" 则 vi 底部会出现 -- INSERT --
- 替换模式 - 按 R 进入
- 可视模式(Visual mode) - 按 v 进入可视模式，可以四处移动光标使选取区域变大或变小。接着您可以使用一个操作符对选中文本进行操作。例如，按 d 键会删除选中的文本内容。

- 增强模式
- 兼容模式 - vim 用近似 vi 的常规模式运行，使用 ":set nocp" 退出兼容模式

进入增强模式
- 运行 vim 而不是 vi
- 执行 `echo "set nocp" >> ~/.vimrc


# 保存工作

在命令模式下按 : 也叫输入 ex 命令

- :w - 保存

保存后会在 vi 底部出现

有些 Linux 发行版只安装 vim 的最小版本，需要安装完全版 vim


# 移动光标

* h
* j
* k
* l
* 0 - 行开头
* ^ - 本行第一个非空字符
* $ - 行尾
* w - 下一个单词或标点。从当前光标当前位置直到下一个单词起始处，不包括它的第一个字符。 w 一般在单词开始处按下，从一个单词头跳到下一个单词头。
* e - 从当前光标当前位置直到单词末尾，包括最后一个字符。 e 一般在单词最后一个字符处按下，从一个单词尾跳到下一个单词尾。
* W - 下一个单词
* b - 上一个单词或标点
* B - 上一个单词
* Ctrl+F - 下一页
* Ctrl+B - 上一页
* n+G - 第 n 行，例如 1G 到第一行
* G - 最后一行
* gg - 第一行
* Ctrl+g - 显示当前编辑文件中当前光标所在行位置以及文件状态信息。


其它命令（比如 j ）也可以前面加数字，就像 g 一样。

% 可以查找配对的括号 ), ], }, (, [, {


# 基本编辑

* u - 撤销， vi 只能撤销上一次操作， vim 可以向上撤销多次操作
* U - 撤销整行的修改。再按 U 又撤销上一个 U ，即恢复原状。
* Ctrl+r - 重做。只能重做 u ，不能重做 U 。 U 由 U 自己重做。


## 添加文本

- a - 在光标后添加
- i - 在光标前添加
- A - 在行尾添加


## 插入一行

- o - 在当前行下方插入一行
- O - 在当前行上方插入一行


## 删除文本

- x - 删除光标处字符，前面可以加数字表示删除几个字符，例如 3x
- d - 可以加光标移动命令作为后缀，例如 dl 删除右边字符
- dd - 删除当前行， 5dd 表示删除 5 行
- dw - 当前词，一般当光标在一个单词开头处使用
- de - 下一个词，一般当光标在一个单词前的空格处使用
- d$ - 从当前字符到行尾
- d0 - 从当前字符到行首
- d^ - 从当前字符到行第一个非空字符
- dG - 当前行到文件尾， d20G 从当前行到文件第 20 行


## 替换文本

- r - r+新字符。注意 r 只能替换一个字符。
- R - 进入替换模式。输入字符替换光标处字符。
- cw - 先删除单词，然后进入插入模式等待输入。
- c$ - 先删除到行尾，然后进入插入模式等待输入。

c 与 d 操作一样，可以加各种 motion ，表示的意思也是删除。 c 相当于先 d 再进入插入模式。


## 剪切、复制和粘贴

d 命令其实是剪切。

- p - 粘贴到光标之后。如果最后一次删除的是一个整行，那么该行将置于当前光标所在行的下一行。
- P - 粘贴到光标之前
- y - 复制
- yy - 复制当前行， 5yy 表示复制 5 行
- yw - 当前词
- y$ - 从当前字符到行尾
- y0 - 从当前字符到行首
- y^ - 从当前字符到行第一个非空字符
- yG - 当前行到文件尾， y20G 从当前行到文件第 20 行


## 合并行

- J - 合并行


# 查找和替换

- f - 行内搜索字符，只能搜索单个字符。例如 fa 搜索下一个 a 字符。首次搜索后按 ; 查找下一个
- / - 搜索整个文件。首次搜索后按 n 查找下一个， N 查找上一个
- ? - 向上搜索整个文件。首次搜索后按 n 查找下一个， N 查找上一个

Ctrl+o 回到之前的位置，重复按可以回退更多步。 Ctrl+i 会跳转到较新的位置。

提示：如果查找已经到达文件末尾，查找会自动从文件头部继续查找，除非 'wrapscan' 选项被复位。

要忽略大小写 ":set ic" ，要大小写敏感 ":set noic" 。要仅此搜索忽略大小写 "/search_string\c"

要高亮搜索到的内容 ":set hls" ，要不高亮 ":set nohls" ，要在已经高亮显示时移除高亮 ":nohlsearch"

要查找短语时显示部分匹配，设置 incsearch 使用 ":set is" 。

:set 的 hls, ic, is 也可以使用全名 hlsearch, ignorecase, incsearch


## 全局搜索和替换

例如
```bash
:s/thee/the
:%s/Line/line/g
```

其中
- % - 确定搜索范围。 % 表示整个文档。默认只是当前行。还可以指定为 1,$ 或者 1,n 表示从第一行到第 n 行
- s - 指定操作（替换）
- /Line/line - 搜索和替换的文本
- g - 全部替换。默认每一行只替换搜索到的第一个

其它
- c - 表示每次替换都要确认

回答
- y
- n
- a - 执行所有替换
- q - 停止替换
- l - last, 执行替换并结束替换
- Ctrl+E, Ctrl+Y - 向下向上滚动查看替换处的上下文


# 编辑多个文件

```bash
vi file1 file2 file3
```

## 切换文件

- :n - 切换到下一个可编辑文件
- :N - 切换到上一个可编辑文件
- :buffers - 查看正在编辑的文件列表
- :buffer + n - 切换到另一个文件，例如 `:buffer 2`


:n/:N 切换到可编辑文件。另有 Ctrl+w Ctrl+w 即按两次 Ctrl+w 切换文件。


## 载入更多文件

- :e + 文件名 - 载入新文件

使用 :ez 载入的文件不响应 :n/:N 只能用 :buffer 切换。


## 文件之间的内容复制


## 插入整个文件

- :r + 文件名 - 将文件内容插入到光标位置之前

还可以读取外部命令的输出，例如 ":r !ls" 可以读取 ls 的输出。


# 保存工作

- :w
- :w + 文件名 - 另存为。但是保存之后编辑的仍然是原文件！而不是另存为之后的文件！
- ZZ - 保存并退出 vi
- v - 先按 v 然后移动光标，然后按 : 底部会出现 :'<,'> 再输入 w + 文件名，会将选定部分保存。


# 执行外部命令

- :! - 执行 shell 命令。例如 :!ls 执行 ls 命令。在 Windows 下可以用 :!dir ，默认目录在 G:\Temp


# 帮助

用 :help 得到帮助。还可以加参数，例如 ":help w", ":help c_Ctrl+D", ":help insert-index", ":help user-manual"

在帮助文档中用 Ctrl+] 跳转 tag(超链接)，用 Ctrl+o(跳到 old position)/Ctrl+T(pop tag) 跳回。

查看所有命令的索引使用 :help index

如果要查看的命令中有 Ctrl ，应该用 "CTRL-" ，例如 ":help CTRL-A" 表示查看 Ctrl+A 命令的帮助。

:help 默认显示 normal mode 帮助，如果要显示其它模式，需要使用 mode prefix 例如 "i_" 表示 insert mode 。例如 ":help i_CTRL-H" 表示 insert mode 下的 Ctrl+H

启动 vim 时指定的参数，例如 "vim -t" 的 -t 参数，的帮助查看方式 ":help -t"

vim 的配置参数(option)的帮助查看方式 ":help 'number'" 即用单引号括起来。

特殊键用尖括号括起来，例如 ":help i_&amp;lt;Up>" 表示查看 insert mode 下的上箭头的帮助。

查看出错代码的帮助，例如 ":help E37"

# ~/.vimrc

在 Windows 下叫 _vimrc 在 VIM 安装目录下。

Windows 下 vim 中定义了变量
- $VIMRUNTIME = VIM exe 所在目录(D:\Vim\vim80)
- $VIM = VIM 安装目录(D:\Vim)


编辑 vimrc
- 在 Linux 下使用 ":edit ~/.vimrc"
- 在 Windows 下使用 ":edit $VIM/_vimrc"

然后 ":r $VIMRUNTIME/vimrc_example.vim" 读取范例到 vimrc ，在此基础上编辑，最后 ":write" 保存。

更多信息参见 :help vimrc-intro


# 命令行补全

在非兼容模式下，可以用 Ctrl+d 和 Tab 键补全 ":" 命令行。


# Reference

- [Linux 命令行大全](/Linux Command Line/12.md)
- vimtutor - D:\Vim\vim80\vimtutor.bat
- :help user-manual