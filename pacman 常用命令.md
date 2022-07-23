+ 清理无用软件包

```
sudo pacman -R $(pacman -Qdtq)
```

+ 清除下载的软件包

```
sudo pacman -Scc
```

+ 系统升级

```
sudo pacman -Syyu --noconfirm

(sudo pamac update)
```
