# Linux commands and configs

### <a href='#ssh-key' name = 'ssh-key'>#</a> ssh key configs

保证远程系统已配置好ssh-server之类的东西

本地创建rsa公钥密钥对：

```bash
ssh-keygen -t rsa
```

远程主机上，添加公钥：

这里要填入的公钥就是生成的公钥密钥对里的`id_rsa.pub`

```bash
mkdir ~/.ssh # if not exist
cat > ~/.ssh/authorized_keys # then input pub keys, or direct create file and write content
chmod 700 ~/.ssh
chmod 600 -R ~/.ssh/*
```


本机上使用ssh登录：

```bash
ssh -i path/to/ssh/key -P XXXX username@hostname
```

这里的`path/to/ssh/key`就是生成的密钥对里的`id_rsa`


### <a href='#scp-upload' name = 'scp-upload'>#</a> scp upload file

```bash
scp -i path/to/ssh/key -P XXXX localfile username@hostname:path/to/remote/file
```

`path/to/remote/file`用`~`就可以传到用户根目录下