``` shell
sudo tee /etc/sudoers.d/kale <<< ‘kale ALL=(ALL) NOPASSWD: ALL’
sudo chmod 440 /etc/sudoers.d/kale
```

其中kale是自己的用户名
