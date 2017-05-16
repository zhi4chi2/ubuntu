```bash
me@mypc:~/test$ alias foo='cd /usr;ls;cd -'
me@mypc:~/test$ foo
bin  games  include  lib  local  locale  sbin  share  src
/home/me/test
me@mypc:~/test$ unalias foo
me@mypc:~/test$ foo
No command 'foo' found, did you mean:
 Command 'woo' from package 'python-woo' (universe)
 Command 'fop' from package 'fop' (universe)
 Command 'fgo' from package 'fgo' (universe)
 Command 'goo' from package 'goo' (universe)
 Command 'fio' from package 'fio' (universe)
 Command 'zoo' from package 'zoo' (universe)
 Command 'fog' from package 'ruby-fog' (universe)
 Command 'fox' from package 'objcryst-fox' (universe)
foo: command not found
me@mypc:~/test$ 
```


注意，在命令行定义的别名在会话结束后就消失了。


---
单独使用 alias 显示系统中的所有别名
```bash
me@mypc:~/test$ alias
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l='ls -CF'
alias la='ls -A'
alias ll='ls -alF'
alias ls='ls --color=auto'
me@mypc:~/test$ 
```
