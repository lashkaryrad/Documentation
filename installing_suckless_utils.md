# install Suckless Display Manager

### Cloning Suckless Repos
- ```git clone https://git.suckless.org/dwm```
- ```git clone https://git.suckless.org/dmenu```
- ```git clone https://git.suckless.org/st```

### Installing Dependencies
```bash
pacman -S xorg-server xorg-xinit libx11 libxinerama libxft webkit2gtk
```

### Configuring Xorg
1. ```vim ~/.xinitrc```
2. Append: ``` exec dwm ```

### Compile Utilities
1. dwm:
```bash
# go to dwm DIR
cd .config/dwm

# make it
make

# install it
sudo make clean installs
```

2. dmenu:
```bash
# go to dwm DIR
cd .config/dmenu

# make it
make

# install it
sudo make clean installs
```

3. st:
```bash
# go to dwm DIR
cd .config/st

# make it
make

# install it
sudo make clean installs
```