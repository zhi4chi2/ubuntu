```bash
me@mypc:~$ less /etc/passwd
me@mypc:~$
```

# 术语

- window size - 由 z/w 命令定义
- screen size/screen width

# 命令

- h/H - 显示帮助
- q - 退出

移动
- 下一页 - Space/f
- 上一页 - b
- 下半页 - d
- 上半页 - u
- 上一行 - k, 前可加数字 NUM
- 下一行 - Enter/j, 前可加数字 NUM
- 右半屏 - 右箭头
- 左半屏 - 左箭头
- 文件头 - g
- 文件尾 - G
- 指定行 - Num+g/G
- 指定位置 - Num+%/p

配对
- { - 如果 top line 中有 { 则将配对的 } 放在 bottom line
- } - 如果 bottom line 中有 } 则将配对的 { 放在 top line
- [
- ]
- (
- )

定位
- m+小写字符 - mark 指定位置
- '+小写字符 - 跳到 mark 位置
- '' - 跳到前一个位置

搜索
- /characters - 向下搜索字符串
- n - 查找下一个，需要先使用 /characters 查找

# Reference

- [Linux Command Line](/Linux Command Line/3.md) - P16
- `man less`