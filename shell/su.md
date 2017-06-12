切换用户，如果省略用户名，切换为 root 。


```bash
me@mypc:~/test$ su
Password: 
su: Authentication failure
me@mypc:~/test$ su eg
Password: 
eg@mypc:/home/me/test$ exit
exit
me@mypc:~/test$ 
```


注意，在 Ubuntu 中不能切换为 root


su eg 时输入的是 eg 的密码


# -l
用 -/-l 表示使用新用户的环境
```bash
me@mypc:~/test$ su - eg
Password: 
eg@mypc:~$ pwd
/home/eg
eg@mypc:~$ exit
logout
me@mypc:~/test$ su -l eg
Password: 
eg@mypc:~$ pwd
/home/eg
eg@mypc:~$ exit
logout
me@mypc:~/test$ 
```


使用 -/-l 时，登录后的路径是 /home/eg ，不使用时登录后的路径是 /home/me/test(原来的当前路径)
