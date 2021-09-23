## 1. Windows 激活时绑定的微软帐号中获取 bitblocker 的恢复密钥

## 2. manjaro 安装 dislocker

``` shell
yay -S dislocker
```

## 3. 手动挂载

``` shell
# 创建两个目录用来解密和挂载加密分区的
sudo mkdir -p /media/bitlocker
sudo mkdir -p /media/bitlockermount

# 解密BitLocker的加密文件系统
sudo dislocker ${encrypted_partition} -p ${recovery_password} -- /media/bitlocker

# 挂载加密分区
sudo mount -o loop -t ntfs /media/bitlocker/dislocker-file /media/bitlockermount
```

## 4. 自动挂载

``` shell
# 在 /etc/fstab 中添加下面两行:
<partition> /media/bitlocker fuse.dislocker recovery-password=<password>,nofail 0 0

/media/bitlocker/dislocker-file /media/bitlockermount auto nofail 0 0

# 上例中是使用 recovery-password 来解密的，对应的你也可以使用 user-password 和 bekfile 来代替。
```
