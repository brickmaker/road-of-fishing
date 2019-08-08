# WSL中python配置

有时候想要最新版本的python，但是不知道如何安装。

安装方法：

**安装python3.7:**

```bash
sudo apt install python3.7
```

**设定python命令：**

```bash
vim ~/.bashrc
```

在文件最后添加：

```shell
alias python='python3.7'
```

**设定pip命令：**

还是在`.bashrc`中，添加

```shell
alias pip='python3.7 -m pip'
```
