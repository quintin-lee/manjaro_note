1.先删除fcitx4软件包.

```
sudo pacman -Rs $(pacman -Qsq fcitx)
```

2.安装fcitx5软件包.

```
sudo pacman -S fcitx5 fcitx5-configtool fcitx5-qt fcitx5-gtk fcitx5-chinese-addons
fcitx5-material-color
```

- fcitx5: 输入法基础框架主程序

- fcitx5-configtool(kcm-fcitx5)：输入法配置程序(KDE桌面环境的支持)

- fcitx5-qt: QT5程序的支持 

- fcitx5-gtk: GTK程序的支持 

- fcitx5-chinese-addons: 简体中文输入的支持，云拼音

- fcitx5-material-color：一款使用 Material Design 配色的 fcitx5 皮肤，旨在模仿 Windows 10 自带输入法的 UI

3.修改环境变量.

    修改输入法环境变量，使应用可以调用Fcitx5输入法
    将下面的内容粘贴到 ~/.xprofile (旧版本是 ~/.pam_environment)

```
export INPUT_METHOD=fcitx5
export GTK_IM_MODULE=fcitx5
export QT_IM_MODULE=fcitx5
export XMODIFIERS=@im=fcitx5
```

4.配置主题.

    使用`fcitx5-material-color`这个主题,可以参照: https://github.com/hosxy/Fcitx5-Material-Color

修改 ~/.config/fcitx5/conf/classicui.conf

```	
# 垂直候选列表
Vertical Candidate List=False
 
# 按屏幕 DPI 使用
PerScreenDPI=True
 
# Font (设置成你喜欢的字体)
Font="思源黑体 CN Medium 13"
 
# 主题
Theme=Material-Color-Blue
```
