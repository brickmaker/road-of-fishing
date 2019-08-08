# WSL 中使用 Git

WSL 中当然可以安装 Git 然后使用，但是存在的问题是，有的时候，自己从 windows 中使用 git，有的时候是用 WSL bash 打开的，这就存在换行的问题，因此需要将两者进行统一。

一种解决方案是将 Windows 上的默认换行也改成 LF(\n)：

1. windows 中的 git 设置默认换行：`git config --global core.autocrlf false`
2. windows 中编辑器默认换行改为 LF：比如在 VSCode 中，设置`"file.eol":"\n"`

在WSL中安装git使用就是了，不用作改动。