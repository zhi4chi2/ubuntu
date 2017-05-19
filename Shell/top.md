```bash
top
```

# 选项

# 交互命令

- h - 显示帮助
- q - 退出



# 输出结果

top 结果分为两部分
- 系统总体状态信息
- 按 CPU 活动时间排序的进程情况表

## 系统总体状态信息

- load average - 处于可运行状态的进程数，三个值分别对应不同时间段。第一个是前 60 秒均值，第二个是前 5 分钟均值，第三个是前 15 分钟均值。小于 1.0 表示机器不忙。
- Tasks - 总进程数
  - zombie - 冻结进程数
- Cpu(s)
  - us - 用户进程（内核外进程）占用 CPU 百分比
  - sy - 系统进程（内核进程）占用 CPU 百分比
  - ni - 友好进程(nice, 即低优先级进程)占用 CPU 百分比
  - id - CPU 空闲
  - wa - 等待 I/O 操作
- Mem - 物理内存使用情况
  - total - 物理内存总量
  - used - 已使用的物理内存
  - free - 空闲的物理内存
  - buffers - 用做内存缓存的物理内存
- Swap - 交换区（虚拟内存）使用情况
  - total
  - used
  - free
  - cached - 缓冲的交换区总量

# Reference

- [Linux 命令行大全](/Linux Command Line/10.md)
- http://man.linuxde.net/top