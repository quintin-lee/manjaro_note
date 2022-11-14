## 1. 换国内源

``` shell
# 运行命令，选则较快的源即可
sudo pacman-mirrors -c China -i -s
```

## 2. 通过 aria2 加速

``` shell
# 安装 aria2
sudo pacman -S aria2
# 配置 pacman, 修改 /etc/pacman.conf 文件,添加如下参数
XferCommand = /usr/bin/aria2c -s 5 %u
或
XferCommand = /usr/bin/axel -n 5 -a -o %o %u

# 这个就是调用aria2c来下载文件，-s就是设置有多少链接，设置为1-5之间，%u就是url，就是下载地址。
```
