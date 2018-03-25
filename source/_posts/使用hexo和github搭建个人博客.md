---
title: 使用hexo和github搭建个人博客
---


##配置git ssh

###生成SSH密钥
查看是否已经有了ssh密钥：cd ~/.ssh
如果没有密钥则不会有此文件夹，有则备份删除
生成密钥：
ssh-keygen -t rsa -C "fozero@126.com"
按3个回车，密码为空。
```
Enter file in which to save the key (/c/Users/SKY/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```
………………
最后得到了两个文件：id_rsa和id_rsa.pub  （我这里是生成在这个目位置/c/Users/SKY/.ssh/id_rsa）
参考https://segmentfault.com/q/1010000003061640

###设置Git的user name和email
```
git config --global user.name "fozero"
git config --global user.email "fozero@126.com"
```
###测试连接是否成功
$ ssh -T git@GitHub.com
但是返回Hi fozero! You've successfully authenticated, but GitHub does not provide shell access.
在git clone使用ssh的方式

解决在天津 ssh-add id_rsa时候报错Could not open a connection to your authentication agent.
先执行ssh-agent在 ssh-add
ssh-agent bash
 ssh-add id_rsa
如果出现这个信息，说明加入成功 Identity added: id_rsa (id_rsa)

###最后，github添加SSH keys
找到并打开id_rsa.pub文件（存放于C:\Users\SKY\.ssh下），在github设置里面添加新的SSH keys，复制id_rsa.pub内容到github中即可
