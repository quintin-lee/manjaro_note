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

+ 安装软件

```
sudo pacman -S 包名
```

+ 卸载软件

```
sudo pacman -Rsnc 包名
```

+ 搜索软件包

```
sudo pacman -Ss 搜索内容
```

+ 查询已安装软件

```
sudo pacman -Qs 搜索内容
```
