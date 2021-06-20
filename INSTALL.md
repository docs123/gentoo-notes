## By-the-handbook

[![Cooking by the book](https://i.ytimg.com/vi/2PNeNGd50pk/maxresdefault.jpg)](https://www.youtube.com/watch?v=K5tVbVu9Mkg)

Add here

## Specific configurations

### Portage

make.conf
```bash
nano /etc/portage/make.conf

USE="bluetooth networkmanager pulseaudio"
EMERGE_DEFAULT_OPTS="--ask --color=y --quiet-build --verbose"
```


### KDE
```bash
emerge xorg-x11 plasma-meta
```
