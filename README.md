# CentOS playground

```shell
# 作成
vagrant up

# 確認
vagrant status

# ssh 接続
vagrant ssh

# 停止
vagrant halt

# 削除
vagrant destory
```

- ssh を Vagrantfile があるディレクトリ関係なく楽に行いたい

```shell
$ vagrant ssh-config --host centos-playground >> ~/.ssh/config

$ grep centos-playground -A 15 ~/.ssh/config
Host centos-playground
  HostName 127.0.0.1
  User vagrant
  Port 2222
  UserKnownHostsFile /dev/null
  StrictHostKeyChecking no
  PasswordAuthentication no
  IdentityFile /Users/t.kiyota/utils/centos-playground/.vagrant/machines/centos-playground/virtualbox/private_key
  IdentitiesOnly yes
  LogLevel FATAL

$ ssh centos-playground       
Last login: Tue Sep  7 02:54:30 2021 from 10.0.2.2
[vagrant@centos-playground ~]$ 
```
