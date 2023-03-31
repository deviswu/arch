# 安装swaywm
### 1. 联网

```shell
$ NetworkManager
$ systemctl enable NetworkManager
$ nmcli d wifi c XXX password ****
$ nmcli d wifi c XXX password **** hidden yes
```

### 2. 安装sway和必要的软件

```bash
sway  xorg-xwayland pulseaudio pavucontrol sof-firmware swaybg
thunar-volman gvfs ntfs-3g //自动挂载硬盘
thunar  tumbler//thunar的依赖包
firefox alacritty dmenu wqy-zenhei mpv vimiv ranger evince  libreoffice fbreader
lux-dl(下载工具)ranger wqy-zenhei ttf-font-awesome
```

如果安装pulseaudio后没有声音，可能是没有安装sof-firmware.

### 3. 输入法

```bash
fcitx5-im fcitx5-chinese-addons qt5-wayland
```

这三个包必须都安装，最后一个不安装会导致弹窗出不来。/etc/environment文件中添加以下几行，然后重新登。

```
GTK_IM_MODULE=fcitx
QT_IM_MODULE=fcitx
XMODIFIERS=@im=fcitx
SDL_IM_MODULE=fcitx
GLFW_IM_MODULE=ibus
```

如果您使用 i3 或 sway，开机自启动放到配置文件.config/sway/config

```
exec --no-startup-id fcitx5 -d
```

### 4. ArchLinuxCN软件仓库镜像安装

编辑/etc/pacman.conf文件

```
[archlinuxcn]
Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```

```
sudo pacman -S archlinuxcn-keyring
```

1. 安装yay
2. 安装xray-bin v2raya

### 5. 添加新用户

```
sudo useradd -m <username>
sudo passwd <username>
sudo usermo -aG wheel <username> //添加到sudo 列表
```

### 6. 截图工具

```
grim slurp swappy wl-clipboard otf-font-awesome
```

```
grim -g "$(slurp)"-| swappy -f -
```

截图工具需要字体支持否则乱码。

### 7.调整时间

```
sudo pacman -S npt
sudo ntpdate -u ntp.aliyun.com
```
### 8.其他软件

foot nautilus wofi和dmenu atril zuthura
