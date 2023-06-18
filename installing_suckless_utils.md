# install Suckless Display Manager

### Cloning Suckless Repos
- ```git clone https://git.suckless.org/dwm```
- ```git clone https://git.suckless.org/dmenu```
- ```git clone https://git.suckless.org/st```

### Installing Dependencies
```bash
pacman -S xorg-server xorg-xinit libx11 libxinerama libxft webkit2gtk```

### Configuring Xorg
1. ```vim ~/.xinitrc```
2. Append: ``` exec dwm ```