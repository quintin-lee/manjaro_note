# 1. 修改/etc/sudoers文件，清徐%sudo ALL=(ALL) ALL前的注释#

# 2. 新建一个用户配置文件
``` shell
sudo tee /etc/sudoers.d/kale <<< ‘kale ALL=(ALL) NOPASSWD: ALL’
sudo chmod 440 /etc/sudoers.d/kale
```

其中kale是自己的用户名
