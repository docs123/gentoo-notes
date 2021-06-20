## By-the-handbook

[![Cooking by the book](https://i.ytimg.com/vi/2PNeNGd50pk/maxresdefault.jpg)](https://www.youtube.com/watch?v=K5tVbVu9Mkg)

Add here

## Specific configurations

### Portage

make.conf
```bash
nano /etc/portage/make.conf

USE="bluetooth networkmanager pulseaudio"
EMERGE_DEFAULT_OPTS="--ask --ask-enter-invalid --color=y --quiet-build --verbose"
```


### KDE
```bash
emerge xorg-x11 plasma-meta
```

## References

+ [Manpage of EMERGE](https://dev.gentoo.org/~zmedico/portage/doc/man/emerge.1.html)
+ [Manpage of PORTAGE](https://dev.gentoo.org/~zmedico/portage/doc/man/portage.5.html)
+ [Global USE flags index](https://packages.gentoo.org/useflags/global)
+ [Gentoo USE Flags - Part 2 - YouTube](https://www.youtube.com/watch?v=IG_paP7NXYI)
+ [Help with package.accept_keywords - reddit](https://removeddit.com/r/Gentoo/comments/ndsoy5/help_with_packageaccept_keywords/)
