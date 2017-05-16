选项：
* -i/--interactive - 删除前需要用户确认。
* -r/--recursive - 递归删除。删除目录时'''必须'''使用。
* -f/--force - 忽略不存在的文件，并且删除已存在的文件无需确认，覆盖 -i 选项
* -v/--verbose


删除目录，必须使用 -r
```bash
me@mypc:~/test$ mkdir d
me@mypc:~/test$ rm d
rm: cannot remove 'd': Is a directory
me@mypc:~/test$ rm -r d
me@mypc:~/test$ 
```