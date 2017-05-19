ps 默认只输出与当前终端会话相关的进程信息。

```bash
ps
```



常用选项
- aux


# 选项

Linux 下的 ps 可以模拟多种 UNIX 版本中的 ps 。选项前不带 - 模拟 BSD

## x

显示所有程序，不以终端机来区分。

```bash
ps x
```

# 输出结果

## USER

进程所有者

## %CPU

CPU 使用百分比

## %MEM

内存使用百分比

## VSZ

使用虚拟内存大小

## RSS

实际使用物理内存大小。单位 KB

## TTY

TTY 显示 ? 表示没有终端。

## STAT

即 state

状态有：
- R - 正在运行或者准备运行
- S - 睡眠。等待某事件发生。
- D - 不可中断的睡眠。例如等待 I/O 操作。
- T - 暂停。
- Z - 无效或者僵尸进程。子进程被终止但还没有被父进程彻底释放掉
- < - 高优先级进程
- N - 低优先级进程

状态后还可以带其它字符表示不同的特殊特性。

## START

进程开启时间。如果超过 24 小时，显示日期。否则显示时间。

## TIME


## COMMAND


# Reference

- [Linux 命令行大全](/Linux Command Line/10.md)
- http://man.linuxde.net/ps
